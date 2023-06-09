# Git Cheat Sheet



<br><br>

## **compare / diff / log**
<hr><br>

Display diff between staging area and working directory
```bash
git diff --staged
```

RIGHT OUTER JOIN **branch_A** ON **branch_B**
```bash
git log branch_B..branch_A
git diff branch_B...branch_A
```

Show commit logs with paths that moved
```bash
git log --stat -M
```



<br><br>



## **Interact with remote**
<hr><br>


Add a git URL as a remote named *[alias]*
```bash
git remote add [alias] [URL]
```

Publish a local branch onto the remote, and set it as upstream
```bash
git push --set-upstream origin [branch]
```
<br>

Delete a remote branch
```bash
git push origin --delete [branch]
```

Print detailed info of the remote & its content (remotes branches for example)
```bash
git remote show origin
```

<br><br>



## **Interact with upstream**
<hr><br>

List all remotes & upstreams
```bash
git remote -v
```

Add an *upstream*, from a fork for example
```bash
git remote add upstream https://github.com/[user]/[project].git
```

Pull from *upstream*
```bash
git fetch upstream
git merge upstream/[branch]
```

<br><br>



## **revert / reset / rm**
<hr><br>


Commit the opposite of commit \<ref\>
```bash
git revert <ref>
```

Unstage all staged files
```bash
git reset <ref>
```

Unstage \<file\>
```bash
git reset HEAD <file>
```

Voids the last **N** commits
```bash
git reset --hard [HEAD~N]
```

Rollback and stage everything
```bash
git reset --soft [HEAD~N]
```

Rollback and don't stage
```bash
git reset --mixed [HEAD~N]
```

Interactive rollback. Pick an action for each rollbacked commit 1-by-1
```bash
git reset --keep
```

Dry-run of `rm`
```bash
rm -n
```

<br><br>



## **stash**
<hr><br>

Save current non-staged edits into the stash
```bash
git stash push (-m [message])
```

List all stash entries
```bash
git stash list
```

Show the content of a stash entry
```bash
git stash show [<stash@entry>]
```

Apply a stash entry, and remove it from stash
```bash
git stash pop [<stash@entry>]
```

Apply a stash entry, but keep it in the stash
```bash
git stash apply [<stash@entry>]
```

Apply a stash entry on top of its parent commit, on a new branch
```bash
git stash branch <new_branch> [<stash@entry>]
```

Delete a stash entry
```bash
git stash drop
```

Delete the entire stash
```bash
git stash clear
```

<br><br>



## **Misc**
<hr><br>

Copy a commit onto the current branch
```bash
git cherry-pick [commit_ID]
```

Quickly find which commit introduced a bug
```bash
git bisect (command)
```

Find which commit deleted \<file\>
```bash
git rev-list HEAD -n 1 -- <file>
```
