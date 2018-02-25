## [Instructions](worksheet-instructions.md)

## Setup

1) Team member A forks the demo repository from https://github.com/harokevin/recipes
<!-- TODO link fork screenshot -->

2) Team member A gives team member B access to team member A's fork on GitHub
<!-- TODO link collaborators screenshot -->

3) Team member A and B clone team member A's online fork onto their computers
<!-- TODO link copy url and clone screenshot -->

### Check Point
Do all teammates have a version of the fork on their computers?


## Making changes and opening a pull request
Goal: In this block one person will add an instruction to a recipe in the repository

1) Team member A makes the first set of changes then opens a `Pull Request`
- Create a `branch` - name it after what you want to accomplish (no spaces). `add-instruction-to-cookies`

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

2) Team member B reviews and accepts the `Pull Request`
  - Notice how the changes are added to the existing content

3) Team member A merges the `Pull Request` into `master`
  - There are a few options here but lets go with the simplest one for now, create a merge commit.

### Check point
Is everyone up to date with master?
- Use `git pull` to sync with the GitHub repository

### Recap
In this block one person created a branch, made a commit locally, pushed the commit to GitHub, opened a GitHub pull request around that commit, got the pull request reviewed by a teammate and merged their changes into the project.

4) Repeat the previous steps but B makes changes and A reviews the `Pull Request`

5) Repeat the entire drill again so that by the end everyone has merged into master twice. This entire piece of work should consist of A making a change and merging, B making a change and merging, then A making a change and merging again, and finally B making a change and merging.

- Check point: Has everyone merged 2 `Pull Requests`?

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

4) All team members `add`, `commit`, `push` and `Pull Request` their changes

5) All team members review and accept their teammate's `Pull Requests`

### Check point
- Notice that everyone's pull request can be merged at this time. There are no conflicts.

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

  `- Fresh ginger paste`

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

4) All team members `add`, `commit`, `push` and `Pull Request` their changes

5) All team members review and accept their teammate's `Pull Requests`

### Check point
- Notice that everyone's pull request can be merged at this time. There are no conflicts.

6) Team member B merges the accepted `Pull Request`

### Check point
- Notice that team member A's pull request can not be merged at this time.
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

  `Chili paste or powder`

- Make sure you always remove the general merge conflict structure.

8) Once you are done merging, `add` and `commit` the changes to resolve the conflict
- Notice that it will take you into a special command line editor that will have a commit name suggestion.
- to write/save the name of this commit and then quit the editor do the following:
	- press escape
	- type `:wq`
	- press enter
- you should now be back at the normal command line
9) After the changes are made `push` the changes.
10) Get the merge conflict resolution changes re-reviewed by the team.
11) Team Member A merges the accepted `Pull Request`.

### Check point
- Team member A has encountered and resolved a merge conflict.


### Check point
- Make sure everyone in your team has encountered a merge conflict and also been the person to merge first(not encounter the merge conflict.)


# Well done!
Now that you and your team have completed the worksheet you should be a little more comfotable working on a project with Git as your version control system. The next steps are all up to you we recommend that you use Git with your next text based project(software, paper, blog) to really solidify your knowledge and get into the habit of using Git.


## Command Reference


## From Git to Github and back diagram

![git-and-github-flow-diagram](https://github.com/Maigard/git-class/blob/rough-draft-of-worksheet-instructions/git-and-github-flow-diagram.png "git-and-github-flow-diagram")
