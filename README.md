Role Name
=========

Docker container running redis.

Requirements
------------

- python >= 2.6
- docker-py >= 1.7.0
- Docker API >= 1.20
- Ansible >= 2.2

Role Variables
--------------

```yaml
---
# Optional, the redis docker image tag name to use. Default 'latest'.
redis_docker_tag: ''

# Optional, whether to use a separate container to store redis data files.
use_backup_container: true

# Optional, the container name to store data. Default 'redis-backup'.
backup_container_name: redis-backup

# Optional, the container name which running redis. Default 'redis'.
redis_container_name: redis

# Optional, the port to expose redis to the host.
# Default not expose redis to the host.
expose_host_port: 0

```

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
