# Day 7: Networking Basics & Remote Access (`ssh`, `ping`, `curl`, `netstat`)

## 1. Overview of Today's Concepts

As a DevOps engineer and backend developer, you must understand how Linux interacts with networks. Today covers checking connectivity, testing HTTP APIs, managing secure remote connections, and inspecting active port listeners.

---

## 2. Core Networking & Diagnostic Commands

### A. Secure Shell Remote Access (`ssh`)

- **Command:** `ssh username@remote_host`
- **What it does:** Establishes an encrypted secure shell connection to a remote server or cloud instance.
- **Key Practice:** Always secure your private keys (`~/.ssh/id_rsa`) with strict permissions (`chmod 600`) to prevent unauthorized access.

### B. Testing Network Reachability (`ping`)

- **Command:** `ping google.com`
- **What it does:** Sends ICMP echo request packets to a target host to test network connectivity, packet loss, and latency round-trip time.

### C. Transferring Data & Testing APIs (`curl`)

- **Command:** `curl -X GET http://localhost:8000/docs`
- **What it does:** A command-line tool for transferring data using various network protocols. Essential for testing FastAPI endpoints, checking HTTP status codes, and inspecting response payloads directly from the terminal.

### D. Inspecting Open Ports & Listeners (`netstat` / `ss`)

- **Command:** `ss -tuln` (or `netstat -tuln`)
- **What it does:** Displays active listening ports and established connections.
  - `-t`: TCP connections
  - `-u`: UDP connections
  - `-l`: Listening sockets only
  - `-n`: Numeric addresses (prevents resolving hostnames/services)
- **DevOps Use Case:** Verifying whether your PostgreSQL database (port `5432`) or FastAPI application (port `8000`) is actively listening for incoming traffic.

---

## 3. Key Takeaways for Full-Stack & DevOps Workflows

- **Port Troubleshooting:** If your frontend cannot communicate with your FastAPI backend, use `ss -tuln` to verify the backend server is running and listening on the expected port.
- **API Validation:** Always use `curl` to test backend health check routes (`/health` or `/docs`) before integrating them into your Next.js frontend or production Nginx reverse proxy.
