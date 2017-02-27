# Udacity Git and Github course

## All course commands and instructions below

### Section 1: Navigating a Commit History
* `diff -u game_new.js game_old.js` // Show diffs between 2 files; -u is unified diff format == easier to read
    * // Lines with - sign were removed: in old version not new version
    * // Lines with + sign were added:   in new version not old version
    * // Keep lines short //if all on one line, git would only show the lines are diff; not where in the line
    * `git diff [older commit1] [newer commit2]`  // Compares 2 commits (alphanumeric strings)
* `commit` //manual user-created checkpoint (think "file save") representing logical change to file
    * // Here's how git commit ids are created: https://git-scm.com/book/en/v2/Git-Internals-Git-Objects
* `git log` // show log, or history, of changes, i.e. commits, to file
* `git log --stat` // Shows # changes to files; additions: green +; deletions: red -
* // Repository (repo): group of connected files, e.g. in same folder /*allows tracking across multiple files*/
* `git --version` //self-explanatory; if not installed: https://www.udacity.com/wiki/ud775/install-git
* `git clone https://github.com/udacity/asteroids.git`  // git clone: copies repo from URI to your local 
    * // **cd** into **/asteroids** and run: `git log`
    * `q`   //quits git log 
    * // Run diff command like earlier on two commits 
* `git diff` vs. `diff -u` // git diff tracks one files commit history; diff -u shows changes across files
* `git checkout [commit id]` // Temporarily resets all dir files to their state at time of this commit 
    * **detached HEAD** // Occurs when checkout commit ID; `git branch` (below) easier; avoids this
    * **HEAD**  // Current state you're in;
* `git checkout master` // Get back to `master` branch
* `scp` // lets you copy directory from one computer to another

### Section 2: Creating and Modifying a Repository
* //git files stored in hidden folder: .git  // view by typing ls -a
* `git init` // Creates repository in `pwd` and subdirectories
* `git status` // Shows which files have changed since last `commit`
* //git works like this: ||Working Directory || Staging Area || Repository
    * `git add [filename(s)]` // Adds to staging area; then `git commit` adds to repository
* `git reset` // Removes file(s) from staging area; e.g. if accidentally added file.txt
* `git commit -m "type: subject  body   footer "` // Best practice to write as a (present tense) command
* `git diff` // With no args shows changes between WD and Staging Area 
* `git diff --staged` // Shows changes in staged not committed yet
* `git reset --hard` //Be **very** careful with this command; deletes all changes in WD too

##### Branches // Named labels for checking out commits (instead of commit ID)
* // Once check out branch, remains checked out until merged
* // Named to make easier on user (instead of alphanumeric commit ID) and avoid `detached HEAD state`
* // multiple branches can be on same commit, but new commit only on checked out branch
* `git branch` // Shows current branches
* `git branch [new-name]` // Creates new branch
* `git checkout [new-name]` // Checks out branch
* `git log --graph --oneline [branch1] [branch2] [etc]` // See sub-bullets
    * `--graph` // Shows commit tree;
    * `--oneline` // Keeps output shorter and after you can specify branches to compare
* `git checkout -b new_branch_name` // Creates new branch and checks out; fixes detached HEAD
* `git gc` // Git garbage collection; deletes unreachable commits from deleted branches
    * These commits are only accessible by commit ID until `git gc` runs
* `git merge [branch1] [branch2]` // Merge branches
    * // Failed? Try: http://genomewiki.ucsc.edu/index.php/Resolving_merge_conflicts_in_Git
    * // And go into the file to see 3 sections: 
        1. // Top section: **HEAD** == your code
        2. // Bottom section: **master** == code in master right now
        3. // middle section: original version both sections modified, called: **common ancestor**
            * // Finally, resolve whichever change you want: delete git text inserted, e.g. HEAD  ====  etc.
    * `git merge --abort` // Backs out of merge
* `git show commit_id` // Compare commit to its parent

### Section 3: Using Github to Collaborate
* // Use password caching so don't have to type pwd every time commit to Github: https://help.github.com/articles/caching-your-github-password-in-git/
* // Can't clone local repo to github; so you have to create "remote" repo in github, then **push** local up
* // If creating new project on github (no local yet), create w/Readme...
    * Else if pushing locally, create remote _without_ readme.md ... 
        * because it counts readme as a commit && that creates conflict
* `git remote` // View remotes
* `git remote add [name] [URL]` // **Add remote**; _[name]_ can be anything but...
    * // e.g. git remote add origin git@github.com:_username_/_reponame_
        * **origin** is common when have one remote
* `git remote -v` // _-v_ is 'verbose'; this command outputs github remotes
* `git push [remote name] [remote branch] // push local changes to remote
    * // e.g. git push origin master
* // on github, clicking _commits_ displays commits pushed to github; not all local
    * // e.g. if edit/create text files on github; pushed from another computer; pushed from another user
* `git pull [remote name] [remote branch] // pull remote changes to sync to local
    * // e.g. git pull origin master
* // **fork**: github copies a repo onto github in your account; then you clone (to local)
* 
