<h1 align="center">👋 Hi, I'm Intasab Fatiam</h1>

<p align="center">
  <b>Aspiring SOC Analyst</b> | Blue Team Enthusiast | Cybersecurity Student<br>
  <i>Learning to detect, investigate, and respond to threats — one log at a time.</i>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Focus-SOC%20Analyst-blue?style=for-the-badge&logo=security&logoColor=white" />
  <img src="https://img.shields.io/badge/Blue%20Team-Defender-0A66C2?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Learning%20%26%20Building-success?style=for-the-badge" />
</p>

---

## 🛡️ About Me

I'm a cybersecurity student on a path to becoming a **SOC (Security Operations Center) Analyst**. I enjoy digging into logs, spotting suspicious behavior, and understanding *how* attacks look from the defender's side. I build hands-on lab projects to turn theory into real detection skills.

🎯 **Goal:** Start my career as a SOC Analyst (Tier 1) and grow into threat detection & incident response.

---

## 🧰 Skills & Tools

| Area | What I've Learned |
|------|-------------------|
| 🌐 **Networking** | Networking fundamentals, TCP/IP, common protocols |
| 🔍 **Packet Analysis** | Wireshark |
| 🐧 **Linux** | Command line, file system, permissions, log files |
| 📡 **Scanning** | Nmap (host discovery, port & service scanning) |
| 📜 **Log Analysis** | Linux `auth.log`, filtering & investigating events |
| 🪟 **Endpoint Monitoring** | Sysmon (Windows event telemetry) |

<p>
  <img src="https://img.shields.io/badge/Wireshark-1679A7?style=flat-square&logo=wireshark&logoColor=white" />
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" />
  <img src="https://img.shields.io/badge/Ubuntu-E95420?style=flat-square&logo=ubuntu&logoColor=white" />
  <img src="https://img.shields.io/badge/Nmap-4682B4?style=flat-square" />
  <img src="https://img.shields.io/badge/Sysmon-0078D6?style=flat-square&logo=windows&logoColor=white" />
  <img src="https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white" />
</p>

---

## 🚀 Featured Project: SSH Brute Force Detection

**Goal:** Detect brute-force login attempts against an SSH service by analyzing Linux authentication logs in a home SOC lab.

### 🧪 Lab Setup
- **Target:** Ubuntu machine (`ubuntu-soc-target`) running OpenSSH
- **Attacker / Source:** Separate host on the lab network attempting repeated SSH logins
- **Data Source:** `/var/log/auth.log`

### 🔎 What I Did
1. Generated multiple failed SSH login attempts against the target.
2. Investigated the logs using Linux command-line tools (`grep`, `tail`, `cut`).
3. Identified repeated `Failed password` events from the same source IP and port.
4. Counted failed attempts to confirm brute-force behavior (`grep -c`).
5. Noted my own investigation activity in the log (`sudo` command entries) — a good reminder that **analyst actions are logged too**.

### 💻 Example Commands

```bash
# View the latest failed SSH logins
sudo grep "Failed password" /var/log/auth.log | tail -n 10

# Count total failed attempts
sudo grep -c "Failed password" /var/log/auth.log
```

### 📌 Key Findings
- Repeated `Failed password` events for the same user from a single source IP within a short time window = **classic brute-force indicator**.
- Log fields useful for investigation: **timestamp, username, source IP, source port, service (sshd)**.

### 📚 What I Learned
- How SSH authentication failures appear in `auth.log`
- How to filter and trim noisy logs to find real signals
- The difference between normal failed logins and brute-force patterns
- Why log retention and monitoring matter for detection

### 🔜 Next Steps
- [ ] Automate detection with a Bash/Python script (threshold-based alerting)
- [ ] Install and configure **Fail2Ban** to block offending IPs
- [ ] Forward logs to a SIEM (Splunk / Wazuh / ELK)
- [ ] Map findings to **MITRE ATT&CK** (T1110 – Brute Force)
- [ ] Write an incident report for the case

> 📸 *Screenshots and full write-up available in the project repository:* **[link to repo]**

---

## 🗺️ Learning Roadmap

- [x] Networking Fundamentals
- [x] Wireshark
- [x] Linux
- [x] Nmap
- [x] Log Analysis
- [x] Sysmon
- [ ] SIEM (Splunk / Wazuh / ELK)
- [ ] MITRE ATT&CK Framework
- [ ] Incident Response Basics
- [ ] Windows Event Logs & Active Directory Security
- [ ] Threat Hunting
- [ ] Security+ / Blue Team certifications

---

## 📫 Let's Connect

<p>
  <a href="https://www.linkedin.com/in/your-profile"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="mailto:your.email@example.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
</p>

<p align="center">
  <i>“Every log tells a story. I'm learning to read them.”</i> 🔐
</p>
