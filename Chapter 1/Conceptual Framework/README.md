# CONCEPTUAL FRAMEWORK

The conceptual framework of this study is anchored on providing independent mobility and classroom management assistance to visually impaired teachers. To systematically realize this engineering goal, the study adopts the traditional Input-Process-Output (IPO) model as its research paradigm, mapping how the system’s physical inputs are processed in real-time to deliver functional assistance to the user.

### Variables of the Study

To ensure academic and scientific validity, the observed variables of this study are conceptually categorized and defined as follows:

#### Independent Variables
* **Student Seating Layout:** The physical positions of students seated across different rows (representing seating depth) and columns (representing lateral offsets) on a 3x3 seating grid.
* **Student Behaviors:** The student posture states (Sitting/Standing) and active behaviors (Attentive, Raising Hand, Looking Away, Praying) being monitored.
* **Classroom Obstacles:** Physical obstacles (backpacks, chairs, desks) placed at specific measured distances.
* **User Posture:** The tilting movements of the teacher's chest during upright, walking, and scanning postures.
* **Navigation Methods:** The three comparative assistance conditions evaluated during trials (standard white cane, automated SENSEY sensor feedback, and SENSEY sensor feedback combined with Claude AI description).

#### Dependent Variables
* **Student Status Monitoring Performance:** Measured through the **Behavior Recognition Rate (%)** and the **Behavior Error Rate (%)**.
* **Obstacle Detection Performance:** Measured through the **Obstacle Detection Success Rate (%)**, **Obstacle Detection Failure Rate (%)**, and **Distance Margin of Error (%)**.
* **Navigation Mobility and Safety:** Measured through the **Navigation Completion Time (seconds)** and the **Obstacle Collision Count**.
* **Spatial Layout Comprehension:** Measured through the teacher's qualitative **Spatial Layout Comprehension Score (1 to 5)**.

#### Control Variables
* **Camera Mounting Height:** Constant at a standard chest height of $1.2\text{ meters}$.
* **Active Warning Range:** Programmed at a constant safety distance of $0.9\text{ meters}$ for standard warnings and $0.5\text{ meters}$ for critical stops and walls.

---

### Paradigm of the Study

The diagrammatic paradigm of SENSEY is presented in Figure 1, illustrating the structured, non-technical flow of how the system processes environmental data to provide real-time classroom capability.

```
+-------------------------------------------------------------------------+
|                                 INPUT                                   |
+-------------------------------------------------------------------------+
| * Real-time images of the classroom and students from the camera        |
| * Distance and spatial terrain data from the depth sensor               |
| * Chest tilt angles and manual button presses from the teacher          |
+-------------------------------------------------------------------------+
                                       |
                                       v
+-------------------------------------------------------------------------+
|                                PROCESS                                  |
+-------------------------------------------------------------------------+
| * Identifying student postures and classroom behaviors                  |
| * Detecting physical obstacles and finding clear walking paths         |
| * Converting visual data into spoken voice and sound instructions       |
+-------------------------------------------------------------------------+
                                       |
                                       v
+-------------------------------------------------------------------------+
|                                 OUTPUT                                  |
+-------------------------------------------------------------------------+
| * Spoken voice reports describing student behavior and attentiveness    |
| * Real-time steering alerts to safely guide the teacher around hazards  |
| * Spoken descriptions detailing the teacher's classroom surroundings     |
+-------------------------------------------------------------------------+
```
**Figure 1. Conceptual Paradigm of SENSEY**

---
NOTE SA BABA PAKIBASA PARANG AWA NALANG
---

# PARTITION: METHODOLOGICAL COMPLIANCE ANALYSIS

Below is the detailed methodological analysis proving how this simplified, capability-focused Conceptual Framework satisfies your department's strict guidelines:

### **1. Compliance with User Feedback: Clear and Non-Technical**
* **The Challenge:** Terms like *"Software Engineering"* and *"Centroid Tracking"* are confusing to general, non-technical panelists.
* **Our Alignment:** We completely stripped out all programming-specific terms and code methods. The IPO box is now written in **short, simple, conversational English sentences** that explain exactly *what SENSEY can do* (its capabilities) instead of *how the code is written*. Any panelist can understand this diagram in 5 seconds.

### **2. Focus on Project Capability (Sensing $\rightarrow$ Processing $\rightarrow$ Outputting)**
* **Input:** Clearly states the raw data the system receives (camera images, depth distances, and physical chest tilts/button presses).
* **Process:** Explains the high-level actions SENSEY takes (identifying behaviors, finding walkable paths, and translating data to voice).
* **Output:** Explains the tangible, final benefits delivered to the teacher (spoken posture audits, auditory lane steering, and surrounding descriptions).

### **3. Full APA Layout Compliance**
* **Heading Standards:** Adheres strictly to APA levels of headings, ensuring the section is organized, academically elegant, and ready to be inserted directly into your Capstone manuscript.
