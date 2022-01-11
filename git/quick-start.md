Quick start with Git
----------------------

### To clone a branch:

Say you want a branch called *feature/add-search-filters*

```
git clone https://github.com/pinglue/monorepo.git

cd monorepo

git checkout feature/add-search-filters
```

Or alternatively you can combine the above two command into one:

```
git clone -b feature/add-search-filters https://github.com/pinglue/monorepo.git

cd monorepo
```

Note that using `git checkout` you can switch between branches. Before doing a project make sure you are in the right branch. To double-check which branch you are in, from the project root run:

```
git branch
```

The above command shows a list of branches downloaded, and the current branch has a * beside it.


### Commit/Push changes
Once you made your changes you need to push the changes to the repository. From the project root folder:

```
git add .
git commit -m "your commit message"
git push
```

AT this point you will need to enter username/password

>**NOTE:** Github no longer accepts username/password like before. You need to use *token* now. The easiest way to use a token is to get the token from the Github site (make sur eyou check all the privilegs just in case) and use this token instead of your password when using the terminal.

>**TIP:** If you use VScode, the Github extension on it will automatically takes care of token and authentication (after a few rounds of refering you to the Github site, etc), and after that it magically connects to the repo and you can push/pull/etc with just a click. You wanna use VSCode for normal git operations

Then using browser navigate to your repo on Github and create a "pull request". When you create a pull request, others can see what changes you made in your branch and give you feedback. You may need to make additional changes and push again (using the commands above). When we approve your changes then we will "merge" your changes into the main branch, and basically your code will be included in the main version of the program.

### Pull changes - conflict resolution

To download the latest changes from the online repository (upstream repo) to your computer use the following command from the project root:

```
git pull
```

The above command is useful if you have an old clone of the repository and some changes are made to the online repo after your cloning. In this case use the above command instead of cloning a whole new project.

### Syncing

Sometimes it may so happen that while you are working on your branch we push/merge some new changes in the main branch. To get these changes in your branch you need to "rebsae" your branch to the main branch:

```bash
# making sure you are in your branch, assuming your branch name is feature/adding-ng-guard
git checkout feature/adding-ng-guard

# fetching (downloading) latest changes from the repo
git fetch

# rebase your branch to the main branch
git rebase origin/main

```

or you can combine the last two commands into one:

```bash
git checkout feature/adding-ng-guard
git pull --rebase origin main
```

If conflicts happen, then the above command shows a list of conflicted files. These files will contain "conflict-markers". You need to open these files using some IDE editor (like VS code or WebStorm) and these editors will show you the conflicting parts and ask you to choose one of the possible options for each conflict (by clicking on buttons). Once you resolve these conflicts save your files. Then commit/push again to your branch (see the previous section) and the conflicts are resolved.