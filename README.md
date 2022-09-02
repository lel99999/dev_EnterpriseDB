# dev_EnterpriseDB
EnterpriseDB Workspace, Development and Notes

##### Install Information
- EnterpriseDB Repo (need an account uid/pwd)
  - [ EnterpriseDB Repo](https://yum.enterprisedb.com/edbrepos/edb-repo-latest.noarch.rpm) <br/>

##### Reload Configuration w/o Restarting DB
- Command:
  ```
  $sudo su - enterprisedb
  $/usr/edb/as<version#>/bin/pg_ctl reload -D /path/to/data

  or 

  SELECT pg_reload_conf()
  ```

##### Notes
- Postgres user replace by enterprisedb

##### Oracle Compatibility
- NOTE: if you already have an installed server, you can use the initialization cluster option (initdb) with “--no-redwood-compat" in order to create a non-Oracle compatible server. By default, the instance created with initdb from an EDB Advanced Server would be an Oracle compatible server. <br/>

- Checking whether existing cluster is Oracle compatible
  ```
  edb=#show db_dialect;

  db_dialect
  -----------------------
  Redwood

  ### If not compatible
  ERROR:  unrecognized configuration parameter "db_dialect"
  ```
##### Commands
- Startup:
  `$sudo su - enterprisedb&&/usr/edb/as<version>/bin/edb-postgres -D /<path>/data` <br/>

- Reload Configs w/o Restarting the DB
  `/usr/edb/as<version>/bin/pg_ctl reload` <br/>

