
---

# **STATISTICAL TREATMENT OF DATA (SOP 1)**

To analyze and interpret the student posture and behavior tracking performance of SENSEY, the raw experimental data gathered in Protocol 1 will undergo formal descriptive statistical treatment. 

Because the evaluation aims to describe and organize the visual status-tracking capabilities of the hardware-software prototype under specific classroom conditions rather than compare separate human populations, **Descriptive Statistics** are applied [15]. 

To evaluate SENSEY's performance comprehensively, the study calculates the **Weighted Arithmetic Mean (Aggregated Frequency Method)** across three distinct analytical levels:

### **Level A: The Overall System Performance (Whole Study — $N_{Total} = 1440$)**

To determine the cumulative success and failure rates across the entire study, the raw frequencies of correct detections, labeling errors, and missed detections are aggregated over the complete $N_{Total} = 1440$ evaluation pool ($3\text{ rows} \times 8\text{ behaviors} \times 20\text{ trials} \times 3\text{ columns}$):

#### **A. Overall Behavior Recognition Rate / Success Rate ($R_{Success\_Overall}$):**
$$R_{Success\_Overall} = \frac{\sum_{i=1}^{24} TP_i}{1440} \times 100$$

#### **B. Overall Behavior Failure Rate ($R_{Failure\_Overall}$):**
$$R_{Failure\_Overall} = \frac{\sum_{i=1}^{24} (FP_i + FN_i)}{1440} \times 100$$

#### **C. Overall Classification Error Rate ($R_{Err\_Overall}$):**
$$R_{Err\_Overall} = \frac{\sum_{i=1}^{24} FP_i}{1440} \times 100$$

#### **D. Overall Missed Detection Rate ($R_{Miss\_Overall}$):**
$$R_{Miss\_Overall} = \frac{\sum_{i=1}^{24} FN_i}{1440} \times 100$$

$$\text{Note: } R_{Success\_Overall} + R_{Failure\_Overall} = 100.0\%$$

---

### **Level B: The Row-by-Row Category Performance (Distance & Depth Occlusion — $N_{Row} = 480$ each)**

To analyze the specific effects of physical distance and linear student-to-student visual occlusion, the data is partitioned into three horizontal row categories [11]. The performance of each row is calculated individually across $480$ evaluations per row ($8\text{ behaviors} \times 20\text{ trials} \times 3\text{ columns}$) [11]:

#### **1. Front Row Performance (Row 1 at 1.0m — $N_{Row1} = 480$):**
$$R_{Success\_Row1} = \frac{\sum TP_{Row1}}{480} \times 100 \quad \text{and} \quad R_{Failure\_Row1} = \frac{\sum (FP_{Row1} + FN_{Row1})}{480} \times 100$$

#### **2. Middle Row Performance (Row 2 at 2.0m — $N_{Row2} = 480$):**
$$R_{Success\_Row2} = \frac{\sum TP_{Row2}}{480} \times 100 \quad \text{and} \quad R_{Failure\_Row2} = \frac{\sum (FP_{Row2} + FN_{Row2})}{480} \times 100$$

#### **3. Back Row Performance (Row 3 at 3.0m — $N_{Row3} = 480$):**
$$R_{Success\_Row3} = \frac{\sum TP_{Row3}}{480} \times 100 \quad \text{and} \quad R_{Failure\_Row3} = \frac{\sum (FP_{Row3} + FN_{Row3})}{480} \times 100$$

---

### **Level C: The Column-by-Column Category Performance (Viewing Angles & Lens Distortion — $N_{Col} = 480$ each)**

To analyze the specific effects of the camera's horizontal viewing angles, radial lens distortion, and oblique shadowing, the dataset is partitioned laterally into three column categories. The performance of each column is calculated individually across $480$ evaluations per column ($8\text{ behaviors} \times 20\text{ trials} \times 3\text{ rows}$):

#### **1. Center Column Performance (Direct $0^\circ$ Angle — $N_{Center} = 480$):**
$$R_{Success\_Center} = \frac{\sum TP_{Center}}{480} \times 100$$
$$R_{Failure\_Center} = \frac{\sum (FP_{Center} + FN_{Center})}{480} \times 100$$
*(Note: Sub-rates $R_{Err\_Center}$ and $R_{Miss\_Center}$ are also extracted from $FP$ and $FN$ accordingly).*

#### **2. Left Column Performance (Oblique Angle — $N_{Left} = 480$):**
$$R_{Success\_Left} = \frac{\sum TP_{Left}}{480} \times 100$$
$$R_{Failure\_Left} = \frac{\sum (FP_{Left} + FN_{Left})}{480} \times 100$$

#### **3. Right Column Performance (Oblique Angle — $N_{Right} = 480$):**
$$R_{Success\_Right} = \frac{\sum TP_{Right}}{480} \times 100$$
$$R_{Failure\_Right} = \frac{\sum (FP_{Right} + FN_{Right})}{480} \times 100$$

---

### **Deep-Learning Performance Indicators**

To provide a technically rigorous evaluation of SENSEY's **YOLOv8m-pose** classifier, the descriptive analysis incorporates three standard machine learning parameters derived from the system's overall confusion matrix to analyze model exactness and sensitivity [1, 35]:

*   **Model Precision ($P$):**
    $$P = \frac{\sum TP}{\sum TP + \sum FP}$$
*   **Model Recall ($R$):**
    $$R = \frac{\sum TP}{\sum TP + \sum FN}$$
*   **F1-Score ($F1$):**
    $$F1 = 2 \times \frac{P \times R}{P + R}$$

---

### **Why this completes your Chapter 3:**
Now, Chapter 3 and Chapter 4 are perfect mirror images of each other. 
1. **Chapter 3** tells the panel *how* you will calculate the Overall, Row-by-Row, and Column-by-Column math.
2. **Chapter 4** then *applies* those exact formulas, showing the results and interpreting the physical phenomena (lens distortion and depth occlusion) causing those numbers. 

This creates a flawlessly integrated Capstone manuscript!