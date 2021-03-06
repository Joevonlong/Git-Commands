Git related Commands
============

_A list of my commonly used Git commands_


## Content
[Git Commands](#gitcommands)

- [Getting & Creating Projects](#creating)
- [Basic Snapshotting](#basicsnapshot)

[SSH Commands](#sshcommands)


## Tutorials and Handbooks
- [廖雪峰的官方网站-Git](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
- [Git Documentation Book](https://git-scm.com/book/en/v2)


## Git Commands <a id="gitcommands"/>

### Getting & Creating Projects  <a id= "creating"/>


| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |



### Basic Snapshotting <a id="basicsnapshot"/>

| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
| `git add [file-name.txt]` | Add a file to the staging area |
| `git add -A` | Add all new and changed files to the staging area |
| `git commit -m "[commit message]"` | Commit changes |
| `git rm -r [file-name.txt]` | Remove a file (or folder) |

### Branching & Merging

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch |
| `git push origin --delete [branchName]` | Delete a remote branch |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |
| `git merge origin/yourbranch ` | Merge remote yourbranch into current local branch |
| `git stash` | Stash changes in a dirty working directory |
| `git stash clear` | Remove all stashed entries |

### Sharing & Updating Projects

| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git diff [source branch] [target branch]` | Preview changes before merging |

### git fetch


>
$ git fetch origin master
>
$ git log -p master..origin/master
>
$ git merge origin/master


以上命令的含义：

首先从远程的origin的master主分支下载最新的版本到origin/master分支上
然后比较本地的master分支和origin/master分支的差别
最后进行合并.


#### git diff


#### git config

#### git merge
- [git-merge完全解析](https://www.jianshu.com/p/58a166f24c81)

#### git log
查看所有的commit 信息

## SSH <a id="sshcommands"/>

### some tutorials
[简书 - Git的多SSH Key解决方案(macOS)](https://www.jianshu.com/p/95e00370fa2c)

[Github - Checking for existing SSH keys](https://help.github.com/en/articles/checking-for-existing-ssh-keys)  

[Github - Generating a new SSH key and adding it to the ssh-agent](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

[Github - Adding a new SSH key to your GitHub account](https://help.github.com/en/articles/adding-a-new-ssh-key-to-your-github-account)

[Gitlab - SSH Introduction](https://gitlab.com/help/ssh/README)

| Command (on MacOS) | Description |
| ------- | ----------- |
| ssh-keygen -t rsa -f ~/.ssh/id_rsa.github -C "your-email-address@example.com" | Generate SSH key pair |
| eval $(ssh-agent -s)| Check env | 
| ssh-add ~/.ssh/other\_id_rsa | Add generated SSH key |
| touch ~/.ssh/config | creat SSH configration file |
| ssh -T git@github.com | test whether your SSH key was added correctly |
| pbcopy < ~/.ssh/id_ed25519.pub | Copy your public SSH key to the clipboard |
| xclip -sel clip < ~/.ssh/id_ed25519.pub | Copy your public SSH key to the clipboard ( WSL / GNU/Linux (requires the xclip package)) |
| cat ~/.ssh/id_ed25519.pub \| clip | Copy your public SSH key to the clipboard ( Git Bash on Windows) |


config file looks like :
> 
#
\# github
#
Host github.com
IdentityFile ~/.ssh/id_rsa_github
#
\# company gitlab
#
Host gitlab.company.com
IdentityFile ~/.ssh/id_rsa_gitlab



