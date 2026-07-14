### **SPECIFIC OBJECTIVE 2**
**To measure the detection reliability, lane classification accuracy (Left, Center, Right), and decision-making success of SENSEY, the blind assistive device, across its physical lanes when executing walkable lane decisions and generating offline, local auditory descriptions of seven (7) trained classroom obstacles.**

---

### **OPERATIONAL SPECIFICATIONS (PROTOCOL 2)**

* **The Setup:** Seven (7) distinct pre-trained classroom obstacle classes are prepared: `person`, `chair`, `dining table`, `backpack`, `laptop`, `book`, and `bottle`. Obstacles are physically positioned in the Left, Center, and Right lanes.
* **The Procedure:** To evaluate SENSEY's directional decision-making and offline verbal descriptions under controlled conditions, each of the 7 obstacles is tested across five (5) distinct lane-blocking configurations:
  * *Scenario 1 (All Lanes Clear):* SENSEY must output `FORWARD` and verbally say: *"No object detected."* [15]
  * *Scenario 2 (Center Lane Blocked):* SENSEY must output `TURN RIGHT` and verbally say: *"Left: none, Center: [Object Name], Right: none"* (e.g., *"Left: none, Center: chair, Right: none"*), generated locally by the YOLOv8m detection [15, 22].
  * *Scenario 3 (Center & Right Lanes Blocked):* SENSEY must output `TURN LEFT` and verbally say: *"Left: none, Center: [Object Name], Right: [Object Name]"*.
  * *Scenario 4 (All Lanes Blocked):* SENSEY must output `STOP` and verbally say: *"Left: [Object Name], Center: [Object Name], Right: [Object Name]"*.
  * *Scenario 5 (Center Blocked close-up at 0.5m):* SENSEY must output `STOP! WALL INFRONT` and verbally say: *"Left: none, Center: wall, Right: none"* [15].
* **Data Size & Sampling:** Ten (10) consecutive trials captured per configuration for each of the 7 trained objects, totaling exactly **350 samples** (7 objects $\times$ 5 scenarios $\times$ 10 trials).
* **Chapter 4 Evidence:** An obstacle evaluation table showing the **Decision Success Rate (%)**, **Local Auditory Spoken Success Rate (%)**, and overall system error profiles.

---

### **STATISTICAL TREATMENT OF DATA (SOP 2)**

To evaluate the operational reliability of SENSEY’s walkable lane decision-making and offline verbal descriptions, **Descriptive Statistics** are applied [15]. 

The success and failure rates of your second research objective are calculated using the **Weighted Arithmetic Mean (Aggregated Frequency Method)**, pooling the raw frequencies of correct outputs across all $N_{Nav\_Total} = 350$ individual environmental trials ($7\text{ trained objects} \times 5\text{ scenarios} \times 10\text{ trials}$) [15]:

$$N_{Nav\_Total} = 350$$

#### **1. Overall Lane Decision Performance Metrics ($N = 350$)**

##### **A. Overall Lane Decision Success Rate ($R_{Decision\_Success}$):**
This metric measures how reliably SENSEY's navigation engine chooses the correct steering path based on physical lane blockages [15]:

$$R_{Decision\_Success} = \frac{\sum_{i=1}^{7} S_{Dec\_i}}{350} \times 100$$

Where $\sum_{i=1}^{7} S_{Dec\_i}$ represents the sum of all successful steering decisions executed across the 350 total trials [15].

##### **B. Overall Lane Decision Failure Rate ($R_{Decision\_Failure}$):**
This metric measures the overall failure rate of SENSEY’s steering logic [15]:

$$R_{Decision\_Failure} = \frac{\sum_{i=1}^{7} F_{Dec\_i}}{350} \times 100$$

Where $\sum_{i=1}^{7} F_{Dec\_i}$ is the sum of all incorrect steering decisions across the 350 total trials.

$$\text{Note: } R_{Decision\_Success} + R_{Decision\_Failure} = 100.0\%$$

---

#### **2. Overall Auditory Spoken Performance Metrics ($N = 350$)**

##### **A. Overall Auditory Spoken Success Rate ($R_{Description\_Success}$):**
This metric measures how accurately the system's verbal reports describe the classroom layout to the **visually impaired teacher** [15]:

$$R_{Description\_Success} = \frac{\sum_{i=1}^{7} S_{Desc\_i}}{350} \times 100$$

Where $\sum_{i=1}^{7} S_{Desc\_i}$ represents the sum of all correct spoken lane descriptions generated across the 350 total trials [15].

##### **B. Overall Auditory Spoken Failure Rate ($R_{Description\_Failure}$):**
This metric measures the failure rate of SENSEY’s verbal scene descriptions, representing instances where an obstacle was misidentified or missed entirely [15]:

$$R_{Description\_Failure} = \frac{\sum_{i=1}^{7} F_{Desc\_i}}{350} \times 100$$

Where $\sum_{i=1}^{7} F_{Desc\_i}$ is the sum of all incorrect spoken descriptions across the 350 total trials.

$$\text{Note: } R_{Description\_Success} + R_{Description\_Failure} = 100.0\%$$

---

#### **3. Object-Specific Performance Metrics ($N_{Object} = 50$ each)**

To profile SENSEY's performance across different physical shapes, each of the 7 obstacles is evaluated individually across its 50 trials ($5\text{ scenarios} \times 10\text{ trials}$):

##### **A. Object-Specific Lane Decision Success and Failure Rates:**
$$R_{Dec\_Object} = \frac{\sum_{i=1}^{5} S_{Dec\_Object,i}}{50} \times 100$$

$$R_{Dec\_Failure\_Object} = \frac{\sum_{i=1}^{5} F_{Dec\_Object,i}}{50} \times 100$$

$$\text{Note: } R_{Dec\_Object} + R_{Dec\_Failure\_Object} = 100.0\%$$

##### **B. Object-Specific Auditory Spoken Success and Failure Rates:**
$$R_{Desc\_Object} = \frac{\sum_{i=1}^{5} S_{Desc\_Object,i}}{50} \times 100$$

$$R_{Desc\_Failure\_Object} = \frac{\sum_{i=1}^{5} F_{Desc\_Object,i}}{50} \times 100$$

$$\text{Note: } R_{Desc\_Object} + R_{Desc\_Failure\_Object} = 100.0\%$$

---
**References**

[11] D. Barrinuevo, G. Jacosalem, J. N. Lagahit, M. J. Lobedica, M. R. Salar, and R. Tolentino, "Precise Obstacles Avoidance System for Visually Impaired People using Xbox 360 Kinect," *ICGST International Journal on Graphics, Vision and Image Processing (GVIP)*, vol. 17, no. 1, pp. 15–23, June 2017.  
https://vertexaisearch.cloud.google.com/grounding-api-redirect/AUZIYQFfJi8GowO1tLJVMxiCEXmfv3_8IplvmriSKrOKBOIUI9gEq4py5QS0jSgJinsVLRTfp4T1o2ePy7-5nwwtxQ2AFZZqMKimdTrhNwXld6lwIQDDxhkBEy0jJmTHvMg7uYEz4mVpxoFsYAHcWyMV4fmFL_FBlccQ7gUzcQ==

[12] J. R. Alayon, V. G. D. Corciega, N. M. L. Genebago, A. B. A. Hernandez, C. R. C. Labitoria, and R. E. Tolentino, "Design of Wearable Wrist Haptic Device for Blind Navigation using Microsoft Kinect for Xbox 360," in *Proceedings of the 2020 4th International Conference on Trends in Electronics and Informatics (ICOEI)*, 2020, pp. 1005–1010, doi: 10.1109/ICOEI48184.2020.9143005.  
https://doi.org/10.1109/ICOEI48184.2020.9143005

[15] Department of Education. (2024). *Statistical treatment of data* [Slide presentation]. ETUlay.

[22] D. Barrinuevo, G. Jacosalem, J. N. Lagahit, M. J. Lobedica, M. R. Salar, and R. Tolentino, "Precise Obstacles Avoidance System for Visually Impaired People using Xbox 360 Kinect," *ICGST International Journal on Graphics, Vision and Image Processing (GVIP)*, vol. 17, no. 1, pp. 15–23, June 2017.
