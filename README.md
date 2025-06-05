# 🖥 System Monitoring with Netdata on AWS

### 🎯 Goal

Set up *Netdata* on an *AWS EC2 instance* using *Docker* to watch system resources like *CPU, **memory, **disk activity, and **Docker containers* in real-time.

---

### 🔧 Tools Used

* *Netdata* – To monitor system performance
* *Docker* – To run Netdata quickly without installing it manually
* *AWS EC2 (Amazon Linux 2)* – Virtual server used to host Netdata
* *Browser* – To view the monitoring dashboard

---

### 📘 Step-by-Step Process

1. Logged into my *EC2 instance* using SSH.

2. Installed *Docker* on the server.

3. Used this command to start Netdata in a Docker container:

   bash
   docker run -d --name=netdata \
     -p 19999:19999 \
     --cap-add=SYS_PTRACE \
     --security-opt apparmor=unconfined \
     netdata/netdata
   

4. Opened *port 19999* in the EC2 security group so I could view the dashboard from a browser.

5. Accessed Netdata from:

   
   http://<your-ec2-public-ip>:19999
   

6. Started watching live stats like:

   * CPU load
   * RAM usage
   * Disk read/write speeds
   * Running Docker container info

7. Took a screenshot of the dashboard and saved it inside the screenshot/ folder.

---

### 🖼 Dashboard Preview

This is what the Netdata dashboard looks like on the EC2 server:

<img src="./netdata-system-monitoring-docker/monitoring.png" alt="Netdata Dashboard" width="400" height="400" />

---

### ✅ Final Result

* Netdata was successfully installed and running on an EC2 instance.
* Learned how to use Docker to quickly set up a monitoring tool.
* Able to track system performance and container activity in real-time.

---

### 📁 Project Structure

```
task-7-netdata-monitoring/
│
├── screenshot/
│   └── netdata-dashboard.png
│
└── README.md
