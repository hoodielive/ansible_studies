# Variables 

* Variable names should only contain letters, numbers and underscores.
* Variables should always start with a letter.
* There are three main scopes for variables:

  * Global
  * Host
  * Play

* They are typically used for configuration values and various parameters.
* Variables can store the return value of executed commands. 
* Variables may also be dictionaries.
* Ansible provides a number of predefined variables.

INI format:

```
[webservers]
host1 http_port=80 maxRequestsPerChild=500
host2 http_port=305 maxRequestPerChild=600
```

YAML format: 
```
webservers: 
  host1:
    http_port: 80
    maxRequestPerChild: 500 
  host2:
    http_port: 305
    maxRequestPerChild: 600
```
