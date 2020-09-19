# Use Variables to Retrieve the Results of Running a Command
* Use the register keyword to store the results of running a command as a variable.
* Variables can be referenced by other tasks in the playbook.
* Registered variables are only valid on the host for the current playbook run. 
* Return values differ from module to module.

### Use 'register' in a playbook.
```yaml
---
- hosts: hostname
  tasks:
    - name: Create a file.
      file:
        path: /tmp/testFile
        state: touch
      register: variable
    - name: Display debug message.
      debug: msg="Register output is {{ variable }}"
```
