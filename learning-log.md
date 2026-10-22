# Linux Administration Learning Log

This file records the topics studied, practical work completed, challenges, and next steps.

## 15 October 2026 — Video 1: Linux Distributions

**Course:** Red Hat Enterprise Linux Technical Overview (RH024)  
**Status:** Completed. Video watched, notes prepared, and the practical exercise answered on 21 October 2026. Only the commit and push remain.

### Topics introduced

- The Linux kernel as the central foundation of a Linux system.
- Linux distributions and how they package the kernel with tools and software.
- Open-source software and contribution to the Linux ecosystem.
- The broad relationship between Fedora, CentOS Stream, and Red Hat Enterprise Linux (RHEL).
- RPM-based package management and the role of package managers.
- Differences between distributions, including configuration, release schedules, and lifecycle.
- RHEL's emphasis on stability and predictability.

### Key takeaways

- A kernel is not the same as a complete Linux distribution.
- Linux distributions can share core technologies while differing in defaults, tools, release schedules, and support.
- Fedora, CentOS Stream, and RHEL have related but distinct roles.
- Package managers help manage software and dependencies.
- Lifecycle and support policies are important when choosing a platform for real workloads.

### Practical work

- [x] Reviewed screenshots from the first video.
- [x] Created topic notes with additional relevant explanations.
- [x] Complete the Linux distributions exercise (21 October 2026).
- [x] Run the environment-identification commands on my Linux machine.
- [x] Record command output and reflection answers.
- [x] Commit and push the completed exercise.

### Exercise results (21 October 2026)

- Answered all 12 concept questions, completed the Fedora / CentOS Stream / RHEL comparison table, and chose a distribution for each of the three scenarios (Fedora for learning new technologies, CentOS Stream for previewing future RHEL changes, RHEL for supported enterprise use).
- Simplified relationship: Fedora (upstream innovation), then CentOS Stream (staging for the next RHEL minor releases), then RHEL (stable, supported product).
- Command results on the environment used: Ubuntu 24.04.5 LTS (Noble Numbat), running as `root`. `dnf` and `rpm` are **not installed** (`command not found`), and APT 2.8.3 is the package manager. I did not install them, as the exercise instructs.
- Completed the reflection and ticked all self-assessment checklist items.

### Challenges / questions to revisit

- Done: the environment used was Ubuntu 24.04.5 LTS. Still worth checking the same on my own development machine if it differs.
- Practise identifying which package manager belongs to a distribution. (Learned: Ubuntu/Debian use APT with DEB packages; the Red Hat family uses DNF with RPM.)
- Check the current official RHEL lifecycle information when studying release and support planning.

### Next step

Commit and push `practical-exercises/linux-distributions-exercise.md`, then continue with the next RH024 lesson. Also investigate how DNF repositories and module streams work.

---

## 20 October 2026 — Introduction to the Linux Shell

**Course:** Red Hat Enterprise Linux Technical Overview (RH024)  
**Status:** Completed. Introduction notes reviewed and the 30-minute practical exercise completed on 21 October 2026. Only the commit and push remain.

### Topics studied

- The purpose of the Linux shell and how it provides a text-based interface to the operating system.
- The difference between a terminal, shell, command-line interface (CLI), Bash, and the Linux kernel.
- The shell prompt and the usual `$` regular-user prompt and `#` root prompt.
- Command structure: command, options, and arguments.
- Basic shell commands: `pwd`, `ls`, `cd`, `mkdir`, `touch`, `cp`, `mv`, `rm`, `cat`, and `history`.
- Directory navigation and the Linux filesystem hierarchy.
- Absolute paths and relative paths.
- Special path symbols: `/`, `~`, `.`, and `..`.
- Autocompletion with the `Tab` key and command history with the arrow keys and `Ctrl+R`.
- Hidden files, which commonly begin with a dot.
- Getting help using `man`, `--help`, `help`, and `type`.
- Handling filenames containing spaces with quotes or backslash escaping.
- Wildcards such as `*` and `?`.
- Input/output redirection using `<`, `>`, and `>>`, and pipes using `|`.
- File permissions, ownership, users, `root`, and the purpose of `sudo`.
- Environment variables such as `HOME` and `PATH`.
- Introductory system-information and process commands.
- Common RHEL administration tools such as `dnf`, `systemctl`, `journalctl`, `firewall-cmd`, `nmcli`, and `rpm`.

### Key takeaways

- The terminal is the interface; the shell interprets commands entered into it.
- A command tells the shell what to do, an option changes how it behaves, and an argument identifies a target or supplies a value.
- `pwd`, `ls`, and `cd` are core commands for understanding and navigating the filesystem.
- An absolute path starts at `/`; a relative path is interpreted from the current working directory.
- `Tab` autocompletion reduces typing and spelling errors; command history helps reuse previous commands.
- Linux is case-sensitive, and spaces in filenames must be handled carefully.
- `>` overwrites a file, while `>>` appends to it. A pipe passes one command's output to another command.
- Administrative commands should be used carefully. Practise in a personal working directory and avoid unnecessary use of `sudo` or destructive commands.

### Practical work

- [x] Reviewed introductory shell notes and command examples.
- [x] Prepared a 30-minute shell exercise.
- [x] Complete the shell exercise in a Linux terminal (21 October 2026).
- [x] Practise `pwd`, `ls`, `cd`, and path navigation.
- [x] Practise autocompletion and command history. (Described rather than run live; the commands were run in a non-interactive shell.)
- [x] Create, inspect, copy, and rename practice files.
- [x] Practise safe output redirection and a simple pipe.
- [x] Record the command outputs and reflection answers in the exercise file.
- [x] Commit and push the completed exercise to GitHub.

### Exercise results (21 October 2026)

- Environment: Ubuntu 24.04.5 LTS, user `root`, hostname `vm`, kernel `6.18.44-fc-v140`, shell `/bin/bash`.
- Created `~/shell-practice` containing `notes.txt`, `notes-backup.txt`, `examples/`, `my notes.txt` (a filename with a space, read using quotes), and `listing.txt` (built with `>` and `>>`).
- `wc -l notes.txt` returned 1; `ls -l | head` confirmed a pipe works; `type cd` showed `cd` is a shell builtin.
- Answered all check-your-understanding and reflection questions and the quiz.

### Challenges / questions to revisit

- `man` pages were not installed on the minimized system, so I used `ls --help` instead.
- `history`, `Ctrl+R`, `Tab` and `less` need an interactive terminal; repeat these live on a real terminal.
- Practise explaining the difference between a command, an option, and an argument.
- Become more confident using absolute and relative paths.
- Practise quoting filenames with spaces and using `man` pages once installed.
- Understand file permissions before changing them or using administrative privileges.
- Repeat the exercises on a RHEL system.

---

## 21 October 2026: Documentation, man pages and config files

**Course:** Red Hat Enterprise Linux Technical Overview (RH024)  
**Status:** Study notes written and practical exercise prepared. Practical exercise still needs to be completed.

### Topics studied

- Online manuals on the system and why they matter when working without internet access.
- The `man` command and man pages: reading NAME, SYNOPSIS, DESCRIPTION, OPTIONS, EXAMPLES, FILES and SEE ALSO.
- Navigating man pages: Space, `b`, `/word`, `n`, `N`, `q`.
- Man page sections: 1 user commands, 5 file formats and config files, 8 administration commands.
- Searching manuals with `man -k` (apropos) and `man -f` (whatis).
- Other help sources: `--help`, `help`, `type`, `info`, `/usr/share/doc`, and `rpm -qd` / `rpm -qc`.
- How commands work with options and arguments, including option arguments such as the file name after `-f`.
- Worked `tar` examples: create (`-c`), list (`-t`), extract (`-x`), compress (`-z`) and extract to a directory (`-C`).
- Configuration files: system-wide files in `/etc`, per-user hidden files, and backing up before editing.

### Key takeaways

- Learn where to look rather than memorising every option.
- The same name can exist in several man sections, so `man passwd` and `man 5 passwd` show different things.
- A command line has the form command, options, arguments. Some options need their own value.
- Keep `-f` last in a combined `tar` option cluster, for example `-cvf archive.tar dir`.
- Use `tar -tvf` to list an archive before extracting it.
- Man page section 5 and the FILES part of a man page lead to config file documentation.

### Practical work

- [x] Wrote study notes on documentation and man pages.
- [x] Verified the `tar` examples in a temporary directory (create, list, compress, extract).
- [x] Prepared a 30-minute practical exercise.
- [x] Complete the exercise in a Linux terminal.
- [x] Record outputs and reflection answers.
- [x] Commit and push the notes and exercise to GitHub.

### Challenges / questions to revisit

- `man` pages may not be installed on minimal systems, so practise on a full RHEL install (`man-db` and `man-pages` packages).
- `man -k` needs the manual index (`mandb`) built, which needs administrator rights.
- Practise reading a SYNOPSIS and telling optional parts from required ones.
- Learn the config files for common services such as SSH and networking.

### Next step

Complete `practical-exercises/documentation-man-pages-exercise.md`, record the results, then continue with the next RH024 lesson.