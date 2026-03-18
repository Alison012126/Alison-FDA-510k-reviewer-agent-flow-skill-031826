FDA 510(k) Review Guidance for Magnetic Resonance Diagnostic Devices (MRDDs)
Document Version: 1.0 Date Issued: October 26, 2023 Prepared By: CDRH, Office of Product Evaluation and Quality (OPEQ) Reviewer Role: Expert FDA Regulatory Officer

I. Introduction and Scope of Review
This guidance document is designed to assist FDA regulatory officers in conducting a thorough and efficient review of Premarket Notification (510(k)) submissions for Magnetic Resonance Diagnostic Devices (MRDDs). It provides a structured approach to assessing compliance with regulatory requirements, recognized consensus standards, and scientific principles to ensure the safety and effectiveness of MRDDs prior to market clearance. This document supplements the general requirements for 510(k) submissions by providing device-specific considerations pertinent to MRDDs.

Regulatory Context: MRDDs are classified as Class II medical devices under 21 CFR 892.1000 and require premarket notification (510(k)) and a determination of substantial equivalence before marketing. This classification reflects the moderate risk associated with these devices, necessitating robust documentation and testing to assure safety and effectiveness.

Definition and Scope: A Magnetic Resonance Diagnostic Device is identified under 21 CFR 892.1000(a) as a device intended for general diagnostic use to present images reflecting spatial distribution and/or magnetic resonance spectra reflecting frequency and distribution of nuclei exhibiting nuclear magnetic resonance. This includes hydrogen-1 (proton) imaging, sodium-23 imaging, hydrogen-1 spectroscopy, phosphorus-31 spectroscopy, and chemical shift imaging.

This guidance is applicable to 510(k) submissions for:

Magnetic Resonance Imaging (MRI) and Magnetic Resonance Spectroscopy (MRS) systems.
Individual components and accessories (e.g., RF coils, patient tables, physiological gating devices).
Modifications to existing MRDDs, components, or accessories that could significantly affect their safety or effectiveness, or represent a major change in intended use.
The MRI system components of dual-modality devices (e.g., PET/MRI systems).
Product Codes: Reviewers should verify that the appropriate product codes are identified in the submission:

LNH: Nuclear Magnetic Resonance Imaging System
LNI: Nuclear Magnetic Resonance Spectroscopic System
MOS: Magnetic Resonance Specialty Coil
Electronic Product Radiation Control (EPRC) Compliance: As electronic products under section 531(2) of Subchapter C of the FD&C Act, MRDDs are subject to radiological health requirements outlined in 21 CFR Parts 1000 through 1050. This includes general and specific performance standards (21 CFR Parts 1010-1050), reporting and recordkeeping (21 CFR Part 1002), notification and corrective actions for non-compliant products (21 CFR Parts 1003 and 1004), and importation (21 CFR Part 1005). Reviewers must confirm adherence to these requirements.

Use of Consensus Standards: FDA-recognized consensus standards provide a streamlined path to demonstrate compliance with certain regulatory requirements. For MRDDs, this includes the updated IEC 60601-2-33 (4th edition), which redefines the main magnetic field (B0) hazard area to ≥ 0.9 mT (previously 0.5 mT). While use of consensus standards is voluntary, FDA highly recommends referencing them with a Declaration of Conformity and supporting documentation. Reviewers should consult the FDA Recognized Consensus Standards Database for the current editions.

II. Review of General 510(k) Content Requirements (21 CFR 807.87)
The 510(k) submission must include all information required by 21 CFR 807.87. This section provides specific considerations for MRDDs within each element.

A. Indications for Use (IFU)
The IFU statement is fundamental, defining the medical purpose of the device and the patient population for which it is intended. It forms the basis for all safety and effectiveness evaluations.

Reviewer Checklist for IFU:

Clarity and Specificity: Is the IFU statement clear, concise, and specific about what the device diagnoses or helps manage? Avoid vague terms.
Consistency: Does the IFU align precisely across all submission documents (e.g., 510(k) Summary, labeling, performance claims, promotional materials)? Any inconsistencies warrant clarification.
Scope of Use: Does the IFU describe general diagnostic use for imaging and/or spectroscopy, reflecting the spatial distribution or frequency/distribution of nuclei?
Clinical Claims: Are there any specific clinical claims (e.g., disease identification, prognosis, staging, prevention of morbidity/mortality) that would necessitate clinical study data? Such claims are generally beyond the scope of a typical 510(k) unless supported by robust clinical evidence, often requiring a Q-submission for discussion with the Agency.
Protocols vs. Indications: Does the submission clearly differentiate between general indications and specific imaging protocols (e.g., "Pediatric Brain protocol" is acceptable, but "Pediatric Epilepsy Foci identification protocol" would likely imply a specific clinical indication requiring further justification)?
RF Coils and Accessories: For coils and accessories, does the IFU specify compatibility with particular MRI system(s), including manufacturer and field strength?
B. Device Description
A comprehensive device description is crucial for demonstrating substantial equivalence and understanding the technological characteristics of the MRDD. Reviewers must scrutinize each component described below.

(1) Magnet
The main magnet is central to an MRDD's function and safety.

Field Strength and Type: Verify the stated field strength (e.g., 1.5T, 3T) and magnet type (superconducting, resistive, permanent). Note: A change in main static magnetic field is generally considered a significant modification requiring a new 510(k).
Dimensions: Assess the dimensions of the patient-accessible bore space.
Installation Type: Identify the installation type (fixed, mobile, interventional, transportable).
Design Characteristics:
Weight: Note for facility planning and safety.
Cryogens and Boil-off Rates: If superconducting, assess cryogen management and safety implications.
Bore Dimensions: Important for patient comfort and accessibility.
Shielding Method: Evaluate the type and effectiveness of shielding.
Shimming Method: Understand how field homogeneity is maintained.
Performance Characteristics:
Decay Characteristics (Quench): Review data on magnetic field decay in the event of a quench (time to 20 mT).
Fringe Field Maps: Critically review 3D fringe field maps, ensuring contours for 0.5 mT, 0.9 mT, 3 mT, 5 mT, 10 mT, 20 mT, 40 mT, and 200 mT are clearly depicted. The 0.9 mT contour is particularly important for defining the controlled access area per IEC 60601-2-33 (4th edition).
Temporal Stability: Evaluate stability of the magnetic field (ppm/hr) over prolonged periods.
Spatial Homogeneity: Assess field homogeneity (ppm/volume) within the imaging volume.
(2) Gradient System
The gradient system is responsible for spatial encoding and is a primary source of acoustic noise and potential peripheral nerve stimulation (PNS).

Illustration: Review a dimensioned illustration of the gradient tube.
Shielding and Cooling: Assess the design for gradient coil shielding and cooling mechanisms.
Maximum Gradient Amplitude, Rise Time, Slew Rate: Verify these parameters for each axis (T/m, ms, T/m/s).
PNS Control:
Describe implementation of cardiac and peripheral nerve stimulation control.
Detail hardware or software mechanisms to limit dB/dt (time rate of change of magnetic field) for systems capable of exceeding 20 T/s.
Confirm the level of gradient output at which the operator is notified of possible PNS.
Assess how the operator is informed about potential PNS and measures to avoid painful stimulation.
Operating Modes: Identify and understand the implemented operating modes (Normal, First Level Controlled, Second Level Controlled) and how users navigate them, particularly concerning dB/dt limits.
(3) Radiofrequency (RF) System
The RF system generates and receives the MR signal.

Architecture: Describe the overall architecture of the RF transmit-receive system.
Channels, Power, Duty Cycle: Verify the number of transmit and receive channels, amplifier peak power, and duty cycle.
Quadrature Transmit Mode: Confirm the ability to operate in quadrature transmit mode and how the user identifies/selects it.
(4) RF Coils
RF coils are critical components, directly impacting image quality and patient safety (e.g., heating).

Type: Specify coil type (transmit, receive, transmit/receive).
Hardware Characteristics: Describe geometry, materials, and dimensions.
Design: Detail the coil design (e.g., linear, quadrature, phased array, multi-channel transmit).
Intended Use: Resonant nuclei, frequencies, and anatomical region of interest.
Schematics and Circuit Diagrams: Essential for understanding coil design, safety features, and decoupling methods.
Decoupling Method(s): For receive-only coils, describe how decoupling from the transmit field is achieved.
(5) SAR Management and Control System
Specific Absorption Rate (SAR) is a key safety parameter, reflecting RF energy deposition in tissue.

Control Implementation: Describe how whole-body averaged (avg-WB), partial body (PB), head-averaged, local (10g-averaged) SAR, and specific absorbed energy (SAR over examination time) control is implemented.
Operating Modes: Explain system operating modes related to SAR limits and user navigation.
Accuracy and Uncertainty: Provide specifications for accuracy and uncertainty in console-reported SAR values.
User Communication: Describe how energy deposition information and associated warnings/feedback are communicated to the user.
(6) Pulse Sequences
Pulse sequences define how MR signals are acquired and are critical for image contrast and diagnostic utility.

Diagram: A pulse sequence diagram is essential.
Type and Contrast: Specify the pulse sequence type (e.g., spin echo, gradient echo, EPI, 2D/3D) and contrast characteristics (T1, T2 weighting, fat saturation).
k-space Trajectory: Describe the k-space sampling method (e.g., spiral, Cartesian).
Associated Options: List any associated options (shimming, parallel imaging, saturation pulses).
Coil Preferences/Limitations: Identify any specific coil requirements or limitations.
Accessory Equipment: List required accessories (e.g., gating devices, elastography drivers).
Image Reconstruction: Summarize the image reconstruction method (e.g., FFT, compressed sensing).
(7) Imaging Protocols
Protocols are workflows combining multiple pulse sequences for specific clinical applications.

Target Anatomy: Specify the target anatomical region for each manufacturer-provided protocol.
Pulse Sequences: List the individual pulse sequences included in each protocol.
Coil Preference/Restriction: Note any specific coil requirements.
Contrast Media: Indicate if the protocol is intended for use with exogenous contrast media.
(8) Image Processing
Image processing algorithms operate on acquired image data, distinct from reconstruction algorithms.

Inputs: Describe inputs, their data formats, and methods of input (e.g., feed from other modules, manual input).
Functional Description: Provide a clear functional description of the algorithm(s).
User Interaction: Characterize the level of user interaction (automated, semi-automated, manual; editability of results).
Outputs: Describe outputs, their data formats, and how they are displayed.
Software Documentation:
Documentation Level: Generally, a "Basic Documentation Level" as per FDA guidance "Content of Premarket Submissions for Device Software Functions" is expected. Reviewers should confirm the appropriate level for the specific device functions.
Cybersecurity: If the device is a "cyber device" under section 524B(c) of the FD&C Act, required cybersecurity documentation (as per "Cybersecurity in Medical Devices: Quality System Considerations and Content of Premarket Submissions" guidance) must be present. This is a critical safety consideration.
Off-The-Shelf (OTS) Software: If OTS software is used, additional information as recommended by FDA guidances ("Off-The-Shelf Software Use in Medical Devices" and "Cybersecurity for Networked Medical Devices Containing Off-The-Shelf (OTS) Software") should be included.
(9) Accessories
A comprehensive list of accessories is needed for overall system understanding and safety assessment.

List: Provide a complete list of all accessories (e.g., physiological monitoring, EKG leads, pulse oximeters, gating devices, elastography drivers, patient positioners).
(10) Additional Information
Patient Table: Dimensions, positioning accuracy, and maximum supported weight.
Patient Communication: Description of nurse call or "panic button" functionality.
RF Shielding: Recommended RF shielding, implementation of "Special Environment" specifications in IEC 60601-1-2, and integrity maintenance during operation.
Fixed Parameter Option (FPO): If FPO (e.g., FPO:B per IEC 60601-2-33) is implemented, describe its application.
III. Safety and Performance Testing
To demonstrate substantial equivalence, the submission must include robust testing data. Not all tests apply to all devices or accessories; relevance should be determined based on the specific submission.

A. Relevant Standards
Reviewers must verify that the applicant has appropriately identified and applied relevant FDA-recognized consensus standards.

Table 1: Key Regulatory Standards for MRDDs and Their Application

| Standard Category | Standard Designation | Primary Application | Reviewer Focus | | :---------------- | :------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | | MRDD Specific | IEC 60601-2-33 (4th Ed.) | Basic safety and essential performance of MR equipment for medical diagnosis. Harmonized with 0.9 mT hazard area. | Verify Declaration of Conformity; scrutinize compliance with B0 hazard area, acoustic noise, SAR, and other particular requirements. | | Performance (NEMA) | NEMA MS 1 | Signal-to-Noise Ratio (SNR) in MR images. | Confirm SNR measurements and acceptance criteria for all coils. | | | NEMA MS 2 | 2D Geometric Distortion in MR images. | Evaluate distortion measurements across orientations and acceptance criteria. | | | NEMA MS 3 | Image Uniformity in MR images. | Assess uniformity measurements/maps and acceptance criteria for all coils. | | | NEMA MS 4 | Acoustic Noise Measurement Procedure for MR. | Compare reported acoustic output with IEC 60601-2-33 requirements. | | | NEMA MS 5 | Slice Thickness in MR imaging. | Verify FWHM values and acceptance criteria. | | | NEMA MS 6 | SNR & Image Uniformity for Single-Channel, Non-Volume Coils. | Ensure specific coil types are evaluated appropriately. | | | NEMA MS 8 | Characterization of SAR for MRI Systems. | Cross-reference with RF energy deposition data. | | | NEMA MS 9 | Characterization of Phased Array Coils for MR. | Focus on phased array coil performance. | | | NEMA MS 10 | Determination of Local SAR in MR. | Cross-reference with local SAR measurements. | | | NEMA MS 12 | Quantification and Mapping of Geometric Distortion for Special Applications. | Review for specialized applications requiring high geometric accuracy. | | General Medical Device Safety | ANSI/AAMI ES60601-1 / IEC 60601-1 | General requirements for basic safety and essential performance of medical electrical equipment. | Ensure overall electrical and mechanical safety; assess compliance with U.S. national differences. | | EMC | IEC 60601-1-2 | Electromagnetic disturbances - requirements and tests (Collateral standard). | Review EMC test reports and compliance with specified limits. | | Biocompatibility | ISO 10993-1 | Biological evaluation of medical devices – Part 1: Evaluation and Testing within a Risk Management Process. | Confirm biocompatibility for all patient-contacting materials. | | Connectivity/Image Formats | NEMA PS 3.1 - 3.20 (DICOM) | Digital Imaging and Communications in Medicine. | Verify DICOM compatibility for image exchange, particularly for clinical image submissions. |

B. Electrical, Mechanical, Structural, and Related System Safety
Primary Safety Standards: Compliance with ANSI/AAMI ES60601-1, IEC 60601-1 (with U.S. national differences), and IEC 60601-1-2 (EMC) is expected. Review test reports and declarations of conformity.
EMC: Ensure comprehensive EMC information is provided as per the FDA guidance "Electromagnetic Compatibility (EMC) of Medical Devices."
Wireless Technology: If wireless technology is incorporated, assess compliance beyond IEC 60601-1-2 using the FDA guidance "Radio-Frequency Wireless Technology in Medical Devices" to address susceptibility to electromagnetic interferences.
C. Physical Laboratory Testing
The submission must contain objective evidence from physical laboratory testing to support the safety and effectiveness claims.

(1) Performance Testing (Imaging)
Signal to Noise Ratio (SNR): Measured SNR values for all coils and pre-determined pass/fail acceptance criteria. Consistency across protocols.
Geometric Distortion: Distortion measurements in sagittal, coronal, and transverse orientations, with acceptance criteria. Focus on clinical relevance.
Image Uniformity: Image uniformity measurements and/or gray-scale uniformity maps for all coils, with acceptance criteria.
Slice Thickness: Full-width-half-maximum (FWHM) values and acceptance criteria.
Spatial Resolution: High contrast spatial resolution using suitable phantoms for clinical pulse sequences with the smallest FOV.
Image Contrast Validation: For new pulse sequences, demonstration of desired contrast behavior (e.g., fat saturation demonstrating adequate fat signal suppression in phantom).
(2) Performance Testing (Spectroscopy)
For systems with spectroscopy protocols, phantom testing should be detailed, including test methods, pulse sequences, coils, phantom geometry/composition, target anatomical region, and RF hardware.

Spatial Localization Accuracy: Comparison of desired and actual volume for spectroscopy voxels.
Spectral Resolution: FWHM of the water resonance using clinical protocols (single voxel, CSI).
Signal to Noise Ratio: Ratio of peak amplitude to standard deviation of background for key metabolites (e.g., NAA, lactate).
Water Suppression: Ratio of water peak area with and without suppression.
Decoupling: Comparison of SNR with and without decoupling.
Spectral Data Processing: Validation of post-processing techniques.
(3) Safety Testing
Acoustic Noise: Measured acoustic output (maximum gradient or clinical acoustic noise), including unweighted peak sound pressure level (Lpeak) and time integral of A-weighted sound pressure level (LAeq). Ensure compliance with IEC 60601-2-33 limits.
Gradient-induced Nerve Stimulation (PNS): For systems capable of dB/dt > 20 T/s, review volunteer studies (minimum 11 subjects) to determine thresholds for mild and painful PNS. If painful stimulation is possible, confirm how it is avoided and that mechanisms are in place to prevent patient harm.
RF Energy Deposition (SAR):
Volume-transmit coils: Measured whole-body averaged, head averaged, and/or partial body SAR values. Test method (pulse energy, calorimetry) must be specified. Report both measured and scanner-displayed SAR values with uncertainty boundaries.
Surface transmit coils: Measured local 10g-averaged SAR values, both measured and scanner-displayed, with uncertainty boundaries.
Multi-channel transmit coils: Discussion comparing peak local (10g-averaged) SAR to peak values in quadrature volume coils conforming to IEC 60601-2-33 limits. This should cover the entire patient population and anatomical scan landmarks. If computational models are used, validate them and provide uncertainty data.
Surface Heating of RF Receive Coils: Temperature rise measurements for all receive-only coils, especially at predetermined local hot spots. Testing in normal operating conditions and a single fault condition (unplugged coil in bore). Justification for acceptable temperature rise and no patient risk.
Biocompatibility: Address biocompatibility for all patient-contacting materials, referencing ISO 10993-1 and related FDA guidance.
Fixed Parameter Options (FPO): If FPO (e.g., FPO:B) is implemented, provide data demonstrating operation within these limits.
Table 2: Key Device Description and Testing Requirements for MRDDs

| MRDD Component/Aspect | Key Device Description Elements | Essential Performance/Safety Testing | | :-------------------- | :------------------------------ | :----------------------------------- | | Magnet | Field strength, type, bore dimensions, installation, cryogens, shielding, shimming. Fringe field maps (0.5-200 mT), temporal stability, spatial homogeneity, quench decay. | Fringe field validation (safety zones), temporal stability, spatial homogeneity, quench characteristics. | | Gradient System | Illustration, shielding/cooling, max amplitude, rise time, slew rate. PNS control mechanisms (hardware/software dB/dt limits). Operating modes (Normal, FLC, SLC). | Gradient-induced nerve stimulation (PNS) volunteer studies (if dB/dt > 20 T/s), acoustic noise (Lpeak, LAeq). Geometric distortion, slice thickness. | | RF System | Architecture (transmit-receive channels), amplifier peak power, duty cycle. Quadrature transmit mode availability. | RF Energy Deposition (SAR) for transmit coils. | | RF Coils | Type (Tx/Rx), hardware (geometry, materials), design (linear, quadrature, phased array), intended use (nuclei, freq, anatomy), schematic, circuit diagrams, decoupling. | SNR, Image Uniformity, Surface Heating (receive-only), RF Energy Deposition (transmit-only/Tx-Rx), Biocompatibility (if patient-contacting). | | SAR Management | Description of avg-WB, PB, head-averaged, local SAR control. Operating modes, accuracy/uncertainty of reported SAR. User warnings/feedback. | Validation of console-reported SAR accuracy. | | Pulse Sequences | Diagram, type, contrast, k-space trajectory, options, coil preference, accessories, reconstruction method. | SNR, Image Contrast Validation, Spatial Resolution, Slice Thickness, Image Uniformity, Geometric Distortion. | | Imaging Protocols | Target anatomy, list of pulse sequences, coil preference, contrast media use. | (Derived from underlying pulse sequence and system performance) | | Image Processing | Inputs, functional description, user interaction, outputs. Software documentation (Basic Level), Cybersecurity, OTS software info. | Functional verification of algorithms, validation of outputs. Cybersecurity risk assessment and mitigation. | | Accessories | List of all included accessories. | Relevant safety and performance testing for each accessory (e.g., biocompatibility, electrical safety). | | System Safety | N/A (cross-cutting) | ANSI/AAMI ES60601-1, IEC 60601-1, IEC 60601-1-2 (EMC), ISO 10993-1. |

IV. Clinical Images
Clinical images are essential to demonstrate the device's ability to generate diagnostic quality images consistent with the IFU.

Reviewer Checklist for Clinical Images:

Diagnostic Quality: Do the provided images demonstrate sufficient diagnostic quality across the range of claimed pulse sequences and anatomical regions?
Newly Introduced Systems: For new systems, confirm sample clinical images are provided for all pulse sequences.
Pulse Sequence Coverage: If a pulse sequence is used in multiple clinical protocols, do the images support its ability to achieve desired contrast characteristics in those protocols? Scientific rationale and a limited set may suffice for multiple protocols.
Format: Images must be in electronic DICOM format.
Patient Identifiers: Verify that all patient identifiers have been removed.
Accompanying Information: Each image should be accompanied by a description of:
Target anatomical site.
Scan parameters employed.
Total imaging time.
Radiologist Attestation (Alternative): If a full set of images is not submitted, verify that a statement from a U.S. Board Certified radiologist attesting to diagnostic quality is included. This must be accompanied by:
A description of the sequences and anatomical regions reviewed by the radiologist.
Full explanation of any issues encountered during image evaluation.
A small, representative subset of clinical images.
V. Device Modifications
Understanding when a modification to an existing device triggers a new 510(k) is crucial for compliance. Reviewers should consult 21 CFR 807.81(a)(3) and relevant FDA guidances ("Deciding When to Submit a 510(k) for a Change to an Existing Device" and "Deciding When to Submit a 510(k) for a Software Change to an Existing Device"). For devices with a Predetermined Change Control Plan (PCCP) under FDORA section 515C, changes consistent with the plan may not require a new 510(k).

Table 3: Common MRDD Modifications Requiring a New 510(k) and Associated Review Focus

| Modification Type | Trigger for New 510(k) (Examples) | Primary Safety/Effectiveness Impact | Required Supporting Data/Review Focus | | :-------------------------- | :----------------------------------------------------------------------- | :------------------------------------------------------------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | | Main Static Magnetic Field | Any change in the main static magnetic field. | Altered resonant frequency, affecting both safety and effectiveness. | SNR, geometric distortion, image uniformity (max FOV). Magnetic field homogeneity, temporal stability (ppm/hr). | | Gradient System | Change to gradient system (e.g., max amplitude, slew rate, shielding). | Altered PNS potential, slice selection efficacy, acoustic output. | Geometric distortion, slice profile thickness (representative volume coil). Acoustic output assessment. Any changes to PNS control. | | RF Body Transmit Coil | Change to integrated RF body transmit coil. | Modified RF energy output, affecting safety and effectiveness. | RF energy deposition (SAR), SNR, image uniformity. | | Other Transmit Coils | Change in coil transmit architecture (e.g., multi-transmit). | Altered safety (heating) and effectiveness (image quality). | RF energy deposition (SAR), coil surface heating, biocompatibility (if patient-contacting), SNR, image uniformity. (Material changes for non-patient contacting housing unlikely to require 510(k)). | | RF Receive Coils | Introduction of a new RF receive-only coil. | Altered system performance, affecting safety and effectiveness. | SNR, image uniformity, coil surface heating, biocompatibility (if patient-contacting). (Modification of existing coils may not require 510(k) unless safety/effectiveness is significantly impacted). | | Pulse Sequences | Introduction of a new pulse sequence affecting intended use or safety (e.g., metal artifact reduction). | Changed intended use, potential safety concerns, altered contrast. | SNR, appropriate contrast behavior. Data supporting the intended use of the new pulse sequence. (Modifications not affecting intended use generally don't require 510(k)). | | Imaging Protocols | Major change in intended use (e.g., adding a "pediatric epilepsy foci identification protocol"). | Changed diagnostic claims, patient population, or risk profile. | Factors: changes to target anatomy, desired contrast characteristics, coil restrictions, contrast media requirements. (Re-ordering existing sequences or adding cleared protocols to similar models generally do not require a new 510(k)). |

VI. Labeling
Labeling (User Manual, Summary Specification Sheet, RF Coil Labels, Site Planning Information) must meet the requirements of 21 CFR 807.87(e) and 21 CFR Part 801. It must be clear, accurate, and provide sufficient information for safe and effective use.

Reviewer Checklist for Labeling:

A. RF Coil Labeling
Clear Identification: Does the label on all RF coils (except integrated body coil) clearly identify whether it is a transmit/receive or receive-only coil?
B. Summary Specification Sheet
Comprehensive Summary: Does it provide a concise overview of the system configuration, components, and available applications?
Magnet: Field strength, type, bore size, installation type, design characteristics (weight, cryogens/boil-off, shielding, shimming), performance (quench decay time to 20mT, temporal stability, spatial homogeneity), and maximum |B|, |grad|B||, |B|.|grad|B|| in patient-accessible values.
Gradient System: Max amplitude, rise time, slew rate, shielding/cooling info, peak acoustic output (peak and A-weighted).
RF Subsystem: Resonant frequencies, number of Tx/Rx channels, amplifier peak power, duty cycle, operating modes.
RF Coils: For each coil: type, design, intended use (nuclei, frequency, anatomical region).
Imaging Protocols: Summary of protocols and/or pulse sequences.
Patient Table: Dimensions and max supported patient weight.
Post-processing features: Summary and software version.
Accessories: List of all provided accessories.
C. User Manual
Regulatory Statement: Contains "Caution: Federal law restricts this device to sale by or on the order of a physician" (21 CFR Part 801).
Indications for Use: Identical to the IFU statement in Form 3881 and 510(k) Summary.
Patient Screening: Recommended procedures, clear contraindications, and special procedures. Referencing ASTM F2503 for MR Safe, MR Conditional, MR Unsafe is encouraged.
Magnetic Field Information: Value and location of maximal |B|, |grad|B||, and |B|.|grad|B|| in patient-accessible areas.
Emergency Procedures: Instructions for rapid patient removal.
Excessive Noise: If noise exceeds 99 dBA, specifies required patient hearing protection. Specifies noise level at control panel and operator hearing protection recommendations.
Controlled Access Area:
States user responsibility for establishing a controlled access area around the MRDD where the magnetic field does not exceed 0.9 mT (or 0.5 mT as a more conservative option), consistent with IEC 60601-2-33.
Provides recommendations for size, shape, and identification (markings, barriers, signs per ISO 7010).
Explains dangers of introducing non-MR compatible equipment and that even MR Conditional devices require adherence to specific safe use conditions.
Liquid Cryogens (if applicable): Information on hazards, procedures after gas release, precautions against lack of oxygen, use of non-magnetic containers, flammable materials near containers. Maintenance/inspection info and frequency of cryogen level checks.
Operating Modes: Clear explanation of system operating modes.
Emergency Shutdown: Clear explanation of operation and appropriate use of the emergency field shutdown unit.
Emergency Responder Precautions: Recommends discussion with local fire department and establishment of site-specific emergency procedures.
Quality Assurance: Recommended QA procedures, phantom specifications, and frequency of procedures.
Maintenance: Recommended maintenance schedules and whether performed by user or service personnel.
Cleaning and Disinfection: Instructions for reusable patient-contacting components.
D. Site Planning Information
Audio and Visual Contact: Design specifications for equipment enabling audio and visual contact with the patient.
Magnetic Fringe Field: 3D magnetic field plots for a typical installation, including 0.5 mT, 0.9 mT, 3 mT, 5 mT, 10 mT, 20 mT, 40 mT, and 200 mT iso-magnetic field contours, with distance scale and magnet outline.
Liquid Cryogens and Cryogenic Gases (if applicable): Design of a venting system for superconducting magnets to an area outside the examination room, designed to withstand a quench.
Decay Characteristics of the Magnetic Field: Time from emergency field shut-down activation to field strength falling to 20 mT. Instructions for actuator installation.
Additional Information: Implementation of "Special Environment" specifications in IEC 60601-1-2.
Table 4: Key Labeling Requirements for MRDDs

| Labeling Document | Critical Information for Review
| User Manual | IFU consistency, patient screening, MR safety information (B0, B1, dB/dt, SAR safety limits). Emergency procedures. Patient communication/safety equipment. Noise levels and protection. Controlled Access Area (0.9 mT). Cryogen safety. Operating modes. Emergency shutdown. QA procedures. Maintenance. Cleaning/Disinfection. | | **** | Required <br> Type: User Manual <br> Audience: Healthcare Professionals, Patients (if specific sections). | | 510(k) Status and Application Scope | Clear identification of whether the present application is for a new system, a modification, a component, or a dual-modality device. | Ensure the scope of the 510(k) (new device, modification) is clearly stated in the cover letter and submission summary. If a modification, verify if it falls under existing guidance for requiring a new 510(k) or if a PCCP is in place. | | Preamble and Regulatory Overview | Introduction, scope, and regulatory background (21 CFR 892.1000, Class II, EPRC). Reference to current FDA-recognized standards (e.g., IEC 60601-2-33 4th edition). | Confirm accurate referencing of updated standards. Verify that the applicant acknowledges EPRC requirements. Check for appropriate use of voluntary consensus standards and declarations of conformity. | | Indications for Use (IFU) | Specificity and consistency of IFU. Avoidance of disease-specific or diagnostic claims without clinical evidence. Specification of compatible MRI systems for coils/accessories. | Assess if the IFU aligns with typical 510(k) scope for MRDDs. If specific clinical claims are made, evaluate the adequacy of supporting evidence. Check for consistency across all labeling and promotional materials. | | Device Description – Core Components | Detailed descriptions of: Magnet (field strength, type, dimensions, fringe fields, stability). Gradient System (amplitude, slew rate, PNS control, operating modes). RF System (architecture, channels, power, duty cycle, quadrature mode). RF Coils (type, design, hardware, intended use, schematics, circuit diagrams, decoupling). SAR Management System (control methods, operating modes, accuracy, user communication). Pulse Sequences (diagrams, type, contrast, k-space, options). Imaging Protocols (target anatomy, sequences, coil restrictions). Image Processing (inputs, algorithms, user interaction, outputs). Software Documentation (Basic Level, Cybersecurity, OTS). Accessories list. | Verify technical specifications against established safety limits and industry norms. Scrutinize fringe field maps and SAR management details. Ensure comprehensive software documentation, especially for cybersecurity risks and OTS software. | | Electrical, Mechanical, Structural, and Related System Safety | Declarations of conformity and test reports for: ANSI/AAMI ES60601-1, IEC 60601-1 (U.S. differences), IEC 60601-1-2 (EMC). Specific information for wireless technology. | Confirm complete test reports and declarations. Review wireless technology sections for comprehensive EMC and interference mitigation strategies as per FDA guidance. | | Physical Laboratory Testing – Performance | Detailed test methods, phantoms, and results for: Imaging (SNR, Geometric Distortion, Image Uniformity, Slice Thickness, Spatial Resolution, Image Contrast Validation). Spectroscopy (Spatial Localization Accuracy, Spectral Resolution, SNR, Water Suppression, Decoupling, Spectral Data Processing). | Evaluate test methodologies and raw data. Assess if pre-determined pass/fail acceptance criteria are adequately justified and met for all performance metrics. | | Physical Laboratory Testing – Safety | Detailed test methods, phantoms/volunteer studies, and results for: Acoustic Noise. Gradient-induced Nerve Stimulation (if dB/dt > 20 T/s). RF Energy Deposition (SAR for volume, surface, and multi-channel coils, including uncertainty). Surface Heating of RF Receive Coils (normal & fault conditions). Biocompatibility. Fixed Parameter Options (FPO compliance). | Critically review all safety testing. Ensure volunteer studies for PNS are robust. Pay close attention to SAR measurements, scanner-displayed values, and uncertainty. Verify hot spot analysis for coil heating and biocompatibility documentation. | | Clinical Images | Sample clinical images (DICOM, de-identified) demonstrating diagnostic quality for all pulse sequences/protocols, with accompanying metadata (anatomy, parameters, time). Alternatively, Board Certified Radiologist attestation with representative subset and explanation of issues. | Assess image quality and consistency with claimed IFU and technical specifications. Verify de-identification and complete metadata. If attestation is provided, confirm its comprehensiveness and support by a representative subset of images. | | Labeling – Specific Documents | RF Coil Labeling (Tx/Rx vs. Rx-only). Summary Specification Sheet (comprehensive system specs). User Manual (IFU, patient screening, magnetic field info, emergency procedures, noise, controlled access area, cryogens, operating modes, emergency shutdown, QA, maintenance, cleaning/disinfection). Site Planning Information (audio/visual, fringe field plots, cryogen venting, field decay characteristics). | Verify all mandatory labeling elements are present and accurate. Focus on patient safety instructions (screening, controlled access, emergencies, cryogens) and technical details provided for installation/site planning. Ensure consistency across all labeling. |

Review Officer's Final Determination Considerations:
Upon completion of the review, the officer will consolidate findings to determine whether the submitted MRDD is substantially equivalent to a legally marketed predicate device. This involves:

Assessment of Intended Use: Is the intended use the same as the predicate? If not, is the new intended use supported by appropriate data?
Technological Characteristics Comparison: Are the technological characteristics identical to the predicate? If not, do the differences raise new questions of safety or effectiveness?
Data Evaluation: Do the performance and safety data (including testing, software, and labeling) adequately address any new questions of safety or effectiveness raised by technological differences?
Risk-Benefit Profile: Does the submission demonstrate that the benefits of the device outweigh its risks when used as intended?
This comprehensive guidance and checklist are designed to facilitate a thorough and consistent review process for MRDD 510(k) submissions, ultimately ensuring that safe and effective devices reach patients.
