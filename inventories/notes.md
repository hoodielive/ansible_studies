# Understanding Core Components of Ansible Inventories 
* Default location of hosts file: '/etc/ansible/hosts'.
* The default location of the hosts file can be set in: '/etc/ansible/ansible.cfg'.
* It can be specified using the '-i' option when running ansible.
* The file can contain individual hosts, groups of hosts and host and group level variables.
* It can also contain variables that determine how you connect 'to' a host. 

## Two formats for inventory file. 
1. INI-based file format:
[webservers]
web01.example.com
web02.example.com

[dbservers]
db[01:04].example.com (db01-db04)

2. YAML-based file format: 
```
all:
  hosts:
    mail.example.com
  children:
    webservers:
      hosts:
        web01.example.com
        web02.example.com
    dbservers:
      hosts:
        db[01:04].example.com
```
