---
title: "Week 9 Worklog"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---
### Week 9 Objectives:

* Learn declarative Infrastructure as Code (IaC) advantages and architectural management.
* Master Terraform directory setup, variables, providers, and state file concepts.
* Provision AWS networks and compute nodes automatically via Terraform CLI execution.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | **Infrastructure as Code Study:**<br>- Study Infrastructure as Code (IaC) benefits: repeatability, auditability, config consistency, declarative vs. imperative modes.<br>- Learn HashiCorp Configuration Language (HCL) syntax and resource dependency configurations. | 15/06/2026 | 15/06/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Terraform CLI & Provider Initializing:**<br>- Install Terraform CLI on workstation; configure AWS profile local credential authentication.<br>- Create a project directory, build baseline configuration files, and execute `terraform init` to download the AWS provider plugin. | 16/06/2026 | 16/06/2026 | [Terraform Course - IaC Tutorial (YouTube)](https://www.youtube.com/watch?v=7xngnjfIlK4) |
| 4 | **Virtual Network Declarative Coding:**<br>- Write declarative configuration files (`providers.tf`, `variables.tf`, `vpc.tf`) mapping VPC resources, public/private subnets, internet gateways, and routing records using Terraform resources. | 17/06/2026 | 18/06/2026 | [Terraform AWS Provider Reference](https://registry.terraform.io/providers/hashicorp/aws/latest/docs) |
| 5 | **Compute Node Code Modeling:**<br>- Code `compute.tf` resources to declare EC2 instances, root storage partitions, security groups, and SSH key associations matching manual settings. | 18/06/2026 | 19/06/2026 | [Terraform EC2 Resource Examples](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance) |
| 6 | **Deployment Verification & Teardown Execution:**<br>- Run `terraform plan` to audit upcoming changes.<br>- Execute `terraform apply` to deploy the infrastructure stack, verify the running resource Console, and execute `terraform destroy` to check resource teardown. | 19/06/2026 | 19/06/2026 | [HashiCorp Terraform Tutorial](https://developer.hashicorp.com/terraform/tutorials/aws-get-started) |

### Week 9 Achievements:

* **Adopted Declarative IaC Models:** Transitioned from manual cloud console clicks to reusable, modular code blocks.
* **Modular Code Parameterization:** Mastered configuration design using input variables and output queries.
* **Rapid Cloud Architecture Spin-up:** Provisioned complex, isolated virtual networks and compute instances in seconds via command-line execution.
* **Controlled State Auditing:** Secured infrastructure change histories using Terraform state logging.