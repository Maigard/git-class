## [Instructions](worksheet-instructions.md)

## Setup

1) Team member A forks the demo repository from https://github.com/harokevin/recipes
<!-- TODO link fork screenshot -->

2) Team member A gives team member B access to team member A's fork on GitHub
<!-- TODO link collaborators screenshot -->

3) Team member A and B clone team member A's online fork onto their computers

Check Point: Do all teammates have a version of the fork on their computers?
<!-- TODO link copy url and clone screenshot -->


## Making changes and opening a pull request
Goal: In this block one person will add an instruction to a recipe in the repository

1) Team member A makes the first set of changes then opens a Pull Request

-  Create a branch - name it after what you want to accomplish (no spaces). `add-instruction-to-cookies`

- Make content changes: open any .md file in the project and add a direction step like `Lets Party` or `Give to neighbors`.

- `add` changes - stages changes

- `commit` changes - saves changes

- `push` changes to the remote/GitHub
	- There might be an extra step that looks something like:
		- `git push --set-upstream origin add-instruction-to-cookies`
	  - If so, run the command shown in your command line.
	  - You will have to run this once per branch.
- Open a `Pull Request` on GitHub
    - A description is optional for this exercise but your `Pull Requests` should usually have some explanation.
<!-- TODO link pr button screenshot -->
<!-- TODO link pr branch select screenshot -->

2) The other team members review and accept the `Pull Request`
  - Notice how the changes are added to the existing content

3) Team member A merges the `Pull Request` into `master`
  - There are a few options here but lets go with the simplest one for now, create a merge commit.

### Check point
 - Is everyone up to date with master?

  - Use `git pull` to sync with the GitHub repository

### Recap
In this block one person created a branch, made a commit locally, pushed the commit to GitHub, opened a GitHub pull request around their branch, got the pull request reviewed by a teammate and merged their changes into the project.


4) Repeat the previous steps but B makes changes and A and C review the `Pull Request`

5) Repeat the previous steps but C makes changes and A and B review the `Pull Request`

6) Repeat the entire drill again so that by the end everyone has merged into master twice. This entire piece of work should consist of:
  - A making a change and merging,
  - B making a change and merging,
  - C making a change and merging,
  - then A making a change and merging again,
  - then B making a change and merging again,
  - and finally C making a change and merging.

### Check point
 - Has everyone merged 2 `Pull Requests`?


## Merge conflict and resolution
 - When you are working with others in a single file you might encounter a `merge conflict`. This is when you have both modified a file and Git does not know what to do so you have to help it out.
 - More precisely, a `merge conflict` occurs when you start with the same file as another person and they modify it behind your back and merge it into master before you. Then, when you want to merge your changes into master you might encounter a `merge conflict` because the file was modified in two different ways.
 - Although merge conflicts do not always happen when working in the same file as another teammate it is important to know how to resolve them when they do happen.

### A merges first and B gets a merge conflict
Goal: In this block two different people will make different changes to the same line of a file. This would happen if both teammates saw an error with the line but had different ways to resolve the error.

1) Team member A creates a `branch` named `fix-typos`

2) Team member B creates a `branch` named `typo-fix`

3a) Team member A makes the following changes:
- recipes/rick_and_morty_szechuan_sauce.md
 - ` - Gresh ginger` => ` - Fresh ginger`

3b) Team member B makes the following changes:
- recipes/rick_and_morty_szechuan_sauce.md
 - ` - Gresh ginger` => ` - Gresh ginger paste`

4) The team members above `add`, `commit`, `push` and `Pull Request` their changes.

5) All team members review and accept their teammate's `Pull Requests`.

### Check point
 - Notice that both active pull request can be merged at this time. There are no conflicts.

6) Team member A merges the accepted `Pull Request`

### Check point
- Notice that team member B's pull request can not be merged at this time.
- Team member B also wants to merge their `Pull Request` but they are unable to because of the `merge conflict`.
- To resolve a conflict you will generally want to work with the person that last made changes. In this scenario that would be Team Member A.
- You will see something like this in your file that Git has added:
```
<<<<<<< HEAD
 - Gresh ginger paste
=======
 - Fresh ginger
>>>>>>> master
```

- The general structure of this is:
```
<<<<<<< your_changes
	[content that you have changed]
=======
	[same line that was changed by another branch you are merging with]
>>>>>>> branch_you_are_merging_with
```

7) Team Member B - Lets say you come to a consensus with your teammate and this is how the merge conflict will be handled:

- The line should be `- Fresh ginger paste`. Not `- Gresh ginger paste` or ` - Fresh ginger`

- To resolve this conflict replace the Git added block with what the line should be:
	```
	<<<<<<< HEAD
	 - Gresh ginger paste
	=======
	 - Fresh ginger
	>>>>>>> master
	```

	to =>

	` - Fresh ginger paste`

- Make sure you always remove the general merge conflict structure.

8) Once you are done merging, `add` and `commit` the changes to resolve the conflict
 - Notice that it will take you into a special command line editor that will have a commit name suggestion.
 - To write/save the name of this commit and then quit the editor do the following:
	- press escape
	- type `:wq`
	- press enter
 - you should now be back at the normal command line

9) After the changes are made `push` the changes.

10) Get the merge conflict resolution changes re-reviewed by the team.

11) Team Member B merges the accepted `Pull Request`.

### Check point
- Team member B has encountered and resolved a merge conflict.


### B merges first and A gets a merge conflict
Goal: In this block two different people will make different changes to the same line of a file. This would happen if both teammates saw an error with the line but had different ways to resolve the error.

1) Team member A creates a `branch` named `amend-chili`

2) Team member B creates a `branch` named `fix-chili-pow`

3-Team Member A) Team member A makes the following changes:
- recipes/rick_and_morty_szechuan_sauce.md
 - ` - Chili paste (if you’re looking for heat)` => ` - Chili paste`

3-Team Member B) Team member B makes the following changes:
- recipes/rick_and_morty_szechuan_sauce.md
 - ` - Chili paste (if you’re looking for heat)` => ` - Chili powder (if you’re looking for heat)`

4) The team members above `add`, `commit`, `push` and `Pull Request` their changes

5) All team members review and accept their teammate's `Pull Requests`

### Check point
Notice that everyone's pull request can be merged at this time. There are no conflicts.

6) Team member B merges the accepted `Pull Request`

### Check point
Notice that team member A's pull request can not be merged at this time.
- Team member A also wants to merge their `Pull Request` but they are unable to because of the `merge conflict`.
- To resolve a conflict you will generally want to work with the person that last made changes. In this scenario that would be Team Member B.
- You will see something like this in your file that Git has added:
```
<<<<<<< HEAD
 - Chili paste
=======
 - Chili powder (if you’re looking for heat)
>>>>>>> master
```

7) Team Member A - Lets say you come to a consensus with your teammate and this is how the merge conflict will be handled:
- The line should be ` - Chili paste or powder`. Not ` - Chili paste` or ` - Chili powder (if you’re looking for heat)`

- To resolve this conflict replace the Git added block with what the line should be:
  ```
  <<<<<<< HEAD
   - Chili paste
  =======
   - Chili powder (if you’re looking for heat)
  >>>>>>> master
  ```

  to =>

  ` - Chili paste or powder`

- Make sure you always remove the general merge conflict structure.

8) Once you are done merging, `add` and `commit` the changes to resolve the conflict
- notice that it will take you into a special command line editor that will have a commit name suggestion.
- to write/save the name of this commit and then quit the editor do the following:
	- press escape
	- type `:wq`
	- press enter
- you should now be back at the normal command line

9) After the changes are made `push` the changes.

10) Get the merge conflict resolution changes re-reviewed by the team.

11) Team Member A merges the accepted `Pull Request`.

### Check point
Team member A has encountered and resolved a merge conflict.


### Check point
Make sure everyone in your team has encountered a merge conflict and also been the person to merge first(not encounter the merge conflict.)


### C merges first and B gets a merge conflict
Goal: In this block two different people will make different changes to the same line of a file. This would happen if both teammates saw an error with the line but had different ways to resolve the error.

1) Team member C creates a `branch` named `sugar-fix`

2) Team member B creates a `branch` named `fix-packed-sugar`

3-Team Member C) Team member A makes the following changes:
- recipes/rick_and_morty_szechuan_sauce.md
	- ` - 4 tbs of brown sugar` => ` - 6 tbs of brown sugar`

3-Team Member B) Team member B makes the following changes:
- recipes/rick_and_morty_szechuan_sauce.md
	- ` - 4 tbs of brown sugar` => ` - 4 tbs of packed brown sugar`

4) The team members above `add`, `commit`, `push` and `Pull Request` their changes

5) All team members review and accept their teammate's `Pull Requests`

### Check point
Notice that everyone's pull request can be merged at this time. There are no conflicts.

6) Team member C merges the accepted `Pull Request`

### Check point
Notice that team member A's pull request can not be merged at this time.
- Team member B also wants to merge their `Pull Request` but they are unable to because of the `merge conflict`.
- To resolve a conflict you will generally want to work with the person that last made changes. In this scenario that would be Team Member C.
- You will see something like this in your file that Git has added:
```
<<<<<<< HEAD
  - 4 tbs of packed brown sugar
=======
  - 6 tbs of brown sugar
>>>>>>> master
```

7) Team Member B - Lets say you come to a consensus with your teammate and this is how the merge conflict will be handled:

- The line should be `- 6 tbs of packed brown sugar`. Not ` - 6 tbs of brown sugar` or ` - 4 tbs of packed brown sugar`

- To resolve this conflict replace the Git added block with what the line should be:
  ```
  <<<<<<< HEAD
    - 4 tbs of packed brown sugar
  =======
    - 6 tbs of brown sugar
  >>>>>>> master
  ```

  to =>

  `- 6 tbs of packed brown sugar`

- Make sure you always remove the general merge conflict structure.

8) Once you are done merging, `add` and `commit` the changes to resolve the conflict
 - notice that it will take you into a special command line editor that will have a commit name suggestion.
 - to write/save the name of this commit and then quit the editor do the following:
	- press escape
	- type `:wq`
	- press enter
 - you should now be back at the normal command line
9) After the changes are made `push` the changes.

10) Get the merge conflict resolution changes re-reviewed by the team.

11) Team Member B merges the accepted `Pull Request`.

### Check point
Team member B has encountered and resolved a merge conflict.


### A merges first and C gets a merge conflict
Goal: In this block two different people will make different changes to the same line of a file. This would happen if both teammates saw an error with the line but had different ways to resolve the error.

1) Team member A creates a `branch` named `instructions-fix`

2) Team member C creates a `branch` named `chill-instructions`

3-Team Member A) Team member A makes the following changes:
- recipes/rick_and_morty_szechuan_sauce.md
	- ` - Strain, cover and let it cool down.` => ` - Strain, cover, and let it cool down.`

3-Team Member C) Team member B makes the following changes:
- recipes/rick_and_morty_szechuan_sauce.md
	- ` - Strain, cover and let it cool down.` => ` - Strain, cover and let it chill.`

4) The team members above `add`, `commit`, `push` and `Pull Request` their changes

5) All team members review and accept their teammate's `Pull Requests`

### Check point
Notice that everyone's pull request can be merged at this time. There are no conflicts.

6) Team member A merges the accepted `Pull Request`

### Check point
Notice that team member A's pull request can not be merged at this time.

- Team member C also wants to merge their `Pull Request` but they are unable to because of the `merge conflict`.
- To resolve a conflict you will generally want to work with the person that last made changes. In this scenario that would be Team Member A.
- You will see something like this in your file that Git has added:
```
<<<<<<< HEAD
 - Strain, cover and let it chill.
=======
 - Strain, cover, and let it cool down.
>>>>>>> master
```

7) Team Member C - Lets say you come to a consensus with your teammate and this is how the merge conflict will be handled:
- The line should be ` - Strain, cover, and let it chill.`. Not ` - Strain, cover, and let it cool down.` or ` - Strain, cover and let it chill.`

- To resolve this conflict replace the Git added block with what the line should be:
  ```
  <<<<<<< HEAD
   - Strain, cover and let it chill.
  =======
   - Strain, cover, and let it cool down.
  >>>>>>> master
  ```

  to =>

  ` - Strain, cover, and let it chill.`

- Make sure you always remove the general merge conflict structure.

8) Once you are done merging, `add` and `commit` the changes to resolve the conflict
- notice that it will take you into a special command line editor that will have a commit name suggestion.
- to write/save the name of this commit and then quit the editor do the following:
	- press escape
	- type `:wq`
	- press enter
- you should now be back at the normal command line

9) After the changes are made `push` the changes.

10) Get the merge conflict resolution changes re-reviewed by the team.

11) Team Member C merges the accepted `Pull Request`.

### Check point
Team member C has encountered and resolved a merge conflict.


# Well done!
Now that you and your team have completed the worksheet you should be a little more comfotable working on a project with Git as your version control system. The next steps are all up to you we recommend that you use Git with your next text based project(software, paper, blog) to really solidify your knowledge and get into the habit of using Git.


# Reference

### Local Workflow:
`git init`: put Git in this folder so that it keeps track of changes to files in this folder and subfolders

### Working Directory: the directory you’re writing code in
**Staging Area** or **index** : files are in the staging area if the changes in them will be included in the next save point

### Repository: everything Git is keeping track of
`git status`: show me which files have been changed and which ones are ready to be committed

`git add filename.txt`: include the changes to this file in the next commit

`git commit -m "commit message"`: wrap up all these changes and save them together with a short description of the changes

`git log`: show a history of all commits

`gitk`: show a history of all commits

`git diff`: show what is different from the last commit line by line

### Remote Repository
`git remote add origin address-of-remote`: make address-of-remote a new place to put my code and call it “origin”

`git push -u origin master`: push my code to the location origin points to, on the master branch, and also in the future I will pull code from this same location

**Upstream**: where I will pull code from in the future
Origin: where I put backups or share my code

`git pull`: grab code from another repository

`git fetch`: grab code from another repository

`git push`: save my history and changes in another location

**Fork**: I want a GitHub repo that looks like someone else’s repo

**Pull Request**: I made some changes that I would like you to include in your repository, please accept them

`git clone`: give me the code at this location

### Branching
`git branch`: what are all my branches? or what are all the names of the different versions of my code?

`git branch feature`: make a new branch/version of my code with the name feature

`git checkout feature`: move to that branch/version of my code so I can make changes to that branch/version of my code

**master**: the name of the branch which should be the official, working, well documented, version of my code

`git merge`: combine the history of two branches so I can have the changes from both in one place

**Merge Conflict**: Git does not know how to combine two histories and needs human assistance


## From Git to Github and back diagram

![git-and-github-flow-diagram](https://github.com/Maigard/git-class/blob/rough-draft-of-worksheet-instructions/git-and-github-flow-diagram.png "git-and-github-flow-diagram")
