# Git

with:
* Kevin (harokevin0@gmail.com)
* Ken (kenschmidt@gmail.com)

---

## What is Git?

* Distributed Version Control System
* Written by Linus Torvalds (The linux guy)

Note: Ken

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

Note: Ken

---

## Git Init
* <section><pre><code data-trim data-noescape>git init</code></pre></section>
* Creates a new <strong>Repository</strong>
Note: Kevin

---

## Git Status
* <section><pre><code data-trim data-noescape>git status</code></pre></section>
* Check the status of <strong>Staged</strong> and <strong>Unstaged</strong> changes
Note: Kevin - Add screenshot to show staged vs unstaged

---

## Git Add
* <section><pre><code data-trim data-noescape>git add</code></pre></section>
* Adds, or <strong>Stages</strong>, changes for commit
Note: Kevin

---

## Git Commit
* <section><pre><code data-trim data-noescape>git commit</code></pre></section>
* Takes your <strong>Staged</strong> changes and saves them in the log
Note: Kevin

---

## Git log
* <section><pre><code data-trim data-noescape>git log</code></pre></section>
* Lets you see your <strong>Commit</strong> history. (History of saves)
* This is where gitk and Source Tree help with visualizing commits
Note: Kevin - extra slides for installing gitk or source tree?

---

## Git Checkout
* <section><pre><code data-trim data-noescape>git checkout [file-name]</code></pre></section>
* The undo button
* Lets you "go back" to the previously committed state of a file(s).
* Forgets modifications shown in <strong>Staged</strong> and <strong>Unstaged</strong> files.
Note: Kevin

---

## Git Branch
* <section><pre><code data-trim data-noescape>git branch [your-branch-name]</code></pre></section>
* Want to work on a new feature without breaking the project? Make a <strong>branch</strong>!
* Branches are like a sandbox
* You can play in them and not worry about breaking anything
* Very useful for working with others. Everyone has their own, or multiple, branch(es)!
Note: Ken

---

## Git Checkout
* <section><pre><code data-trim data-noescape>git checkout [branch-name]</code></pre></section>
* This command also allows you to <strong>Checkout</strong> other branches.
* Remember that this command, when given a file name, forgets the changes made to that file after the latest commit.
Note: Kevin

---

## Git Merge
* <section><pre><code data-trim data-noescape>git merge [branch-name]</code></pre></section>
* Sandbox branch works? Time to recombine with the rest of the project
* Merging brings what you are working on back into the  <strong>master</strong> branch
Note: Ken

---
