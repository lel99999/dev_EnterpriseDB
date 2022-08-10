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

