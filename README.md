docker4wordpress
=========

Installs wodby/docker4wordpress by cloning the repository and configuring `.env` based upon `defaults/main.yml`.

Requirements
------------

Python
DNS Records pointing towards configurable `project.base_url`

Role Variables
--------------

We recommend configuring the `project` and `mariadb` dictionaries in `defaults/main.yml`

Configuration options for services `mariadb`, `php`, `nginx`, and `traefik` can be found within `defaults/main.yml`

Dependencies
------------

See `vars/main.yml` for dependency configuration

- geerlingguy.docker
  - disables `docker-compose` installation and installs `docker-ce`
- geerlingguy.pip
  - installs `docker-compose==1.24.0rc1` and `docker`

Example Playbook
----------------

    - hosts: wordpress

      vars:
        project:
          name: Vermilion Tech!
          base_url: vermilion.tech
          path: /docker/d4w.vermilion.tech

      roles:
         - { role: vermilion_tech.ansible_role_docker4wordpress }

License
-------

BSD

Author Information
------------------

Kaden Nelson `kaden@vermilion.tech` vermilion.tech
