# FUTURE_CS_02
Security Alert Monitoring &amp; Incident Response

SIEM Incident Response with Elastic Stack

This project demonstrates security alert monitoring, incident analysis, and response reporting using the Elastic Stack (Elasticsearch, Logstash, Kibana, Filebeat).

It simulates real-world SOC analyst tasks by ingesting sample logs, detecting suspicious activities, classifying incidents, and drafting remediation recommendations.

🔧 Tools Used

Elasticsearch (7.x) → Stores & indexes log data

Kibana → Log visualization & dashboarding

Filebeat → Log shipper (ingests logs into Elasticsearch)

Sample Logs → Authentication logs, system events

SIEM Methodology → Alert analysis, classification, remediation

📂 Project Structure
SIEM-Task/
│── sample_logs/              # Contains sample authentication/system logs  
│── elasticsearch.yml         # Config file for Elasticsearch  
│── kibana.yml                # Config file for Kibana  
│── filebeat.yml              # Config file for Filebeat  
│── Incident_Response_Report.md # Detailed analysis & recommendations  
│── README.md                 # Project documentation  

⚡ Setup & Execution

Start Elasticsearch & Kibana

bin\elasticsearch
bin\kibana


Configure Filebeat (point to sample_logs/ directory)

filebeat.inputs:
  - type: log
    paths:
      - C:\ELK\sample_logs\*.log


Run Filebeat

filebeat -e


Access Kibana
👉 http://127.0.0.1:5601

Go to Discover tab → search logs, detect anomalies.

🔎 Sample Incident Analysis

📌 Example log detected:

Aug 11 20:00:01 testhost sshd[1234]: Failed password for invalid user admin from 10.1.2.3 port 5001 ssh2


✅ Analysis:

Multiple failed SSH login attempts from external IP → brute-force attack attempt.

📌 Incident Classification:

Category: Authentication Attack

Severity: Medium → High (if repeated)

📌 Remediation Recommendations:

Block IP 10.1.2.3 at firewall

Enable account lockout policy

Monitor for further brute-force attempts

Consider MFA for SSH access

🛠 Skills Demonstrated

SIEM log ingestion & visualization (Elastic Stack)

Security incident detection & classification

Writing professional Incident Response Reports

Use of Kibana dashboards & log queries
