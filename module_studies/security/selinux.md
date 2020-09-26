# SELINUX and SEBOOLEAN Modules:

The selinux module changes the policy and state of SELinux.
```yaml
- name: show options for seliux module 
  selinux:
    configfile: /etc/selinux/config
    policy: targeted
    state: enforcing|permissive|disabled
```

The seboolean module toggles SELinux booleans.
```yaml
- name: show options for the sebooleans module
  seboolean:
    name: boolean_name
    state: no|yes
    persistent: no|yes
```

The sefcontext module manages selinux file context mapping definitions.
```yaml
- name: show options for the sefcontext module
  sefcontext:
    ftype: a|d|etc.
    reload: yes|no
    target: '/path/to/dir(/.*)?'
    setype: selinux_type
    state: present|absent
- name: apply new selinux context to the filesystem
  command: restorecon -irv /path/to/dir
```
