# Android Testing Codelab

This folder contains the source code for the Android testing codelab. It gives an introduction into testing on Android, including unit tests and UI tests. It is for self-study purpose.

### Use an iterative development workflow
It's important to consider the units of responsibility that emerge as we design new feature. For each unit, we write a corresponding unit test. The two cycles associated with iterative, test-driven development as the below figure
<img src="https://developer.android.com/images/training/testing/testing-workflow.png" height="255">

### Understand the testing pyramid

Application should include three categories of tests: small (unit test), medium (integration test) and large (ui test):<br />
* <b>Small tests (70%)</b>: unit tests that you can run in isolation from production systems. They typically mock every major component and should run quickly on your machine. <br/>
* <b>Medium tests (20%)</b>: integration tests that sit in between small tests and large tests. They integrate several components, and they run on emulator or real devices. <br/>
* <b>Large tests (10%)</b>: integration and ui tests that run by completing a UI workflow. They ensure that key end-user tasks work as expected on emulator or real devices. <br/>
<img src="https://developer.android.com/images/training/testing/pyramid.png" height="255">

### Understand threads in tests

AndroidX Test makes use of the following threads:<br/>
* <i>The main thread = UI thread = activity thread</i>, where UI interactions and activity lifecycle events occur.
* <i>The instrucmentation thread</i>, where most of your tests run. When your test suite begins, the <b>AndroidJUnitTest</b> class starts this thread<br/>

If you need a test to execute on the main thread, annotate it using @UIThreadTest.

### Small Tests
As we add and change app's functionality, make sure that these features behave as intended by creating and running unit tests against them. We have three major ways for creating small tests: <br/>
* <b> [Roboelectric](http://robolectric.org/) </b>: requires unit tests to interact more extensively with the Android framework. <br/>
* <b> [Mockito](https://site.mockito.org/) </b>: running unit tests against a modified version of "android.jar", which doesn't contain any code.
* <b> Instrucmented unit tests </b>: run instrucmented unit tests on a physical device or emulator, which doesn't involve any mocking or stubbing of the framework.

### Medium Tests
TBD <br/>

### Large Tests
The [AndroidJUnitRunner](https://developer.android.com/reference/androidx/test/runner/AndroidJUnitRunner.html) class defines an instrucmentation-based [JUnit](https://junit.org/junit4/) test runner that lets you run JUnit3- or JUnit4- styles test classess on Android devices. The test runner faciliates loading your test package and the app under test onto a device or emulator, running your tests, and reporting the results. The [AndroidJUnitRunner](https://developer.android.com/reference/androidx/test/runner/AndroidJUnitRunner.html) class also supports the following tools and framework from AndroidX Test: <br/>
* <b> [JUnit4 Rules](https://developer.android.com/training/testing/junit-rules.html) </b>: ATSL includes code for managing the lifeccycles of key app components involved in your tests, such as activities and services. <br/>
* <b> [Espresso](https://developer.android.com/training/testing/espresso/index.html) </b>: Espresso synchronizes asynchronous tasks while automating the following in-app interactions, both on your development machine and on real devices: <br/>


### License


```
Copyright 2019 An Tran.

Licensed to the Apache Software Foundation (ASF) under one or more contributor
license agreements. See the NOTICE file distributed with this work for
additional information regarding copyright ownership. The ASF licenses this
file to you under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License. You may obtain a copy of
the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the
License for the specific language governing permissions and limitations under
the License.
```
