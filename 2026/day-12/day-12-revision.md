# Day 12 – Breather & Revision (Days 01–11)

## Goal

## What to Review 

- **Mindset & plan:** Yes, I am very focused and I want to be a Successfull DevOps Engineer
- **Processes & services:** ps, ps aux, top, htop, systemctl status nginc, journalctl -u nginx -n 50 etc..
- **File skills:** echo >>, chmod, chown, ls -l, cp, mkdir etc..

## Mini Self-Check 

**Which 3 commands save you the most time right now, and why?**

- journalctl -u -f (Helps me monitor service logs in real time and quickly identify errors.)
- pa aux --sort=-%cpu | head -n 10 (Quickly shows which processes are consuming high CPU.)
- ls -l (Helps me check file permissions, ownership, and directory details instantly.)

**How do you check if a service is healthy? List the exact 2–3 commands you’d run first.**

- systemctl status nginx(service)
- journalctl -u nginx -n 50 
- ps aux | grep nginx

**How do you safely change ownership and permissions without breaking access? Give one example command.**

- chown -R professor:planners heist-project/

**What will you focus on improving in the next 3 days?**

- Linux Troubleshooting Practice
- File/Directory Permission and Ownership
- Shell Scripting in details