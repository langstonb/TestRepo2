# Automation & Build Server

DevOps Package

# Mission Statement

DevOps Package

To significantly  __reduce the barriers to entry __ of DevOps strategies into the day\-to\-day workflow of Automation Studio project development\, in order to  __increase the efficiency\, quality\, and maintainability __ of the resulting applications



# Contents

Automation & Build Server

![](img%5CAutomation%20and%20Build%20Server0.png)

* What is it?
* Why is it important?
* Included Template Files
* How to Implement
  * How to use Jenkins
  * B&R\-Jenkins Helper Library
  * Getting Started
  * Customizing the Jenkinsfile
  * Integration with Bitbucket
* Automated Deployment



# What is it?

Automation & Build Server

# Automation & Build Server

Definition

Automation Server

A build server is an isolated production environment where software projects are compiled and built\.

The code is pulled directly from a source control repository prior to build\.

* An automation server is used to automate tasks and processes\.
* The automation server monitors the source control repo\. As soon as a code change is checked into the repo \(or at a specific time interval\)\, the automation server will automatically trigger the following:
  * Check out the latest version of the code from the source control repo
  * Compile the code on the build server
  * Initiate the automated unit/integration tests
  * Communicate the results \(pass/fail\) to the interested parties via email\, Teams\, Confluence\, etc
  * Initiate automated deployment
  * … and so on
* The automation server is essentially the “puppet master” of the automations within the DevOps process



# Why is it important?

Build & Automation Server

# Benefits

Build & Automation Server

* By building the project and running tests in an isolated production environment\, you will be testing against a collection of known dependencies\. In other words\, you avoid the “it fails for you\, but it works on my PC” situation
* By automating the deployment pipeline with a build server\, developers quickly receive feedback about whether their changes introduced a problem into the system
  * The sooner a problem is identified\, the easier/cheaper it is to fix
  * The build server provides a clear paper trail for what change introduced a problem
* When used in combination with proper version control practices\, the latest version of code will always be in a releasable state
* Since the releases are automated and not manual\, release steps are consistent and no steps are forgotten



# Target Applications

Build & Automation Server

x

* __Any and all __ applications can benefit from the incorporation of a build and automation server
  * Any steps that are triggered automatically are inherently more efficient and reliable than executing the step manually
* These are general software development tools that will give us a strategic advantage over our competitors
* A build and automation server is particularly useful if:
  * You are managing multiple projects
    * The automation server will update all interested parties via email / Teams
    * The build server will automatically generate the PIP in a consistent environment\, which makes machine updates easier because only the changes will get transferred to the target
  * The application has unit tests
    * The automation server will run them automatically and more frequently
    * The build/automation server will allow for a clean slate testing environment
    * The build server triggers all tests\, so you have confidence that your code changes don’t impact other aspects of the code



# Included Template Files

DevOps Package

Automation & Build Server

The only template file provided for this topic is a template Jenkinsfile\.

Further explanation on how to edit this Jenkinsfile according to your situation is provided [later on](slide27.xml)\.

![](img%5CAutomation%20and%20Build%20Server1.png)



# How to Implement

  * How to use Jenkins
  * B&R\-Jenkins Helper Library
  * Getting Started
  * Customizing the Jenkinsfile
  * Integration with Bitbucket

# How to use Jenkins

# Jenkins

Proposed Tool

Jenkins is a very popular\, open\-source tool which provides deployment pipeline functionality

It can be used to automate all sorts of tasks related to building\, testing\, delivering and deploying software

This is the tool that B&R uses for our automation server\, so the rest of this PPT will be focused on Jenkins\. You are free to investigate other options as desired\.

![](img%5CAutomation%20and%20Build%20Server2.png)



# ATL Jenkins Server

Used by All NA Regions

  * B&R North America has a build/automation server running out of our ATL office that you can utilize as long as B&R engineers are involved in your project and have credentials to your source control repository
    * This is convenient because it means you don’t have to build up your own server right away
    * To get started with this option\, contact your B&R NA representative\. Note that this option is not available outside of North America
  * Once B&R is no longer actively involved in the project\, though\, you will need to create your own build/automation server setup
    * B&R does not manage customer automation servers long\-term
  * Alternatively\, you can create your own automation server setup from the get\-go

![](img%5CAutomation%20and%20Build%20Server3.png)



# Multibranch Pipeline

Jenkins Project Type

* There are a few different project types within Jenkins\, but the one we recommend is the  __Multibranch Pipeline__ \.
* A pipeline is a workflow defined in text\-based code within a text file called “Jenkinsfile”
* A Multibranch Pipeline project automatically creates sub\-projects for every branch in the source code repository
  * If a new branch is created and pushed to the repository\, then a new sub\-project in the multibranch pipeline is created and runs for that branch
* The Jenkinsfile is committed to the source control repository\, so the pipeline itself is protected by version control
  * This also means that the developers can freely/directly add steps to the pipeline



# Use Multiple Multibranch Pipelines

Recommendation

* You can configure multiple Jenkins pipelines to run in series
  * Once the first pipeline completes successfully\, the next one automatically starts running\, and so on\.
  * Alternatively\, since the pipelines are separated\, you can run the integration tests \(which typically take longer\) at a lower frequency than the unit tests\. The unit tests could run every time code is committed and pushed\, but the integration test run only every 4 hours\, for example\.

Build\, Unit Tests

Integration Testing

\(longer running tests\)

Release Deployment

Machine Deployment



Recommendation

* We recommend using at least the following 3 distinct multibranch pipelines for AS project development:
  * Multibranch pipeline 1: Builds the project and runs unit tests
  * Multibranch pipeline 2: Runs integration tests
  * Multibranch pipeline 3: Handles the release deployment
* Note: the template Jenkinsfile in this DevOps package is a starter implementation that corresponds to one single pipeline for building the project\, running unit tests\, and release deployment\. Integration testing is not yet included \(this will come in a future update to the DevOps package\)\.

Build\, Unit Tests

Integration Testing

\(longer running tests\)

Release Deployment

Machine Deployment



# B&R-Jenkins Helper Library

Ready\-made Scripts

Readymade Groovy Scripts

* B&R North America has written a helper library that includes a lot of useful functions for interacting with AS projects
* The library contains Groovy scripts\, which are wrappers around Python scripts and general commands
* You don’t need to edit this library at all\, but you will be using it in your Jenkinsfile
  * The functions are described on the next slides as an FYI
* Public link to the library on GitHub: [https://github\.com/br\-automation\-com/BnR\-Jenkins\-Helper\-Library](https://github.com/br-automation-com/BnR-Jenkins-Helper-Library)
  * The Groovy scripts are located within the “vars” folder on the repo
  * The Python scripts that the Groovy scripts utilize are located within the “resources\\scripts” folder on the repo
* These scripts have been tested in AS4\.7 and above\. Prior AS versions may work\, but they are currently untested\.



Add to Jenkins Server

* To utilize this helper library on your Jenkins server\, do the following:
* Go to “Manage Jenkins”
* Select “System”
* Scroll down to the “Global Pipeline Libraries” section\. Click “Add”\. Then:
  * Fill out a Name for the library \(whatever you prefer\)
  * In the “Default Version” field\, type “main”
  * Check the boxes for “Load implicitly”\, “Allow default version to be overridden”\, and “Include @Library changes in job recent changes”
  * Set the Retrieval method to “Modern SCM”
  * Set “Source Code Management” to “GitHub”
  * Fill out the credentials accordingly \(or add new credentials if needed\)
  * In the “Repository HTTPS URL” field\, paste this URL: [https://github\.com/br\-automation\-com/BnR\-Jenkins\-Helper\-Library\.git](https://github.com/br-automation-com/BnR-Jenkins-Helper-Library.git)
  * In the “Library Path” field\, paste the following: \./

![](img%5CAutomation%20and%20Build%20Server4.png)

![](img%5CAutomation%20and%20Build%20Server5.png)



# Version Info Functions

B&R\-Jenkins Helper Library

| Function | Description | Arguments |
| :-: | :-: | :-: |
| Version | Returns full version number based on tag (e.g. 1.2.3.9004)<br /> | workspace |
| ReleaseVersion | Returns Major.Minor.Bugfix style version number<br /> | workspace |
| MajorVersionNumber | Returns just the Major version number | workspace |
| MinorVersionNumber | Returns just the Minor version number | workspace |
| BugFixVersionNumber | Returns just the bug version number | workspace |

The workspace is where Jenkins checks out the project from the repo and runs the pipeline\.

To reference the workspace in the Jenkinsfile\, use the readymade environment variable "$\{WORKSPACE\}"



# Git Info Functions

B&R\-Jenkins Helper Library

| Function | Description | Arguments |
| :-: | :-: | :-: |
| BranchName | Returns the name of the git branch | workspace |
| Tag | Returns the last tag in the branch | workspace |
| IsReleaseCandidate | Returns true if the branch is in the release/* branch | workspace |
| IsReleaseBranch | Returns true if branch is master or main | workspace |

The workspace is where Jenkins checks out the project from the repo and runs the pipeline\.

To reference the workspace in the Jenkinsfile\, use the readymade environment variable "$\{WORKSPACE\}"



# AR Helper Functions

B&R\-Jenkins Helper Library

| Function | Description | Arguments |
| :-: | :-: | :-: |
| BuildASProject | Builds an Automation Studio Project | project – path within the workspace to the project (the folder containing the .apj file). For example: "$WORKSPACE\\TestProject"<br />configuration – configuration name in the AS project<br />max_warnings – the maximum number or build warnings that are allowed in order to consider the build a success. Set this to -1 to accept infinite warnings<br />buildpip – whether to build the PIP or not |
| BuildARsimStructure | Creates the ARsim structure | project – path within the workspace to the project (the folder containing the .apj file). For example: "$WORKSPACE\\TestProject"<br />configuration – configuration name in the AS project |



# Unit Test Functions

B&R\-Jenkins Helper Library

| Function | Description | Arguments |
| :-: | :-: | :-: |
| RunArUnitTests | Runs unit test configuration in ArSim | tests – the name of the unit tests to run. Use “all” to run all tests<br />configuration – configuration name in the AS project that contains the unit tests<br />project – path within the workspace to the project (the folder containing the .apj file). For example: "$WORKSPACE\\TestProject“ |
| ProcessArTestResults | Process test results xml files | N/A |



# Information Sharing Functions

B&R\-Jenkins Helper Library

| Function | Description | Arguments |
| :-: | :-: | :-: |
| UploadToGitHub | Uploads build artifacts to a GitHub repository | version – version number of the artifact<br />organization – repo organization name<br />name – repo name<br />file – filename of the artifact to upload |
| SendNotifications | Sends an email to team members | buildStatus – the status/result of the most recent build of the pipeline<br />recipients – list of email addresses to send the email to |



# Getting Started

Note: If you are utilizing the B&R Jenkins server initially\, then you can skip the steps in this slide

# System Requirements

Build and Automation Server

* If you are setting up your own build/automation server\, note the following system requirements:
* Hardware requirements
  * 12 GB of RAM
  * 10 GB of drive space \(>50 GB recommended\)
* Software requirements
  * Windows 10
  * Automation Studio 4\.7 or above \(version must match the project\)
    * Plus all required upgrades for the project \(manually installed on server\)
    * Note: supporting scripts have been tested in AS4\.7 and above\. Prior versions may work\, but have not been checked
  * Python ≥ 3\.9
    * Required for automated build scripts
  * Jenkins
  * Java Development Kit



Note: If you are utilizing the B&R Jenkins server initially\, then you can skip the steps in this slide

# Downloads and Installation

Build and Automation Server

* [Jenkins Download](https://www.jenkins.io/download/)
* [Java Development Kit Download](https://adoptium.net/temurin/releases/?version=11)
* [Python Download](https://www.python.org/downloads/)
* Installation instructions for Jenkins and the JDK are located [here](https://www.jenkins.io/doc/book/installing/windows/)\.
  * Please review the video for full instructions on how to install the JDK\, Jenkins\, and make assorted configuration changes after install\.
* We recommend installing Jenkins on a server or dedicated PC
* We recommend installing Jenkins with the “recommended plugins” option
  * And manually add the “Office 365 Connector” plugin
  * Configure Extended E\-mail Notification plugin
* Python requirements
  * pip install requests junitparser GitPython

![](img%5CAutomation%20and%20Build%20Server6.png)



# Creating Jenkins Agent Docker Container

# Jenkins Agent

Build and Automation Server

![](img%5CAutomation%20and%20Build%20Server7.png)

Create a new node to run the Jenkins agent

Goto “Manage Jenkins”



Build and Automation Server

![](img%5CAutomation%20and%20Build%20Server8.png)

Create a new node to run the Jenkins agent

Goto “Manage Jenkins”

Select “Nodes” under the System Configuration



Build and Automation Server

Create a new node to run the Jenkins agent

Goto “Manage Jenkins”

Select “Nodes” under the System Configuration

Click the “New Node” button

![](img%5CAutomation%20and%20Build%20Server9.png)



Build and Automation Server

![](img%5CAutomation%20and%20Build%20Server10.png)

Create a new node to run the Jenkins agent

Goto “Manage Jenkins”

Select “Nodes” under the System Configuration

Click the “New Node” button

Define the name of your node and select “Permanent Agent”

Click “Create”



Build and Automation Server

Create a new node to run the Jenkins agent

Goto “Manage Jenkins”

Select “Nodes” under the System Configuration

Click the “New Node” button

Define the name of your node and select “Permanent Agent”

Click “Create”

Define “Remote root directory”

![](img%5CAutomation%20and%20Build%20Server11.png)



Build and Automation Server

Create a new node to run the Jenkins agent

Goto “Manage Jenkins”

Select “Nodes” under the System Configuration

Click the “New Node” button

Define the name of your node and select “Permanent Agent”

Click “Create”

Define “Remote root directory”

Define labels based on Automation Studio Version

![](img%5CAutomation%20and%20Build%20Server12.png)



Build and Automation Server

Create a new node to run the Jenkins agent

Goto “Manage Jenkins”

Select “Nodes” under the System Configuration

Click the “New Node” button

Define the name of your node and select “Permanent Agent”

Click “Create”

Define “Remote root directory”

Define labels based on Automation Studio Version

Change “Usage” to “Only build jobs with label expressions matching this mode”

![](img%5CAutomation%20and%20Build%20Server13.png)



Build and Automation Server

![](img%5CAutomation%20and%20Build%20Server14.png)

Create a new node to run the Jenkins agent

Goto “Manage Jenkins”

Select “Nodes” under the System Configuration

Click the “New Node” button

Define the name of your node and select “Permanent Agent”

Click “Create”

Define “Remote root directory”

Define labels based on Automation Studio Version

Change “Usage” to “Only build jobs with label expressions matching this mode”

Change “Launch method” to “Launch agent by connecting it to the controller”

Check “Use WebSocket”



Build and Automation Server

![](img%5CAutomation%20and%20Build%20Server15.png)

Create a new node to run the Jenkins agent

Goto “Manage Jenkins”

Select “Nodes” under the System Configuration

Click the “New Node” button

Define the name of your node and select “Permanent Agent”

Click “Create”

Define “Remote root directory”

Define labels based on Automation Studio Version

Change “Usage” to “Only build jobs with label expressions matching this mode”

Change “Launch method” to “Launch agent by connecting it to the controller”

Check “Use WebSocket”

Click “Save”



Build and Automation Server

Create a new node to run the Jenkins agent

Goto “Manage Jenkins”

Select “Nodes” under the System Configuration

Click the “New Node” button

Define the name of your node and select “Permanent Agent”

Click “Create”

Define “Remote root directory”

Define labels based on Automation Studio Version

Change “Usage” to “Only build jobs with label expressions matching this mode”

Change “Launch method” to “Launch agent by connecting it to the controller”

Check “Use WebSocket”

Click “Save”

Copy the secret provided

![](img%5CAutomation%20and%20Build%20Server16.png)



# Docker Build

Build and Automation Server

![](img%5CAutomation%20and%20Build%20Server17.png)

Create a Docker container for the agent

Open the Dockerfile in a text editor



Build and Automation Server

Create a Docker container for the agent

Open the Dockerfile in a text editor

Adjust the JENKINS\_URL for your configuration

![](img%5CAutomation%20and%20Build%20Server18.png)



Build and Automation Server

Create a Docker container for the agent

Open the Dockerfile in a text editor

Adjust the JENKINS\_URL for your configuration

Add the Jenkins secret from the node creation to JENKINS\_SECRET

Adjust the JENKINS\_AGENT\_NAME with the name of the node

![](img%5CAutomation%20and%20Build%20Server19.png)



Build and Automation Server

Create a Docker container for the agent

Open the Dockerfile in a text editor

Adjust the JENKINS\_URL for your configuration

Add the Jenkins secret from the node creation to JENKINS\_SECRET

Adjust the JENKINS\_AGENT\_NAME with the name of the node

Create the Docker image

![](img%5CAutomation%20and%20Build%20Server20.png)



# Create Jenkins project

Note: If you are utilizing the B&R Jenkins server initially\, then you can skip the steps in this slide

# Create a Multibranch Pipeline

Jenkins

* Open the Jenkins server web browser
* From the Dashboard\, click “New Item” in the top left and select “Multibranch Pipeline”
* Fill out the configuration for this new pipeline\. Required changes:
  * Add a Branch Source
    * Fill out the corresponding fields\, which vary depending on the source type
  * Set the Build Configuration Mode to “by Jenkinsfile” and update the script path to where you want this file to live in your repo
    * This file is where you will define your pipeline
  * Add the “Clean before checkout” option to the repository
* Paste the provided template “Jenkinsfile” to the location you specified in step 3b
* Open the “Jenkinsfile” in a text editor

![](img%5CAutomation%20and%20Build%20Server21.png)



---

Getting Started section

# Overview of the Jenkinsfile Template

Getting Started

The provided Jenkinsfile template accomplishes the following tasks:

Builds the AS project

Runs the unit tests

Creates an ARsim structure and PIP

Uploads the ARsim structure and PIP to GitHub\, and sends them to an MS Teams channel via a chat message

Sends an email with the results of the build



# Customizing the Jenkinsfile

  * Variables
  * Agent
  * Environment
  * Options
  * Stages
  * Post

Starting from the template

* The provided template Jenkinsfile is a starting point for your pipeline definition
* There are a few things in this file that must be adjusted for it to run properly for your system
* The following slides identify the purpose of each section in the Jenkinsfile and any changes you must make\. There are 6 main sections in the Jenkinsfile pipeline:
  * _Variable Definitions_  – Defines global variables
  * _Agent_  – Defines where the pipeline will run within the Jenkins environment
  * _Environment_  – Defines global environment variables
  * _Options_  – Configures options
  * _Stages_  – Defines the steps in the pipeline\. If a stage fails\, subsequent stages don’t run
  * _Post_  – Always runs at the end of the pipeline\, even if a stage fails



  * __Variables__
  * Agent
  * __Environment__
  * Options
  * Stages
  * Post

# Difference between Variables and Environment Variables

Additional Context

Variables

Defined outside the pipeline\, at the top of the file

All variables are global

Environment Variables

Defined within an environment\{\} section\, either at the top level of the pipeline \(for pipeline global environment variable declarations\) or within a stage of the pipeline \(for stage local declarations\)

Global environment variables can also be defined in the configuration of Jenkins\. In this case\, the variables are accessible to all pipelines

There are also some built\-in environment variables that can be used throughout any Jenkinsfile \(analogous to System Variables in mapp View\)\. A full list of predefined and readily available environment variables in Jenkins is available [here](https://www.jenkins.io/doc/book/pipeline/jenkinsfile/#using-environment-variables)\.

The built\-in workspace environment variable \($\{WORKSPACE\}\) is not available until the pipeline starts running\. Therefore\, if the variable you are creating needs to reference the workspace\, you must declare it as an environment variable\. In our template file\, this is why PROJECT\_DIR and RELEASE\_VERSION are declared as environment variables\.



  * __Variables__
  * Agent
  * Environment
  * Options
  * Stages
  * Post

# Variables

Customizing the Jenkinsfile

Starting at the top of the Jenkinsfile\, we will begin by adjusting the global variables\. The following table describes each variable\. Adjust the values accordingly:

| Variable Name | Description |
| :-: | :-: |
| TEAMS_CHANNEL_URL | Teams channel webhook URL where messages about the pipeline status will automatically be sent. For more details on how to define this, refer to the “Options” section.  |
| CONFIG_NAME | Name of the configuration in the AS project that you are running through the pipeline |
| UNIT_TEST_CONFIG_NAME | Name of the unit test configuration in the AS project |
| REPO_NAME | Name of the GitHub repository. Only required if you plan to upload files to GitHub.  |
| REPO_ORGANIZATION | Name of the GitHub organization. Only required if you plan to upload files to GitHub.  |
| EMAIL_LIST | List of email addresses that you want to send the results to, each separated by a semicolon |



  * Variables
  * __Agent__
  * Environment
  * Options
  * Stages
  * Post

# Agent

Customizing the Jenkinsfile

* Edit the “agent” line accordingly\.
  * If you are utilizing the B&R Jenkins server to start\, then identify the docker container your pipeline will run in\. This simply depends on the AS version of your project
    * Example: AS\_412
  * If you have built your own Jenkins server\, then specify the [agent](https://www.jenkins.io/doc/book/using/using-agents/) accordingly\.

![](img%5CAutomation%20and%20Build%20Server22.png)



  * Variables
  * Agent
  * __Environment__
  * Options
  * Stages
  * Post

# Environment

Customizing the Jenkinsfile

The following table describes each environment variable\. Adjust the values accordingly:

| Variable Name | Description |
| :-: | :-: |
| PROJECT_DIR | Specify the path within the repository to the AS project (the folder containing the .apj file). <br />Use \\ for folder separation.<br />Example: PROJECT_DIR = "$WORKSPACE\\TestProject“<br />If the project is stored in the root directory, then leave it defined as PROJECT_DIR = "$WORKSPACE" |
| RELEASE_VERSION | Holds the version number of the code in the repo. No changes required.  |



  * Variables
  * Agent
  * Environment
  * __Options__
  * Stages
  * Post

# Options

Customizing the Jenkinsfile

![](img%5CAutomation%20and%20Build%20Server23.png)

* The “options” section sets up a webhook to an MS Teams channel so that you can automatically send information to that channel\. This includes:
  * Updates on when the pipeline has started / stopped
  * Whether the pipeline succeeded
  * The output files of the pipeline \(by default in our template\, the output files are the zipped up ARsim structure and PIP\)
* To establish this connection\, you need to obtain your Teams channel webhook URL \(see next slides\) and paste it in the value for the TEAMS\_CHANNEL\_URL variable



  * Variables
  * Agent
  * Environment
  * __Options__
  * Stages
  * Post

# Obtaining the Webhook URL

Microsoft Teams Connection

Navigate to the channel in the Team that you want to establish the connection to

Click the “…” button

Click “Connectors”

![](img%5CAutomation%20and%20Build%20Server24.png)



  * Variables
  * Agent
  * Environment
  * __Options__
  * Stages
  * Post

Microsoft Teams Connection

Navigate to the channel in the Team that you want to establish the connection to

Click the “…” button

Click “Connectors”

Click “Configure” for “Incoming Webhook”

![](img%5CAutomation%20and%20Build%20Server25.png)



  * Variables
  * Agent
  * Environment
  * __Options__
  * Stages
  * Post

Microsoft Teams Connection

![](img%5CAutomation%20and%20Build%20Server26.png)

Navigate to the channel in the Team that you want to establish the connection to

Click the “…” button

Click “Connectors”

Click “Configure” for “Incoming Webhook”

Give your webhook a name and click “Create”



  * Variables
  * Agent
  * Environment
  * __Options__
  * Stages
  * Post

Microsoft Teams Connection

![](img%5CAutomation%20and%20Build%20Server27.png)

Navigate to the channel in the Team that you want to establish the connection to

Click the “…” button

Click “Connectors”

Click “Configure” for “Incoming Webhook”

Give your webhook a name and click “Create”

Afterwards\, the URL you need will be populated in the field at the bottom\. Copy this link and paste it at the top of the Jenkinsfile as the value of the TEAMS\_CHANNEL\_URL variable



  * Variables
  * Agent
  * Environment
  * Options
  * __Stages__
  * Post

  * Update Tags
  * Build AS Project
  * Unit Tests
  * Deploy

# Stages

Customizing the Jenkinsfile

* The next section in the pipeline is the stages\.
  * This is where you define the actions that the build server will perform\.
  * This is the “meat and potatoes” of the pipeline\.
* There are 4 stages set up in the template Jenkinsfile\, which we will now go through one by one:
  * Update Tags
  * Build AS Project
  * Unit Tests
  * Deploy



  * Variables
  * Agent
  * Environment
  * Options
  * __Stages__
  * Post

  * __Update Tags__
  * Build AS Project
  * Unit Tests
  * Deploy

# Stage: Update Tags

Customizing the Jenkinsfile

* This stage force\-pulls the tags in the repository
  * Note that therefore\, at least one tag must exist in the repo
* This information will be used later to create a version number
* No changes necessary

![](img%5CAutomation%20and%20Build%20Server28.png)



  * Variables
  * Agent
  * Environment
  * Options
  * __Stages__
  * Post

  * Update Tags
  * __Build AS Project__
  * Unit Tests
  * Deploy

# Stage: Build AS Project

Customizing the Jenkinsfile

This stage builds the AS project

A value of \-1 for “max\_warnings” means you can have infinite warnings\. If you optionally specify a positive value here\, the stage will fail if the number of build warnings exceeds this value\.

![](img%5CAutomation%20and%20Build%20Server29.png)



---

What if you want to run your pipeline for multiple configurations in the project – how would we do this? 
You would just copy/paste the lines within each Step. So here, copy/paste the BuildASProject line for the additional config. Set this up with them during the initial meeting


  * Variables
  * Agent
  * Environment
  * Options
  * __Stages__
  * Post

  * Update Tags
  * Build AS Project
  * __Unit Tests__
  * Deploy

# Stage: Unit Tests

Customizing the Jenkinsfile

This stage runs the automated unit tests

If the pipeline gets stuck on a unit test for longer than 15 minutes\, the tests will fail\. Optionally adjust this timeout value as desired\.

![](img%5CAutomation%20and%20Build%20Server30.png)



  * Variables
  * Agent
  * Environment
  * Options
  * __Stages__
  * Post

  * Update Tags
  * Build AS Project
  * Unit Tests
  * __Deploy__

# Stage: Deploy

Customizing the Jenkinsfile

The template separates the deploy stage between release branches and feature/develop branches

Therefore\, you can trigger different actions depending on what branch you pushed to

By default\, both stages create the ARsim structure and Project Installation Package

If you want to perform another action in either stage\, add it accordingly

![](img%5CAutomation%20and%20Build%20Server31.png)



  * Variables
  * Agent
  * Environment
  * Options
  * Stages
  * __Post__

  * Always
  * Success
  * Unstable

# Post

Customizing the Jenkinsfile

* The code within Post will always run\, even if a stage in the pipeline fails
* Within Post\, there are 3 subsections:
  * __Always__  – runs in every single post processing
  * __Success__  – runs if all unit tests pass
  * __Unstable__  – runs if any of the unit tests fail\. This is classified as “unstable” rather than a failure because the pipeline itself completed\, but the tests did not pass\.



  * Variables
  * Agent
  * Environment
  * Options
  * Stages
  * __Post__

  * __Always__
  * Success
  * Unstable

# Post: Always

Customizing the Jenkinsfile

  * The “Always” post script converts the B&R Unit test results into a data format that Jenkins can understand what passed/failed
  * Archives the ARsim structure and PIP so that they can be used in subsequent pipelines or uploaded to GitHub/Teams
  * Sends an email with the build status to the EMAIL\_LIST recipients
  * The PIP that gets automatically generated uses the following installation settings:
    * Consistent installation
    * Allow updates without data loss
    * Keep PV values
    * Ignore version
    * Always install



  * Variables
  * Agent
  * Environment
  * Options
  * Stages
  * __Post__

  * __Always__
  * Success
  * Unstable

# Example of a Successful Build Email Notification

All Tests Passed

![](img%5CAutomation%20and%20Build%20Server32.png)

![](img%5CAutomation%20and%20Build%20Server33.png)



  * Variables
  * Agent
  * Environment
  * Options
  * Stages
  * __Post__

  * __Always__
  * Success
  * Unstable

# Example of an Unstable Build Email Notification

Some Tests Failed

![](img%5CAutomation%20and%20Build%20Server34.png)

![](img%5CAutomation%20and%20Build%20Server35.png)



  * Variables
  * Agent
  * Environment
  * Options
  * Stages
  * __Post__

  * Always
  * __Success__
  * __Unstable__

# Post: Success, Unstable

Customizing the Jenkinsfile

  * Both the “Success” and “Unstable” post scripts do the following:
    * Upload the artifacts to GitHub
    * Send a message to the Teams channel with the status and artifact download links
  * The only differences between these post scripts are:
    * The color scheme \(green for success\, yellow for unstable\)
    * The text that gets used for the Teams message \(“Build Success” vs “Build Unstable”\)\.



  * Variables
  * Agent
  * Environment
  * Options
  * Stages
  * __Post__

  * Always
  * __Success__
  * __Unstable__

# Example of MS Teams Messages

Success vs Unstable

![](img%5CAutomation%20and%20Build%20Server36.png)

![](img%5CAutomation%20and%20Build%20Server37.png)



  * Variables
  * Agent
  * Environment
  * Options
  * Stages
  * __Post__

  * Always
  * __Success__
  * __Unstable__

# Post: Success, Unstable

Customizing the Jenkinsfile

  * Required steps:
  * Comment/uncomment the upload lines depending on whether you want to upload the artifacts to GitHub
  * If you do choose to upload\, make sure you have edited the REPO\_NAME and REPO\_ORGANIZATION variables at the top of the Jenkinsfile accordingly

![](img%5CAutomation%20and%20Build%20Server38.png)



# Integration with Bitbucket

# Integrate Jenkins with Bitbucket

How\-to

![](img%5CAutomation%20and%20Build%20Server39.png)

From the Bitbucket project\, click on your user icon and select “Manage account”

Select “HTTP access token” in the menu on the left

Click “Create token”

![](img%5CAutomation%20and%20Build%20Server40.png)



How\-to

![](img%5CAutomation%20and%20Build%20Server41.png)

Add a token name

Set the Permissions to “Repository read”

Click “Create”



How\-to

Make sure to copy the generated token as you will not be able view this again\.

![](img%5CAutomation%20and%20Build%20Server42.png)



How\-to

Create new project in Jenkins

Enter name of project

Select multibranch pipeline



How\-to

Add Credential

Select project name

Add source

Select Bitbucket

![](img%5CAutomation%20and%20Build%20Server43.png)

![](img%5CAutomation%20and%20Build%20Server44.png)



How\-to

![](img%5CAutomation%20and%20Build%20Server45.png)

Change “Kind” to “Username with password”

Paste HTTP access token created from Bitbucket

Give unique ID



How\-to

Select new Credential

Set the “Owner” to the Bitbucket project key \(4 letter identifier\)

Once Owner is entered\, the Repository Name should show up in list



How\-to

Then Add “Advanced clone behaviors”

And ensure that “Fetch tags” is checked

![](img%5CAutomation%20and%20Build%20Server46.png)

![](img%5CAutomation%20and%20Build%20Server47.png)



How\-to

After saving\, the repositories will be scanned

![](img%5CAutomation%20and%20Build%20Server48.png)



# Automated Deployment

DevOps Package

* Recommendations on automated deployment will be added in a future revision of the B&R DevOps package
* For an immediate solution\, consider [Shuv](https://loupe.team/story/introducing-shuv/)\*
  * Shuv handles many aspects of the CI/CD process for you\, in addition to automated deployment
  * Further details on next slide

![](img%5CAutomation%20and%20Build%20Server49.png)

\* Note that there is a cost to use Shuv \(it is not free\)



![](img%5CAutomation%20and%20Build%20Server50.png)

![](img%5CAutomation%20and%20Build%20Server51.png)

Tag event \+ checkout

Manages CI/CD pipelines for your Automation Studio projects and B&R PLCs

Automated pipelines trigger on Git events

Builds simulator and physical PIPs

Runs unit tests and integration tests against the simulator

Integrates with Git to keep track of code versions

Delivers OTA software updates to PLCs that are connected to Shuv via MQTTS



We reserve the right to change the content of this presentation without prior notice\. The information contained herein is believed to be accurate as of the date of publication\, however\, B&R makes no warranty\, expressed or implied\, with regards to the products or the documentation contained within this document\. B&R shall not be liable in the event if incidental or consequential damages in connection with or arising from the furnishing\, performance or use of these products\. The software names\, hardware names and trademarks used in this document are registered by the respective companies\.

Copyright © B&R – Subject to change without notice

