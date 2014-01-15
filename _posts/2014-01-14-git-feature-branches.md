---
layout: post
title:  "Git Feature Branch Workflow"
date:   2014-01-14 23:00:00
categories: git workflow
---

Git is a powerful source code management system but it so flexible that it is easy to get into trouble unless you follow a procedure to keep yourself out of trouble.  A workflow is set of guidelines to try to keep things simple and avoid pitfalls.  If you don't know where to start or you're having trouble finding a rhythm, you could start with something like this.

Feature branches are practial in Git mostly because branches are so lightweight and easy to create.  This workflow is based on the model presented in [A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/) and for the purposes of this post, we'll assume that the mainline branch for is called _develop_, to be consistent with the model in that article.

## Feature Branches
All non-trivial _develop_ work should be done in a feature branch.  Why?


* Focused development proceeds for a stable starting point
* All commits in the feature branch are directly related to the feature
* Commits in the feature branch are linear since the branch was forked
* Commits can be made frequently
* Commits do not need to be code reviewed
* Commits can always contain groups of related changes
* The branch can be broken without affecting other developers
* Changes in test success or failure are always due to a change made in the branch
* The branch can be pushed frequently to the team server providing hourly backups of work
* It never happens that you broke your own changes and can't go back to a working version


## How To Use A Feature Branch

### Choose Your Starting Point Wisely
Your starting point shouldn't change during the short life of your feature branch so make it a good one.


* Branch off the latest passing build of _develop_
* Make sure it contains all the other features you will need to complete your work


### Make Your Changes Without Merging
You know how to develop; go ahead and implement the feature.  Pretend someone sent you a zip file of the source code and asked you to add the feature.

### Test Your Changes
Once you've implemented the feature, you should test it completely enough that it would build successfully on the build server.  Your branch was in this condition when you started, so if anything fails, it is related to something you did.  That makes fixing any problems easier.

### Choose Your End Point Wisely
Before your merge back to _develop_, make sure the head of _develop_ builds successfully on the build server.  If you try to merge with a broken build and you don't fix problems because the build was already broken, you could merge hidden problems that will be hard to sort out. 

### Merge and Resolve Conflicts Locally
If there were no other intervening changes to _develop_, your branch would now be ready to become the new head. But there were other changes so you have to merge them.  Check out _develop_ and do a merge from your feature branch.  We need a merge commit message so prevent a fast-forward merge.  If there are no conflicts you have a clean merge.  If you do have conflicts, resolve them.  Don't pollute your merge commit with any additional changes.

### Write a Good Commit Message
The merge commit is the most important commit you are planning to push, so amend its commit message to contain a summary of all the changes you made.  The editor will list all of the files you modified to help you remember changes you need to document.  You can also use the log of individual commit messages in your feature branch.  It can be also useful to use a difftool to compare the merge commit to the previous head.

### Retest Your Merged Changes
Even though your changes were good before merging, and _develop_ was good before you merged, the combined result might not be good.  So you have to retest.

### Add Fixups Locally So Your Branch Will Build on the Build Server
If your merge code doesn't build or pass tests, then there was some unexpected interaction between the two branches.  However, knowing that they passed separately will make the process of figuring out why they don't pass together.  Commit any need changes as fixups.

### Code Review Your Work
You've merged your changes, resolved any conflicts, added any fixups and it builds and passes all tests.  You are now in the perfect position to code review your work.  Use a difftool to compare the previous head to your local head.  Amend the merge commit message again to record that the change has been code reviewed and by whom.

### Push To Integration
Double-check that you are on the _develop_ branch, double-check the log show your merge commit and any fixups and then push the branch the team server.

In the unfortunate event that someone else pushed a change to _develop_ while you were merging, fixing up, and code reviewing, you can fetch from the team server and then merge the team server head of _develop_ into your local _develop_ branch.  This will create yet another merge commit, which has to be retested, but that is probably easier than going back and remerging your branch.

### Delete Your Feature Branch
When you have merged your feature branch into _develop_, you can immediately delete your local branch and any pushed copy of that branch.  This is because your merge commit has one parent that was the head of your feature branch.  You feature branch, including all the micro-commits that were part of it are now accessible from the head of _develop_ going backwards.

## Other Guidelines

### Keep the Feature Branch Clean
Resist the temptation to pull from _develop_ into your feature branch.  One rarely has to do this but it is tempting to do so because of habit.  You want to "keep up" with _develop_.
 
Why not?

* If you merge other work into your branch, when you merge back into _develop_:
* you may have conflicts in code you did not modify
* your merge commit will contain a mixture of your work and all the work you merged
* Your feature branch becomes a non-linear spaghetti tree of your changes mixed with other changes
* Other developers who are looking at your branch cannot easily see how the feature's _develop_ is going


### Phased Features and Reusing Feature Branches
If a feature is incomplete but the has reached a partial milestone and the branch still builds and passes all tests, you can consider merging your work so far into _develop_, resetting the feature branch to the head of _develop_, and then continuing to develop the next phase of the feature.  This is advisable if others are blocked waiting for a partial implementation of your feature or if the number of modified files becomes unwieldy.

### Unforeseen Dependencies
What if after your start your feature branch, you get stuck because you need a defect fix that is now in _develop_ but not in your branch?  One solution is to cherry-pick just the changes you need from the other branch, if possible.  Another is to complete the feature enough so that it builds and passes all tests, and then merge your incomplete but stable branch with _develop_ and continue.  In any case, try to avoid cross-merging your branch with _develop_.

### Merge was Time-Consuming and You Cannot Push Right Away
Part of this workflow is based on being able to amend local commits before pushing to _develop_.  If the merge steps are time-consuming and you need to back up you work without pushing to _develop_ proper, you can push to a temporary branch on the team server.  If need be, you can force push as many times as you have to.  Just remember to delete the pushed backup of your merge in progress when you finally push to _develop_ itself.

### Collaborating with Yourself or Other Developers
A feature branch can easily be used by the same developer from two different machines or by two different developers by pulling the feature branch from the team server with rebasing.  If a backup push is rejected, the rebase just moves your unpushed commits to the end of the linear feature branch _develop_ permitting you to push again.
