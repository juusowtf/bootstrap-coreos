# bootstrap-coreos

Yet another role to bootstrap CoreOS for Ansible provisioning. As you might know, Ansible needs a Python interpreter on the server for most of the Ansible modules to work. There isn't one in CoreOS by default. So we're going to install [PyPy](http://pypy.org/index.html) on it.

This role is heavily influenced by the good work done in defunctzombie's [ansible-coreos-bootstrap](https://github.com/defunctzombie/ansible-coreos-bootstrap) role. Only problem with it at the moment is that it's not very configurable. Also the syntax used in that role is a bit outdated.

## Requirements

None.

## Role Variables
```yaml
# Variables and their default values as set in defaults/main.yml
pypy_install_location: /usr/share/pypy
pypy_version: 5.3.1
```
## Dependencies

None.

## Example Playbook

```yaml
  - hosts: servers
    gather_facts: no
    roles:
      - jzmch.bootstrap-coreos
```

## License

BSD
