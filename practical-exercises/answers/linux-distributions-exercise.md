# Linux Distributions — Completed Exercise

## Part A — Check your understanding

1\. What is the Linux kernel responsible for?

The Linux kernel is the core part of the operating system. It manages hardware and system resources such as the CPU, memory, storage devices, and other connected hardware. It also allows software applications to communicate with the hardware through system services.

2\. What extra components turn the kernel into a usable Linux distribution?

A Linux distribution combines the Linux kernel with system utilities, software libraries, applications, package-management tools, configuration files, and installation tools. Together, these components provide a complete operating system that users can install and operate.

3\. Explain one difference between a Linux kernel and a Linux distribution.

The kernel manages the computer's hardware and system resources, while a distribution includes the kernel and the additional software needed to create a usable operating system. For example, Linux is the kernel, while Fedora and Red Hat Enterprise Linux are distributions.

4\. What is open-source software? Does open source always mean software is free of cost?

Open-source software is software whose source code is available under a licence that allows people to inspect it and, subject to the licence terms, modify and redistribute it. Open source does not always mean free of cost. Companies can charge for subscriptions, technical support, training, and other services related to open-source software.

5\. What role does Fedora play in the Red Hat ecosystem?

Fedora is a community-driven Linux distribution that focuses on innovation and newer technologies. It serves as an important upstream source for technologies that may later be incorporated into Red Hat Enterprise Linux (RHEL).

6\. Where does CentOS Stream sit in relation to Fedora and RHEL?

CentOS Stream sits between Fedora and RHEL in the Red Hat development ecosystem. It provides a view of changes being developed for upcoming RHEL minor releases, allowing developers and contributors to test and work with these changes before they become part of a RHEL release.

7\. What is one reason an organisation might choose RHEL?

An organisation might choose RHEL because it offers an enterprise-focused platform with predictable maintenance, security updates, and commercial support options. This helps organisations manage their systems reliably and plan upgrades.

8\. Give three ways Linux distributions can differ.

1. Package management: Some distributions use DNF and RPM, while others use APT and DEB packages.
2. Release schedules: Some distributions introduce new features frequently, while others prioritise predictable updates and long-term maintenance.
3. Support models: Some rely mainly on community support, while others offer commercial support and defined enterprise maintenance policies.

9\. What is a package manager, and why are dependencies important?

A package manager is a tool used to install, update, search for, and remove software. Dependencies are other packages or components that a program needs to function correctly. Managing dependencies helps ensure that the required software is installed and compatible.

10\. Explain the difference between RPM and DNF at a beginner level.

RPM is a package format and a low-level tool for querying, installing, and managing RPM packages. DNF is a higher-level package manager that can download software from repositories and resolve dependencies automatically. In simple terms, RPM works directly with RPM packages, while DNF makes installing and managing software easier by handling dependencies and repositories.

11\. Why should an administrator check a distribution's lifecycle before planning an upgrade?

An administrator should check the lifecycle to understand how long a version will receive maintenance and security updates. This helps the organisation plan upgrades, avoid unsupported systems, maintain security, and reduce unexpected downtime or compatibility problems.

12\. Why might a command that works on one Linux distribution not work exactly the same way on another?

Different distributions may use different package managers, installed tools, configuration files, directory conventions, and default settings. For example, `dnf install` is used on DNF-based systems, while `apt install` is commonly used on Debian- and Ubuntu-based systems. A command may also be unavailable if its associated software is not installed.

## Part B — Put the distributions in context

| Distribution                    | Main role / characteristic                                                            | One thing to investigate                                           |
| ------------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Fedora                          | Community-driven distribution focused on innovation and newer technologies.           | Its release schedule and how it introduces new software.           |
| CentOS Stream                   | Development distribution that tracks changes for upcoming RHEL minor releases.        | How developers contribute to and test upcoming RHEL changes.       |
| Red Hat Enterprise Linux (RHEL) | Enterprise Linux platform focused on stability, predictable maintenance, and support. | Its support lifecycle, security updates, and subscription options. |

Explain the relationship in two or three sentences:

Fedora is an important upstream source of new technologies for the Red Hat ecosystem. CentOS Stream provides visibility into the development of upcoming RHEL minor releases, while RHEL provides an enterprise-focused platform with predictable maintenance and support. Although the distributions are related, they have different purposes and release processes.

## Part C — Command-line exploration

Since you use Pop!\_OS on your development machine, the following is an example of how to complete this section. The results below are expected examples, not verified output from your current terminal. Run the commands on your machine and replace the version and command results with what you actually see.

### 1. Identify the operating system

Command:

```
cat /etc/os-release
```

Example output on a Pop!\_OS system:

```
NAME="Pop!_OS"
ID=pop
VERSION="..."
ID_LIKE="ubuntu debian"
```

The exact version depends on the version installed.

### 2. Identify the current user

Command:

```
whoami
```

Expected output for your usual terminal account:

```
wethinkcode_
```

### 3. Check whether DNF is available

Command:

```
dnf --version
```

On a standard Pop!\_OS installation, DNF is generally not installed by default. You may see an error similar to:

```
dnf: command not found
```

### 4. Check whether RPM is available

Command:

```
rpm --version
```

On a standard Pop!\_OS installation, the RPM tool is generally not installed by default. You may see:

```
rpm: command not found
```

### 5. List installed RPM packages

Command:

```
rpm -qa | head -n 10
```

If RPM is unavailable, this command will fail. That is acceptable for this exercise; do not install RPM or DNF just to complete it.

### Record your results

- Distribution name and version: Pop!\_OS — enter the exact version shown in `/etc/os-release`.
- Is DNF available? Generally, no; it is not installed by default on Pop!\_OS.
- Is RPM available? Generally, no; it is not installed by default on Pop!\_OS.
- What did you learn from the output? Pop!\_OS is based on Ubuntu and uses the Debian package-management ecosystem. It commonly uses APT and DEB packages instead of the DNF and RPM tools associated with Fedora and RHEL-family distributions.
- Were any commands unavailable? DNF and RPM may be unavailable on this system. Confirm this by running the commands.

Additional command to try:

```
apt --version
```

This checks the APT package manager used by Pop!\_OS. You can also run `apt list --installed | head -n 10` to inspect a small sample of installed packages.

## Part D — Choose a distribution for a scenario

1\. A learner wants to explore newer Linux technologies and community-developed software.

Answer: Fedora.

Fedora is a suitable choice because it focuses on innovation and provides access to newer technologies and community-developed software. It is useful for learning about modern Linux features.

Before choosing it, I would investigate its release schedule and check whether the software I want to learn is supported.

2\. A developer wants insight into changes being prepared for a future RHEL minor release.

Answer: CentOS Stream.

CentOS Stream is suitable because it tracks development for upcoming RHEL minor releases. It allows developers to explore and test changes that are being prepared for RHEL.

Before choosing it, I would check whether the version and packages I need are available and whether the environment is appropriate for development or testing.

3\. A business needs a supported enterprise platform and values predictable maintenance.

Answer: Red Hat Enterprise Linux (RHEL).

RHEL is suitable because it is designed for enterprise workloads and offers predictable maintenance, security updates, and commercial support options.

Before choosing it, I would investigate the support lifecycle, subscription costs, application compatibility, and the organisation's support requirements.

## Part E — Reflection

The most important concept I learned from this lesson is the difference between the Linux kernel and a Linux distribution. Before watching the video, I did not fully understand how Fedora, CentOS Stream, and Red Hat Enterprise Linux are related or how they serve different purposes. Understanding Linux distributions will help me as a software engineering student because different development, cloud, and cybersecurity environments may use different distributions, package managers, and system configurations. Knowing these differences will help me install software, troubleshoot errors, manage systems, and choose suitable environments for my projects. My next step is to investigate essential Linux commands, package management, and the differences between APT and DNF.


