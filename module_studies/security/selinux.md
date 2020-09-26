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
