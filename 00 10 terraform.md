# 🌍 Terraform – Infrastructure as Code (IaC)

## 📌 What is Terraform?

**Terraform** is an **Infrastructure as Code (IaC)** tool by HashiCorp used to **define, provision, and manage cloud infrastructure** in a **declarative and automated** way.

With Terraform, you write code to create resources such as:

* EC2, S3, IAM (AWS)
* Virtual Machines, Storage, Networking (Azure)
* Compute Engine, GCS, IAM (GCP)

---

## 🧱 Infrastructure as Code (IaC)

**IaC** means managing infrastructure using **code instead of manual steps**.

### 🔑 Key Benefits

* Automated deployments
* Version-controlled infrastructure
* Consistent & repeatable environments
* Faster provisioning
* Reduced human errors

---

## ☁️ Multi‑Cloud Support

Terraform supports **multi‑cloud and hybrid environments**:

* **AWS**
* **Azure**
* **Google Cloud Platform (GCP)**

Single tool → multiple cloud providers.

---

## 🧠 Core Terraform Concepts

| Concept   | Description                         |
| --------- | ----------------------------------- |
| HCL       | HashiCorp Configuration Language    |
| Providers | Cloud/API plugins (AWS, Azure, GCP) |
| State     | Tracks current infrastructure       |
| Resources | Actual cloud services               |
| Modules   | Reusable infrastructure blocks      |

---

## 📁 Basic Terraform File Structure

```text
terraform-project/
│── main.tf
│── variables.tf
│── outputs.tf
│── terraform.tfstate
```

* **main.tf** → primary infrastructure definition
* **terraform.tfstate** → current state tracking

---

## 📝 Terraform Configuration Language (HCL)

Terraform uses **HCL**, a declarative language:

```hcl
resource "aws_s3_bucket" "example" {
  bucket = "my-bucket-name"
}
```

---

## 🖥️ Terraform Installation

---

### 🪟 Windows (PowerShell – Run as Administrator)

#### Install Chocolatey

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; \
[System.Net.ServicePointManager]::SecurityProtocol = \
[System.Net.ServicePointManager]::SecurityProtocol -bor 3072; \
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

#### Install Terraform

```powershell
choco --version
choco install terraform
terraform --version
```

---

### 🟡 Amazon Linux (EC2)

```bash
sudo yum install -y yum-utils shadow-utils
sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo
sudo yum install terraform
terraform --version
```

---

### 🐧 Ubuntu / WSL

```bash
wget -O - https://apt.releases.hashicorp.com/gpg | \
  sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(grep -oP '(?<=UBUNTU_CODENAME=).*' /etc/os-release || lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list

sudo apt update && sudo apt install terraform
```

#### OR (Snap)

```bash
sudo apt install snapd
sudo snap install terraform --classic
```

---

### 🍎 macOS

```bash
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
terraform --version
```

---

## 🔧 Cloud CLI Prerequisites

### AWS CLI

```bash
aws --version
```

### Azure CLI

```bash
az --version
```

---

## 🔐 AWS IAM Setup (Required for Terraform)

### Steps

1. Create **IAM User** → `atul`
2. Create **IAM Group** → `admin`
3. Attach policy → `AdministratorAccess`
4. Add user `atul` to group `admin`
5. Generate **Access Key & Secret Key**

---

## ⚙️ Configure AWS CLI

```bash
aws configure
```

Enter:

* Access Key ID
* Secret Access Key
* Region: `us-east-1`
* Output format: `json`

---

## 🪣 Test AWS Access (S3)

```bash
aws s3 mb s3://hfgkhj7797j475586
aws s3 ls
aws s3 rb s3://hfgkhj7797j475586
```

---

## 🧑‍💻 VS Code Setup

### Recommended Extensions

* HashiCorp Terraform
* Azure Terraform

---

## 📄 Terraform Provider Configuration (main.tf)

```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "6.31.0"
    }
  }
}

provider "aws" {
  region = "us-east-1"
}
```

---

## 🚀 Initialize Terraform

```bash
terraform init
```

### What it does:

* Downloads provider plugins
* Initializes backend
* Prepares working directory

---

## ✅ Key Commands to Remember

```bash
terraform init
terraform plan
terraform apply
terraform destroy
```

---

## 🎯 Summary

* Terraform enables **automated, scalable, multi‑cloud deployments**
* Uses **HCL** and **state tracking**
* Works across **AWS, Azure, GCP**
* Ideal for **DevOps, Cloud Engineers, and Architects**

---

**Built with ❤️ for Cloud & DevOps learning** 🚀
