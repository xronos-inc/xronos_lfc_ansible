# Provision a host with Lingua Franca role

Provision a Lingua Franca development system with all supported target languages.

## Features

- lfc compiler (user install)
- openjre 17
- LF C RTI
- gcc, g++ and cmake
- python3
- rust (user install)

## OS support

- Ubuntu 22.04
- Ubuntu 24.04

Platforms supported:

- linux/amd64
- linux/arm64
- linux/arm/v7 (armhf)
- linux/riscv64

## Prerequisites

- Ansible 2.15

## Example playbook

```yaml
- name: Install Lingua Franca development tools
  hosts: myhosts
  gather_facts: true
  roles:
    - name: xronos_lfc_ansible
      role: xronos_lfc_ansible
```

## Variables

### Features

- `lfc_install_cmake`: install cmake. Defaults to `false`.
- `lfc_install_rti`: install RTI. Defaults to `true`.

### Versions

- `lfc_version`: version of LFC to install. Defaults to empty (latest).
- `lfc_cmake_version`: version of cmake to install. Defaults to empty (latest).
- `lfc_rti_commit`: git branch, tag or commit hash of the RTI build. Default is `main`.
- `lfc_openjdk_17_jre_version`: version of openjdk-17-jre to install. Default is empty (latest).
