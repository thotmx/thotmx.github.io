---
title: Moving commits from master to a branch
date: 2015-07-16
tags: git
---

###Problem

Sometimes when I start a small fix, I think that is not necessary to put it on a new branch maybe with one commit should be enough. But then I realize that should be necessary a bigger effort to fix it completely. So, I'll need a new branch. But I've committed one o two yet. What can I do?

###Solution

Create a new branch on your working directory:

  ```
  git branch not-so-simple-feature
  ```

Move the master pointer two, three or n commits back (two on this example):

  ```
  git reset --hard HEAD~2
  ```

Now you can move to the new branch and continue working.

  ```
  git checkout not-so-simple-feature
  ```

