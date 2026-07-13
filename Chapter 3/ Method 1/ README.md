
# **STATISTICAL TREATMENT OF DATA (SOP 1)**

To analyze and interpret the student posture and behavior tracking performance of the developed SENSEY system, the raw experimental data gathered in Protocol 1 will undergo formal descriptive statistical treatment. 

Because the evaluation aims to describe and organize the visual status-tracking capabilities of the hardware-software prototype under specific classroom conditions rather than compare separate human populations, **Descriptive Statistics** are applied [15]. 

To evaluate SENSEY's performance both conceptually (as a whole system) and operationally (divided by row distance), the study calculates the **Weighted Arithmetic Mean (Aggregated Frequency Method)** across two distinct analytical levels:

---

### **Level A: The Overall System Performance (Whole Study — $N_{Total} = 1440$)**

To determine the cumulative success and failure rates of the student tracking module across the entire study, the raw frequencies of correct detections, labeling errors, and missed detections across all 24 configurations are aggregated over the complete $N_{Total} = 1440$ evaluation pool:

#### **A. Overall Average Behavior Recognition Rate / Success Rate ($R_{Success\_Overall}$):**
This metric measures SENSEY's cumulative success rate in both detecting student presence and correctly identifying their active posture and behavior. It is calculated by dividing the sum of all True Positives ($TP$) across all 24 configurations by the total evaluation pool ($N_{Total} = 1440$) [1, 35]:

$$R_{Success\_Overall} = \frac{\sum_{i=1}^{24} TP_i}{1440} \times 100$$

Where $\sum_{i=1}^{24} TP_i$ represents the sum of all successful posture and behavior classifications across the 24 seating configurations in Table 4.1.

#### **B. Overall Average Behavior Failure Rate ($R_{Failure\_Overall}$):**
This metric measures SENSEY's cumulative failure rate [11, 12]. It represents the sum of all tracking failures—comprising both classification errors ($FP$) and completely missed detections ($FN$)—divided by the total evaluation pool ($N_{Total} = 1440$) [11, 12, 35]:

$$R_{Failure\_Overall} = \frac{\sum_{i=1}^{24} (FP_i + FN_i)}{1440} \times 100$$

Where $\sum_{i=1}^{24} (FP_i + FN_i)$ is the sum of all classification errors and missed detections across the 24 configurations in Table 4.1.

$$\text{Note: } R_{Success\_Overall} + R_{Failure\_Overall} = 100.0\%$$

---

### **Level B: The Row-by-Row Category Performance ($N_{Row} = 480$ each)**

To analyze the specific effects of distance and student-to-student occlusion, the data is divided into three separate row categories [11]. The performance of each row is calculated individually across its eight (8) behavior configurations, representing $480$ evaluations per row ($8\text{ behaviors} \times 20\text{ trials} \times 3\text{ students}$):

#### **A. Front Row Category Performance (Row 1 at 1.0m — $N_{Row1} = 480$):**
$$R_{Success\_Row1} = \frac{\sum_{i=1}^{8} TP_{Row1,i}}{480} \times 100$$

$$R_{Failure\_Row1} = \frac{\sum_{i=1}^{8} (FP_{Row1,i} + FN_{Row1,i})}{480} \times 100$$

#### **B. Middle Row Category Performance (Row 2 at 2.0m — $N_{Row2} = 480$):**
$$R_{Success\_Row2} = \frac{\sum_{i=1}^{8} TP_{Row2,i}}{480} \times 100$$

$$R_{Failure\_Row2} = \frac{\sum_{i=1}^{8} (FP_{Row2,i} + FN_{Row2,i})}{480} \times 100$$

#### **C. Back Row Category Performance (Row 3 at 3.0m — $N_{Row3} = 480$):**
$$R_{Success\_Row3} = \frac{\sum_{i=1}^{8} TP_{Row3,i}}{480} \times 100$$

$$R_{Failure\_Row3} = \frac{\sum_{i=1}^{8} (FP_{Row3,i} + FN_{Row3,i})}{480} \times 100$$

$$\text{Note: } R_{Success\_Row} + R_{Failure\_Row} = 100.0\% \text{ for each individual row.}$$

---

### **3. Deep-Learning Performance Indicators**

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
**References**

[1] Sameh Magdy, Tarek Mahmoud, and Mohamed Ibrahim, "Face Recognition based on Hidden Markov Model and Canny Operators," *ICGST International Journal on Graphics, Vision and Image Processing (GVIP)*, vol. 17, no. 1, pp. 1–7, June 2017.

[11] D. Barrinuevo, G. Jacosalem, J. N. Lagahit, M. J. Lobedica, M. R. Salar, and R. Tolentino, "Precise Obstacles Avoidance System for Visually Impaired People using Xbox 360 Kinect," *ICGST International Journal on Graphics, Vision and Image Processing (GVIP)*, vol. 17, no. 1, pp. 15–23, June 2017.

[12] J. R. Alayon, V. G. D. Corciega, N. M. L. Genebago, A. B. A. Hernandez, C. R. C. Labitoria, and R. E. Tolentino, "Design of Wearable Wrist Haptic Device for Blind Navigation using Microsoft Kinect for Xbox 360," in *Proceedings of the 2020 4th International Conference on Trends in Electronics and Informatics (ICOEI)*, 2020, pp. 1005–1010, doi: 10.1109/ICOEI48184.2020.9143005.

[15] Department of Education. (2024). *Statistical treatment of data* [Slide presentation]. ETUlay.

[35] P. Kadam, G. Fang, Y. Amirabdollahian, J. J. Zou, and P. Holthaus, "Hand Pose Detection Using YOLOv8-pose," School of Engineering, Design and Built Environment, Western Sydney University & Robotics Research Group, University of Hertfordshire, Technical Report, 2024. [Online]. Available: https://uhra.herts.ac.uk/id/eprint/25619/1/paper_17.pdf