# SCOPE AND DELIMITATION

This section outlines the boundaries, operational capabilities, and deliberate exclusions of the study, defining the exact research coverage and system constraints under which SENSEY was developed and evaluated.

### Scope of the Study

The scope of this research is bounded by the following parameters:

* **Target Subject and Population:** The primary beneficiary of this study is the **visually impaired teacher** actively managing an indoor educational environment. The evaluation phase utilized a visually impaired participant (or blindfolded subjects simulating visual impairment) to evaluate system navigation and status monitoring capabilities.
* **Study Area and Environment:** The physical evaluation of SENSEY was conducted inside a simulated, structured classroom environment measuring $10\text{ m} \times 8\text{ m}$, configured to replicate standard school layouts at the Polytechnic University of the Philippines – Santa Rosa Campus, Tagapo, Laguna, Philippines.
* **Functional Capabilities:** The developed blind assistive device is bounded by two primary indoor operational features:
  1. *Student Status Monitoring:* Real-time, NPU-accelerated tracking of up to **three (3) students** positioned across a $3 \times 3$ seating grid, classifying two postures (*Sitting*, *Standing*) and four active behaviors (*Attentive*, *Raising Hand*, *Looking Away*, *Praying*) using the **YOLOv8m-pose** estimation algorithm. Additionally, to maintain student privacy during continuous monitoring, the system integrates a real-time, keypoint-guided face-blurring algorithm that automatically anonymizes student faces on the visual monitor interface.
  2. *Walkable Path Navigation:* Real-time detection and mapping of low-profile floor hazards and typical classroom furniture across three lateral safety lanes (Left, Center, Right) using the **YOLOv8m** object detection algorithm and a gravity-aligned 3D spatial coordinate rotation algorithm.
* **Research Instruments:** The technical evaluation utilized three standardized testing protocols: a 480-sample student seating grid census test, a 320-sample static obstacle distance calibration test, and a 30-run comparative dynamic navigation trial comparing traditional white cane navigation against SENSEY configurations.
* **Timeframe:** The development, integration, and empirical testing of the SENSEY system were completed within the Academic Year 2025–2026.

---

### Delimitations of the Study

The following operational constraints, environmental conditions, and deliberate system design omissions define the boundaries outside the scope of this project:

* **Omission of Haptic Feedback:** Physical vibration actuators were deliberately omitted from SENSEY's design to reduce the device's physical weight, complex wiring, and high battery energy demands. All multimodal feedback is delivered exclusively through real-time auditory speech reports and a spatial audio metronome.
* **Omission of Student Facial Recognition:** Biometric student facial identification features were intentionally excluded from SENSEY's software architecture to comply with strict data privacy regulations, such as the Philippine Data Privacy Act of 2012 (Republic Act No. 10173). Instead, the system is delimited to non-identifying postural and behavioral tracking, actively applying a dynamic, keypoint-guided face-blurring mask to preserve student anonymity on the monitor interface while conserving the edge-processor's memory.
* **Omission of Outdoor and GPS Navigation:** This study is strictly delimited to indoor classroom environments. Features such as outdoor GPS mapping, cellular tracking, or high-range ultrasonic sensor arrays were excluded, as the device is specialized for indoor spatial navigation and localized obstacle avoidance.
* **Hardware Physical Blind Spot:** The system's close-range detection capability is physically limited by the OAK-D Lite depth sensor's baseline distance, which introduces a close-range "dead zone" for any objects located closer than **$0.4\text{ meters}$** ($40\text{ cm}$) from the camera lens.
* **Visual Occlusions:** The system cannot detect students or low-profile floor hazards that are completely hidden from the camera's direct line of sight (e.g., behind solid wooden desks, podiums, or other students). The **YOLOv8m-pose** algorithm requires at least partial visibility of human keypoint joints to perform postural classifications.
* **Lighting Constraints:** SENSEY is delimited to indoor environments with standard classroom lighting (approximately 300 to 500 lux). Extreme low-light settings (darkened rooms) or direct, overexposed sunlight hitting the camera lens will degrade the depth calculation and pose-detection accuracy.

---
---
PAKIBASA LAHAT. MAGTATANONG AKO SAINYO SINASABI KO NA SAINYO PALANG, KUNG AYAW HANAP NA KAGRUPO SA LOWER YEAR MAY NEXT SEM PANAMAN
---
---

# PARTITION: METHODOLOGICAL COMPLIANCE ANALYSIS

Below is the detailed methodological analysis proving how this updated, privacy-inclusive Scope and Delimitation section satisfies your department's academic guidelines:

### **1. Integration of Student Privacy & Face Blurring (Slide 16 Compliance)**
* **The Challenge:** Continuous classroom monitoring raises serious ethical and legal concerns regarding student privacy, particularly under local laws like the Philippine Data Privacy Act of 2012. 
* **Our Alignment:** 
  * Under the **Scope**, we explicitly added the system's real-time, keypoint-guided face-blurring capability as a key functional feature.
  * Under the **Delimitations**, we justified the omission of facial recognition by linking it directly to these data privacy laws, explaining that the system is intentionally designed to preserve student anonymity. This is a highly robust, ethical, and defensive argument for your final defense panel.

### **2. Correction of the Student Sample Count**
* **Our Alignment:** The maximum student limit remains correctly set to **three (3) students** in the Scope block, maintaining absolute logical consistency with your 3x3 seating grid experimental methodology for Chapter 4.

### **3. Full APA Layout Compliance**
* **Our Alignment:** Adheres strictly to APA structural headings, with clear bold hierarchies and formal terminology tailored specifically to the **visually impaired teacher** as the target user.
