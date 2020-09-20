# YUM/DNF Module studies 
The dnf/yum module - Use the yum package manager to install, upgrade, downgrade, remove and list packages and groups.

### Example: 
```yaml
- name: install a package
  dnf:
    name: package_name
    state: latest 
- name: install a list of packages
  dnf:
    name: 
      - package_name
      - package_name
    state: latest 
- name: install rpm from a remote repo
  dnf:
    name: http://website.com/path/to/rpm
    state: present
- name: install rpm from a local file
  dnf:
    name: /path/to/rpm
    state: present
- name: remove a package
  dnf:
    name: package_name
    state: absent
```
