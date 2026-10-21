# Practical Exercise: Introduction to the Linux Shell

**Learning journey:** Red Hat Enterprise Linux Technical Overview (RH024)  
**Estimated time:** 30 minutes  
**Level:** Beginner  
**Environment:** A Linux terminal, ideally Red Hat Enterprise Linux (RHEL). Other Linux distributions are suitable for practising the basic shell commands.

## Objective

Practise using the shell to identify your environment, navigate directories, use autocompletion, manage files, read command help, and use simple redirection and pipes.

## Safety rules

- Work only inside the practice directory you create below.
- Do not use `sudo` for this exercise.
- Do not run `rm -rf`, change system permissions, or delete files outside your practice directory.
- Your command output may differ slightly depending on your Linux distribution and configuration.
- If a command is unavailable, record that fact and continue where possible.

## Task 1 — Identify your environment (4 minutes)

Run these commands one at a time:

```bash
whoami
pwd
hostname
uname -r
cat /etc/os-release
echo "$SHELL"
```

Record the following:

- Current username:
- Current working directory:
- Hostname:
- Kernel release:
- Distribution name and version:
- Shell path:

**Check your understanding:** Which command identifies the distribution, and which command displays the kernel release?

## Task 2 — Navigate directories and practise autocompletion (5 minutes)

1. Display your current location:

   ```bash
   pwd
   ```

2. Go to your home directory:

   ```bash
   cd ~
   ```

3. List the contents, including hidden entries:

   ```bash
   ls -la
   ```

4. Create a practice directory and enter it:

   ```bash
   mkdir shell-practice
   cd shell-practice
   ```

5. Confirm your location:

   ```bash
   pwd
   ```

6. Practise autocompletion. Type `cd sh` from your home directory and press `Tab` if the `shell-practice` directory is a unique match. You can return to the practice directory with `cd ~/shell-practice`.

Record one example of how `Tab` helped you complete a command or path. If completion does not happen, press `Tab` twice to inspect possible matches or check that you typed the correct prefix.

**Check your understanding:** What is the difference between `cd ..` and `cd ~`?

## Task 3 — Create and manage files (7 minutes)

Make sure you are inside `~/shell-practice`, then run:

```bash
touch notes.txt
mkdir examples
echo "I am learning the Linux shell." > notes.txt
cat notes.txt
cp notes.txt backup.txt
mv backup.txt notes-backup.txt
ls -l
```

Expected result:

- `notes.txt` contains the sentence you wrote.
- `notes-backup.txt` is a copy of that file.
- `examples` is a directory.

Now create a filename with a space:

```bash
touch "my notes.txt"
ls -l
```

Read the file by using quotes:

```bash
cat "my notes.txt"
```

Record the names of the files and directory you created.

**Check your understanding:** Why did you put quotation marks around `my notes.txt`?

## Task 4 — Help, history, and useful shortcuts (4 minutes)

Run:

```bash
ls --help
history
type cd
```

If your system has manual pages installed, also try:

```bash
man ls
```

Press `q` to leave the manual page. If `man` is unavailable, record that and use `ls --help` instead.

Try these keyboard shortcuts:

- Press the up-arrow to recall a previous command.
- Press `Ctrl+R` and type a word from a command you ran.
- Press `Ctrl+L` to clear the terminal display.

Record which shortcut you found most useful and why.

## Task 5 — Redirection and pipes (5 minutes)

Ensure you are still inside `~/shell-practice`.

1. Save a directory listing to a file:

   ```bash
   ls > listing.txt
   ```

2. Append another line:

   ```bash
   echo "Shell practice completed." >> listing.txt
   ```

3. Read the file:

   ```bash
   cat listing.txt
   ```

4. Count the lines in your notes file:

   ```bash
   wc -l notes.txt
   ```

5. Send a directory listing through a pipe:

   ```bash
   ls -l | less
   ```

   Press `q` to exit `less`. If `less` is not installed, use `ls -l | head` instead.

**Check your understanding:** What is the difference between `>` and `>>`? What does `|` do?

## Task 6 — Review and reflect (5 minutes)

Answer these questions in your own words:

1. What is the difference between a terminal and a shell?
2. In `ls -l /etc`, identify the command, option, and argument.
3. What is the difference between an absolute path and a relative path?
4. What does `Tab` autocompletion do?
5. What does `..` mean in a path?
6. What is the difference between `>` and `>>`?
7. Name one command you found useful and explain why.
8. What is one shell concept you want to practise more?

## Completion checklist

- [ ] Identified the operating system, kernel, username, and shell.
- [ ] Navigated to the home directory and created a practice directory.
- [ ] Used `pwd`, `ls`, and `cd`.
- [ ] Tried autocompletion and command history.
- [ ] Created, copied, and renamed files.
- [ ] Opened a filename containing spaces.
- [ ] Used command help or a manual page.
- [ ] Used `>` and `>>` safely inside the practice directory.
- [ ] Tried a pipe.
- [ ] Answered the reflection questions.

## Results log

Complete this section after doing the exercise.

**Date completed:**  
**Linux distribution/version:**  
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

## Suggested GitHub workflow

From the root of your Linux learning repository, save this file as:

`practical-exercises/introduction-to-shell-exercise.md`

Update your learning log, then review the changes:

```bash
git status
git diff
```

Stage only the files for this lesson (adjust the learning-log filename if your repository uses a different one):

```bash
git add learning-log.md practical-exercises/introduction-to-shell-exercise.md
git commit -m "Add introduction to Linux shell learning exercise"
git push
```

If your learning log has a different filename or folder, substitute its actual path. Check `git status` before committing to ensure you are committing the intended files.
