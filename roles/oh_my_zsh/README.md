Fork of original
================
https://github.com/gantsign/ansible-role-oh-my-zsh
https://galaxy.ansible.com/gantsign/oh-my-zsh

Ansible Role: Oh My Zsh
=======================

Role to download, install and configure [Oh-My-Zsh](http://ohmyz.sh/).

Requirements
------------

* Ansible >= 2.8

* Linux Distribution

    * Debian Family

        * Debian

            * Buster (10)

        * Ubuntu

            * Focal Fossa (20.04)

    * Note: other versions are likely to work but have not been tested.

Role Variables
--------------

The following variables will change the behavior of this role (default values
are shown below):

```yaml
# Default theme
oh_my_zsh__theme: robbyrussell

# Default plugins
oh_my_zsh__plugins:
  - git

# Wether to install by default for all specified users.
# May be overridden by `oh_my_zsh: install:` under each user.
oh_my_zsh__install: yes

# User configuration
# Important: oh-my-zsh is installed per user so you need to specify the users to install it for.
oh_my_zsh__users:
  - name: example1
    oh_my_zsh:
      theme: robbyrussell
      plugins:
        - git
  - name: example2
    oh_my_zsh:
      theme: robbyrussell
      plugins:
        - git
        - mvn
  - name: example3
    oh_my_zsh:
      install: no
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: kwusen.kwusen.oh_my_zsh
      oh_my_zsh__users:
        - name: example
```

Development & Testing
---------------------

This project uses [Molecule](http://molecule.readthedocs.io/) to aid in the
development and testing; the role is unit tested using
[Testinfra](http://testinfra.readthedocs.io/) and
[pytest](http://docs.pytest.org/).

To develop or test you'll need to have installed the following:

* Linux (e.g. [Ubuntu](http://www.ubuntu.com/))
* [Docker](https://www.docker.com/)
* [Python](https://www.python.org/) (including python-pip)
* [Ansible](https://www.ansible.com/)
* [Molecule](http://molecule.readthedocs.io/)

License
-------

MIT

Author Information
------------------

John Freeman

GantSign Ltd.
Company No. 06109112 (registered in England)
