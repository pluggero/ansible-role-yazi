# Ansible Role: Yazi

[![CI](https://github.com/pluggero/ansible-role-yazi/actions/workflows/ci.yml/badge.svg)](https://github.com/pluggero/ansible-role-yazi/actions/workflows/ci.yml) [![Ansible Galaxy downloads](https://img.shields.io/ansible/role/d/pluggero/yazi?label=Galaxy%20downloads&logo=ansible&color=%23096598)](https://galaxy.ansible.com/ui/standalone/roles/pluggero/yazi)

An Ansible Role that installs yazi on various Linux distributions.

## Requirements

Requires a compatible Rust toolchain to build Yazi from source; Recommended role: `pluggero.rustup`.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
yazi_version: "x.x.x"
```

- The version of yazi to install.

```yaml
yazi_install_method: "dynamic"
```

The method used to install yazi can be defined in the variable `yazi_install_method`.
The following methods are available:

- `source`: Installs yazi from source
- `package`: Installs yazi from the package manager of the distribution
  - **NOTE**: This method installs the latest version available in the package manager and not the version defined in `yazi_version`.
  - In that distributions where the yazi is not available in the package manager, it will be installed from the source.
- `dynamic`: Installs yazi from package manager if available in the correct version, otherwise installs from source

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  roles:
    - pluggero.yazi
```

## License

MIT / BSD

## Author Information

This role was created in 2025 by Robin Plugge.
