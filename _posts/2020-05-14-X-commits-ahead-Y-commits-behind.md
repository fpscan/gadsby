---
toc: false
layout: post
description: I got this when I started using github.
categories: [how-to, git]
title: GitHub keeps saying “This branch is X commits ahead, Y commits behind”
---
# This branch is X commits ahead, Y commits behind

There is a easier way to sync your fork with the original repository. Open your git:

```git
git remote add upstream https://github.com/upstream/repo.git
```

When you want to sync the changes from upstream

```git
git pull --rebase upstream master
```

```git
git push --force-with-lease origin master
```

I highly recommend that you make new branch for each changes, so you can work on something else while other PR is still waiting for approval. 

Before creating a new branch, pull the changes from upstream. Your master needs to be up to date.
```git
git pull
```

Create the branch on your local machine and switch in this branch :
```git
git checkout -b [name_of_your_new_branch]
```

Push the branch on github :
```git
git push origin [name_of_your_new_branch]
```

I use [GitHub Desktop](https://desktop.github.com/) which is easy to use for overall.