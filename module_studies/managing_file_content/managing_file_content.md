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

