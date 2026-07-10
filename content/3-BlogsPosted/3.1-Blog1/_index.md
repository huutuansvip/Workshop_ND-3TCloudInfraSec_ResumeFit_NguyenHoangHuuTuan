---
title: "Blog 1"
date: 2026-06-29
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---
# AWS SYSTEM OBSERVABILITY: STREAMING CLOUDWATCH METRICS TO VPC-BASED OPENTELEMETRY COLLECTORS USING LAMBDA

*Posted by: Nguyen Hoang Huu Tuan*

Managing observability for large-scale cloud systems is always a challenging task, especially when organizations seek to balance cost, flexibility, and security. Although OpenTelemetry is rapidly becoming the industry standard helping organizations escape vendor lock-in, they face a major technical hurdle: how to stream metrics from AWS CloudWatch directly into internal collection systems strictly isolated inside a private VPC. To address this challenge, using AWS Lambda as a data transit hub from CloudWatch Metric Streams to the internal network has proven to be highly effective, ensuring data streams are delivered securely and instantaneously.

### HERE ARE THE KEY HIGHLIGHTS OF THIS PUSH-BASED OBSERVABILITY SOLUTION:

* **Transitioning from Pull to Push Model:** Relying on tools like Prometheus to constantly poll/pull data triggers API throttling, metrics loss, and high costs. The push-based model using CloudWatch Metric Streams resolves this, delivering event-driven data with sub-minute latency for real-time alerting.
* **Overcoming Amazon Data Firehose Limitations:** Although Firehose supports pushing data to HTTP endpoints, they are required to be publicly accessible endpoints. To route data into private subnets, AWS utilizes an AWS Lambda function (Lambda Transform Function) as a secure bridge. Firehose batches the data and invokes Lambda, which then pushes metrics through a Network Load Balancer (NLB) deep into the VPC securely.
* **OpenTelemetry Collector as the Heart of the System:** Running on Amazon EC2 instances inside the VPC, the Collector serves as a processing hub with three flexible components: Receivers (ingesting data), Processors (filtering, enriching, or masking sensitive data), and Exporters (shipping data to various destinations such as Grafana, AWS X-Ray, or Amazon OpenSearch).
* **Scalability and Backup Redundancy:** Utilizing a Network Load Balancer (NLB) to distribute TCP traffic to EC2 instances allows the system to easily scale horizontally. Additionally, an Amazon S3 bucket is configured as a backup destination for Firehose (generating zero storage fees if Lambda successfully forwards the data).
* **Cost Optimization and Eliminating Vendor Lock-in:** OpenTelemetry (completely free under the Apache 2.0 license) relieves businesses of high third-party software licensing fees. Its standardized nature allows operations teams to freely switch backend observability platforms later without rebuilding the telemetry collection pipeline.

Overall, combining AWS services like Lambda, Firehose, and Network Load Balancer forms a perfect bridge, closing the gap between public cloud services and enclosed private networks. This architecture resolves latency issues and traditional API bottlenecks while giving development teams maximum control. By establishing an intelligent data flow, organizations can freely construct a robust, independent, cost-effective monitoring ecosystem ready to scale without vendor lock-in risks.

> Building a monitoring system is not hard; the hard part is making it secure, cost-effective, and vendor-neutral.

---

### ARCHITECTURE DIAGRAM
![CloudWatch Metric Stream to OpenTelemetry Collector Architecture](/images/blog1_architecture.png)

---

### REFERENCES & LINKS

* **Group Post Link:** [AWS Study Group - First Cloud Journey Post](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2173544653410495/)
* **AWS Architectural Blog:** [Streaming CloudWatch metrics to VPC-based OpenTelemetry collectors using AWS Lambda](https://aws.amazon.com/blogs/architecture/streaming-cloudwatch-metrics-to-vpc-based-opentelemetry-collectors-using-lambda/)