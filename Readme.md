  # Git exercises

## Part 1:

### Initialization

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git
$ git clone git@github.com:ijessica12/git-advanced-exercise.git
Cloning into 'git-advanced-exercise'...
warning: You appear to have cloned an empty repository.

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git
$ cd git-advanced-exercise

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ touch test{1..4}.md

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git add test1.md && git commit -m"chore create initial file"
[main (root-commit) c3530f0] chore create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git add test2.md && git commit -m"chore create another file"
[main c4cc1d8] chore create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git add test3.md && git commit -m"chore create third and fourth files"
[main 0d6f7f0] chore create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 `````
### Challenge 1

 `````bash

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git add test4.md

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git commit --amend -m "chore create third and fourth files"
[main 19eb136] chore create third and fourth files
 Date: Wed Sep 3 14:21:27 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git log --oneline
19eb136 (HEAD -> main) chore create third and fourth files
c4cc1d8 chore create another file
c3530f0 chore create initial file
`````
### Challenge 2

`````bash

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git rebase -i HEAD~2
[detached HEAD 81a5f72] chore create second file
 Date: Wed Sep 3 14:20:39 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git log --oneline
88f2fd4 (HEAD -> main) chore create third and fourth files
81a5f72 chore create second file
c3530f0 chore create initial file
`````
### Challenge 3

`````bash

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git rebase -i --root
[detached HEAD f53256c] chore create initial and second file
 Date: Wed Sep 3 14:20:14 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git log --oneline
00cb126 (HEAD -> main) chore create third and fourth files
f53256c chore create initial and second file
`````
### Challenge 4

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git reset HEAD~1

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git add test3.md

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git commit -m "chore:create third file"
[main 7efa642] chore:create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git add test4.md

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git commit -m "chore:create fourth file"
[main 0accee6] chore:create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git rebase -i HEAD~2
[detached HEAD 4ee25c8] chore:create third and fourth files
 Date: Wed Sep 3 15:25:26 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.
`````
### Challenge 6

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ echo "bad content">unwanted.txt

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git add unwanted.txt
warning: in the working copy of 'unwanted.txt', LF will be replaced by CRLF the
next time Git touches it

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git commit -m "chore:unwanted commit"
[main 17233f5] chore:unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git log --oneline
4ee25c8 (HEAD -> main) chore:create third and fourth files
f53256c chore create initial and second file
`````
## Challenge 7

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ echo "new test file">extra.txt

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git add extra.txt
warning: in the working copy of 'extra.txt', LF will be replaced by CRLF the nex
t time Git touches it

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git commit -m "chore:create extra file"
[main e3df76d] chore:create extra file
 1 file changed, 1 insertion(+)
 create mode 100644 extra.txt

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git log --oneline
e3df76d (HEAD -> main) chore:create extra file
4ee25c8 chore:create third and fourth files
f53256c chore create initial and second file

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git rebase -i --root
Successfully rebased and updated refs/heads/main.

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git log --oneline --reverse
85d78fe chore:create extra file
8d97056 chore create initial and second file
76285f1 (HEAD -> main) chore:create third and fourth files
`````
### Challenge 8

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (ft/branch)
$ echo "test 5 content ">test5.md

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (ft/branch)
$ git add test5.md
warning: in the working copy of 'test5.md', LF will be replaced by CRLF the next
 time Git touches it

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (ft/branch)
$ git commit -m "chore implemented test 5"
[ft/branch 0cdaf13] chore implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (ft/branch)
$ git log --oneline
0cdaf13 (HEAD -> ft/branch) chore implemented test 5
76285f1 (main) chore:create third and fourth files
8d97056 chore create initial and second file
85d78fe chore:create extra file

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (ft/branch)
$ git checkout main
Switched to branch 'main'
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git cherry-pick 0cdaf13
[main 0b76d1c] chore implemented test 5
 Date: Wed Sep 3 16:24:58 2025 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git log --oneline
0b76d1c (HEAD -> main) chore implemented test 5
76285f1 chore:create third and fourth files
8d97056 chore create initial and second file
85d78fe chore:create extra file
`````
### Challenge 9

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git log --oneline --graph --decorate --all
* 0b76d1c (HEAD -> main) chore implemented test 5
| * 0cdaf13 (ft/branch) chore implemented test 5
|/
* 76285f1 chore:create third and fourth files
* 8d97056 chore create initial and second file
* 85d78fe chore:create extra file
`````
### Challenge 10

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/desktop/git/git-advanced-exercise (main)
$ git reflog
0b76d1c (HEAD -> main) HEAD@{0}: cherry-pick: chore implemented test 5
76285f1 HEAD@{1}: checkout: moving from ft/branch to main
0cdaf13 (ft/branch) HEAD@{2}: checkout: moving from main to ft/branch
76285f1 HEAD@{3}: checkout: moving from ft/branch to main
0cdaf13 (ft/branch) HEAD@{4}: commit: chore implemented test 5
76285f1 HEAD@{5}: checkout: moving from main to ft/branch
76285f1 HEAD@{6}: rebase (finish): returning to refs/heads/main
76285f1 HEAD@{7}: rebase: fast-forward
8d97056 HEAD@{8}: rebase: fast-forward
85d78fe HEAD@{9}: rebase: fast-forward
9389e6f HEAD@{10}: rebase (start): checkout 9389e6f9d5e9f86afdb004c5fd7a9d219a8f
db49
76285f1 HEAD@{11}: rebase (finish): returning to refs/heads/main
76285f1 HEAD@{12}: rebase (pick): chore:create third and fourth files
8d97056 HEAD@{13}: rebase (pick): chore create initial and second file
85d78fe HEAD@{14}: rebase (pick): chore:create extra file
8807350 HEAD@{15}: rebase (start): checkout 88073509c19f11997c82415d197063c2efa0
dcee
e3df76d HEAD@{16}: commit: chore:create extra file
4ee25c8 HEAD@{17}: rebase (finish): returning to refs/heads/main
4ee25c8 HEAD@{18}: rebase (start): checkout HEAD~2
17233f5 HEAD@{19}: commit: chore:unwanted commit
4ee25c8 HEAD@{20}: rebase (finish): returning to refs/heads/main
4ee25c8 HEAD@{21}: rebase (squash): chore:create third and fourth files
7efa642 HEAD@{22}: rebase (start): checkout HEAD~2
0accee6 HEAD@{23}: commit: chore:create fourth file
7efa642 HEAD@{24}: commit: chore:create third file
f53256c HEAD@{25}: reset: moving to HEAD~1
00cb126 HEAD@{26}: rebase (finish): returning to refs/heads/main
00cb126 HEAD@{27}: rebase (pick): chore create third and fourth files
f53256c HEAD@{28}: rebase (squash): chore create initial and second file
c3530f0 HEAD@{29}: rebase: fast-forward
2739701 HEAD@{30}: rebase (start): checkout 273970191e86892769d4ae7fef1e54416559
74f2
88f2fd4 HEAD@{31}: rebase (finish): returning to refs/heads/main
88f2fd4 HEAD@{32}: rebase (pick): chore create third and fourth files
81a5f72 HEAD@{33}: rebase (reword): chore create second file
c4cc1d8 HEAD@{34}: rebase: fast-forward
c3530f0 HEAD@{35}: rebase (start): checkout HEAD~2
19eb136 HEAD@{36}: commit (amend): chore create third and fourth files
0d6f7f0 HEAD@{37}: commit: chore create third and fourth files
c4cc1d8 HEAD@{38}: commit: chore create another file
c3530f0 HEAD@{39}: commit (initial): chore create initial file
`````
## Part 2:

### Challenge 1

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (ft/new-feature)
$ 
`````
### Challenge 2

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (ft/new-feature)
$ echo "new features like theme change and so on">feature.txt

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (ft/new-feature)
$ git add feature.txt
warning: in the working copy of 'feature.txt', LF will be replaced by CRLF the n
ext time Git touches it

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (ft/new-feature)
$ git commit -m"Implemented core functionality for new feature"
[ft/new-feature 40d9e45] Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (ft/new-feature)
$
`````
### Challenge 3

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (ft/new-feature)
$ git checkout main
Switched to branch 'main'
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ echo "hello there">readme.txt

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ git add readme.txt
warning: in the working copy of 'readme.txt', LF will be replaced by CRLF the ne
xt time Git touches it

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ git commit -m "Updated project readme"
[main 33d81bd] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$
`````
### challenge 4

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ git push origin main
Enumerating objects: 14, done.
Counting objects: 100% (14/14), done.
Delta compression using up to 4 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (14/14), 1.15 KiB | 196.00 KiB/s, done.
Total 14 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), done.
To github.com:ijessica12/git-advanced-exercise.git
 * [new branch]      main -> main

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ git checkout ft/new-feature
Switched to branch 'ft/new-feature'

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (ft/new-feature)
$ git push origin ft/new-feature
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 334 bytes | 334.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/new-feature' on GitHub by visiting:
remote:      https://github.com/ijessica12/git-advanced-exercise/pull/new/ft/new
-feature
remote:
To github.com:ijessica12/git-advanced-exercise.git
 * [new branch]      ft/new-feature -> ft/new-feature
`````
### Challenge 5

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ git branch -D ft/new-feature
Deleted branch ft/new-feature (was 40d9e45).

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ git push origin --delete ft/new-feature
To github.com:ijessica12/git-advanced-exercise.git
 - [deleted]         ft/new-feature
`````
### Challenge 6

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ git checkout -b ft/new-branch-from-commit HEAD~2
Switched to a new branch 'ft/new-branch-from-commit'

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (ft/new-branch-from-commit)
$ git log --oneline
76285f1 (HEAD -> ft/new-branch-from-commit) chore:create third and fourth files
8d97056 chore create initial and second file
85d78fe chore:create extra file

`````
### Challenge 7

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (ft/new-branch-from-commit)
$ git checkout main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ git merge ft/new-branch-from-commit
Already up to date.

`````
### Challenge 8

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (ft/new-branch-from-commit)
$ git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (ft/new-branch-from-commit)
$ git log --oneline --graph --decorate
* 33d81bd (HEAD -> ft/new-branch-from-commit, main) Updated project readme
* 0b76d1c chore implemented test 5
* 76285f1 chore:create third and fourth files
* 8d97056 chore create initial and second file
* 85d78fe chore:create extra file

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (ft/new-branch-from-commit)
$ git push origin ft/new-branch-from-commit --force
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote: Create a pull request for 'ft/new-branch-from-commit' on GitHub by visit
ing:
remote:      https://github.com/ijessica12/git-advanced-exercise/pull/new/ft/new
-branch-from-commit
remote:
To github.com:ijessica12/git-advanced-exercise.git
 * [new branch]      ft/new-branch-from-commit -> ft/new-branch-from-commit

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (ft/new-branch-from-commit)
$ git checkout main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ git merge ft/new-branch-from-commit
Already up to date.
`````
### Challenge 9

`````bash
CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ git branch -m ft/new-branch-from-commit ft/improved-branch-name

CMU@DESKTOP-DGCLDK7 MINGW64 ~/Desktop/git/git-advanced-exercise (main)
$ git branch
  ft/branch
  ft/improved-branch-name
* main
`````
### Challenge 10

`````bash

