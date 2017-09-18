Last login: Sun Sep 17 13:02:37 on ttys000	
wireless-10-148-220-71:~ cindyyongoueth$ git branch master	
fatal: Not a git repository (or any of the parent directories): .git	
wireless-10-148-220-71:~ cindyyongoueth$ pwd	
/Users/cindyyongoueth	
wireless-10-148-220-71:~ cindyyongoueth$ cd git/ICP2017/homework/1
-bash: cd: git/ICP2017/homework/1: No such file or directory
wireless-10-148-220-71:~ cindyyongoueth$ cd git
wireless-10-148-220-71:git cindyyongoueth$ cd ICP2017F
wireless-10-148-220-71:ICP2017F cindyyongoueth$ cd homework
wireless-10-148-220-71:homework cindyyongoueth$ cd 1
wireless-10-148-220-71:1 cindyyongoueth$ ls
readme.md
wireless-10-148-220-71:1 cindyyongoueth$ git branch master
fatal: A branch named 'master' already exists.
wireless-10-148-220-71:1 cindyyongoueth$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.
wireless-10-148-220-71:1 cindyyongoueth$ git branch -D test1
Deleted branch test1 (was 4305299).
wireless-10-148-220-71:1 cindyyongoueth$ git branch -D test2
Deleted branch test2 (was 4305299).
wireless-10-148-220-71:1 cindyyongoueth$ git branch test1
wireless-10-148-220-71:1 cindyyongoueth$ git branch test2
wireless-10-148-220-71:1 cindyyongoueth$ git checkout test1
Switched to branch 'test1'
wireless-10-148-220-71:1 cindyyongoueth$ cd ICP2017F
-bash: cd: ICP2017F: No such file or directory
wireless-10-148-220-71:1 cindyyongoueth$ pwd
/Users/cindyyongoueth/git/ICP2017F/homework/1
wireless-10-148-220-71:1 cindyyongoueth$ ls
readme.md
wireless-10-148-220-71:1 cindyyongoueth$ cd ..
wireless-10-148-220-71:homework cindyyongoueth$ ls
1		homework.md
wireless-10-148-220-71:homework cindyyongoueth$ cd 1
wireless-10-148-220-71:1 cindyyongoueth$ git checkout test1
Already on 'test1'
wireless-10-148-220-71:1 cindyyongoueth$ vim test.txt
wireless-10-148-220-71:1 cindyyongoueth$ git add test.txt
wireless-10-148-220-71:1 cindyyongoueth$ git commit
[test1 5f2c401] I created test.txt in the branch test1
 1 file changed, 1 insertion(+)
 create mode 100644 homework/1/test.txt
wireless-10-148-220-71:1 cindyyongoueth$ git checkout test2
Switched to branch 'test2'
wireless-10-148-220-71:1 cindyyongoueth$ ls
readme.md
wireless-10-148-220-71:1 cindyyongoueth$ vim test.txt
wireless-10-148-220-71:1 cindyyongoueth$ git checkout test2
Already on 'test2'
wireless-10-148-220-71:1 cindyyongoueth$ git checkout test1
error: The following untracked working tree files would be overwritten by checkout:
	homework/1/test.txt
Please move or remove them before you switch branches.
Aborting
wireless-10-148-220-71:1 cindyyongoueth$ git add test.txt
wireless-10-148-220-71:1 cindyyongoueth$ git commit 
[test2 68c8003] This is when I created test.txt in branch test2
 1 file changed, 1 insertion(+)
 create mode 100644 homework/1/test.txt
wireless-10-148-220-71:1 cindyyongoueth$ git checkout test1
Switched to branch 'test1'
wireless-10-148-220-71:1 cindyyongoueth$ git checkout master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.
wireless-10-148-220-71:1 cindyyongoueth$ git merge test1
Updating 4305299..5f2c401
Fast-forward
 homework/1/test.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 homework/1/test.txt
wireless-10-148-220-71:1 cindyyongoueth$ ls
readme.md	test.txt
wireless-10-148-220-71:1 cindyyongoueth$ git merge test2
Auto-merging homework/1/test.txt		
CONFLICT (add/add): Merge conflict in homework/1/test.txt		
Automatic merge failed; fix conflicts and then commit the result.		
wireless-10-148-220-71:1 cindyyongoueth$ git checkout test2		
homework/1/test.txt: needs merge		
error: you need to resolve your current index first		
wireless-10-148-220-71:1 cindyyongoueth$ git status		
On branch master		
Your branch is ahead of 'origin/master' by 1 commit.		
  (use "git push" to publish your local commits)		

You have unmerged paths.		
  (fix conflicts and run "git commit")		
  (use "git merge --abort" to abort the merge)		

Unmerged paths:		
  (use "git add <file>..." to mark resolution)		

	both added:      test.txt		

Untracked files:		
  (use "git add <file>..." to include in what will be committed)

	../.test.txt.swp

no changes added to commit (use "git add" and/or "git commit -a")
wireless-10-148-220-71:1 cindyyongoueth$ vim test.txt
wireless-10-148-220-71:1 cindyyongoueth$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)

	both added:      test.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	../.test.txt.swp

no changes added to commit (use "git add" and/or "git commit -a")
wireless-10-148-220-71:1 cindyyongoueth$ git add test.txt
wireless-10-148-220-71:1 cindyyongoueth$ commit 
-bash: commit: command not found
wireless-10-148-220-71:1 cindyyongoueth$ git commit 
[master 22e97ea] Merge branch 'test2'
wireless-10-148-220-71:1 cindyyongoueth$ git checkout test2
Switched to branch 'test2'
wireless-10-148-220-71:1 cindyyongoueth$ git branch -d test2
error: Cannot delete branch 'test2' checked out at '/Users/cindyyongoueth/git/ICP2017F'
wireless-10-148-220-71:1 cindyyongoueth$ git branch -d test1
error: The branch 'test1' is not fully merged.
If you are sure you want to delete it, run 'git branch -D test1'.
wireless-10-148-220-71:1 cindyyongoueth$ git master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)
wireless-10-148-220-71:1 cindyyongoueth$ git -d test1
Unknown option: -d
usage: git [--version] [--help] [-C <path>] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]
wireless-10-148-220-71:1 cindyyongoueth$ git branch -d test1
Deleted branch test1 (was 5f2c401).
wireless-10-148-220-71:1 cindyyongoueth$ git branch ls
wireless-10-148-220-71:1 cindyyongoueth$ ls
readme.md	test.txt
wireless-10-148-220-71:1 cindyyongoueth$ git branch 
  ls
* master
  test
  test2
wireless-10-148-220-71:1 cindyyongoueth$ git branch -D test
Deleted branch test (was 4305299).
wireless-10-148-220-71:1 cindyyongoueth$ git branch 
  ls
* master
  test2
wireless-10-148-220-71:1 cindyyongoueth$ git master
Already on 'master'
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)
wireless-10-148-220-71:1 cindyyongoueth$ git branch -d test2
Deleted branch test2 (was 68c8003).
wireless-10-148-220-71:1 cindyyongoueth$ git branch 
  ls
* master
wireless-10-148-220-71:1 cindyyongoueth$ git add test.txt
wireless-10-148-220-71:1 cindyyongoueth$ git commit 
On branch master
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)

Untracked files:
	../.test.txt.swp

nothing added to commit but untracked files present
wireless-10-148-220-71:1 cindyyongoueth$ git add test.txt.swp
fatal: pathspec 'test.txt.swp' did not match any files
wireless-10-148-220-71:1 cindyyongoueth$ git add .test.txt.swp
fatal: pathspec '.test.txt.swp' did not match any files
wireless-10-148-220-71:1 cindyyongoueth$ git commit
On branch master
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)

wireless-10-148-220-71:1 cindyyongoueth$ git add test.txt
wireless-10-148-220-71:1 cindyyongoueth$ git cd ..
git: 'cd' is not a git command. See 'git --help'.

The most similar commands are
	ca
	cm
wireless-10-148-220-71:1 cindyyongoueth$ cd ..
wireless-10-148-220-71:homework cindyyongoueth$ pwd
/Users/cindyyongoueth/git/ICP2017F/homework
wireless-10-148-220-71:homework cindyyongoueth$ git add /1/.test.txt.swp
fatal: Invalid path '/1': No such file or directory
wireless-10-148-220-71:homework cindyyongoueth$ git add 1/.test.txt.swp
fatal: pathspec '1/.test.txt.swp' did not match any files
wireless-10-148-220-71:homework cindyyongoueth$ cd 1
wireless-10-148-220-71:1 cindyyongoueth$ ls
readme.md	test.txt
wireless-10-148-220-71:1 cindyyongoueth$ git rm ../.test.txt.swp
fatal: pathspec '../.test.txt.swp' did not match any files
wireless-10-148-220-71:1 cindyyongoueth$ git commit
On branch master
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)

Untracked files:
	../.test.txt.swp

nothing added to commit but untracked files present
wireless-10-148-220-71:1 cindyyongoueth$ git push
Counting objects: 15, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (12/12), done.
Writing objects: 100% (15/15), 1.25 KiB | 640.00 KiB/s, done.
Total 15 (delta 4), reused 0 (delta 0)
remote: Resolving deltas: 100% (4/4), completed with 1 local object.
To github.com:cyyongoueth/ICP2017F.md.git
   4305299..22e97ea  master -> master
wireless-10-148-220-71:1 cindyyongoueth$ 

