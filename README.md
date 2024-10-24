Ansible Role: Postgresql-docker
===============================

Install PostgreSQL Docker Compose project.

Requirements
------------

Requires the following to be installed:
- docker
- docker compose

Role Variables
--------------

Common Docker projects variables:

```yaml
# Base directory for Docker projects
docker_projects_path: # /var/apps
```

Available role variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
# Docker project variables

postgres_project_name: postgres

# PostgreSQL project variables

postgres_version: 16

postgres_shm_size: 128mb

postgres_password: P05t6re5

postgres_databases: []
#  - database: dbname
#    user:     username
#    password: us3rp4ssw0rd
```

Dependencies
------------

This role depends on :
- [djuuu.docker_project](https://github.com/Djuuu/ansible-role-docker-project)

Example Playbook
----------------

```yaml
- hosts: all
  gather_facts: true
  gather_subset:
    - "!all"
    - "!min"
    - user_id

  roles:
    - djuuu.postgresql_docker
```

License
-------

Beerware License
