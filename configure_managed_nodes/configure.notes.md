# Configure Managed Nodes

* Create and distribute SSH keys to Managed nodes and configure privilege escalation.
1. Generate SSH keys: 'ssh-keygen -t ecdsa -b 521 -C "rhce" -f ~/.ssh/id_ecdsa'.
2. Distribute SSH keys: 'ssh-copy-id rhce@<node>' or 'for servers in $(cat list_of_servers.txt); do ssh-copy-id rhce@$servers; done'
3. Escalate Privileges: '#visudo' && 'echo "user_name ALL=(ALL) NOPASSWD: ALL | tee -a /etc/sudoers.d/users.sudoers"'
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

- Example:
```
$ ansible dbservers -i ../infra/inventory/inventory.ini -m ping
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
