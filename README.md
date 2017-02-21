# Udacity Git and Github course

## All course commands and instructions below

### Section 1: Navigating a Commit History
1. `diff -u game_new.js game_old.js` // Show diffs between 2 files; -u is unified diff format == easier to read
    1. // Lines with - sign were removed: in old version not new version
    2. // Lines with + sign were added:   in new version not old version
    3. // Keep lines short //if all on one line, git would only show the lines are diff; not where in the line
    4. `git diff [older commit1] [newer commit2]`  // Compares 2 commits (alphanumeric strings)
2. `commit` //manual user-created checkpoint (think "file save") representing logical change to file
3. `git log` // show log, or history, of changes, i.e. commits, to file
4. `git log --stat` //shows files and # of changes to those files; green plus == additions; red minus == deletions
5. // Repository or repo == group of connected files, e.g. game.js index.html index.css /*allows tracking across multiple files*/
6. `git --version` //self-explanatory; if not installed: https://www.udacity.com/wiki/ud775/install-git
7. `git clone https://github.com/udacity/asteroids.git`  // git clone: copies repo from some location to your local 
    1. //cd into /asteroids and run: git log 
    2. `q`   //quits git log 
    3. // Run diff command like earlier on two commits 
8. `git diff` vs. `diff -u` // git diff tracks one files commit history; diff -u shows changes across files
9. `git checkout [commit id]` // Temporarily reset all files in a directory to their state at the time of a specific commit; takes commit id as arg
10. `scp` // lets you copy directory from one computer to another
11. //HEAD  // the current state you're in; checkout older commit, and you'll be in "detached HEAD", so create new branch to deal with them.

### Section 2: Creating and Modifying a Repository
1. //git files stored in hidden folder: .git  // view by typing ls -a
2. `git init` // Creates repository in `pwd` and subdirectories
3. `git status` // Shows which files have changed since last `commit`
4. 
3. 
