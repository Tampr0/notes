
# GIT
##### INITIAL SETTINGS
- `git init` - create an empty repository
- `git config --global user.name "your name"`
- `git config --global user.email "your email"`
##### BASIC COMMANDS
- `git diff --cached` - check what is about to be commited
- `git diff` - shows any changes but not yet added to index
- `git status` - same as diff
- `git add .` - take a snapshot of the contents to the index
- `git commit` - permanently store the contents
- `git commit -a` - any modified (but not new) are added to index and commit
When commiting, after `-m`, type single short line summarizing the change. After that, use second `-m` to put a blank line and type a more specific desciption. If you won't close the quotes, you can break lines if necessary.
##### LOGS
- `git log` - view the history of changes
- `git log -1` - should print your commit message.
- `git-format-patch(1)` - should send an email with commit message.
- `git log -p` - see the diffs at each step
- `git log --stat --summary` - overview of the change
##### REMOTE REPO
- `git remote -v` - print the list of remotes repositories
- `git remote set-url heroku <new_path>` - change remote repository's path
##### OTHER
When you'd like to experiment with implementations:

- `git branch experimental` - creates new branch named newone
- `git branch` - print list of all branches
- `git switch <branch_name>` - switch to chosen branch

When you change the branch, edit a file, commit the change and switch back to master branch, you'll notice that change you've made is no longer visible. 
If you make a different change on master branch and commit these changes, the two branches will diverge.
To merge the changes run 
`git merge experimental`. 
If the changes don't conflict, you're done. If there is conflict, markers will appeared in the problematic files (`git diff`)
After resolving conflicts, use `git commit -a` to commit the result of the merge. Check the history in a nice graphical representation using `gitk`.
Now you can delete `experimental branch` simply using `git branch -d experimental`
- `git branch -D crazy-idea` - probably forcing the deletion, check it!.

###Collaboration
Suppose there is a repo in `/home/alice/project` and someone wants to contribute.


- `git clone /gome/alice/project myrepo` - creates new directory "myrepo" containing Alice's repository (it posses the original project's history).
After making some changes and commits them, `myrepo` is ready to pull by 

`cd /home/alice/project`

`git pull /home/bob/myrepo master`

This merges the changes from Bob's `master` branch into Alice's current branch.
If there are conflicts caused by addtional changes made in the meantime, they need to by fix manually.

`pull` command fetches changes from remote branch and merges them into the current branch.

To inspect changes without merging, use `fetch` with special symbol `FETCH_HEAD`

- `git fetch /home/bob/myrepo master` - This operation is safe even if there are some uncommitted local changes.
- `git log -p HEAD..FETCH_HEAD` - shows everything that is reachable from the `FETCH_HEAD`, but exclude anything that is reachable from `HEAD`.

`...(current state of Alice)HEAD ...(exclude)... FETCH_HEAD(Bob's work)...`

- `gitk HEAD..FETCH_HEAD` - visualizing Bob's work (after `FETCH_HEAD`)
- `git HEAD...FETCH_HEAD` - (notice three dots) both works since their forked.
- `git remote add bob /home/bob/myrepo` - remote repository shorthand
- `git fetch bob` - fetch with shorthand, all fetched data is stored in remote-tracking branch, in this case `bob/master`
- `git log -p master..bob/master` - shows a list of all changes that Bob made since he branched from Alice's master branch.
- `git merge bob/master` - merge changes into alice's master branch.
- `git pull . remotes/bob/master` - another way to do the merging. Note that `git pull` always merges into the current branch, regardless of any other commands typed.

After cloning someone's repo there is no need to type path, Git stores the location of the repository in configuration, and it is later used for pulls.

`git config --get remote.origin.url`

`/home/alice/project`

- `git config -l` - complete config created by `clone`



