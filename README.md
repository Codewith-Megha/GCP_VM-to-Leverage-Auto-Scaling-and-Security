# GCP_VM-to-Leverage-Auto-Scaling-and-Security
# GCP VM Auto Scaling and Security Implementation  
### Megha Pandey

---

## 📌 Project Overview

This project demonstrates the deployment of a Virtual Machine on Google Cloud Platform (GCP) with:

- Managed Instance Group (MIG)
- Auto Scaling based on CPU utilization
- Firewall security configuration
- IAM role-based access control

The implementation ensures scalability, availability, and secure access management in a cloud environment.

---

## 🎯 Objective

To:

- Create a VM on Google Cloud Platform.
- Implement auto-scaling policies based on workload (CPU utilization).
- Configure security using firewall rules and IAM roles.

---

## 🏗 Architecture Overview
            Internet Users
                    │
                    ▼
            Firewall Rules
       (Port 80 - HTTP, Port 22 - SSH)
                    │
                    ▼
        Managed Instance Group (MIG)
            Auto Scaling Enabled
                    │
          ┌─────────┴─────────┐
          ▼                   ▼
    VM Instance 1        VM Instance 2
    (E2-micro)           (E2-micro)
          │
          ▼
    Compute Engine
          │
          ▼
     IAM Role Control


---

## 🖥 Infrastructure Details

| Component | Configuration |
|-----------|---------------|
| Cloud Provider | Google Cloud Platform |
| Service Used | Compute Engine |
| Region | asia-south1 (Mumbai) |
| Zone | asia-south1-c |
| Machine Type | E2-micro |
| OS | Ubuntu |
| Scaling Metric | CPU Utilization |
| Min Instances | 1 |
| Max Instances | 2 |
| Target CPU | 60% |

---

## 🚀 Implementation Steps

### 1️⃣ Instance Template Creation
- Created an instance template defining:
  - Machine type (E2-micro)
  - Ubuntu OS
  - HTTP enabled
  - Default service account attached

---

### 2️⃣ Managed Instance Group
- Created a stateless managed instance group.
- Initial instance count: 1
- Linked to instance template.

---

### 3️⃣ Auto Scaling Configuration
- Enabled autoscaling.
- CPU utilization threshold set to 60%.
- Minimum instances: 1
- Maximum instances: 2

Scaling behavior:
- CPU > 60% → Add new instance
- CPU < 60% → Remove extra instance

---

### 4️⃣ Load Testing
Used stress tool to simulate CPU load:

```bash
sudo apt install stress
stress --cpu 2 --timeout 300

This triggered automatic scaling from 1 → 2 instances.

🔐 Security Configuration
🔹 Firewall Rules

Port 22 (SSH) – Allowed

Port 80 (HTTP) – Allowed

Firewall rules ensure controlled inbound traffic.

🔹 IAM Roles

Compute Engine default service account assigned role-based permissions.

Project access managed using IAM.

Ensures secure and controlled resource access.

📊 Results

VM deployed successfully.

Managed Instance Group created.

Auto-scaling triggered successfully under CPU load.

Security configured using firewall and IAM policies.

📁 Repository Contents
/Assignment_Report.pdf
/screenshots/
/architecture-diagram.png
README.md
🎥 Video Demonstration

Video Link:
[PASTE YOUR GOOGLE DRIVE OR YOUTUBE LINK HERE]

📌 Conclusion

This project demonstrates practical implementation of:

Cloud-based VM deployment

Horizontal auto scaling

Secure firewall configuration

Role-based IAM access control

The solution ensures scalability, availability, and security in a cloud environment.

Author

Megha Pandey


---

# ✅ What To Do Now

1. Create a file named `README.md`
2. Paste this content
3. Replace:

[PASTE YOUR GOOGLE DRIVE OR YOUTUBE LINK HERE]

4. Save
5. Run:

```bash
git add .
git commit -m "Added README"
git push