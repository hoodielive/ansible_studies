# Understanding Ansible Facts 

* Facts provide certain information about a given target host.
* Facts are automatically discovered by Ansible when it reaches out to a host.
* Facts can be disabled.
* Facts are cached for use in the playbook executions.

    ```
    ansible -i ivi.ini control.rhce.lab -m setup
    ```
