# **STATISTICAL TREATMENT OF DATA (SOP 1)**

To analyze and interpret the student posture and behavior tracking performance of the developed SENSEY system, the raw experimental data gathered in Protocol 1 will undergo formal descriptive statistical treatment. 

Because the evaluation aims to describe and organize the visual status-tracking capabilities of the hardware-software prototype under specific classroom conditions rather than compare separate human populations, **Descriptive Statistics** are applied [15]. 

To calculate the overall performance metrics across the entire study, the system utilizes the **Weighted Arithmetic Mean (Aggregated Frequency Method)**, pooling raw frequencies across all $N_{Total} = 480$ individual student-state evaluations ($8\text{ behavior configurations} \times 20\text{ trials} \times 3\text{ student rows}$):

$$N_{Total} = 480$$

---

### **1. Cumulative Success and Failure Rates**

To determine the overall baseline capabilities of SENSEY, the raw frequencies of correct detections, labeling errors, and missed detections are aggregated across the 480 evaluations:

#### **A. Overall Average Behavior Recognition Rate / Success Rate ($R_{Success\_Overall}$):**
This metric measures SENSEY's cumulative success rate in both detecting student presence and correctly identifying their active posture and behavior. It is calculated by dividing the sum of all True Positives ($TP$) across all configurations by the total evaluation pool ($N_{Total} = 480$) [1, 35]:

$$R_{Success\_Overall} = \frac{\sum_{i=1}^{8} TP_i}{N_{Total}} \times 100$$

Where $\sum_{i=1}^{8} TP_i$ represents the sum of all successful posture and behavior classifications across the 8 behavior configurations evaluated across the three rows.

#### **B. Overall Average Behavior Failure Rate ($R_{Failure\_Overall}$):**
This metric measures SENSEY's cumulative failure rate [11, 12]. It represents the sum of all tracking failures—comprising both classification errors ($FP$) and completely missed detections ($FN$)—divided by the total evaluation pool ($N_{Total} = 480$) [11, 12, 35]:

$$R_{Failure\_Overall} = \frac{\sum_{i=1}^{8} (FP_i + FN_i)}{N_{Total}} \times 100$$

Where $\sum_{i=1}^{8} (FP_i + FN_i)$ is the sum of all classification errors and missed detections across the 8 behavior configurations evaluated across the three rows.

$$\text{Note: } R_{Success\_Overall} + R_{Failure\_Overall} = 100.0\%$$

---

### **2. Deep-Learning Performance Indicators**

To provide a technically rigorous evaluation of SENSEY's **YOLOv8m-pose** classifier, the descriptive analysis incorporates three standard machine learning parameters derived from the system's confusion matrix to analyze model exactness and sensitivity [1, 35]:

#### **A. Model Precision ($P$):**
Precision measures SENSEY's exactness in avoiding false alarms, proving the reliability of the auditory alerts delivered to the **visually impaired teacher** [1]. It is calculated as:

$$P = \frac{\sum TP}{\sum TP + \sum FP}$$

#### **B. Model Recall ($R$):**
Recall measures SENSEY's sensitivity, proving how effectively the device identifies all students despite physical foreground occlusions [35]. It is calculated as:

$$R = \frac{\sum TP}{\sum TP + \sum FN}$$

#### **C. F1-Score ($F1$):**
The F1-Score represents the harmonic mean of Precision and Recall, providing a single balanced benchmark score to evaluate the overall stability of SENSEY's student status tracking module [35]:

$$F1 = 2 \times \frac{P \times R}{P + R}$$

---

### **Descriptive Statistical Treatment Rationale**

The selection of Descriptive Statistics for SOP 1 is technically justified under university research guidelines based on the following three parameters:

* **Purpose of the Analysis:** The primary objective of SOP 1 is to organize, summarize, and profile SENSEY's deep-learning classification capabilities under different physical seating rows and occlusion conditions. It is diagnostic rather than comparative; it does not test a hypothesis ($H_0$) or compare distinct human cohorts [15].
* **No Group Variance Assumptions:** Parametric tests (such as t-tests or ANOVA) require comparing different population means [15]. Because SENSEY's student tracking is evaluated on a single, standardized, and repeatable mechanical framework to measure software performance, there are no independent human-subject groups to compare.
* **Frequency and Percentage Base:** The standard method for validating neural network classifiers is to count successful occurrences (frequencies) and represent them as rates of accuracy, error, and sensitivity (percentages) [1, 15]. Presenting these rates alongside a formal Confusion Matrix is the mathematically correct and industry-accepted way to describe the workability of a computer vision system to your capstone panel.

---
---

# PARTITION: METHODOLOGICAL COMPLIANCE ANALYSIS

Below is the detailed methodological analysis proving how this specialized, student-limited Statistical Treatment of Data section strictly satisfies your department's academic guidelines:

### **1. 100% Mathematical Consistency with your 3-Student Layout**
* **Our Alignment:** The total evaluation pool ($N_{Total}$) has been configured to exactly **480 samples**, matching your physical seating arrangement ($8\text{ behaviors} \times 20\text{ trials} \times 3\text{ student rows}$). This ensures that your Chapter 3 formulas align perfectly with your Chapter 4 master tables, leaving no mathematical gaps for your panel to question.

### **2. Rigorous Verification of Failure Modes ($R_{Failure\_Overall}$)**
* **Our Alignment:** In accordance with your testing workflow (using the physical push-button auditory census to audit missing bounding boxes), the **Behavior Failure Rate ($R_{Failure\_Overall}$)** is defined as the sum of **Classification Errors ($FP$)** and **Missed Detections ($FN$)** [11, 12]. This ensures that your overall success and failure rates balance to exactly $100\%$, providing a clear, logical data structure.

### **3. Complete Theoretical Justification (Slide 15 Compliance)**
* **Our Alignment:** This section provides a solid defense of why descriptive statistics are the mathematically correct tools to evaluate student tracking. By explaining that SOP 1 is a diagnostic, descriptive technical evaluation of software classification performance, you justify using percentage success/error rates, saving your inferential t-tests for your navigation and usability evaluations (SOP 2 & 3).

---
**References**

[1] Sameh Magdy, Tarek Mahmoud, and Mohamed Ibrahim, "Face Recognition based on Hidden Markov Model and Canny Operators," *ICGST International Journal on Graphics, Vision and Image Processing (GVIP)*, vol. 17, no. 1, pp. 1–7, June 2017.

[11] D. Barrinuevo, G. Jacosalem, J. N. Lagahit, M. J. Lobedica, M. R. Salar, and R. Tolentino, "Precise Obstacles Avoidance System for Visually Impaired People using Xbox 360 Kinect," *ICGST International Journal on Graphics, Vision and Image Processing (GVIP)*, vol. 17, no. 1, pp. 15–23, June 2017.

[12] J. R. Alayon, V. G. D. Corciega, N. M. L. Genebago, A. B. A. Hernandez, C. R. C. Labitoria, and R. E. Tolentino, "Design of Wearable Wrist Haptic Device for Blind Navigation using Microsoft Kinect for Xbox 360," in *Proceedings of the 2020 4th International Conference on Trends in Electronics and Informatics (ICOEI)*, 2020, pp. 1005–1010, doi: 10.1109/ICOEI48184.2020.9143005.

[15] Department of Education. (2024). *Statistical treatment of data* [Slide presentation]. ETUlay.

[35] P. Kadam, G. Fang, Y. Amirabdollahian, J. J. Zou, and P. Holthaus, "Hand Pose Detection Using YOLOv8-pose," School of Engineering, Design and Built Environment, Western Sydney University & Robotics Research Group, University of Hertfordshire, Technical Report, 2024. [Online]. Available: https://uhra.herts.ac.uk/id/eprint/25619/1/paper_17.pdf