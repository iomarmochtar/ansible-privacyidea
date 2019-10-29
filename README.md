Ansible PrivacyIdea Role
========================

Supporting:
- privacyidea installation using independent python distribution (using miniconda).
- Choose backend database, sqlite (default), mysql and postgresql.
- LDAP proxy installation.
- Flexible application path.

Install
-------

```bash
ansible-galaxy install iomarmochtar.privacyidea
```

Requirements
------------

- Internet access to download all required files and packages.
- Disable SELinux.
- Backend database if you are using other than sqlite.

Role Variables
--------------

You can see all the default variable in **defaults/main.yml**, but you may change following variables:
- **install**, set to "true" if you want do installation.
- **install_ldap_proxy**, set to "true" if you want to install ldap proxy.
- **admin_act**, for admin account that will be created.
- **admin_pwd**, admin account password.
- **admin_email**, admin's email. 
- **driver**, set to mysql or postgresql otherwise will set to the default one (sqlite).
- **db_params**, database parameter for mysql or postgresql.


Example Playbook
----------------

This is example of installing privacyidea including it's ldap proxy by using mysql as data store. 
make sure the database is available with given grans

```yaml
---
- hosts: 127.0.0.1 
  roles:
    - role: iomarmochtar.privacyidea
      install: true
      install_ldap_proxy: true
      driver: mysql
      db_params:
        db_name: 2fa
        port: 3306
        host: 127.0.0.1
        username: 2fa
        password: 2fa
```

License
-------

GNU GPL v3.0


Author Information
------------------

```
Author: Imam Omar Mochtar
Email: iomarmochtar@gmail.com
Website: https://blog.mochtar.net
```
