# Basic Usage \(Finish me!\)

Git isn't an easy thing whatsoever. However, take the time, and you'll discover it becomes the most powerful tool TJUAV has.

## Installation

1. Install git. This varies for Mac and Windows.
2. For windows, use this link \([https://gitforwindows.org/](https://gitforwindows.org/)\) and get the "Git for Windows setup" one. When you're given the option, choose to use git from windows command line \(NOT using gitbash\)
3. For Mac, first install brew using

```text
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew doctor
```

  4. Then install git using

```text
brew install git
```

  5. Run "git --version" in your command line to confirm that git installed properly and is working  
  6. To clone a repository, run

```text
git clone <repository url>
```

For example:

```text
git clone https://github.com/tj-uav/Lectures.git
```

  7. To update a repository with the newest version, run  


```text
git pull
```

  8. To view the status of ur repository, run  


```text
git status
```

This tells you all the files you've changed \(in red\) and all the files you're ready to commit \(in green\)  
  9. To push something so that everyone else can see it, run  


```text
git add .
git commit -m <message>
git push
```

For the message, give a brief description of your push, for example "Add preprocessing code". PLEASE DONT PUSH UNLESS UR SURE ABOUT UR PUSH, ITS A PAIN TO UNDO PUSHES. Also, you can't push unless you've just pulled, so make sure you're always pulling before u start working. If you don't, merge conflicts will occur, which are a megapain and not fun.  
10. To discard a change, run  


```text
git stash
```

WARNING: whenever u discard changes, it's hard to retrieve them. You can do  


```text
git stash pop
```

but that might mess things up, so always commit and push changes you wanna keep.

