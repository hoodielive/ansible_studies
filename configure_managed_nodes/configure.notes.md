# Configure Managed Nodes

* Create and distribute SSH keys to Managed nodes and configure privilege escalation.
1. Generate SSH keys: 'ssh-keygen -t ecdsa -b 521 -C "rhce" -f ~/.ssh/id_ecdsa'.
2. Distribute SSH keys: 'ssh-copy-id rhce@<node>' or 'for servers in $(cat list_of_servers.txt); do ssh-copy-id rhce@$servers; done'
3. Escalate Privileges: '#visudo' && 'echo "user_name ALL=(ALL) NOPASSWD: ALL | tee -a /etc/sudoers.d/users.sudoers"'
4. Control Node: Managed Node 1 and Managed Node 2.
