Docker
=========


Ansible role which installs Docker using on the 

- Supported distros:
    - Debian
    - Ubuntu

Role Variables
--------------


A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

| Variable                | Required | Default | Choices                   | 
|-------------------------|----------|---------|---------------------------|
| docker_install_compose  | no       | true    | true, false               | 


- Specifies whether `docker-compose` should be installed amongside docker 



Example Playbook
----------------

```yml
- hosts: all
  become: true
  roles:
    - docker
```

