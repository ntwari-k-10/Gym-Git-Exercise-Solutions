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
