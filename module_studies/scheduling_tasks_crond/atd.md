# Schedule Tasks with at:

The at module - schedules the execution of a command or script with the at command.

```yaml
- name: show options of the at module
  at:
    command: command_to_run
    script_file: /path/to/script.sh
    count: count of units in the future to execute the command or script
    unit: minutes|hours|days|weeks 
    state: present|absent
```
