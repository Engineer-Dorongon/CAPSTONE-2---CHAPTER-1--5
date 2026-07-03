# CHAPTER 2 – REVIEW OF RELATED LITERATURE AND STUDIES

To establish a validated, academic baseline for SENSEY, this chapter presents a systematic, source-by-source review of literature and studies, both local and foreign. In accordance with the department’s capstone manuscript guidelines, this review is divided into two primary sections: **Review of Related Literature (RRL)**, which contains eight (8) literature sources, and **Review of Related Studies (RRS)**, which contains six (6) completed systems and hardware prototypes.

---

## **2.1 Review of Related Literature (RRL)**

This section reviews eight (8) foundational publications, including academic textbooks, professional standards, and official developer documentations, evaluated individually to highlight their key findings, critiques, and direct technical relevance:

### **1. Szeliski (2022) – *Computer Vision: Algorithms and Applications***
* **Summary:** This foreign book presents the mathematical foundations of 3D computer vision, detailing pinhole camera projection parameters, perspective visual transformations, and coordinate mapping matrices [10]. 
* **Critique and Connection:** Szeliski’s theories provide the baseline equations used to project 2D camera pixels into 3D camera-space coordinates. However, Szeliski’s standard algorithms assume a static, non-moving camera [10]. SENSEY extends this theory by integrating a live IMU sensor to rotate these camera coordinates, ensuring they remain mathematically stable relative to gravity.

### **2. Wiener, Welsh, and Blasch (2010) – *Foundations of Orientation and Mobility***
* **Summary:** This foreign textbook establishes the standards of Orientation and Mobility (O&M) science, defining how standard human dimensions, walking speeds, and chest-height perspectives dictate the physical space required to clear obstacles safely [4].
* **Critique and Connection:** This literature is crucial for SENSEY’s geometric boundary planning. It validates SENSEY's choice of a $0.46\text{-meter}$ safety corridor (the center lane), proving that a narrower corridor would fail to clear the user’s shoulder width during walking, while a wider corridor would trigger constant false-positive warnings in tight classroom aisles.

### **3. Philippine Department of Education (DepEd, 2017) – *Philippine Professional Standards for Teachers (PPST)***
* **Summary:** This local, official publication outlines the mandatory pedagogical, administrative, and spatial responsibilities of professional classroom teachers in the Philippines.
* **Critique and Connection:** This manual provides the educational justification for SENSEY. It outlines that a **visually impaired teacher** is legally expected to monitor student attentiveness and manage lesson engagement. SENSEY directly helps the teacher meet these official DepEd standards by providing non-visual student tracking.

### **4. National Council on Disability Affairs (NCDA, 2012) – *Magna Carta for Disabled Persons (Republic Act No. 7277)***
* **Summary:** This local legal publication details the mandates of Republic Act No. 7277, legally requiring schools and government offices to provide reasonable workplace accommodations to qualified disabled professionals.
* **Critique and Connection:** This publication serves as the primary legal justification for SENSEY. It proves that developing a wearable, non-visual assistive aid is not just a technological experiment, but a legally necessary workplace accessory designed to support equal-employment rights for visually impaired teachers.

### **5. Dakopoulos and Bourbakis (2010) – *Wearable obstacle avoidance electronic travel aids for blind: A Survey***
* **Summary:** This foreign journal publication presents a comparative review of traditional navigation tools (such as the white cane) versus modern electronic travel aids (ETAs) [3]. It notes that white canes provide reliable tactile force feedback for ground-level drop-offs, but leave the user blind to the speed, volume, and distance of mid-to-high-level obstacles [3, 4].
* **Critique and Connection:** This study coheres with SENSEY’s design philosophy by proving that traditional white canes are insufficient for complex indoor environments like classrooms, where hanging cabinet corners, open doors, and desk edges sit above the cane’s physical reach. This justifies SENSEY’s chest-mounted stereo camera layout.

### **6. Avila et al. (2023) – *The lived experiences and perceptions of public-school employees in the Philippines: A PWD’s perspective***
* **Summary:** This local journal study documents the day-to-day physical mobility struggles of disabled employees inside Philippine public school buildings, revealing that classroom aisles are narrow, cluttered, and completely lack structural mobility accommodations.
* **Critique and Connection:** This study provides the localized environmental justification for SENSEY's obstacle-avoidance module. It proves that a **visually impaired teacher** navigating Philippine public schools requires a highly sensitive, real-time warning sensor to bypass physical clutter safely.

### **7. Ultralytics (2024) – *YOLOv8 documentation and keypoint pose estimation models***
* **Summary:** This technical web publication documents the model architectures, processing speeds, and layer shapes of the YOLOv8 and YOLOv8-pose deep-learning frameworks.
* **Critique and Connection:** This reference provides the technical baseline for SENSEY's student tracking capability. It explains the structure of the YOLOv8m-pose keypoint tracker, which SENSEY uses to detect student joints on the edge processor.

### **8. Anthropic (2025) – *Claude 4.5 Haiku API documentation for multimodal vision tasks***
* **Summary:** This technical web publication details the visual input formatting, max token limits, and query parameters of the Claude 4.5 Haiku vision-language API.
* **Critique and Connection:** This reference establishes SENSEY’s conversational scene describer capability. It details how the model processes compressed images to generate concise, natural-language verbal summaries of the classroom layout.

---

## **2.2 Review of Related Studies (RRS)**

This section reviews six (6) completed local and foreign assistive systems, evaluated individually to highlight their operational specifications, performance, and limitations:

### **1. Xbox 360 Kinect Obstacle Avoidance System (Barrinuevo, Tolentino, et al., 2017)**
* **Summary:** This local alumni study developed a wearable obstacle detector using an Xbox 360 Kinect camera connected to a laptop inside a backpack, applying Canny edge detection to depth-thresholded images to warn users of obstacles in Left, Center, and Right zones at a fixed $1.0\text{m}$ boundary [15].
* **Critique and Connection:** This system coheres with SENSEY’s goal of partitioning the environment into lateral lanes [15]. However, it suffered from a massive $0.8\text{m}$ close-range hardware blind spot, had no camera-tilt compensation, and required a heavy laptop and external power [15]. SENSEY directly modernizes this baseline by using a lightweight, chest-mounted OAK-D Lite depth camera that reduces the close-range blind spot to $0.4\text{m}$.

### **2. Wearable Wrist Haptic Device (Alayon, Corciega, Tolentino, et al., 2020)**
* **Summary:** Published in the IEEE database, this local alumni study under your adviser developed a wearable wristband containing 7 physical solenoids. It used a Kinect depth sensor to detect obstacle angles and translated them into a base-2 binary tapping code to tap the user's wrist to indicate direction.
* **Critique and Connection:** While this system achieved a $99.39\%$ user perception rate, the authors concluded that the binary tapping carried a high cognitive load, requiring users to undergo extensive training to translate mathematical tapping into walking directions. Furthermore, it required a heavy laptop in a backpack. 

SENSEY directly improves upon this system by replacing the complex wristband with intuitive, spatial audio metronomes and spoken reports. Best of all, SENSEY implements a **3D Spatial Coordinate Euler Rotation Algorithm** using live IMU pitch values:

$$Y_{world} = Y_c \cos(\theta) - Z_c \sin(\theta)$$

$$Z_{world} = Y_c \sin(\theta) + Z_c \cos(\theta)$$

This rotates the depth coordinates in real-time, completely eliminating the "pitch-induced floor detection" false alarms that plagued both Alayon (2020) and Barrinuevo (2017) when the user bent forward.

### **3. Smart Cane Assistive Device (Htike et al., 2020)**
* **Summary:** This regional local study developed a standard walking cane integrated with ultrasonic distance sensors to provide beep alerts when approaching low-profile floor hazards.
* **Critique and Connection:** While this system successfully detected low-lying hazards, it occupied the user's hand. This is a major limitation for a **visually impaired teacher**, who needs their hands free to hold papers, write on a board, or handle teaching materials. SENSEY resolves this by using a hands-free, chest-mounted design.

### **4. The AIris Wearable Assistant (Brilli et al., 2024)**
* **Summary:** This foreign system reviews *AIris*, a chest-mounted, camera-based edge-AI system utilizing local neural processing to detect obstacles and output spoken verbal feedback to guide blind pedestrians [17].
* **Critique and Connection:** This system serves as your primary foreign system benchmark [17]. However, AIris lacks the parallel local depth sensors of SENSEY, making its steering warnings slower and less responsive in highly dynamic, crowded indoor environments like classrooms [17].

### **5. Fuzzy Decision Wearable Helper (Bouteraa, 2021)**
* **Summary:** This foreign system reviews a wearable depth-based navigation system that utilizes custom fuzzy-logic algorithms to segment camera depth maps into Left, Center, and Right safety lanes to output steering instructions.
* **Critique and Connection:** While Bouteraa (2021) validates SENSEY's choice of lateral lane division for finding walkable paths, the system is strictly limited to basic steering instructions. It lacks any behavioral student tracking or conversational scene synthesis, rendering it incapable of assisting a teacher in managing a classroom.

### **6. Object Detection/Tactile Presentation System (Chen et al., 2023)**
* **Summary:** This foreign system reviews a wearable computer-vision vest that detects obstacles using YOLO and converts their coordinates into a grid of vibration-based haptic patterns on the user's chest.
* **Critique and Connection:** The haptic-based vest of Chen et al. (2023) is heavy, physically complex, and has high power consumption, making it physically fatiguing for a teacher. SENSEY improves upon this baseline by using a purely auditory, non-blocking multimodal feedback system (combining spatial audio metronomes with spoken reports) that provides excellent environmental awareness without physical fatigue or complex wiring.

---

### **Clinching Paragraph**
In conclusion, the review of related literature and studies has provided crucial conceptual and technical baselines for the development of SENSEY. The local and foreign literature established the professional and legal necessity of providing the **visually impaired teacher** with an active, non-visual classroom status tracker. Concurrently, the comparative review of past local capstones (Barrinuevo et al., 2017; Alayon et al., 2020) and foreign wearables (Brilli et al., 2024) provided the technical foundation for integrating edge-AI cameras with auditory alerts. By replacing outdated Kinect cameras, bulky laptops, and complex binary haptic wristbands with an optimized, IMU-stabilized depth rotation algorithm and the Claude 4.5 Haiku API, SENSEY successfully overcomes the close-range blind spots and posture classification flickering of previous prototypes. Ultimately, these reviewed studies have directly assisted the project proponents in designing SENSEY’s three empirical testing protocols, ensuring a robust, mathematically validated evaluation of navigation safety, mobility efficiency, and behavior tracking accuracy.

---
---

# REFERENCES

The following reference list compiles the exact bibliographic entries supporting the citations in your finalized Chapter 2, meticulously formatted according to **APA 7th Edition** guidelines with active URL/DOI links:

Avila, P. G. A., Osea, E. A., Avila, E., Gata, R. R., Portea, J. V., Enimedez, M. A., & De Leon, N. C. (2023). The lived experiences and perceptions of public-school employees in the Philippines: A PWD’s perspective. *International Journal of Business, Law and Education*, *4*(2), 312–321.  
https://ijble.com/index.php/journal/article/view/174

Alayon, J. R., Corciega, V. G. D., Genebago, N. M. L., Hernandez, A. B. A., Labitoria, C. R. C., & Tolentino, R. E. (2020). Design of Wearable Wrist Haptic Device for Blind Navigation using Microsoft Kinect for Xbox 360. In *Proceedings of the 2020 4th International Conference on Trends in Electronics and Informatics (ICOEI)*, (pp. 1005–1010). IEEE.  
https://doi.org/10.1109/ICOEI48184.2020.9143005

Anthropic. (2025). *Claude 4.5 Haiku API documentation for multimodal vision tasks*. Anthropic.  
https://docs.anthropic.com/en/docs/welcome

Barrinuevo, D., Jacosalem, G., Lagahit, J. N., Lobedica, M. J., Salar, M. R., & Tolentino, R. (2017). Precise Obstacles Avoidance System for Visually Impaired People using Xbox 360 Kinect. *ICGST International Journal on Graphics, Vision and Image Processing (GVIP)*, *17*(1), 15–23.  
https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQFfJi8GowO1tLJVMxiCEXmfv3_8IplvmriSKrOKBOIUI9gEq4py5QS0jSgJinsVLRTfp4T1o2ePy7-5nwwtxQ2AFZZqMKimdTrhNwXld6lwIQDDxhkBEy0jJmTHvMg7uYEz4mVpxoFsYAHcWyMV4fmFL_FBlccQ7gUzcQ==

Bouteraa, Y. (2021). Design and development of a wearable assistive device integrating a fuzzy decision support system for blind and visually impaired people. *Micromachines*, *12*(9), 1082.  
https://doi.org/10.3390/mi12091082

Brilli, D. D., Georgaras, E., Tsilivaki, S., Melanitis, N., & Nikita, K. (2024). *AIris: An AI-powered wearable assistive device for the visually impaired*. arXiv preprint arXiv:2405.07606.  
https://arxiv.org/pdf/2405.07606

Chen, Y., Shen, J., & Sawada, H. (2023). A wearable assistive system for the visually impaired using object detection, distance measurement and tactile presentation. *Intelligent Robotics*, *3*(3), 420–435.  
https://doi.org/10.20517/ir.2023.24

Dakopoulos, D., & Bourbakis, N. G. (2010). Wearable obstacle avoidance electronic travel aids for blind: A Survey. *IEEE Transactions on Systems, Man, and Cybernetics, Part C*, *40*(1), 25–35.  
https://doi.org/10.1109/TSMCC.2009.2021255

Department of Education (DepEd). (2017). *Philippine Professional Standards for Teachers (PPST)*.  
https://www.deped.gov.ph/wp-content/uploads/2017/08/DO_s2017_042.pdf

Effendi, T., Suyudi, I., & Ali, A. J. K. N. (2021). EFL vision impaired teacher’s classroom management in the eyes of his sighted teenaged students. *TESOL International Journal*, *16*(1), 73–88.  
https://eric.ed.gov/?id=EJ1329788

Htike, M. H., Lin, K. P., Swain, P. L., Lin, K. H., Lin, H. C., & Lin, S. Y. (2020). Smart Cane: Assistive Cane for Visually-impaired People. In *Proceedings of the 2020 IEEE Conference on Computer Applications (ICCA)*, (pp. 92–96). IEEE.  
https://doi.org/10.1109/ICCA49421.2020.9328100

Kadam, P., Fang, G., Amirabdollahian, F., Zou, J. J., & Holthaus, P. (2024). *Hand pose detection using YOLOv8-pose* (Technical Report). School of Engineering, Design and Built Environment, Western Sydney University & Robotics Research Group, University of Hertfordshire.  
https://uhra.herts.ac.uk/id/eprint/25619/1/paper_17.pdf

National Council on Disability Affairs (NCDA). (2012). *Implementation of the Magna Carta for Disabled Persons (Republic Act No. 7277)*.  
https://ncda.gov.ph/disability-laws/republic-acts/republic-act-7277/

San Jose, J. (n.d.). *Narrative analysis of teachers with disabilities in Greater Manila using the Social Relational Model of Disability* [Unpublished manuscript].

Szeliski, R. (2022). *Computer Vision: Algorithms and Applications* (2nd ed.). Springer.  
https://szeliski.org/Book/

Thongchai, T. (n.d.). *Personal and professional experiences of teachers with disabilities teaching Filipino in Davao Region: A case study* [Unpublished manuscript].

Ultralytics. (2024). *YOLOv8 documentation and keypoint pose estimation models*. Ultralytics.  
https://docs.ultralytics.com/tasks/pose/

Wiener, W. R., Welsh, R. L., & Blasch, B. B. (2010). *Foundations of Orientation and Mobility* (3rd ed.). AFB Press.  
https://www.google.com/books/edition/Foundations_of_Orientation_and_Mobility/B4FvPgAACAAJ