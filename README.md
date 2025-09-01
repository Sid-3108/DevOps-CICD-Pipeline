End-to-End CICD Lab 🚀

This project demonstrates a **complete CICD pipeline** using:

- **AWS EC2** (infrastructure)  
- **Terraform** (server provisioning)  
- **Ansible** (configuration management)  
- **Jenkins** (CI/CD pipeline)  
- **Tomcat** (application deployment)  
- **Git & GitHub Webhooks** (source control & automation)

It covers the full flow from provisioning servers → configuring Jenkins/Docker → building a Java app → deploying it on Tomcat → triggering builds via GitHub.

---

📌 Important Note
- The **Java application code** is present in the **`main` branch**.  
- This **`images` branch** contains only **output-screenshots** (step-by-step guides).  

---

# 📚 Guides

- [Terraform Setup](terraform/README.md)  
  Provision EC2 servers for Jenkins & Docker.  

- [Ansible Setup](ansible/README.md)  
  Install and configure Jenkins + Docker on those servers.  

- [Jenkins Configuration](jenkins/README.md)  
  Unlock Jenkins, configure Maven, build the Java app, and optionally deploy to Tomcat.   

- [GitHub Webhook Integration](webhook/README.md)  
  Trigger Jenkins builds automatically when code is pushed to GitHub.  

---

# 🔗 Branching Structure

- **`main` branch** → contains the runnable Java code + Terraform & Ansible config files.  
- **`docs` branch** → contains documentation and step-by-step instructions (this branch).  

---


---
Summary:
- an intro (end-to-end CICD with AWS/Terraform/Ansible/Jenkins/Tomcat)  
- a note that Java code is on `main`  
- navigation to each sub-guide  

Do you also want me to draft a **shorter root README.md for the `main` branch** (just saying “code is here, docs are in docs branch”)?

