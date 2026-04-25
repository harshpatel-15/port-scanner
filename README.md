# 🔐 Port Scanner

A Python-based TCP port scanner tool built for cyber security learning and network analysis.

---

## 📌 About This Project

This project was built as part of my cyber security learning journey.
A port scanner checks which ports are open or closed on a computer or network — just like a real cyber security professional does!

> ⚠️ **Ethical Use Only** — Only scan your own PC or networks you have permission to scan.

---

## ⚙️ How It Works

1. You give it a target IP address (default: 127.0.0.1 — your own PC)
2. It scans ports 1 to 1024 one by one
3. It tries to connect to each port using TCP
4. If connection succeeds → Port is OPEN
5. If connection fails → Port is CLOSED
6. Shows all open ports at the end

---

## 🛠️ Technologies Used

- **Language:** Python 3
- **Library:** socket (built-in — no installation needed!)
- **Concept:** TCP/IP Networking, Port Scanning

---

## ▶️ How to Run

1. Make sure Python is installed
2. Run the script:
```bash
python port_scanner.py
```
3. To scan your own PC safely use: `127.0.0.1`
4. To change target edit line 6:
```python
target = "127.0.0.1"
```

---

## 📸 Output Example

```
=============================================
      PORT SCANNER - Cyber Security Tool
=============================================
Target   : 127.0.0.1
Ports    : 1 to 1024
---------------------------------------------
Scanning port 100...
  [OPEN]  Port 80
  [OPEN]  Port 443
---------------------------------------------
Scan Complete!
Open Ports Found : 2
Open Ports List  : [80, 443]
=============================================
```

---

## 📚 What I Learned

- TCP/IP networking concepts
- Python socket programming
- How port scanning works in cyber security
- Network security fundamentals

---

## 👨‍💻 Author

**Harsh Patel**
BSc IT Student — GLS University, Ahmedabad
GitHub: github.com/harshpatel-15
