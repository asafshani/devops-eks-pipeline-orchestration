# DevOps EKS Pipeline Orchestration

This repository demonstrates Jenkins automation to provision and configure AWS EKS infrastructure using Terraform and Ansible.

## Overview

The pipeline has two stages:
1. **Terraform Jenkinsfile** provisions AWS networking and an EKS cluster.
2. **Ansible Jenkinsfile** configures the EKS worker nodes post-provisioning.

Each Jenkinsfile includes failure handling to improve reliability during CI/CD execution.

## Repository Contents

- `Jenkinsfile.terraform`: Infrastructure provisioning logic
- `Jenkinsfile.ansible`: Node configuration logic
- `.gitignore`: Prevents sensitive and temporary files from being committed

## Related Repositories

- [terraform-aws-networking](https://github.com/asafshani/terraform-aws-networking)
- [ansible-eks-configuration](https://github.com/asafshani/ansible-eks-configuration)

## Setup Instructions

1. Create Jenkins jobs for each pipeline.
2. Upload respective Jenkinsfiles to those jobs.
3. Ensure credentials, AWS access, and SSH keys are properly configured.
4. Monitor Jenkins logs for success and failure messages.

## Job Behavior

- The Terraform job clones your repo, applies infrastructure, and triggers the Ansible job if successful.
- If either job fails, Jenkins logs the failure and halts the pipeline until reviewed.

## License

This project is intended for professional demonstration purposes and can be adapted for personal use.
