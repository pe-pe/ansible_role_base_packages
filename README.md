Base Packages
=========

Ansible role that installs provided list of base packages for which does not make sense to create separate roles.

Requirements
------------

none

Role Variables
--------------

List of packages to be installed:
```
base_packages:
  - package_name1
  - package_name2
```

Dependencies
------------

none

Example Playbook
----------------

Example how to use the role:

```
- hosts: all
  roles:
    - role: pe_pe.base_packages
      base_packages:
        - unzip
        - curl
```

License
-------

MIT

Author Information
------------------

PePe
