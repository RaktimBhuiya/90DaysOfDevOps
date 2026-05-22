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

** Find the largest log file in /var/log**
- du -sh /var/log/* 2>/dev/null | sort -h | tail -5

** Look at a config file in /etc**
- cat /etc/hostname

** Check your home directory**
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

**Use a command that shows live CPU usage
Look for processes sorted by CPU percentage
Note the PID (Process ID) of the top process**