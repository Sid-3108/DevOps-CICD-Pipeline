 Ansible — Configure Jenkins & Docker Servers

This folder contains the **Ansible playbook** that installs:
- **Jenkins** on the `jenkins-server`
- **Docker** (with remote API on port 4243) on the `docker-server`

Both servers are created by Terraform.

---

 📂 Files
- `DevOpsSetup.yml` → playbook for Jenkins & Docker setup  
- `hosts.example` → inventory template (edit with your server IPs)

---

 ⚙️ Prerequisites (on anchor EC2)
- Python & pip:
`bash
sudo apt-get install -y python3-pip
sudo pip3 install ansible boto boto3

CREATED ANSIBLE INVENTORY FILE

sudo mkdir -p /etc/ansible
sudo cp ansible/hosts.example /etc/ansible/hosts
sudo nano /etc/ansible/hosts

USAGE ANSIBLE COMMANDS FOR EXECUTION
ansible all -m ping
ansible-playbook ansible/DevOpsSetup.yml

