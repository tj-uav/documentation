# Basic Usage

## Accessing a repository  

To clone a repository, run the following:

```text
git clone <repository url>
```

For example:

```bash
git clone https://github.com/tj-uav/Lectures.git
```

  To update a repository with the newest version, run the following:  


```text
git pull
```

To view the status of your repository, run the following:  


```text
git status
```

This tells you all the files you've changed \(in red\) and all the files you're ready to commit \(in green\)  
  To push something so that everyone else can see it, run  


```text
git add .
git commit -m <message>
git push
```

For the message, give a brief description of your push, for example "Add preprocessing code". **PLEASE DON'T PUSH UNLESS UR SURE ABOUT THE CONTENTS OF YOUR, IT IS ALWAYS A PAIN TO UNDO PUSHES**. Do not push unless you're 100% positive you want your changes .

Also, you can't push unless you've just pulled, so make sure you're always pulling before you start working. If you don't, merge conflicts may occur the next time you push, which are a total pain to resolve. Don't worry though, git will make sure it doesn't happen.  


To discard a change, run the following:  


```text
git stash
```

To retrieve the changes, run the following  


```text
git stash pop
```

{% hint style="warning" %}
Git stash is useful but often might mess things up in various manners. Though there's a place for stashing, try to stick with standard commits.
{% endhint %}

