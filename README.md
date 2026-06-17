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


