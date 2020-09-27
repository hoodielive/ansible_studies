# Understanding Ansible Vault
- Can be used to encrypt any structured data file used by Ansible: 
  - Variable files in group_vars and host_vars directories.
  - Variable files loaded by include_vars and vars_files in playbooks.
  - Variable files passed on the command line using '-e' @var_file.yml
- Passwords on an encrypted file can be updated using the ansible-vault rekey command.
- Can be used to encrypt individual variables inside a YAML file using the !vault tag.
- Uses vault IDs to support multiple vault passwords (labels are used to distinguish between individual passwords):
    * example: --vault-id label@source

### The Ansible Vault Command:

Create an encrypted file:
```bash
ansible-vault create file.yml 
```

Create an encrypted file with a vault ID:
```bash
ansible-vault create --vault-id label@source file.yml 
```

Edit an encrypted file:
```bash
ansible-vault edit file.yml
```

Rekey encrypted files a vault ID:
```bash
ansible-vault rekey file1.yml file2.yml
```

Encrypt an existing file:
```bash
ansible-vault encrypt file.yml
```

Encrypt an exiting file with a vault ID:
```bash
ansible-vault encrypt --vault-id label@source file.yml
```

Decrypt a file:
```bash
ansible-vault decrypt file.yml
```

View an encrypted file: 
```bash
ansible-vault view file.yml
```

Encrypt a string to be used as a variable in a YAML file:
```bash
ansible-vault encrypt_string --ask-vault-pass 'string_value' --name 'secret_var'
```

### Providing Vault Passwords

Use password stored in a text file: 
```bash
ansible-playbook --vault-password-file /path/to/password/file playbook.yml
```

Use password store in a text file with a Vault ID:
```bash
ansible-playbook --vault-id label@source playbook.yml
```

Prompt for a password
```bash
ansible-playbook --ask-vault-pass playbook.yml
```

Prompt for a password with a Vault ID:
```bash
ansible-playbook --vault-id label@prompt playbook.yml
```

Use multiple passwords with vault ID:
```bash
ansible-playbook --vault-id label1@password_file --vault-id label2@password_file playbook.yml
```
