# Ansible Role: common

[![License](https://img.shields.io/badge/License-Apache%202.0-brightgreen.svg)](https://opensource.org/licenses/Apache-2.0)
[![GitHub release](https://img.shields.io/github/release/5KYDEV0P5/common.svg)](https://github.com/5KYDEV0P5/common/releases)
[![Website](https://img.shields.io/website-up-down-green-red/http/skydevops.co.in.svg?label=skydevops)]()
[![Build Status](https://travis-ci.org/5KYDEV0P5/common.svg?branch=master)](https://travis-ci.org/5KYDEV0P5/common)
<!-- [![Ansible Role](https://img.shields.io/badge/ansible%20role-skydevops.common-brightgreen.svg)](https://skydevops.co.in) -->
<!-- [![tag](https://img.shields.io/github/tag/5KYDEV0P5/common.svg)](https://github.com/5KYDEV0P5/common/tags) -->
<!-- [![Github All Releases](https://img.shields.io/github/downloads/5KYDEV0P5/common/total.svg)]( ) -->
<!-- [![GitHub issues](https://img.shields.io/github/issues/5KYDEV0P5/common.svg)](https://github.com/5KYDEV0P5/common/issues) -->
<!-- [![release](http://github.com/github/5KYDEV0P5/common/release.svg?style=flat)](https://github.com/5KYDEV0P5/common/releases/latest) -->
<!-- https://img.shields.io/github/commits-since/sky-kshatriyan/common/latest.svg -->


## Description

Install and configures directory structure and required packages on RedHat/CentOS and Debian/Ubuntu

## Requirements

- Ansible >=2.3
- EPEL Repo for RedHat/CentOS


## Role Variables

All variables which can be overridden are stored in [vars/main.yml](vars/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `data_dir` | /data | Creates a data directory |
| `apps_dir` | /apps | Creates a application installation directory |
| `apt_libraries_utilities` | ntp, lsof, wget,  zip,<br> python-software-properties,<br> unzip,<br> build-essentials | Install the list of packages needed for Debian/Ubuntu family VM's, add them as named variables |
| `yum_libraries_utilities` | ntp, lsof, wget, dkms,<br> kernel-devel,<br> kernel-tools,<br> zip,<br> unzip,<br> iptables-services,<br> policycoreutils-python,<br>  build-essentials | Install the list of packages needed for RedHat/CentOS family VM's, add them as named variables |


## Example 

### Playbook

Just install Libraries and utilities 

```yaml
- hosts: all
  become: yes
  gather_facts: yes
  roles:
    - role: common
```

## License


Licensed under the Apache License V2.0. See the [LICENSE file](LICENSE) for details.

## Author Information

You can find me on Twitter: [@skydevops](https://twitter.com/skydevops)

## Contributors

- Shashi Yebbare ([@skydevops](https://twitter.com/skydevops))