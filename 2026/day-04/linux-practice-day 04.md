# Day 04 – Linux Practice: Processes and Services

# Run and record output for at least 6 commands

- **cd** : Changed Directory
- **id**: shows information about a user along with its id
- **groups**: display user is part of which group
- **whoami**: who is logged in to system i.e. current user
- **who**: more information than whoami about the current logged in user to system
- **w**: more information than who about the current logged in user to syste

# Include 2 process commands

- **ps aux**: Detailed Process Information.
- **top**: Real-Time Process Monitoring.

# Include 2 service commands

- **systemctl start service_name**:	Start a service.
- **systemctl status service_name**: Check the status of a service.

# Include 2 log commands

- **journalctl**:	View system and service logs.
- **tail -f /var/log/syslog**:	Monitor log file in real time.

# Pick one service on your system (example: ssh, cron, docker) and inspect it

- **systemctl status docker**: Checks whether the Docker service is running or stopped. It Displays service status, PID, uptime, logs, and recent activity.

- **systemctl status ssh**: Checks the status of the SSH service used for remote login access.

- **systemctl status cron**: Checks the status of the Cron service used for scheduled tasks/jobs.