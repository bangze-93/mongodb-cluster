# Install MongoDB Cluster (Docker) using Ansible on Ubuntu 20 
### Adjust with your env
- ##### <i> ``` vars/all.yaml ``` </i> 
```
---
mongo_cluster_name: MongoDB-Cluster
mongo_version: 7.0.12
mongo_initdb_root_username: admin
mongo_initdb_root_password: YtZkg4308OsR2yXM
mongo_vol_dir: /opt/mongodb
timezone: Asia/Jakarta
...
```
- ##### <i> ``` inventory/hosts ``` </i>
```
[mongo]
mongo01 ansible_host=192.168.60.141
mongo02 ansible_host=192.168.60.142
mongo03 ansible_host=192.168.60.143

[all:vars]
ansible_user=user
ansible_ssh_pass=P4s5word
ansible_become_password=P4s5word
```
### Run playbook
```
ansible-playbook playbook.yaml
```
### Access MongoDB using MongoDB Compass

```
mongodb://admin:YtZkg4308OsR2yXM@192.168.60.141:27017,192.168.60.142:27017,192.168.60.143:27017/?replicaSet=MongoDB-Cluster&authMechanism=DEFAULT&authSource=admin
```




