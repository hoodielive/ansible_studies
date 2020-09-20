# Loops 

* May be performed using the loop or with _<lookup> keywords.
* Standard Loop usage:
    * Iterate over a simple list.
    * Iterate over a list of hashes.
    * Iterate over a dictionary.
* When statements are processed separately for each item in a loop.

## Example:
```yaml
---
- hosts: webservers
  become: yes
  tasks:
    - name: create a list of users.
      user:
        name: " {{ item }}"
        state: present
        groups: wheel 
      loop: 
        - violet
        - graham
        - bethany
```
