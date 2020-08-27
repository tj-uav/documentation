# Advanced Usage

**Branches**

Branches are subdivisions of repositories. Generally the `master` branch is reserved to the "best, working code." If you're pushing to it willy-nilly without getting approval from your teammates, you're doing something wrong.  For code more in development, branches work well. They allow different users to work simultaneously and make an easily traceable path of code, and help to avoid merge conflicts. 

To move to another branch \(`git branch -a` to view all the branches\), simply use the following:

```text
git checkout <branchName>
```

Another trick is the `-b` flag, which makes a new branch and even enters it for you!

```text
git checkout <newBranchName>
```

If you just want to make a new branch though, just do the following:

```text
git branch <newBranchName>
```

Need to delete a branch for whatever reason? The `-d` flag has you covered:

```text
git branch -d <branchNameToDelete>
```

Branch creation and deletion can also be done on the web GitHub interface, and even make it easy to deal make sure you're not doing something wrong. But it could also be easy to delete some work on accident, so be careful.

{% hint style="warning" %}
Make sure to push your branch changes to the repository once you make it.
{% endhint %}

**Issues**

Issues are used to manage problems that are currently present in a repo. Issues can be about any problems with the repository, including changes in code structure, functionality that still needs to be implemented, or errors in code that need to be fixed. Issues can be created by anyone and assigned to anyone, but they can only be closed by admins.

These are best managed on the GitHub interface in the Issues tab for each repository, to the point where it's self explanatory how to use it. However, use the following tips:

1. Keep the issues formal, we need it to be as clear as possible, we want to make sure every programmer knows exactly what the complaint is.
2. Keep the tags accurate.
3. Try to use milestones where possible to keep track of progress. This is optional but in the push to leverage the features of Issues it's a good idea.
4. Actually assign the right people to the Assignees. It's surprising to see that having the right people actually make a difference.

**Pull Requests**

When you want to merge your branch's changes into master \(or for that matter any branch into another\), you need to submit a pull request. A pull request entails that an admin will look through your code and make sure it is working and appropriate for the master branch \(it'll be used in the final competition code\). Pull requests will only be accepted if 1\) your code has been thoroughly tested, 2\) your code has been thoroughly documented, 3\) all issues relating to your code have been closed, and 4\) multiple people have reviewed your code. 

Especially for pushes to `master` of any repository multiple people will need to verify your code - your lead, the section programming lead, and someone from your subteam to verify as well. This is to ensure quality of the code used in competition

