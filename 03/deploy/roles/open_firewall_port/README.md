open_firewall_port
==================

This role allows permanently opening a chosen TCP port in firewall.

Parameters:
- port - TCP port

Invocation:
- in playbook
```
- hosts: ...
  roles:
    - { role: open_firewall_port, port: 1234 }
```
- in other roles
```
- include_role:
    name: open_firewall_port
  become: yes
  vars:
    port: 1234
```
