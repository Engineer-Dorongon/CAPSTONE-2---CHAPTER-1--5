Here is the finalized **SOP 3** and its matching **Objective 3**. 

By replacing "traditional methods" with **"traditional mobility benchmarks"**, you completely avoid the clunky *"2017 baseline"* phrasing inside the research questions. In your *Definition of Terms* (Chapter 1), you will simply define *"traditional mobility benchmarks"* as your department's established baseline metrics (specifically the $377\text{-second}$ travel time). 

This is highly elegant, academically professional, and perfectly preserves your preferred sentence structure:

---

### **STATEMENT OF THE PROBLEM (SOP 3)**
**Is there a significant improvement in the visually impaired teacher's navigation safety, mobility, and spatial awareness when utilizing the SENSEY system compared to traditional mobility benchmarks?**

---

### **OBJECTIVES OF THE STUDY**

#### **General Objective**
To evaluate the performance, usability, and workability of **SENSEY: An Intelligent Wearable Aid with Real-Time Object Detection and Multimodal Feedback for Inclusive Education** to support **visually impaired teachers**.

#### **Specific Objective 3**
**To determine if there is a significant improvement in the visually impaired teacher's navigation safety, mobility, and spatial awareness when utilizing the SENSEY system compared to traditional mobility benchmarks.**

---
---

# **PARTITION: OPERATIONAL SPECIFICATIONS & STATISTICAL TREATMENT**

### **OPERATIONAL SPECIFICATIONS (PROTOCOL 3)**

* **The Setup:** A classroom obstacle course measuring $10\text{ m} \times 8\text{ m}$ is physically constructed, replicating the exact physical layout and corridor turns of your department's past research [11].
* **The Subjects:** Due to visual impairment recruitment limitations, the study utilizes a **Simulation Control Group consisting of three (3) blindfolded sighted participants** representing the **visually impaired teacher** [11, 12, 19].
* **The Procedure:** Each subject navigates the course using SENSEY in its fully integrated, offline operational mode. The user relies on the local depth-sensing metronome beeps for continuous steering and presses the physical chest button to hear local, offline YOLOv8m spoken descriptions when negotiating narrow desk aisles.
* **Data Size & Sampling:** Each of the 3 subjects executes ten (10) consecutive successful navigation trials, totaling exactly **30 runs** (3 subjects $\times$ 10 trials) [15].
* **Chapter 4 Evidence:** A data table showing the 30 individual trials' completion times (seconds) and average collision counts, compared directly against the traditional mobility benchmark constant of **377 seconds** [15].

---

### **STATISTICAL TREATMENT OF DATA (SOP 3)**

To determine if SENSEY provides a statistically significant improvement in travel speed compared to traditional mobility benchmarks, **Inferential Statistics** are applied [15]. 

Because the study compares the mean completion time of a single experimental sample group ($N = 30$ trials) against a known traditional mobility benchmark constant ($\mu_0 = 377\text{ seconds}$), a parametric **One-Sample $t$-test** is utilized as the primary statistical treatment [15]:

$$t = \frac{\bar{X} - \mu_0}{\frac{s}{\sqrt{N}}}$$

Where:
*   $t$ is the calculated $t$-value compared against the critical $t$-value at a $95\%$ confidence level ($\alpha = 0.05$) [15].
*   $\bar{X}$ is the mean navigation completion time (in seconds) achieved by the three subjects using SENSEY.
*   $\mu_0$ is the traditional mobility benchmark constant ($\mu_0 = 377\text{ seconds}$) [15].
*   $s$ is the standard deviation of SENSEY's trial completion times.
*   $N$ is the total number of navigation trials ($N = 30$) [15].
*   The degrees of freedom ($df$) for this test is defined as:
    $$df = N - 1 = 29$$

#### **The Decision Rule for Chapter 4:**
The calculated $t$-statistic is compared against the critical $t$-value at $df = 29$ and a significance level of **$\alpha = 0.05$**:
*   If the calculated $p$-value is **less than $0.05$** ($p < 0.05$), the **Null Hypothesis ($H_0$) is rejected and the Alternative Hypothesis ($H_a$) is accepted**, mathematically proving SENSEY provides a statistically significant improvement in the teacher's navigation speed and mobility compared to traditional benchmarks [15].
