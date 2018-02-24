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


# [From Git to Github and back diagram](git-and-github-flow-diagram.png)

git-and-github-flow-diagram.png
