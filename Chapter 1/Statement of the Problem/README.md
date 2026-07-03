# Statement of the Problem

### General Problem
A visually impaired teacher faces a critical lack of spatial awareness in active classrooms, rendering them unable to independently monitor student behaviors and attentiveness, or safely navigate around floor-level and forward-facing classroom obstacles.

### Specific Problems
Specifically, this study seeks to answer the following guide questions:

1. **How** accurate and precise is the blind assistive device in monitoring student postures and classroom behaviors across varying seating rows and column positions for the visually impaired teacher?
2. **How** reliable is the blind assistive device in detecting classroom obstacles and distinguishing walkable paths across its physical lanes for the visually impaired teacher?
3. **Is there** a significant improvement in the visually impaired teacher's navigation safety, mobility, and spatial awareness when utilizing the SENSEY system compared to traditional methods?

---
---
## NOTE BELOW PARA MALAMAN NIYO CONTENT NANG KADA QUESTIONS, MY RELATION, CONSISTENCY SA RESEARCH FORMAT AT HINDI MEMA IMBENTO LANG
---
---

# Research Analysis: Compliance with Academic Guidelines

Below is the detailed scientific and methodological analysis of how each question in the Statement of the Problem (SOP) strictly satisfies the academic standards outlined in your department's research guidelines:

### **Analysis of Question 1 (Student Status Monitoring)**
* **Guideline Compliance (SOP Guidelines - Slide 12):** This question begins with the permitted guide word **"How"** and focuses on a technically researchable problem.
* **Statistical Measurability (Title Defense Guidelines):** It completely avoids subjective terms. Instead, it asks for **accuracy** and **precision**, which are standard, quantifiable computer-vision metrics. In Chapter 4, this is evaluated through a Confusion Matrix, yielding numerical percentages for True Positives, False Positives, and Precision/Recall rates.
* **Variables and Isolation:** The question isolates and defines your testing variables: **distance** (varying seating rows) and **angle** (column positions). By organizing your data around these variables, you prove the system's spatial detection limits on a 3x3 grid, showing the panel exactly where the NPU pose classifier is most effective.
* **Felt Problem Justification (Introduction Guidelines - Slide 6):** This directly addresses the "felt problem" of the visually impaired teacher's classroom blind spot, proving that the system provides active, spatial classroom status updates.

### **Analysis of Question 2 (Obstacle Detection & Lane Mapping)**
* **Guideline Compliance (SOP Guidelines - Slide 12):** This question uses the guide word **"How"** and targets the core functional capability of SENSEY's spatial depth mapping.
* **Symmetric Literature Alignment (Barrinuevo et al., 2017 - Table 2):** It directly mirrors the established methodology of your university's 2017 baseline study, which tested the system's reliability over 385 obstacle samples.
* **Statistical Measurability:** "Reliability" is measured mathematically as a **Detection Success Rate (%)** (Successes vs. Failures), while "distinguishing walkable paths" is measured through **Decision-Making Accuracy (%)** across the 5 lane-blocking scenarios (Forward, Left, Right, Stop, Stop Wall).
* **Geometric Rigor:** The testing structure for this question uses your right-triangle/Pythagorean calibration ($c = \sqrt{a^2 + b^2}$) across three posture angles ($0^\circ$, $-20^\circ$, $-40^\circ$). This demonstrates mathematical rigor, proving to the engineering panel that your depth-coordinate scaling matches physical reality.

### **Analysis of Question 3 (Navigation, Mobility, & Usability)**
* **Guideline Compliance (SOP Guidelines - Slide 12 & Slide 13):** This question uses the guide phrase **"Is there a..."** which is specifically permitted under your department's guidelines.
* **Hypothesis Testing (Objective Guidelines - Slide 13):** Because it asks a binary question ("Is there a significant improvement..."), it sets up a formal **Null Hypothesis ($H_0$)** and **Alternative Hypothesis ($H_a$)** that you will statistically test, accept, or reject in Chapter 5.
* **Scientific Control Group:** It compares SENSEY against "traditional methods" (navigating with a standard white cane), satisfying the requirements of human-subject testing.
* **Quantifiable Human Factors (Barrinuevo et al., 2017 - Table 3):** It measures the ultimate practical value of the Capstone project through:
  * **Mobility:** Total completion time (seconds).
  * **Safety:** Bounding box/collision errors.
  * **Spatial Awareness:** The qualitative 1-to-5 recall score enabled by the Claude AI description, proving that SENSEY provides cognitive mapping to the user rather than just blind steering.
