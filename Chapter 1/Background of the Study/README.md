# 1.1 Background of the Study

Over the past decade, global educational frameworks and employment policies have shifted heavily toward inclusive education and equal-opportunity employment, encouraging professionals with physical disabilities to pursue active careers. However, traditional classroom environments remain physically and socially unaccommodating for a **visually impaired teacher**. Standard teaching spaces are optimized exclusively for sighted instructors, requiring constant visual feedback to manage classroom activities, monitor student engagement, and safely navigate around furniture. Although general assistive mobility tools exist, they are primarily designed for linear outdoor travel and do not address the complex, cluttered, and highly dynamic spatial layouts of active classrooms. This lack of specialized educational assistive technology represents a significant barrier, preventing visually impaired teachers from achieving full professional autonomy and safety in their workplaces.

This professional and physical exclusion is particularly pronounced in the Philippines. Research has documented that visually impaired educators in the Davao Region frequently experience feelings of exclusion and reduced self-confidence because of the lack of structural support and localized assistive technologies (Thongchai, n.d.). This is exacerbated by the inaccessibility of educational infrastructure in major urban centers like Metro Manila, which limits full professional participation (San Jose, n.d.). While some visually impaired teachers successfully develop exceptional personal adaptation strategies—such as relying heavily on spatial memory and acute auditory monitoring (Effendi et al., 2021)—these methods are mentally exhausting and lack technological consistency. Furthermore, basic classroom infrastructure in Philippine public schools often lacks any mobility accommodations, forcing teachers to risk physical injuries (Avila et al., 2023). Standard electronic travel aids fail to detect low-profile tripping hazards (such as backpacks or cables on the floor) and are highly prone to triggering false-positive alerts on the flat floor itself when the user's natural walking gate or chest-slouch dynamically tilts the camera pitch.

To resolve these specific technical and functional limitations, SENSEY has been developed as an intelligent wearable **blind assistive device**. Designed as a chest-mounted system, the device integrates a stereo depth-sensing camera, an inertial measurement sensor, and a high-performance coprocessor to execute parallel processing pathways. For classroom monitoring, the system applies an NPU-accelerated **YOLOv8m-pose estimation algorithm** to classify student postures and active behaviors, stabilized by a temporal smoothing voting method to eliminate split-second classification noise (Kadam et al., 2024). For navigation, the device utilizes a gravity-aligned 3D spatial coordinate rotation algorithm combined with an NPU-accelerated **YOLOv8m object detection algorithm** to detect classroom obstacles, filter out flat floor surfaces, and distinguish clear walkable paths across its lateral safety lanes (Saranya & Arulselvarani, 2025). For context-aware environmental understanding, the cloud-linked **Claude 4.5 Haiku vision-language API** synthesizes natural-language descriptions of the teacher's immediate surroundings (Brilli et al., 2024), delivering these spatial and behavioral insights through intuitive, real-time auditory speech and sound alerts.

The subsequent sections of this chapter outline the theoretical and conceptual frameworks that anchor SENSEY's adaptive design. By establishing a rigorous testing methodology—consisting of a student behavior monitoring grid test, a terrain detection calibration test, and a comparative navigation usability trial against traditional methods, this study aims to provide concrete empirical proof of system usability. Through this structured technological intervention, SENSEY seeks to mathematically and physically validate a new standard of mobility safety and classroom management autonomy for the **visually impaired teacher**.

---
---

# REFERENCES

The following reference list compiles the exact bibliographic entries supporting the citations in your finalized Background of the Study, meticulously formatted according to **APA 7th Edition** guidelines:

Avila, P. G. A., Osea, E. A., Avila, E., Gata, R. R., Portea, J. V., Enimedez, M. A., & De Leon, N. C. (2023). The lived experiences and perceptions of public-school employees in the Philippines: A PWD’s perspective. *International Journal of Business, Law and Education*, *4*(2), 312–321.

Brilli, D. D., Georgaras, E., Tsilivaki, S., Melanitis, N., & Nikita, K. (2024). *AIris: An AI-powered wearable assistive device for the visually impaired*. arXiv. https://doi.org/10.48550/arXiv.2405.07606

Effendi, T., Suyudi, I., & Ali, A. J. K. N. (2021). EFL vision impaired teacher’s classroom management in the eyes of his sighted teenaged students. *TESOL International Journal*, *16*(1), 73–88.

Kadam, P., Fang, G., Amirabdollahian, F., Zou, J. J., & Holthaus, P. (2024). *Hand pose detection using YOLOv8-pose* (Technical Report). School of Engineering, Design and Built Environment, Western Sydney University & Robotics Research Group, University of Hertfordshire. https://uhra.herts.ac.uk/id/eprint/25619/1/paper_17.pdf

Saranya, M., & Arulselvarani, S. (2025). Real-time obstacle detection using YOLOv8 for assistive navigation. *Indian Journal of Science and Technology*. http://indjst.org/articles/real-time-obstacle-detection-using-yolov8-for-assistive-navigation

San Jose, J. (n.d.). *Narrative analysis of teachers with disabilities in Greater Manila using the Social Relational Model of Disability* [Unpublished manuscript].

Thongchai, T. (n.d.). *Personal and professional experiences of teachers with disabilities teaching Filipino in Davao Region: A case study* [Unpublished manuscript].
