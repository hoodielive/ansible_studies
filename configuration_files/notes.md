# Configuration Files
* Possbile locations of Ansible configuration files (in order processed):
  * ANSIBLE_CONFIG (environment variable)
  * ansible.cfg (in current directory)
  * ~/.ansible.cfg(in home directory)
  * /etc/ansible/ansible.cfg

* A configuration file will not automatically load if it is in a world writable directory.
* Configuration can be set in environment variables.

## Common Ansible Configurations

* The ansible-config command can be used to view configurations:
  * list - Prints all configuration options.
  * dump - Dumps configuration.
  * view - View the configuration file.

* Commonly used settings:
  * inventory - Specifies the default inventory file. 
  * roles_path - Sets paths to search in for roles. 
  * forks - Specifies the amount of hosts configured by Ansible at the same time (Parallelism).
  * ansible_managed - Text inserted into templates which indicate that file is managed by Ansible
    and changes will be overwritten.
