# OBJECTIVES OF THE STUDY

### General Objective
To evaluate the performance, usability, and workability of **SENSEY: An Intelligent Wearable Aid with Real-Time Object Detection and Multimodal Feedback for Inclusive Education** to support **visually impaired teachers**.

### Specific Objectives
To satisfy the general objective and provide the empirical evidence required for system evaluation, the study will fulfill the following measurable milestones:

1. **To evaluate the accuracy and stability** of the SENSEY blind assistive wearable device in monitoring student postures and classroom behaviors across varying seating rows and column positions for the **visually impaired teacher**.
2. **To measure the reliability** of the SENSEY blind assistive wearable device in detecting classroom obstacles and distinguishing walkable paths across its physical lanes (Left, Center, Right).
3. **To determine if there is** a significant improvement in the **visually impaired teacher's** navigation safety, mobility, and spatial awareness when utilizing the SENSEY system compared to traditional methods.

---
---

# PARTITION: OPERATIONAL SPECIFICATIONS (TESTING PROTOCOLS)

The following operational specifications outline the exact testing parameters, sample sizes, and data-gathering procedures designed to fulfill each specific research objective and provide the statistical evidence required for Chapter 4:

### **Operational Specifications for Specific Objective 1**
* **The Setup:** Three (3) participants acting as students are positioned across a physical $3\times3$ seating grid consisting of three rows (varying distances) and three columns (varying horizontal offsets).
* **Testing Variables:** Two (2) postural states (*Sitting*, *Standing*) and four (4) active behaviors (*Attentive*, *Raising Hand*, *Looking Away*, *Praying*), forming eight (8) distinct behavioral combinations.
* **Testing Configurations:** Six (6) distinct positional arrangements: Row 1, Row 2, Row 3, Left Column, Center Column, and Right Column.
* **Data Size & Sampling:** Ten (10) consecutive frame samples captured per behavioral combination across all six seating configurations, totaling exactly **480 samples**.
* **Chapter 4 Evidence:** 
  * **Behavior Recognition Rate (%)** (Success Rate)
  * **Behavior Error Rate (%)** (Failure Rate)
  * Confusion matrices showing posture/action classification accuracy and system tracking stability.

### **Operational Specifications for Specific Objective 2**
* **The Setup:** Placing standard obstacles (`backpack` representing floor hazards; `chair`/`person` representing forward-facing obstacles) in the Left, Center, and Right lanes at ground distances of 0.5m, 1.0m, and 1.5m.
* **Testing Variables:** Tested across three (3) chest-tilt angles ($0^\circ$, $-20^\circ$, $-40^\circ$) to simulate walking postures, and five (5) lane-blocking decision scenarios (Forward, Left, Right, Stop, Stop Wall) to verify walkable path differentiation.
* **Data Size & Sampling:** Ten (10) consecutive frame samples captured per configuration, totaling exactly **320 samples**.
* **Chapter 4 Evidence:** 
  * **Obstacle Detection Success Rate (%)** (Success Rate)
  * **Obstacle Detection Failure Rate (%)** (Failure Rate)
  * Distance margin of error (%) using right-triangle calibration, lane classification accuracy (%), and walkable path decision-making logic success rate (%).

### **Operational Specifications for Specific Objective 3**
* **The Setup:** One (1) **visually impaired teacher** (or blindfolded participant) navigating a classroom obstacle course ($10\text{m} \times 8\text{m}$) containing desks, chairs, and floor hazards.
* **Variables:** 10 navigation runs executed under three (3) comparative conditions:
  * *Trial A (Control Group):* Traditional navigation using a standard white cane (No Device).
  * *Trial B (Experimental Group 1):* Navigation using SENSEY's local automated depth-lane sensors only (metronome and steering voice prompts).
  * *Trial C (Experimental Group 2):* Navigation using SENSEY's local sensors combined with the Claude-Vision AI Scene Describer (triggered by pressing the physical chest button).
* **Data Size:** 10 runs completed per condition, totaling **30 runs**.
* **Chapter 4 Evidence:** A comparison table of the **visually impaired teacher's** navigation completion times (seconds) representing *mobility*, physical collision counts representing *navigation safety*, and qualitative spatial comprehension scores (1 to 5) representing *spatial awareness*.

---
---

# PARTITION: METHODOLOGICAL COMPLIANCE ANALYSIS

Below is the detailed methodological analysis proving how each objective satisfies your department's strict Capstone and Thesis guidelines:

### **Analysis of General Objective**
* **Guideline Compliance (Objective Guidelines - Slide 13):** The general objective is written as a direct, word-for-word reiteration of your approved research title (*"SENSEY: An Intelligent Wearable Aid..."*). This satisfies the administrative guidelines of university-level thesis defense panels, ensuring that the scope of the study does not drift from what was officially approved.

### **Analysis of Specific Objective 1 (Student Behavior Monitoring)**
* **SOP Symmetrical Alignment (Slide 13):** This objective is a direct, parallel translation of **SOP Question 1**. It swaps the question phrase *"How accurate and stable is..."* with the active, measurable engineering infinitive **"To evaluate the accuracy and stability of..."** and keeps the rest of the sentence identical.
* **Statistical Measurability (Title Defense Guidelines):** It targets the core software performance of your NPU tracking code. By evaluating accuracy and stability across your proposed 480-sample 3x3 seating grid, you generate the concrete data required to calculate the **Behavior Recognition Rate (%)** and **Behavior Error Rate (%)** (adapted from Page 11 of your alumni resources).

### **Analysis of Specific Objective 2 (Obstacle & Walkable Path Detection)**
* **SOP Symmetrical Alignment (Slide 13):** This objective is a direct, parallel translation of **SOP Question 2**. It swaps the question phrase *"How reliable is..."* with the active engineering infinitive **"To measure the reliability of..."** and keeps the rest of the sentence identical.
* **Symmetric Literature Alignment (Barrinuevo et al., 2017):** The operational testing (using 320 samples of backpacks, chairs, and people) directly mirrors the 385-sample static obstacle testing of your adviser's 2017 paper (Table 2). It provides the exact empirical data required to calculate the **Obstacle Detection Success Rate (%)** and **Obstacle Detection Failure Rate (%)**, proving your system has eliminated close-range blind spots.

### **Analysis of Specific Objective 3 (Classroom Usability & Navigation)**
* **SOP Symmetrical Alignment (Slide 13):** This objective is a direct, parallel translation of **SOP Question 3**. It swaps the question phrase *"Is there..."* with the active infinitive **"To determine if there is..."** and keeps the rest of the sentence identical.
* **Hypothesis Testing (Slide 13):** Because it is a direct parallel of the binary SOP Question 3, it sets up a formal **Null Hypothesis ($H_0$)** and **Alternative Hypothesis ($H_a$)** that you will statistically accept or reject in Chapter 5.
* **Control Group Integration:** The operational specs outline a complete three-part comparative study (Trial A: White Cane control vs. Trials B/C: SENSEY configurations). By comparing completion times (mobility) and collisions (safety), this objective provides the empirical data required in Chapter 4 to prove the system's dynamic usability for the **visually impaired teacher**.
