Here is the finalized and fully corrected **Evaluation Framework for Student Posture and Behavior Status Tracking**. 

The **Success Rate / Behavior Recognition Rate** and the **Behavior Failure Rate** (composed mathematically of both $FP$ and $FN$) have been explicitly integrated and defined in the operational metrics list to ensure your methodology matches your Chapter 4 master data tables exactly.

---

# EVALUATION FRAMEWORK FOR STUDENT POSTURE AND BEHAVIOR STATUS TRACKING

To evaluate SENSEY’s capability in monitoring and auditing student classroom dynamics, the study implements a structured performance evaluation framework. This framework measures the classification accuracy and visual tracking stability of the **YOLOv8m-pose** model under realistic depth-based visual occlusions, using student positions spaced exactly $1.0\text{ meter}$ apart (Row 1 at 1.0m, Row 2 at 2.0m, and Row 3 at 3.0m).

### **Operational Definitions of Performance Metrics**

The evaluation utilizes seven standard computer vision and human-factors indicators to analyze the system’s performance across 480 test trials [1, 11, 12, 35]:

#### **1. Behavior Recognition Rate / Success Rate ($R_{Rec}$)**
This metric measures the overall success rate of SENSEY in both detecting the student's presence and correctly identifying their active posture or behavioral action [1, 35]. It is calculated as:

$$R_{Rec} = \frac{TP}{N} \times 100$$

Where $TP$ represents True Positives (the count of student behaviors correctly detected and classified) and $N$ represents the total number of experimental trials ($N = 480$) [1, 35].

#### **2. Behavior Failure Rate ($R_{Fail}$)**
This metric measures the overall failure rate of SENSEY's tracking pipeline [11, 12]. In accordance with machine learning standards, it represents the sum of both classification errors ($FP$) and missed detections ($FN$) across your trials [11, 12, 35]. It is calculated as:

$$R_{Fail} = \frac{FP + FN}{N} \times 100$$

Where $FP$ represents False Positives, $FN$ represents False Negatives, and $N$ represents the total number of trials ($N = 480$) [11, 12].

$$\text{Note: } R_{Rec} + R_{Fail} = 100\%$$

#### **3. Behavior Classification Error Rate ($R_{Err}$)**
This metric measures the sub-rate of failures caused strictly by SENSEY successfully detecting a student's presence but assigning the incorrect postural or behavioral label to their action (False Positives) [1]. It is calculated as:

$$R_{Err} = \frac{FP}{N} \times 100$$

Where $FP$ represents False Positives (mislabeled students) and $N$ represents the total number of trials ($N = 480$) [1].

#### **4. Missed Detection Rate ($R_{Miss}$)**
This metric measures the sub-rate of failures caused strictly by SENSEY completely missing the student due to distance limits or depth occlusions (False Negatives), verified when a student physically exists but is omitted from the spoken audio audit [35]. It is calculated as:

$$R_{Miss} = \frac{FN}{N} \times 100$$

Where $FN$ represents False Negatives (undetected students) and $N$ represents the total number of trials ($N = 480$) [35].

$$\text{Note: } R_{Fail} = R_{Err} + R_{Miss}$$

#### **5. Model Precision ($P$) & Recall ($R$)**
Precision measures SENSEY's exactness in avoiding false alarms, proving the reliability of the auditory alerts delivered to the **visually impaired teacher** [1]. Recall measures SENSEY's sensitivity, proving how effectively the device identifies all students despite physical foreground occlusions [35]. These are calculated as:

$$P = \frac{TP}{TP + FP}$$

$$R = \frac{TP}{TP + FN}$$

#### **6. F1-Score ($F1$)**
The F1-Score represents the harmonic mean of Precision and Recall, providing a single balanced benchmark score to evaluate the overall stability of SENSEY's student tracking module [35]:

$$F1 = 2 \times \frac{P \times R}{P + R}$$

---

### **Descriptive Statistical Treatment Rationale**

The evaluation of your student status tracking module relies strictly on **Descriptive Statistics** [15]. Under university research guidelines, this classification is justified based on the following methodological parameters:

* **Purpose of the Analysis:** The primary objective of SOP 1 is to describe, organize, and summarize the observed performance profiles of SENSEY's deep-learning model under controlled classroom conditions. It is diagnostic rather than comparative; it does not test a "hunch" (hypothesis) or compare distinct human cohorts [15].
* **No Group Variance Assumptions:** Parametric tests (like t-tests or ANOVA) require comparing different population means [15]. Since SENSEY's posture tracking is evaluated on a single, standardized, and repeatable mechanical framework to measure software accuracy, there are no independent human-subject groups to compare. 
* **Frequency and Percentage Base:** The standard method for validating neural network classifiers is to count successful occurrences (frequencies) and represent them as rates of accuracy, error, and sensitivity (percentages) [1, 15]. Presenting these rates alongside a formal Confusion Matrix is the mathematically correct and industry-accepted way to describe the workability of a computer vision system to your capstone panel.

---
---

# PARTITION: CHAPTER 3 COMPLIANCE ANALYSIS

Below is the detailed methodological analysis proving how this evaluation framework satisfies your department's research guidelines:

### **1. Technical Precision of the Metrics (Slide 20 Compliance)**
* **The Rule:** Measurements and variables must be clearly defined with non-circular, mathematically rigorous descriptions.
* **Our Alignment:** SENSEY's evaluation framework is highly technical and academically robust. Instead of just using "Accuracy," we divided system performance into three distinct mutually exclusive categories: **Correct Detections ($R_{Rec}$)**, **Labeling Errors ($R_{Err}$)**, and **Missed Detections ($R_{Miss}$)**, with their sum forming the **Behavior Failure Rate ($R_{Fail}$)**. This completely addresses your physical testing workflow (using the push-button auditory census to audit missing bounding boxes) and provides a highly professional, complete scientific structure.

### **2. Logical Justification of Descriptive Statistics (Slide 15 Compliance)**
* **Our Alignment:** Capstone panels often ask: *"Why didn't you run a t-test on your student tracking accuracy?"* The **Descriptive Statistical Treatment Rationale** section provides your defense team with an bulletproof mathematical defense. It explains that since SOP 1 is a diagnostic, descriptive technical evaluation of software classification performance, descriptive percentages and confusion matrices are the mathematically correct tools to use, while saving your inferential t-tests for your navigation and usability evaluations (SOP 2 & 3).

---
**References**

[1] Sameh Magdy, Tarek Mahmoud, and Mohamed Ibrahim, "Face Recognition based on Hidden Markov Model and Canny Operators," *ICGST International Journal on Graphics, Vision and Image Processing (GVIP)*, vol. 17, no. 1, pp. 1–7, June 2017.

[11] D. Barrinuevo, G. Jacosalem, J. N. Lagahit, M. J. Lobedica, M. R. Salar, and R. Tolentino, "Precise Obstacles Avoidance System for Visually Impaired People using Xbox 360 Kinect," *ICGST International Journal on Graphics, Vision and Image Processing (GVIP)*, vol. 17, no. 1, pp. 15–23, June 2017.

[12] J. R. Alayon, V. G. D. Corciega, N. M. L. Genebago, A. B. A. Hernandez, C. R. C. Labitoria, and R. E. Tolentino, "Design of Wearable Wrist Haptic Device for Blind Navigation using Microsoft Kinect for Xbox 360," in *Proceedings of the 2020 4th International Conference on Trends in Electronics and Informatics (ICOEI)*, 2020, pp. 1005–1010, doi: 10.1109/ICOEI48184.2020.9143005.

[15] Department of Education. (2024). *Statistical treatment of data* [Slide presentation]. ETUlay.

[35] P. Kadam, G. Fang, Y. Amirabdollahian, J. J. Zou, and P. Holthaus, "Hand Pose Detection Using YOLOv8-pose," School of Engineering, Design and Built Environment, Western Sydney University & Robotics Research Group, University of Hertfordshire, Technical Report, 2024. [Online]. Available: https://uhra.herts.ac.uk/id/eprint/25619/1/paper_17.pdf