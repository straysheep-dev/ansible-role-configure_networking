configure_networking
=========

![molecule workflow](https://github.com/straysheep-dev/ansible-role-configure_networking/actions/workflows/molecule.yml/badge.svg) ![ansible-lint workflow](https://github.com/straysheep-dev/ansible-role-configure_networking/actions/workflows/ansible-lint.yml/badge.svg)

Manage the files, services, and settings of common network components.

> [!NOTE]
> 1. To initialize submodules in this template, do: `git submodule update --init --recursive`
> 2. Replace all instances of `role_name` with the actual `role_name`, **EXCEPT FOR `role_name_check: 1` in `molecule.yml`**
> 3. Replace all instances of `ansible-role-template` with `ansible-role-<role_name>`
> 4. To update submodules, do: `git submodule update --remote --recursive`, see [straysheep.dev/blog/resources/#git](https://straysheep.dev/blog/2019/07/15/-resources/#git)

> [!IMPORTANT]
> **Git Submodules & CI**: The dockerfiles for molecule tests are maintained in a [monorepo](https://github.com/straysheep-dev/docker-configs) as submodules for maintainability / repeatability across all roles. Because of this, the CI workflow requires `actions/checkout` to have `submodules: 'recursive'`.

Requirements
------------

**OS**

For now, only Debian and Ubuntu are supported in molecule testing. This role defaults to using netplan to configure networkd, though you can change the `network_renderer` under [defaults/main.yml](./defaults/main.yml) to be `NetworkManager`. Over time support will be expanded.

Role Variables
--------------

All modifiable variables are under [defaults/main.yml](./defaults/main.yml).

- `hostname_string: "devops"`: Set the hostname
- `network_renderer: "networkd"`: Use 'networkd' for servers, and 'NetworkManager' for desktops

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yml
- name: "Default Playbook"
  hosts: all
    #some_group
  vars:
    hostname_string: "ubuntu-server"
    network_renderer: "networkd"
  roles:
    - role: straysheep_dev.configure_networking
```


License
-------

[MIT](./LICENSE)

Author Information
------------------

[straysheep-dev/ansible-configs](https://github.com/straysheep-dev/ansible-configs)
