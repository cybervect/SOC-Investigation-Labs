# Incident Triage: Suspicious SSH Login

**Scenario:** The SOC dashboard flagged a critical alert for a successful SSH authentication from an unknown, suspicious IP address[cite: 5]. 

## Objective
To investigate the critical alert, analyze the reputation of the source IP address, and follow proper escalation procedures for a confirmed compromise[cite: 5, 6, 7].

## Investigation Steps

**1. Alert Identification (SOC Dashboard)**
* Monitored the SOC Dashboard and identified a critical severity alert generated on Sep 27th, 2026 at 12:55.
* The alert message detailed a "Successful SSH login from the suspicious IP address 221.181.185.159".

**2. Threat Intelligence Validation (IP Hunter)**
* Queried the source IP (`221.181.185.159`) using the internal IP Hunter tool to check its reputation against databases like AbuseIPDB and Cisco Talos[cite: 6].
* The database confirmed the IP is malicious and has been involved in 4 known cyber attacks[cite: 6].
* Identified the ISP as China Mobile Communications Corporation[cite: 6].
* Noted the associated threat categories: Port Scan, C2 Server, and PlugX (a known remote access trojan).

**3. Escalation & Remediation (Team Chat & Firewall)**
* Communicated the findings via Team Chat to Will Griffin, Senior Security Analyst, explicitly noting that this was a *successful* authentication attempt rather than a failed brute-force, requiring immediate senior intervention[cite: 7].
* The Senior Analyst acknowledged the evidence and took the lead to initiate further incident response.

## Evidence

### Alert Triage
<img width="907" height="603" alt="1e5ca56c-1d1e-4487-8ee0-3d7670b82882 (1)" src="https://github.com/user-attachments/assets/0f789b6e-8577-4244-9b1d-d55cbd77a3eb" />

### Threat Intelligence 
<img width="905" height="603" alt="59b8f521-6a48-48b8-a2e4-2c12d35cf981 (1)" src="https://github.com/user-attachments/assets/0a6c2662-59a9-431e-a567-048757eb67d5" />

### Escalation
<img width="905" height="605" alt="270583d2-5e0c-4f10-9061-ead76fafca3a (1)" src="https://github.com/user-attachments/assets/ce96aa41-570a-412b-8837-9468d6f78ac3" />

## Conclusion
By verifying the IP address reputation before escalating, the SOC avoided raising a false positive. The identification of C2 and PlugX activity associated with the IP indicates a severe compromise, correctly prompting an immediate handoff to a Senior Security Analyst for active threat containment.
