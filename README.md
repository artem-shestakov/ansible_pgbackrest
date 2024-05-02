pgBackRest
=========

Role to install and setup bpBackRest

Role Variables
--------------

* `pg_backrest_dirs` - directory for creating
```yaml
pg_backrest_dirs:
  - path: /var/log/pgbackrest
    mode: '0770'
    owner: postgres
    group: postgres
  - path: /etc/pgbackrest
  - path: /etc/pgbackrest/conf.d
```
* `pg_backrest_stanzas` - stanzas and cronjobs for backup
```yaml
pg_backrest_stanzas:
  global:
    config:
      - path: /var/lib/pgbackrest
  cluster_1:
    config:
      - path: /var/lib/pgsql/13/data
        port: 5432
    cron:
      full: "0 1 * * 0"
      diff: "0 1 * * 1-6"
```

Dependencies
------------

Example Playbook
----------------
todo

License
-------

BSD

Author Information
------------------

Artem Shestakov
artem.s.shestakov@gmail.com
