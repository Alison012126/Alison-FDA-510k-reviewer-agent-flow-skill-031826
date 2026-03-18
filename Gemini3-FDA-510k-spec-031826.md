Agentic Medical Device Reviewer – Technical Specification
1. Executive Summary
The Agentic Medical Device Reviewer is a modern, AI-powered single-page application (SPA) designed to streamline, automate, and enhance the regulatory review process for FDA 510(k) medical device submissions. Built entirely on a modern React frontend architecture, the application leverages the latest advancements in Large Language Models (LLMs)—specifically Google's Gemini 3.1 Pro and Gemini 2.5 Flash—to digest complex medical documentation, extract key performance metrics, and generate standardized, highly structured review memos.
The primary objective of this system is to reduce the cognitive load on regulatory affairs professionals and FDA reviewers by automating the extraction of critical data points from dense PDF or text submissions. The application enforces strict output formatting, requiring the AI to generate comprehensive markdown documents (typically 2000–4000 words) that include specific tabular data (e.g., exactly 5 tables per major review section) to ensure consistency across reviews.
Key capabilities include:
Client-Side Document Processing: Secure, in-browser PDF parsing and text extraction, ensuring sensitive proprietary medical device data does not need to be uploaded to a third-party parsing server.
Multi-Stage AI Pipeline: A sequential workflow that guides the user from initial submission summarization, through FDA database intelligence gathering, review guidance generation, and finally, a comprehensive preliminary review.
Custom AI Skills: An extensible interface allowing users to define arbitrary "skills" (e.g., "Extract all ISO standards") and apply them dynamically to the ingested context.
"WOW" User Interface: A highly polished, responsive, and accessible UI featuring 10 distinct Pantone-inspired color themes, Light/Dark mode toggling, and internationalization (English/Traditional Chinese) support.
Rich Text Editing and Export: Integrated Markdown rendering with seamless toggling between raw text editing and formatted preview, coupled with one-click exports to .md and .txt formats.
This document serves as the definitive technical specification for the current implementation, detailing the system architecture, state management, component hierarchy, utility functions, and prompt engineering strategies.
2. System Architecture
The application follows a Client-Side Single-Page Application (SPA) architecture. There is no dedicated backend server for business logic; instead, the application relies on direct client-to-API communication with the Google Gemini API.
2.1 Architectural Principles
Decentralized Processing: Heavy lifting such as PDF parsing and Markdown rendering is offloaded to the client's browser using Web Workers (via pdfjs-dist).
Ephemeral State: All application state (uploaded documents, generated reviews, API keys) is stored in memory using React Context. Refreshing the page clears the state, ensuring that sensitive data is not inadvertently persisted across sessions unless explicitly downloaded by the user.
Component-Driven Design: The UI is broken down into modular, reusable React components (e.g., MarkdownEditor, Sidebar) to promote maintainability and testability.
Utility-First Styling: Tailwind CSS is used exclusively for styling, allowing for rapid iteration and dynamic theme generation using CSS variables.
2.2 High-Level Data Flow
Input Phase: The user provides input via file upload (PDF, TXT, MD) or direct text pasting.
Processing Phase: If a PDF is uploaded, pdfjs-dist extracts the text. The user configures the LLM parameters (Model selection, API Key).
Execution Phase: The application constructs a highly specific prompt combining the user's instructions, the extracted text, and strict formatting rules. This prompt is sent to the Gemini API via the @google/genai SDK.
Rendering Phase: The API returns a Markdown string, which is saved to the global state. The MarkdownEditor component reacts to this state change, parsing the Markdown into HTML using react-markdown and displaying it to the user.
Export Phase: The user reviews the output, makes manual edits if necessary, and downloads the final document to their local filesystem.
3. Technology Stack
The application is built using a modern, enterprise-ready frontend stack:
3.1 Core Framework
React 19.0.0: The core UI library, utilizing functional components and Hooks (useState, useEffect, useContext, useRef) for state and lifecycle management.
TypeScript 5.8: Provides static typing across the entire codebase, ensuring type safety for API responses, state objects, and component props.
Vite 6.2: The build tool and development server, chosen for its extremely fast Hot Module Replacement (HMR) and optimized Rollup-based production builds.
3.2 Styling and UI
Tailwind CSS 4.1: The utility-first CSS framework. Version 4 introduces the new @theme directive, which is heavily utilized to define the dynamic Pantone color palettes.
Lucide React 0.546: A comprehensive library of clean, consistent SVG icons used throughout the application (e.g., FileText, Search, Zap, Settings).
Clsx & Tailwind-Merge: Utility libraries used to conditionally join class names and resolve Tailwind class conflicts, particularly useful in the Sidebar component for active/inactive states.
3.3 AI and Data Processing
@google/genai 1.29.0: The official Google GenAI SDK used to communicate with the Gemini models (gemini-3-flash-preview, gemini-2.5-flash).
pdfjs-dist 5.5.207: Mozilla's robust PDF parsing library. Used to extract raw text from uploaded PDF files directly in the browser.
React-Markdown 10.1.0: A React component that safely parses and renders Markdown strings into HTML elements, supporting standard Markdown syntax (tables, lists, bold, italics).
4. Core Data Models & State Management
State management is handled natively using React's Context API (createContext, useContext) combined with the useState hook. This lightweight approach avoids the boilerplate of Redux while providing global state access to all deeply nested components.
4.1 The AppState Interface
The entire application state is defined by the AppState interface in src/store.tsx:
code
TypeScript
export type Theme = 'light' | 'dark';
export type Language = 'en' | 'zh';
export type PantoneStyle = 
  | 'classic-blue' | 'living-coral' | 'ultra-violet' | 'greenery' 
  | 'rose-quartz' | 'serenity' | 'marsala' | 'radiant-orchid' 
  | 'emerald' | 'tangerine-tango';

export interface AppState {
  // Global UI Settings
  theme: Theme;
  language: Language;
  pantoneStyle: PantoneStyle;
  
  // Authentication
  apiKey: string;
  
  // Module Outputs (Markdown Strings)
  submissionSummary: string;
  fdaInfo: string;
  reviewGuidance: string;
  preliminaryReview: string;
  customSkillResult: string;
  followUpQuestions: string;
}
4.2 The AppProvider Context
The AppProvider component wraps the root of the application, initializing the state with default values (Light theme, English language, Classic Blue style). It exposes an updateState function that accepts a Partial<AppState>, allowing any component to merge updates into the global state seamlessly.
code
TypeScript
const updateState = (updates: Partial<AppState>) => {
  setState((prev) => ({ ...prev, ...updates }));
};
This pattern is crucial for the multi-stage pipeline. For example, the PreliminaryReviewTab needs to read both state.submissionSummary and state.reviewGuidance to construct its prompt. By storing these in the global context, data flows easily between isolated tabs.
5. User Interface (WOW UI) & Theming
The "WOW UI" requirement is fulfilled through a highly dynamic, CSS-variable-driven theming system integrated directly into Tailwind CSS v4.
5.1 Dynamic Pantone Palettes
The application supports 10 distinct styles based on the Pantone Color of the Year. These are defined in src/index.css using Tailwind's @theme directive:
code
CSS
@theme {
  --color-pantone-classic-blue: #0f4c81;
  --color-pantone-living-coral: #ff6f61;
  --color-pantone-ultra-violet: #5f4b8b;
  --color-pantone-greenery: #88b04b;
  /* ... other colors ... */
}
When the user selects a style from the Sidebar, the AppContent component dynamically updates the document.body.className:
code
TypeScript
useEffect(() => {
  document.body.className = `theme-${state.theme} style-${state.pantoneStyle}`;
}, [state.theme, state.pantoneStyle]);
The CSS then maps the specific Pantone color to a generic --primary variable:
code
CSS
.style-classic-blue { --primary: var(--color-pantone-classic-blue); }
.style-living-coral { --primary: var(--color-pantone-living-coral); }

/* Tailwind utility mappings */
.bg-primary { background-color: var(--primary); }
.text-primary { color: var(--primary); }
.border-primary { border-color: var(--primary); }
This allows components to simply use classes like bg-primary or text-primary, and the color will instantly transition across the entire app when the user changes their preference.
5.2 Dark Mode Integration
Dark mode is implemented using Tailwind's standard dark: variant. The theme-dark class applied to the body sets the base background to bg-gray-900 and text to text-gray-100. Every UI component (cards, textareas, buttons, sidebars) includes explicit dark: classes to ensure a cohesive experience in low-light environments.
5.3 Responsive Sidebar Navigation
The Sidebar component (src/components/Sidebar.tsx) provides the main navigation.
Desktop: It acts as a fixed, 64-width (16rem) left-hand rail.
Mobile: It transforms into an off-canvas drawer, toggled via a floating hamburger menu button. The transition uses Tailwind's transform transition-transform duration-300 for smooth sliding animations.
6. Module Specifications (The 6 Tabs)
The application is divided into 6 distinct functional modules, each represented by a Tab component. Every tab follows a similar layout pattern: a CSS Grid with two columns on large screens (lg:grid-cols-2). The left column contains the inputs, controls, and configuration, while the right column contains the MarkdownEditor displaying the output.
6.1 510(k) Submission Summary (SubmissionSummaryTab.tsx)
Purpose: To ingest raw 510(k) submission documents and transform them into a highly structured, standardized Markdown summary.
Inputs:
File Upload (PDF, TXT, MD) via a hidden <input type="file"> triggered by a styled button.
Direct text paste via a <textarea>.
If a PDF is uploaded, a "PDF Extraction Settings" panel appears, allowing the user to specify a Start Page and End Page. This is critical for massive submissions where the user only wants to analyze specific sections (e.g., the Executive Summary or Performance Testing).
Processing:
If a PDF is present, extractTextFromPdf is called.
The extracted text (or pasted text) is injected into a strict prompt:
"You are an expert FDA regulatory reviewer. Analyze the following 510(k) submission summary. Transform the document into an organized markdown document. Include exactly 5 tables summarizing key information. The final output should be comprehensive, around 2000-3000 words."
Outputs:
The resulting Markdown is saved to state.submissionSummary and rendered in the right-hand panel.
6.2 FDA Info Search (FDAInfoTab.tsx)
Purpose: To leverage Google's Search Grounding capabilities to find external, up-to-date FDA regulatory information, recalls, or predicate device data related to the current submission.
Inputs:
A customizable prompt textarea (defaults to requesting a 3000-4000 word summary).
Implicitly relies on state.submissionSummary as context.
Processing:
This module specifically uses the generateContentWithSearch utility function, which injects the { googleSearch: {} } tool into the Gemini API configuration.
The prompt combines the user's query with the first 5000 characters of the submissionSummary to provide context to the model without exceeding token limits unnecessarily.
Outputs:
The search-grounded Markdown is saved to state.fdaInfo.
6.3 Review Guidance (ReviewGuidanceTab.tsx)
Purpose: To process internal FDA review instructions or guidance documents and generate an actionable checklist for the reviewing officer.
Inputs:
File Upload (PDF, TXT, MD) or direct text paste.
Processing:
The prompt instructs the model to act as an expert reviewer and create an organized guidance document.
Strict Constraints: The prompt explicitly demands "a review checklist and exactly 5 tables" and a length of "3000-4000 words".
Outputs:
The generated guidance is saved to state.reviewGuidance.
6.4 Preliminary Review (PreliminaryReviewTab.tsx)
Purpose: The core analytical engine of the application. It cross-references the applicant's submission against the generated review guidance to produce a preliminary assessment.
Inputs:
A customizable prompt.
Implicitly requires both state.submissionSummary and state.reviewGuidance to be populated. If they are not, a yellow warning banner is displayed, and the "Conduct Review" button is disabled.
Processing:
The prompt concatenates the user's instruction, the first 15,000 characters of the submission summary, and the first 15,000 characters of the review guidance. This massive context window allows the Gemini model to perform deep comparative analysis.
The prompt enforces the generation of exactly 5 tables and a 3000-4000 word length.
Outputs:
The comprehensive report is saved to state.preliminaryReview.
6.5 Custom Skill (CustomSkillTab.tsx)
Purpose: To provide an escape hatch for specific, ad-hoc analytical tasks that don't fit into the standard pipeline (e.g., "Extract all biocompatibility standards", "Translate the indications for use to Spanish").
Inputs:
Skill Description: A textarea defining the behavior of the skill.
Prompt: A textarea defining the immediate instruction.
Implicitly uses state.submissionSummary as the target data.
Processing:
Combines the prompt, the skill description, and the submission summary into a single API call.
Outputs:
Saved to state.customSkillResult.
6.6 Follow-up Questions (FollowUpQuestionsTab.tsx)
Purpose: To conclude the review process by generating a list of actionable questions for the applicant based on gaps or concerns identified in the preliminary review.
Inputs:
Implicitly requires state.preliminaryReview and state.submissionSummary.
Processing:
The prompt instructs the model to generate "exactly 20 comprehensive follow-up questions" formatted as a numbered list.
It feeds the first 10,000 characters of both the preliminary review and the submission summary to the model.
Outputs:
Saved to state.followUpQuestions.
7. Core Utilities & Services
The application relies on several abstracted utility files to handle complex logic outside of the React component tree.
7.1 PDF Processing (src/lib/pdf.ts)
Handling PDFs entirely on the client side is critical for data privacy. The application uses pdfjs-dist.
Implementation Details:
Worker Configuration: PDF.js requires a Web Worker to parse files without blocking the main UI thread. The worker is configured dynamically using a CDN link matching the installed version:
code
TypeScript
pdfjsLib.GlobalWorkerOptions.workerSrc = `//cdnjs.cloudflare.com/ajax/libs/pdf.js/${pdfjsLib.version}/pdf.worker.min.mjs`;
Extraction Logic: The extractTextFromPdf function converts the File object to an ArrayBuffer, loads it into the PDF.js document model, and iterates through the requested pages.
Page Range Support: It accepts startPage and endPage parameters. It loops from startPage to Math.min(endPage, pdf.numPages), extracting text items and concatenating them with a page marker (--- Page X ---) to maintain structural context for the LLM.
7.2 LLM Integration (src/lib/gemini.ts)
This file wraps the @google/genai SDK, providing a clean interface for the React components.
Implementation Details:
Singleton Pattern: The getGenAI function ensures that the GoogleGenAI client is only instantiated once.
API Key Resolution: It attempts to use the API key passed from the UI state (state.apiKey). If that is empty, it falls back to process.env.GEMINI_API_KEY (which is injected by Vite during the build process based on the .env file). If neither exists, it throws a synchronous error.
Standard Generation (generateContent): Accepts a prompt, model name, and optional system instructions.
Search-Grounded Generation (generateContentWithSearch): Identical to standard generation, but injects the tools: [{ googleSearch: {} }] configuration, enabling the model to query the live internet for up-to-date FDA data.
7.3 Markdown Editor & Export (src/components/MarkdownEditor.tsx)
A highly reusable component used in the right-hand column of every tab.
Implementation Details:
View Modes: Maintains an internal isEditing boolean state.
false (Preview Mode): Renders the content using <Markdown> from react-markdown. It uses Tailwind Typography (prose dark:prose-invert max-w-none) to ensure the rendered HTML (headings, tables, lists) looks beautiful and respects the current theme.
true (Edit Mode): Renders a raw <textarea> allowing the user to manually correct the AI's output. Changes are propagated up to the global state via the onChange prop.
Export Functionality: The handleDownload function creates a Blob from the markdown string, generates a temporary URL.createObjectURL, and programmatically triggers a hidden <a> tag click to download the file to the user's machine. It supports both .md and .txt extensions, dynamically generating the filename based on the component's title prop (e.g., 510(k)-submission-summary.md).
8. Prompt Engineering Strategy
A significant portion of the application's success relies on the specific phrasing of the prompts sent to the Gemini models. The prompts are hardcoded within the component logic but are designed to enforce strict constraints:
Role Playing: Prompts begin by establishing a persona: "You are an expert FDA regulatory reviewer." This primes the model to use appropriate regulatory terminology and adopt a formal, analytical tone.
Explicit Formatting: The prompts explicitly demand Markdown format.
Quantitative Constraints: To meet the specific requirements of the design, the prompts include hard constraints:
"Include exactly 5 tables summarizing key information."
"The final output should be comprehensive, around 2000-3000 words." (or 3000-4000 words depending on the tab).
"generate exactly 20 comprehensive follow-up questions"
Context Injection: The prompts dynamically interpolate the text extracted from the user's files. To prevent token limit exhaustion and reduce latency, the application truncates the context (e.g., .substring(0, 15000)) before sending it to the API. While Gemini 1.5/2.0 models have massive context windows, truncating ensures the application remains snappy during rapid iteration.
9. Security & Deployment Considerations
9.1 API Key Management
Environment Variable: In a deployed environment (like Google Cloud Run), the GEMINI_API_KEY is injected securely via environment variables and exposed to the Vite build process.
User Override: Users can provide their own API key via the Sidebar. This key is stored only in React state. It is never saved to localStorage, sessionStorage, or cookies. If the user closes the tab, the key is wiped from memory, ensuring high security for Bring-Your-Own-Key (BYOK) scenarios.
9.2 Data Privacy
Medical device submissions often contain highly confidential intellectual property.
Because PDF parsing is done entirely on the client side using pdfjs-dist, the raw PDF file is never uploaded to a server.
Only the extracted text is sent to the Google Gemini API. Users must ensure their organization's agreement with Google covers the transmission of this data to the LLM.
9.3 Build and Deployment
The application is built using npm run build, which invokes Vite to bundle the React application into static HTML, CSS, and JS files located in the dist/ directory.
These static files can be hosted on any standard web server (Nginx, Apache) or static hosting service (Vercel, Netlify, Firebase Hosting).
The included package.json defines a dev script that binds to 0.0.0.0:3000, ensuring compatibility with containerized development environments.
10. Future Extensibility
The modular architecture allows for straightforward future enhancements:
Additional LLM Providers: The gemini.ts file can be abstracted into an llm.ts interface, allowing integration with OpenAI (GPT-4o) or Anthropic (Claude 3.5 Sonnet) by adding new SDKs and updating the Model dropdowns in the UI.
Persistent Storage: The AppProvider could be updated to sync state with Firebase Firestore or local IndexedDB, allowing users to save and resume reviews across sessions.
Advanced Document Parsing: Integration with OCR libraries (like Tesseract.js) could be added to the pdf.ts utility to handle scanned, non-searchable PDFs.
Localization: The state.language property is currently a placeholder for future i18n implementation. A library like react-i18next could be integrated to swap out UI strings based on this state.
20 Comprehensive Follow-up Questions
Context Window Limits: Currently, the application truncates context strings (e.g., .substring(0, 15000)) before sending them to the Gemini API. Given that Gemini models support context windows of up to 1M+ tokens, should we remove this hardcoded truncation to allow for the analysis of massive, multi-hundred-page submissions?
PDF OCR Capabilities: The current pdfjs-dist implementation extracts embedded text. If a user uploads a scanned PDF (images only), the extraction will fail. Should we integrate a client-side OCR library like Tesseract.js, or offload OCR to a cloud service?
API Key Persistence: Currently, user-provided API keys are lost on page refresh. Would you prefer we securely store the API key in the browser's localStorage so users don't have to re-enter it every time they open the app?
Export Formats: The application currently exports to .md and .txt. Would it be beneficial to add a PDF export feature (e.g., using html2pdf.js or jspdf) so reviewers can generate final, formatted reports directly?
State Persistence: If a user accidentally closes the browser tab, all their generated reviews and uploaded text are lost. Should we implement an auto-save feature using IndexedDB to persist the AppState locally?
Multi-Language UI Implementation: The UI includes a language toggle (English/Traditional Chinese), but the UI strings are currently hardcoded in English. Should we prioritize implementing a full i18n framework (like react-i18next) to translate the interface?
Prompt Customization: The core prompts (e.g., "Include exactly 5 tables") are hardcoded in the component files. Should we expose these system prompts in a "Settings" modal so advanced users can tweak the exact instructions sent to the AI?
Table Formatting: The prompt requests "exactly 5 tables", but the LLM decides the columns and content. Should we provide the LLM with a strict JSON schema or Markdown template to ensure the tables always have the exact same column headers (e.g., "Test Type", "Acceptance Criteria", "Result")?
Error Handling for Hallucinations: LLMs can occasionally hallucinate regulatory facts. Should we add a prominent disclaimer to the UI, or implement a "Verification" step where the AI cites the exact page number from the uploaded PDF for every claim it makes?
File Size Limits: Is there a maximum file size we should enforce for PDF uploads to prevent the browser from crashing due to memory exhaustion during the arrayBuffer conversion?
Streaming Responses: The UI currently shows a "Processing..." spinner until the entire response is generated. Should we implement the generateContentStream API so the user can see the Markdown being typed out in real-time?
Model Selection Expansion: The app currently supports Gemini 3 Flash Preview and Gemini 2.5 Flash. Should we add support for Gemini 1.5 Pro for tasks requiring deeper reasoning, even if it is slower and more expensive?
FDA Database Integration: The "FDA Info Search" uses Google Search grounding. Would it be more accurate to integrate directly with the openFDA API to query specific predicate device databases (e.g., the 510(k) releasable database) instead of relying on general web search?
Checklist Interactivity: The "Review Guidance" tab generates a checklist in Markdown. Should we parse this Markdown and render actual, clickable HTML checkboxes that the user can interact with and save their progress?
Custom Skill Library: The "Custom Skill" tab requires the user to type the skill description every time. Should we implement a "Skill Library" where users can save, name, and quickly select their frequently used custom prompts?
Token Usage Tracking: Should we add a UI element that tracks and displays the estimated token usage for each API call, helping users monitor their potential API costs?
Concurrent Processing: Currently, the user must wait for one tab to finish processing before moving to the next. Should we implement background processing so a user can start the "FDA Info Search" while the "Submission Summary" is still generating?
Theme Customization: The app provides 10 Pantone styles. Should we add a color picker to allow users to define a completely custom primary color, rather than restricting them to the predefined list?
Document Comparison: A common regulatory task is comparing a new submission to a predicate device. Should we add a "Predicate Comparison" tab that allows uploading two PDFs and generates a gap analysis table?
Accessibility (a11y): Have specific accessibility standards (e.g., WCAG 2.1 AA) been mandated for this application? If so, we should conduct an audit on the contrast ratios of the Pantone colors and ensure all interactive elements have proper ARIA labels.
