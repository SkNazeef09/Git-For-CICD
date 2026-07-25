# Using Git — Local Repository & Remote GitHub Setup

A hands-on tutorial covering Git installation, initializing a local repository, making commits, and connecting to a remote repository on GitHub via SSH.

## Table of Contents

- [1. Install Git](#1-install-git)
- [2. Initialize a Local Git Repository](#2-initialize-a-local-git-repository)
- [3. Stage and Commit Changes](#3-stage-and-commit-changes)
- [4. View Commit History](#4-view-commit-history)
- [5. Connect to a Remote Repository](#5-connect-to-a-remote-repository)

---

## 1. Install Git

```bash
sudo apt update
sudo apt install git

git --version
```

---

## 2. Initialize a Local Git Repository

```bash
mkdir gitdemo
cd gitdemo
git init
```

Create a file:

```bash
nano file1
```

Add the following content:

```
this is first line of code
```

Check the repository status:

```bash
git status
```

---

## 3. Stage and Commit Changes

### Add the file to the staging area

```bash
git add file1
git status
```

### Configure your Git identity

```bash
git config user.name "Nazeef Shaikh"
git config user.email "nazeef@gmail.com"
```

### Create the initial commit

```bash
git commit
```

> When prompted, this will open your editor to write a commit message — you'll also need your GitHub credentials configured if pushing later.

### Modify the file

```bash
nano file1
```

Append a second line:

```
this is second line of code
```

Check status, stage, and commit the change:

```bash
git status
git add file1
git status
git commit -m "added second line of code"
```

---

## 4. View Commit History

```bash
git log
```

---

## 5. Connect to a Remote Repository

### Generate an SSH key

```bash
ssh-keygen -t rsa -b 4096
```

Display the public key:

```bash
cd .ssh
cat id_rsa.pub
```

Copy the output and add it to your GitHub account:

**GitHub → Settings → SSH and GPG Keys → New SSH Key**

### Clone the remote repository

```bash
cd
mkdir gitdemo2
cd gitdemo2

git clone git@github.com:aasemquazi/test1.git

cd test1
git status
```

### Create and commit a new file

```bash
nano pqr
```

Content:

```
first line of code
```

Check status, stage, and commit:

```bash
git status
git add pqr
git status
git commit -m "added"
git status
```

### Push to GitHub

```bash
git push
```

Verify the changes on [GitHub.com](https://github.com).

---

## References

- [Git Documentation](https://git-scm.com/doc)
- [Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)
- [Git Basics — Getting a Git Repository](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)
