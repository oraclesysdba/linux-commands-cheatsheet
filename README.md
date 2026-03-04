
<p align="center">
  <img src="https://img.shields.io/badge/Linux-Commands-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux Badge"/>
  <img src="https://img.shields.io/badge/Shell-Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white" alt="Bash Badge"/>
  <img src="https://img.shields.io/badge/Commands-259+-E8B84E?style=for-the-badge" alt="Commands Badge"/>
</p>

<h1 align="center">🐧 Linux Commands Cheatsheet</h1>

<p align="center">
  <b>A comprehensive quick reference to 259+ essential Linux commands across 20 categories.</b><br/>
  Ideal for beginners, developers, and system administrators.
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/samson-j-997403234">
    <img src="https://img.shields.io/badge/Author-Samson%20J-blue?style=flat-square&logo=linkedin" alt="Author"/>
  </a>
</p>

---

## 📖 What's Inside

This repository contains a **complete Linux commands cheatsheet** available in multiple formats:

| File | Format | Description |
|------|--------|-------------|
| `linux-cheatsheet.txt` | 📝 Text | Plain text, terminal-friendly reference |
| `Linux-Cheatsheet.pptx` | 📊 PowerPoint | Professionally designed dark-themed slides |

---

## 📚 Categories Covered

| # | Category | Key Commands |
|---|----------|-------------|
| 1 | **System Information & Status** | `uname`, `uptime`, `hostname`, `free`, `lscpu` |
| 2 | **File & Directory Operations** | `ls`, `cd`, `cp`, `mv`, `rm`, `mkdir`, `find` |
| 3 | **Viewing & Editing Files** | `cat`, `less`, `head`, `tail`, `vim`, `nano` |
| 4 | **File Permissions & Ownership** | `chmod`, `chown`, `chgrp`, `umask` |
| 5 | **User & Group Management** | `useradd`, `usermod`, `passwd`, `sudo`, `su` |
| 6 | **Process Management** | `ps`, `top`, `kill`, `systemctl`, `jobs` |
| 7 | **Text Processing & Search** | `grep`, `sed`, `awk`, `sort`, `cut`, `wc` |
| 8 | **Searching & Finding Files** | `find`, `locate`, `which`, `whereis` |
| 9 | **Disk Usage & Management** | `df`, `du`, `fdisk`, `mount`, `mkfs` |
| 10 | **Archiving & Compression** | `tar`, `gzip`, `zip`, `bzip2`, `xz` |
| 11 | **Networking Commands** | `ping`, `ssh`, `scp`, `curl`, `wget`, `netstat` |
| 12 | **Package Management** | `apt`, `yum`, `dnf`, `dpkg`, `rpm` |
| 13 | **I/O Redirection & Piping** | `>`, `>>`, `\|`, `tee`, `xargs` |
| 14 | **Shell Shortcuts** | `Ctrl+C/Z/D/L/R`, `!!`, `history` |
| 15 | **Cron Jobs & Scheduling** | `crontab`, `at`, cron format |
| 16 | **System Management & Power** | `shutdown`, `reboot`, `modprobe` |
| 17 | **Log Management** | `journalctl`, syslog, auth.log |
| 18 | **Environment Variables** | `export`, `PATH`, `source`, `alias` |
| 19 | **SSH & Remote Access** | `ssh-keygen`, `sshfs`, SSH config |
| 20 | **Useful Tips & Combinations** | One-liners, monitoring, tricks |

---

## 🔐 Quick Reference: Permission Values

```
r (read)    = 4
w (write)   = 2
x (execute) = 1

Common Examples:
  755 (rwxr-xr-x) → Owner full, others read+execute
  644 (rw-r--r--) → Owner read+write, others read only
  700 (rwx------) → Owner full access only
```

---

## ⏰ Quick Reference: Cron Format

```
* * * * *  command
│ │ │ │ │
│ │ │ │ └── Day of Week    (0-7, Sun=0,7)
│ │ │ └──── Month          (1-12)
│ │ └────── Day of Month   (1-31)
│ └──────── Hour           (0-23)
└────────── Minute         (0-59)

Examples:
  0 2 * * *       → Daily at 2:00 AM
  */15 * * * *    → Every 15 minutes
  0 0 * * 0       → Every Sunday at midnight
  30 18 * * 1-5   → Weekdays at 6:30 PM
```

---

## 🚀 How to Use

**Option 1:** Browse this README for a quick overview

**Option 2:** Download `linux-cheatsheet.txt` for a terminal-friendly reference
```bash
# Download directly
curl -O https://raw.githubusercontent.com/YOUR_USERNAME/linux-cheatsheet/main/linux-cheatsheet.txt

# Quick search for a command
grep -i "find" linux-cheatsheet.txt
```

**Option 3:** Download `Linux-Cheatsheet.pptx` for presentations or offline study

---

## 🤝 Contributing

Found a missing command or want to improve a description? Contributions are welcome!

1. Fork this repository
2. Add your changes
3. Submit a pull request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<p align="center">
  <b>Made with ❤️ by <a href="https://www.linkedin.com/in/samson-j-997403234">Samson J</a></b><br/>
  <i>"The command line is a powerful tool — master it and you master the machine."</i>
</p>
