# ansible-servicenow-inventory
ServiceNow Inventory plugin for Ansible

### Local Development Setup
#### Inventory development
##### Option 1
1. Install ansible 
2. Install ansible collection or use the docker image of ansible ee
```shell
ansible-galaxy install -r collections/requirements.yml
```
3. Run ansible-inventory
```shell
ansible-inventory -i inventory/servicenow.cmdb.linux.now.yml --graph --vars
```
##### Option 2
#### Docker
* copy [env.example](env.example) to env
* Enter all the information in env
```shell
docker run -it --env-file env \
  -v $(pwd):/app \
  --name ansible_servicenow_ee \
  docker.io/arumugamsubramanian/ansible-servicenow-ee:latest bash
```
* Run ansible-inventory
```shell
ansible-inventory -i inventory/servicenow.cmdb.linux.now.yml --graph --vars
```