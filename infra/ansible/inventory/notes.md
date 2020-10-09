# Ansible Inventory 

- An inventory is a list of hosts that Ansible manages.
- Multiple inventory files may be specified using a directory.
- Takes ini or yaml format.

### Locations 
Default: '/etc/ansible/hosts'

Specified by CLI: 'ansible -i <filename>' (used over default).

Change default location: '/etc/ansible/ansible.cfg'.

### Inventory Variables Best Practices 
1. Variables should be stored in YAML files located relative to the inventory file.
2. Host and group variables should be sorted in host_vars and group_vars directories respectively (directories must be created).
3. Variable files should be named after the host or group for which they contain variables (files may end in .yml or yaml).

### INI Example 
```
node1.rhce.lab ansible_port=5556

[webservers]
node1.rhce.lab
node2.rhce.lab 

[webvservers:vars]
http_port=8080

[dbservers]
db[01:99].rhce.lab
```

### YAML Example 
```
---
all:
  hosts:
    node1.rhce.lab
      ansible_port: 5556
      ansible_host: 10.0.2.4
  children:
    webservers: 
      hosts:
        node1.rhce.lab
        node2.rhce.lab
      vars:
        http_port: 8080
    dbservers:
      hosts:
        db[01:99].rhce.lab
```
