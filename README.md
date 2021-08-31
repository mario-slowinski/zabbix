zabbix
======

Ansible role to configure Zabbix Agent.

Requirements
------------

* [ansible.builtin](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/index.html)

Role Variables
--------------

* defaults

  * `Debian.yaml`

    ```yaml
    Debian_pkgs: []       # list of Zabbix repo and agent packages
      - deb: ""           # Debian Zabbix repo package URL
      - name: ""          # zabbix-agent package
    ```

  * `RedHat.yaml`

    ```yaml
    RedHat_pkgs: []       # list of Zabbix repo and agent packages
      - name: ""          # RedHat Zabbix repo package URL
      - name: ""          # zabbix-agent package
    ```

  * `main.yaml`

    ```yaml
    zabbix_options: {}    # dict of Zabbix config key=value pairs
      Server:             # list of values => coma separated in config
        - zabbix-server
        - 10.0.0.1
      ServerActive:
        - zabbix-server
        - 10.0.0.1
      Hostname: ""        # empty value => remove option in config
    ```

* vars

  ```yaml
  zabbix_config: {}     # zabbix file attributes
  ```

Dependencies
------------

* [service](https://github.com/mario-slowinski/service)
  * [software](https://github.com/mario-slowinski/software)

Tags
----

* **zabbix.config** - Configure Zabbix

Examples
--------

* `requirements.yaml`

  ```yaml
  - name: zabbix
    src: https://github.com/mario-slowinski/zabbix
  ```

* `playbook.yaml`

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
