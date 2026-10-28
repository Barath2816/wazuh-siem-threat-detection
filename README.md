# Wazuh SIEM Custom Detection Lab

## Overview
This project demonstrates a custom Wazuh SIEM deployment for endpoint security monitoring. It includes custom detection rules for unauthorized MAC address changes and Nmap port scan detection, along with real-time alerting, active response, dashboard visualization, and email notifications.

---

## Features

✔ Real-time endpoint monitoring

✔ MAC address spoofing detection

✔ Nmap port scan detection

✔ Custom Wazuh detection rules

✔ JSON and Journald log collection

✔ Dashboard visualization

✔ MITRE ATT&CK mapping

✔ Email notifications

✔ Active Response (MAC restoration)

✔ Custom XML rule development

✔ Security event investigationReal-time endpoint monitoring

✔ MAC address spoofing detection

✔ Nmap port scan detection

✔ Custom Wazuh detection rules

✔ JSON and Journald log collection

✔ Dashboard visualization

✔ MITRE ATT&CK mapping

✔ Email notifications

✔ Active Response (MAC restoration)

✔ Custom XML rule development

✔ Security event investigation

---

## Architecture

```
                    Attacker (Nmap)

                           │
                           ▼

                 Kali Linux (Agent)

            ┌──────────────┴──────────────┐

            ▼                             ▼

      MAC Monitor                  iptables Logs

      (Python JSON)             (Kernel Journald)

            ▼                             ▼

          Wazuh Agent (Log Collection)

                    ▼

          Ubuntu Wazuh Manager

                    ▼

         Custom XML Detection Rules

                    ▼

        ┌────────┬─────────┬──────────┐

        ▼        ▼         ▼          ▼

   Dashboard   Email   Active Response  MITRE Mapping
```

---

## Technologies Used

| Technology | Purpose |
|------------|----------|
| Wazuh | SIEM |
| Ubuntu | Manager |
| Kali | Agent |
| Python | MAC Detection |
| Bash | Active Response |
| XML | Custom Rules |
| JSON | Log Generation |
| iptables | Scan Logging |
| journald | Kernel Logs |
| Nmap | Attack Simulation |
| Postfix | Email Alerts |
| VirtualBox | Lab |

---

## Project Structure

```
Wazuh-MAC-Address-Change-Detection/
│
├── docs/
├── diagrams/
├── screenshots/
├── scripts/
├── sample_logs/
├── wazuh/
├── README.md
├── LICENSE
├── requirements.txt
└── .gitignore
```
## Nmap Detection

```
Attacker runs Nmap

↓

iptables logs SYN packets

↓

Kernel Journald

↓

Wazuh Agent

↓

Manager

↓

Custom XML Rules

↓

Dashboard Alert

↓

MITRE T1046

↓

Investigation

```

---


## Custom Detection Rules

Rule ID    Purpose

100100     Detect Nmap scan

100101     Detect high-frequency port scan

100500     Detect MAC address change

100501     Trigger Active Response

---



## Sample Attacks 

Rule ID: 100101

Level: 12

Description:

Possible Nmap Port Scan detected from 192.168.56.108

MITRE

T1046

Source IP

192.168.56.108

Destination IP

192.168.56.107

Protocol

TCP

Destination Port

6901

Timestamp

2026-10-12 19:13




## Screenshots


### Dashboard
<img width="1852" height="776" alt="Screenshot 2026-09-19 175850" src="https://github.com/user-attachments/assets/30764d7f-2d1c-4d07-b0cd-f34a2f6ffdf0" />
<img width="1853" height="802" alt="Screenshot 2026-09-19 175900" src="https://github.com/user-attachments/assets/94c56cd6-3464-40cc-87fc-766d73a6f0f5" />

### Endpoint
<img width="1846" height="660" alt="Screenshot 2026-09-19 175615" src="https://github.com/user-attachments/assets/d1e075e4-d11c-4934-99eb-775d674a5623" />


### Email Alert
<img width="1506" height="642" alt="Screenshot 2026-09-19 180122" src="https://github.com/user-attachments/assets/fd97174d-75fa-4364-99b1-35098dd7ef6f" />


### Architecture
<img width="1223" height="1286" alt="Wazuh SIEM Custom Detection Lab Workflow" src="https://github.com/user-attachments/assets/d4fe05ef-80b6-42ed-bcbb-0f26140c70a8" />



---



## Real World Use Cases

• Detect reconnaissance before exploitation

• Detect MAC spoofing inside enterprise networks

• Monitor endpoint activity using Wazuh

• Support SOC analysts during investigations

• Demonstrate custom SIEM detection engineering



## MITRE ATT&CK Mapping

Technique

T1046

Network Service Discovery

Used to detect reconnaissance through Nmap scanning.


## Future Enhancements

Detect UDP, ACK, FIN, NULL, and Xmas scans.
Integrate Suricata IDS alerts.
Add GeoIP enrichment for external attackers.
Integrate VirusTotal and AbuseIPDB.
Send alerts to Slack or Microsoft Teams.
Create custom Wazuh dashboards.
Automate incident response playbooks.

---



## Author

Barath P


Cyber Security Enthusiast

---



## License

This project is licensed under the MIT License.
