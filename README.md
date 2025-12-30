# Cloud Computing Lab 12 - Terraform Infrastructure

**Submitted By:** Areej Fatima  
**Roll Number:** BSE-2023-010  
**Semester:** VA

## 📋 Overview

This repository contains a comprehensive Terraform-based infrastructure deployment lab that demonstrates cloud infrastructure provisioning, configuration management, and deployment automation. The project progressively builds from basic VM deployment to advanced concepts like load balancing, reverse proxying, high availability, and caching.

## 🎯 Learning Objectives

- Master Infrastructure as Code (IaC) using Terraform
- Deploy and configure cloud resources programmatically
- Implement modular Terraform architecture
- Configure web servers (Nginx & Apache)
- Set up reverse proxy and load balancing
- Implement HTTPS with SSL/TLS certificates
- Configure caching mechanisms
- Achieve high availability infrastructure

## 📁 Project Structure

```
CC_areej_010_Lab12/
├── modules/
│   ├── subnet/
│   │   ├── variables.tf
│   │   ├── main.tf
│   │   └── outputs.tf
│   └── webserver/
│       ├── variables.tf
│       ├── main.tf
│       └── outputs.tf
├── main.tf
├── variables.tf
├── terraform.tfvars
├── locals.tf
├── outputs.tf
├── entry-script.sh
└── README.md
```

## 🚀 Tasks Completed

### Task 0: Environment Setup
- Created GitHub Codespace
- Established SSH connection
- Configured development environment

### Task 1: Basic Infrastructure Deployment
- Initialized Terraform project structure
- Created configuration files (main.tf, variables.tf, outputs.tf)
- Generated SSH keys for secure access
- Deployed first VM instance with Nginx web server
- Verified deployment through browser access

**Key Files:**
- `variables.tf` - Input variable definitions
- `terraform.tfvars` - Variable values
- `locals.tf` - Local value computations
- `main.tf` - Main infrastructure configuration
- `outputs.tf` - Output value definitions
- `entry-script.sh` - VM initialization script

**Commands Used:**
```bash
terraform init
terraform apply
terraform destroy
```

### Task 2: Infrastructure Iteration
- Modified infrastructure configuration
- Redeployed with updated parameters
- Validated changes through testing

### Task 3: Configuration Management
- Updated infrastructure configurations
- Tested modifications
- Restored original main.tf configuration
- Performed cleanup operations

### Task 4: Subnet Module Development
- Created reusable subnet module
- Implemented module structure with variables, main logic, and outputs
- Integrated subnet module into main configuration
- Deployed infrastructure using modular approach

**Module Structure:**
```
modules/subnet/
├── variables.tf    # Module input parameters
├── main.tf         # Subnet resource definitions
└── outputs.tf      # Module outputs
```

### Task 5: Webserver Module Development
- Developed comprehensive webserver module
- Abstracted VM and web server configuration
- Integrated webserver module with existing infrastructure
- Validated modular deployment

**Module Structure:**
```
modules/webserver/
├── variables.tf    # Webserver configuration parameters
├── main.tf         # VM and webserver resources
└── outputs.tf      # IP addresses and connection info
```

### Task 6: HTTPS Configuration
- Implemented SSL/TLS certificates
- Configured HTTPS on Nginx
- Set up HTTP to HTTPS redirection
- Verified secure connections

**Security Features:**
- SSL/TLS encryption
- Automatic HTTP → HTTPS redirect
- Secure certificate management

### Task 7: Reverse Proxy Implementation
- Deployed Apache backend server (web1)
- Configured Nginx as reverse proxy
- Set up SSL termination at proxy level
- Implemented secure backend communication

**Architecture:**
```
Client → [HTTPS] → Nginx (Reverse Proxy) → [HTTP] → Apache (Backend)
```

### Task 8: Load Balancing
- Deployed second backend server (web2)
- Configured Nginx load balancer
- Implemented round-robin distribution
- Tested traffic distribution across backends

**Load Balancing Configuration:**
```
Client → [HTTPS] → Nginx (Load Balancer) → [HTTP] → Apache (web1)
                                          → [HTTP] → Apache (web2)
```

### Task 9: High Availability Testing
- Simulated backend server failures
- Validated automatic failover
- Tested service continuity with single backend active
- Demonstrated HA architecture resilience

**Test Scenarios:**
- ✅ Service available with web1 only
- ✅ Service available with web2 only
- ✅ Automatic failover between backends

### Task 10: Caching Implementation
- Configured Nginx caching layer
- Validated cache performance (MISS → HIT)
- Verified cache directory structure
- Measured performance improvements

**Caching Benefits:**
- Reduced backend load
- Improved response times
- Enhanced scalability

### Cleanup
- Destroyed all infrastructure resources
- Verified state file cleanup
- Confirmed resource deallocation

## 🛠️ Technologies Used

- **Terraform** - Infrastructure as Code tool
- **Nginx** - Web server, reverse proxy, and load balancer
- **Apache** - Backend web server
- **SSL/TLS** - Encryption and secure communications
- **SSH** - Secure remote access
- **GitHub Codespaces** - Cloud development environment

## 📚 Key Concepts Demonstrated

1. **Infrastructure as Code (IaC)**
   - Declarative infrastructure definitions
   - Version-controlled infrastructure
   - Reproducible deployments

2. **Modular Architecture**
   - Reusable Terraform modules
   - Separation of concerns
   - Maintainable code structure

3. **Web Server Configuration**
   - Nginx configuration
   - Apache setup
   - SSL/TLS implementation

4. **Advanced Networking**
   - Reverse proxy setup
   - Load balancing strategies
   - High availability patterns

5. **Performance Optimization**
   - Caching strategies
   - Traffic distribution
   - Resource optimization

## 🔧 Prerequisites

- Terraform installed (v1.0+)
- Cloud provider account (GCP/AWS/Azure)
- SSH key pair
- Basic understanding of networking
- GitHub account for Codespaces

## 📖 How to Use This Repository

### 1. Clone the Repository
```bash
git clone https://github.com/areej-10/CC_areej_010_Lab12.git
cd CC_areej_010_Lab12
```

### 2. Configure Variables
Edit `terraform.tfvars` with your specific values:
```hcl
project_id = "your-project-id"
region     = "your-region"
# Add other required variables
```

### 3. Initialize Terraform
```bash
terraform init
```

### 4. Review Plan
```bash
terraform plan
```

### 5. Apply Configuration
```bash
terraform apply
```

### 6. Access Outputs
```bash
terraform output
```

### 7. Destroy Resources (when done)
```bash
terraform destroy
```

## 📸 Screenshots Reference

All tasks include comprehensive screenshots demonstrating:
- Configuration files
- Terminal commands and outputs
- Browser verification
- Module structure
- Testing results

## 🎓 Learning Outcomes

By completing this lab, I have gained hands-on experience with:

- ✅ Writing production-grade Terraform code
- ✅ Designing modular infrastructure
- ✅ Configuring enterprise web servers
- ✅ Implementing security best practices
- ✅ Building high-availability systems
- ✅ Performance optimization techniques
- ✅ Infrastructure testing and validation

## 🔐 Security Considerations

- SSH keys used for secure access
- HTTPS enforced for all web traffic
- SSL/TLS certificates properly configured
- Backend servers isolated from direct internet access
- Sensitive variables managed through terraform.tfvars (not committed)

## 🤝 Contributing

This is an academic project. For questions or suggestions, please open an issue.

## 📝 License

This project is part of academic coursework.

## 👤 Author

**Areej Fatima**  
Roll Number: BSE-2023-010  
Semester: VA

---

**Note:** This repository demonstrates practical cloud computing and DevOps concepts learned during the Cloud Computing course. All infrastructure was created, tested, and properly destroyed as part of the lab exercises.
