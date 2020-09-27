# Understanding Ansible Galaxy:

DO NOT REINVENT THE WHEEL!

Ansible Galaxy is a large 'public' repository for downloading and sharing community developed roles.

The ansible-galaxy utility creates and removes roles or install roles from Ansible Galaxy or a git-based scm (software configuration management).

Syntax:
[delete|import|info|init|install|list|login|remove|search|setup] [--help] [options]

### Create roles directory structure:
ansible-galaxy init role_name 

### Search galaxy for roles:
ansible-galaxy search keyword --author authorname

### Install a role:
(from galaxy) ansible-galaxy install role_name 
(from a file) ansible-galaxy install -r file.yml

### List installed roles:
ansible-galaxy list

### Print information about installed roles:
ansible-galaxy info role_name

### Remove a role:
ansible-galaxy remove role_name
