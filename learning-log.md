# Linux Administration Learning Log

This file records the topics studied, practical work completed, challenges, and next steps.

## 15 October 2026 — Video 1: Linux Distributions

**Course:** Red Hat Enterprise Linux Technical Overview (RH024)  
**Status:** Video watched; notes and exercise prepared. Practical exercise still needs to be completed.

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
- [ ] Complete the Linux distributions exercise.
- [ ] Run the environment-identification commands on my Linux machine.
- [ ] Record command output and reflection answers.
- [ ] Commit and push the completed exercise.

### Challenges / questions to revisit

- Confirm which distribution and version I use on my development machine.
- Practise identifying which package manager belongs to a distribution.
- Check the current official RHEL lifecycle information when studying release and support planning.

### Next step

Complete [`practical-exercises/linux-distributions-exercise.md`](practical-exercises/linux-distributions-exercise.md), then continue with the next RH024 lesson.

---

## 20 October 2026 — Introduction to the Linux Shell

**Course:** Red Hat Enterprise Linux Technical Overview (RH024)  
**Status:** Introduction notes reviewed; 30-minute practical exercise prepared. Practical exercise still needs to be completed.

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
- [ ] Complete the shell exercise in a Linux terminal.
- [ ] Practise `pwd`, `ls`, `cd`, and path navigation.
- [ ] Practise autocompletion and command history.
- [ ] Create, inspect, copy, and rename practice files.
- [ ] Practise safe output redirection and a simple pipe.
- [ ] Record the command outputs and reflection answers in the exercise file.
- [ ] Commit and push the completed exercise to GitHub.

### Challenges / questions to revisit

- Identify the shell and Linux distribution/version on my machine.
- Practise explaining the difference between a command, an option, and an argument.
- Become more confident using absolute and relative paths.
- Practise autocompletion, quoting filenames with spaces, and using `man` pages.
- Understand file permissions before changing them or using administrative privileges.

### Next step

Complete [`practical-exercises/introduction-to-shell-exercise.md`](practical-exercises/introduction-to-shell-exercise.md), record the results, then continue with the next RH024 lesson.
