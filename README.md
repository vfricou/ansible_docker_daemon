# Docker daemon Ansible role

This role install and update official docker-ce daemon on Debian >= 10 or CentOS >= 7 hosts only.

It set officials docker repository and install `docker-ce` packages from them.

## Tags
### Install
Perform installation of all packages needed to deploy docker-ce and install docker-ce package and docker-compose utility.
```bash
ansible-playbook Docker.yml -t install
```

### Update
Launch a daemon upgrade to latest version.  
Note : This will not automaticaly update docker-compose command.
```bash
ansible-playbook Docker.yml -t update
```

## Playbook

```yaml
- name: install ansible dependencies on remote host
  hosts:
    - docker-daemon
  roles:
    - docker-daemon
  vars:
    ansible_python_interpreter: /usr/bin/python
```