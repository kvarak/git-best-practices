
# Git is cool. But how do we use it?

![https://xkcd.com/1597/](https://imgs.xkcd.com/comics/git.png "If that doesn't fix it, git.txt contains the phone number of a friend of mine who understands git. Just wait through a few minutes of 'It's really pretty simple, just think of branches as...' and eventually you'll learn the commands that will fix everything.")

https://xkcd.com/1597/

## Do's and Dont's when using Git

- Commit early and often
  - "Commit small" or "One change, one commit" is an approach that results in this, but has a tangible benefit with regards to reverting, cherry-picking, etc.
- Use rebase as your default merge
  - This comes up often in tips (`pull -r`, only fast forward merge, etc). You could change your git config settings to set rebase as default merge, however, I'm not really a fan. I've seen wordings that state "always rebase, don't merge", but that makes it sound like "merge is bad", which it isn't, but has it's uses. But your default way of thinking should be to rebase.
- But don't rewrite published history multiple people work on.
  - That's the general rule, but that's more or less a rule for the branches that needs to be "steady". Rebasing a feature branch that have been pushed while "work-in-progress" is in most cases fine.
- Create a branch, don't work on master locally, it'll be easier later.
- Update your local repo before you start working (`git pull -r`)
  - Update your master, then update your local branch that you work on (with rebase please).
- Only fast-forward to master
- Interactively rebase your local branch to make sure your commit history is nice and correct (`git rebase master -i`)
- Have the habit to delete branches that aren't needed. Good branch hygiene. Both locally and remote.
  -  `git fetch --prune` is your friend.
- Pick a workflow, and use it. If you have one, read up on it.
- Keep up to date - pull often
- Read the output from the Git commands. `git status` is your friend, use it often
- Unsure what will happen? Try it! Don't want to risk your files? Try it out in a different clone first.
  - Unsure what happened? Learn how to use `git reflog` to investigate.
- Git is not an artifact management system
  - Avoid large binaries (Word documents are binaries)
  - Don't commit auto generated files if they can be generated on the fly
- HEAD is where the changes should happen. Stand on the branch you want to change. 
- Before commiting, review your changes with `git status` followed by `git diff` to make sure you'll commit what you want to change.
  - Learn and get into the habit of using `git add -p`
- Use Tags to mark releases, instead of creating a branch "just in case".
- Create Git aliases to make your life easier
- Use pull requests if it makes sense. But don't use PRs as the quality tollgate.
- Push to remote as often as you can, you don't want your colleagues to suffer a "big bang merge"
- Protect your remote master and other important branches from direct pushes (especially force pushes).
  - Protecting from force pushes is a setting on the Git server (GitHub)
  - Protecting from direct pushes needs a CI that does the pushes for you.
- Learn how to write a Git commit message - https://chris.beams.io/posts/git-commit/
- Make sure your .gitconfig is up to date for what you're developing in. https://www.gitignore.io/
- Sharpen your Git skills by practising often: https://github.com/praqma-training/git-katas/

## More reading

- http://opinionatedgit.com/
- https://dangitgit.com/en
