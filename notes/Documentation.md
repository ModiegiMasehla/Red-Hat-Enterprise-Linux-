# Study Notes: Documentation on RHEL

**Course:** Red Hat Enterprise Linux Technical Overview (RH024)  
**Topic:** Documentation: online manuals on the system, man pages, command arguments, and config files

## 1. Why documentation matters

Linux ships with a lot of its own documentation. An administrator who can read the **online manuals on the system** can learn what a command does, which options it accepts, and how to configure a service, without leaving the terminal and even without internet access. The key idea: you do not need to memorise every option; you need to know where to look.

## 2. Where documentation lives

| Source | How to reach it | Best for |
|---|---|---|
| Manual pages (man pages) | `man command` | Full reference for a command, file or topic |
| Built-in help | `command --help` | Quick summary of usage and options |
| Shell help | `help cd`, `type cd` | Bash built-in commands |
| Info documents | `info command` | Longer, structured manuals for some GNU tools |
| Package documents | `/usr/share/doc/` | READMEs, examples, licences shipped with packages |
| Red Hat documentation | docs.redhat.com | Official guides and product documentation |

Useful RPM queries on RHEL for package documentation:

- `rpm -qd packagename` lists documentation files of an installed package.
- `rpm -qc packagename` lists its configuration files.

Note: on minimal installs and containers the manual pages may not be installed. On RHEL they come from the `man-db` and `man-pages` packages, which you can add with `dnf install man-db man-pages` if you have permission.

## 3. The `man` command and man pages

`man` opens the manual page for a command, file format or topic. A man page is displayed through a pager (usually `less`), so the same keys work.

### Reading a man page

Typical sections inside one page:

- **NAME**: the command and a one-line description.
- **SYNOPSIS**: the exact syntax (see section 4).
- **DESCRIPTION**: what it does and what each option means.
- **OPTIONS**: detailed list of options.
- **EXAMPLES**: sample use (when present).
- **FILES**: related config files.
- **SEE ALSO**: related pages.

### Navigation keys

| Key | Action |
|---|---|
| Space / `f` | Page forward |
| `b` | Page back |
| Up / Down arrows | Scroll one line |
| `/word` | Search forward for "word" |
| `n` / `N` | Next / previous match |
| `g` / `G` | Top / bottom |
| `h` | Help for the pager |
| `q` | Quit |

### Man page sections (numbers)

The same name can exist in several sections, so man pages are grouped by number.

| Section | Contents | Example |
|---|---|---|
| 1 | User commands | `man 1 ls` |
| 2 | System calls | `man 2 open` |
| 3 | Library functions | `man 3 printf` |
| 4 | Special files / devices | `man 4 null` |
| 5 | File formats and **config files** | `man 5 passwd` |
| 6 | Games | |
| 7 | Miscellaneous (conventions, overviews) | `man 7 man-pages` |
| 8 | System administration commands | `man 8 mount` |

Example of why the number matters: `passwd` is both a command and a file. `man passwd` shows the command (section 1) and `man 5 passwd` shows the format of the `/etc/passwd` file.

### Searching when you do not know the command name

- `man -k keyword` (same as `apropos keyword`) searches page names and descriptions.
- `man -f command` (same as `whatis command`) gives the one-line description.
- If searches return nothing, the index may need building: `sudo mandb` (administrator privilege required).

Example: `man -k archive` lists commands related to archives, such as `tar`.

## 4. How commands work with arguments

A command line has this general shape:

`command [options] [arguments]`

- **Command**: the program to run (`tar`).
- **Options** (also called flags or switches): change behaviour. Short form uses one dash (`-l`), long form uses two (`--help`). Short options can be combined (`-xvf`).
- **Arguments**: what the command acts on, such as files, directories, or a value.
- **Option arguments**: some options need a value of their own. For example `-f` in `tar` takes the archive file name, `-C` takes a directory.

### Reading the SYNOPSIS

- `[ ]` means optional.
- `...` means it can be repeated.
- `|` means choose one.
- Text in bold or capitals is replaced by your own value, e.g. `FILE`.

Example: `ls [OPTION]... [FILE]...` means options are optional and you may list several files.

### Example: `ls -l /etc`

- `ls` is the command.
- `-l` is the option (long listing).
- `/etc` is the argument (directory to list).

## 5. Worked examples with `tar`

`tar` creates and extracts archives. Its main options:

| Option | Meaning |
|---|---|
| `-c` | **c**reate an archive |
| `-x` | e**x**tract an archive |
| `-t` | **t**est / list contents |
| `-v` | **v**erbose, show files as they are processed |
| `-f archive` | use this archive **f**ile (its argument is the file name) |
| `-z` | compress or decompress with gzip |
| `-C dir` | change to directory `dir` before extracting |

| Command | What it does |
|---|---|
| `tar -cvf project.tar project` | Creates `project.tar` from the `project` directory, listing files as it goes |
| `tar -tvf project.tar` | Lists the contents of `project.tar` without extracting |
| `tar -czvf project.tar.gz project` | Creates a gzip-compressed archive |
| `tar -xvf project.tar` | Extracts the archive into the current directory |
| `tar -xvf project.tar -C restore` | Extracts into the existing directory `restore` |

Tips verified while practising (GNU tar 1.35):

- `-f` is followed by the archive name, so keep it last in a combined cluster: `-cvf name`, not `-cfv name`.
- Compressed archive was much smaller than the plain one for the same files (191 bytes versus 10240 bytes in a small test).
- The target directory for `-C` must already exist.
- Always list with `-t` before extracting an unknown archive.

To learn more: `man tar` and `tar --help`.

## 6. Configuration files

Most Linux services and tools are configured by plain text files.

- System-wide configuration lives mostly in `/etc` (for example `/etc/passwd`, `/etc/hostname`, `/etc/ssh/sshd_config`).
- Per-user configuration is often a hidden file or folder in the home directory (for example `~/.bashrc`).
- Man page section 5 documents file formats, so `man 5 passwd` explains what each field in `/etc/passwd` means.
- The FILES part of a command's man page names the config files it reads.
- Before editing a config file, make a backup (for example `cp file file.bak`), and reload or restart the service afterwards.
- Config files of an installed RPM package can be listed with `rpm -qc packagename`.

## 7. Quick reference

| I want to... | Command |
|---|---|
| Read the manual for a command | `man tar` |
| Read a specific section | `man 5 passwd` |
| Search manuals by keyword | `man -k archive` |
| One-line description | `man -f tar` |
| Quick usage summary | `tar --help` |
| Help for a Bash built-in | `help cd` |
| See whether something is built in | `type cd` |
| List a package's docs / config files | `rpm -qd pkg` / `rpm -qc pkg` |

## 8. Self-check questions

1. What are the three parts of a command line?
2. Why does `man passwd` differ from `man 5 passwd`?
3. In `tar -xvf project.tar -C restore`, what are the arguments of `-f` and `-C`?
4. How would you find a command for compressing files if you did not know its name?
5. Where would you look for configuration files of a service, and where for their documentation?

**Answers:** (1) command, options, arguments. (2) The first shows section 1, the passwd command; the second shows section 5, the file format. (3) `-f` takes `project.tar`; `-C` takes `restore`. (4) `man -k compress`. (5) Configuration under `/etc`; documentation through `man`, section 5, and `/usr/share/doc`.