# Git command

## Initializing Git

**`git init`**

## Config

**`git config --global user.name "Mr.Bean"`**

**`git config --global user.email "saiyaviraj04@gmail.com"`**

## Command line color

**`git config --global color.ui auto`**

**`git config`**

**`git config -l` or `git config --list`**

Working Directory --> Staging Area --> Commit History --> Remote Sever

-----------------(git add)--------- (git commit)----- -----(git push)

Remote Server

(Github,Bitbucket,AWS codecommit,GitLab)

## Working Directory -> Git Repository

Working Directory consist of couple of file example all of this are in local machine

- CSS
- html
- JS
- Python....

Repositories in Git contain a collection of files of various different version of a product

## Make Repository

Initialize our working directory or repository

### Initialize git

**`git init`**

### Remove git

**`rm -rf .git`**

### Creating dummies file

**`touch index.js`**
**`touch index.html`**
**`touch main.css`**

### Status

**`git status`**

### Add to Staging area

**`git add index.html`**
**`git status`**

### Remove/Unstage from Staging area

**`git rm --cached index.html`**
**`git status`**

### Add all file to Staging area

add . -> Current directory downwards

**`git add .`**
**`git status`**

### Remove/Unstage all file from Staging area

**`git rm -r --cached .`**
**`git status`**

### Different directory

```bash
Mr.S@LAPTOP-FKJAF3O6 MINGW64 /f/learning-git (master)
$ mkdir test

Mr.S@LAPTOP-FKJAF3O6 MINGW64 /f/learning-git (master)
$ cd test

Mr.S@LAPTOP-FKJAF3O6 MINGW64 /f/learning-git/test (master)
$ touch test.js

Mr.S@LAPTOP-FKJAF3O6 MINGW64 /f/learning-git/test (master)
$ git add .

Mr.S@LAPTOP-FKJAF3O6 MINGW64 /f/learning-git/test (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   test.js

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../index.html
        ../index.js
        ../main.css
```

### Add all the file

**`git add -A`**
**`git status`**

### Git Commit

Commit is save point

All these files are in staging area

index.html
index.js
main.css
test/test.js

### To Commit all files'

**`git commit -m "bootstrap project"`**

```bash
4 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 index.html
 create mode 100644 index.js
 create mode 100644 main.css
 create mode 100644 test/test.js
```

**`git status`**

#### To see changes of commit

**`git log`**

```bash
commit 72744aa24da9acca2177cc8551c74d0900150be0 (HEAD -> master)
Author: Mr.Bean <saiyaviraj04@gmail.com>
Date:   Sat May 8 12:49:59 2021 +0530

    bootstrap project
```

#### For more detail

The hash value can be fing in git log

**`git show 72744aa24da9acca2177cc8551c74d0900150be0`**

```bash
commit 72744aa24da9acca2177cc8551c74d0900150be0 (HEAD -> master)
Author: Mr.Bean <saiyaviraj04@gmail.com>
Date: Sat May 8 12:49:59 2021 +0530

    bootstrap project

diff --git a/index.html b/index.html
new file mode 100644
index 0000000..e69de29
diff --git a/index.js b/index.js
new file mode 100644
index 0000000..e69de29
diff --git a/main.css b/main.css
new file mode 100644
index 0000000..e69de29
diff --git a/test/test.js b/test/test.js
new file mode 100644
index 0000000..e69de29
```

### Open file and modify in terminal

**`vi index.js`**

press **`i`** to insert

press Escape

to quit use

**`:wq`**

#### To run the file

**`cat index.js`**

```bash
console.log('Hello Git');
```

**`git status`**

#### Difference in stage file and modify file

**`git diff`**

```bash
diff --git a/index.js b/index.js
index e69de29..47bfe62 100644
--- a/index.js
+++ b/index.js
@@ -0,0 +1 @@
```

**`git add .`**

**`git status`**

**`git commit -m "added console log"`**

**`git log`**

```bash
[master 4fab763] added console log
 1 file changed, 1 insertion(+)
```

```bash
commit 4fab7636a1bb402c151b26d7ffc82a45afa3527f (HEAD -> master)
Author: Mr.Bean <saiyaviraj04@gmail.com>
Date:   Sat May 8 13:09:27 2021 +0530

    added console log

commit 72744aa24da9acca2177cc8551c74d0900150be0
Author: Mr.Bean <saiyaviraj04@gmail.com>
Date:   Sat May 8 12:49:59 2021 +0530

    bootstrap project
```

**`git show 4fab7636a1bb402c151b26d7ffc82a45afa3527f`**

We have +console.log before we that we only add empty file

```bash
commit 4fab7636a1bb402c151b26d7ffc82a45afa3527f (HEAD -> master)
Author: Mr.Bean <saiyaviraj04@gmail.com>
Date:   Sat May 8 13:09:27 2021 +0530

    added console log

diff --git a/index.js b/index.js
index e69de29..47bfe62 100644
--- a/index.js
+++ b/index.js
@@ -0,0 +1 @@
+console.log('Hello Git');

```

#### Remove console.log

**`vi index.js`**

**`git diff`**

```bash
diff --git a/index.js b/index.js
index 47bfe62..8b13789 100644
--- a/index.js
+++ b/index.js
@@ -1 +1 @@
-console.log('Hello Git');

```

**`git status`**

```bash
On branch master
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
modified: index.js

no changes added to commit (use "git add" and/or "git commit -a")
```

#### To restore the file

**`git restore index.js`**

**`git status`**

#### To change the message (Amend)

vi main.css

Add body {}; in file main.css

`git commit -m "Addong Css"`

`git log`

```bash
commit 0a713525027a37b55540fb89d66c63d4b4ac6941 (HEAD -> master)
Author: Mr.Bean <saiyaviraj04@gmail.com>
Date:   Sat May 8 14:03:55 2021 +0530

    Adding CSS

```

`git commit --amend -m "Addong Css body{} in main.css"`

`git log`

```bash
commit 47d9038a207ff218018d27f9ae8bad8998c8858d (HEAD -> master)
Author: Mr.Bean <saiyaviraj04@gmail.com>
Date:   Sat May 8 14:03:55 2021 +0530

    Addong Css body{} in main.css


```

git add kidcredo-Maain.html or git add \*.html or git add.
git status
git commit -m "Update 18/03/2020"
git remote add origin <https://github.com/Mrbean0007/OurWebWorks.git>
git push -u origin master

bb0f9680f3e23f7285483cff1b7b323c28805b04

## GitHub

Create a new repository at Github website first.

## Git Push

### Add a remote server

`git remote add origin https://github.com/Mrbean0007/learning-git.git`

### Find Branch

```bash
Mr.S@LAPTOP-FKJAF3O6 MINGW64 /f/learning-git (master)
$ git branch
* master
```

Current we are in branch called master

### To change in main branch

`git branch -M main`

```bash
Mr.S@LAPTOP-FKJAF3O6 MINGW64 /f/learning-git (master)
$ git branch -M main

Mr.S@LAPTOP-FKJAF3O6 MINGW64 /f/learning-git (main)
$
```
