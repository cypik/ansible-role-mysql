<p align="center"> <img src="https://user-images.githubusercontent.com/50652676/62451340-ba925480-b78b-11e9-99f0-13a8a9cc0afa.png" width="100" height="100"></p>
<!-- ThisREADME file is for the MySQL role using Ansible -->

<h1 align="center">
    Ansible Role Mysql
</h1>

This Ansible role is designed to manage MySQL databases and users on Ubuntu 22.04.

## Table of Contents
- [Example Playbook](#Example Playbook)
- [Role Variables](#Role Variables)
- [License](#license)


## Example Playbook

**IMPORTANT:** Since the `master` branch used in `source` varies based on new modifications, we suggest that you use the release versions [here](https://github.com/cypik/ansible-role-docker-jenkins/releases).


```yaml
- hosts: localhost
  remote_user: root
  become: true
  roles:
    - cypik.ansible_role_mysql
```

## Role Variables

You can customize the role behavior by modifying the following variables:
- `mysql_root_password`: The root password for MySQL.
- `mysql_databases`: A list of databases to create.
- `mysql_users`: A list of users to create.
- `mysql_user_host`: A list of user_host to create.

Example of variables in `defaults/main.yml`:

```yaml


mysql_databases:
  - { database: "1db8" }
  - { database: "2db2" }
  - { database: "3db4" }
    

mysql_users:
  - { user: "1user", password: "password5", database: "1db8" }
  - { user: "2user", password: "password6", database: "2db2" }
  - { user: "3user", password: "password7", database: "3db4" } 
```
## License
This project is licensed under the MIT License - see the [LICENSE](https://github.com/cypik/ansible-role-mysql/blob/master/LICENSE) file for details.


## Installation

```console
  $ ansible-galaxy install cypik.ansible_role_mysql
```