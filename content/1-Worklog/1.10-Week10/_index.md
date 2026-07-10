---
title: "Week 10 Worklog"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---
### Week 10 Objectives:

* Understand Serverless architecture computing paradigms and event-driven executions.
* Deploy an AWS Lambda function with custom code.
* Create and expose HTTP endpoints using Amazon API Gateway.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | **Serverless Concepts Study:**<br>- Study serverless compute principles: event-driven architecture, invocation models, Lambda cold starts, runtime environments, and resource allocation. | 22/06/2026 | 22/06/2026 | [FCAJ Cloud Journey](https://cloudjourney.awsstudygroup.com/) |
| 3 | **Lambda Logic Development:**<br>- Develop a Python Lambda function; write logic to parse input event parameters, extract JSON keys, process variables, and return formatted HTTP response payloads. | 23/06/2026 | 23/06/2026 | [AWS Lambda & API Gateway Tutorial (YouTube)](https://www.youtube.com/watch?v=eOBq__h4OJ4) |
| 4 | **API Gateway Routing Integration:**<br>- Deploy an Amazon API Gateway (HTTP API configuration); map routes (`GET` and `POST` methods) to trigger the backend Lambda function; configure CORS rules to permit external front-end access. | 24/06/2026 | 24/06/2026 | [Amazon API Gateway Developer Guide](https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html) |
| 5 | **API Integration Testing:**<br>- Execute integration tests locally using curl and Postman; send JSON payloads to the public API endpoint and review response contents; inspect CloudWatch logs to audit Lambda execution profiles. | 25/06/2026 | 25/06/2026 | [Testing REST APIs in API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-test-method.html) |
| 6 | **Serverless Data Store Integration:**<br>- Deploy a serverless Amazon DynamoDB table; grant write permissions to the Lambda IAM execution role, and update Lambda logic to save user requests directly into DynamoDB. | 26/06/2026 | 26/06/2026 | [AWS Serverless Applications Developer Guide](https://docs.aws.amazon.com/serverless/latest/developerguide/what-is-serverless.html) |

### Week 10 Achievements:

* **Serverless Backend Implementations:** Provisioned event-driven cloud logic without managing underlying OS frameworks.
* **Public REST API Gateways:** Built production-ready public endpoints with path routing controls using API Gateway.
* **Serverless Execution Audits:** Utilized CloudWatch Logs integration to troubleshoot runtime issues.
* **Key-Value Datastore Operations:** Integrated DynamoDB storage libraries, enabling secure write operations without database server overhead.