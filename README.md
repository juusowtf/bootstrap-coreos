# bootstrap-coreos

Yet another role to bootstrap CoreOS for Ansible provisioning.

## Requirements

None.

## Role Variables

pypy_install_location: (default: /usr/share/pypy)
pypy_version: (default: 5.3.1)

## Dependencies

None.

## Example Playbook

´´´yaml
  - hosts: servers
    roles:
      - jzmch.bootstrap-coreos
´´´

## License

BSD
