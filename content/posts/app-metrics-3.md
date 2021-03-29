---
title: "Application Metrics Guidelines - Part 3"
date: 2021-03-15T10:00:00-08:00
draft: false
toc: false
images:
tags:
  - metrics
  - dropwizard
  - java
---

## Part 3: Metrics Nomenclature

In the previous part, I gave an overview on Application Metrics and Resource Metrics. While resource metrics comes inbuilt with many Java frameworks and libraries, we will still need to instrument Application Metrics so that we can measure the performance of the system.

### Metrics Nomenclature

We need to have a naming convention for these metrics, as it will be easy to understand and report the metrics on. The following are rules, if not, guidelines for each component of a metric. Currently, the various Metrics SDK does not enforce these rules, but these are guidelines that people should ideally follow for consistency.

```
<organization>.<service>.<resource>.<entity>.<metricType>.<operation>.<status>
```

**Rules**

* Each term should be separated by “dot”.

* Metric naming should be camelCase.

* Example — *org.myApp.createData.message.gauge.create.success*

* Some of these are optional. It is on the onus of developers to understand the optional ones.

### Metrics Instrumentation

These are the naming conventions for metrics. Once we have identified the different metrics that you plan to instrument for you metrics, the next step is to actually instrument the metrics. There are different libraries that provide you easy ways to implement application metrics. Some of them are —

* Dropwizard Metrics — [https://metrics.dropwizard.io/4.0.0/](https://metrics.dropwizard.io/4.0.0/)

* SpringBoot Metrics — [https://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-metrics.html](https://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-metrics.html)

* StatsD Metrics — [https://github.com/etsy/statsd](https://github.com/etsy/statsd)

This concludes the series of Metrics Guidelines. There is a lot more to metrics post instrumentation. You will have to dashboard the metrics, create alerts on metrics and report them. I have just given an overview of Metrics and ways to identify metrics. Hope this helps you start of instrumenting custom metrics in your code. Happy Coding!
