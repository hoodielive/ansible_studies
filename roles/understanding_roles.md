# Understanding Roles

- The default location for roles is /etc/ansible/roles.
- Roles provide a way to automatically load certain vars_files, tasks, and handlers based on known file structures.
- Roles expect a particular directory structure.
- Directories not being used may be excluded.
- Each directory in use most contain a main.yml with relavant content.
- $HOME/ansible/path/roles/common: 

```bash
├── README.md
├── defaults
│   └── main.yml
├── files
├── handlers
│   └── main.yml
├── meta
│   └── main.yml
├── tasks
│   └── main.yml
├── templates
├── tests
│   ├── inventory
│   └── test.yml
└── vars
    └── main.yml
```

### Role Directories
- tasks, this directory contains the main list of tasks to be executed by this role::import task.
- handlers, this directory contains handlers, which may be used by this role or even anywhere outside of this role.
- defaults, this directory contains default variables for the role and is meant to provide the value to a variable if no other value is given (low precedence).
- vars - this directory contains variables used within the role (high precedence than the defaults directory). Namely, anything that is defined here will take precdence over the defaults.
- files - this directory contains files which can be deployed via this role.
- templates - this directory contains templates which can be deployed via this role.
- meta - this directory defines some of the metadata for this role.


# Understanding Roles

- The default location for roles is /etc/ansible/roles.
- Roles provide a way to automatically load certain vars_files, tasks, and handlers based on known file structures.
- Roles expect a particular directory structure.
- Directories not being used may be excluded.
- Each directory in use most contain a main.yml with relavant content.
- $HOME/ansible/path/roles/common: 

```bash
├── README.md
├── defaults
│   └── main.yml
├── files
├── handlers
│   └── main.yml
├── meta
│   └── main.yml
├── tasks
│   └── main.yml
├── templates
├── tests
│   ├── inventory
│   └── test.yml
└── vars
    └── main.yml
```

### Role Directories
- tasks, this directory contains the main list of tasks to be executed by this role::import task.
- handlers, this directory contains handlers, which may be used by this role or even anywhere outside of this role.
- defaults, this directory contains default variables for the role and is meant to provide the value to a variable if no other value is given (low precedence).
- vars - this directory contains variables used within the role (high precedence than the defaults directory). Namely, anything that is defined here will take precdence over the defaults.
- files - this directory contains files which can be deployed via this role.
- templates - this directory contains templates which can be deployed via this role.
- meta - this directory defines some of the metadata for this role.

### RHEL System Roles:
- Provided by the RHEL Extras repository.
- Requires the rhel-system-roles package to be installed.
- Can be used by Ansible Engine and Ansible Tower to manage RHEL systems.
- Needs to be installed on the Ansible control node(s) which can then be used to manage and configure the client nodes.
- Supported system roles include: kdump, network, selinux, timesync, and postfix (tech preview).
- The documentation can be found in the following location: 
    * /usr/share/doc/rhel-system-roles-<version>-/SUBSYSTEM/
- The Ansible roles may be found in the following location:
    * /usr/share/ansible/roles/rhel-system-roles.SUBSYSTEM/

### Create the directory structure for Roles:
```yaml
ansible-galaxy init role_name
```
