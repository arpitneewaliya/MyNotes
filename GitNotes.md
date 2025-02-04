# A Complete guide to Git and GitHub
These are my personal notes that I have prepared to help me in learning Git and GitHub. These notes will be extremely helpful to me in the future for reference.
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
$ git config --global user.name "Your Name"
$ git config --global user.email "your.name@gmail.com"
```

This username will appear on all your commits.

## Important Git commands
1. `git status` - Shows the status of the working directory (untracked, modified, or staged files).
```bash
$ git status
```
```bash
On branch main

No commits yet

Untracked files:
  (use "git add ..." to include in what will be committed)
    index.html

nothing added to commit but untracked files present (use "git add" to track)
```
2. `git add <filename>` - Stages changes for the next commit.
```bash
$ git add README.md
```
3. `git commit -m "message"` - Commits staged changes with a message.
```bash
$ git commit -m "Update README.md"
```

```bash
[main 1a2b3c4] Update README.md
 1 file changed, 2 insertions(+), 1 deletion(-)
```

4. `git push` - Pushes local commits to a remote repository.
```bash
$ git push origin main
```

```bash
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 300 bytes | 300.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/user/repo.git
   1a2b3c4..4d5e6f7  main -> main
```

5. `git pull` - Fetches and merges changes from a remote repository to your local branch.
```bash
$ git pull origin main
```

```bash
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
Unpacking objects: 100% (3/3), 300 bytes | 300.00 KiB/s, done.
From https://github.com/user/repo
   1a2b3c4..4d5e6f7  main     -> origin/main
Updating 1a2b3c4..4d5e6f7
Fast-forward
 README.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```

6. `git branch` -  Lists all local branches (the current branch is highlighted with `*` ).
```bash
$ git branch
```

```bash
* main
  feature-branch
```

7. `git checkout <branch>` - Switches to the specified branch.

```bash
$ git checkout feature-branch
```

```bash
Switched to branch 'feature-branch'
```

8. `git merge <branch>` - Merges the specified branch into the current branch.

```bash
$ git merge feature-branch
```
```bash
Updating 1a2b3c4..4d5e6f7
Fast-forward
 file.txt | 1 +
 1 file changed, 1 insertion(+)
```
