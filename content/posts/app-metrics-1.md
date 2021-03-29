---
title: "Application Metrics Guidelines - Part 1"
date: 2021-03-10T10:00:00-08:00
draft: false
toc: false
images:
tags:
  - metrics
  - dropwizard
  - java
---

## Introduction to Metrics

The purpose of this series is to outline a set of guidelines that developers should follow while instrumenting metrics into their application. Before we dive deep into the nitty-gritty of application metrics, let us start off with a simple introduction of metrics.

### **What are metrics?**

Metrics capture a value pertaining to your systems *at a specific point in time. *For example, the current lag in consuming messages from a kafka cluster, or, the current CPU utilization of your service. Metrics are usually collected once per second, one per minute, or at another regular interval to monitor a system over time. Therefore, metrics are useful in effectively monitoring a production-compliant service.

### **Types of Metrics**

We are basing the types of metrics from DropWizard Metrics. There are a lot of other Metrics libraries, but essentially. the concept is more or less the same.

**Gauge:**

* A gauge is the simplest metric type. It is the instantaneous value of something.

* A gauge is used if you want to set the metric to a particular value. Example: If you want to update the status of a particular task. Or, if you want to measure the number of pending jobs in a queue.

* Metrics exposed: *value*

**Counter:**

* A counter is an incrementing and decrementing value of a metric. A service would use a Counter only when you need an absolute number.

* Example Usage: The total number of bytes sent in HTTP requests. The total number of open connection.

* Metrics exposed: *count*

**Meter:**

* A meter measures the average rate of events over a period of time. This measures the mean throughput and one-, five-, and fifteen-minute exponentially-weighted moving average throughputs.

* Example Usage: Average number of calls per second (events/sec)

* Metrics exposed: *count, mean rate, 1-minute rate, 5 minute rate, 15-minute rate*

**Histogram:**

* A histogram measures is used to keep track of a stream of values and does a statistical distribution of those values.

* Example Usage: Average size of request in bytes over a period of time

* Metrics exposed: *count, mean rate, 1-minute rate, 5 minute rate, 15-minute rate, min, max, stddev, median, 75%, 95%, 98%, 99%, 99.9%*

**Timer:**

* A timer measures both the rate that a particular piece of code is called and the distribution of its duration.

* It is basically a combination of both a meter and a histogram.

* Example Usage: 99th percentile time of all requests that hit an API

* Metrics exposed: *count, mean rate, 1-minute rate, 5 minute rate, 15-minute rate, min, max, stddev, median, 75%, 95%, 98%, 99%, 99.9%*

I hope this gives an overview of Metrics and the different types of metrics. In the [next part](https://surya.codes/posts/2021/03/application-metrics-guidelines-part-2/), I will give an overview on the Custom Application Metrics and Resource Metrics.
