Create/Update an MSSQL Server in Azure
=========

Creates new Microsoft SQL Server in Azure

Requirements
------------

ansible >=2.7.0
Azure RM modules
Resource group must exists prior

Server Module Documentation: <https://docs.ansible.com/ansible/latest/modules/azure_rm_sqlserver_module.html>

Role Variables
--------------

```yaml
Variables outside of script directly needed for formating:

#Default required
resource_group:
location: #Azure location

#SQL Database Options
sql_server: #Name of the SQL server you're creating or changing
sql_version: #Version of MSSQL Server
```

Dependencies
------------

Example Playbook
----------------

```yaml
---

- name: Create or Update an Azure SQL Server
  hosts: localhost
  pre_tasks:
    - name: Setting desired state
      set_fact:
        resource_group: testRG
        location: canadacentral
        sql_server: MyServer01
        sql_server_admin: myadminaccount
        sql_server_password: XXXXXXXXXXXX

  connection: local
  roles:
    - azure-sqlserver

```

License
-------

MIT

Author Information
------------------

Adam Brassard: Abrass on IRC