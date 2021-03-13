---
description: 'Using Git to access, edit, and publish changes'
---

# Git

## Cloning

To access any repositories on your PC, the first thing you need to do is clone them.

To clone a repository, you will first need to get its clone URL. First, visit the repository page \(Example: `https://github.com/tj-uav/repo-name`\). Then, Click on the `Code` button, and copy the HTTPS URL.

To actually clone the repository, you will need to open either a Terminal or a Git Bash Console. Next, you should navigate to the directory where you want to clone the repository. Here, you should run the following command, where &lt;url&gt; is the repository URL you copied from the previous step.

```text
git clone <url>
```

Now, the repository is succesfully cloned to your PC in your chosen directory.

## Pulling

When working with a team, there are often new changes made by other team members that you will need to use to continue working. To update your cloned repository's code with the cloud, you will need to pull changes.

The simplest way to pull changes is by simply using this command:

```text
git pull
```

As long as the terminal or Git Bash Console is open inside a cloned directory, the directory will be updated with the most recent changes from the cloud.

