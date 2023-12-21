layout: page
title: Automation and Build Server
permalink: /AutomationAndBuildServer


B&R Internal

# Automation & Build Server

DevOps Package

# Mission Statement

DevOps Package

To significantly  __reduce the barriers to entry __ of DevOps strategies into the day\-to\-day workflow of B&R applications engineers in order to  __increase the efficiency\, quality\, and maintainability __ of AS project development



# Contents

Automation & Build Server

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal0.png)

* What is it?
* Why is it important?
* Included Template Files
* How to Implement
  * How to use Jenkins
  * B&R\-Jenkins Helper Library
  * Getting Started
  * Customizing the Jenkinsfile
  * Integration with Bitbucket



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

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal1.png)



# How to Implement

  * How to use Jenkins
  * B&R\-Jenkins Helper Library
  * Getting Started
  * Customizing the Jenkinsfile
  * Integration with Bitbucket

# How to use Jenkins

# Jenkins

Proposed Tool for B&R Internal

Jenkins is a very popular\, open\-source tool which provides deployment pipeline functionality

It can be used to automate all sorts of tasks related to building\, testing\, delivering and deploying software

This is what we will use for our build servers in B&R NA

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal2.png)



# ATL Jenkins Server

Used by All NA Regions

  * Jenkins is installed in a VM on the Atlanta server
  * All North America regions and territories will use this build server
    * If you work out of a regional office and want to install Jenkins locally instead\, contact Brittany and Wes for the necessary steps
  * This Jenkins server is accessible via the following link:
    * [http://brusatlavbuild1\.br\-automation\.com:8080/](http://brusatlavbuild1.br-automation.com:8080/)
    * Login credentials are the same as your Windows login
  * Docker containers are installed on the VM for AS4\.10– 4\.12\, to enable simultaneous AS builds \(e\.g\. if two build chains happen to run at the same time\)
    * If you are using <AS4\.10\, please let us know and we will install another docker container accordingly
    * Builds will queue if they are triggered at the same time

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal3.png)



Used by All NA Regions

  * Although the Jenkins server is installed on the internal B&R Atlanta server\, it can still be used with customer projects that we are involved in\. As long as someone on our team has credentials to access the customer repository\, then our internal build server can interact with it\.
  * Note\, however\, that we are not set up to manage the customer’s build/automation server after the project has been completed\. Therefore\, at that time they either need to set up their own Jenkins server\, or they lose the Jenkins server functionality\. The customer\-facing version of this DevOps package will provide the steps for customers to set up their own server\.

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal4.png)



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

ATL Jenkins Server

Readymade Groovy Scripts

* The ATL Jenkins server uses a helper library that has a lot of useful functions for interacting with AS projects
* The library contains Groovy scripts\, which are wrappers around Python scripts and general commands
* You don’t need to edit this library at all\, but you will be using it in your Jenkinsfile
* Public link to the library on GitHub: [https://github\.com/br\-automation\-com/BnR\-Jenkins\-Helper\-Library](https://github.com/br-automation-com/BnR-Jenkins-Helper-Library)
  * The Groovy scripts are located within the “vars” folder on the repo
  * The Python scripts that the Groovy scripts utilize are located within the “resources\\scripts” folder on the repo
* These scripts have been tested in AS4\.7 and above\. Prior AS versions may work\, but they are currently untested\.
* The available functions are described on the next slides and are provided here as an FYI\. To skip forward to the steps for editing your Jenkinsfile\, click [here](slide26.xml)\.



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
| UploadToConfluence | Uploads build artifacts to a Confluence page | projectId – 4-character project identifier<br />pageName – name of the page in Confluence to upload to<br />file – filename of the artifact to upload<br />token – user credentials token for access rights |
| SendNotifications | Sends an email to team members | buildStatus – the status/result of the most recent build of the pipeline<br />recipients – list of email addresses to send the email to |



# Getting Started

# Create a Multibranch Pipeline

Submit Request

When you are ready to create a pipeline\, send an email to Brittany and Wes\. We will then coordinate a meeting to create your pipeline together and go over a few additional details

Note that all AS projects that you intend to run through a pipeline must be configured for ARsim in order for the full pipeline to be able to run \(particularly\, the automated tests\)

Once the pipeline is in place\, open the template Jenkinsfile in a text editor to begin making your customizations



---

Notes for Brittany/Wes: 
Remember to ask them their AS version. If less than 4.7, we need to test the scripts. If 4.7 or 4.8, we need to install on the build server (it only has 4.9-4.12 right now).
PIP installation settings – these ok?

What if you want to run your pipeline for multiple configurations in the project – how would we do this? 
You would just copy/paste the lines within each Step. See “Stages” section. Help them through this in the first meeting. 



# Overview of the Jenkinsfile Template

DevOps Package

The provided Jenkinsfile template accomplishes the following tasks:

Builds the AS project

Runs the unit tests

Creates an ARsim structure and PIP

Uploads the ARsim structure and PIP to GitHub or Confluence\, and sends them to an MS Teams channel via a chat message

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
| CONFLUENCE_CRED_ID | ID of the Personal Access Token for Confluence. Only required if you plan to upload files to Confluence.<br />For more details, refer to the “Post” section.   |
| CONFLUENCE_PROJECT_ID | Name of the confluence page. Only required if you plan to upload files to Confluence. |
| CONFLUENCE_PAGE_NAME | Name of the confluence page. Only required if you plan to upload files to Confluence. |
| EMAIL_LIST | List of email addresses that you want to send the results to, each separated by a semicolon |



  * Variables
  * __Agent__
  * Environment
  * Options
  * Stages
  * Post

# Agent

Customizing the Jenkinsfile

* Edit the “agent” line to identify the docker container your pipeline will run in\. This simply depends on the AS version of your project
  * Example: AS\_412

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal5.png)



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

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal6.png)

* The “options” section sets up a webhook to a Teams channel so that you can automatically send information to that channel\. This includes:
  * Updates on when the pipeline has started / stopped
  * Whether the pipeline succeeded
  * The output files of the pipeline \(By default in our template\, the output files are the zipped up ARsim structure and PIP\)
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

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal7.png)



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

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal8.png)



  * Variables
  * Agent
  * Environment
  * __Options__
  * Stages
  * Post

Microsoft Teams Connection

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal9.png)

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

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal10.png)

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

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal11.png)



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

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal12.png)



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

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal13.png)



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

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal14.png)



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
  * Archives the ARsim structure and PIP so that they can be used in subsequent pipelines or uploaded to GitHub/Confluence/Teams
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

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal15.png)

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal16.png)



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

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal17.png)

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal18.png)



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
    * Upload the artifacts to your destination of choice \(GitHub\, Confluence\, or both\)
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

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal19.png)

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal20.png)



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
  * Comment/uncomment the upload lines according to your selected destination \(GitHub/Confluence\)

    * If GitHub:
  * Edit the REPO\_NAME and REPO\_ORGANIZATION variables at the top of the Jenkinsfile accordingly

  * If Confluence:
* Create a Personal Access Token \(PAT\) in Confluence\. Steps are provided [here](https://confluence.atlassian.com/enterprise/using-personal-access-tokens-1026032365.html) in section “Creating PATs in the application”
* Add the PAT to the Jenkins project \(detailed steps on subsequent slides\)
* Edit the CONFLUENCE\_CRED\_ID variable value at the top of the Jenkinsfile to equal the ID of your PAT from step 2\.

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal21.png)

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal22.png)



  * Variables
  * Agent
  * Environment
  * Options
  * Stages
  * __Post__

  * Always
  * __Success__
  * __Unstable__

# Add PAT to Jenkins Project

For Uploading Files to Confluence

  * To add a Personal Access Token \(PAT\) from Confluence to a Jenkins project:
* The output of the PAT in Confluence is a long text string\. In the Jenkins project\, go to Configure\.

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal23.png)



  * Variables
  * Agent
  * Environment
  * Options
  * Stages
  * __Post__

  * Always
  * __Success__
  * __Unstable__

For Uploading Files to Confluence

  * To add a Personal Access Token \(PAT\) from Confluence to a Jenkins project:
* Scroll down to the “Properties” section at the bottom\. Beneath the “Registry Credentials” dropdown\, click the “Add” button\.

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal24.png)



  * Variables
  * Agent
  * Environment
  * Options
  * Stages
  * __Post__

  * Always
  * __Success__
  * __Unstable__

For Uploading Files to Confluence

  * To add a Personal Access Token \(PAT\) from Confluence to a Jenkins project:
* Select your Jenkins project name from the dropdown\.

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal25.png)



  * Variables
  * Agent
  * Environment
  * Options
  * Stages
  * __Post__

  * Always
  * __Success__
  * __Unstable__

For Uploading Files to Confluence

  * To add a Personal Access Token \(PAT\) from Confluence to a Jenkins project:
* Change the “Kind” to “secret text”\. Paste your long PAT string in the “Secret” field\. Give the credentials a meaningful ID\. Remember the ID \(this is what you need to specify in the Jenkinsfile\)\. Click “Add” at the bottom of the window to add your Confluence PAT to your Jenkins project\.

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal26.png)



# Integration with Bitbucket

# Integrate Jenkins with Bitbucket

How\-to

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal27.png)

From the Bitbucket project\, click on your user icon and select “Manage account”

Select “HTTP access token” in the menu on the left

Click “Create token”

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal28.png)



How\-to

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal29.png)

Add a token name

Set the Permissions to “Repository read”

Click “Create”



How\-to

Make sure to copy the generated token as you will not be able view this again\.

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal30.png)



How\-to

Create new project in Jenkins

Enter name of project

Select multibranch pipeline



How\-to

Add Credential

Select project name

Add source

Select Bitbucket

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal31.png)

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal32.png)



How\-to

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal33.png)

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

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal34.png)

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal35.png)



How\-to

After saving\, the repositories will be scanned

![](img%5CAutomation%20and%20Build%20Server%20-%20Internal36.png)



# Measurables

# Automation and Build Server

Measurables

| Measurable | Purely B&R | Mix, B&R Primary | Mix, Customer Primary |
| :-: | :-: | :-: | :-: |
| A Jenkins pipeline is in place, which at the very least runs your unit tests | Required | Required | Maybe |



Materials prepared by Brittany Langston & Wesley Buchanan

