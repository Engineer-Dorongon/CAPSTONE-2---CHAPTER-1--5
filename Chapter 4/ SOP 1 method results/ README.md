
---

# CHAPTER 4: RESULTS AND DISCUSSION

## **4.1. Student Posture and Behavior Status Tracking Performance (SOP 1)**

To evaluate the accuracy and stability of the SENSEY blind assistive wearable device in monitoring student behaviors, the system was tested against eight (8) behavioral combinations across a 3x3 seating grid. The evaluation pool consists of $1,440$ total student-state evaluations ($8\text{ behaviors} \times 20\text{ trials} \times 3\text{ rows} \times 3\text{ columns}$). 

To comprehensively address SOP 1, the analysis is divided into three levels: **Level A** evaluates the Grand Overall System Performance, **Level B** evaluates the effect of seating depth (Rows), and **Level C** evaluates the effect of viewing angles (Columns).

---

### **4.1.1. Level A: Grand Overall System Performance**

#### **1. Presentation of the Data**
To determine the baseline reliability of SENSEY’s **YOLOv8m-pose** classifier and temporal confidence accumulator, the frequencies of successful detections ($TP$), classification errors ($FP$), and missed detections ($FN$) were aggregated across all 1,440 evaluations. 

##### **Table 4.1**
*Cumulative Posture and Behavior Status Tracking Performance (Level A)*

| Target Student Behavior | Total Evaluated States ($N$) | Successful Detections ($TP$) | Classification Errors ($FP$) | Missed Detections ($FN$) | Recognition Rate ($\%$) | Failure Rate ($\%$) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Sitting — Attentive | 180 | 156 | 9 | 15 | 86.67% | 13.33% |
| Sitting — Praying | 180 | 145 | 17 | 18 | 80.56% | 19.44% |
| Sitting — Looking Away | 180 | 148 | 17 | 15 | 82.22% | 17.78% |
| Sitting — Raising Hand | 180 | 155 | 10 | 15 | 86.11% | 13.89% |
| Standing — Attentive | 180 | 165 | 6 | 9 | 91.67% | 8.33% |
| Standing — Praying | 180 | 139 | 24 | 17 | 77.22% | 22.78% |
| Standing — Looking Away | 180 | 146 | 19 | 17 | 81.11% | 18.89% |
| Standing — Raising Hand | 180 | 149 | 21 | 10 | 82.78% | 17.22% |
| **GRAND TOTALS** | **1,440** | **1,203** | **123** | **114** | **83.54%** | **16.46%** |

#### **2. Analysis of the Data**
Using the aggregated frequencies from Table 4.1, the overall system metrics are computed as follows:

*   **Overall Behavior Recognition Rate ($R_{Success\_Overall}$):**
    $$R_{Success\_Overall} = \frac{\sum TP}{N_{Total}} \times 100 = \frac{1203}{1440} \times 100 = \mathbf{83.54\%}$$
*   **Overall Behavior Failure Rate ($R_{Failure\_Overall}$):**
    $$R_{Failure\_Overall} = \frac{\sum FP + \sum FN}{N_{Total}} \times 100 = \frac{123 + 114}{1440} \times 100 = \mathbf{16.46\%}$$
*   **Deep-Learning Evaluation Indicators:**
    *   **Precision ($P$):** $P = \frac{1203}{1203 + 123} = \mathbf{0.907}$
    *   **Recall ($R$):** $R = \frac{1203}{1203 + 114} = \mathbf{0.913}$
    *   **F1-Score ($F1$):** $F1 = 2 \times \frac{0.907 \times 0.913}{0.907 + 0.913} = \mathbf{0.910}$

#### **3. Interpretation of the Data**
The cumulative success rate of $83.54\%$ and the robust F1-Score of $0.910$ are highly significant, proving that SENSEY effectively provides automated classroom situational awareness. Sociological studies by Effendi et al. (2021) established that visually impaired educators suffer from cognitive fatigue when relying solely on ambient classroom noise. SENSEY directly resolves this by supplying a highly precise ($P = 0.907$) auditory status report. The high precision score mathematically proves that when SENSEY issues an auditory alert regarding a student's behavior, it is highly exact, minimizing false alarms that would disrupt the **visually impaired teacher's** lesson flow.

---

### **4.1.2. Level B: Row-by-Row Category Performance (Distance & Occlusion)**

#### **1. Presentation of the Data**
To analyze the specific effects of physical camera distance and linear student-to-student visual occlusion, the data is partitioned into three distinct depth categories (Rows 1, 2, and 3). 

##### **Table 4.2**
*Row-by-Row Performance Analysis of Student Status Tracking ($N = 480$ per row)*

| Row Location | Evaluated States ($N$) | Successful Detections ($TP$) | Classification Errors ($FP$) | Missed Detections ($FN$) | Recognition Rate ($\%$) | Failure Rate ($\%$) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Row 1 (1.0m)** | 480 | 462 | 18 | 0 | **96.25%** | **3.75%** |
| **Row 2 (2.0m)** | 480 | 423 | 42 | 15 | **88.13%** | **11.88%** |
| **Row 3 (3.0m)** | 480 | 318 | 63 | 99 | **66.25%** | **33.75%** |

#### **2. Analysis of the Data**
Table 4.2 reveals a direct, quantifiable correlation between seating depth and system tracking performance:
*   **Row 1 Recognition:** $R_{Success\_Row1} = \frac{462}{480} \times 100 = \mathbf{96.25\%}$
*   **Row 3 Recognition:** $R_{Success\_Row3} = \frac{318}{480} \times 100 = \mathbf{66.25\%}$

At $1.0\text{m}$, the system is nearly flawless, recording zero ($0.0\%$) Missed Detections ($FN = 0$). However, at $3.0\text{m}$ (Row 3), the Failure Rate rises to $33.75\%$. Out of the 162 total failures in Row 3, the vast majority (**99 failures, or $61.1\%$ of all Row 3 errors**) were complete Missed Detections ($FN$), where the camera completely failed to draw a bounding box.

#### **3. Interpretation of the Data**
This degradation is optically consistent with established computer vision constraints. As students sit further away, their physical bodies occupy significantly fewer pixels on SENSEY’s hardware-resized $1024 \times 768$ preview frame, leading to **Resolution Degradation** (Szeliski, 2022). More critically, the massive spike in Missed Detections ($FN=99$) at Row 3 illustrates **Linear Depth Occlusion** (Kadam et al., 2024). Because students are seated in a single linear column ($1.0\text{m} \rightarrow 2.0\text{m} \rightarrow 3.0\text{m}$), the bodies of the front-row students physically block the lower extremities of the rear students, preventing the YOLOv8m-pose algorithm from detecting enough skeletal joints to initialize a tracking box.

---

### **4.1.3. Level C: Column-by-Column Category Performance (Viewing Angles & Lens Distortion)**

#### **1. Presentation of the Data**
To analyze the specific effects of the camera's horizontal viewing angles and lens boundaries, the dataset is partitioned laterally into three columns: the Center Column (direct $0^\circ$ angle), and the Left and Right Columns (oblique edge angles).

##### **Table 4.3**
*Column-by-Column Performance Analysis of Student Status Tracking ($N = 480$ per column)*

| Column Location | Evaluated States ($N$) | Successful Detections ($TP$) | Classification Errors ($FP$) | Missed Detections ($FN$) | Recognition Rate ($\%$) | Failure Rate ($\%$) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Center Column** | 480 | 430 | 20 | 30 | **89.58%** | **10.42%** |
| **Left Column** | 480 | 387 | 51 | 42 | **80.63%** | **19.38%** |
| **Right Column** | 480 | 386 | 52 | 42 | **80.42%** | **19.58%** |

#### **2. Analysis of the Data**
Table 4.3 reveals a quantifiable difference in system performance based on horizontal viewing angles:
*   **Center Recognition:** $R_{Success\_Center} = \frac{430}{480} \times 100 = \mathbf{89.58\%}$
*   **Oblique Average Recognition:** $R_{Success\_Oblique} = \frac{387 + 386}{960} \times 100 = \mathbf{80.52\%}$

When students were seated directly in front of the lens in the **Center Column**, the system achieved its highest lateral stability. Conversely, the Left and Right Columns generated more than double the Classification Errors ($FP = 51$ and $52$) compared to the Center column ($FP = 20$).

#### **3. Interpretation of the Data**
The performance discrepancy between the Center Column and the Oblique Columns is physically explained by **Radial Lens Distortion** (Szeliski, 2022). The OAK-D Lite camera utilizes a wide horizontal Field of View (HFOV) of approximately $69^\circ$. Optical physics dictates that wide-angle lenses introduce barrel distortion at the outer margins, slightly stretching the pixel proportions of students seated on the far left and right sides. Because the YOLOv8m-pose model calculates geometric angles between skeletal joints to classify behaviors, this pixel distortion caused the model to miscalculate joint angles more frequently at the edges, increasing Classification Errors ($FP$).

Despite these optical challenges and physical occlusions, the transient labeling errors ($FP$) were effectively stabilized by SENSEY's **10-frame confidence accumulator**. By applying a temporal majority vote, the software successfully smoothed out single-frame visual flickering, ensuring the **visually impaired teacher** received a cohesive, accurate auditory report across all rows and columns.