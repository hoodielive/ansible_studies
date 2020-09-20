# Firewalld Module
*The firewalld module allows for the addition or deletion of running or permanent firewall rules by servicews or ports (TCP or UDP).* 

### Example
```yaml
- name: add firewalld rules by service 
  firewalld:
    zone: public|dmz|internal|external|trusted|etc.
    service: service_name
    permanent: yes|no
    immediate: yes|no
    state: enabled|disabled|present|absent
- name: add firewall rules by port(s)
  firewalld:
    zone: public|dmz|internal|external|trusted|etc.
    port: 8080/tcp|170-179/udp
    permanent: yes|no
    immediate: yes|no
    state: enabled|disabled|present|absent
- name: add firewall rich rule
  firewalld:
    zone: public|dmz|internal|external|trusted|etc.
    rich_rule: rule family=ipv4 forward-port forward-port port=443 protocol=tcp to-port=8443
    permanent: yes|no
    immediate: yes|no
    state: enabled|disabled|present|absent

```

