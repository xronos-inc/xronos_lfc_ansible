# Provision a host with Lingua Franca role

Provision a Lingua Franca development system with all supported target languages.

Features

- lfc compiler (user install)
- Oracle Java 17 or openjdk
- LF C RTI
- gcc, g++ and cmake
- python3
- rust (user install)

Platforms supported

- linux/amd64
- linux/arm64
- linux/arm/v7 (armhf)
- linux/riscv64

## Prerequisites

- Ansible 2.15
- Debian-based host accessible via SSH with apt-get and sudo available

## Example playbook

```yaml
---
- name: Install Lingua Franca development tools
  hosts: myhosts
  gather_facts: true
  roles:
    - name: xronos_lfc_ansible
      role: xronos_lfc_ansible
```

## Variables

Defaults that may be overridden:

```yaml
# install rust compiler
lfc_install_rust: true

# install the latest RTI
lfc_install_rti: true

# use oracle JDK instead of openjdk (when possible)
lfc_jdk_use_oracle: true
```
