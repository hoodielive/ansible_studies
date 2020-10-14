# Understanding Variables { Template Studies }
Variables:
  * Can contain letters, numbers and underscores.
  * Must begin with a letter. 
  * Can be stored in dictionaries, which map keys to values.
  * Dictionary variables can be referenced using bracket notation or dot-notation:
    * Example: dictionary_name['field'] or dictionary.field
  * Variables stored as a list(array) may be accessed by putting the element number in brackets:
    * Example (first element of an array)::{{ array_name[0] }}.
  * Variables may be defined or set in the following locations: 
    * Inventories (also in host_vars and group_vars directoriesj).
    * Playbooks (i.e., set in roles/role_name/vars/main.yml).
    * The command line (i.e., with '-e' or '--extra-vars').
  * Referenced defined variables using the Jinja2 templating system.
    * Example: This is my {{ variable }}.
  * Transform variable values using Jinja2 filters (i.e., join|capitalize, etc.).
  * Ansible stores information about remote hosts in variables known as Ansible facts.
  * Ansible provides special, reserved variables known as magic variables.
    * Examples: hostvars, groups, group_names, and inventory_hostname.
  * Custom facts (AKA local facts) can be added to the remote system by the user:
    * Defined in files that end with .fact.
    * Local fact files are stored in /etc/ansible/facts.d.
    * Fact file directory can be changed using the fact_path keyword.
    * Local facts can be viewed by running the following: ansible <hostname> -m setup -a "filter=ansible_local"
