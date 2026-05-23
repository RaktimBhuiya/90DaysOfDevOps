# Day 07 – Linux File System Hierarchy & Scenario-Based Practice

# Task

**Part 1: Linux File System Hierarchy (30 minutes)**
**Document the purpose of these essential directories:**

1. **Core Directories (Must Know):**

- / (root) - The starting point of everything

- /home - User home directories

- /root - Root user's home directory

- /etc - Configuration files

- /var/log - Log files (very important for DevOps!)

- /tmp - Temporary files

2. **Additional Directories (Good to Know):**

- /bin - Essential command binaries

- /usr/bin - User command binaries

- /opt - Optional/third-party applications


**Hands-on task:**

**Find the largest log file in /var/log**
- du -sh /var/log/* 2>/dev/null | sort -h | tail -5

**Look at a config file in /etc**
- cat /etc/hostname

**Check your home directory**
- ls -la ~

**Part 2: Scenario-Based Practice**

Example Scenario: Check if a service is running

Question: How do you check if the 'nginx' service is running?
My Solution (Step by step):

**Step 1: Check service status**

- systemctl status nginx

Why this command? It shows if the service is active, failed, or stopped

**Step 2: If service is not found, list all services**

- systemctl list-units --type=service

Why this command? To see what services exist on the system

**Step 3: Check if service is enabled on boot**

- systemctl is-enabled nginx

# Scenario 1: Service Not Starting
- First check: Is the service running or failed?
- Then check: What do the logs say?
- Finally check: Is it enabled to start on boot?

**step 1**
- systemctl status myapp

**step 2**
- journalctl -u myapp -n 50

**step 3**
- systemctl is-enabled myapp

**step 4**
- systemctl restart myapp

# Scenario 2: High CPU Usage
**Your manager reports that the application server is slow.
You SSH into the server. What commands would you run to identify
which process is using high CPU?**

**Hint:**

- Use a command that shows live CPU usage
- Look for processes sorted by CPU percentage
- Note the PID (Process ID) of the top process

**Step 1**
- top

**Shows:**
- live CPU usage
- memory usage
- running processes
- Top CPU consumers appear at top.

**Press:**
- q

to exit.

**Step 2**
- ps aux --sort=-%cpu | head -10

**Step 3**
- pidof process_name

**Step 4**
- ps -p 1023 -o pid,%cpu,%mem,cmd

# Scenario 3: Finding Service Logs

**A developer asks: "Where are the logs for the 'docker' service?"
The service is managed by systemd.
What commands would you use?**

**Hint:**

- systemd services → logs are in journald
- Command pattern: journalctl -u <service-name>
- Use -n flag to limit number of lines
- Use -f flag to follow logs in real-time (like tail -f)

Commands to explore:

- systemctl status ssh
- journalctl -u ssh -n 50
- journalctl -u ssh -f

# Scenario 4: File Permissions Issue

**A script at /home/user/backup.sh is not executing.
When you run it: ./backup.sh
You get: "Permission denied"

What commands would you use to fix this?**

**Hint:**

- First: Check what permissions the file has
- Understand: Files need 'x' (execute) permission to run
- Fix: Add execute permission with chmod

**Step-by-step solution structure:**

**Step 1: Check current permissions**
- Command: ls -l /home/user/backup.sh
- Look for: -rw-r--r-- (notice no 'x' = not executable)

**Step 2: Add execute permission**
- Command: chmod +x /home/user/backup.sh

**Step 3: Verify it worked**
- Command: ls -l /home/user/backup.sh
- Look for: -rwxr-xr-x (notice 'x' = executable)

**Step 4: Try running it**
- Command: ./backup.sh