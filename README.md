# bootstrap-coreos

Yet another role to bootstrap CoreOS for Ansible provisioning.

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
    roles:
      - jzmch.bootstrap-coreos
```

## License

BSD
