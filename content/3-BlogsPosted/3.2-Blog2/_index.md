---
title: "Blog 2"
date: 2026-06-29
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---
# PROD-READY ARCHITECTURE: BUILDING AN AI GATEWAY TO AMAZON BEDROCK WITH AMAZON API GATEWAY

*Posted by: Nguyen Thai Dat*

Hello everyone. Recently, while building AWS infrastructure labs—from configuring networks, troubleshooting security with Secrets Manager in Cloud9, to drafting plans for integrating Machine Learning with Prometheus for monitoring—I encountered a challenging problem: How do we manage access rights and control costs when multiple teams start sharing Large Language Models (LLMs) hosted on Amazon Bedrock?

In practice, when building Generative AI applications, you cannot simply hand out raw Bedrock API endpoints or keys for everyone to invoke directly. Costs would skyrocket, and tenant isolation (managing data boundaries between users) would be virtually non-existent. After struggling with this for a while, I discovered an excellent reference pattern from Dynatrace and decided to run an experimental implementation. Today, I'll share my hands-on experience designing this "AI Gateway".

### GENERAL ARCHITECTURE - LIGHTWEIGHT YET POWERFUL

Instead of letting clients hit Bedrock directly, we establish a protective shield centered around Amazon API Gateway. The entire data flow breaks down as follows (refer to the diagram for visualization):

* **Route 53 (Optional but recommended):** Instead of using the lengthy default AWS API Gateway URL, we map a custom domain via Route 53 for a cleaner, professional corporate presentation.
* **API Gateway (Main Entryway):** Here, we configure rate-limiting rules to prevent abuse and set quotas to avoid budget overruns. The key benefit is its support for HTTP response streaming, ensuring real-time token streaming from the LLM back to the client runs seamlessly.
* **Lambda Authorizer (Security Guard):** Clients calling the API cannot proceed without credentials. We configure a Lambda function to validate incoming JWT tokens, ensuring only authorized requests access backend resources.
* **Lambda Integration (Heart of the System):** This is my favorite part. The integration Lambda function acts as a diligent forwarder. It intercepts the client's raw request (headers, body, and query parameters), signs it automatically using AWS Signature Version 4 (SigV4), and routes it safely to the target Amazon Bedrock endpoints.

### WHY DO I VALUE THIS DESIGN PATTERN?

During actual deployment, this model solves two core problems that infrastructure engineers heavily prioritize:

#### 1. Transparent to Client Experience
I frequently test code locally using AWS Boto3 SDK. The beauty of this gateway is that client-side code remains virtually unchanged when invoking APIs. External systems interact as if they are talking directly to Bedrock, while every request is silently audited and moderated behind the scenes.

#### 2. Future-proof Design
Every Cloud practitioner knows that AWS rolls out updates for Bedrock continuously. If the gateway hardcoded every API endpoint, adding a new model would require editing code constantly.

Since the integration Lambda function only acts as a 'packaging and forwarding' courier without altering the API payloads, new Bedrock model releases or features like Knowledge Bases work immediately without modifying backend gateway code.

### CONCLUSION

Coming from a background focused on monitoring systems and data visualization (like Grafana or Zabbix), routing all AI traffic through a single API Gateway makes it simple to attach monitoring tools to track infrastructure health and project-specific costs.

Leveraging serverless architectures for AI governance enhances security while optimizing operations overhead. If you are architecting infrastructure for GenAI applications on AWS, this AI Gateway model is a must-have component in your stack.

---

### ARCHITECTURE DIAGRAM
![AI Gateway Architecture Diagram](/images/blog2_architecture.png)

---

### REFERENCES & LINKS

* **Group Post Link:** [AWS Study Group - AI Gateway Bedrock Post](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2179637596134534/)
* **AWS Architectural Blog:** [Building an AI Gateway to Amazon Bedrock with Amazon API Gateway](https://aws.amazon.com/blogs/architecture/building-an-ai-gateway-to-amazon-bedrock-with-amazon-api-gateway/)