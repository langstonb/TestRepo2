# Testing

DevOps Package

# Mission Statement

DevOps Package

To significantly  __reduce the barriers to entry __ of DevOps strategies into the day\-to\-day workflow of Automation Studio project development\, in order to  __increase the efficiency\, quality\, and maintainability __ of the resulting applications



# Contents

Testing

* What is it?
* Why is it important?
* Included Template Files
* How to Implement:
  * A Test Plan
  * Test Driven Development
  * B&R Unit Testing
  * Integration Testing
  * Manual Testing

![](img%5CTesting0.png)



# Before we get started

Setting the stage

Testing can either be  __automated__  or  __manual__

In DevOps\, the goal is that you have as much automated testing as possible\. Therefore\, the primary focus of this PPT automated testing

Nonetheless\, some manual testing will inevitably be necessary\. Therefore\, manual testing strategies are provided at the end

![](img%5CTesting1.jpg)



# What is it?

Automated Testing

# Automated Testing

Definition

![](img%5CTesting2.png)

Automated testing begins with a defined test plan\, comprised of required features and previously discovered bugs\.  The test plan is the contract of what the software is expected to deliver\.

A consistent set of inputs is used for each test\. This allows multiple programmers to execute the tests in the exact same way\.

The tests are run automatically \- not by hand \(manually\) by each engineer

If a bug is discovered\, a new test is written to catch the bug so that once it is fixed\, you will always be checking to confirm it does not return in the future

![](img%5CTesting3.png)

![](img%5CTesting4.png)

![](img%5CTesting5.png)



# Types of Tests

![](img%5CTesting6.png)

Requires manual testing

Will be added in a future revision of the DevOps package

Our primary focus



# Why is it important?

Automated Testing

# Benefits

Automated Testing

Running automated tests is MUCH faster than manual testing

Bugs that are found later in development are more difficult and take longer to fix

![](img%5CTesting7.png)

Saving engineering time saves you money

End up with fewer bugs in production code \(studies have shown between 40%\-90% less bugs[1](https://www.microsoft.com/en-us/research/wp-content/uploads/2009/10/Realizing-Quality-Improvement-Through-Test-Driven-Development-Results-and-Experiences-of-Four-Industrial-Teams-nagappan_tdd.pdf)\!\)

New tests are written for each new bug that is found\. This ensures that future features/bugfixes don’t break existing functionality

Existing tests are repeatably executed with every release

Encourages the design of more modular / testable code

![](img%5CTesting8.png)

![](img%5CTesting9.png)

Increase the testability\, readability\, and adaptability of the code\.

_Testability_ : create thorough and reproducible tests

_Readability_ : tests become a record of bugs and features\. Makes it easier for other engineers to understand the code

_Adaptability_ : promotes the creation of modular code

![](img%5CTesting10.png)



# Arguments Against Automated Testing

And How to Address Them

![](img%5CTesting11.png)

Creating unit tests is too time consuming

The result is higher quality software and less bugs in the field\. The time you spend writing automated tests would end up being spent \(and then some\!\) during manual testing anyway

![](img%5CTesting12.png)

If you don’t know enough about the requirements to write a test\, then you don’t have enough information to write quality code\. We must avoid the tendency to start coding before a proper plan is in place

You can’t write the test until you know the design

* It can be difficult at first\, but like most things it gets easier the more you do it
  * It is definitely difficult if you wait to add unit tests at the end \(don’t do that\!\)
  * This could also be an indication that your design is not easily testable \(too much functionality in a single function / function block / task\, etc\)
  * Not everything is able to be unit tested\. But in those cases\, you will rely on manual testing

![](img%5CTesting13.png)

Unit testing is hard\!

![](img%5CTesting14.png)

I don’t know how\!

Hence why this DevOps package exists\!



# Included Template Files

DevOps Package

Testing

The following template files are included in the DevOps package:

A [template Excel file ](slide68.xml)for keeping track of your tests

A unit test getting started guide

Examples of good and bad unit tests

![](img%5CTesting15.png)



# How to Implement

  * A Test Plan
  * Test Driven Development
  * B&R Unit Testing
  * Integration Testing
  * Manual Testing

# Test Plan

![](img%5CTesting16.png)

# How to Build a Test Plan

Testing at B&R

* The testing process begins with a solid and complete test plan that is closely linked to the project spec
* The test plan must be thoughtfully written before testing and development begin
  * The requirements \+ project specification \+ test plan all go together\. These should be completed before you write any code\.
* In this section\, we will identify recommendations for building such a test plan\. The overall  steps are as follows:

Test Execution and Reporting

Analyze the Application

Design the Test Strategy

Define the Test Modules and Test Cases



Analyze the Application

Design the Test Strategy

Define the Test Modules and Test Cases

Test Execution and Reporting

# Analyze the Application

How to Build a Test Plan

* The first step in building a test plan is to fully understand the application under test
* __Therefore\, the __  __specification__  __ must be written before you can create your test plan__
  * For new projects\, the base functionality must be defined
  * For new features in an existing project\, the details for that feature must be defined
* Remember: If the project has not been defined yet\, then you cannot write reliable or quality code \(not to mention\, quality tests\!\)



Analyze the Application

Design the Test Strategy

Define the Test Modules and Test Cases

Test Execution and Reporting

# Design the Test Strategy

How to Build a Test Plan

There are several things that must be defined in the overall test strategy:

Testing Scope

Testing Type

Resource Planning

Testing Schedule



Analyze the Application

Design the Test Strategy

Define the Test Modules and Test Cases

Test Execution and Reporting

How to Build a Test Plan

There are several things that must be defined in the overall test strategy:

__Testing Scope__

Testing Type

Resource Planning

Testing Schedule

_Testing Scope_

Based on the project specification\, define what will and will not be tested



Analyze the Application

Design the Test Strategy

Define the Test Modules and Test Cases

Test Execution and Reporting

How to Build a Test Plan

There are several things that must be defined in the overall test strategy:

Testing Scope

__Testing Type__

Resource Planning

Testing Schedule

_Testing Type_

This DevOps package provides direct recommendations on unit testing and manual testing

Integration testing will be addressed in a future revision



Analyze the Application

Design the Test Strategy

Define the Test Modules and Test Cases

Test Execution and Reporting

How to Build a Test Plan

_Resource Planning_

Define at least one  __personnel resource __ for the following 4 testing roles\. Note that one single person can hold multiple roles:

There are several things that must be defined in the overall test strategy:

Testing Scope

Testing Type

__Resource Planning__

Testing Schedule

| Role | Description |
| :-: | :-: |
| Test manager  | Defines the tests |
| Test developer  | Writes the automated tests |
| Manual tester  | Executes the manual tests. Does not analyze the results of any subjective tests (if applicable)<br />Note: This should not be the programmer. Ideally should be an experience user of the machine under test |
| Manual test approver  | Analyzes the outcome of the subjective manual tests (if applicable) |



Analyze the Application

Design the Test Strategy

Define the Test Modules and Test Cases

Test Execution and Reporting

How to Build a Test Plan

_Resource Planning_

Define  __test environments__ :

There are several things that must be defined in the overall test strategy:

Testing Scope

Testing Type

__Resource Planning__

Testing Schedule

| Test Env’t | Description / Action Items |
| :-: | :-: |
| Automated test environment  | Refer to the Build Server section of this DevOps package |
| On-machine testing | Identify the point of contact for scheduling machine time<br />Identify any materials and prerequisites needed for on-machine testing  <br />Estimate the time expected to complete the manual tests<br />Identify the testing location (OEM or end user)<br />Remember: manual testing is a distinct step from commissioning!  |



Analyze the Application

Design the Test Strategy

Define the Test Modules and Test Cases

Test Execution and Reporting

How to Build a Test Plan

There are several things that must be defined in the overall test strategy:

Testing Scope

Testing Type

Resource Planning

__Testing Schedule__

* _Testing Schedule_
* Identify how often you will run the automated tests
  * Refer to the Build Server section of this DevOps package
* Identify when and how often you will run the manual tests\, first in simulation and then on machine
* Plan a time to review all test results and define the next steps
  * i\.e\. [Test execution and reporting](slide27.xml)



Analyze the Application

Design the Test Strategy

Define the Test Modules and Test Cases

Test Execution and Reporting

# Define the Test Module and Test Cases

How to Build a Test Plan

* Definitions:
  * A test module describes an overall functionality on the machine\. This is used for organizing all of the test cases\.
  * A test case is a specific\, granular test condition\. Several test cases are used to fully test a test module\.
* Examples:
  * Test Module: Alarm System
    * Test Case 1: Confirm that the alarm history successfully exports
    * Test Case 2: Confirm that the AlarmList widget on the HMI properly displays the alarms
    * …
  * Test Module: Recipe System
    * Test Case 1: Confirm you are warned / prompted if the default recipe is missing
    * Test Case 2: Confirm that you can edit the active recipe and the changes are applied immediately
    * …
* Directives:
  * All test modules and corresponding test cases must be defined\. This should be done within the testing template excel sheet that is provided in this DevOps package
  * Identify whether each test case will be implemented with unit testing or manual testing
  * Identify who has ownership of each test case \(refer to [Resource Planning](slide20.xml)\)



Analyze the Application

Design the Test Strategy

Define the Test Modules and Test Cases

Test Execution and Reporting

How to Build a Test Plan

Below is a list of generic tests that should be applied to every machine \(slide 1 of 2\)\. This list will continue to be expanded to over time\.

HMI

All inputs should have proper limits \(>max and <min are not permitted\)

Language changes accordingly as well as all the text fits in the given spaces in all languages

Unit conversion functions

Confirm that inputs are locked out for users that don't have access\. Part of the manual tests\.

Confirm the alarm list is visible / working properly\, and that alarms are acknowledgeable

If HMI gets disconnected from the PLC \(in hardware topologies where this is possible\)\, test that recovery is possible\, but also that commands don't happen unintendedly after disconnect \(i\.e\. if you are manually jogging\, disconnect\, don't keep jogging indefinitely\) \(i\.e\. if you are in automatic mode\, HMI disconnects\, is it ok to continue?\)

Manually test for system responsiveness\, if it is "good enough“

Basic Motion

E\-stop\, confirm it works

Homing\, confirm it works and it's repeatable

Software limits \(confirm the axis stops after reaching the limit\)

Hardware limits \(confirm the axis stops after reaching the limit and before the hard stop\)

Jog\, confirm it works

Error conditions and recovery \- examples: lag error\, loss of comm from the PLC to the drive\, etc\. Will depend on the app\, but think about these error conditions and confirm that you can successfully recover\.



Analyze the Application

Design the Test Strategy

Define the Test Modules and Test Cases

Test Execution and Reporting

How to Build a Test Plan

Below is a list of generic tests that should be applied to every machine \(slide 2 of 2\)\. This list will continue to be expanded to over time\.

IO

Check that the ModuleOKs are monitored and that the response is as intended \(just an alarm\, stop the machine\, service mode\, etc\)

For any IO points that have a status feedback\, make sure you're monitoring them and doing something with that information\. The test here is regarding what you actually do with that status information\. Confirm that the next step works\.

Fieldbuses\- if disconnected\, check you can recover\, and that the machine responds in the way that you need it to\.

Data management

Wear level monitoring info that came in AR4\.9\, make sure you are using that information and that the response is as intended\.

If your file device storage medium gets full\, check that upon trying to save new data you are appropriately warned and that you don't lose any data



Analyze the Application

Design the Test Strategy

Define the Test Modules and Test Cases

Test Execution and Reporting

# Test Execution and Reporting

How to Build a Test Plan

* Automated Tests
  * The automation server executes the tests in ARsim and provides a report on the automated tests
  * Refer to the Automation Server section of this DevOps package

* Manual Tests
  * Manual tests are manually executed and reported
  * Manual testing should be done only after the Automated Tests are in a good state \(mostly or fully all passing\)
  * To help keep track of the status of the manual tests\, there is a template Excel file provided in this package
  * Details for how to use the file are included on the first tab \(“Overview”\)
  * Be sure to identify the software version you are testing in the sheet\, so that it is clear exactly what version you have tested

![](img%5CTesting17.png)

![](img%5CTesting18.png)



Analyze the Application

Design the Test Strategy

Define the Test Modules and Test Cases

Test Execution and Reporting

How to Build a Test Plan

* At this step you must also define the overall test criteria for what constitutes pass/fail
  * At what point do you consider a feature or the machine as a whole “done”?
* It is indeed possible that a machine can ship with certain defects \(failed tests\)\. It is up to the project manager discretion whether a specific test is a show\-stopper or not
  * Ask yourself: Is the cost of delaying shipment worth the defect?
* Execute all tests at least once\. For each failed test\, identify if the test case is a showstopper or not\.
  * This saves you from having to make this decision for every single test\. In practice you only need to decide for tests that fail at any point\.
  * Alternatively\, you can define a priority for each failed test\. Then pick a cutoff point where the machine can ship despite defects

![](img%5CTesting19.png)



# Test Driven Development

Overview

We will not only be focusing simply on automated unit tests themselves\, but also on the  __Test Driven Development \(TDD\) __ workflow\, which provides guidelines for when/how to write your tests



Test First

* Write the test
  * In TDD\, the test is written BEFORE the feature itself
* Run the test
  * The test must fail because the feature has not been implemented yet
  * If the test succeeds\, re\-work the test until it fails
* Write the code for the feature
  * Afterwards\, run the test\. If the feature was implemented correctly\, the test should pass
  * If the test fails\, re\-work the feature until the test passes



Refactor

![](img%5CTesting20.png)

* Run all tests\, check if they succeed
* If all tests succeed\, consider refactoring
  * Now that you have identified what needs to be done in order to pass each test\, you may realize a better way to accomplish a feature\. Refactor accordingly\.
  * If some tests fail\, correct the features and/or the tests themselves
  * Once this whole process is complete\, return to the “Test First” development phase by writing the tests for the next features to be implemented \(step 1 on the previous slide\)



# What to Test

Automated Testing

* Test the common / baseline functionality
  * This will tell you when the code breaks after you made a change \(new feature / bugfix\)
* Test the edge cases of unusually complex code that you think could have potential errors
  * This is code that is likely to break when changes are made
* Whenever you find a bug\, write a new test case to cover it  __before __ fixing it
  * This ensures that you have correctly identified how to reproduce the bug and that your fix is correct
  * It also ensures that you will catch it if the bug returns due to a code change in the future
* Add edge case tests to less critical code whenever you have extra time
  * Increases code quality when time permits

![](img%5CTesting21.png)



# What/When NOT to Test

Automated Testing

* <span style="color:#FF0000"> __Do__ </span>   <span style="color:#FF0000"> __not__ </span>  write tests for trivial code
* <span style="color:#FF0000"> __Do__ </span>   <span style="color:#FF0000"> __not__ </span>  write trivial tests that don’t add benefit to your process
* <span style="color:#FF0000"> __Do__ </span>   <span style="color:#FF0000"> __not__ </span>  use unit testing to test system level functions
  * Better covered by integration tests or manual testing\, as opposed to unit testing
  * Integration test recommendations coming soon
* <span style="color:#FF0000"> __Do__ </span>   <span style="color:#FF0000"> __not__ </span>  write tests while the application requirements are still rapidly changing
  * Remember\, the requirements must be clearly defined up front in order to write meaningful tests and quality code
* <span style="color:#FF0000"> __Do__ </span>   <span style="color:#FF0000"> __not__ </span>  wait until the end of the application development to write all your tests
  * It is quite easy to end up with a lot of code that is difficult to test because it is not written in a modular way

![](img%5CTesting22.png)



![](img%5CTesting23.png)

# Backfilling Unit Tests

Into Existing Projects

* Although Test Driven Development is indeed the best way to work\, there will be some instances where you will be forced to backfill unit tests rather than integrate them as you go
* Most commonly\, this will occur if you are working on an established / existing project that does not yet have any unit tests implemented
* __Without a doubt\, it is valuable to backfill unit tests\!__
* However\, there are some additional considerations / tips to keep in mind for this situation \(see next slide\)
* The unit tests that you should definitely and immediately implement \(even if no other tests exist yet\) are tests for new bugs that you encounter and fix



![](img%5CTesting24.png)

Some Tips

  * Understand the existing code\. Define or find the spec for this code\, because those are the “rules” that you will be testing for\.
  * Review your existing manual test plan and identify the tests that you can automate
  * Wait until the end of development for features that are already in progress
    * If you are refactoring existing code or the application is in flux\, do not write the unit tests yet
    * Since the tests were not the very first thing you did \(aka TDD\)\, they should be the very last thing you do
    * Brand new features should be implemented with TDD
  * You may want/need to refactor existing code to make it more testable
  * Do not test trivial things
    * This is especially a risk when you are backfilling
    * Focus on things that are in the project specification\. If you are writing tests for things that are not in the spec\, this is a hint that they might be trivial / unhelpful / meaningless
    * Test things that you actually expect might break in the future
  * Make sure you are adding value
    * Don’t backfill just for the sake of backfilling\. Make the tests count\.
    * Put in enough effort so that you trust the results of the test even though they were an afterthought\.
    * If no value is added\, you will not convince others \(or yourself\) to write unit tests for projects in the future



# B&R Unit Testing

# Introductory Resources

B&R Unit Testing

For a step\-by\-step guide on how to set up and use B&R Unit Testing\, refer to the guide from AutomationCON 2021\. This has been included as a template file\.

![](img%5CTesting25.png)



# Dedicated Unit Test Configuration

B&R Unit Testing

The unit test tasks should not be deployed on a commissioned machine

Therefore\, you should have a dedicated configuration in the AS project for unit testing

![](img%5CTesting26.png)

![](img%5CTesting27.png)



# Tips for Writing in C

| Topic | ST | C |
| :-: | :-: | :-: |
| Assignment operator | := | = |
| Address reference | ADR(var) | &var |
| End of line | ; | ; |
| Comment | // | // |
| Equality | = | == |
| Inequality | <> | != |
| “And” operator | AND | && |
| “Or” operator | OR | || |
| “Not” operator | NOT | ! |
| String boundary | ‘ | “ |
| Dynamic variable | AH GUID: 7777cae3-cdc0-4bf8-a12e-287ec8f75000 | Link |

B&R Unit Testing

* B&R Unit Tests must be written in the C programming language\. The task under test can be written in any programming language \(ST\, ladder\, etc\)\, but the tests themselves have to be in C\.
* Here are a few tips / tricks to help you transition quickly from ST to C:

| For loop |  |  |
| :-: | :-: | :-: |
| ST | C |  |
| FOR Var1 := 1 TO 9 DO<br />  //code<br />END_FOR |  | for (Var1 = 1; Var1<10, Var1++)<br />{<br />  //code<br />} |

| Case statement |  |
| :-: | :-: |
| ST | C |
| CASE (stateVar) OF<br />   STATE1: <br />        //code<br />   STATE2:<br />        //code<br />END_CASE | Switch (stateVar)<br />{<br />   case 1:<br />      //code<br />      break;<br />   case2:<br />      //code<br />      break;<br />}<br />break; |

| If statement |  |
| :-: | :-: |
| ST | C |
| IF (condition) THEN<br />   //code<br />ELSIF(condition) THEN<br />  //code<br />ELSE<br />  //code<br />END_IF | if(condition) {<br />   //code<br />} <br />else if(condition) {<br />  //code<br />} <br />else {<br />  //code<br />} |



---

Additional tips: 
- Also note in C if (i = 0) is perfectly valid and assigns 0 to i and evaluates as false.  Some people recommend reversing the statement so that the compiler will catch mistypes (e.g. if (0 = i) would not compile if you really meant if (0 == i))
- And for loop exit condition is always <= in ST but you can decide < or <= in C


# Built-In Tests

B&R Unit Test Framework

* The following tests are built into the B&R Unit Testing framework\. Use cases are provided in the template files\.
* _Setup & Teardown_
* These tests are used to clean things up before / after the tests run
* More specifically:

![](img%5CTesting28.png)

![](img%5CTesting29.png)

Runs before each individual test

Runs after each individual test

Runs before the entire group of tests in the test suite

Runs after the entire group of tests in the test suite

\_SETUP\_TEST:

\_TEARDOWN\_TEST:

\_SETUP\_SET:

\_TEARDOWN\_SET:

![](img%5CTesting30.png)

* _Cyclic code_
* The \_CYCLIC\_SET test code is called once per program cycle\, as long as the test set is active \(in progress\)
* Use cases:
  * Increment a timeout counter
  * Call mapp FUBs that are under test



# Test Structure

B&R Unit Testing

* Each test should have 3 fundamental sections:
* Arrange
  * Sets up the test case
  * Any required settings\, parameters\, or other preparation needed for that specific test case should be performed here
* Act
  * Calls the function to be tested
  * Act steps should cover the main thing to be tested
* Assert
  * Assert expected outcome

![](img%5CTesting31.png)

![](img%5CTesting32.png)

![](img%5CTesting33.png)



B&R Unit Testing

Each test should have 3 fundamental sections:

Arrange

Act

Assert

For simple tests\, this can be accomplished as shown\.

\_TEST testCase1\(void\)

\{

<span style="color:#2E952E">// Arrange</span>

instMyCalc\.CalcOperator <span style="color:#008080"> </span>  <span style="color:#000000">=</span>  <span style="color:#008080"> </span>  <span style="color:#000000">splMyCalcOPERATOR\_ADD</span>  <span style="color:#000000">;</span>  <span style="color:#000000">    instMyCalc\.Param1</span>  <span style="color:#008080">   </span>  <span style="color:#000000">=</span>  <span style="color:#008080"> </span>  <span style="color:#000000">1;</span>  <span style="color:#000000">    instMyCalc\.Param2</span>  <span style="color:#008080">   </span>  <span style="color:#000000">=</span>  <span style="color:#008080"> </span>  <span style="color:#000000">2;</span>

<span style="color:#2E952E">// Act</span>

MyCalculator\(&instMyCalc\);

<span style="color:#2E952E">// Assert</span>

TEST\_ASSERT\_EQUAL\_INT\(3\, <span style="color:#008080"> </span>  <span style="color:#000000">instMyCalc\.Result</span>  <span style="color:#000000">\);</span>  <span style="color:#000000">    TEST\_ASSERT\_EQUAL\_INT\(ERR\_OK\,</span>  <span style="color:#008080"> </span>  <span style="color:#000000">instMyCalc\.Status</span>  <span style="color:#000000">\);</span>

\}



B&R Unit Testing

_Advanced Example:_

Each test should have 3 fundamental sections:

Arrange

Act

Assert

For more advanced tests or tests for asynchronous function blocks\, these sections should be implemented in a case statement\.

This allows the FUBs to be called until they complete the asynchronous action \(since they are called within \_CYCLIC\_SET\)

\_TEST <span style="color:#008080"> </span>  <span style="color:#000000">PowerOn</span>  <span style="color:#000000">\(</span>  <span style="color:#0000FF">void</span>  <span style="color:#000000">\)</span>  <span style="color:#000000">\{</span>  <span style="color:#000000">    TIMEOUT\_TEST\_CASE</span>  <span style="color:#000000">    </span>  <span style="color:#0000FF">switch</span>  <span style="color:#008080"> </span>  <span style="color:#000000">\(</span>  <span style="color:#000000">TestState</span>  <span style="color:#000000">\)</span>  <span style="color:#000000">    \{</span>  <span style="color:#000000">        </span>  <span style="color:#0000FF">case</span>  <span style="color:#008080"> </span>  <span style="color:#000000">TEST\_ARRANGE:</span>  <span style="color:#000000">          </span>  <span style="color:#000000">TestState</span>  <span style="color:#008080"> </span>  <span style="color:#000000">=</span>  <span style="color:#008080"> </span>  <span style="color:#000000">TEST\_ACT;</span>  <span style="color:#000000">        </span>  <span style="color:#0000FF">break</span>  <span style="color:#000000">;</span>  <span style="color:#000000">        </span>  <span style="color:#0000FF">case</span>  <span style="color:#008080"> </span>  <span style="color:#000000">TEST\_ACT:</span>  <span style="color:#000000">            </span>  <span style="color:#0000FF">switch</span>  <span style="color:#008080"> </span>  <span style="color:#000000">\(</span>  <span style="color:#000000">ActSubState</span>  <span style="color:#000000">\)</span>  <span style="color:#000000">            \{</span>  <span style="color:#000000">                </span>  <span style="color:#0000FF">case</span>  <span style="color:#008080"> </span>  <span style="color:#000000">0:</span>  <span style="color:#000000">                    </span>  <span style="color:#000000">AxisControl\.Command\.Power</span>  <span style="color:#008080"> </span>  <span style="color:#000000">=</span>  <span style="color:#008080"> </span>  <span style="color:#000000">true;</span>  <span style="color:#000000">                    </span>  <span style="color:#000000">ActSubState</span>  <span style="color:#008080"> </span>  <span style="color:#000000">=</span>  <span style="color:#008080"> </span>  <span style="color:#000000">1;</span>  <span style="color:#000000">                </span>  <span style="color:#0000FF">break</span>  <span style="color:#000000">;</span>  <span style="color:#000000">                </span>  <span style="color:#0000FF">case</span>  <span style="color:#008080"> </span>  <span style="color:#000000">1:</span>  <span style="color:#000000">                    TEST\_BUSY\_CONDITION\(</span>  <span style="color:#000000">AxisControl\.Status\.Busy</span>  <span style="color:#008080"> </span>  <span style="color:#000000">==</span>  <span style="color:#008080"> </span>  <span style="color:#000000">true\);</span>  <span style="color:#000000">                    </span>  <span style="color:#000000">TestState</span>  <span style="color:#008080"> </span>  <span style="color:#000000">=</span>  <span style="color:#008080"> </span>  <span style="color:#000000">TEST\_ASSERT;</span>  <span style="color:#000000">                </span>  <span style="color:#0000FF">break</span>  <span style="color:#000000">;</span>  <span style="color:#000000">            \}</span>  <span style="color:#000000">        </span>  <span style="color:#0000FF">break</span>  <span style="color:#000000">;</span>  <span style="color:#000000">        </span>  <span style="color:#0000FF">case</span>  <span style="color:#008080"> </span>  <span style="color:#000000">TEST\_ASSERT:</span>  <span style="color:#000000">            TEST\_ASSERT\(</span>  <span style="color:#000000">AxisControl\.Status\.IsPowered</span>  <span style="color:#000000">\);</span>  <span style="color:#000000">            TEST\_DONE;</span>  <span style="color:#000000">        </span>  <span style="color:#0000FF">break</span>  <span style="color:#000000">;</span>  <span style="color:#000000">    \}</span>

<span style="color:#000000">    TEST\_BUSY;</span>  <span style="color:#000000">\}</span>



# Return Statements

B&R Unit Testing

* Each test must always provide a return statement in every scan of the test
* The possible return statements are Busy\, Abort\, or Done
  * Full list shown below
* It is common practice to put TEST\_BUSY outside of your case statement so that the default return statement is that the test is busy
  * See screenshot below
* When one of these return statements is executed\, the test immediately ends\. No subsequent code will run

![](img%5CTesting34.png)

  * In the screenshot to the right\, we don’t technically need the “break;” after TEST\_DONE\, but it is included for clarity nonetheless
  * This also means that you should have your FUB calls at the top of the test\, rather than at the end

![](img%5CTesting35.png)

GUID: 713c4282\-3dea\-4b74\-ace1\-41d8099255a7



# Busy and Abort Return Statements

Use Case

If you are testing asynchronous function blocks\, utilize the Busy and Abort conditions to allow for the FUB to finish processing

Use TEST\_BUSY\_CONDITION\(fub\.Busy == false\) or TEST\_BUSY\_CONDITION\(fub\.Status == 65535\) to wait for the FUB to finish being busy

Use TEST\_ABORT\_CONDITION\(fub\.Status \!= 0\) to abort the test in the event of an error

Examples:

<span style="color:#000000">DirInfo</span>  <span style="color:#000000">\(&</span>  <span style="color:#000000">DirInfo\_UT</span>  <span style="color:#000000">\);</span>

<span style="color:#000000">TEST\_BUSY\_CONDITION\(</span>  <span style="color:#000000">DirInfo\_UT\.status</span>  <span style="color:#008080"> </span>  <span style="color:#000000">==</span>  <span style="color:#008080"> </span>  <span style="color:#000000">65535\);</span>  <span style="color:#000000">TEST\_ABORT\_CONDITION\(</span>  <span style="color:#000000">DirInfo\_UT\.status</span>  <span style="color:#008080"> </span>  <span style="color:#000000">\!=</span>  <span style="color:#008080"> </span>  <span style="color:#000000">0\);</span>



# Test Asserts

B&R Unit Testing

An assert statement is used to declare the expected/passing result of the test

The most basic assert is TEST\_ASSERT\(condition\)\, where the asserted condition is a Boolean value

A full list of available asserts is located at the following GUID \(after installing B&R unit testing\): 50125d50\-e096\-4775\-859c\-2051cb498f67

![](img%5CTesting36.png)



# Timeout Counter

Avoid Getting Stuck in a Test

* It recommended to implement a timeout counter to fail a test if it gets stuck for too long
* The test will be failed if the counter exceeds a certain value
* To implement the timeout counter:
  * Copy the code for the TIMEOUT\_TEST\_CASE macro \(within the template test file\) to the top of your test suite file \(right beneath the \#include section\)\. This macro will force the test to fail if the cycleCount is exceeded\. The rest of the tests in the test suite will subsequently run as usual\.
  * Adjust the cycleCount to a value that makes sense for your testing
  * Declare the following variables test task variable file:
    * “ActSubState” of type USINT
    * “cycleCount” of type USINT
  * Within \_CYCLIC\_SET\, increment cycleCount \(cycleCount\+\+\)
  * Call TIMEOUT\_TEST\_CASE at the top of each test
  * Now\, each test will be protected from getting stuck / never ending

![](img%5CTesting37.png)



# Strategy for UIConnect Commands in Tests

Special Case

If you need to use commands from a UIConnect structure in a test\, you must follow this order of operations within a case statement:

Trigger the command

Wait for the status that the command is in progress \(whatever that may be\)

Wait for it to return to idle

Then SOMETIMES wait for it to refresh \(it’ll automatically do this depending on what command you run\)

Wait for it to return to idle AGAIN

_Then_  you can move on in your testing process

Not following this order of operations causes intermittent failures

Example: Note that the UIConnect case statement is embedded within the TEST\_ACT case of the overall case statement

![](img%5CTesting38.png)



# Variable Mapping File

B&R Unit Testing

* In most \(if not all\) tests\, you will need to use a value of a local variable within the task under test within the unit test\. To get that variable data into the unit test task\, use a Variable Mapping File \(\.vvm\)\. Steps:
* Add the local variable and type file of the task under test as a reference to the unit test task
  * This way\, the unit test task has its own instance of every variable within the task under test
* Add a Variable Mapping File \(\.vvm\) to the unit test configuration
* Within the \.vvm\, map the local variables from the task under test to the equivalent local variable instances within the unit test task\.
  * Variable mapping goes in both directions: inputs from the task under test to the unit test task\, and outputs from the unit test task to the task under test

![](img%5CTesting39.png)



B&R Unit Testing

* Note that you cannot directly map function block outputs from the task under test to the unit test task function block outputs
* As a result\, you need to make a “middle man” structure to capture the value of the FUB outputs and bring them in to the unit test task
  * In the screenshot below\, this corresponds to the MpBlockStatus structure in the unit test task

![](img%5CTesting40.png)



# Debugging

B&R Unit Testing

Breakpoints can be set directly in the unit test code

Therefore\, when a unit test fails\, use the debugger to troubleshoot the problem

![](img%5CTesting41.png)



# Integration Testing

At B&R

pytest and Selenium are the foundation of the mapp View integration testing framework

pytest: Python testing suite

Selenium: driver interface for web browsers\. Allows you to interact with the Chrome browser\.

![](img%5CTesting42.png)

![](img%5CTesting43.png)



pytest

The pytest framework makes it easy to write small\, readable tests\, and can scale to support complex functional testing for applications and libraries\.

Install pytest with:

pip install pytest

Run pytest with:

pytest

pytest finds all files within your current directory that are named test\_\*\.py or \*\_test\.py \(where \* can be anything\) and runs those tests



# Automated Integration Testing Workflow

Summary

* Place all of your test files \(test\_\*\.py or \*\_test\.py\) within one directory of your project repository
* Call pytest in your Jenkinsfile using the helper function RunMappViewIntegrationTests\(\)
  * This helper function allows you to point to another directory that holds your tests\, rather than requiring it to be the same directory as your Jenkinsfile
* For more details on the Jenkinsfile\, refer to the Build Server section of the DevOps Package



# Integration Testing

pytest assert

Unlike B&R unit tests\, there is only 1 assert statement in pytest:

__assert \<Boolean expression>\, “optional failure message”__

_Example:_

def f\(\):

return 3

def test\_function\(\):

assert f\(\) == 4\, “Value was not 4”

def test\_function\_2\(\):

my\_list = \[“apple”\, “banana”\]

assert “apple” in my\_list



# Pytest fixtures

Integration Testing

  * _Example: _
  * import pytest
  * class Fruit:
  * def \_\_init\_\_\(self\, name\):
  * self\.name = name
  * def \_\_eq\_\_\(self\, other\):
  * return self\.name == other\.name
  * @pytest\.fixture
  * def my\_fruit\(\):
  * return Fruit\("apple"\)
  * @pytest\.fixture
  * def fruit\_basket\(my\_fruit\):
  * return \[Fruit\("banana"\)\, my\_fruit\]
  * def test\_my\_fruit\_in\_basket\(my\_fruit\, fruit\_basket\):
  * assert my\_fruit in fruit\_basket

  * A fixture provides a defined\, reliable\, and consistent context for the tests\. This could include an environment \(e\.g\.\, a database configured with known parameters\) or content \(such as a dataset\)\.
  * Fixtures are essentially subroutines that each test case requests\, by adding it as a parameter to the test case
  * Fixtures define the steps and data that constitute the  _setup\, teardown\, and arrange_  phase of a test\. In pytest\, they are functions you define that serve this purpose\.
  * Fixtures are defined with the @pytest\.fixture decorator on a function



# Integration Testing

pytest fixtures

Fixtures can have scopes: function\, module\, class\, package\, session

“Yield” inside a fixture stops the function at that point but will resume at that point after the test  function runs \(Useful for creating a setup and teardown within a single fixture\)

_Example: _

<span style="color:#DCDCAA">@</span>  <span style="color:#4EC9B0">pytest</span>  <span style="color:#DCDCAA">\.fixture</span>  <span style="color:#D4D4D4">\(</span>  <span style="color:#9CDCFE">scope</span>  <span style="color:#D4D4D4">=</span>  <span style="color:#CE9178">"class"</span>  <span style="color:#D4D4D4">\)</span>

<span style="color:#569CD6">def</span>  <span style="color:#D4D4D4"> </span>  <span style="color:#DCDCAA">opcua\_setup</span>  <span style="color:#D4D4D4">\(\):</span>

<span style="color:#D4D4D4">    </span>  <span style="color:#6A9955">\#Setup</span>

<span style="color:#D4D4D4">    </span>  <span style="color:#9CDCFE">opcua\_client</span>  <span style="color:#D4D4D4"> = </span>  <span style="color:#4EC9B0">Client</span>  <span style="color:#D4D4D4">\(</span>  <span style="color:#CE9178">"</span>  <span style="color:#CE9178">opc\.tcp</span>  <span style="color:#CE9178">://localhost:4840/"</span>  <span style="color:#D4D4D4">\)</span>

<span style="color:#D4D4D4">    </span>  <span style="color:#9CDCFE">opcua\_client</span>  <span style="color:#D4D4D4">\.</span>  <span style="color:#DCDCAA">connect</span>  <span style="color:#D4D4D4">\(\)</span>

<span style="color:#D4D4D4">    </span>  <span style="color:#C586C0">yield</span>  <span style="color:#D4D4D4"> </span>  <span style="color:#9CDCFE">opcua\_client</span>

<span style="color:#D4D4D4">    </span>  <span style="color:#6A9955">\#Teardown</span>

<span style="color:#D4D4D4">    </span>  <span style="color:#9CDCFE">opcua\_client</span>  <span style="color:#D4D4D4">\.</span>  <span style="color:#DCDCAA">disconnect</span>  <span style="color:#D4D4D4">\(\)</span>



pytest parameterized test

pytest enables you to run the same test multiple times with different inputs \(i\.e\.\, test parameterization\)

Do this by using the @pytest\.mark\.parameterize function decorator

_Example:_

@pytest\.mark\.parametrize\("test\_input\,expected"\, \[\("3\+5"\, 8\)\, \("2\+4"\, 6\)\, \("6\*9"\, 42\)\]\)

def test\_eval\(test\_input\, expected\):

assert eval\(test\_input\) == expected



Selenium

Selenium allows you to automate web browsers\, primarily for testing purposes

Install selenium with:

pip install selenium



Selenium

* Basic components
* Session
  * driver = webdriver\.Chrome\(\)
* Take action on browser
  * driver\.get\(“http://localhost:81/index\.html?visuId=mappFramework”\)
* Request browser information
  * title = driver\.title
* Find an element\(s\)
  * text\_box = driver\.find\_element\(by=By\.NAME\, value="my\-text"\)
  * submit\_button = driver\.find\_element\(by=By\.CSS\_SELECTOR\, value="button"\)
* Take action on an element
  * text\_box\.send\_keys\("Selenium"\)
  * submit\_button\.click\(\)
* Request element information
  * value = message\.text
* End the session \(close the browser\)
  * driver\.quit\(\)



Selenium

Find elements using Developer tools in Chrome by pressing F12\, or via the “…” menu:

![](img%5CTesting44.png)



Selenium

![](img%5CTesting45.png)

![](img%5CTesting46.png)



IntegrationTestBase\.py

Helper functions:

get\_element – returns an element

wait\_for\_element – waits for an element to be available

wait\_and\_click\_element – waits for an element to be available and click the element

wait\_for\_init\_page – waits for the initial page to load

load\_content – clicks a button that loads a content and waits for the content to be loaded

set\_input – sets an input to a value

get\_value – gets the value of an output

get\_table\_column – returns a column from a table

get\_table\_row – returns the row of a table\, row is identified by a value in a specified column

select\_table\_row – clicks a row of a table\, row is identified by a value in a specified column

select\_downdown\_item – select an item in a dropdown input

get\_open\_dialog\_id – returns the id of the currently opened dialog

read\_variable – reads a variable via OpcUa

write\_variable – writes a variable via OpcUa



IntegrationTestBase\.py

* Included fixtures within the DevOps package:
* visu\_setup\(\)
  * Selenium Chrome Webdriver
  * Will be used in every test
* opcua\_setup\(\)
  * OpcUa client
  * Also need to install asyncua and opcua packages \(pip install asyncua opcua\)
  * Will be needed in most tests
* login\(\)
  * logs in as a specific user



Example



# Manual Testing

At B&R

![](img%5CTesting47.png)

# Template Excel File

Manual Testing

For the situations where it is not possible to write an automated test\, manual testing must be done

To help keep track of the status of the manual tests\, there is a template Excel file provided in this package

Details for how to use the file are included on the Overview tab

![](img%5CTesting48.png)

![](img%5CTesting49.png)



# Manual Testing

Multiple Asserts

* When defining your manual tests\, it can be advantageous to combine more than one expected result \(assert\) into one test
  * Manual testing is more “expensive” since it takes more time\. So\, designing your tests in such a way that a couple of things that are naturally related can be checked over the course of a test can make sense \(as opposed to one dedicated assert per test\)
* However\, this must be balanced with being able to get useful information out of a failed test\.
  * If your test is written in such a way that 10 things are checked all within one test\, then if that test fails you will spend additional time trying to figure out exactly where/how it failed
* Keep this in mind as you design your tests

![](img%5CTesting50.png)



Good Examples

Multiple asserts that are related to minimize testing effort

![](img%5CTesting51.png)



Bad Examples

Tedious test that should be automated \(error prone when executed manually\)

![](img%5CTesting52.png)



We reserve the right to change the content of this presentation without prior notice\. The information contained herein is believed to be accurate as of the date of publication\, however\, B&R makes no warranty\, expressed or implied\, with regards to the products or the documentation contained within this document\. B&R shall not be liable in the event if incidental or consequential damages in connection with or arising from the furnishing\, performance or use of these products\. The software names\, hardware names and trademarks used in this document are registered by the respective companies\.

Copyright © B&R – Subject to change without notice

