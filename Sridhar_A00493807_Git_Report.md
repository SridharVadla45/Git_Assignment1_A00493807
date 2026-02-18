# Git Assignment #1 Submission Report
**Student Name:** Sridhar  
**A-Number:** A00493807  
**Course:** MCDA 5512

---

### Task (1): Repository Initialization and Status Check

**Description**
For the initial task, I established the project environment by creating a dedicated directory `Git_Assignment1_A00493807`. I then initialized a local Git repository to begin version tracking and executed the status command to confirm the repository was successfully created on the 'main' branch without any prior commits.

**Command ran**
`git init && git status`

**Result of the screenshot**
```text
Initialized empty Git repository in /Users/sridhar/GIT/Git_Assignment1_A00493807/.git/
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

---

### Task (2): File Creation and Version Control

**Description**
I created `countries.txt` and `shapes.txt` with their required content and staged them using the `git add` command. After verifying the staged status, I committed them with a descriptive message. I then added a third file, `numbers.txt`, and committed it separately to build a multi-commit history, which I finally verified using the oneline log view.

**Command ran**
`git add . && git commit -m "Adding Countries and Shapes" && git log --oneline`

**Result of the screenshot**
```text
[main (root-commit) 6a659ef] Adding Countries and Shapes
 2 files changed, 6 insertions(+)
 
[main 4c55b8d] Adding numbers
 1 file changed, 3 insertions(+)

4c55b8d (HEAD -> main) Adding numbers
6a659ef Adding Countries and Shapes
```

---

### Task (3): Branch Creation and Commit

**Description**
To demonstrate branching, I created a new branch named `LearnAnalytics` and immediately switched to it. On this new branch, I created `languages.txt` with specific data science tools and committed the file. I ended by listing all branches, identifying that `LearnAnalytics` was the active branch.

**Command ran**
`git checkout -b LearnAnalytics && git commit -m "Adding languages" && git branch`

**Result of the screenshot**
```text
Switched to a new branch 'LearnAnalytics'
[LearnAnalytics 7d1064b] Adding languages on LearnAnalytics branch
 1 file changed, 3 insertions(+)

* LearnAnalytics
  main
```

---

### Task (4): Merging Conflicting Changes

**Description**
I simulated a classic merge conflict by having two branches, `user1` and `user2`, modify the same content in `countries.txt`. Upon merging `user1` into the combined branch, Git flagged a conflict. I resolved this by manually editing the file to include all proposed countries from both users, ensuring a complete and integrated data set.

**Command ran**
`git merge user1 && [Resolve Conflicts] && git commit -m "Merge fixed"`

**Result of the screenshot**
```text
CONFLICT (content): Merge conflict in countries.txt
Automatic merge failed; fix conflicts and then commit the result.

[combine_countries 45ebc9b] Resolved merge conflict
Germany
France
Italy
Japan
China
India
```

---

### Task (5): Stashing and Applying Changes

**Description**
Using the `git stash` command, I safely tucked away my uncommitted changes on the `user3` branch to switch to `main` for an urgent edit. After committing the update on the main branch, I returned to `user3` and utilized `git stash apply` to bring back my work-in-progress, allowing me to continue without losing any modifications.

**Command ran**
`git stash && git checkout main && git stash apply`

**Result of the screenshot**
```text
Saved working directory and index state WIP on user3...
Switched to branch 'main'
...
On branch user3
Changes not staged for commit:
        modified:   countries.txt
```

---

### Task (6): Advanced git workflow

**Description**
In the advanced workflow phase, I utilized `git cherry-pick` to selectively apply a specific bug fix from the `bugfix` branch onto the `main` branch. This allowed me to integrate the critical fix while excluding other unnecessary or experimental changes from the source branch, maintaining a clean and stable production line.

**Command ran**
`git cherry-pick [commit_hash] && git status`

**Result of the screenshot**
```text
[main a1a6482] Fix: critical bug
 1 file changed, 1 insertion(+)
 create mode 100644 bugfix.txt

On branch main
nothing to commit, working tree clean
```
