<!-- ===================== HEADER ===================== -->
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0A66C2,100:00C9A7&height=220&section=header&text=Hi,%20I'm%20[Your%20Name]&fontSize=48&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=Aspiring%20SOC%20Analyst%20%7C%20Blue%20Team%20Enthusiast&descAlignY=58&descSize=20" width="100%" />

<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1200&color=00C9A7&center=true&vCenter=true&width=700&lines=%F0%9F%9B%A1%EF%B8%8F+Learning+to+detect+threats+one+log+at+a+time;%F0%9F%94%8D+Log+Analysis+%7C+Wireshark+%7C+Nmap+%7C+Sysmon;%F0%9F%90%A7+Linux+%26+Networking+Enthusiast;%F0%9F%8E%AF+Goal%3A+Become+a+SOC+Analyst" alt="Typing SVG" />
</a>

<br/>

<img src="https://komarev.com/ghpvc/?username=YOUR_GITHUB_USERNAME&label=Profile%20Views&color=0A66C2&style=for-the-badge" />
<img src="https://img.shields.io/badge/Focus-SOC%20Analyst-0A66C2?style=for-the-badge" />
<img src="https://img.shields.io/badge/Status-Learning%20%26%20Building-success?style=for-the-badge" />

</div>

---

## 🛡️ About Me

I'm a cybersecurity student on a path to becoming a **SOC (Security Operations Center) Analyst**. I enjoy digging into logs, spotting suspicious behavior, and understanding *how* attacks look from the defender's side. I build hands-on lab projects to turn theory into real detection skills.

🎯 **Goal:** Start my career as a Tier 1 SOC Analyst and grow into threat detection & incident response.

---

## 🧰 Skills & Tools

<div align="center">

<img src="https://skillicons.dev/icons?i=linux,ubuntu,bash,python,windows,git,github,vscode&theme=dark" />

<br/><br/>

<img src="https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white" />
<img src="https://img.shields.io/badge/Nmap-4682B4?style=for-the-badge" />
<img src="https://img.shields.io/badge/Sysmon-0078D6?style=for-the-badge&logo=windows&logoColor=white" />
<img src="https://img.shields.io/badge/Log%20Analysis-FF6B6B?style=for-the-badge" />
<img src="https://img.shields.io/badge/Networking-00C9A7?style=for-the-badge" />

</div>

| Area | What I've Learned |
|------|-------------------|
| 🌐 **Networking** | Fundamentals, TCP/IP, common protocols |
| 🔍 **Packet Analysis** | Wireshark |
| 🐧 **Linux** | Command line, file system, permissions, log files |
| 📡 **Scanning** | Nmap (host discovery, port & service scanning) |
| 📜 **Log Analysis** | Linux `auth.log`, filtering & investigation |
| 🪟 **Endpoint Monitoring** | Sysmon telemetry |

---

## 🚀 Featured Project: SSH Brute Force Detection

**Goal:** Detect brute-force login attempts against an SSH service by analyzing Linux authentication logs in a home SOC lab.

### 🗺️ Detection Workflow

```mermaid
flowchart LR
    A[💻 Attacker Host] -->|Repeated SSH logins| B[🐧 Ubuntu SOC Target]
    B -->|Writes events| C[(📜 /var/log/auth.log)]
    C -->|grep / tail / cut| D[🔎 Analyst Investigation]
    D --> E{Same IP, many<br/>Failed password?}
    E -->|Yes| F[🚨 Brute Force Detected]
    E -->|No| G[✅ Normal Activity]
```

### 🧪 Lab Setup
- **Target:** Ubuntu machine (`ubuntu-soc-target`) running OpenSSH
- **Source:** Separate host on the lab network attempting repeated SSH logins
- **Data Source:** `/var/log/auth.log`

### 💻 Investigation in Action

```console
soc@ubuntu-soc-target:~$ sudo grep "Failed password" /var/log/auth.log | tail -n 10
sshd[2402]: Failed password for soc from 192.168.163.1 port 50926 ssh2
sshd[2402]: Failed password for soc from 192.168.163.1 port 50926 ssh2
sshd[2402]: Failed password for soc from 192.168.163.1 port 50926 ssh2

soc@ubuntu-soc-target:~$ sudo grep -c "Failed password" /var/log/auth.log
```

> 📸 *Add your screenshot here:* `![Brute force detection](images/bruteforce-detection.png)`

### 📌 Key Findings
- Repeated `Failed password` events for the same user from a single source IP in a short time window = **classic brute-force indicator**.
- Useful fields: **timestamp, username, source IP, source port, service (sshd)**.
- My own `sudo` commands also appeared in the log, a reminder that **analyst actions are logged too**.

### 📚 What I Learned
- How SSH authentication failures appear in `auth.log`
- Filtering noisy logs to find real signals
- Normal failed logins vs. brute-force patterns

### 🔜 Next Steps

| Task | Status |
|------|--------|
| Automate detection with a Bash/Python script | 🔲 Planned |
| Block offenders with Fail2Ban | 🔲 Planned |
| Forward logs to a SIEM (Splunk / Wazuh / ELK) | 🔲 Planned |
| Map to MITRE ATT&CK (T1110 – Brute Force) | 🔲 Planned |
| Write a full incident report | 🔲 Planned |

---

## 🗺️ Learning Roadmap

```mermaid
timeline
    title My SOC Analyst Journey
    Completed : Networking Fundamentals : Wireshark : Linux : Nmap : Log Analysis : Sysmon
    In Progress : SSH Brute Force Detection Lab
    Up Next : SIEM (Splunk / Wazuh) : MITRE ATT&CK : Incident Response
    Future : Threat Hunting : Security+ / Blue Team Certs
```

<div align="center">

| Progress | |
|---|---|
| Fundamentals | ![](https://geps.dev/progress/100) |
| Detection & Analysis | ![](https://geps.dev/progress/40) |
| SIEM & IR | ![](https://geps.dev/progress/10) |

</div>

---

## 📊 GitHub Stats

<div align="center">

<img height="170" src="https://github-readme-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME&show_icons=true&theme=tokyonight&hide_border=true" />
<img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_GITHUB_USERNAME&layout=compact&theme=tokyonight&hide_border=true" />

<br/>

<img src="https://streak-stats.demolab.com?user=YOUR_GITHUB_USERNAME&theme=tokyonight&hide_border=true" />

<br/>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=YOUR_GITHUB_USERNAME&theme=tokyo-night&hide_border=true" width="95%" />

</div>

---

## 📫 Let's Connect

<div align="center">

<a href="https://www.linkedin.com/in/your-profile"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
<a href="mailto:your.email@example.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>

<br/><br/>

<i>“Every log tells a story. I'm learning to read them.”</i> 🔐

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00C9A7,100:0A66C2&height=120&section=footer" width="100%" />

</div>
