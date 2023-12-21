# Project Management

DevOps Package

# Mission Statement

DevOps Package

To significantly  __reduce the barriers to entry __ of DevOps strategies into the day\-to\-day workflow of Automation Studio project development\, in order to  __increase the efficiency\, quality\, and maintainability __ of the resulting applications



# Contents

Project Management

* What is it?
* Why is it important?
* How to Implement:

![](img%5CProject%20Management0.png)

  * Project planning
  * Jira
  * Confluence
  * Bitbucket
  * Open\-source licensing



# What is it, &Why is it important?

Project Management

# Agile Workflow

What is it?

The following article provides a thorough overview of Agile project management\, and how it compares to the traditional waterfall approach

Agile strategies are recommended

Agile Project Management

![](img%5CProject%20Management1.png)



# Project Management Topics

Overview

For effective project management\, the following topics must be addressed:

Content Collaboration – to store information

Issue Tracking – to manage tasks

Hosting Service – to manage Git repositories

The subsequent slides identify the tools we use at B&R\, which will therefore be referenced throughout the rest of the DevOps package\.



# Content Collaboration

Project Management

A content collaboration tool is needed to store information such as meeting notes\, brainstorming\, project planning\, documentation\, etc

At B&R\, we use Confluence\. Therefore\, the examples shown in this DevOps package are all tailored towards Confluence\.

Alternate options that you can also consider include Microsoft Sharepoint\, Notion\, Guru\, Stack Overflow for Teams\, and so on\.

![](img%5CProject%20Management2.png)



# Issue Tracking

Project Management

An issue tracking system is needed to manage the tasks associated with a project via the agile workflow\.

At B&R\, we use Jira\. Therefore\, the examples shown in this DevOps package are all tailored towards Jira\.

Alternate options that you can consider include Asana\, monday\.com\, Microsoft Azure Boards\, and so on\.

![](img%5CProject%20Management3.png)



# Hosting Service

Project Management

A hosting services is needed to manage your Git repositories\.

At B&R\, we use Bitbucket and GitHub\. Therefore\, the examples in this DevOps package will be tailored to either Bitbucket or GitHub\.

Alternate options that you can consider include Microsoft Azure Repos\, GitLab\, Amazon AWS CodeCommit\, and so on\.

![](img%5CProject%20Management4.png)

![](img%5CProject%20Management5.png)

![](img%5CProject%20Management6.png)



# How to Implement

  * Project Planning
  * Jira
  * Confluence
  * Bitbucket
  * Open\-Source Licensing

# Project Planning

# Define Personnel Resources

Project Planning

Prior to software development\, identify the individuals that will be responsible for various roles\. The following list describes the baseline/minimum roles that must be defined\. Additional roles may be required depending on the application complexity\. Note that one person can hold more than one role\.

| Role | Description |
| :-: | :-: |
| Project Manager | Responsible for the successful execution the project. Primary decision maker. Handles project version definition.  |
| Application Architect | Responsible for designing the application. Typically, a senior engineer.  |
| Engineer | Responsible for developing the application. Can be any engineer.  |
| Test Manager* | Defines the tests |
| Test Developer* | Writes the automated tests |
| Manual Tester* | Executes the manual tests. Does not analyze the results of any subjective tests (if applicable) |
| Manual Test Approver* | Analyzes the outcome of the subjective manual tests (if applicable) |

\* Refer also to the Testing PPT

within this DevOps package



# Project Overview Diagram

Created in Tandem with the Machine Specification

Prior to any software development\, create a  __block diagram / class diagram / flow chart __ that represents each control element of the machine

Once you have this diagram\, each block will become an  __epic__  within your Jira project\.

Then the more granular requirements for that control element will become  __stories\, tasks and bugs __ within that epic

Event/ Debug Logging

mapp Framework \(standard mapp implementation\)

Main

State Machine

Process

State Machine



---

https://c4model.com/ 

# Code Design & Testing

Consider Testing from the Start

As you dive further into the details of the code design\, be thinking about how you are going to test the code  _while you are designing it_  \(and before you start writing it\)

The process of writing your unit tests will become easier if you keep them in mind from the get\-go

Refer to the Testing section of this DevOps package for further context

![](img%5CProject%20Management7.png)



# Jira

Issues\, Project Topics\, and Boards

Issues

# Terminology

Everything is an “Issue”

* Every work item within Jira is generically referred to as an “Issue”
  * This applies to things like bugs / tasks\, as well as projects as a whole
* Therefore\, don’t be concerned if you attempt to create a Project\, for example\, but the dialog says “Create Issue”\.

![](img%5CProject%20Management8.png)



# Jira Issue Hierarchy

Overview

The following graphic summarizes the hierarchy of issues within Jira

At the top level you have either a Project or a Service Project

![](img%5CProject%20Management9.png)



# Jira Issue Types

Classifications of Work

![](img%5CProject%20Management10.png)

Task

Piece of work within an epic

Does not directly bring value to the end user

Does not require specification or review

_Examples_ :

Set up Hypervisor

Set up an SQL database

Epic

Feature/module\, or high\-level req’t

Large chunk of work

Can broken down into smaller pieces

_Examples_ :

HMI

Module

Station

Story

Piece of work within an epic

Has a clear\, defined value to the end user

_Examples_ :

Communication program

Alarms page

Trak process point code

Sub\-task

Piece of work within a story\, task or bug

Used to divide a story into specific chunks\.

_Examples_ :

Add alarms to task

Bug

Problem that impacts or prevents the function of a feature

Unwanted or unexpected behavior

_Examples_ :

Page fault

mapp View button not working

![](img%5CProject%20Management11.png)

![](img%5CProject%20Management12.png)

![](img%5CProject%20Management13.png)

![](img%5CProject%20Management14.png)

These five issue types are used to define all work within a project



---

Reference: https://confluence.br-automation.com/display/COPED/AnS+Issue+Types 

# Create an Issue

Story / Task / Bug / Epic

![](img%5CProject%20Management15.png)

To create a story\, task\, bug\, or epic\, do the following:

Open the project in Jira

Click the “Create” button at the top

Select the proper issue type from the “Issue Type” dropdown

Fill out the rest of the form accordingly

The newly created issue will then be sent to your backlog\.



![](img%5CProject%20Management16.png)

Sub\-task

The workflow for creating a sub\-task is slightly different than the other issue types:

Open up the issue that you want to create a sub\-task under

Go to “More”  “Create sub\-task”

Fill out the fields accordingly



# Changing the Issue Type

Story / Task / Bug / Epic

![](img%5CProject%20Management17.png)

If you created a new Jira issue but accidentally created it with the wrong type\, you can adjust it after the fact as follows:

Navigate to the Jira issue

Go to “More”  “Move”

Change the “Current Issue Type” dropdown to the intended issue type

Click Next and follow the subsequent prompts \(which vary depending on the new issue type\)

![](img%5CProject%20Management18.png)



# Jira

Project Topics

# Jira Project Pages

Sidebar Summary

The following pages are available in every Jira project:

| Page | Description |
| :-: | :-: |
| Backlog | Displays all open issues which are currently being worked on, as well as all issues that are waiting to be assigned in the future |
| Active sprints / Kanban board | Displays the current sprint or the Kanban board, depending on which board is currently selected via the dropdown right above the Backlog page |
| Releases | Allows you to define release versions, which can then be assigned to each Jira issue. Big-picture deadlines for development. Allows you to see a progress bar for how far along you are in a particular release.  |
| Reports | Allows you to view the status and progress of the whole project.  |
| Issues | Lists out all issues within the project. Can be filtered.  |
| Components | Similar to releases, but for topics rather than a point in time / due date. Useful for collecting all issues related to one topic, even if they span multiple epics (e.g. all motion issues).  |
| Timesheets | Allows you to see time logged to the project by the various contributors  |
| Structure | Allows you to create customizable filters for project analysis |
| Objects | Currently unused at B&R |

![](img%5CProject%20Management19.png)



# Components vs Epics

Comparison

Components and Epics are quite similar in that they are higher level containers for Jira issues\. However\, there are some key differences:

|  | Components | Epics |
| :-: | :-: | :-: |
| Duration | Exists for the duration of the project | Intended to be completed and closed out within a shorter time frame than the project as a whole. (Can also remain open for the whole project, but generally intended to be completed at some point) |
| Intended use | Topic related. Issues that belong to one component can be spread out across multiple epics | Intended for a specific feature or module of the machine |
| Quantity | Multiple components can be assigned to each issue | Only one epic can be assigned to each issue |
| Time tracking | No requirement | Every Jira issue must be assigned to an Epic for time tracking to function properly |
| Filter capability | Has a dedicated page within the Jira project sidebar which makes it easy to select a component and view all corresponding issues. You can also see all issues assigned to a component by using the “Component” filter option in the issue filter | See all issues assigned to an epic by using the “Epic Link” filter option in the issue filter |



# Releases

Define Software Versions

![](img%5CProject%20Management20.png)

Release versions allow you to define a software version and then assign Jira issues to that version \(via the “Fix Version” field in the issue details\)

While the release is in progress\, you get a progress bar showing how far along you are in completing all of the things assigned to that release

Once you complete a release\, you can view all issues related to the release as well as a full list of built\-in release notes

![](img%5CProject%20Management21.png)

![](img%5CProject%20Management22.png)



# Jira

Boards

# Boards

Kanban and Sprint

* There are two types of boards in a Jira project:
* Kanban
  * Define different workflow stages \(e\.g\. To Do\, In Progress\, Done\) as columns \(aka swimlanes\) and move each Jira issue through the process as it’s being worked on
  * Issues are organized by epic
* Scrum/Sprint
  * Similar to Kanban\, but limits your scope of work to only the tasks within the active sprint
  * Sprints are short periods of time \(typically about 2 weeks\) that are essentially short\-term goals for progress on the overall project\. You assign/plan work that is achievable to complete in that time frame\, and then focus exclusively on those tasks\. Planning out the work in short intervals like this also helps you to make continual progress on a project\, rather than inadvertently waiting until close to the deadline to try to cram everything in\. We highly recommend the use of sprints\, as they are an invaluable time management tool\.



How to Create

Create a new board via the dropdown at the top of the sidebar

You will then have the option to create either a scrum board or Kanban board

![](img%5CProject%20Management23.png)

![](img%5CProject%20Management24.png)



![](img%5CProject%20Management25.png)

How to Configure

Configure the board via the “Board” dropdown on the right side

This is where you define your columns and what issue statuses belong in each column

The column definition is up to your personal preference\. If you have no strong preference\, then we recommend the following setup:

![](img%5CProject%20Management26.png)



# Confluence

# Confluence Space

What Information Should You Store?

* Confluence is used to store project information such as:
  * Big picture timelines
  * Personnel lists
  * Summary of Jira issues \(via a macro – not manually entered\)
  * Application spec
  * Meeting notes
  * etc
* Confluence is quite flexible in that you can add new pages and sections as you see fit
* Take care of project permissions\!

![](img%5CProject%20Management27.png)



# Confluence Space Template

Project Pages

Various Confluence project templates are available to help you organize your project

You can also create your own template to be reused within your organizetion

At B&R\, our default template includes the pages shown below:

![](img%5CProject%20Management28.png)

| Template Page | Description |
| :-: | :-: |
| Organizational | Contains buttons for easily creating meeting notes.<br />Contains summary lists of all open Jira issues and Confluence tasks. |
| Requirements | Allows you to input the project specification as individual requirement pages |
| Application | For storing a .zip copy of the project (optional – should use source control instead) |
| Project controlling | For defining big-picture deadlines |
| About | For listing out the relevant personnel at the customer and at B&R |
| Userlist | Lists out all people who have access to the Confluence space |



# Bitbucket

# Version Control PPT

Dedicated PPT

For details on Bitbucket\, refer to the dedicated PPT within the DevOps package for Version Control\.

![](img%5CProject%20Management29.jpg)



# Open-Source Licensing

How to Select

* If you are creating collaborative software that is intended to be shared and expanded upon \(i\.e\. not a direct customer project\)\, then you should include an open\-source license with the code\.
* The following resources are available to help you select an open\-source license:
  * [The Legal Side of Open Source | Open Source Guides](https://opensource.guide/legal/#which-open-source-license-is-appropriate-for-my-project)
  * [Licensing a repository \- GitHub Docs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository#choosing-the-right-license)
  * [Choose an open source license | Choose a License](https://choosealicense.com/)
* If you are unsure what license to select\, then the [MIT license](https://choosealicense.com/licenses/mit/) is recommended\.

![](img%5CProject%20Management30.png)



We reserve the right to change the content of this presentation without prior notice\. The information contained herein is believed to be accurate as of the date of publication\, however\, B&R makes no warranty\, expressed or implied\, with regards to the products or the documentation contained within this document\. B&R shall not be liable in the event if incidental or consequential damages in connection with or arising from the furnishing\, performance or use of these products\. The software names\, hardware names and trademarks used in this document are registered by the respective companies\.

Copyright © B&R – Subject to change without notice

