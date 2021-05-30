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

### Finally push

`git push -u origin main`

Find an error called Permission denied (publickey).

We have to config our SSH key.

Under for profile pic open setting.

Then select SSH and GPG key

We have tp generate a private-publicy key.

Then we need to upload public key on our account.

Then through are private key we can push on our account

Read the docs
[Generate SSH and Add](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)

```bash
Mr.S@LAPTOP-FKJAF3O6 MINGW64 /f/learning-git (main)
$ ssh-keygen -t ed25519 -C "saiyaviraj04@gmail.com"
Generating public/private ed25519 key pair.
Enter file in which to save the key (/c/Users/Mr.S/.ssh/id*ed25519):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/Mr.S/.ssh/id_ed25519
Your public key has been saved in /c/Users/Mr.S/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:IyB5fPgJSeJMuymL05S3tqV7lTK9xMc09/YXdOGmXRA saiyaviraj04@gmail.com
The key's randomart image is:
+--[ED25519 256]--+
| o . E. |
| +* o .. |
| _B . ...|
|_ = . o . +o|
|. = . +oS+ o .= o|
|.= . .o.\_.o .oo |
|+ . o .= o . ..|
| . . +. . o|
| +o .|
+----[SHA256]-----+
```

passphrase:viraj

```bash
Mr.S@LAPTOP-FKJAF3O6 MINGW64 /f/learning-git (main)
$ ssh-keygen -p -f ~/.ssh/id_ed25519
Key has comment 'saiyaviraj04@gmail.com'
Enter new passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved with the new passphrase.
```

## Adding another

`vi main.py`

no need to add origin now it has been register by first push

`git push`

## Git Pull

So we have change the readme file on github so see changes we need to pull
`git pull`

```bash
$ git push
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 1.11 KiB | 379.00 KiB/s, done.
Total 4 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/Mrbean0007/learning-git.git
   6930adf..15f966f  main -> main

```
