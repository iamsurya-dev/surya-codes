---
title: "Application Metrics Guidelines - Part 2"
date: 2021-03-13T10:00:00-08:00
draft: false
toc: false
images:
tags:
  - metrics
  - dropwizard
  - java
---

## Part 2: Application and Resource Metrics

In Part 1, I gave an overview on Metrics and the different types of Metrics. In this part, let us go through Application Metrics and Resource Metrics.

### Application Metrics

Application metrics indicate top-level health of your system by measuring its useful output. When considering these metrics, it’s often helpful to break them down into four subtypes:

**Throughput**

* It’s the amount of work the system is doing per unit time. Throughput is usually recorded as an absolute number.

* Example: Requests to an API per second

* Metric Type: Meter, Histogram

**Success**

* These metrics represent the percentage of work that was executed successfully.

* Example: % of Responses from a REST endpoint that are of status 2xx

* Metric Type: Meter

**Error**

* These metrics capture the number of erroneous results. It can be expressed as a rate of errors per unit time or normalized by the throughput to yield errors per unit of work.

* Example: % of Responses from a REST endpoint that are of status 5xx

* Metric Type: Meter

**Performance**

* These metrics quantify how efficiently a component is doing its work.

* For example is latency represents the time required to complete a unit of work. It can be expressed as an average or as a percentile, such as “99% of requests returned within 0.1s”.

* Example: 90th percentile response time in seconds

* Metric Type: Timer, Histogram

These metrics are incredibly important for observability. They help us answer questions about the service’s internal health and performance:

1. Is the system available and actively doing what it was built to do?

1. How fast is it producing work?

1. What is the quality of that work?

### Resource Metrics

Resource metrics can help you reconstruct a detailed picture of a system’s state, making them especially valuable for investigation and diagnosis of problems. It gives an insight on some low-level resources such as CPU, memory, disks and network interfaces, which are important to monitor. Typically, these metrics are JVM specific metrics and NOT tied to the custom application metrics. A lot of these metrics come by default in Java Frameworks as well. It contains:

**Utilization**

* It’s the percentage of time that a resource is busy, or the percentage of the resource’s capacity that is in use.

**Saturation**

* It’s a measure of the amount of requested work that the resource cannot yet service, often queued; often termed as *“operational backlog”*.

**Errors**

* It represents internal errors that may not be observable in the work the resource produces.

**Availability**

* It represents the percentage of time that the resource responded to requests.

* This metric is only well-defined for resources that can be actively and regularly checked for availability.

Now that we have an understanding of the different use cases of Metrics, we will [next look](https://surya.codes/posts/2021/03/application-metrics-guidelines-part-3/) at metrics nomenclature of custom application metrics.
