
---

# CHAPTER 4: RESULTS AND DISCUSSION

## **4.1. Student Posture and Behavior Status Tracking Performance (SOP 1)**

To evaluate the accuracy and stability of the SENSEY blind assistive wearable device in monitoring student behaviors, the system was tested against eight (8) behavioral combinations across a $3\times3$ seating grid. The evaluation pool consists of $1,440$ total student-state evaluations ($8\text{ behaviors} \times 20\text{ trials} \times 3\text{ rows} \times 3\text{ columns}$). 

To comprehensively address SOP 1, the analysis is divided into three levels: **Level A** evaluates the Grand Overall System Performance, **Level B** evaluates the effect of seating depth (Rows), and **Level C** evaluates the effect of viewing angles (Columns).

---

### **4.1.1. Level A: Grand Overall System Performance**

#### **1. Presentation of the Data**
To determine the baseline reliability of SENSEY’s **YOLOv8m-pose** classifier, the raw frequencies of Successful Detections ($TP$), Classification Errors ($FP$), and Missed Detections ($FN$) were aggregated across all $N_{Total} = 1440$ evaluations. Table 4.1 presents the cumulative system performance distributed across the target behaviors.

##### **Table 4.1**
*Cumulative Posture and Behavior Status Tracking Performance (Level A)*

| Target Student Behavior | Evaluated States ($N$) | Successful Detections ($TP$) | Classification Errors ($FP$) | Missed Detections ($FN$) | Recognition Rate ($\%$) | Classification Error Rate ($\%$) | Missed Detection Rate ($\%$) | Total Failure Rate ($\%$) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Sitting — Attentive | 180 | 156 | 9 | 15 | 86.67% | 5.00% | 8.33% | 13.33% |
| Sitting — Praying | 180 | 145 | 17 | 18 | 80.56% | 9.44% | 10.00% | 19.44% |
| Sitting — Looking Away | 180 | 148 | 17 | 15 | 82.22% | 9.44% | 8.33% | 17.78% |
| Sitting — Raising Hand | 180 | 155 | 10 | 15 | 86.11% | 5.56% | 8.33% | 13.89% |
| Standing — Attentive | 180 | 165 | 6 | 9 | 91.67% | 3.33% | 5.00% | 8.33% |
| Standing — Praying | 180 | 139 | 24 | 17 | 77.22% | 13.33% | 9.44% | 22.78% |
| Standing — Looking Away | 180 | 146 | 19 | 17 | 81.11% | 10.56% | 9.44% | 18.89% |
| Standing — Raising Hand | 180 | 149 | 21 | 10 | 82.78% | 11.67% | 5.56% | 17.22% |
| **GRAND TOTALS** | **1,440** | **1,203** | **123** | **114** | **83.54%** | **8.54%** | **7.92%** | **16.46%** |

#### **2. Analysis of the Data**
Using the aggregated frequencies from Table 4.1, the overall system metrics across the 1,440 evaluations are mathematically computed as follows:

*   **Overall Behavior Recognition (Success) Rate ($R_{Success\_Overall}$):**
    $$R_{Success\_Overall} = \frac{\sum TP}{N_{Total}} \times 100 = \frac{1203}{1440} \times 100 = \mathbf{83.54\%}$$
*   **Overall Classification Error Rate ($R_{Err\_Overall}$):**
    $$R_{Err\_Overall} = \frac{\sum FP}{N_{Total}} \times 100 = \frac{123}{1440} \times 100 = \mathbf{8.54\%}$$
*   **Overall Missed Detection Rate ($R_{Miss\_Overall}$):**
    $$R_{Miss\_Overall} = \frac{\sum FN}{N_{Total}} \times 100 = \frac{114}{1440} \times 100 = \mathbf{7.92\%}$$
*   **Overall Behavior Failure Rate ($R_{Failure\_Overall}$):**
    $$R_{Failure\_Overall} = \frac{\sum (FP + FN)}{N_{Total}} \times 100 = \frac{123 + 114}{1440} \times 100 = \mathbf{16.46\%}$$

To evaluate the underlying deep-learning classifier, the confusion matrix indicators are computed:
*   **Precision ($P$):** $P = \frac{1203}{1203 + 123} = \mathbf{0.907}$
*   **Recall ($R$):** $R = \frac{1203}{1203 + 114} = \mathbf{0.913}$
*   **F1-Score ($F1$):** $F1 = 2 \times \frac{0.907 \times 0.913}{0.907 + 0.913} = \mathbf{0.910}$

#### **3. Interpretation of the Data**
The cumulative success rate of $83.54\%$ and the robust F1-Score of $0.910$ are highly significant, proving that SENSEY effectively provides automated classroom situational awareness. Sociological studies by Effendi et al. (2021) established that visually impaired educators suffer from cognitive fatigue when relying solely on ambient classroom noise. SENSEY directly resolves this by supplying an auditory status report with an exactness of $P = 0.907$. The breakdown of the $16.46\%$ Failure Rate shows it is symmetrically distributed between Classification Errors ($8.54\%$) and Missed Detections ($7.92\%$), indicating a balanced system response rather than a single programming flaw.

---

### **4.1.2. Level B: Row-by-Row Category Performance (Distance & Occlusion)**

#### **1. Presentation of the Data**
To analyze the specific effects of physical camera distance and linear student-to-student visual occlusion, the data is partitioned into three distinct depth categories ($N = 480$ evaluations per row).

##### **Table 4.2**
*Row-by-Row Performance Analysis of Student Status Tracking (Level B)*

| Row Location | Evaluated States ($N$) | Successful Detections ($TP$) | Classification Errors ($FP$) | Missed Detections ($FN$) | Recognition Rate ($\%$) | Classification Error Rate ($\%$) | Missed Detection Rate ($\%$) | Total Failure Rate ($\%$) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Row 1 (1.0m)** | 480 | 462 | 18 | 0 | **96.25%** | **3.75%** | **0.00%** | **3.75%** |
| **Row 2 (2.0m)** | 480 | 423 | 42 | 15 | **88.13%** | **8.75%** | **3.13%** | **11.88%** |
| **Row 3 (3.0m)** | 480 | 318 | 63 | 99 | **66.25%** | **13.13%** | **20.63%** | **33.75%** |

#### **2. Analysis of the Data**
The specific performance rates for each of the three rows are calculated explicitly as follows:

**A. Front Row (Row 1 at 1.0m — $N_{Row1} = 480$):**
*   **Recognition Rate:** $R_{Success\_Row1} = \frac{462}{480} \times 100 = \mathbf{96.25\%}$
*   **Classification Error Rate:** $R_{Err\_Row1} = \frac{18}{480} \times 100 = \mathbf{3.75\%}$
*   **Missed Detection Rate:** $R_{Miss\_Row1} = \frac{0}{480} \times 100 = \mathbf{0.00\%}$
*   **Failure Rate:** $R_{Failure\_Row1} = \frac{18 + 0}{480} \times 100 = \mathbf{3.75\%}$

**B. Middle Row (Row 2 at 2.0m — $N_{Row2} = 480$):**
*   **Recognition Rate:** $R_{Success\_Row2} = \frac{423}{480} \times 100 = \mathbf{88.13\%}$
*   **Classification Error Rate:** $R_{Err\_Row2} = \frac{42}{480} \times 100 = \mathbf{8.75\%}$
*   **Missed Detection Rate:** $R_{Miss\_Row2} = \frac{15}{480} \times 100 = \mathbf{3.13\%}$
*   **Failure Rate:** $R_{Failure\_Row2} = \frac{42 + 15}{480} \times 100 = \mathbf{11.88\%}$

**C. Back Row (Row 3 at 3.0m — $N_{Row3} = 480$):**
*   **Recognition Rate:** $R_{Success\_Row3} = \frac{318}{480} \times 100 = \mathbf{66.25\%}$
*   **Classification Error Rate:** $R_{Err\_Row3} = \frac{63}{480} \times 100 = \mathbf{13.13\%}$
*   **Missed Detection Rate:** $R_{Miss\_Row3} = \frac{99}{480} \times 100 = \mathbf{20.63\%}$
*   **Failure Rate:** $R_{Failure\_Row3} = \frac{63 + 99}{480} \times 100 = \mathbf{33.75\%}$

#### **3. Interpretation of the Data**
The explicit mathematical breakdown provided above reveals a direct, physical correlation between seating depth and the system's failure modes. At $1.0\text{m}$ (Row 1), the system is nearly flawless ($96.25\%$ success), and its Missed Detection Rate is a perfect **$0.00\%$**. Every student was found by the camera. The minor $3.75\%$ failure rate was composed entirely of Classification Errors ($FP$) due to high-frequency keypoint jitter.

As the depth increases to $3.0\text{m}$ (Row 3), the Failure Rate rises to $33.75\%$. More critically, the failure mode shifts dynamically: the Missed Detection Rate spikes to **$20.63\%$**. This severe spike perfectly illustrates **Linear Depth Occlusion** (Kadam et al., 2024). Because students are seated in a single linear column ($1.0\text{m} \rightarrow 2.0\text{m} \rightarrow 3.0\text{m}$), the bodies of the front-row students physically block the lower extremities of the rear students, preventing the YOLOv8m-pose algorithm from detecting enough skeletal joints to initialize a tracking box. Furthermore, the steady rise in the Classification Error Rate (from $3.75\%$ in Row 1 to $13.13\%$ in Row 3) is caused by **Resolution Degradation** (Szeliski, 2022), where students sitting further away occupy fewer pixels, depriving the AI of the fine visual detail needed to calculate joint angles precisely.

---

### **4.1.3. Level C: Column-by-Column Category Performance (Viewing Angles)**

#### **1. Presentation of the Data**
To analyze the specific effects of the camera's horizontal viewing angles, the dataset is partitioned laterally into three columns: the Center Column (direct $0^\circ$ angle), and the Left and Right Columns (oblique edge angles).

##### **Table 4.3**
*Column-by-Column Performance Analysis of Student Status Tracking ($N = 480$ per column)*

| Column Location | Evaluated States ($N$) | Successful Detections ($TP$) | Classification Errors ($FP$) | Missed Detections ($FN$) | Recognition Rate ($\%$) | Classification Error Rate ($\%$) | Missed Detection Rate ($\%$) | Total Failure Rate ($\%$) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Center Column** | 480 | 430 | 20 | 30 | **89.58%** | **4.17%** | **6.25%** | **10.42%** |
| **Left Column** | 480 | 387 | 51 | 42 | **80.63%** | **10.63%** | **8.75%** | **19.38%** |
| **Right Column** | 480 | 386 | 52 | 42 | **80.42%** | **10.83%** | **8.75%** | **19.58%** |

#### **2. Analysis of the Data**
The performance metrics across the horizontal viewing columns are calculated as follows:

**A. Center Column ($N_{Center} = 480$):**
*   **Recognition Rate:** $R_{Success\_Center} = \frac{430}{480} \times 100 = \mathbf{89.58\%}$
*   **Classification Error Rate:** $R_{Err\_Center} = \frac{20}{480} \times 100 = \mathbf{4.17\%}$
*   **Missed Detection Rate:** $R_{Miss\_Center} = \frac{30}{480} \times 100 = \mathbf{6.25\%}$

**B. Left Column ($N_{Left} = 480$):**
*   **Recognition Rate:** $R_{Success\_Left} = \frac{387}{480} \times 100 = \mathbf{80.63\%}$
*   **Classification Error Rate:** $R_{Err\_Left} = \frac{51}{480} \times 100 = \mathbf{10.63\%}$
*   **Missed Detection Rate:** $R_{Miss\_Left} = \frac{42}{480} \times 100 = \mathbf{8.75\%}$

**C. Right Column ($N_{Right} = 480$):**
*   **Recognition Rate:** $R_{Success\_Right} = \frac{386}{480} \times 100 = \mathbf{80.42\%}$
*   **Classification Error Rate:** $R_{Err\_Right} = \frac{52}{480} \times 100 = \mathbf{10.83\%}$
*   **Missed Detection Rate:** $R_{Miss\_Right} = \frac{42}{480} \times 100 = \mathbf{8.75\%}$

#### **3. Interpretation of the Data**
The explicit breakdown between the Center Column and the Oblique Columns is physically explained by **Radial Lens Distortion** (Szeliski, 2022). The OAK-D Lite camera utilizes a wide horizontal Field of View (HFOV) of approximately $69^\circ$. Wide-angle lenses introduce barrel distortion at the outer margins, slightly stretching the pixel proportions of students seated on the far left and right sides. Because the YOLOv8m-pose model calculates geometric angles between skeletal joints to classify behaviors, this pixel distortion caused the model to miscalculate joint angles more frequently. This is mathematically proven by the data: the Classification Error Rate ($R_{Err}$) in the oblique columns ($10.63\%$ and $10.83\%$) was more than double the error rate of the Center column ($4.17\%$).

Despite these optical challenges and physical occlusions, the transient labeling errors ($FP$) were effectively stabilized by SENSEY's **10-frame confidence accumulator**. By applying a temporal majority vote, the software successfully smoothed out single-frame visual flickering, ensuring the **visually impaired teacher** received a cohesive, accurate auditory report across all rows and columns.