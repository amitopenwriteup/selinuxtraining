
````markdown
# Security Labs – SELinux, nftables, and Identity Management

This repository contains hands-on lab exercises and supporting materials for working with **Linux security technologies**, including:

- **SELinux (Security-Enhanced Linux)**
- **nftables (Next Generation Netfilter)**
- **Identity Management (IdM / FreeIPA / Kerberos)**

The labs are designed for learners and professionals who want practical exposure to securing Linux systems.

---

## 📂 Repository Structure

### 🔒 SELinux Labs
- `Lab 1 selinux.txt` – Introduction and basics
- `Lab 3 selinux Port.txt` – Working with SELinux ports
- `Lab 5 selinux.txt` – Advanced SELinux scenarios
- `Lab 6 permssive mode.txt` – SELinux permissive mode
- `Lab 7 selinux.txt` – Policy testing
- `lab 2 Selinux policy.txt` – Creating custom SELinux policies
- `lab 4 selinux solution.txt` – Policy troubleshooting
- `selinux db-lab.md` – SELinux with databases
- `selinux.pptx` – SELinux presentation

### 🌐 nftables Labs
- `Lab 2 nft table chain.txt` – Creating tables and chains
- `Lab 3 block traffic ip.txt` – Blocking traffic by IP
- `Lab 4 nftables counter.txt` – Counters and statistics
- `Lab 5 Basic Packet Filtering.txt` – Basic packet filtering
- `Lab 6 nftables output.txt` – Rule output examples
- `Lab 7 nftables.txt` – Advanced rules
- `Lab 8 nft NAT.txt` – NAT configuration
- `Lab 9 nft project.txt` – Capstone project
- `Lab1 nftables.txt` – Getting started
- `lab 1 nft cmd.txt` – Command cheatsheet
- `lab7 nftables.txt` – Additional practice
- `nftables-ruleoutput.docx` – Rule output documentation
- `nftables.pptx` – nftables presentation

### 👤 Identity Management & Kerberos
- `lab 1 idm setup.txt` – FreeIPA setup
- `lab 2 idm cli.txt` – Managing IdM with CLI
- `lab 5 ipa ui.txt` – IdM Web UI usage
- `lab 6 idm.txt` – Advanced IdM labs
- `lab4 idarules.txt` – Rules and access control
- `kerbrose-setup.txt` – Kerberos setup guide
- `idm.pptx` – IdM presentation

### 📝 Mixed/Other
- `Lab4 policy creation.txt` – Policy creation walkthrough
- `Lab selinux new.md` – Combined SELinux notes

---

## 🚀 How to Use

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
````

2. Follow each lab file in order for a guided learning experience.
3. Refer to `.pptx` presentations for conceptual understanding.
4. Use `.docx` and `.md` files for detailed outputs and explanations.

---

## 📘 Learning Objectives

By completing these labs, you will learn to:

* Configure and enforce **SELinux policies**.
* Create and manage **nftables firewall rules** for filtering, NAT, and monitoring.
* Set up and manage **Identity Management (FreeIPA)** with **Kerberos** integration.
* Troubleshoot and secure Linux environments effectively.

---

## 🛠 Requirements

* Linux system (CentOS / RHEL recommended)
* `nftables` installed and enabled
* `policycoreutils` and `selinux` tools
* FreeIPA / IdM packages (if working on IdM labs)
* Root or sudo privileges

---

## 📄 License

This repository is for **educational purposes**. Please review and adapt the labs carefully before using them in production environments.

---

## ✨ Author

**Amit Maheshwari**
📧 [amit@openwriteup.com](mailto:amit@openwriteup.com)

```
