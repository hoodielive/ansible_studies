# Lets Manage Parallelism

- Parallelism is the word used for Ansible's default ability to interact with multiple hosts at the same time.
- The parallel processes spawned by Ansible are known as forks.
- The default number of forks in Ansible is 5.
- The default number of forks can be changed by editing the forks parameter in ansible.cfg.
- The number of forks can be changed on a per command basis by using the '-f' flag.
- Ansible allows for rolling updates using the serial keyword. 

### Change default forks value in ansible.cfg:
```bash
forks = desired_number
```

### Change forks value in the command line:
```bash
ansible host -f desired_number -m module -a 'arguments'
ansible-playbook -f desired_number playbook.yml
```
