#git rebase - there seem to be two schools of thought. The rebase camp and the merge camp.

One could argue there are two schools of thought for dealing with merge conflict. In one corner you have 'git merge'. In the other, you have 'git rebase'.

While a “git merge” may be the simplest way, it’s not always preferred - so knowing how to use “git rebase” is yet another notch in your belt of git mastery.

The prime argument in the battle between “git merge” and “git rebase” is the differences in your commit history.

Merging leaves your commit history intact - however, this can get unruly when you have a lot of commits.

Rebasing, on the other hand, presents a cleaner commit history - the caveat being “rebase” is rewriting your commit history.

One day you’ll find yourself in the fiery pits of merge commit hell. You’ll look up and see a glimmer of hope. You look closer to see the glimmer is a tiny shell with the command “git rebase” typed and ready for execution.

The “rebase” man page reads ““git rebase: Forward-port local commits to the updated upstream head.”

In other words, rebase will merge the requested branch (e.g. master) and apply your local commits to the top of the history. This is done without a merge commit (assuming there were no conflicts). The end result is a much tidier history.

And one more time to drive it home:

# not mine --- Rebasing is the process of moving or combining a sequence of commits to a new base commit. Rebasing is most useful and easily visualized in the context of a feature branching workflow. The general process can be visualized as the following:

You can greatly reduce the likelihood of merge conflicts by frequently committing your work. Should that happen you’ve still got some options to help get you back on track.

If you’re attempting to rebase and run into merge conflicts you can run “rebase —continue”. The rebase will proceed and you’ll have a merge commit - but it will contain useful information about the conflict and how it was solved.

Sometimes the rabbit hole is too deep and too scary. If your conflicts are bad and you need to try a normal merge, it’s quite simple. Running “git rebase —abort” will leave you right where you left off prior to attempting to rebase.

Using the —I flag for an interactive mode is a powerful tool when rebasing.

As mentioned above the resulting history is one of the biggest arguments for or against “git rebase”. Squashing multiple commits into one is made much simpler by running “git rebase -I”.

For example, git rebase -I HEAD~3

This will give you access to the last three commits. Now simply change “pick” to “squash” on the commit lines you want to be combined.  Save your work, and done! Those commits are now “squashed” into one. Your 







https://git-scm.com/book/en/v2/Git-Branching-Rebasing

https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase

https://help.github.com/articles/about-git-rebase/

https://nathanleclaire.com/blog/2014/09/14/dont-be-scared-of-git-rebase/

https://www.git-tower.com/learn/git/faq/rebase

