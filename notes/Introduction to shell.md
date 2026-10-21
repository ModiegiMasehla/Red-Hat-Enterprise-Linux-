# Introduction to the Linux Shell on Red Hat — Study Notes

These notes introduce the Linux shell, with examples relevant to Red Hat Enterprise Linux (RHEL). They cover the basic concepts, commands, arguments, directories, autocompletion, file management, navigation, permissions, and other essential shell skills.

## 1. What is Linux?

Linux is an open-source operating system used on servers, desktops, cloud platforms, and many other computing devices.

Red Hat Enterprise Linux (RHEL) is a Linux distribution developed by Red Hat for enterprise environments. It is commonly used for managing servers, networks, applications, and cloud infrastructure.

Examples of Linux distributions include:

- Red Hat Enterprise Linux (RHEL)
- Ubuntu
- Fedora
- Debian
- Rocky Linux

## 2. What is the shell?

The shell is a program that allows a user to communicate with the operating system by entering commands.

Instead of clicking icons and menus in a graphical user interface (GUI), you can type commands to perform tasks such as creating files, navigating directories, managing users, and checking system information.

User

Enters a command

Shell (e.g. Bash)

Interprets the command

Linux operating system

Performs the requested operation

### Important terms

- Shell: A command interpreter that accepts and processes commands.
- Terminal: The application or interface where you interact with a shell.
- Command-line interface (CLI): A text-based way to interact with a computer.
- Bash: The Bourne Again SHell, a widely used shell and the default interactive shell in many RHEL environments.
- GUI: A graphical user interface that uses windows, menus, buttons, and icons.
- Kernel: The core of the operating system. It manages resources such as memory, processes, and hardware.

Remember: the terminal is where you type; the shell interprets what you type.

## 3. What is a shell prompt?

The shell prompt indicates that the shell is ready to accept a command.

For example:

```
[user@localhost ~]$
```

| Part        | Meaning                                |
| ----------- | -------------------------------------- |
| `user`      | The current username                   |
| `localhost` | The computer's hostname                |
| `~`         | The current user's home directory      |
| `$`         | Usually indicates a regular user shell |

A root user's prompt often ends with `#` instead of `$`.

Example:

```
[root@localhost ~]#
```

Important: The `#` shown in many Linux tutorials may represent the root prompt or a comment marker, depending on where it appears. Do not type the prompt itself when entering a command.

## 4. Commands, arguments, and options

A command tells the shell what action to perform.

An argument provides information that the command needs, such as a filename or directory.

An option modifies how the command behaves. Options are commonly written with a hyphen (`-`) or double hyphen (`--`).

General structure:

```
command [options] [arguments]
```

Example:

```
ls -l /home
```

- `ls` — command that lists directory contents.
- `-l` — option that displays detailed information.
- `/home` — argument specifying the directory to list.

Another example:

```
mkdir projects
```

- `mkdir` — command to create a directory.
- `projects` — argument specifying the directory name.

### More examples

| Command          | Purpose                                    |
| ---------------- | ------------------------------------------ |
| `pwd`            | Displays the current working directory     |
| `ls`             | Lists files and directories                |
| `ls -a`          | Shows hidden files as well                 |
| `ls -l`          | Shows detailed file information            |
| `cd /etc`        | Changes to the `/etc` directory            |
| `mkdir notes`    | Creates a directory named `notes`          |
| `touch file.txt` | Creates an empty file if it does not exist |
| `cat file.txt`   | Displays a file's contents                 |

## 5. Arguments and options in more detail

Arguments and options are not the same thing.

Consider this command:

```
ls -lh /var/log
```

- `ls` is the command.
- `-l` requests a long listing.
- `-h` displays file sizes in a human-readable format.
- `/var/log` is the argument identifying the directory.

You can combine short options, as in `-lh`.

Long options often use two hyphens:

```
ls --all
```

This displays hidden entries, including filenames that begin with a dot (`.`).

## 6. Autocompletion

Autocompletion is a shell feature that completes commands, filenames, directory names, and paths when you press the Tab key.

It saves time and reduces typing mistakes.

### Example 1: Completing a command

Type:

```
pw
```

Press `Tab`. Depending on what is installed and available, Bash may complete the command to `pwd`.

### Example 2: Completing a directory

Suppose you have a directory called `Documents`.

Type:

```
cd Doc
```

Press `Tab`. If the match is unambiguous, Bash may complete it to:

```
cd Documents
```

### Example 3: Multiple matches

If several filenames begin with the same letters, pressing `Tab` twice may display possible matches, depending on your shell configuration.

Benefits of autocompletion:

- Saves time.
- Reduces spelling errors.
- Helps with long filenames and directory paths.
- Makes command-line work more efficient.

### Useful keyboard shortcuts

| Shortcut   | Function                                             |
| ---------- | ---------------------------------------------------- |
| `Tab`      | Autocompletes commands and paths                     |
| `↑` / `↓`  | Browses previously entered commands                  |
| `Ctrl + C` | Interrupts the current foreground command            |
| `Ctrl + L` | Clears the terminal display                          |
| `Ctrl + A` | Moves the cursor to the start of the line            |
| `Ctrl + E` | Moves the cursor to the end of the line              |
| `Ctrl + R` | Searches command history                             |
| `Ctrl + D` | Sends end-of-input; often exits an interactive shell |

## 7. Directories and the Linux file system

A directory is a location that contains files and other directories. It is similar to a folder in a graphical operating system.

Linux organizes files and directories in a hierarchical structure that begins at the root directory, represented by `/`.

`/` — Root directory

`/home`

Users' personal directories, such as `/home/student`.

`/etc`

System-wide configuration files.

`/var`

Variable data, including many logs and caches.

`/tmp`

Temporary files.

`/usr`

Many installed programs, libraries, and shared resources.

`/root`

The root administrator's home directory.

`/dev`, `/proc`, `/sys`

Special interfaces for devices and kernel/system information.

### Absolute and relative paths

An absolute path begins at `/` and identifies a location from the root of the file system.

```
/home/student/Documents
```

A relative path identifies a location relative to the current working directory.

```
Documents
```

If your current directory is `/home/student`, then `Documents` refers to `/home/student/Documents`.

### Special directory symbols

| Symbol | Meaning                                          |
| ------ | ------------------------------------------------ |
| `/`    | Root of the file system                          |
| `~`    | Current user's home directory                    |
| `.`    | Current directory                                |
| `..`   | Parent directory                                 |
| `-`    | Previous working directory when used with `cd -` |

## 8. Navigating directories

The most important navigation commands are `pwd`, `ls`, and `cd`.

### `pwd` — Print Working Directory

Displays the full path of the directory you are currently in.

```
pwd
```

Example output:

```
/home/student
```

### `ls` — List

Displays the files and directories in a location.

```
ls
ls -l
ls -a
ls -lh
ls /etc
```

### `cd` — Change Directory

Moves from one directory to another.

```
cd /etc
cd ..
cd ~
cd -
```

`cd ..` moves up one directory, while `cd ~` takes you to your home directory.

## 9. Creating, copying, moving, and deleting files

| Command    | Purpose                                          | Example                          |
| ---------- | ------------------------------------------------ | -------------------------------- |
| `mkdir`    | Creates a directory                              | `mkdir projects`                 |
| `mkdir -p` | Creates parent directories if needed             | `mkdir -p work/java/tests`       |
| `touch`    | Creates an empty file if needed                  | `touch notes.txt`                |
| `cp`       | Copies a file                                    | `cp notes.txt backup.txt`        |
| `cp -r`    | Copies a directory and its contents recursively  | `cp -r projects projects-backup` |
| `mv`       | Moves or renames a file                          | `mv notes.txt study.txt`         |
| `rm`       | Removes a file                                   | `rm notes.txt`                   |
| `rmdir`    | Removes an empty directory                       | `rmdir old-folder`               |
| `rm -r`    | Removes a directory and its contents recursively | `rm -r old-folder`               |

Safety warning: Linux deletion commands such as `rm` may permanently remove files without placing them in a recycle bin. Check the path before running a deletion command, especially when using `rm -r` or `rm -rf`.

## 10. Viewing and editing file contents

Linux provides commands for reading and modifying text files.

| Command                    | Purpose                                       |
| -------------------------- | --------------------------------------------- |
| `cat file.txt`             | Prints file contents                          |
| `less file.txt`            | Views a file page by page                     |
| `head file.txt`            | Displays the first 10 lines by default        |
| `tail file.txt`            | Displays the last 10 lines by default         |
| `tail -f file.log`         | Follows new lines added to a log file         |
| `nano file.txt`            | Opens the file in Nano if installed           |
| `vi file.txt`              | Opens the file in Vi, where available         |
| `echo "Hello"`             | Prints text                                   |
| `echo "Hello" > file.txt`  | Writes text to a file, replacing its contents |
| `echo "Hello" >> file.txt` | Appends text to a file                        |

Be careful with `>` because it overwrites an existing file. Use `>>` to append instead.

## 11. Linux commands are case-sensitive

Linux commands and filenames are generally case-sensitive.

For example:

```
ls
```

is a valid command, but:

```
LS
```

normally is not.

Similarly, `notes.txt`, `Notes.txt`, and `NOTES.txt` can be three different filenames.

## 12. Hidden files and directories

In Linux, filenames that begin with a dot (`.`) are normally treated as hidden in directory listings.

Examples:

```
.bashrc
.bash_profile
.ssh
```

Use the following command to show hidden entries:

```
ls -a
```

To see hidden entries with detailed information:

```
ls -la
```

Configuration files such as `.bashrc` may contain settings for the Bash shell.

## 13. Getting help with commands

You do not need to memorize every command. Linux provides built-in help resources.

| Command     | Purpose                                              |
| ----------- | ---------------------------------------------------- |
| `man ls`    | Opens the manual page for `ls`                       |
| `ls --help` | Displays help for `ls`, when supported               |
| `help cd`   | Shows Bash's built-in help for `cd`                  |
| `type cd`   | Identifies how the shell interprets `cd`             |
| `which ls`  | Shows the path of an executable found through `PATH` |
| `history`   | Lists previously entered commands                    |

For example:

```
man mkdir
```

In a manual page, press `q` to quit. Some commands provide `--help`, but not every command supports that option.

## 14. Command history

The shell keeps a history of many previously entered commands.

```
history
```

You can also press the up-arrow key to recall a previous command.

To search history interactively:

1. Press `Ctrl + R`.
2. Type part of the command you remember.
3. Press `Ctrl + R` again to search older matches.
4. Press `Enter` to execute the displayed command, or use the arrow keys to edit it first.

History is useful for repeating commands without retyping them.

## 15. Command completion versus command history

These features are different:

- Autocompletion (`Tab`) helps finish a command or path you are currently typing.
- Command history (`↑`, `↓`, `history`) helps retrieve commands you entered previously.

For example, use `Tab` to complete `Doc` to `Documents`, but use the up-arrow to retrieve a command you ran earlier.

## 16. Absolute paths, spaces, and quoting

When filenames contain spaces, you must handle the spaces correctly.

Suppose the filename is `my notes.txt`.

You can use quotation marks:

```
cat "my notes.txt"
```

Or escape the space using a backslash:

```
cat my\ notes.txt
```

You can also use Tab completion to complete filenames containing spaces.

For commands that operate on multiple paths, remember that unquoted spaces normally separate arguments.

## 17. Redirection and pipes

The shell can direct command output to files or pass output between commands.

### Output redirection

```
ls > files.txt
```

Writes the output of `ls` to `files.txt`, replacing its previous contents.

```
ls >> files.txt
```

Appends the output to the end of the file.

### Input redirection

```
sort < names.txt
```

Uses `names.txt` as the input to `sort`.

### Pipes

The pipe symbol `|` sends one command's output to another command.

```
ls -l /etc | less
```

This sends the listing into `less`, allowing you to browse it page by page.

Another example:

```
cat /etc/passwd | wc -l
```

Counts the lines in `/etc/passwd`. For this specific task, `wc -l /etc/passwd` is simpler and avoids an unnecessary `cat`.

## 18. Wildcards and pattern matching

Wildcards let you work with groups of filenames.

| Symbol  | Meaning                          | Example            |
| ------- | -------------------------------- | ------------------ |
| `*`     | Matches zero or more characters  | `ls *.txt`         |
| `?`     | Matches one character            | `ls file?.txt`     |
| `[abc]` | Matches one character from a set | `ls file[123].txt` |

For example:

```
ls *.log
```

Lists filenames in the current directory that end in `.log`, if any match.

Remember that wildcards are generally expanded by the shell before the command runs.

## 19. File permissions and ownership

Linux uses permissions to control who can read, modify, or execute files and directories.

The three main permission groups are:

- User (u): The file owner.
- Group (g): Members of the file's assigned group.
- Others (o): Everyone else.

The three basic permissions are:

| Permission | Letter | For files                   | For directories                                                  |
| ---------- | ------ | --------------------------- | ---------------------------------------------------------------- |
| Read       | `r`    | Read contents               | List directory entries                                           |
| Write      | `w`    | Modify contents             | Create, remove, or rename entries, subject to other restrictions |
| Execute    | `x`    | Run an executable or script | Access/traverse the directory                                    |

Useful commands:

```
ls -l
chmod
chown
```

Example:

```
chmod u+x script.sh
```

Adds execute permission for the file's owner.

```
chown student:student file.txt
```

Changes a file's owner and group, assuming you have the required privileges.

Avoid changing ownership or permissions on system files without understanding the consequences.

## 20. Users, root, and `sudo`

Linux supports multiple user accounts. A regular user has permissions appropriate to that account, while `root` is the superuser with extensive administrative privileges.

The command `sudo` can run a command with elevated privileges when the user is authorized.

Example:

```
sudo dnf check-update
```

This asks `sudo` to run `dnf check-update` with elevated privileges. The exact behavior depends on the system's `sudo` configuration.

Best practice: Use a regular account for everyday tasks and elevate privileges only when necessary. Do not assume that every RHEL user is allowed to use `sudo`.

## 21. Environment variables and `PATH`

An environment variable stores information that programs can use.

Examples include:

- `HOME` — the user's home directory.
- `USER` — the current username in typical environments.
- `PATH` — directories searched when you run a command by name.

Display a variable:

```
echo "$HOME"
echo "$PATH"
```

When you type:

```
ls
```

the shell uses its command lookup rules to find the executable. The `PATH` environment variable contains a colon-separated list of directories searched for executable programs.

## 22. Processes and system information

Linux commands can also display information about the operating system and running programs.

| Command    | Purpose                                    |
| ---------- | ------------------------------------------ |
| `whoami`   | Shows the effective username               |
| `id`       | Displays user and group IDs                |
| `uname -r` | Displays the kernel release                |
| `hostname` | Displays the system's hostname             |
| `date`     | Displays the system date and time          |
| `ps`       | Displays process information               |
| `top`      | Provides a live process and resource view  |
| `df -h`    | Shows file system disk usage               |
| `free -h`  | Shows memory usage                         |
| `uptime`   | Shows how long the system has been running |

Some commands may require extra packages or permissions, depending on the RHEL installation.

## 23. The Linux shell in Red Hat specifically

Red Hat Enterprise Linux uses many standard Linux commands, so the shell skills you learn on RHEL also apply to other Linux distributions.

RHEL-specific administration commonly involves the following tools:

| Command        | Purpose                            |
| -------------- | ---------------------------------- |
| `dnf`          | Manages software packages          |
| `systemctl`    | Manages system services and units  |
| `journalctl`   | Reads systemd journal logs         |
| `firewall-cmd` | Manages firewalld configuration    |
| `nmcli`        | Manages NetworkManager connections |
| `rpm`          | Queries and manages RPM packages   |

Examples:

```
dnf --help
systemctl status sshd
journalctl -n 20
```

The `systemctl` example checks the status of the SSH daemon service. Depending on the installed software, the service may not exist or may have a different configuration.

These commands are relevant to administration and troubleshooting, but you should learn the basic shell commands first.

## 24. Practical exercise: Your first shell session

Try the following exercise in a Linux or RHEL terminal using a regular user account.

## Practice checklist

0 of 10 completed

Display your current directory.

`pwd`

Create a practice directory.

`mkdir shell-practice`

Enter the new directory.

`cd shell-practice`

Create an empty file.

`touch notes.txt`

List the file with detailed information.

`ls -l`

Write a sentence into the file.

`echo "Learning Linux shell" > notes.txt`

Read the file's contents.

`cat notes.txt`

Create a copy of the file.

`cp notes.txt backup.txt`

List all entries, including hidden ones.

`ls -la`

Return to the parent directory.

`cd ..`

Reset checklist


## 25. Key terms to remember

| Keyword              | Definition                                              |
| -------------------- | ------------------------------------------------------- |
| Shell                | Program that interprets commands                        |
| Bash                 | A widely used Linux shell                               |
| Terminal             | Interface used to interact with the shell               |
| Command              | Instruction that performs an action                     |
| Argument             | Value or target supplied to a command                   |
| Option               | Modifier that changes a command's behavior              |
| Autocompletion       | Completing a command or path using Tab                  |
| Directory            | A location containing files and other directories       |
| Path                 | The location of a file or directory                     |
| Root directory       | The top-level directory, `/`                            |
| Home directory       | A user's personal directory                             |
| Absolute path        | A path beginning at `/`                                 |
| Relative path        | A path interpreted from the current directory           |
| Wildcard             | Pattern character used to match filenames               |
| Redirection          | Sending input or output to a file or other destination  |
| Pipe                 | Passing one command's output to another command         |
| Permission           | Rule controlling access to a file or directory          |
| Process              | A running program or task                               |
| Environment variable | A named value available to the shell and programs       |
| `sudo`               | Runs a command with elevated privileges when authorized |

The most important commands to master first are: `pwd`, `ls`, `cd`, `mkdir`, `touch`, `cp`, `mv`, `rm`, `cat`, `man`, and `history`.

Once you understand commands, arguments, paths, autocompletion, and navigation, you will have a solid foundation for learning more advanced Red Hat Linux administration.