# Mr Milu ansible role rabbitmq

Ansible role to install and configure rabbitmq in debian and ubuntu systems

## REQUIREMENTS

ansible >= 2.4  
magic variables in remote host

## DEPENDENCIES
ubuntu / debian

## VARIABLES
#### Vars:
urls for asc keys and their respective repo entries

#### Defaults:
- list of users  

```
rabbitmq_users:
- user: "admin"
  password: "password"
  tags: "management"
  vhost: "/"
  configure_priv: ".*"
  read_priv: ".*"
  write_priv: ".*"
  state: "present"
```

* nofile limits (ulimit) setup via systemd

```
rabbit_nofile_limit: 300000
```

* enable ui management console

```
rabbit_enable_management: yes
```
* list of paths to copy extra config files in /etc/rabbitmq/rabbitmq.conf.d

```
rabbitmq_extra_files: []
```

Also this role generate the general config file with all default values commented

* the packages that this role needs to install:

```
rabbitmq_pkgs:
- "esl-erlang"
- "rabbitmq-server"
```

## TODO
- manage vhosts
- add tls support
- manage queues
- add tags


## author
aizquierdo@mrmilu.com
