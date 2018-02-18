# Git

with:
* Kevin (harokevin0@gmail.com)
* Ken (kenschmidt@gmail.com)

---

## Follow along!

* https://tinyurl.com/git-class

---

## What is Git?

* Collaboration and versioning tool
* Distributed Version Control System
* Written by Linus Torvalds (The linux guy)

---

## What problems does git solve?

* https://teamtreehouse.com/library/git-basics/why-version-control-matters/life-without-version-control

---

## What problems does git solve?

* A better way to “undo” changes
* A better way to collaborate than mailing files back and forth
* A better way to share your code and other scientific work with the world

---

## Try Git!

* https://try.github.io/

---

## Starting from Scratch
~~~~
git init
~~~~
* Creates a new **`*repository*`**
* Transforms your folder into a **`*repository*`**

Note: 1.1 https://try.github.io/levels/1/challenges/1
Next 1.2
---

## What's going on?
~~~~
git status
~~~~
* View the status of your **`*repository*`**
* Shows you **`*staged*`** and **`*unstaged*`** changes
* **`*staged:*`** changes you want to save
* **`*unstaged:*`** changes you don't want to save

Note: 1.2 https://try.github.io/levels/1/challenges/2
Next 1.4
---

## Time to take the stage
~~~~
git add [file-name]
~~~~
* Adds, or **`*stages*`**, changes for commit
* Says: "Okay, lets prepare to save this"

Note: 1.4 https://try.github.io/levels/1/challenges/4
Next 1.6
---

## Get Committed
~~~~
git commit -m "my short note about my changes"
~~~~
* Takes your **`*staged*`** changes and saves them in the log
<p></p>

On first setup:
~~~~
git config --global user.email "your@email.co"
git config --global user.name "Your Name"
~~~~

Note: 1.6 https://try.github.io/levels/1/challenges/6
Next 1.9

---

## What did we do?
~~~~
git log
~~~~
* Lets you see your **`*commit*`** history. (History of saves)
* This is where gitk and Source Tree help with visualizing commits

Note: 1.9 https://try.github.io/levels/1/challenges/9
Next 1.10

---

## Who's out there?

~~~
git remote add
~~~
* Makes a link to a remote repository (i.e. github, bitbucket, gitlab)
* Used to collaborate with other people working on the project

Note: 1.10 https://try.github.io/levels/1/challenges/10
Next 1.11

---

## Take my work!

~~~
git push
~~~
* Pushes local changes to a remote repository

Note: 1.11 https://try.github.io/levels/1/challenges/11
Next 1.12

---

## What did you do?

~~~
git pull
~~~
* Pulls changes made to the remote repository into the local one

Note: 1.12 https://try.github.io/levels/1/challenges/12
Next 1.13

---

## What changed?

~~~
git diff
~~~
* Displays the differences between different versions
* HEAD in all caps refers to the latest version checked into the repo

Note: 1.13 https://try.github.io/levels/1/challenges/13
Next 1.15

---

## What am I about to do?

~~~
git diff --staged
~~~
* Displays the differences that are on the staged about to be committed

Note: 1.15 https://try.github.io/levels/1/challenges/15
Next 1.16

---

## Wait! I don't want to do that.

~~~
git reset
~~~
* Removes a file from the stage

Note: 1.16 https://try.github.io/levels/1/challenges/16
Next 1.17

---

## Start Over!
~~~~
git checkout [file-name]
~~~~
* The undo button
* Lets you "go back" to the previously committed state of a file(s).
* Forgets modifications shown in **`*staged*`** and **`*unstaged*`** files.

Note: 1.17 https://try.github.io/levels/1/challenges/17
Next 1.18

---

## Let's try something
~~~~
git branch [your-branch-name]
~~~~
* Want to work on a new feature without breaking the project? Make a **`*branch*`**!
* Branches are like a sandbox

Note: 1.18 https://try.github.io/levels/1/challenges/18
Next 1.19

---

## Let's check it out
~~~~
git checkout [branch-name]
~~~~
* This command also allows you to **`*checkout*`** other branches.
* Remember that this command, when given a file name, forgets the changes made to that file after the latest commit.

~~~~
git checkout [file-name]
~~~~
vs
~~~~
git checkout [branch-name]
~~~~


Note: 1.19 https://try.github.io/levels/1/challenges/19
Next checkout -b sidenote

---

## Shortcut!
~~~~
git checkout -b [branch-name]
~~~~
* This combines the **`*branch*`** creation and **`*checkout*`** commands together
* Useful because the two commands are used frequently and together

Note: disconnected side note
Next 1.20

---

## I don't Want this anymore
~~~~
git rm
~~~~
* Removes Files from repository (including the filesystem)

Note: 1.20 https://try.github.io/levels/1/challenges/20
Next 1.23

---

## Let's Get Together
~~~~
git merge [branch-name]
~~~~
* Merging brings the changes you were working on back in one branch into another

Note: 1.23 https://try.github.io/levels/1/challenges/23
Next 1.24

---

## Clean Up
~~~~
git branch -d [branch-name]
~~~~
* removes a branch from your repository

Note: 1.24 https://try.github.io/levels/1/challenges/24
No more

---

## Resources

http://ohshitgit.com/
https://sethrobertson.github.io/GitFixUm/fixup.html

---

## Git Clients

* Command Line <i class="fa fa-linux" aria-hidden="true"></i> <i class="fa fa-apple" aria-hidden="true"></i> <i class="fa fa-windows" aria-hidden="true"></i>
  * https://git-scm.com/
* Source Tree <i class="fa fa-apple" aria-hidden="true"></i> <i class="fa fa-windows" aria-hidden="true"></i>
  * https://www.sourcetreeapp.com/
* gitk <i class="fa fa-linux" aria-hidden="true"></i> <i class="fa fa-apple" aria-hidden="true"></i> <i class="fa fa-windows" aria-hidden="true"></i>
  * https://git-scm.com/
* TortoiseGIT <i class="fa fa-windows" aria-hidden="true"></i>
  * https://tortoisegit.org/

---

## Next week

* Homework:
  - Install a git client
  - Create a GitHub account
