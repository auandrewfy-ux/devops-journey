# Day 6: Process Management, System Monitoring & Service Control

## 1. Overview of Today's Concepts

As a System Administrator and DevOps engineer, understanding how processes run, consuming system resources, and managing background services is critical for keeping production applications healthy and responsive.

---

## 2. Core Process & Monitoring Commands

### A. Viewing Running Processes (`ps`)

- **Command:** `ps aux`
- **What it does:** Displays a snapshot of all running processes across the system.
  - `a`: Shows processes for all users.
  - `u`: Displays user/owner-oriented format.
  - `x`: Includes processes not attached to a terminal (like background daemons).

### B. Real-Time Resource Monitoring (`top` / `htop`)

- **Command:** `htop` (or `top`)
- **What it does:** Provides a dynamic, real-time view of system performance, CPU usage, memory utilization, swap space, and active process trees. `htop` offers an interactive, color-coded interface supporting mouse navigation.

### C. Terminating Misbehaving Processes (`kill` & `pkill`)

- **Command:** `kill -9 <PID>`
- **What it does:** Forces termination of a process using its Process ID (PID). `-9` sends the `SIGKILL` signal, instantly stopping the process.
- **Alternative:** `pkill -f python3` terminates processes matching a specific name pattern.

---

## 3. Managing Services with `systemctl` (Systemd)

Linux systems use `systemd` to manage background services (daemons). The `systemctl` utility controls these services:

- **Check Service Status:**
  ```bash
  sudo systemctl status postgresql
  ```
