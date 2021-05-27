# git cheet sheet

## .gitignore file

---

**root level = where .gitignore is present**
(below is e.g. to understand root and child level)

- .gitignore (root level)
- first root folder (root level)
  - first child folder (child level)
  - first child file(child level)
    - first child's child (all level)
- first root file(root level)

1. ignore file/folder from all level
   `filenm`
   `folderNm/`

2. ignore file/folder which are root level (not ignore from nested folder)
   `/filenm`
   `/folder/`

3. ignore all file by extension
   `*.ext`

**file would be like .gitignore**
`file.txt` (ignore all file.txt all lelvel)
`folder` (ignore all folder all lelvel)
`/file.txt` ( ignore only root level file)
`*.txt` (ignore all .txt file all level)
`/*.txt` (ignore all .txt file in root level only)
`/first-folder/*.txt` (ignore all .txt file in first-folder only)

## git bash it work like unix/linux terminal (if you use)

---

## single branch

so u can fired linux cmd to like

1. `ls` listing files
2. `touch filenm` create file, etc
3. `rm -rf .git` delete/remove .git folder so now its no longer git repo.
4. `pwd` present working directory
5. `cd` change directory

### git cmds as follows

---

### git init

init the git (create file and folder for manageing curr folder's files)

### git status

show the status of files

**types of file status**

1. untract
   git no longer to manage it
   `git add <filenm>` git starting tracking (i.e file in stage mode when we fire commit then this[stage's file] file going to commit )
   `git add -A` or `git add --a ` or `git add .` for all file
2. unmodified
   no changes are made in compare to last state (**after `git stage` or `git add` fired**)
3. modified
   modified the file in compare to last state of file (**after `git stage` or `git add` fired**)
4. staged
   files are save (with modification in compare to **last `git stage` or `git add` fired**)
   **if file are not in stage mode then modification of file are no longer save even if you fired `git commit`**

### git commit -m `<comit-msg>`

    save the changes

### git checkout `<filenm>`

    restore/overwrite file content from last commit content of same file

### git checkout -f

    restore/overwrite file content from last commit content of same file, for all file (which files are in modified state)

### git log

    history of commit
    if you fire `git add <file>` then it won't show u the same becoz u add to the stage so no diff there

### git log -p `-<number>`

    show last specified <number> of commits

### git diff

    show diffrence between working file(modifieding) with `staged` files(privisiouly add to `staged` state),

### git diff --stage

    compare `staged` file to last commit file

### git rm `<filenm>`

remove/delete file from folder(remove from HDD)
so file is no longer avail so it also remove from `stage` area

### git rm --cached `<filenm>`

remove from `staged` area but exit in Hdd

---

## creating branches

> when you change branch its actully change the files to
> which means if in one branch u have 10 line of code and then u change the branch
> in that branch u have 15 line of code in same file
> then in editor also ur files contain change

### git branch

show the avail branches

### git branch `<branchNm>`

create new branch

### git checkout `<branchNm>` or git switch `<branchNm>`

change the branch from master(curr) to new (specified)

### git checkout -b `<branchNm>`

create and switch to the branch

### git commit -a -m `<msg>`

add file into staged area and commit with msg

### git merge `<branchNm>`

add changes/code to the master branch from specified branch,
before it move to the master branch to add master,
or in which branch where you wish to add another branch's chganges/code

### git diff [first-branch]...[second-branch]

Shows content differences between two branches

---

# github

### git remote add `<urlShortNm>` `<urlOfRepo>`

its Add remote link name in urlShortNm with urlOfRepo (remote link of repo's like github acc link where all project kept in)
so further we just use urlShortNm instead of Long url intial/mainly used `origin`

### git push -u `origin(urlShortnm)' `<branchName>`

its send/push all code from local machine to remote-location/github acc or bitbucket
only push one branch with its own all commites
**before it set the `SSH` client and used `SSH` URL for `private repos` **

### git push

it will push code in where u last time used push with `-u`

### git remote set-url `<urlShortNm>` `<urlOfRepo>`

its sets/overwrite/change url that previosuly add

### git clone `<urlOfRepo>` `<folderNm>`

it will clone code from given url into the given folder name
if fol name is not given then it will be take repo's name

---

**Do check by own**

### git fetch

Downloads all history from the remote tracking branches

### git merge

Combines remote tracking branches into current local branch

### git push

Uploads all local branch commits to GitHub

### git pull

Updates your current local working branch with all new commits from the corresponding remote branch on GitHub.
`git pull` is a combination of `git fetch` and `git merge`
