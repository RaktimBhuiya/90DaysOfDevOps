## Linux Troubleshooting Runbook
##Target Service / Process

**Service**: docker
**Purpose**: Container runtime service used to run and manage containers.

# 1. Environment Basics
**Command 1**

- uname -a

**Observation:**

- Verified Linux kernel version, architecture, and hostname.
- System appears to be running a stable Linux kernel.

**Command 2**

- cat /etc/os-release

Observation:

- Confirmed Linux distribution and OS version.
- Useful for checking package/service compatibility.

# 2. Filesystem Sanity

**Command 3**

- mkdir /tmp/runbook-demo

**Observation:**

- Temporary troubleshooting workspace created successfully.

**Command 4**

- cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo

**Observation:**

- File copy operation succeeded.
- Filesystem is writable and permissions look normal.

# 3. Snapshot: CPU & Memory

**Command 5**

- systemctl status docker

**Observation:**

- Docker service is active and running.
- Main process (dockerd) is healthy with no immediate failures.

**Command 6**

- ps -o pid,pcpu,pmem,comm -p $(pidof dockerd)

**Observation:**

- Docker daemon CPU and memory usage are low.
- No unusual resource spikes observed.

**Command 7**

- free -h

**Observation:**

- Sufficient free memory available.
- No swap pressure detected.

# 4. Snapshot: Disk & IO

**Command 8**

- df -h

**Observation:**

- Root filesystem has adequate free disk space.

**Command 9**

- du -sh /var/log

**Observation:**

- Log directory size is within expected range.
- No excessive log growth detected.

**Command 10**

- vmstat 1 5

**Observation:**

- CPU idle time remains healthy.
- No abnormal IO wait or memory bottlenecks.

# 5. Snapshot: Network

**Command 11**

- ss -tulpn | grep docker

**Observation:**

- Verified Docker-related listening ports.
- No unexpected open ports found.
**Command 12**
curl -I http://localhost

**Observation:**

- Local HTTP endpoint responded successfully.

# 6. Logs Reviewed

**Command 13**

- journalctl -u docker -n 50

**Observation:**

- Reviewed recent Docker service logs.
- No critical errors or crash loops identified.

**Command 14**

- tail -n 50 /var/log/syslog

**Observation:**

- Checked recent system logs for warnings/errors.
- No major system-level issues observed.

# If This Worsens (Next Steps)

1. Restart Docker service and monitor behavior:

   - systemctl restart docker

2. Increase logging verbosity and capture detailed diagnostics:

   - journalctl -u docker -f

3. Trace Docker daemon system calls for deeper investigation:

   - strace -p $(pidof dockerd)