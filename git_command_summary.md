## This notebook summarizes the commonly used Git commands in version control



A quick look at the commands

- Initialize repo `git init`
- Check current status `git status`
- Link local repo to remote repo `git remote add <remote_url>`
- Add new/modified file `git add <filename>` or `git add .`
- Remove file `git rm <file_path>`
- Move/rename file `git mv <old_path> <new_path>`
- Commit changes `git commit -m <message_for_the_commit>`
- Push changes to remote branch `git push origin <remote_branch>`
- See all commit history `git log`, you can add options such as `--oneline` and `--graph`
- Reverse the status of the untracked file to the latest commit `git checkout -- <file_path>`
- Unstage the tracked file `git reset HEAD <file_path>`
- Reverse the repo to one previous commit `git reset --hard <commit_id>`
- Show the commit information `git show <commit_id>`
- Create tag for commit `git tag <tag_name> <commit_id>` , delete tag `git tag -d <tag_name>`
- Create branch `git branch <branch_name>` , check local branch `git branch` , check local and remote branch `git branch -av`  , delete branch `git branch -d <branch_name>` , swtich branch `git checkout <branch_name>` 
- Merge <branch_to_merge> to current branch `git merge <branch_to_merge>`
- Delete unwanted branch in the remote repo `git push origin --delete <branch_to_delete>`

- Fetch all branches in the remote repo `git fetch`



#### Working scenario

- Normal work flow (It's a good habit to use `git status` before adding files and commit changes)

```
continue your normal work flow
git status
git add .
git commit -m <message>
```



- See changes for a particular file before and after the latest commit

```
git log --pretty=oneline <file_path>  ## this return the latest commit id
git show <commit_id>

git log -p <file_path>
```



- Reverse the repo to the previous commit

```
git log ## to get the commit id you want to reverse
git reset --hard <commit_id>
```



- Reverse the file to the previous commit

```
git log ## to get the commit id you want to reverse
git checkout <commit_id> -- <file_path>
```



- Create a new branch for a new feature and merge to master branch

```
git branch <new_branch>
git checkout <new_branch>
continue your development
git add .
git commit -m <message>
git checkout master
git merge <new_branch>
```



- Resolve merge conflict

```
resolve your merge conflict in the file
git add .
git commit
add the information to the log and save the log
git push 
```



- Fetch all branches and work on a particular branch

```
git fetch
git checkout -b <branch_to_switch> <remote_branch_to_link>
normal work flow ...
```



#### Chrome extension for better experience with Github

Octotree, Enhanced GitHub, Gitzip for GitHub