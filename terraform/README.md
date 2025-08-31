Terraform — Launch Jenkins & Docker Servers

This folder contains Terraform configs to create **two Ubuntu 20.04 EC2 instances**:
- `jenkins-server`
- `docker-server`

Both are `t2.micro` (free tier). Security Group should allow **22, 80, 8080, 9999, 4243**.

---

 📂 Files
- `main.tf` → defines AWS provider, key pair, and EC2 servers  
- `variables.tf` → defines region, SG id, AMI, instance type, etc.  
- `terraform.tfvars.example` → sample values (copy → `terraform.tfvars` and edit)  

---

 ⚙️ Prerequisites (on your anchor EC2)
`bash
sudo apt update
sudo apt install -y wget unzip git python3-pip
sudo pip3 install awscli boto boto3 ansible
aws configure   # enter Access Key, Secret, and region
ssh-keygen -t rsa -b 2048   # hit Enter for prompts

CREATED 2 EC 2 SERVERS BY USING TERRAFORM

resource "aws_instance" "servers" {
  for_each = toset(var.my_servers)
  ami                    = var.ami_id
  instance_type          = var.ins_type
  key_name               = aws_key_pair.mykeypair.key_name
  vpc_security_group_ids = [var.sg_id]

  tags = { Name = each.key }
}



USAGE COMMANDS TO START TERRAFORM EXECUTION

cd terraform
cp terraform.tfvars.example terraform.tfvars   # edit sg_id, etc.
terraform init
terraform validate
terraform plan
terraform apply -auto-approve
