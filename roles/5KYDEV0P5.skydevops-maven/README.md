# Ansible Role: MAVEN

[![License](https://img.shields.io/badge/License-Apache%202.0-brightgreen.svg)](https://opensource.org/licenses/Apache-2.0)
[![Build Status](https://travis-ci.org/5KYDEV0P5/skydevops-maven.svg?branch=master)](https://travis-ci.org/5KYDEV0P5/skydevops-maven)
[![Average time to resolve an issue](http://isitmaintained.com/badge/resolution/5KYDEV0P5/skydevops-maven.svg)](http://isitmaintained.com/project/5KYDEV0P5/skydevops-maven "Average time to resolve an issue")
[![Percentage of issues still open](http://isitmaintained.com/badge/open/5KYDEV0P5/skydevops-maven.svg)](http://isitmaintained.com/project/5KYDEV0P5/skydevops-maven "Percentage of issues still open")

## Description

Install and configures Apache Maven on RedHat/CentOS and Debian/Ubuntu.

## Requirements
- Ansible >=2.4
- EPEL Repo for RedHat/Centos, which can be installed automatically using the [common](https://github.com/5KYDEV0P5/common) ansible role.
- Java which can be installed using the [skydevops-java](https://github.com/5KYDEV0P5/skydevops-java)



## Role Variables
All the variable that can be overridden are stored in [vars/main.yml](vars/main.yml) or [defaults/main.yml](defaults/main.yml) file as shown in the table below:

| Name                	| Default Value                                                 	| Description                                                          	|
|---------------------	|---------------------------------------------------------------	|----------------------------------------------------------------------	|
| `main_rel`          	| : 3                                                           	| Major version of Maven                                                |
| `min_rel`           	| : 5                                                           	| Minor version of Maven                                                |
| `patch_rel`         	| : 3                                                           	| Patch version of Maven                                                |
| `maven_version`.      | : {{main_rel}}.{{min_rel}}.{{patch_rel}}                        | Maven Version that will be installed                                  |
| `maven_install_dir` 	| : /apps                                                       	| Install directory for maven                                          	|
| `maven_src_tar`     	| : apache-maven-{{maven_version}}-bin.zip 	                      | Apache Maven Archive                                                 	|
| `maven_home`        	| : apache-maven-{{maven_version}}                              	| M2_HOME ENV variable                                                 	|
| `maven_shared_home` 	| : /usr/shared/maven                                           	| Symlink to the installed Maven                                       	|
| `maven_repo_dir`    	| : /data/maven/repo                                            	| Maven repo directory                                                 	|
| `maven_profile_sh`  	| : /etc/profile.d/maven.sh                                     	| Jinja2 Template,  contains the info <br>to source the ENV variables 	|

## Dependencies

- Ansible [common](https://github.com/5KYDEV0P5/common) Role, to install required directory structure and packages.
- Ansible [java](https://github.com/5KYDEV0P5/skydevops-java) Role, which installs and configures java from Oracle.

## Example Playbook and defaults

### Playbook Default file locations based on playbook execution 

```sh
# The defaults PATHS where Ansible looks for the files
When executing the playbook from the following path:
$ cd /home/${USER}/
$ ansible-playbook ${playbook_dir}/playbook.yml

   /home/${USER}/roles/${ansible_role}/files/apache-maven-3.5.3-bin.zip   
   /home/${USER}/roles/${ansible_role}/apache-maven-3.5.3-bin.zip   
   /home/${USER}/roles/${ansible_role}/tasks/files/apache-maven-3.5.3-bin.zip   
   /home/${USER}/roles/${ansible_role}/tasks/apache-maven-3.5.3-bin.zip   
   /home/${USER}/${playbook_dir}/files/apache-maven-3.5.3-bin.zip   
   /home/${USER}/${playbook_dir}/apache-maven-3.5.3-bin.zip
```

### Use the following to run playbook

```yaml
- hosts: all
  become: yes
  gather_facts: yes
  roles:
    - role: 5KYDEV0P5.common

- hosts: testservers
  become: yes
  gather_facts: yes
  roles:
    - role: 5KYDEV0P5.skydevops-java
    - role: 5KYDEV0P5.skydevops-maven
```

## License

- Licensed under the Apache License V2.0. 
- See the [LICENSE file](LICENSE) for details.

## Author Information

- You can find me on Twitter: [@skydevops](https://twitter.com/skydevops)
- You can find me on Facebook: [@skydevops](https://www.facebook.com/skydevops)

## Contributors

- Shashi Yebbare ([@skydevops](https://twitter.com/skydevops))