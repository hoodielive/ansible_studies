# Managing File Content 
### File 
The file module - manages file and file properties.
```yaml
- name: create a file
  file:
    path: /path/to/file
    state: touch 
```

### Copy 
The copy module - copy files to remote locations.
```yaml
- name: add content to specific file
  copy:
    content: file_content
    dest: /path/to/file
```

### lineinfile
The lineinfile module - manage lines in text lines.

```yaml
- name: replace a line
  lineinfile:
    path: /path/to/file
    regexp: 'regular_expression'
    line: line to insert/replace in the file
```
### Create files and Replace Strings
The replace module - replace all instances of a particular string within a file. 

```yaml
- name: replace strings within a file
  replace:
    path: /path/to/file
    regexp: regular_expression
    line: 'string that replaces what regexp matches'
```

### The Template module
The template module - Template a file out to a remote server.

```yaml
- name: show template options
  template:
    src: /path/to/template.j2
    dest: /path/to/dest
    owner: owner_name
    group: group_name
    mode: file_permissions.
```

