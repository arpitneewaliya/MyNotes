# A Complete guide to Git and GitHub
## What is Git?
> Git is a version control system.
Git helps you keep track of code changes.
Git is used to collaborate on code.

Git is a popular version control system.
It was created by *Linus Torvalds* in 2005,
and has been maintained by *Junio Hamano* since then.

It is used for:
- Tracking code changes
- Tracking who made changes
- Coding collaboration

## Using Git with command line
To start using Git, we are first going to open up our Command shell.

For Windows, you can use Git bash, which comes included in Git for Windows. For Mac and Linux you can use the built-in terminal.

The first thing we need to do, is to check if Git is properly installed:

```bash
$ git --version
```

This shows the version of git you have.

---
### Configure Git
Now let Git know who you are. This is important for version control systems, as each Git commit uses this information:


```bash
git config --global user.name "Your Name"
git config --global user.email "your.name@gmail.com"
```

This username will appear on all your commits.

## Important Git commands
1. `git status` - Shows the status of the working directory (untracked, modified, or staged files).
```bash
git status
```
```bash
On branch main

No commits yet

Untracked files:
  (use "git add ..." to include in what will be committed)
    index.html

nothing added to commit but untracked files present (use "git add" to track)
```
