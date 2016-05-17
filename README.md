Role Name
=========

Docker container running redis.

Requirements
------------

- python >= 2.6
- docker-py >= 0.3.0
- Docker >= 1.9
- Ansible >= 2.1

Role Variables
--------------

`use_backup_container`: Optional, whether to use a separate container to store redis backup files. Default true.  
`backup_container_name`: Optional, the container name to store data. Default 'redis-backup'.  
`redis_container_name`: Optional, the container name where postgresql running in. Default 'redis'.  
`expose_host_port`: Optional, the port to expose redis from the host. Default not to expose redis to the host.  
`redis_docker_tag`: Optional, the redis docker image tag name to use. Default 'latest'.  

Dependencies
------------


Example Playbook
----------------

    - hosts: servers
      roles:
         - role: ansible-docker-redis
           use_datastore_container: true
           datastore_container_name: dbstore
           postgres_container_name: postgres
           expose_host_port: 5432
           postgres_docker_tag: 9.5
           postgres_docker_env:
             POSTGRES_PASSWORD: pg_admin_pw
             POSTGRES_USER: pg_admin_user
             PGDATA: /var/lib/postgresql/data/pgdata
             POSTGRES_DB: pg_default_db
             POSTGRES_INITDB_ARGS: "--data-checksums"


License
-------

MIT

Author Information
------------------

YoctolInfo
