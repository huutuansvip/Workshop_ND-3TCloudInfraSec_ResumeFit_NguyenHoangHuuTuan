---
title: "Week 8 Worklog"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---
### Week 8 Objectives:

* Understand Continuous Integration and Continuous Deployment (CI/CD) pipelines.
* Design build and release automation workflows using GitHub Actions.
* Securely integrate AWS credentials with GitHub environments to automate static code publishing to S3.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | **CI/CD Paradigms Study:**<br>- Learn software delivery principles: continuous integration, continuous deployment, automation testing, build logs audit, and release management.<br>- Compare GitHub Actions pipelines with AWS CI/CD native tools (CodePipeline, CodeBuild, CodeDeploy). | 08/06/2026 | 08/06/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Git Version Control Setup:**<br>- Create a clean public/private GitHub repository for target site code files.<br>- Synchronize local workspace files, configure remotes, and manage branches (`main` and `develop`). | 09/06/2026 | 09/06/2026 | [Set Up CI/CD to Auto Deploy to AWS ECS (YouTube)](https://www.youtube.com/watch?v=gfCkScWWTvk) |
| 4 | **OIDC Trust Integration Setup:**<br>- Set up an OpenID Connect (OIDC) identity provider trust in IAM, referencing GitHub Actions as trusted source.<br>- Create a custom IAM Role with S3 deployment permissions trust-bound to the GitHub repository, eliminating static secrets. | 10/06/2026 | 11/06/2026 | [AWS OIDC with GitHub Actions Guide](https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services) |
| 5 | **YAML Workflow Automation Coding:**<br>- Write a GitHub Actions YAML script (`.github/workflows/deploy.yml`) defining trigger rules, run environments, OIDC authentication credentials, and S3 file synchronization steps. | 11/06/2026 | 12/06/2026 | [AWS S3 Actions Integration Reference](https://github.com/aws-actions/configure-aws-credentials) |
| 6 | **Pipeline Testing & Output Verification:**<br>- Commit modifications to local files and push changes to trigger the action pipeline.<br>- Monitor the GitHub Actions console logs to audit step executions and verify changes publish automatically to the S3 bucket website endpoint. | 12/06/2026 | 12/06/2026 | [GitHub Actions Documentation](https://docs.github.com/en/actions) |

### Week 8 Achievements:

* **Automated CI/CD Workflows:** Built automated software delivery workflows, replacing slow, error-prone manual console uploads.
* **Secured Cloud Access with OIDC:** Implemented secure, keyless AWS authentication from GitHub Actions runners using modern OIDC role trust definitions.
* **Rapid Website Publishing:** Configured automated build-and-sync flows that update S3 hosted assets instantly on every repository push.
* **DevOps Best Practices:** Acquired skills in pipeline debugging, execution log auditing, and version control workflows.