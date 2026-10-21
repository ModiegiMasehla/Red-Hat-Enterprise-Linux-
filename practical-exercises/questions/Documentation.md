# Practical Exercise: Linux Documentation, Man Pages, Arguments and Config Files

**Learning journey:** Red Hat Enterprise Linux Technical Overview (RH024)  
**Estimated time:** 30 minutes  
**Level:** Beginner  
**Environment:** A Linux terminal, ideally Red Hat Enterprise Linux (RHEL). Other distributions work for practice.

## Objective

Practise using the online manuals on the system: the `man` command and man pages, `--help`, command arguments, a `tar` example, and finding config files.

## Safety rules

- Work only inside the practice directory you create below.
- Do not use `sudo` and do not edit any system config files. Only read them.
- Do not run `rm -rf` or delete anything outside your practice directory.
- If `man` is unavailable, record that fact and use `--help` instead. Do not install anything just for this exercise.

## Task 1: Read a man page (6 minutes)

```bash
man ls
```

Use these keys: Space (next page), `b` (back), `/hidden` then Enter (search), `n` (next match), `q` (quit).

Record:

- The one-line description under NAME:
- The option that shows hidden entries:
- The option for a long listing:

**Check your understanding:** What does the SYNOPSIS part of a man page show?

## Task 2: Man page sections (5 minutes)

```bash
man passwd
man 5 passwd
man 7 man-pages
```

Record:

- What does `man passwd` describe?
- What does `man 5 passwd` describe?
- What do the numbers 1, 5 and 8 mean?

**Check your understanding:** Why does the same name appear in different sections?

## Task 3: Search the manuals (4 minutes)

```bash
man -k archive
man -f tar
tar --help | head -n 20
```

If `man -k` returns nothing, record that the manual index may not be built (building it needs administrator rights, so do not do it here).

Record:

- Two commands found by `man -k archive`:
- The description given by `man -f tar`:

## Task 4: Arguments and options with tar (8 minutes)

```bash
mkdir -p ~/doc-practice/project/docs
cd ~/doc-practice
echo "hello" > project/docs/a.txt
echo "world" > project/b.txt
tar -cvf project.tar project
tar -tvf project.tar
tar -czvf project.tar.gz project
ls -l project.tar project.tar.gz
mkdir restore
tar -xvf project.tar -C restore
ls -R restore
```

Record for each tar command what it did:

| Command | What it did |
|---|---|
| `tar -cvf project.tar project` | |
| `tar -tvf project.tar` | |
| `tar -czvf project.tar.gz project` | |
| `tar -xvf project.tar -C restore` | |

Also record the file sizes of `project.tar` and `project.tar.gz`, and which is smaller.

**Check your understanding:** In `tar -xvf project.tar -C restore`, identify the command, the options and the option arguments.

## Task 5: Find configuration files (4 minutes)

Read only. Do not edit.

```bash
ls /etc | head -n 20
cat /etc/os-release
man 5 hostname
```

If `rpm` is available (RHEL, Fedora), also try:

```bash
rpm -qc bash | head -n 5
rpm -qd bash | head -n 5
```

If `rpm` is unavailable (Debian/Ubuntu), record that and skip this step.

Record:

- Where system configuration files are kept:
- One config file and what it holds:
- Was `rpm` available?

**Check your understanding:** Which man page section documents config file formats?

## Task 6: Review and reflect (3 minutes)

1. Where can you find documentation on a Linux system without internet access?
2. What are the keys to search inside a man page and to quit it?
3. What is the difference between an option and an argument?
4. Give one `tar` command to create an archive and one to list it.
5. How do you find a command when you only know the topic?
6. Where do config files usually live, and how do you learn their format?

## Cleanup (inside the practice directory only)

```bash
cd ~
rm -r ~/doc-practice
```

## Completion checklist

- [ ] Opened a man page and used search and quit keys.
- [ ] Compared man page sections 1 and 5.
- [ ] Used `man -k`, `man -f` or `--help`.
- [ ] Created, listed and extracted a tar archive.
- [ ] Identified command, options and arguments.
- [ ] Located config files under `/etc`.
- [ ] Answered the reflection questions.

## Results log

**Date completed:** 
**Distribution/version:**  
**Time taken:** 

### Commands I ran successfully

-

### Output or observations

-

### Challenges and how I resolved them

-

### Reflection: what I learned

-

### Next practice goal

-

## Quick revision quiz

1. Which command opens the manual for `ls`?  `man ls` / `ls man` / `help ls --man`
2. Which key quits a man page?  `q` / `x` / `Esc Esc`
3. Which man section covers config file formats?  `1` / `5` / `8`
4. In `tar -cvf a.tar dir`, what is `a.tar`?  The command / an option argument / a section
5. Which option of tar extracts an archive?  `-x` / `-c` / `-t`
6. Which command searches manuals by keyword?  `man -k` / `man -q` / `man -z`

## Answer key

1. `man ls`. 2. `q`. 3. `5`. 4. An option argument (the value of `-f`). 5. `-x`. 6. `man -k`.