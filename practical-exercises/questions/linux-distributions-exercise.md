# Practical Exercise: Linux Distributions

**Topic:** Linux Distributions  
**Suggested time:** 30–45 minutes  
**Status:** Ready to complete

## Learning outcomes

By completing this exercise, I should be able to:

- Explain the difference between the Linux kernel and a Linux distribution.
- Describe the roles of Fedora, CentOS Stream, and RHEL.
- Explain why distributions have different release schedules and configuration choices.
- Recognise basic RPM/DNF package-management commands.
- Identify the factors to consider when choosing a distribution.

## Part A — Check your understanding

Answer in your own words. Use the notes only after attempting each question.

1. What is the Linux kernel responsible for?
2. What extra components turn the kernel into a usable Linux distribution?
3. Explain one difference between a Linux kernel and a Linux distribution.
4. What is open-source software? Does open source always mean software is free of cost?
5. What role does Fedora play in the Red Hat ecosystem?
6. Where does CentOS Stream sit in relation to Fedora and RHEL?
7. What is one reason an organisation might choose RHEL?
8. Give three ways Linux distributions can differ.
9. What is a package manager, and why are dependencies important?
10. Explain the difference between RPM and DNF at a beginner level.
11. Why should an administrator check a distribution's lifecycle before planning an upgrade?
12. Why might a command that works on one Linux distribution not work exactly the same way on another?

## Part B — Put the distributions in context

Complete the table.

| Distribution | Main role / characteristic | One thing to investigate |
|---|---|---|
| Fedora |  |  |
| CentOS Stream |  |  |
| Red Hat Enterprise Linux (RHEL) |  |  |

Then write two or three sentences explaining the simplified relationship between the three distributions.

## Part C — Command-line exploration

Run these commands only on a Linux system where you have permission to work. If a command is unavailable, record that result instead of installing anything immediately.

```bash
# 1. Identify the current operating system
cat /etc/os-release

# 2. Identify the current user
whoami

# 3. Check whether DNF is available
dnf --version

# 4. Check whether the RPM tool is available
rpm --version

# 5. If RPM is installed, list a small sample of installed packages
rpm -qa | head -n 10
```

Record your results:

- Distribution name and version:
- Is DNF available?:
- Is RPM available?:
- What did you learn from the output?:
- Were any commands unavailable? If so, which ones?:

**Important:** If you are using Pop!_OS or another Debian/Ubuntu-based distribution, DNF and RPM may not be installed by default. That is expected. Do not install them just to complete this exercise. The purpose is to observe your current environment and compare it with the Red Hat ecosystem.

## Part D — Choose a distribution for a scenario

For each scenario, choose the most suitable direction from Fedora, CentOS Stream, or RHEL. Explain your reasoning; there may be more than one defensible answer depending on requirements.

1. A learner wants to explore newer Linux technologies and community-developed software.
2. A developer wants insight into changes being prepared for a future RHEL minor release.
3. A business needs a supported enterprise platform and values predictable maintenance.

For each answer, mention one factor you would check before making a final decision, such as support requirements, compatibility, or lifecycle.

## Part E — Reflection

Write a short paragraph answering these questions:

- What was the most important concept from this lesson?
- What is one thing you did not know before watching the video?
- How could understanding distributions help in software development, cloud computing, or cybersecurity?
- What topic would you like to investigate next?

## Self-assessment checklist

- [ ] I can explain what the Linux kernel does.
- [ ] I can define a Linux distribution.
- [ ] I can describe the broad relationship between Fedora, CentOS Stream, and RHEL.
- [ ] I understand the basic purpose of RPM and DNF.
- [ ] I can name several ways distributions differ.
- [ ] I have recorded my command-line observations.
- [ ] I have answered the reflection questions.

## Suggested Git commit

After completing the exercise and recording your answers, use a commit message such as:

```text
learn: complete Linux distributions exercise
```
