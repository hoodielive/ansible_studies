# Create an Archive

The archive module creates compressed archive on one or more files or directories.

```yaml
- name: show options for archive module
  archive: 
    path:
      - /path/to/file
      - /path/to/file
      - /path/to/dir
      - /globbed/path/using/*
    exclude_path:
      - /file/to/exclude
      - /dir/to/exclude
      - /glob/to/exclude/ex*
    format: gz|bz2|tar|xz|zip
    dest: /name/of/archive.tgz
```
