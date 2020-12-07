Base Packages
=========

Ansible role that installs provided list of base packages for which does not make sense to create separate roles. Packages are installed according to user specification - from native operating system package manager or pip  (package installer for Python).
When pip packages are requested to be installed - the role will install native operating system package to provide pip command and additional dependencies in case executed on hosts where Ansible is leveraging on Python 2.x (ie. role will install `epel-release` on EL7).

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

Following variable specifies name of native operating system package delivering pip, which is installed whenever `base_pip_packages` is not empty. It's set by default to:
- `python3-pip` for distributions where Ansible leverages on Python 3.x
- `python-pip` for other distributions


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
