# Common Issues \(Finish me!\)

### Merge Conflicts

### Undo commit

If you're reading this, that means you've really screwed up. Not in making a frivolous commit that contains something it shouldn't have, rather in the time git punishes you for such a mistake. 

Now here's where you might be lucky. If you didn't push to GitHub yet, all you need to do is the following:

```text
git reset --soft HEAD~1
```

This here will undo that last commit, as if it never happened. The `--soft` flag keeps everything that would have been pushed \(i.e. pre-push state\). To revert to what the previous push would have looked like without the changes you made, replace `--soft` with `--hard`.

Now let's say you already pushed to the GitHub \("remote"\) repositories. If it's a non-sensitive mistake, just make another commit that fixes it. Not completely sure what constitutes a sensitive mistake? Basically no large files \(makes cloning the repository take an incredible amount of time, see the CV repository, 712 MiB at time of writing\), passwords, or anything that reveals a major flaw in security. 

{% hint style="info" %}
It's best practice to just fix the mistake, but if need be `git revert` also generates an automatic commit revert. This won't remove the commit completely; rather, just undo the changes. It's an easy way of going back without loosing progress or interrupting anyone else's workflow. **This means files no longer part of the repository will still be downloaded, hence why large files have to be removed with the next steps.**
{% endhint %}

### Had to get here? Here's where it starts to become a total pain.

{% hint style="danger" %}
Any steps from here on should be additionally accompanied by a ping to everyone on Slack saying that this change has been made. This **WILL** effect the workflow of all users and means **EVERY SINGLE PERSON** will have to make sure they didn't pull what you had now since completely removed.  
  
And yes, this is perhaps one of the only times where it is completely appropriate to perform an @everyone ping.
{% endhint %}

#### Remove previous commit

```text
git push <repo clone address> +<commitID to remove>^:<branch>
```

This should in theory push the branch back commit and practically destroy the very existence of the commit. There's other ways to do this but this is probably the safest method only if you know no other commits were made up to this point.

#### Remove older commit

Let's say you realize that it wasn't the latest commit but instead one that's a bit older. Start out with the following, where `commitID` is the ID of the commit that you want removed:

```text
git rebase -i <commitID>^
```

This brings up an editor with a list off all the commits made since that one.

{% hint style="warning" %}
This editor's probably `vi`, which can be notoriously difficult to use sometimes. To be clear, this is not `vim` which can be found rather commonly, so it might be even more unfriendly than some users realize. `vim` basics still apply. Though it can be incredibly powerful, don't worry about needing to learn how to leverage it.
{% endhint %}

Use the arrow keys to put your cursor on the line that has the commit ID of the commit you want to remove, then type `dd`. Don't worry, you won't add anything, as you aren't in insert mode. Then type `:wq` \(command, write, quit\) and press `enter` to exit.

Finally, force push the branch with the following command.

```text
git push <branch> -f
```

{% hint style="danger" %}
As mentioned earlier, an @everyone ping is appropriate to ensure all programmers pull this edit and make sure your force push doesn't break their code. To be clear force pushing should be reserved for the most terrible of situations. 
{% endhint %}

