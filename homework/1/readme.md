Homework 1 answers
  
A)  
```bash
git branch test1
git branch test2
 ```
B)  
```bash
git checkout test1
Switched to branch 'test1'
D       test1.txt
vim test2.txt
 ```
C)  
```bash
This is some example text for branch test1
```
D)  
```bash
$ git add --all
warning: LF will be replaced by CRLF in homework/1/test2.txt.
The file will have its original line endings in your working directory.
$ git commit --all
[test1 44aadcf] Example text Please enter the commit message for your changes. Lines starting
 1 file changed, 1 insertion(+)
 create mode 100644 homework/1/test2.txt
```
E)   
```bash
$ git checkout test2
Switched to branch 'test2'
$ ls
readme.md
```   
I do not see the test.txt in the homework/1/ directory for the test2 branch because I switched from branch test1 to branch test2.  
F)
```bash
$ vim test2.txt
This is some example text for branch test2
```
G)  
```bash
git checkout test1
error: The following untracked working tree files would be overwritten by checkout:
        homework/1/test2.txt
Please move or remove them before you switch branches.
Aborting
rm -rf test2.txt
```
H)  
```bash
$ git merge test1
Merge made by the 'recursive' strategy.
 homework/1/test2.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 homework/1/test2.txt
```
I)  
```bash
$ ls
readme.md  test2.txt
```
J)   
```bash
$ git merge test2
Auto-merging homework/1/test2.txt
CONFLICT (add/add): Merge conflict in homework/1/test2.txt
Automatic merge failed; fix conflicts and then commit the result.
```   
Error arises because both branches have the same text file names.  
K)  
```bash
$ git checkout test2
error: you need to resolve your current index first
homework/1/test2.txt: needs merge
```
L)  
```bash
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Changes to be committed:

        new file:   readme.md

Unmerged paths:
  (use "git add <file>..." to mark resolution)

        both added:      test2.txt
```
Both branches have a text file named test2.txt  
M)  
```bash
$ vim test2.txt
```
N)  
```bash
$ git status
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Changes to be committed:

        new file:   readme.md

Unmerged paths:
  (use "git add <file>..." to mark resolution)

        both added:      test2.txt
$ git checkout test2
Switched to branch 'test2'
```

O)  
```bash
$ git branch -d test1
error: The branch 'test1' is not fully merged.
If you are sure you want to delete it, run 'git branch -D test1'.

```
P)  
```bash
$ git checkout master
Switched to branch 'master'

$ git branch -d test1
Deleted branch test1 (was 44aadcf).


$ git branch
* master
  test2

```  
Q)You cannot delete test2 from test1, you can only delete those branches from the master branch.  
R)  
```bash
$ git checkout test2
Switched to branch 'test2'

$ git branch -d test2
error: Cannot delete branch 'test2' checked out at 'C:/Users/Ashmir/git/ICP2017F'
```
S)  
```bash
$ git checkout master
Switched to branch 'master'

$ git branch -d test2
Deleted branch test2 (was dd49c2f).

$ git branch
* master
```
T)  
```bash
$ git add –all

$ git commit -m "deleted branchs"

$ git push origin master

$ git push origin --delete test1

$ git push origin --delete test2


