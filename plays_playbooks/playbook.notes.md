# Understanding Plays and Playbooks 

* The goal of a play to map a group of hosts to some well-defined roles.
* A play can consist of one or more tasks which make calls to ansible modules.
* A playbook is a series of plays.

    ```
    ---
    - hosts: webservers
      become: yes
      tasks:
      - name: ensure apache is at the latest version.
        yum:
          name: httpd
          state: latest
      - name: write our custom apache config file.
        template:
          src: /srv/httpd.j2
          dest: /etc/httpd/conf/httpd.conf
      - name: ensure that apache is started. 
        service:
          name: httpd
          state: started
    - hosts: dbservers
      become: yes
      tasks:
      - name: esure postgresql is at the latest version.
        yum:
          name: postgresql
          state: latest
      - name: ensure that postgresql is started. 
        service:
          name: postgresql
          state: started
    ```
