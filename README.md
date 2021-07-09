zabbix
======

Ansible role to configure Zabbix Agent.

Requirements
------------

* [ansible.builtin](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/index.html)

Role Variables
--------------

* defaults

  ```yaml
  zabbix_pkgs: []       # list of Zabbix repo and agent package
    - deb: ""           # Debian Zabbix repo package
    - name: ""          # RedHat Zabbix repo package

  zabbix_options: {}    # dict of Zabbix config key=value pairs
  ```

* vars

  ```yaml
  zabbix_config: {}     # sshd_config file attributes
  ```

Dependencies
------------

* [service](https://github.com/mario-slowinski/service)
  * [software](https://github.com/mario-slowinski/software)

Tags
----

* zabbix.config

Example Playbook
----------------

* `requirements.yml`

  ```yaml
  - name: zabbix
    src: https://github.com/mario-slowinski/zabbix
  ```

* playbook usage

  ```yaml
  - hosts: servers
    gather_facts: true  # to get ansible_os_family
    roles:
      - role: zabbix
  ```

License
-------

[GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.html)

Author Information
------------------

[mario.slowinski@gmail.com](mailto:mario.slowinski@gmail.com)
