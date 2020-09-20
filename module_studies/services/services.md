# Service Module
The service module - this controls services on a remote host. The supported init systems are BSD init, OpenRC, SysV, Solaris SMF, systemd and upstart.

### Example
```yaml
- name: Show options for service module
  service:
    name: service_name
    state: started|stopped|restarted|reloaded
    enabled: yes|no
    args: additional args provided on command line
```

### Systemd module
Controls systemd services on a remote host. 

### Example
```yaml
- name: Show options for systemd module 
  systemd: 
    name: service_name
    state: started|stopped|restarted|reloaded
    enabled: yes|no
    daemon_reload: yes|no
    force: yes|no
```
