# Configure Managed Nodes

* Create and distribute SSH keys to Managed nodes and configure privilege escalation.
1. Generate SSH keys: 'ssh-keygen -t ecdsa -b 521 -C "rhce" -f ~/.ssh/id_ecdsa'.
2. Distribute SSH keys: 'ssh-copy-id rhce@<node>' or 'for servers in $(cat list_of_servers.txt); do ssh-copy-id rhce@$servers; done'
3. Escalate Privileges: '#visudo - comment' && 'echo "user_name ALL=(ALL) NOPASSWD: ALL | tee -a /etc/sudoers.d/users.sudoers"'
4. Control Node: Managed Node 1 and Managed Node 2.

## Validation
- Use Ansible ad-hoc commands:
  * 'ansible host -i inventory_file -m module -a "args"'
      * Used to execute quick one-liners.
      * Useful for non-routine tasks.
      * Execute them by using ansible command (ansible-playbook is used for 'playbooks').
      * Args require double quotes ("") and are 'space' delimited.
      * Commands are executed as the user running Ansible.
      * Use '-b' option to exec commands as the 'root' user.
      * The '-a' option may be used without the -m option to run 'shell' commands.

## Common Uses 
* File transfer
* Package Management 
* User and group management 
* Managing services
* Fact gathering 
* General System Information 
* Software deployment from Git
* Playbook creation testing

### Example:
```
$ ansible dbservers -i inventory/inventory.ini -m ping
db01.rhce.lab | SUCCESS => {
		"ansible_facts": {
				"discovered_interpreter_python": "/usr/libexec/platform-python"
		},
		"changed": false,
		"ping": "pong"
}
db02.rhce.lab | SUCCESS => {
		"ansible_facts": {
				"discovered_interpreter_python": "/usr/libexec/platform-python"
		},
		"changed": false,
		"ping": "pong"
}
```

### Example2:
```
# Returns all the 'facts' about labservers.
$ ansible labservers -i inventory/inventory.ini -m setup
```

### Example3:
```
# If you are in the directory running the adhoc commands 
# You do 'NOT' have to use the '-i' to specify the inventory_file.
$ ansible labservers -m setup | head -20
```

### Example4:
```
$ ansible labservers -m copy -a "src=/home/rhce/Clones/ansible_studies/infra/ansible/secretFile dest=/tmp"node2.rhce.lab | CHANGED => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": true,
    "checksum": "3c1bb0cd5d67dddc02fae50bf56d3a3a4cbc7204",
    "dest": "/tmp/secretFile",
    "gid": 1000,
    "group": "rhce",
    "md5sum": "ff22941336956098ae9a564289d1bf1b",
    "mode": "0600",
    "owner": "rhce",
    "secontext": "unconfined_u:object_r:user_home_t:s0",
    "size": 15,
    "src": "/home/rhce/.ansible/tmp/ansible-tmp-1600546177.2337775-8026-196863355963736/source",
    "state": "file",
    "uid": 1000
}
node1.rhce.lab | CHANGED => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": true,
    "checksum": "3c1bb0cd5d67dddc02fae50bf56d3a3a4cbc7204",
    "dest": "/tmp/secretFile",
    "gid": 1000,
    "group": "rhce",
    "md5sum": "ff22941336956098ae9a564289d1bf1b",
    "mode": "0600",
    "owner": "rhce",
    "secontext": "unconfined_u:object_r:user_home_t:s0",
    "size": 15,
    "src": "/home/rhce/.ansible/tmp/ansible-tmp-1600546177.2306256-8024-130127375094629/source",
    "state": "file",
    "uid": 1000
}
node3.rhce.lab | CHANGED => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": true,
    "checksum": "3c1bb0cd5d67dddc02fae50bf56d3a3a4cbc7204",
    "dest": "/tmp/secretFile",
    "gid": 1000,
    "group": "rhce",
    "md5sum": "ff22941336956098ae9a564289d1bf1b",
    "mode": "0600",
    "owner": "rhce",
    "secontext": "unconfined_u:object_r:user_home_t:s0",
    "size": 15,
    "src": "/home/rhce/.ansible/tmp/ansible-tmp-1600546177.2393231-8028-139511431258555/source",
    "state": "file",
    "uid": 1000
}
```

# Example4:
```
$ ansible dbservers -a "cat /tmp/secretFile"
db02.rhce.lab | CHANGED | rc=0 >>
This is a test
db01.rhce.lab | CHANGED | rc=0 >>
This is a test
```
