# Version Control

DevOps Package

# Mission Statement

DevOps Package

To significantly  __reduce the barriers to entry __ of DevOps strategies into the day\-to\-day workflow of Automation Studio project development\, in order to  __increase the efficiency\, quality\, and maintainability __ of the resulting applications

# Contents

Version Control

* What is it?
* Why is it important?
* Included Template Files
* How to Implement:

![](img%5CVersion%20Control0.png)

  * Code Review
  * Versioning
  * Submodules
  * Hooks
  * AS Settings

  * Git
  * Sourcetree
  * Commits
  * Branching
  * Resolving Merge Conflicts

# Before we get started

Setting the stage

There is a huge amount of great material online that covers the “what”\, “why”\, and “how” of version control

In this presentation\, we will link to those external resources for general topics

We will primarily focus here on the things that are specific to B&R

![](img%5CVersion%20Control1.jpg)

# What is it, &Why is it important?

Version Control

# Version Control

Definition and Benefits

Source Code Management

![](img%5CVersion%20Control2.png)

![](img%5CVersion%20Control3.png)

# Build Version Framework

Integration with mapp View

The Build Version framework is a tool that automatically pulls git repository and PC version information and adds it to an AS project to display on the mapp View HMI\.

__This allows you to always be certain exactly which version of the software is running on the machine\!__

The build version framework installer is available on GitHub [here](https://github.com/br-na-pm/BuildVersionProject/releases/tag/V1.0.0)\. Note that to import this framework into your AS project\, you must have the [mapp Framework ](https://github.com/br-automation-com/mapp-Framework/releases)installed as well in order to use the import tool \(you aren’t required to use the mapp Framework itself in your project though\)

![](img%5CVersion%20Control4.png)

# Included Template Files

DevOps Package

Version Control

* The following two template files are provided with the DevOps package:
* [A standardized \.](slide24.xml)[gitignore](slide24.xml)[ file](slide24.xml)
* [A Git configuration script](slide13.xml)
* [authors\-export\.ps1 ](slide72.xml)[Powershell](slide72.xml)[ script](slide72.xml)

# How to Implement

  * Git
  * Sourcetree
  * Commits
  * Branching
  * Resolving Merge Conflicts

  * Code Review
  * Versioning
  * Submodules
  * Hooks

# Git

Version Control System

![](img%5CVersion%20Control5.png)

![](img%5CVersion%20Control6.png)

![](img%5CVersion%20Control7.png)

# Installation

Git

* Installation Considerations:
* Use default installations settings\, except for selecting your preferred default text editor \(e\.g\.\, Notepad\+\+\)
* After installation\, run the provided script  __GitConfigHelper\.bat__  to accomplish the following:
  * Change the default branch name to ‘main’ \(as opposed to ‘master’\)
  * Allow a secure connection
  * Set the credential manager to the Windows credential manager core

![](img%5CVersion%20Control8.png)

---

https://confluence.br-automation.com/display/COPED/My+First+Repository

# Bitbucket and GitHub

Hosting Services

A hosting service enables you to manage a Git repository

There are many choices for hosting services\, but the two that we use at B&R are Bitbucket and GitHub

Alternatives include Microsoft Azure Repos\, GitLab\, Amazon AWS CodeCommit\, and so on

![](img%5CVersion%20Control9.png)

![](img%5CVersion%20Control10.jpg)

Create a Repo

![](img%5CVersion%20Control11.png)

![](img%5CVersion%20Control12.jpg)

# Sourcetree

Git Client

A Git client allows you to interact with the Git repository via a visual interface\, without the command line

Just as with the hosting service\, there are many options for Git clients\. At B&R\, we use Sourcetree

Alternate options include Tortoise Git\, Git Extensions\, GitHub Desktop\, and so on\.

![](img%5CVersion%20Control13.png)

Setup

# Installation

Sourcetree

![](img%5CVersion%20Control14.png)

![](img%5CVersion%20Control15.png)

# Add a Remote Account

Sourcetree

![](img%5CVersion%20Control16.png)

![](img%5CVersion%20Control17.png)

After installation\, click on the Remote tab and “Add an account…”

In the resulting pop\-up\, change the hosting service dropdown to “GitHub” or “Bitbucket Server” accordingly\, and then click the button to either “Refresh OAuth Token” or “Refresh Password”

Follow the prompts to login on GitHub/Bitbucket and approve the authorization\.

# Identify External Merge Tool

Sourcetree Setup

![](img%5CVersion%20Control18.png)

* The tool we use at B&R to resolving merge conflicts is Visual Studio Code\. You can download it [here](https://code.visualstudio.com/)\.
* This tool must be identified in the Sourcetree options\. Therefore\, after installing Sourcetree and Visual Studio Code\, go to Tools  Options\. Select the “Diff” tab\.
* Within the “External Diff / Merge” section:
  * Set the External Diff Tool dropdown to “Custom”
  * Set the Diff Command to:C:\\Users\\%USERNAME%\\AppData\\Local\\Programs\\Microsoft VS Code\\Code\.exe
  * Set the Diff Command Arguments to: \-\-diff \-\-wait "$LOCAL" "$REMOTE"
  * Set the Merge Tool dropdown to “Custom”
  * Set the Merge Tool to: C:\\Users\\%USERNAME%\\AppData\\Local\\Programs\\Microsoft VS Code\\Code\.exe
  * Set the Merge Tool Arguments to: \-n \-\-wait "$MERGED"

# Authentication Issue

Mistyped Password

If you mistype your password while authorizing your Bitbucket/GitHub account\, follow the instructions in [this post](https://stackoverflow.com/questions/45690641/sourcetree-wont-let-me-delete-password) to fully delete the incorrect password and try again\.

![](img%5CVersion%20Control19.png)

# Clone Repo

Sourcetree

* Once your account is activated and working\, you can clone a repository from any organization that your account has access to\. Select the organization from the dropdown on the right\.
  * If you don’t see any organizations in your dropdown\, contact your project leader so that they can grant you access\.
* The list will then refresh with all available repositories\. Click “Clone” next to the one you want to clone

![](img%5CVersion%20Control20.png)

# Checkout Branch

Sourcetree

![](img%5CVersion%20Control21.png)

After you clone a repo\, take care to check out the branch that you intend to work on

The branches that are available on the remote repository are located on the left beneath “REMOTES”\.

Your local repository branches are listed under “BRANCHES”

The branch that is bolded is the one that you are currently checked out to

To check out a branch\, either double click it or use the right click menu

If you’re checking out a branch for the first time from the remote\, make sure to keep the box checked so that the “Local branch should track remote branch”

![](img%5CVersion%20Control22.png)

# Standardized .gitignore File

What is the end\-all\-be\-all recommended file?

* There are a handful of standardized \.gitignore files floating around the B&R universe\. For example:
  * [https://www\.toptal\.com/developers/gitignore/api/automationstudio](https://www.toptal.com/developers/gitignore/api/automationstudio)
  * [https://confluence\.br\-automation\.com/display/RDGO/adapt\+\.gitignore\+in\+the\+repository](https://confluence.br-automation.com/display/RDGO/adapt+.gitignore+in+the+repository)
  * [https://confluence\.br\-automation\.com/pages/viewpageattachments\.action?pageId=140411692](https://confluence.br-automation.com/pages/viewpageattachments.action?pageId=140411692)
* If you are unsure where to start\, the recommended standardized \.gitignore file is included within the template files of this DevOps package \(which closely matches the first option listed above\)\.
  * Note that this \.gitignore file should be placed in the root directory of the project \(the same directory as the \.apj file\)
* Make sure to add  _and push_  the \.gitignore file to the repo BEFORE you add any files that should be ignored\. If the \.gitignore is not ignoring your files as expected\, see [here](https://stackoverflow.com/a/53431148)\.

![](img%5CVersion%20Control23.png)

# Tips for Using Git with Safety

Do not work in parallel

* If your project includes safety\, then there are some additional considerations regarding the \.gitignore file:
* You do NOT have to exclude the DLFiles folder when using Git \(despite the fact that this is shown at GUID b8c69e5e\-7579\-4e41\-b853\-13cf9ccbef53\)\. This is only required if you are using Subversion \(not Git\)\.
* You MUST INCLUDE all \.set files within the safety project
  * Our template \.gitignore file contains this exception for you already
* Merging changes in a SafeDESIGNER project is not possible\. Only one person can work on the SafeDESIGNER project at a time\.
* Even if you don’t make any changes but you simply open the SafeDESIGNER project or compile\, several files within the project structure will indeed be updated\. This is expected – please always commit and push these changes to keep everything in line and up to date\.
  * If it is frustrating for your workflow that many safety files will change each time you compile\, then another option to consider is to completely exclude the SafeDESIGNER project from source control and instead include the SD project as a \.zip file\. Note that you will have to manually include this \.zip file within the \.gitignore file\, since the template is configured to ignore all contained \.zip files by default\.

# Tips for Using Git with VC4

Do not work in parallel

Only 1 person should open or make changes to a VC4 visualization at a time

The reason is because Git compares XML line by line\, but VC4 moves XML around liberally\. Therefore\, it is very easy to create many merge conflicts that are tedious to solve\. It is better to avoid this situation entirely\.

![](img%5CVersion%20Control24.png)

---

Ticket 400252714


# Commits

# Commit Description

Git

* When committing to the repo\, include the Jira ID \(if applicable\) at the beginning of the commit description\, along with a short sentence about what you changed
  * e\.g\.\, AAZM\-423 – xyz was fixed/changed
* [Recommendations](https://www.conventionalcommits.org/en/v1.0.0/) for writing commit messages
* Remember to commit often\!

![](img%5CVersion%20Control25.png)

# How to Undo a Commit

Git

The following resources explain the strategies for handling several different undo situations in Git

These methods are executed directly in the terminal

To access the terminal\, click the “Terminal” icon within your repo in Sourcetree at the top right

![](img%5CVersion%20Control26.png)

![](img%5CVersion%20Control27.png)

![](img%5CVersion%20Control28.png)

# Reverse Commit

Sourcetree

Instead of undoing a commit\, you can also create a new commit which reverses all of the changes in the selected commit\.

This can be executed directly from the Sourcetree History view via the right\-click menu\.

![](img%5CVersion%20Control29.png)

# Push to / Pull from the Remote

Sourcetree

Any commits you make will be stored in your local repository

In order to make the changes available to everyone else working on the project\, you must  __push__  to the remote repository

Similarly\, in order to obtain the changes that other teammates have made\, you must  __pull__  from the remote repository

![](img%5CVersion%20Control30.png)

Sourcetree Commands

# Branching

The Basics

Creating and Merging Branches

Gitflow Workflow

Branch Management

![](img%5CVersion%20Control31.png)

![](img%5CVersion%20Control32.png)

![](img%5CVersion%20Control33.png)

# Gitflow Branching

Branch Strategy at B&R

* Two long\-living branches:
* main
* develop
* Supporting branches \(temporary\):
* feature
* release
* hotfix

Branch Strategy at B&R

* Two long\-living branches:
* main
  * Officially released code
  * As bug\-free as possible
  * Each merge into main must be [tagged](slide35.xml) with a version number
  * There is only 1 instance of the main branch\, and it is never deleted
* develop
  * Integration branch for new features
  * Latest development version ready for testing \(may contain bugs\)
  * Should compile and run on real hardware
  * There is only 1 instance of the develop branch\, and it is never deleted
  * Create a  __release__  branch from the develop branch once you are ready to prep for release

Branch Strategy at B&R

* Supporting branches:
* feature
  * Used for developing new features
  * Several feature branches can exist simultaneously
  * Can be both local and remote
  * Useful anytime you expect to commit multiple times for one particular feature\, even if the feature is completed within a short period of time
  * Merged back into  __develop__  after the feature has been reviewed and it is ready for integration testing\. Then the branch is deleted\.
* release
  * branched from  __develop__  once all planned bugs/features are merged for the next release
  * Only used for bug fixes\, documentation\, and other release oriented tasks \(no new features\)
  * Merged back into  __main __  _and_   __develop __ once testing is complete and discovered bugs are fixed\. Then the branch is deleted\.
* hotfix
  * Branched from  __main__  when critical bug found in production that must be solved immediately
  * Used to develop critical bugfixes
  * <span style="color:#000000">Merged back into </span>  <span style="color:#000000"> __main __ </span>  <span style="color:#000000"> _and_ </span>  <span style="color:#000000"> </span>  <span style="color:#000000"> __develop\. __ </span> Then the branch is deleted\.

# Manual vs Git-flow

Branching in Sourcetree

You can use the icons at the top of Sourcetree to manually branch and merge according to the strategy previously described

![](img%5CVersion%20Control34.png)

Alternatively\, you can use the Git\-flow icon in the top right\. Git\-flow guides you to follow the branching strategy with a simple GUI\. This is the recommended method\.

![](img%5CVersion%20Control35.png)

# Git-flow

Branching in Sourcetree

After initialization\, click the “Git\-flow” icon again to start a new action

As application engineers\, you will typically select the “Start New Feature” action\. The project lead will start the release or hotfixes\.

When you first launch Git\-flow\, you must initialize the repo for Git\-flow\. Remember to change the production branch name to “main” \(“master” is the default value\)

![](img%5CVersion%20Control36.png)

![](img%5CVersion%20Control37.png)

# Git-flow Feature

Branching in Sourcetree

Commit and push to your feature branch as needed during development\.

Execute a [code review ](slide50.xml)\(more on this later\)

Once complete and reviewed\, click the “Git\-flow” icon again and select “Finish Feature”\. This will merge the feature branch back into develop for you and delete the feature branch

When you start a new feature\, give it a name and then confirm that it starts at the “develop” branch\.

![](img%5CVersion%20Control38.png)

![](img%5CVersion%20Control39.png)

# Resolving Merge Conflicts

# Merge Conflict

Definition

* A merge conflict means there are incompatible changes in the files you are trying to merge together
* This can happen\, for example\, when you are trying to merge two branches together
* This can also happen if you and a teammate are editing the same lines in the same file\. For example:
  * Your teammate commits and pushes changes to the server
  * You make changes to the same lines of code and commit the same file to your local server
  * Prior to pushing your changes\, you must pull\. However\, upon trying to pull\, you will be notified of the conflict between your local file and the change recently pushed by your teammate
* This section will guide you through how to resolve such merge conflicts
* As mentioned [previously](slide20.xml)\, we at B&R use Visual Studio Code to resolve merge conflicts

![](img%5CVersion%20Control40.png)

# How to Resolve Merge Conflicts

Sourcetree

![](img%5CVersion%20Control41.png)

Conflicted files appear with an exclamation mark next to them after you’ve committed and tried to pull changes from the server

# Launch External Merge Tool

![](img%5CVersion%20Control42.png)

How to Resolve Merge Conflicts

To resolve\, right click on the conflicted file and select “Resolve Conflicts  Launch External Merge Tool”\.

Accept Current Change

Accept Incoming Change

Accept Both Changes

Compare Changes

# Visual Studio Code Options

How to Resolve Merge Conflicts

![](img%5CVersion%20Control43.png)

There are 3 options in Visual Studio Code to resolve a conflict:

Accept Current Change

Accept Incoming Change

Accept Both Changes

The Compare Changes option allows you to view the differences side\-by\-side\.

These actions are integrated directly within Visual Studio Code as button selections above each conflict

Accept Current Change

Accept Incoming Change

Accept Both Changes

Compare Changes

How to Resolve Merge Conflicts

![](img%5CVersion%20Control44.png)

The example on the right will be used to show the result of each of the 3 merge conflict options\.

In this example:

<span style="color:#2F7366">“x := x / 3;” is the change to the line made locally\. </span>

<span style="color:#2F628F">“x := x \* 3;” is the change to the line that a teammate has already pushed to the server\, which you have not successfully pulled yet\. </span>

__Accept Current Change__

Accept Incoming Change

Accept Both Changes

Compare Changes

# Accept Current Change

How to Resolve Merge Conflicts in Visual Studio Code

_Option: Accept Current Change_

Applies your local changes and disregards the changes from the server

Therefore\, in this example\, we keep the line  <span style="color:#2F7366">“x := x / 3;”</span>

Accept Current Change

__Accept Incoming Change__

Accept Both Changes

Compare Changes

# Accept Incoming Change

How to Resolve Merge Conflicts in Visual Studio Code

_Option: Accept Incoming Change_

Applies the server’s changes and disregards your local changes

Therefore\, in this example\, we use the line  <span style="color:#2F628F">“x := x \* 3;”</span>

Accept Current Change

Accept Incoming Change

__Accept Both Changes__

Compare Changes

# Accept Both Changes

How to Resolve Merge Conflicts in Visual Studio Code

![](img%5CVersion%20Control45.png)

_Option: Accept Both Changes_

Applies your local changes  _and_  the server’s changes

Therefore\, in this example\, we now have both lines  <span style="color:#2F7366">“x := x / 3;” </span> and <span style="color:#2F7366"> </span>  <span style="color:#2F628F">“x := x \* 3;”</span>

Accept Current Change

Accept Incoming Change

Accept Both Changes

__Compare Changes__

# Compare Changes

How to Resolve Merge Conflicts in Visual Studio Code

The Compare Changes option shows a side\-by\-side view of the conflicting differences\.

![](img%5CVersion%20Control46.png)

# Code Review Strategy

At B&R

# When to Review

Code Review Strategy

__Prior__  to closing out a feature via Git\-flow \(and therefore merging the feature into the develop branch\)\, we recommend that the feature gets  __reviewed__  by a peer engineer or the project lead

If any changes are required per the review\, they would then be implemented on the same feature branch before it is closed

![](img%5CVersion%20Control47.png)

# Why to Review

Code Review Strategy

* There are 2 purposes of a code review:
  * Increase the code quality
    * Confirm that the feature indeed works
    * Brainstorm if the implementation is optimal or if it should be adjusted
  * Increase the number of people that are familiar with the code
    * By executing a review\, this guarantees that at least one other person is familiar with the feature and how it is implemented in case the original developer becomes unavailable

![](img%5CVersion%20Control48.png)

# Scheduling Code Reviews

Code Review Strategy

* The best way to trigger a code review is via a pull request
  * This can be triggered from Sourcetree: right click on the branch and select “pull request”
* Then the status of the pull requests will be visible to everyone who has access to the repository\, and there will be a paper trail for all code reviews
* You can also choose to lock the develop/main branches so that a pull request is absolutely required before anything can be merged to it

![](img%5CVersion%20Control49.png)

# Versioning

# Tagging

Git\-flow

Each merge into the main branch should be tagged with a version number

When you close a release via Git\-flow\, you can add the version number tag directly in the dialog box:

![](img%5CVersion%20Control50.png)

![](img%5CVersion%20Control51.png)

Git\-flow will merge the release branch into main and develop\. Afterwards\, make sure to checkout and push both branches

# Version Number Scheme

At B&R

* The version number scheme we use at B&R is:  <span style="color:#C00000"> __XX__ </span>  __\.__  <span style="color:#007A33"> __YY__ </span>  __\.__  <span style="color:#2684FF"> __ZZ__ </span>
  * <span style="color:#C00000"> __XX = Major Revision__ </span>
    * Incompatible with previous major revisions
  * <span style="color:#007A33"> __YY = Minor Revision __ </span>
    * New features added
  * <span style="color:#2684FF"> __ZZ = Bug Fixes__ </span>
    * No new features\, just small changes / bugfixes

![](img%5CVersion%20Control52.png)

# Submodules

Definition & Use Cases

* A submodule is a reference to another git repository within your repository
  * The submodule repo \(child repo\) is managed completely independently
  * The parent repo references a specific commit within the submodule that it is currently using
* Uses Cases within an AS project:
  * Separating out project components \(custom libraries\, application modules\)
  * Same use case as a feature branch\, but isolated to its own repository
  * Delegating a part of the project to a third party

![](img%5CVersion%20Control53.png)

# Separating Out Project Components

Submodule Use Case – Further Details

* Situation:
* A project/repo is used for a series machine\. There is a specific feature that is only needed for 1 machine\. What is the best way to manage this?
* Submodule Implementation:
* Use a submodule for the one\-off feature\.
* The submodule points to a package in the Logical View containing all of the files needed for the one\-off feature\.
* If Configuration View files are needed as well for the feature\, they would still be placed in this folder so that one single submodule can manage the files\. Then after you add the submodule to your project\, you would have to manually add referenced files in the Configuration View to the appropriate files from that package\.
  * If you don’t do it this way then you’d have to manage 2 or more submodules for one feature\, since a submodule can only point to one specific directory\, which would be quite difficult to manage\.

![](img%5CVersion%20Control54.png)

---




Submodule Use Case – Further Details

* Situation:
* A project/repo is used for a series machine\. There is a specific feature that is only needed for 1 machine\. What is the best way to manage this?
* Example:
* One example where this submodule method works quite nicely is if the one\-off feature could be contained completely in a library\.
* There would be one version of the library that is used for the series of the machines\, and another version of the library that is adjusted as needed for the one\-off\.
* In this case\, the submodule would contain just that library\. The project repo points to a submodule for that library:
  * The main branch \(for the series machines\) points to a submodule with the commonly used library implementation
  * Then there would be a separate branch for the one\-off machine\, which would point to a different submodule containing the modified version of the library
* In this situation\, the code itself remains unchanged since we are just swapping out which library is being utilized\. The inputs/outputs are consistent\.

![](img%5CVersion%20Control55.png)

---




Submodule Use Case – Further Details

Situation:

A project/repo is used for a series machine\. There is a specific feature that is only needed for 1 machine\. What is the best way to manage this?

Caveat:

If\, however\, the one\-off feature is too tangled/embedded in the application to where it’s not perfectly modular \(e\.g\. you have to modify existing files\, not just add new files\)\, then this submodule method may not make the most sense\.

In this case\, the alternate suggestion is to have a branch for the one\-off machine and make the necessary changes in that branch\.

As updates are made to the main branch\, merge main into the one\-off branch\. If ever there is an incompatibility between main and the one\-off feature\, then the feature would be adjusted within the one\-off branch\.

![](img%5CVersion%20Control56.png)

---




# Submodules

Workflow

* Commit/push changes to the submodule repo as usual
* Commit/push changes to parent repo to update the commit reference \(“pointer”\) to the submodule
  * The parent repo keeps records what commit hash it is currently using of the submodule\. So\, if you push a change to the submodule without committing the new reference commit value in the parent repo\, then the parent repo will still be referencing the previous commit in the submodule\.
* This is how a submodule reference looks within Sourcetree\, prior to staging the change\. In this example\, “BaseProject” is the submodule \(child\) repo\.
  * Once this change is pushed to the parent repo\, the parent repo is now using the commit starting with “08fb” on the submodule

![](img%5CVersion%20Control57.png)

![](img%5CVersion%20Control58.png)

# Detached Head

Higher Risk with Submodules

* Make sure if you commit to the top\-level project that you also commit any submodules that have changes to them\.
* If you don’t\, then you’ll end up on a detached head on the submodule repository
  * This means your latest changes within that repo will be reverted to the last commit to the top\-level repository\, which can be confusing\. It also means that any new commits to the sub repository are not associated with any branch\, which is not good\!
* To recover from a detached head: \([Source](https://community.atlassian.com/t5/Sourcetree-questions/Fix-a-detached-head-lost-master-branch/qaq-p/165563#:~:text=Right-click%20on%20your%20most%20recent%20commit%20in%20the,master%2C%20then%20merge%20your%20new%20branch%20into%20it.)\)
  * Do NOT check out any other branch \(stay on the detached head\)
  * Right click on your most recent commit in the detached head and select “Branch”
  * Give the branch a name\. Leave "Specified commit:" selected\. Uncheck the "Checkout New Branch”\.
  * Afterwards\, confirm in SourceTree that the new branch is on your latest commit\.
  * Now you can checkout the develop branch and merge the branch you just created into it\. Afterwards\, delete that branch\.

# Hooks

Overview

* Hooks are scripts that automatically run at certain git repository events
* There are two types:
  * Local Hooks: for events related to committing or checking\-out to your local repo
  * Server Hooks: for events related to pushing changes to the remote server
    * Note that tasks accomplished via server hooks can \(and arguably should\) be accomplished by the build/automation server instead

![](img%5CVersion%20Control59.png)

![](img%5CVersion%20Control60.png)

![](img%5CVersion%20Control61.png)

Location and Samples

* All hooks are located in the \.git/hooks folder
  * The \.git folder is located in the root directory of the repo
  * Note that this is a hidden folder\, so make sure those are shown in your file explorer
* Many sample hooks are pre\-populated within the \.git/hooks folder to use as a starting point
  * They are all of the “\.sample” file extension
  * To activate a pre\-made hook for your repo\, simply remove the “\.sample” file extension

![](img%5CVersion%20Control62.png)

# Local Hooks

Overview of Commonly Used Hooks

* pre\-commit
  * Runs before you attempt to commit to the repository
  * Useful for code quality checks \(whitespace errors\, modules OK not monitored\, etc\)
* prepare\-commit\-msg
  * Runs after pre\-commit
  * Useful for prepopulating commit messages
* commit\-msg
  * Runs after the commit message
  * Useful for checking commit message standards \(reference JIRA issue\)
* post\-commit
  * Runs after a commit
  * Trigger local integration tests
* post\-checkout
  * Runs after a checkout
  * Useful for cleaning workspace \(clean AS project\)

# Server Hooks

Overview of Commonly Used Hooks

* pre\-receive
  * Runs when someone attempts to push commits to the repository
  * Enforce any development policy \(code quality/standard checks\, commit message checks\, etc\)
  * Called once per push
* update
  * Runs after pre\-receive
  * Called separately for each ref \(branch\) that was pushed
  * Reject single ref’s in a push instead of the entire push
* post\-receive
  * Runs after a successful push
  * Useful for triggering continuous integration system \(e\.g\.\, could automatically trigger the Jenkins build\)
  * Useful for notifications

# AS Project Settings

# CPU Properties

![](img%5CVersion%20Control63.png)

Recommended Setting

On the Build tab of the CPU properties\, it is recommended to add the \.git file extension to the list for “Objects ignored for build warnings 9232 and 9233”\.

This will prevent those warnings from triggering because \.git files exist in the project directory which are not directly related to the project itself

# Migrating from SVN

# Creating Authors file

Migrating from SVN

* The authors files will translate svn usernames to email addresses for git
* PowerShell command to extract all authors from SVN:
  * Run the  __authors\-export\.ps1 __ script from within your svn directory
  * Must have svn command line tools installed
    * This is an option when installing TortoiseSVN
    * If you are unsure whether you installed it or you know that you didn’t\, you can just run the TortoiseSVN installer again and take care to include this option
* Edit authors\.txt file to match the following format:
  * buchananw = Wesley Buchanan wesley\.buchanan@br\-automation\.com
  * www\-data = system \<noreply@br\-automation\.com>

![](img%5CVersion%20Control64.png)

# Cloning Repository

Migrating from SVN

* For standard layout of trunk\, branchs\, tags \(internal/external redmine\)
  * git svn clone \[SVN repo URL\] \-\-prefix=svn/ \-\-no\-metadata \-\-authors\-file "authors\.txt" \-\-stdlayout
* For non\-standard layout \(B&R’s svn repository\)
  * git svn init \[SVN repo URL\] \-\-no\-metadata
  * git svn fetch –authors\-file “authors\.txt”

![](img%5CVersion%20Control65.png)

# Convert svn ignore

Migrating from SVN

git svn show\-ignore > \.gitignore

git add \.gitignore

git commit \-\-m ‘convert svn:ignore to \.gitignore’

![](img%5CVersion%20Control66.png)

# Pushing to new Git repository

Migrating from SVN

git remote add origin \[my new git repo\]\.git

git add \.

git commit \-\-m ‘migrating svn to git’

git push \-\-u origin main

![](img%5CVersion%20Control67.png)

# Syncing new svn commits

Migrating from SVN

git svn rebase

git push

![](img%5CVersion%20Control68.png)

We reserve the right to change the content of this presentation without prior notice\. The information contained herein is believed to be accurate as of the date of publication\, however\, B&R makes no warranty\, expressed or implied\, with regards to the products or the documentation contained within this document\. B&R shall not be liable in the event if incidental or consequential damages in connection with or arising from the furnishing\, performance or use of these products\. The software names\, hardware names and trademarks used in this document are registered by the respective companies\.

Copyright © B&R – Subject to change without notice

