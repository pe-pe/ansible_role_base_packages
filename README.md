Base Packages
=========

Ansible role that installs provided list of base packages for which does not make sense to create separate roles. Packages are installed according to user specification - from native operating system package manager or pip  (package installer for Python).

Requirements
------------

None

Role Variables
--------------

Lists of packages to be installed (using native package manager and pip):
```yaml
base_packages:
  - package_name1
  - package_name2
  ...

base_pip_packages:
  - pip_package_name1
  - pip_package_name2
  ...
```
By default both lists of packages are empty.

Following variable specifies name of native operating system package delivering pip, which is installed whenever any base_pip_packages is not empty. It's set to `python3-pip` by default:
```yaml
pip_package: python3-pip
```

Dependencies
------------

None

Example Playbook
----------------

Example how to use the role:

```yaml
- hosts: all
  roles:
    - role: pe_pe.base_packages
      base_packages:
        - unzip
        - curl
      base_pip_packages:
        - molecule
```

License
-------

MIT

Author Information
------------------

PePe
