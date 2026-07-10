---
title: "Week 2 Worklog"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---
### Week 2 Objectives:

* Learn and apply AWS Identity and Access Management (IAM) concepts.
* Understand the principle of least privilege and configure security groups & access rights.
* Practice creating users, groups, custom policies, and roles.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | **IAM Architecture Study:**<br>- Study AWS Identity and Access Management (IAM) key concepts: Users, Groups, Roles, Policies, and multi-factor authentication (MFA).<br>- Learn about policy types: AWS Managed Policies, Customer Managed Policies, and Inline Policies. | 27/04/2026 | 27/04/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Access Delegation Setup:**<br>- Create IAM Administrator User to avoid using the Root Account for daily operations.<br>- Create developer IAM Users and assign them to a newly created 'Developers' group; configure password complexity rules (12+ characters, special symbols) and force password changes on initial sign-in. | 28/04/2026 | 28/04/2026 | [AWS IAM User - Step-by-Step Tutorial (YouTube)](https://www.youtube.com/watch?v=bO25vbkoJlA) |
| 4 | **JSON Custom Policy Engineering:**<br>- Write a custom IAM policy using JSON format to allow Read/Write access strictly to a specific S3 bucket while denying visibility to other buckets.<br>- Use AWS Policy Simulator to verify that user permissions operate correctly under the custom policy conditions. | 29/04/2026 | 29/04/2026 | [AWS IAM Policies Reference](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies.html) |
| 5 | **Resource Delegation with IAM Roles:**<br>- Study IAM Roles and how they differ from Users; understand temporary credentials provided by AWS STS.<br>- Create an IAM Role for EC2 with read-only access to S3, attach it to a running instance, and log in to test accessing S3 files without saving access keys. | 30/04/2026 | 01/05/2026 | [IAM Roles for Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-amazon-ec2.html) |
| 6 | **Access Auditing and reporting:**<br>- Generate an IAM Credential Report to analyze account security posture, checking for unused keys or weak security.<br>- Define programmatic access configurations and disable inactive access keys. | 01/05/2026 | 01/05/2026 | [AWS IAM Best Practices Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) |

### Week 2 Achievements:

* **Comprehensive Access Governance Mastery:** Mastered AWS IAM access management framework, user delegation models, and JSON-based policy definitions.
* **Isolated Root Account Credentials:** Enforced security guidelines by delegating administrator functions to dedicated IAM Admin users, keeping root credentials locked.
* **Custom JSON Policy Design:** Successfully configured fine-grained S3 resource restrictions, preventing developers from accessing sensitive cross-department storage.
* **Keyless Resource Authentication:** Configured IAM Roles for compute instances, removing the hazard of hardcoding AWS Access Keys in codebase configurations.
* **System Credential Auditing:** Conducted first programmatic security audit utilizing credential reports and established a rotating password policy.