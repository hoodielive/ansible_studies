# Create Plays and Playbooks 

## Common Modules 
* Ping 
    * Validates a server is running and reachable.
    * No required parameters.
* Setup
    * Gather Ansible facts. 
    * No required parameters.
* Yum/DNF
    * Manage packages with yum/dnf package manager.
    * Common parameters (not required): name and state. 
* Service
    * Control services on remote hosts.
    * Common paramaters: name (required), state and enabled. 
* User
    * Manage user accounts and attributes.
    * Common parameters: - name (required), state, group, and groups.
* Copy
    * Copy files to a remote host.
    * Common parameters: - src, dest(required), owner, group, and mode.
* File
    * Manages files and directories.
    * Common parameters: - path(required), state, owner, group and mode.
* Git
    * Interact with git repositories.
    * Common parameters: - repo(required), dest(required), and clone.
