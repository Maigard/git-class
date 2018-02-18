# Worksheet Instructions

You will need a computer to participate in the worksheet exercises.

You will be paired into a team of `2-3` people. Each member in your team will be assigned a letter `A`, `B`, or `C`.

You and your team will follow the worksheets and work together to complete all of the steps.

At any given point in the exercise you will either be a `Driver` or an `Observer`.

`Driver`: Person preforming commands

`Observer`: Person observing commands

You are a driver when it is your turn to follow your worksheet. You are an Observer when someone else in your team is the Driver. It is important that you understand what the worksheet is trying to have you accomplish when you are driving as well as what your teammate(s) is/are trying to accomplish when you are observing.

TODO - add a note on how this workflow differs from day 1


# Example Process

## Setup

1) Team member A forks the demo repository(https://github.com/harokevin/recipes)
2) Team member A gives team member B access to team member A's fork on GitHub
3) Team member A and B clone team member A's online fork onto their computers
- Check Point: Do all teammates have a version of the fork on their computers?


## Making changes and opening a pull request
1) Team member A makes the first set of changes then opens a `Pull Request`
	- Create a `branch`
	- Make content changes
	- `add` changes, stage changes
	- `commit` changes, save changes
	- `push` changes to the remote/GitHub
	- Open a `Pull Request` on GitHub
2) Team member B reviews and accepts the `Pull Request`
  - Notice how the changes are added to the existing content
3) Team member A merges the `Pull Request` into `master`
4) Repeat steps the previous steps but B makes changes and merges and A accepts
- Check point: Has everyone merged 2 `Pull Requests`?
- Check point: Is everyone up to date with master?

## Merge conflict and resolution

 - When you are working with others in a single file you might encounter a `merge conflict`. This is when you have both modified a file and Git does not know what to do so you have to help it out.
 - More precisely, a `merge conflict` occurs when you start with the same file as another and they modify it behind your back and merge it into master before you. Then, when you want to merge your changes into master you might encounter a `merge conflict` because the file was modified in two different ways.
 - Although merge conflicts do not always happen when working in the same file as another team mate it is important to know how to resolve them for when they do happen.

### A merges first and B gets a merge conflict
1) Team member A creates a `branch` named `fix-typos`
2) Team member B creates a `branch` named `typo-fix`
3-Team Member A) Team member A makes the following changes:
	- recipes/rick_and_morty_szechuan_sauce.md
	 ` - Gresh ginger` => ` - Fresh ginger`

3-Team Member B) Team member B makes the following changes:
	- recipes/rick_and_morty_szechuan_sauce.md
	 ` - Gresh ginger` => ` - Gresh ginger paste`

4) All team members `add`, `commit`, `push` and `Pull Request` their changes
5) All team members review and accept their teammate's `Pull Requests`
- Check point: notice that everyone's pull request can be merged at this time. There are no conflicts.
6) Team member A merges the accepted `Pull Request`
- Check point: notice thatTeam member B's pull request can not be merged at this time.
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
	The line should be `- Fresh ginger paste`. Not `- Gresh ginger paste` or ` - Fresh ginger`

	To resolve this conflict replace the Git added block with what the line should be:
		```
		<<<<<<< HEAD
		 - Gresh ginger paste
		=======
		 - Fresh ginger
		>>>>>>> master
		```

		to =>

		`- Fresh ginger paste`

	Make sure you always remove the general merge conflict structure.

8) Once you are done merging, `add` and `commit` the changes to resolve the conflict
 - notice that it will take you into a special command line editor that will have a commit name suggestion.
 - to write/save the name of this commit and then quit the editor do the following:
  	-- press escape
		-- type `:qw`
		-- press enter
 - you should now be back at the normal command line
9) After the changes are made `push` the changes.
10) Get the merge conflict resolution changes's re-reviewed by the team.
11) Team Member B merges the accepted `Pull Request`.
- Check point: Team member B has encountered and resolved a merge conflict.


### B merges first and A gets a merge conflict
Repeat the scenario above but swap roles

1) Team member A creates a `branch` named `ammend-chili`
2) Team member B creates a `branch` named `fix-chili-pow`

3-Team Member A) Team member A makes the following changes:
	- recipes/rick_and_morty_szechuan_sauce.md
	 ` - Chili paste (if you’re looking for heat)` => ` - Chili paste`

3-Team Member B) Team member B makes the following changes:
	- recipes/rick_and_morty_szechuan_sauce.md
	 ` - Chili paste (if you’re looking for heat)` => ` - Chili powder (if you’re looking for heat)`

These changes will result in a merge conflict that looks something like this:
```
<<<<<<< HEAD
 - Chili paste
=======
 - Chili powder (if you’re looking for heat)
>>>>>>> master
```

the resolution to this merge conflict will look like

```
<<<<<<< HEAD
 - Chili paste
=======
 - Chili powder (if you’re looking for heat)
>>>>>>> master
```

to =>

`Chili paste or powder`




### C merges first and B gets a merge conflict
Repeat the scenario above but swap roles

1) Team member C creates a `branch` named `sugar-fix`
2) Team member B creates a `branch` named `fix-packed-sugar`

3-Team Member C) Team member A makes the following changes:
	- recipes/rick_and_morty_szechuan_sauce.md
	 ` - 4 tbs of brown sugar` => ` - 6 tbs of brown sugar`

3-Team Member B) Team member B makes the following changes:
	- recipes/rick_and_morty_szechuan_sauce.md
	 ` - 4 tbs of brown sugar` => ` - 4 tbs of packed brown sugar`

These changes will result in a merge conflict that looks something like this:
```
<<<<<<< HEAD
  - 4 tbs of packed brown sugar
=======
  - 6 tbs of brown sugar
>>>>>>> master
```

the resolution to this merge conflict will look like

```
<<<<<<< HEAD
  - 4 tbs of packed brown sugar
=======
  - 6 tbs of brown sugar
>>>>>>> master
```

to =>

`- 6 tbs of packed brown sugar`


### A merges first and C gets a merge conflict
Repeat the scenario above but swap roles

1) Team member A creates a `branch` named `instructions-fix`
2) Team member C creates a `branch` named `chill-instructions`

3-Team Member A) Team member A makes the following changes:
	- recipes/rick_and_morty_szechuan_sauce.md
	 ` - Strain, cover and let it cool down.` => ` - Strain, cover, and let it cool down.`

3-Team Member C) Team member B makes the following changes:
	- recipes/rick_and_morty_szechuan_sauce.md
	 ` - Strain, cover and let it cool down.` => ` - Strain, cover and let it chill.`

These changes will result in a merge conflict that looks something like this:
```
<<<<<<< HEAD
 - Strain, cover and let it chill.
=======
 - Strain, cover, and let it cool down.
>>>>>>> master
```

the resolution to this merge conflict will look like

```
<<<<<<< HEAD
 - Strain, cover and let it chill.
=======
 - Strain, cover, and let it cool down.
>>>>>>> master
```

to =>

` - Strain, cover, and let it chill.`


 - Check point: make sure everyone in your team has encountered a merge conflict and also been the person to merge first(not encounter the merge conflict.)

# TODO Formatting

## Tips

Be patient with your team. This is not a race. We are all in the same boat trying to learn new skills.

If you get stuck or something seems off ask one of the helpers.
