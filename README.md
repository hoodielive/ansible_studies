# EX294 Preparation and General Ansible Studies

### Lab Setup ###
*Note: I configured 5 servers (4 Centos 8, 1 Ubuntu 20.04) for labs:*
 - 4 Centos 8 Servers 
 - 1 Ubuntu 20.04
 
1. Server1 8GB, IPA Server to have enterprise services to managed Kerberos, DNS, MAIL, FTP, HTTPS, etc
2. Server2 8GB, Ansible Control Node.
3. Server3 4GB, Ansible Node1. 
4. Server4 4GB, Ansible Node2.
5. Server5 4GB, Ansible Node3. 

### Partition Scheme ###
1. 70Gb VHD on rootvg 
* 2GB  /boot xfs 
* 10GB /home xfs 
* 20GB /     xfs (root) 
* 20GB /var  xfs 
* 4GB  swap 
* 14GB free space 

### IP Address Space ###
1. Private Host IP Range on the 10.0.3.0/24 subnet - rhce.lab (namespace).
  * IPA Server 10.0.3.2/24
  * Ansible Control Node 10.0.3.10/24
  * Ubuntu 20.04 - Node1 10.0.3.11/24
  * Centos 8 - Node2 10.0.3.12/24
  * Centos 8 - Node3 10.0.3.13/24

### EX294 Objectives 

As an RHCE exam candidate, you should be able to handle all responsibilities expected of a Red Hat Certified System Administrator, including these tasks:

Be able to perform all tasks expected of a Red Hat Certified System Administrator

* Understand and use essential tools
* Operate running systems
* Configure local storage
* Create and configure file systems
* Deploy, configure, and maintain systems
* Manage users and groups
* Manage security

### Understand core components of Ansible

* Inventories
* Modules
* Variables
* Facts
* Plays
* Playbooks
* Configuration files
* Use provided documentation to look up specific information about Ansible modules and commands

### Install and configure an Ansible control node

* Install required packages
* Create a static host inventory file
* Create a configuration file
* Create and use static inventories to define groups of hosts
* Manage parallelism

### Configure Ansible managed nodes

* Create and distribute SSH keys to managed nodes
* Configure privilege escalation on managed nodes
* Validate a working configuration using ad hoc Ansible commands

### Script administration tasks

* Create simple shell scripts
* Create simple shell scripts that run ad hoc Ansible commands

### Create Ansible plays and playbooks

* Know how to work with commonly used Ansible modules
* Use variables to retrieve the results of running a command
* Use conditionals to control play execution
* Configure error handling
* Create playbooks to configure systems to a specified state

### Use Ansible modules for system administration tasks that work with:

* Software packages and repositories
* Services
* Firewall rules
* File systems
* Storage devices
* File content
* Archiving
* Scheduled tasks
* Security
* Users and groups

### Work with roles

* Create roles
* Download roles from an Ansible Galaxy and use them

### Use advanced Ansible features

* Create and use templates to create customized configuration files
* Use Ansible Vault in playbooks to protect sensitive data
* Create and use templates to create customized configuration files 
* Work with Ansible variables and facts 
* Create and work with roles 
* Download roles from an Ansible Galaxy and use them Manage parallelism 
* Use Ansible Vault in playbooks to protect sensitive data 
* Use provided documentation to look up specific information about Ansible modules and commands

*As with all Red Hat performance-based exams, configurations must persist after reboot without intervention.*


