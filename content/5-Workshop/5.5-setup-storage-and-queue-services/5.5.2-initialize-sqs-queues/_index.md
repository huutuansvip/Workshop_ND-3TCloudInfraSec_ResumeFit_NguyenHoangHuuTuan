---
title: "Initialize SQS Queues"
date: 2026-07-09
weight: 2
chapter: false
pre: " <b> 5.5.2. </b> "
---

Use queues to separate heavy AI processing tasks from the main web response flow.

1. Go to the **SQS** interface. Create a Standard queue named `ResumeMatching-DLQ` (Dead Letter Queue) used to catch messages that encounter errors during processing.

![Create queue](/images/5-Workshop/Tao_queue.jpg)
<p align="center"><i>Create queue</i></p>

2. Initialize the main queue named `ResumeMatching-Queue`.

![Create main queue](/images/5-Workshop/Tao_main_queue.jpg)
<p align="center"><i>Create main queue</i></p>

3. Enable the **Dead-letter queue** feature on the main queue, point to the ARN of `ResumeMatching-DLQ` and set `Maximum receives` = `3`.
