# User and Group Management

The user module manages user accounts and user attributes.
```yaml
- name: show options for user module
  user: 
    name: user_name
    shell: /bin/bash|/bin/zsh|etc.
    home: /path/to/home/dir
    comment: user_description
    uid: set the uid of the user
    group: set the user's primary group
    groups: list of groups to add the user to
    append: no|yes
    state: present|absent
```

### Manage groups 

The group module adds and removes groups.
```yaml
- name: show options for the group module
  group:
    name: group_name
    gid: set the gid for the group
    system: yes|no
    state: present|absent
```
