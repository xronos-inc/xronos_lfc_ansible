# Provision a host with Lingua Franca role

Provision a Lingua Franca development system with all supported target languages.

Features

- lfc compiler (user install)
- lingo package manager (user install)
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

## Install Ansible prerequisites

```shell
ansible-galaxy install -r roles/requirements.yml
```

## Example playbook

```yaml
---
- name: Install LF development tools
  hosts: myhosts
  gather_facts: true
  roles:
    - name: lfc_ansible
      role: lfc_ansible
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

# install lingo (requires rust)
lfc_install_lingo: true
```
