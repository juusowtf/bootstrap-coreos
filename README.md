[![Build Status](https://travis-ci.org/jzmch/bootstrap-coreos.svg?branch=master)](https://travis-ci.org/jzmch/bootstrap-coreos)
[![Ansible Role](https://img.shields.io/badge/role-jzmch.bootstrap--coreos-blue.svg)](https://galaxy.ansible.com/jzmch/bootstrap-coreos/)
# bootstrap-coreos

Yet another role to bootstrap CoreOS for Ansible provisioning. As you might know, Ansible needs a Python interpreter on the server for most of the Ansible modules to work. There isn't one in CoreOS by default. So we're going to install [PyPy](http://pypy.org/index.html) on it.

This role is heavily influenced by the good work done in defunctzombie's [ansible-coreos-bootstrap](https://github.com/defunctzombie/ansible-coreos-bootstrap) role. Only problem with it at the moment is that it's not very configurable. Also the syntax used in that role is a bit outdated.

## Requirements

None.

## Dependencies

None.

## Installation

### "The Default Ansible Way"

```shell
ansible-galaxy install jzmch.bootstrap-coreos
```

Depending on your setup, this command installs the role to `/etc/ansible/roles` directory. You might run into errors installing there, because it is owned by root. So make sure it is owned by your user.

```shell
sudo chown <user>:<group> /etc/ansible/roles
```

### Specify roles path in a local `ansible.cfg`

There are times when you want to install roles to the working directory where your other Ansible scripts are. You can do that by creating a local `ansible.cfg` file into the root of your working directory (the place where you run Ansible). The file should contain at least these lines:

```yaml
[defaults]
roles_path = roles/
```

Now when you run `ansible-galaxy install jzmch.bootstrap-coreos`, it will be installed to `./roles/` directory.

#### Using --roles-path=[path]

You can also specify the roles path directly in the install command. But you still need to have the roles path setup in the Ansible configuration file in order for them to work.

## Role Variables
```yaml
# Variables and their default values as set in defaults/main.yml
pypy_dir: /home/core/lib/pypy
pypy_version: 5.3.1
ansible_python_interpreter: /home/core/bin/python
```
You should set the values for these in your inventory/group_vars/host_vars/playbook etc.

## Example Playbook

```yaml
  - hosts: servers
    gather_facts: no
    roles:
      - jzmch.bootstrap-coreos
```

## License

BSD
