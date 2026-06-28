# From Beginner to CTF

Author: Vida

Learning Platform:

* Kali Linux
* Burp Suite Community
* Firefox
* PortSwigger Web Security Academy

---

# Goal

This document contains everything I learn while studying Burp Suite and Web Security.

The purpose is not only to memorize commands but to understand how web applications work and how security vulnerabilities are discovered.

---

# Prerequisites

Before learning Burp Suite, a few Linux commands are essential.

They are used every day in penetration testing.

---

# Linux Cheat Sheet

## pwd

Print Working Directory

Shows the current directory.

```bash
pwd
```

Example

```text
/home/kali/Desktop
```

---

## ls

List files.

```bash
ls
```

Useful options

```bash
ls -l
```

Detailed view

```bash
ls -a
```

Show hidden files

---

## cd

Change directory.

```bash
cd Desktop
```

Return to Home

```bash
cd ~
```

Go back one directory

```bash
cd ..
```

---

## mkdir

Create directory.

```bash
mkdir CTF
```

---

## touch

Create empty file.

```bash
touch notes.txt
```

---

## cp

Copy files.

```bash
cp notes.txt backup.txt
```

Copy folders

```bash
cp -r folder backup
```

---

## mv

Move or rename files.

Rename

```bash
mv test.txt notes.txt
```

Move

```bash
mv notes.txt Desktop/
```

---

## rm

Delete file

```bash
rm notes.txt
```

Delete directory

```bash
rm -r folder
```

⚠ Never use:

```bash
rm -rf /
```

---

## cat

Display file content.

```bash
cat notes.txt
```

---

## nano

Simple text editor.

```bash
nano notes.txt
```

Useful shortcuts

```text
CTRL + O
Save

CTRL + X
Exit
```

---

## chmod

Change file permissions.

Example

```bash
chmod +x script.sh
```

Makes a script executable.

---

## find

Search files.

```bash
find . -name "*.txt"
```

---

## grep

Search inside files.

```bash
grep "admin" file.txt
```

---

## history

Show previous commands.

```bash
history
```

---

## clear

Clear terminal.

```bash
clear
```

Shortcut

```text
CTRL + L
```

---

## Stop running process

```text
CTRL + C
```

Very important.

---

# Why Linux?

Almost every penetration testing tool runs inside Linux.

Examples

* Burp Suite
* Nmap
* ffuf
* Gobuster
* Hydra
* SQLMap
* Wireshark

Learning Linux is one of the most important skills in Cyber Security.

---

# Next Chapter

Introduction to Burp Suite