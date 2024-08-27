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
![Screenshot from 2024-08-27 15-28-40](https://github.com/user-attachments/assets/2dcfb26d-39c8-460d-bb70-0ffd9cae0e1f)
![Screenshot from 2024-08-27 15-29-41](https://github.com/user-attachments/assets/fe9e38bc-174a-4e90-871f-26e7897d5515)





