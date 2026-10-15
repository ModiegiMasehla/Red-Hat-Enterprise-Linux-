# Notes: Linux Distributions

**Course:** Red Hat Enterprise Linux Technical Overview (RH024)  
**Topic:** Linux Distributions  
**Date watched:** 15 October 2026

## 1. What is a Linux distribution?

A **Linux distribution (distro)** is an operating system built around the Linux kernel and combined with other software, tools, libraries, package-management utilities, and a way to install and maintain the system.

The Linux kernel is the central foundation of a Linux-based operating system. It helps manage hardware and system resources and provides core services that applications use.

Different distributions can use the same Linux kernel family while making different choices about software, defaults, release schedules, support, and configuration.

## 2. Linux kernel

- The kernel is the central foundation of a Linux system.
- It helps manage CPU time, memory, devices, and other system resources.
- A distribution includes the kernel alongside the tools and software needed to make a usable operating system.
- The kernel is not the same thing as a complete Linux distribution.

**Remember:** Linux kernel + system tools + software + distribution-specific choices make up a usable Linux distribution.

## 3. Open source

The video explains that Red Hat uses and contributes back to open-source software, strengthening the Linux ecosystem.

Open source generally means that source code is available under a licence that permits specified uses, inspection, modification, and redistribution. The exact permissions and obligations depend on the licence.

Benefits can include:
- People can inspect how software works.
- Developers can collaborate on improvements.
- Fixes and improvements can be shared.
- Organisations can build products and services around open-source projects.

Open source does **not** automatically mean that software has no costs, no support options, or no licence obligations.

## 4. The Fedora, CentOS Stream, and RHEL relationship

The course graphic introduces three related distributions:

### Fedora

- A community Linux distribution associated with innovation and newer technologies.
- It often serves as an upstream source for technologies that may later be incorporated into Red Hat Enterprise Linux.
- It is useful for exploring newer Linux software and developments.

### CentOS Stream

- Sits between Fedora and Red Hat Enterprise Linux in the Red Hat development ecosystem.
- Tracks development of the next minor release of RHEL.
- Provides a view into changes being prepared for future RHEL updates.

### Red Hat Enterprise Linux (RHEL)

- An enterprise Linux distribution designed for stability, predictability, and long-term use in business environments.
- Offers a supported platform for enterprise workloads.
- Emphasises a predictable lifecycle and controlled updates.

**Simplified relationship:**

```text
Fedora  →  CentOS Stream  →  Red Hat Enterprise Linux (RHEL)
innovation   preview of the next       enterprise stability,
             RHEL minor release        predictability and support
```

This is a simplified way to understand the relationship, not a claim that every package moves through the three distributions unchanged or in a strictly identical sequence.

## 5. Package management

A **package manager** helps install, update, query, and remove software packages while handling dependencies.

The video identifies RPM-based package management as common to RHEL, CentOS Stream, and Fedora.

Useful terms:

- **Package:** A bundle containing software and metadata needed for installation and management.
- **Dependency:** Another package or component that software needs to work correctly.
- **Repository:** A source from which package-management tools can obtain software packages and metadata.
- **RPM:** The package format and low-level package-management tool used in RPM-based distributions.
- **DNF:** A higher-level package manager commonly used to manage software and dependencies on modern Fedora and RHEL-family systems.

Examples to explore on an appropriate Linux system:

```bash
# Show the operating system information, when available
cat /etc/os-release

# Display the DNF version, if DNF is installed
dnf --version

# Search package metadata for a package (may require repository access)
dnf search PACKAGE_NAME

# Show information about an installed or available package
dnf info PACKAGE_NAME

# List installed RPM packages
rpm -qa
```

Replace `PACKAGE_NAME` with a real package name. Commands may differ by distribution and may require administrator privileges or network access. Do not run installation or removal commands on a production system without understanding their impact.

## 6. How distributions differ

The video notes that Linux distributions share core technologies, including the Linux kernel, databases, and programming languages, but differ in areas such as:

- **Configuration:** Default settings and the way system components are configured.
- **Release schedule:** How often new versions or updates are delivered.
- **Package management:** The package format and tools used to install software.
- **Support model:** Community support, commercial support, or a combination.
- **Intended use:** For example, desktop use, development, servers, or enterprise workloads.
- **Lifecycle:** How long versions receive maintenance and security updates.

These differences matter because instructions for one distribution may not work exactly the same way on another.

## 7. RHEL lifecycle and predictability

The video describes RHEL's lifecycle as being designed for stability and predictability, and mentions a major-version release cadence of approximately every three years.

Treat this as the cadence described in the lesson, rather than a guarantee that every release or support policy will always follow an exact schedule. Check current official Red Hat lifecycle documentation when planning upgrades or support.

Why lifecycle matters:
- Organisations need to plan upgrades and testing.
- Stable environments can reduce unexpected change.
- Security updates and maintenance policies affect operational risk.
- Applications should be tested against the target operating system and supported software versions.

## 8. Extra notes: choosing a distribution

There is no single best distribution for every situation. Consider:

1. **Purpose:** Is it for learning, a personal desktop, a server, or an enterprise workload?
2. **Support:** Is community help enough, or is vendor support required?
3. **Stability vs. new features:** Does the workload need newer software or predictable change?
4. **Lifecycle:** How long will the version receive updates?
5. **Compatibility:** Does the required software support this distribution?
6. **Administration:** Which package manager, tools, and configuration conventions does it use?

For a beginner, a virtual machine is a useful place to explore a distribution without changing the main operating system.

## 9. Key vocabulary

| Term | Meaning |
|---|---|
| Linux kernel | Core part of the operating system that manages hardware and system resources |
| Distribution / distro | A complete operating system assembled around the Linux kernel with tools and software |
| Open source | Software distributed under a licence that allows specified access and uses of its source code |
| Package | Software bundle managed by package tools |
| Package manager | Tool for installing, updating, querying, and removing packages |
| Repository | Source of packages and package metadata |
| RPM | Package format and package-management tool used in RPM-based distributions |
| DNF | Higher-level package manager used by modern Fedora and RHEL-family systems |
| Lifecycle | Period during which a product or release receives defined maintenance and support |
| Upstream | A project or development source from which changes or software may flow to another project |

## 10. Quick revision

- The Linux kernel is the foundation of a Linux system, but it is not a complete distribution by itself.
- A Linux distribution combines the kernel with tools, software, and distribution-specific choices.
- Fedora, CentOS Stream, and RHEL are related but serve different roles.
- RHEL focuses on enterprise stability, predictability, and support.
- RPM and DNF are important terms in the Red Hat ecosystem.
- Distributions can differ in configuration, release schedules, package management, support, and lifecycle.
- Open source encourages collaboration, but licences still matter.

## Sources and follow-up reading

- [RH024: Red Hat Enterprise Linux Technical Overview](https://www.redhat.com/en/services/training/rh024-red-hat-linux-technical-overview)
- [Red Hat Documentation](https://docs.redhat.com/)
- [Red Hat Enterprise Linux Life Cycle](https://access.redhat.com/support/policy/updates/errata)
- [Fedora Project](https://fedoraproject.org/)
- [CentOS Stream](https://www.centos.org/centos-stream/)
