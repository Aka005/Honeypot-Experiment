# SSH Honeypot (Cowrie) Deployment
This project involved deploying an SSH honeypot using Cowrie in a virtualized lab environment to simulate real-world attacker behavior. The goal was to observe and analyze malicious SSH activity, including brute-force attempts, command execution, and potential malware deployment. This strengthened my defensive security skills and improved my ability to detect and analyze attacker tactics.
<br><br>
## 🧰 Technologies
- Docker
- Cowrie Honeypot
- Kali Linux (Attacker VM)
- Parrot Linux (Honeypot VM)
- VirtualBox
- SSH
- Nmap
- Log analysis (Cowrie logs)
<br><br>
## ✨ Features
- Runs a fully functional SSH honeypot on port 2222
- Captures and logs attacker behavior and commands
- Simulates a real Linux system to attract attackers
- Isolated environment to prevent accidental damage
- Generates forensic evidence for analysis
<br><br>
## ⌨️ Keyboard Shortcuts / Commands
- Start honeypot container:
docker run -p 2222:2222 cowrie/cowrie:latest
- Scan honeypot SSH port:
nmap -sV -p 2222 <victim_ip>
- SSH into honeypot:
ssh root@<victim_ip> -p 2222
- View running containers:
docker ps -a
<br><br>
## 🔄 The Process
1. Set up a dedicated Linux VM to run Cowrie
2. Install Docker and configure permissions
3. Start the Cowrie honeypot container on port 2222
4. Use Kali Linux as the attacker VM to scan and connect
5. Simulate attacks such as brute-force attempts and command execution
6. Collect logs and analyze attacker behavior
<br><br>
## 📈 Overall Growth
This project significantly improved my hands-on defensive security experience. I gained confidence working with Linux, Docker, SSH services, and network isolation, while learning how attackers probe and exploit exposed systems. It strengthened my ability to think like both an attacker and a defender, a critical mindset for cybersecurity roles.
<br><br>
## What I Learned
- 🛠️ How to deploy and manage Cowrie honeypots using Docker, including port forwarding (2222:2222)
- 🔐 How attackers conduct SSH brute-force attacks using automated tools and weak credentials
- 🌐 How Host-only networking in VirtualBox safely isolates honeypots from production networks
- 🧪 How to use Nmap service detection (-sV) to identify exposed SSH services
- 🧾 How to analyze Cowrie logs to extract attacker TTPs and session data
- 🔍 How to collect forensic evidence from Docker containers using container inspection and logs
- ⚙️ How attackers perform post-login reconnaissance, including commands like uname -a, cat /etc/passwd, and netstat
- 🧠 How honeypots deceive attackers and collect intelligence without exposing real systems
- 📌 Improved awareness of real-world SSH exploitation techniques used in the wild
<br><br>
## How Can It Be Improved?
- Automate log parsing using Python or an ELK stack
- Integrate with a SIEM for real-time alerting
- Deploy additional honeypots (FTP, HTTP, SMB) for broader coverage
- Implement alerts for high-risk attacker behavior
- Visualize attack data using Grafana dashboards

## ▶️ Running the Project
1. Set Up the Lab
- Create two VirtualBox VMs:
🛡️ Honeypot: Parrot Linux
🧨 Attacker: Kali Linux
- Configure both VMs to use a Host-only Network
2. Install Docker (Honeypot VM)
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
3. Run the Cowrie SSH Honeypot
docker run -p 2222:2222 cowrie/cowrie:latest
4. Find the Honeypot IP
ip a
📌 Use the Host-only IP (example: 192.168.56.106)
5. Simulate Attacks (Kali VM)
nmap -sV -p 2222 192.168.56.106
ssh root@192.168.56.106 -p 2222
6. Review Logs (Honeypot VM)
docker logs <container_id>

## Video
Coming soon — I will record a walkthrough of the setup and attack simulation.
