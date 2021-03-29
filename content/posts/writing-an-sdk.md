---
title: "Writing an SDK in Java"
date: 2021-03-27T17:34:49-08:00
draft: false
toc: false
images:
tags:
  - til
  - sdk
  - java
---

Based on my experiences with building and publishing SDKs, I want to highlight the most important aspects a developer should think about, while building an SDK. Since, I haven’t build an SDK in other programming languages, these tips may/may not be language agnostic.

### **1. Keep your API’s simple**

When building an SDK, your API’s should be very simple and very easy to implement. Think about the users of the SDK, and try to ensure that they can implement the API’s with as minimal of code changes as possible.

### **2. Ensure proper Javadocs for API’s**

All public classes and API’s should have well-defined Javadocs to ensure that a user can understand everything there is to know about a class and its methods. You may also want to think about publishing your javadocs as well. Please refer to — [http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html](http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html) to get good practices on writing Javadocs.

### **3. SDK Initialization**

When calling the SDK class, make sure that your SDK initialization in done one of the standard Java design patterns. The more popular ways of initializations are singleton pattern, builder pattern, constructor with overload etc.

### **4. Logging Standards**

Needless to say, the SDK should follow standing logging conventions (log4j, slf4j). Also, logs should be unique to the SDK, in order to clearly distinguish SDK logs versus Application logs.

### **5. Example Projects**

Include sample projects in your repository that implements the latest version of the SDK. If you are writing an SDK in Java, try to include sample projects for different frameworks such as SpringBoot, Dropwizard as well as for a simple Java application. You may also want to think about implementing the SDK in a Scala app as well.

### **6. Backward Compatibility**

As far as possible, try and ensure that each release of the SDK does not include any breaking changes and is backward compatible to the previous version.

### **7. README file**

Have a README file that explains the following: Description, Advantage of using the SDK, why this SDK, how to import the SDK(what to include in the the POM), Current release version, how to implement the SDK.

### **8. Release Planning & Versioning**

All breaking changes to the API should be a major version release (1.0, 2.0 etc). [https://semver.org/](https://semver.org/) gives more details on how to handle releases. Each SDK release should have a list of changes that are properly documented. The Github Release page ([https://help.github.com/articles/creating-releases/](https://help.github.com/articles/creating-releases/)) is really useful, and you can use that to draft your releases.

These are just a few tips for you to get started on with writing and publishing an SDK. Happy to hear your thoughts on this! All the best building your SDK :)
