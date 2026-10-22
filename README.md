# Red Hat Linux Administration Learning Journey

## Overview

This repository documents my learning journey in Linux administration as I work through the free **Red Hat Enterprise Linux Technical Overview (RH024)** course offered by Red Hat.

My goal is to develop a strong foundation in Linux, gain practical experience with command-line tools and system administration, and build the skills needed to pursue Red Hat certifications and future opportunities in Linux administration, cloud computing, DevOps, and cybersecurity.

I will use this repository to record my notes, practical exercises, commands, troubleshooting experiences, and progress through consistent Git commits.

## Learning Objectives

- Understand Linux operating system fundamentals.
- Become comfortable navigating the Linux command line.
- Manage files, directories, users, groups, and permissions.
- Learn essential Linux system administration concepts.
- Understand processes, services, and system resources.
- Practise basic system monitoring and troubleshooting.
- Develop good documentation and version-control habits.
- Build a foundation for further Red Hat Enterprise Linux training and certification.

## Topics Covered

The following topics are documented as I progress through the course and practical exercises.

- [x] Introduction to Linux and Red Hat Enterprise Linux (Linux distributions: kernel, distributions, Fedora, CentOS Stream, RHEL, RPM and DNF)
- [ ] Linux architecture and operating system fundamentals
- [x] Command-line navigation and essential commands (introduction to the shell)
- [ ] File and directory management (started: create, copy, rename and quoting filenames)
- [ ] File permissions and ownership
- [ ] User and group management
- [ ] Processes and system resource monitoring
- [ ] Services and system administration basics
- [ ] Software and package management concepts
- [ ] Networking fundamentals
- [ ] System logs and troubleshooting
- [ ] Practical exercises and revision notes
- [ ] Documentation and man pages (notes written and exercise prepared; exercise not yet completed)

*Progress will be updated as each topic is studied and practised.*

## Repository Structure

```text
red-hat-linux-administration/
├── README.md
├── notes/
│   ├── linux-fundamentals.md
│   ├── introduction-to-shell.md
│   ├── rhel-documentation-study-notes.md
│   └── 
├── practical-exercises/
│   ├── linux-distributions-exercise.md
│   ├── introduction-to-shell-exercise.md
│   ├── documentation-man-pages-exercise.md
│   └── 
└── progress/
    └── learning-log.md
```

The structure will evolve as I complete more lessons and practical exercises.

## Practical Learning Approach

For each topic, I aim to:

1. Study the relevant course material.
2. Write concise notes in my own words.
3. Practise commands in a Linux environment.
4. Record examples and explain what each command does.
5. Document errors, troubleshooting steps, and lessons learned.
6. Commit and push my progress to GitHub.

## Example Linux Commands

Some basic commands I will practise and document include:

| Command | Purpose |
|---|---|
| `pwd` | Display the current working directory |
| `ls -la` | List files, including hidden files, with details |
| `cd` | Change directories |
| `mkdir` | Create a directory |
| `touch` | Create an empty file or update its timestamp |
| `cp` | Copy files or directories |
| `mv` | Move or rename files |
| `cat` | Display file contents |
| `grep` | Search text for matching patterns |
| `find` | Search for files and directories |
| `whoami` | Display the current username |
| `df -h` | Display filesystem disk usage |
| `free -h` | Display memory usage |
| `ps aux` | Display running processes |
| `man command` | Open the manual page for a command |
| `man 5 passwd` | Open a specific man page section (5 = file formats and config files) |
| `man -k keyword` | Search manual pages by keyword |
| `command --help` | Show a quick usage summary |
| `type command` | Show how the shell interprets a command |
| `tar -cvf name.tar dir` | Create an archive |
| `tar -tvf name.tar` | List the contents of an archive |
| `tar -xvf name.tar -C dir` | Extract an archive into a directory |

These examples are an initial practice list, not a claim that every topic has been completed.

## Documentation, Man Pages and Config Files

Part of the RH024 course covers finding help on the system itself, without internet access.

- **Man pages:** `man` opens the online manuals on the system. Use `/word` to search, `n` for the next match and `q` to quit.
- **Sections:** the same name can exist in several sections. `man passwd` shows the command, while `man 5 passwd` shows the format of the `/etc/passwd` file.
- **Searching:** `man -k keyword` finds pages by topic and `man -f command` gives a one-line description.
- **Arguments:** a command line has the form `command [options] [arguments]`, and some options take their own value, such as `-f archive.tar` in `tar`.
- **Config files:** system-wide configuration is mostly in `/etc`, and man page section 5 documents the file formats.

Example: `tar -xvf project.tar -C restore` extracts `project.tar` into the existing directory `restore`.

## Learning Log

I will use the learning log to track:

- **Date:** When I studied or practised a topic.
- **Topic:** The concept covered.
- **Practical work:** Commands or exercises completed.
- **Challenges:** Errors or concepts that needed further research.
- **Key takeaways:** What I learned and how I can apply it.

Completed so far: Linux distributions (15 October 2026), introduction to the shell (20 October 2026). In progress: documentation and man pages (21 October 2026). See `progress/learning-log.md`.

## Resources

- [Red Hat Enterprise Linux Technical Overview (RH024)](https://www.redhat.com/en/services/training/rh024-red-hat-linux-technical-overview)
- [Red Hat Documentation](https://docs.redhat.com/)
- [Red Hat Customer Portal](https://access.redhat.com/)
- [Linux man-pages project](https://www.kernel.org/doc/man-pages/)

## Version Control and Consistency

This repository is also an opportunity to practise Git and GitHub workflows. I will aim to make meaningful commits that reflect actual learning and progress.

Example commit messages:

```text
docs: add Linux fundamentals notes
docs: document essential command-line commands
learn: add file management exercises
learn: document Linux permissions
docs: update learning progress log
docs: add documentation and man pages notes
```

## Career Goals

Linux administration is an important foundation for my software engineering journey. I am particularly interested in developing skills that complement software development, data engineering, cloud technologies, and cybersecurity.

Through this project, I aim to demonstrate curiosity, consistency, practical problem-solving, and a commitment to continuous learning. I also hope to use