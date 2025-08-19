# Splunk-Investigation

## Objective
This SIEM project aimed to establish a controlled environment for simulating and detecting a brute force attack. The goals were to analyze the baseline traffic and establish some alerts, creating baselines after analyzing the current traffic. Then, after a simulated attack, to identify the attack itself, determine whether the alerts generated were successful, and then learn how to combine that data in a report and explain the findings.

### Skills Learned
- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Creation and fine-tuning alerts and baselines.
- Escalation procedures.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.
- Deployed a new add-on.
- Reporting an IOC and recommended mitigations.

### Tools Used
- Splunk
- SIEM System for log injestion and analysis.

## Steps
<img width="775" height="392" alt="image" src="https://github.com/user-attachments/assets/3e92b888-4e0d-44cc-8d03-93c15e78380a" />

*Ref 1: Screenshot of Project Overview*
<img width="784" height="399" alt="image" src="https://github.com/user-attachments/assets/48ed4bbd-cbd6-4fe9-9ddf-51048695669b" />

*Ref 2: Lumu Add-On*

Logs analyzed: 
- Windows server logs, before and after the attack
- Apache server logs, before and after the attack

<img width="807" height="428" alt="image" src="https://github.com/user-attachments/assets/b67f5d6a-9988-4dc7-af74-8b5ba5aa9f47" />
<img width="795" height="324" alt="image" src="https://github.com/user-attachments/assets/7d6160bb-7d3c-401b-9d86-02f1b84c9be1" />
<img width="787" height="327" alt="image" src="https://github.com/user-attachments/assets/f894dfcf-5d6b-4613-b05f-197c0d460887" />

*Ref 3: Initial Alerts Created for Windows Log*

<img width="791" height="427" alt="image" src="https://github.com/user-attachments/assets/6ba52234-17d5-4151-b61a-f90949df1b45" />
<img width="833" height="367" alt="image" src="https://github.com/user-attachments/assets/f8e74ad0-3dc8-465d-9d6b-392b97fd4b8b" />

*Ref 4: Windows Logs Dashboard Before the Attack*
<img width="808" height="202" alt="image" src="https://github.com/user-attachments/assets/a26b1924-177a-471c-a59c-c2cad8442f7b" />

*Ref 5: Apache Logs Created*

<img width="720" height="384" alt="image" src="https://github.com/user-attachments/assets/10e8d2d0-c4a8-48af-ae28-62a62a33517a" />
<img width="712" height="291" alt="image" src="https://github.com/user-attachments/assets/21ecdc2e-a383-4524-b3f8-e8043abc146e" />
<img width="811" height="377" alt="image" src="https://github.com/user-attachments/assets/67cfabc6-cbce-4ea3-8bf6-92aeaeee9987" />

*Ref 6: Apache Dashboard Before the Attack*

- After the simulated attack, noted an increase in high severity level activiies in Windows server logs, indicating an attack. Also noted a spike in failed Windows activities. 
The sudden increase in failed activities indicated potential malicious activity, such as a brute force attack or user enumeration.
- The number of failed Windows activity rose above the previously set threshold.

<img width="631" height="316" alt="image" src="https://github.com/user-attachments/assets/c504b5f7-02cd-4d8c-8eea-727c4d3267d3" />

<img width="680" height="253" alt="image" src="https://github.com/user-attachments/assets/44980ffb-e974-4c39-84aa-c8da466185ac" />

<img width="717" height="266" alt="image" src="https://github.com/user-attachments/assets/d6f718be-c7c4-4fcc-b761-6157c52150b7" />

*Ref 7: Summary of Windows Attack Analysis*
- Analyzing the Apache server logs, a spike in POST activity was noted.
- Geolocation showed a spike in activity from a new location (Kiev).
- Also detected a spike in activities for 2 URIs from 6 to 8pm, indicating a potential brute force attack.
  <img width="676" height="245" alt="image" src="https://github.com/user-attachments/assets/f4f03c5e-4788-4036-9aa1-86d095acb315" />
  
<img width="723" height="292" alt="image" src="https://github.com/user-attachments/assets/17263ad8-ade6-434d-8211-4ed01d0a3d45" />

<img width="675" height="332" alt="image" src="https://github.com/user-attachments/assets/8e5609f6-909e-407b-b1b1-10cd8d061766" />

*Ref 8: Summary of Apache Attack Analysis*

CONCLUSIONS:

- Given the data in the logs, determined that a brute force attack had occurred, originted in Ukraine.
- Determined the primary user involved, though there was other suspicious activity also noted.
- For future mitigations, determined that 2FA, identity lockout after 5 failed attempts, and IP Access Restrictions should be put in place.





