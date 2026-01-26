# SSH Honeypot (Cowrie) Deployment
**About Project**
This project involved deploying an SSH honeypot using Cowrie in a virtualized lab environment to simulate real-world attacker behavior. The goal was to observe and analyze malicious SSH activity, including brute-force attempts, command execution, and potential malware deployment. This strengthened my defensive security skills and improved my ability to detect and analyze attacker tactics.


**Technologies**
- Docker
- Cowrie Honeypot
- Kali Linux (Attacker VM)
- Parrot Linux (Honeypot VM)
- VirtualBox
- SSH
- Nmap
- Log analysis (Cowrie logs)


**Features**
- Runs a fully functional SSH honeypot on port 2222
- Captures and logs attacker behavior and commands
- Simulates a real Linux system to attract attackers
- Isolated environment to prevent accidental damage
- Generates forensic evidence for analysis


**Keyboard Shortcuts**
- Start honeypot container:
docker run -p 2222:2222 cowrie/cowrie:latest
- Scan honeypot SSH port:
nmap -sV -p 2222 <victim_ip>
- SSH into honeypot:
ssh root@<victim_ip> -p 2222
- View running containers:
docker ps -a


**The Process**
1. Set up a dedicated Linux VM to run Cowrie
2. Install Docker and configure permissions
3. Start the Cowrie honeypot container on port 2222
4. Use Kali Linux as the attacker VM to scan and connect
5. Simulate attacks such as brute-force attempts and command execution
6. Collect logs and analyze attacker behavior



**Overall Growth**
This project helped me build practical skills in defensive security, attack simulation, and incident analysis. It improved my ability to identify malicious behavior, analyze attack patterns, and understand how attackers interact with SSH services in real environments.


**What I Learned**
- 🛠️ How to deploy Cowrie in Docker using docker run and configure port forwarding (2222:2222)
- 🔐 SSH attack simulation: how attackers use brute-force attempts and automated scripts to guess credentials
- 🧩 Network isolation with VirtualBox (Host-only network) to safely run honeypots without affecting real systems
- 🧪 How to use nmap for service discovery (nmap -sV -p 2222) to identify open SSH services
- 🧾 Log analysis skills by reviewing Cowrie logs to identify attacker TTPs (Tactics, Techniques, and Procedures)
- 🔍 Forensic evidence collection from Docker containers (docker ps -a, container logs)
- ⚙️ Understanding attacker behavior by analyzing command patterns like uname -a, cat /etc/passwd, and netstat
- 🧠 How honeypots work: how they simulate real systems and capture malicious activity for research and defense
- 📌 Improved threat awareness by learning common SSH exploitation techniques used in real-world environments


**How Can It Be Improved?**
- Add automated log analysis using Python or ELK stack
- Integrate with SIEM tools for real-time monitoring
- Add multiple honeypots (FTP, HTTP, SMB) to diversify attack data
- Implement alerting for suspicious behavior
- Store and visualize data with Grafana dashboards


**Video**
Coming soon — I will record a walkthrough of the setup and attack simulation.
