# AWS_CLOUD_SECURITY_SIMULATION
# Secure Cloud Infrastructure with Automated Detection & Response

## Why This Project Exists
Most cloud outages and breaches don’t happen because of “hackers”.
They happen because of **misconfigurations, over-permissioned access, and unsafe automation**.

This project simulates exactly those real-world mistakes — and shows how to **detect, stop, and recover from them automatically** using modern Cloud Security and DevSecOps practices.

Everything here is built with one principle in mind:

> Humans make decisions.  
> Automation executes them safely.  
> Guardrails prevent disasters.



## What This Project Demonstrates
This is not a tutorial project.  
It is a **security-focused cloud system** designed to answer questions like:

- What happens if someone makes an S3 bucket public?
- What if a security group is opened to the internet?
- What if Terraform applies a dangerous change in production?
- How do we detect this?
- How do we stop it automatically?
- How do we prove it happened?



## High-Level Architecture
- Secure AWS infrastructure provisioned using **Terraform**
- Strong **IAM guardrails** (no long-lived credentials, least privilege everywhere)
- **CI/CD-controlled execution** (humans approve, pipelines apply)
- Automated **detection and remediation** of misconfigurations
- Near real-time **security visibility dashboard**

This project is built entirely within **AWS Free Tier**, focusing on **design and correctness**, not scale.



## Infrastructure & Guardrails
- Custom VPC with public and private subnets
- Private compute resources (no direct internet exposure)
- Terraform remote state stored securely with versioning
- Permission boundaries and restricted execution roles
- No direct human access to production infrastructure

If a change cannot be reviewed, it cannot be applied.



## CI/CD (DevSecOps Core)
- Infrastructure changes flow through GitHub Actions
- Mandatory `terraform plan` review before execution
- No secrets stored in repositories
- CI/CD authenticates using **OIDC → STS**
- Production execution is fully automated

This removes “hero deployments” and accidental changes.



## Detection & Automated Response
The system safely simulates common cloud security incidents:

- Public S3 bucket exposure
- Security groups open to `0.0.0.0/0`
- Overly permissive IAM policies

**Detection Flow:**
1. Misconfiguration occurs
2. AWS Config / CloudTrail detects the event
3. EventBridge triggers remediation
4. Lambda automatically reverts the change
5. Event is logged for visibility

No manual intervention required.



## Security Visibility Dashboard
A lightweight Python-based dashboard provides:
- Timeline of detected security events
- Type of violation
- Automated action taken
- Current status (remediated / blocked)

This gives immediate visibility without heavy SIEM tooling.



## Security Principles Applied
- Identity-first security (IAM over network trust)
- Least privilege by default
- Separation of duties (human vs machine)
- Immutable infrastructure mindset
- Detect early, remediate automatically
- Reduce blast radius, always



## Technologies Used
- AWS (Free Tier)
- Terraform
- GitHub Actions
- IAM, VPC, S3
- AWS Config, CloudTrail, EventBridge
- AWS Lambda
- Python (dashboard & automation)



## Disclaimer
All incidents are **intentionally simulated** in a controlled environment.
No real attacks are performed.



## Author
Rakshit  
Cloud Security & DevSecOps Engineer
