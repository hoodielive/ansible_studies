# Understanding Templates 

The template module processes a template and pushes it out to a remote server.
  * Templates are files that contain both static and dynamic value, through the use of variables.
  * Ansible processes templates using jinja2.
  * Templates are designated with the .j2 extension.
  * Templates are often used for configuration file management.
  * Templates have access to the same variables as the plays that call them. 

```yaml
- name: show template options
  template:
    src: /path/to/template.j2
    dest: /path/to/dest
    owner: owner_name
    group: group_name
    mode: file_permissions
    validate: validation_command %s
    backup: no|yes
```
