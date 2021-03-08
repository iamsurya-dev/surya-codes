---
title: "TIL: Testing static methods in Java"
date: 2021-03-07T21:39:12-08:00
draft: true
toc: false
images:
tags:
  - til
  - powermock
  - java
---

## TIL: Testing static methods in Java

Let’s assume that we have 3 files: `PersonUtil.java` and `People.java` and `PeopleTest.java`.

If you encounter a situation where you want to test method `getName()` , you would need to use PowerMock to mock static method `getPerson()`. Here’s how we implement this.

Few things to note here: `@PrepareForTest` should be added to set the list of classes that has to be mocked. In our main test, all we do is mock the `PeopleUtil.class` , and when `getPerson()` is called, then return “TestName”.
If you are using Maven, then we depend on: powermock-api-mockito, powermock-module-junit4 for the PowerMock dependencies.
One last thing to keep in mind is that, there are some compatibility issues between PowerMock and Mockito. So, while adding the dependency version, you should refer to https://github.com/powermock/powermock/wiki/Mockito#supported-versions