# Git Advanced Exercise Solutions
## Part1
### 1: Missing File Fix
```bash
 advanced-git on  main took 2s 
❯ git clone https://github.com/ntwari-k-10/Gym-Git-Exercise-Solutions.git
Cloning into 'Gym-Git-Exercise-Solutions'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (3/3), done.
advanced-git on  main [?] 
❯ cd Gym-Git-Exercise-Solutions
Gym-Git-Exercise-Solutions on  main 
❯ touch test{1..4}.md

Gym-Git-Exercise-Solutions on  main [?] 
❯ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	test1.md
	test2.md
	test3.md
	test4.md

nothing added to commit but untracked files present (use "git add" to track)
Gym-Git-Exercise-Solutions on  main [?] 
❯ git add test1.md && git commit -m "chore: Create initial file"
[main 8296cc0] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md

Gym-Git-Exercise-Solutions on  main [?⇡] 
❯ git status -s
?? test2.md
?? test3.md
?? test4.md
Gym-Git-Exercise-Solutions on  main [?⇡] 
❯ git add test2.md && git commit -m "chore: Create another file"
[main 3754d28] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

Gym-Git-Exercise-Solutions on  main [?⇡] 
❯ git add test3.md && git commit -m "chore:Create third and fourth file"
[main 0a121b7] chore:Create third and fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
Gym-Git-Exercise-Solutions on  main [?⇡] 
❯ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	test4.md

nothing added to commit but untracked files present (use "git add" to track)

Gym-Git-Exercise-Solutions on  main [?⇡] 
❯ git log
commit 0a121b7490e3f35700cd1f846e7cb3b9f02b5472 (HEAD -> main)
Author: Kevin NTWARI <ntwarik10@gmail.com>
Date:   Wed Jun 17 09:15:45 2026 +0200

    chore:Create third and fourth file

commit 3754d2875bfe913dc6195fe878e8040929bae0a9
Author: Kevin NTWARI <ntwarik10@gmail.com>
Date:   Wed Jun 17 09:14:06 2026 +0200

    chore: Create another file

commit 8296cc0a20f7899c9ab5a17f856611c38ea8a646
Author: Kevin NTWARI <ntwarik10@gmail.com>
Date:   Wed Jun 17 09:11:50 2026 +0200

    chore: Create initial file

commit 20f97f05ebdae15b56dc037a50b0abc77ebd2fb4 (origin/main, origin/HEAD)
Author: Ntwari kevin <ntwarik10@gmail.com>
Date:   Thu Apr 16 14:39:47 2026 +0200

    Initial commit
Gym-Git-Exercise-Solutions on  main [?⇡] took 13s 
❯ git add test4.md && git commit -m "chore: Create fourth file"
[main cf3454d] chore: Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md
Gym-Git-Exercise-Solutions on  main [⇡] 
```
### 2: Editing Commit History
```bash
Gym-Git-Exercise-Solutions on  HEAD (af0d90c) took 36s 
❯ git rebase -i HEAD~3
[detached HEAD e79aebd] chore: Create second file
 Date: Wed Jun 17 11:13:12 2026 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated detached HEAD.
```
### 3: Keeping History Tidy - Squashing Commits
```bash
Gym-Git-Exercise-Solutions on  HEAD (e528caf) 
❯ git rebase -i --root
[detached HEAD 31c12bf] chore: Create initial file
 Date: Wed Jun 17 09:11:50 2026 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated detached HEAD.

Gym-Git-Exercise-Solutions on  HEAD (537626f) took 3m3s 
❯ git log --online
fatal: unrecognized argument: --online

Gym-Git-Exercise-Solutions on  HEAD (537626f) 
❯ git log --oneline
537626f (HEAD) chore: Create fourth file
61a1dbd chore:Create third and fourth file
31c12bf chore: Create initial file
20f97f0 (origin/main, origin/HEAD) Initial commit
```
### 4: Splitting a Commit
```bash
Gym-Git-Exercise-Solutions on  HEAD (537626f) 
❯ git status
Not currently on any branch.
nothing to commit, working tree clean

Gym-Git-Exercise-Solutions on  HEAD (537626f) 
❯ git reset HEAD~

Gym-Git-Exercise-Solutions on  HEAD (61a1dbd) [?] 
❯ git status
Not currently on any branch.
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	test4.md

nothing added to commit but untracked files present (use "git add" to track)
Gym-Git-Exercise-Solutions on  HEAD (537626f) 
❯ git reset HEAD~

Gym-Git-Exercise-Solutions on  HEAD (61a1dbd) [?] 
❯ git status
Not currently on any branch.
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	test4.md

nothing added to commit but untracked files present (use "git add" to track)

Gym-Git-Exercise-Solutions on  HEAD (61a1dbd) [?] 
❯ git commit --amend --no-edit
[detached HEAD 78e4da3] chore:Create third and fourth file
 Date: Wed Jun 17 11:13:26 2026 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

Gym-Git-Exercise-Solutions on  HEAD (78e4da3) [?] 
❯ git status
Not currently on any branch.
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	test4.md

nothing added to commit but untracked files present (use "git add" to track)

Gym-Git-Exercise-Solutions on  HEAD (78e4da3) [?] 
❯ git reset HEAD~1 test4.md
git commit --amend --no-edit
[detached HEAD d31444a] chore:Create third and fourth file
 Date: Wed Jun 17 11:13:26 2026 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

Gym-Git-Exercise-Solutions on  HEAD (d31444a) [?] 
❯ git status
Not currently on any branch.
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	test4.md

nothing added to commit but untracked files present (use "git add" to track)

Gym-Git-Exercise-Solutions on  HEAD (d31444a) [?] 
❯ git rm --cached test4.md
fatal: pathspec 'test4.md' did not match any files

Gym-Git-Exercise-Solutions on  HEAD (d31444a) [?] 
❯ git status
Not currently on any branch.
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	test4.md

nothing added to commit but untracked files present (use "git add" to track)

Gym-Git-Exercise-Solutions on  HEAD (d31444a) [?] 
❯ git rm --cached test4.md
fatal: pathspec 'test4.md' did not match any files

Gym-Git-Exercise-Solutions on  HEAD (d31444a) [?] 
❯ echo "test4.md" >> .gitignore

Gym-Git-Exercise-Solutions on  HEAD (d31444a) [?] 
❯ git log --oneline
d31444a (HEAD) chore:Create third and fourth file
31c12bf chore: Create initial file
20f97f0 (origin/main, origin/HEAD) Initial commit

Gym-Git-Exercise-Solutions on  HEAD (d31444a) [?] 
❯ git add --intent-to-add test4.md
The following paths are ignored by one of your .gitignore files:
test4.md
hint: Use -f if you really want to add them.
hint: Disable this message with "git config set advice.addIgnoredFile false"

Gym-Git-Exercise-Solutions on  HEAD (d31444a) [?] 
❯ git add .gitignore test4.md
git commit -m "Remove test4.md from gitignore and start tracking it again"
The following paths are ignored by one of your .gitignore files:
test4.md
hint: Use -f if you really want to add them.
hint: Disable this message with "git config set advice.addIgnoredFile false"
[detached HEAD 2d37f0c] Remove test4.md from gitignore and start tracking it again
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore

Gym-Git-Exercise-Solutions on  HEAD (2d37f0c) 
❯ git log --oneline
2d37f0c (HEAD) Remove test4.md from gitignore and start tracking it again
d31444a chore:Create third and fourth file
31c12bf chore: Create initial file
20f97f0 (origin/main, origin/HEAD) Initial commit

Gym-Git-Exercise-Solutions on  HEAD (2d37f0c) 
❯ git rebase -i HEAD~1
Successfully rebased and updated detached HEAD.

Gym-Git-Exercise-Solutions on  HEAD (2d37f0c) took 30s 
❯ git rebase -i HEAD~1
[detached HEAD 12e3b46] chore: Create last file
 Date: Wed Jun 17 12:23:20 2026 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore
Successfully rebased and updated detached HEAD.

Gym-Git-Exercise-Solutions on  HEAD (12e3b46) took 1m32s 
❯ git log --oneline
12e3b46 (HEAD) chore: Create last file
d31444a chore:Create third and fourth file
31c12bf chore: Create initial file
20f97f0 (origin/main, origin/HEAD) Initial commit

Gym-Git-Exercise-Solutions on  HEAD (12e3b46) 
❯ git status
Not currently on any branch.
nothing to commit, working tree clean

Gym-Git-Exercise-Solutions on  HEAD (12e3b46) 
❯ git reset HEAD~1

Gym-Git-Exercise-Solutions on  HEAD (d31444a) [?] 
❯ git status
Not currently on any branch.
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.gitignore

nothing added to commit but untracked files present (use "git add" to track)

Gym-Git-Exercise-Solutions on  HEAD (d31444a) [?] 
❯ git reset HEAD~1

Gym-Git-Exercise-Solutions on  HEAD (31c12bf) [?] 
❯ git status
Not currently on any branch.
Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.gitignore
	test3.md

nothing added to commit but untracked files present (use "git add" to track)

Gym-Git-Exercise-Solutions on  HEAD (31c12bf) [?] 
❯ git add test3.md

Gym-Git-Exercise-Solutions on  HEAD (31c12bf) [+?] 
❯ git commit -m "chore:Create Third file"
[detached HEAD 3fed9d0] chore:Create Third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

Gym-Git-Exercise-Solutions on  HEAD (3fed9d0) [?] 
❯ git add test4.md
The following paths are ignored by one of your .gitignore files:
test4.md
hint: Use -f if you really want to add them.
hint: Disable this message with "git config set advice.addIgnoredFile false"

Gym-Git-Exercise-Solutions on  HEAD (3fed9d0) [?] 
❯ git add -f test4.md

Gym-Git-Exercise-Solutions on  HEAD (3fed9d0) [+?] 
❯ git status
Not currently on any branch.
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   test4.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.gitignore

Gym-Git-Exercise-Solutions on  HEAD (3fed9d0) [+?] 
❯ git commit -m "chore: Created fourt file"
[detached HEAD e954189] chore: Created fourt file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

Gym-Git-Exercise-Solutions on  HEAD (e954189) [?] 
❯ git log --oneline
e954189 (HEAD) chore: Created fourt file
3fed9d0 chore:Create Third file
31c12bf chore: Create initial file
20f97f0 (origin/main, origin/HEAD) Initial commit

Gym-Git-Exercise-Solutions on  HEAD (e954189) [?] 
❯ git log

```
### 5: Advanced Squashing
```bash
Gym-Git-Exercise-Solutions on  HEAD (e954189) [?] 
❯ git log --oneline
e954189 (HEAD) chore: Created fourt file
3fed9d0 chore:Create Third file
31c12bf chore: Create initial file
20f97f0 (origin/main, origin/HEAD) Initial commit

Gym-Git-Exercise-Solutions on  HEAD (e954189) [?] 
❯ git reset --soft HEAD~2

Gym-Git-Exercise-Solutions on  HEAD (31c12bf) [+?] 
❯ git status
Not currently on any branch.
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   test3.md
	new file:   test4.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.gitignore


Gym-Git-Exercise-Solutions on  HEAD (31c12bf) [+?] 
❯ git commit -m " chore:Create third and fourth file"
[detached HEAD ec70a59]  chore:Create third and fourth file
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

Gym-Git-Exercise-Solutions on  HEAD (ec70a59) [?] 
❯ git log --oneline
ec70a59 (HEAD)  chore:Create third and fourth file
31c12bf chore: Create initial file
20f97f0 (origin/main, origin/HEAD) Initial commit

Gym-Git-Exercise-Solutions on  HEAD (ec70a59) [?] 
❯ 
```
### 6: Dropping a Commit
```bash
Gym-Git-Exercise-Solutions on  HEAD (ec70a59) [?] 
❯ touch unwanted.txt

Gym-Git-Exercise-Solutions on  HEAD (ec70a59) [?] 
❯ nano unwanted.txt

Gym-Git-Exercise-Solutions on  HEAD (ec70a59) [?] 
❯ git add unwanted.txt

Gym-Git-Exercise-Solutions on  HEAD (ec70a59) [+?] 
❯ git commit -m "Unwanted commit"
[detached HEAD 00284a1] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt

Gym-Git-Exercise-Solutions on  HEAD (00284a1) [?] 
❯ git log --oneline
00284a1 (HEAD) Unwanted commit
ec70a59  chore:Create third and fourth file
31c12bf chore: Create initial file
20f97f0 (origin/main, origin/HEAD) Initial commit

Gym-Git-Exercise-Solutions on  HEAD (00284a1) [?] 
❯ git rebase -i HEAD~2
Successfully rebased and updated detached HEAD.

Gym-Git-Exercise-Solutions on  HEAD (ec70a59) [?] took 20s 
❯ git log --oneline
ec70a59 (HEAD)  chore:Create third and fourth file
31c12bf chore: Create initial file
20f97f0 (origin/main, origin/HEAD) Initial commit

Gym-Git-Exercise-Solutions on  HEAD (ec70a59) [?] 
❯ 

❯ 
```
### 7.Reordering Commits
```bash
Gym-Git-Exercise-Solutions on  HEAD (ec70a59) [?] 
❯ git rebase -i HEAD~2
Successfully rebased and updated detached HEAD.

Gym-Git-Exercise-Solutions on  HEAD (ec70a59) [?] took 10s 
❯ git rebase -i HEAD~3
fatal: invalid upstream 'HEAD~3'

Gym-Git-Exercise-Solutions on  HEAD (ec70a59) [?] 
❯ git rebase -i HEAD~2
Successfully rebased and updated detached HEAD.

Gym-Git-Exercise-Solutions on  HEAD (8490b74) [?] took 34s 
❯ git log --oneline
8490b74 (HEAD) chore: Create initial file
bd9502e  chore:Create third and fourth file
20f97f0 (origin/main, origin/HEAD) Initial commit

Gym-Git-Exercise-Solutions on  HEAD (8490b74) [?] 
❯ git rebase -i HEAD~2
Successfully rebased and updated detached HEAD.

Gym-Git-Exercise-Solutions on  HEAD (5b8fa24) [?] took 22s 
❯ git log --oneline
5b8fa24 (HEAD)  chore:Create third and fourth file
60d1e0c chore: Create initial file
20f97f0 (origin/main, origin/HEAD) Initial commit

Gym-Git-Exercise-Solutions on  HEAD (5b8fa24) [?] 
❯ 
```
### 8: Cherry-Picking Commits
```bash
Gym-Git-Exercise-Solutions on  HEAD (5b8fa24) [?] 
❯ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

Gym-Git-Exercise-Solutions on  ft/branch [?] 
❯ touch test5.md

Gym-Git-Exercise-Solutions on  ft/branch [?] 
❯ nano test5.md

Gym-Git-Exercise-Solutions on  ft/branch [?] took 31s 
❯ git add test5.md

Gym-Git-Exercise-Solutions on  ft/branch [+?] 
❯ git commit -m "Implemented test 5"
[ft/branch ad92934] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

Gym-Git-Exercise-Solutions on  ft/branch [?] 
❯ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

Gym-Git-Exercise-Solutions on  main [?⇡] 
❯ git checkout ft/branch
Switched to branch 'ft/branch'

Gym-Git-Exercise-Solutions on  ft/branch [?] 
❯ git log --oneline
ad92934 (HEAD -> ft/branch) Implemented test 5
5b8fa24  chore:Create third and fourth file
60d1e0c chore: Create initial file
20f97f0 (origin/main, origin/HEAD) Initial commit

Gym-Git-Exercise-Solutions on  ft/branch [?] 
❯ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

Gym-Git-Exercise-Solutions on  main [?⇡] 
❯ git cherry-pick ad92934
[main a7eb3ea] Implemented test 5
 Date: Thu Jun 18 14:19:01 2026 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

Gym-Git-Exercise-Solutions on  main [?⇡] 
❯ ls
README.md  test1.md  test2.md  test3.md  test4.md  test5.md

Gym-Git-Exercise-Solutions on  main [?⇡] 
❯ git log --oneline
a7eb3ea (HEAD -> main) Implemented test 5
fcbe770 chore: Create fourth file
f9705e3 chore:Create third and fourth file
018de26 chore: Create second file
8296cc0 chore: Create initial file
20f97f0 (origin/main, origin/HEAD) Initial commit

Gym-Git-Exercise-Solutions on  main [?⇡] 
❯ 
```
### 9: Visualizing Commit History (Bonus)
```bash
Gym-Git-Exercise-Solutions on  main [?⇡] 
❯ git log --graph
* commit a7eb3ea8c5559697f437983a6392561f1965300e (HEAD -> main)
| Author: Kevin NTWARI <ntwarik10@gmail.com>
| Date:   Thu Jun 18 14:19:01 2026 +0200
| 
|     Implemented test 5
| 
* commit fcbe7709aeebb12d3812a0f663cbd75b2025e0ab
| Author: Kevin NTWARI <ntwarik10@gmail.com>
| Date:   Wed Jun 17 09:20:08 2026 +0200
| 
|     chore: Create fourth file
| 
* commit f9705e3583870b7fa89cb951bdd136d7cb09a83a
| Author: Kevin NTWARI <ntwarik10@gmail.com>
| Date:   Wed Jun 17 09:15:45 2026 +0200
| 
|     chore:Create third and fourth file
| 
* commit 018de2618129d0ac658eba6c0667fda841220244
| Author: Kevin NTWARI <ntwarik10@gmail.com>
| Date:   Wed Jun 17 09:14:06 2026 +0200
| 
|     chore: Create second file
| 
* commit 8296cc0a20f7899c9ab5a17f856611c38ea8a646
| Author: Kevin NTWARI <ntwarik10@gmail.com>
| Date:   Wed Jun 17 09:11:50 2026 +0200
| 
|     chore: Create initial file
| 
* commit 20f97f05ebdae15b56dc037a50b0abc77ebd2fb4 (origin/main, origin/HEAD)
  Author: Ntwari kevin <ntwarik10@gmail.com>
  Date:   Thu Apr 16 14:39:47 2026 +0200
  
      Initial commit

```
### 10: Understanding Reflogs (Bonus)
```bash
Gym-Git-Exercise-Solutions on  main [?⇡] 
❯ git reflog
a7eb3ea (HEAD -> main) HEAD@{0}: cherry-pick: Implemented test 5
fcbe770 HEAD@{1}: checkout: moving from ft/branch to main
ad92934 (ft/branch) HEAD@{2}: checkout: moving from main to ft/branch
fcbe770 HEAD@{3}: checkout: moving from ft/branch to main
ad92934 (ft/branch) HEAD@{4}: commit: Implemented test 5
5b8fa24 HEAD@{5}: checkout: moving from 5b8fa24b5853d357ba829be5de3c1713e76b5393 to ft/branch
5b8fa24 HEAD@{6}: rebase (pick): chore:Create third and fourth file
60d1e0c HEAD@{7}: rebase (pick): chore: Create initial file
20f97f0 (origin/main, origin/HEAD) HEAD@{8}: rebase (start): checkout HEAD~2
8490b74 HEAD@{9}: rebase (pick): chore: Create initial file
bd9502e HEAD@{10}: rebase (pick): chore:Create third and fourth file
20f97f0 (origin/main, origin/HEAD) HEAD@{11}: rebase (start): checkout HEAD~2
ec70a59 HEAD@{12}: rebase (start): checkout HEAD~2
00284a1 HEAD@{13}: commit: Unwanted commit
ec70a59 HEAD@{14}: reset: moving to HEAD~1
b91ea3b HEAD@{15}: commit: Unwanted commit
ec70a59 HEAD@{16}: commit: chore:Create third and fourth file
31c12bf HEAD@{17}: reset: moving to HEAD~2
e954189 HEAD@{18}: commit: chore: Created fourt file
3fed9d0 HEAD@{19}: commit: chore:Create Third file
31c12bf HEAD@{20}: reset: moving to HEAD~1
d31444a HEAD@{21}: reset: moving to HEAD~1
12e3b46 HEAD@{22}: rebase (reword): chore: Create last file
2d37f0c HEAD@{23}: rebase: fast-forward
d31444a HEAD@{24}: rebase (start): checkout HEAD~1
2d37f0c HEAD@{25}: commit: Remove test4.md from gitignore and start tracking it again
d31444a HEAD@{26}: commit (amend): chore:Create third and fourth file
78e4da3 HEAD@{27}: commit (amend): chore:Create third and fourth file
61a1dbd HEAD@{28}: reset: moving to HEAD~
537626f HEAD@{29}: rebase (pick): chore: Create fourth file
61a1dbd HEAD@{30}: rebase (pick): chore:Create third and fourth file
31c12bf HEAD@{31}: rebase (squash): chore: Create initial file
8296cc0 HEAD@{32}: rebase: fast-forward
20f97f0 (origin/main, origin/HEAD) HEAD@{33}: rebase: fast-forward
67d2f1e HEAD@{34}: rebase (start): checkout 67d2f1e40f745ac07f6f9c209ae6b3500f9d1c59
e528caf HEAD@{35}: rebase (pick): chore: Create fourth file
281a263 HEAD@{36}: rebase (pick): chore:Create third and fourth file
e79aebd HEAD@{37}: rebase (reword): chore: Create second file
8685acf HEAD@{38}: rebase: fast-forward
8296cc0 HEAD@{39}: rebase (start): checkout HEAD~3
af0d90c HEAD@{40}: commit (amend): chore: Create fourth file
87ffa49 HEAD@{41}: commit: chore: Create fourth file
c790fe3 HEAD@{42}: commit: chore:Create third and fourth file
8685acf HEAD@{43}: commit: chore: Create another file
8296cc0 HEAD@{44}: rebase (start): checkout HEAD~3
fcbe770 HEAD@{45}: rebase (finish): returning to refs/heads/main
fcbe770 HEAD@{46}: rebase (pick): chore: Create fourth file
f9705e3 HEAD@{47}: rebase (pick): chore:Create third and fourth file
018de26 HEAD@{48}: rebase (reword): chore: Create second file
3754d28 HEAD@{49}: rebase: fast-forward
8296cc0 HEAD@{50}: rebase (start): checkout HEAD~3
cf3454d HEAD@{51}: commit: chore: Create fourth file
0a121b7 HEAD@{52}: commit: chore:Create third and fourth file
3754d28 HEAD@{53}: commit: chore: Create another file
8296cc0 HEAD@{54}: commit: chore: Create initial file
20f97f0 (origin/main, origin/HEAD) HEAD@{55}: clone: from https://github.com/ntwari-k-10/Gym-Git-Exercise-Solutions.git
(END)
```

## Part 2: Branching Basics (10 Challenges)
### 1. Feature Branch Creation
```bash
advanced-git on  main [?] 
❯ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'

```
### 2: Working on the Feature Branch
```bash
advanced-git on  ft/new-feature [?] 
❯ touch feature.txt

advanced-git on  ft/new-feature [?] 
❯ nano feature.txt

advanced-git on  ft/new-feature [?] took 37s 
❯ git add feature.txt

advanced-git on  ft/new-feature [+?] 
❯ git commit -m "Implemented core functionality for new feature"
[ft/new-feature 4209625] Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
```
### 3:Switching Back and Making More Changes
```bash
advanced-git on  ft/new-feature [?] 
❯ git checkout main
Switched to branch 'main'

advanced-git on  main [?] 
❯ echo "Updated project readme">readme.text

advanced-git on  main [?] 
❯ ls
Gym-Git-Exercise-Solutions  readme.text  test1.md  test2.md  test3.md  test4.md


```
### 4: Local vs. Remote Branches
```bash
git push -u origin <branch-name>
git pull branch-name
git fetch --all


❯ git push -u origin ft/new-feature
Enumerating objects: 15, done.
Counting objects: 100% (15/15), done.
Delta compression using up to 8 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (15/15), 1.26 KiB | 184.00 KiB/s, done.
Total 15 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), done.
remote: 
remote: Create a pull request for 'ft/new-feature' on GitHub by visiting:
remote:      https://github.com/ntwari-k-10/Gym-Git-Exercise-Solutions/pull/new/ft/new-feature
remote: 
To github.com:ntwari-k-10/Gym-Git-Exercise-Solutions.git
 * [new branch]      ft/new-feature -> ft/new-feature
branch 'ft/new-feature' set up to track 'origin/ft/new-feature'.

advanced-git on  main [?] took 5s 
❯ git pull origin main
remote: Enumerating objects: 51, done.
remote: Counting objects: 100% (51/51), done.
remote: Compressing objects: 100% (33/33), done.
remote: Total 51 (delta 15), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (51/51), 18.93 KiB | 133.00 KiB/s, done.
From github.com:ntwari-k-10/Gym-Git-Exercise-Solutions
 * branch            main       -> FETCH_HEAD
 * [new branch]      main       -> origin/main
hint: You have divergent branches and need to specify how to reconcile them.
hint: You can do so by running one of the following commands sometime before
hint: your next pull:
hint:
hint:   git config pull.rebase false  # merge
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
hint:
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation.
fatal: Need to specify how to reconcile divergent branches.


```
### 5: Branch Deletion
```bash
advanced-git on  main [?] 
❯ git branch --merged
* main

advanced-git on  main [?] 
❯ git merge ft/new-feature
merge: ft/new-feature - not something we can merge

advanced-git on  main [?] 
❯ git checkout -b ft/new-feature origin/ft/new-feature
branch 'ft/new-feature' set up to track 'origin/ft/new-feature'.
Switched to a new branch 'ft/new-feature'

advanced-git on  ft/new-feature [?] 
❯ git checkout main
git merge ft/new-feature
Switched to branch 'main'
Already up to date.

advanced-git on  main [?] 
❯ git branch --merged
  ft/new-feature
* main

advanced-git on  main [?] 
❯ git merge ft/new-feature
Already up to date.

advanced-git on  main [?] 
❯ git branch -d ft/new-feature
Deleted branch ft/new-feature (was 4209625).

```

### 6: Creating a Branch from a Commit
```bash
advanced-git on  main [?] 
❯ git log --oneline
4209625 (HEAD -> main, origin/ft/new-feature) Implemented core functionality for new feature
b961bcd chore: Created the fourth file and staged it
ca68ae1 chore: Create third and fourth files
b56292d chore: Create second file
4874f19 chore: Create initial file

advanced-git on  main [?] 
❯ git checkout -b ft/new-branch-from-commit b961bcd
Switched to a new branch 'ft/new-branch-from-commit'

advanced-git on  ft/new-branch-from-commit [?] 
❯ git log --oneline
b961bcd (HEAD -> ft/new-branch-from-commit) chore: Created the fourth file and staged it
ca68ae1 chore: Create third and fourth files
b56292d chore: Create second file
4874f19 chore: Create initial file

```
### 7: Branch Merging
```bash
❯ git checkout main
Switched to branch 'main'

advanced-git on  main [?] 
❯ git log --oneline
4209625 (HEAD -> main, origin/ft/new-feature) Implemented core functionality for new feature
b961bcd (ft/new-branch-from-commit) chore: Created the fourth file and staged it
ca68ae1 chore: Create third and fourth files
b56292d chore: Create second file
4874f19 chore: Create initial file

advanced-git on  main [?] 
❯ git merge ft/new-branch-from-commit
Already up to date.
advanced-git on  main [?] 
❯ git branch --merged
  ft/new-branch-from-commit
* main

advanced-git on  main [?] 
❯ git log --oneline
4209625 (HEAD -> main, origin/ft/new-feature) Implemented core functionality for new feature
b961bcd (ft/new-branch-from-commit) chore: Created the fourth file and staged it
ca68ae1 chore: Create third and fourth files
b56292d chore: Create second file
4874f19 chore: Create initial file

advanced-git on  main [?] 
❯ 

```
### 8: Branch Rebasing
```bash
advanced-git on  main [?] 
❯ git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'

advanced-git on  ft/new-branch-from-commit [?] 
❯ git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.

advanced-git on  ft/new-branch-from-commit [?] 
❯ git log --oneline
4209625 (HEAD -> ft/new-branch-from-commit, origin/ft/new-feature, main) Implemented core functionality for new feature
b961bcd chore: Created the fourth file and staged it
ca68ae1 chore: Create third and fourth files
b56292d chore: Create second file
4874f19 chore: Create initial file

advanced-git on  ft/new-branch-from-commit [?] 
❯ 

```
