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
- tasks, this directory contains the main list of tasks to be executed by this role. 
- handlers, this directory contains handlers, which may be used by this role or even anywhere outside of this role.
- defaults, this directory contains default variables for the role and is meant to provide the value to a variable if no other value is given (low precedence).
- vars - this directory contains variables used within the role (high precedence).
- files - this directory contains files which can be deployed via this role.
- templates - this directory contains templates which can be deployed via this role.
- meta - this directory defines some of the metadata for this role.
