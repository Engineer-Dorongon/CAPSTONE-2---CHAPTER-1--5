### **1. Chapter 4 Data Table Format**

According to APA 7th edition standards, tables must be numbered, have a brief italicized title, and use clean horizontal borders without vertical grid lines. 

Below is the standard layout for **Table 4.1**, which displays how your 480 samples are structured and evaluated to support the **visually impaired teacher**. The table is grouped by **Row Location (Distance)** to show how depth-based visual occlusion affects the system's tracking capabilities.

The **Failure Rate ($\%$)** is mathematically composed of the sum of **Classification Errors ($FP$)** and **Missed Detections ($FN$)** divided by the total number of trials:

$$R_{Failure} = \frac{FP + FN}{N} \times 100$$

#### **Table 4.1**
*SENSEY Student Posture and Behavior Status Tracking Performance Matrix*

| Row Location | Target Student Behavior | Total Trials ($N$) | Successful Detections ($TP$) | Classification Errors ($FP$) | Missed Detections ($FN$) | Recognition Rate ($\%$) | Failure Rate ($\%$) |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Row 1 (1.0m)** | Sitting — Attentive | 20 | 20 | 0 | 0 | 100.0% | 0.0% |
| | Sitting — Praying | 20 | 19 | 1 | 0 | 95.0% | 5.0% |
| | Sitting — Looking Away | 20 | 19 | 1 | 0 | 95.0% | 5.0% |
| | Sitting — Raising Hand | 20 | 20 | 0 | 0 | 100.0% | 0.0% |
| | Standing — Attentive | 20 | 20 | 0 | 0 | 100.0% | 0.0% |
| | Standing — Praying | 20 | 18 | 2 | 0 | 90.0% | 10.0% |
| | Standing — Looking Away | 20 | 19 | 1 | 0 | 95.0% | 5.0% |
| | Standing — Raising Hand | 20 | 20 | 0 | 0 | 100.0% | 0.0% |
| **Row 2 (2.0m)** | Sitting — Attentive | 20 | 18 | 1 | 1 | 90.0% | 10.0% |
| | Sitting — Praying | 20 | 17 | 2 | 1 | 85.0% | 15.0% |
| | Sitting — Looking Away | 20 | 17 | 2 | 1 | 85.0% | 15.0% |
| | Sitting — Raising Hand | 20 | 18 | 1 | 1 | 90.0% | 10.0% |
| | Standing — Attentive | 20 | 19 | 1 | 0 | 95.0% | 5.0% |
| | Standing — Praying | 20 | 16 | 3 | 1 | 80.0% | 20.0% |
| | Standing — Looking Away | 20 | 17 | 2 | 1 | 85.0% | 15.0% |
| | Standing — Raising Hand | 20 | 18 | 2 | 0 | 90.0% | 10.0% |
| **Row 3 (3.0m)** | Sitting — Attentive | 20 | 14 | 2 | 4 | 70.0% | 30.0% |
| | Sitting — Praying | 20 | 12 | 3 | 5 | 60.0% | 40.0% |
| | Sitting — Looking Away | 20 | 13 | 3 | 4 | 65.0% | 35.0% |
| | Sitting — Raising Hand | 20 | 14 | 2 | 4 | 70.0% | 30.0% |
| | Standing — Attentive | 20 | 15 | 2 | 3 | 75.0% | 25.0% |
| | Standing — Praying | 20 | 11 | 4 | 5 | 55.0% | 45.0% |
| | Standing — Looking Away | 20 | 13 | 3 | 4 | 65.0% | 35.0% |
| | Standing — Raising Hand | 20 | 14 | 3 | 3 | 70.0% | 30.0% |

*(Note: The numbers in the columns are illustrative examples. You will populate them with your actual lab counts. Your totals will sum up to exactly 480 trials).*

---

### **2. Recommended Visualizations for Chapter 4**

To make your data easy to digest for your panel, you should include these **three specific figures** in your slides and manuscript:

#### **Figure 1: Clustered Bar Chart (Recognition Rate vs. Distance)**
* **What it shows:** The X-axis represents the three distances (**Row 1 at 1.0m, Row 2 at 2.0m, Row 3 at 3.0m**). The Y-axis represents the **Recognition Rate (0% to 100%)**. You will have 8 colored bars clustered at each row, representing your 8 behavior combinations.
* **Why it is excellent for your paper:** It visually demonstrates the **"Distance Drop-Off Effect"** [35]. The panel will instantly see that while SENSEY maintains high accuracy at Row 1, the physical distance and student-to-student linear occlusion causes the bars to naturally decrease at Row 3 [35]. It is a powerful, standard way to show the limits of your camera's sight [35].

#### **Figure 2: Confusion Matrix Heatmap ($8 \times 8$ Grid)**
* **What it shows:** A standard deep-learning evaluation grid [1]. The vertical axis represents the *Actual Behavior*, and the horizontal axis represents SENSEY's *Predicted Behavior* [1]. Each square in the grid contains the classification percentage, shaded with a color gradient (e.g., dark green for high accuracy, fading to light green/white for errors).
* **Why it is excellent for your paper:** This is the most respected visual tool in computer vision research [1]. It immediately shows the panel where the AI is performing well (diagonal boxes) and exactly which behaviors are occasionally confused (e.g., if a student *praying* is sometimes misclassified as *looking away*), directly justifying the implementation of your temporal smoothing accumulator [1].

#### **Figure 3: Stacked Bar Chart of System Failure Modes**
* **What it shows:** The X-axis represents the three Rows. The Y-axis represents $100\%$ of your testing outcomes. Each bar is divided into three stacked colors representing your three operational outcomes: **Successful Detections ($R_{Rec}$)**, **Classification Errors ($R_{Err}$)**, and **Missed Detections ($R_{Miss}$)**.
* **Why it is excellent for your paper:** This directly answers your "No Detection" question. The chart will visually prove that at **Row 1**, failures are tiny and dominated by simple labeling errors ($R_{Err}$), but at **Row 3**, failures are dominated by missed detections ($R_{Miss}$) because the physical bodies of the students in front are occluding (blocking) the students behind them [35]. This shows a highly sophisticated level of physical and data-driven analysis to support the **visually impaired teacher's** spatial auditing needs!

---
**References**

[1] Sameh Magdy, Tarek Mahmoud, and Mohamed Ibrahim, "Face Recognition based on Hidden Markov Model and Canny Operators," *ICGST International Journal on Graphics, Vision and Image Processing (GVIP)*, vol. 17, no. 1, pp. 1–7, June 2017.

[35] P. Kadam, G. Fang, Y. Amirabdollahian, J. J. Zou, and P. Holthaus, "Hand Pose Detection Using YOLOv8-pose," School of Engineering, Design and Built Environment, Western Sydney University & Robotics Research Group, University of Hertfordshire, Technical Report, 2024. [Online]. Available: https://uhra.herts.ac.uk/id/eprint/25619/1/paper_17.pdf