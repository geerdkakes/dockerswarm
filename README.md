# Playbook for configuring a swarm cluster

This playbook follows the advanced docker training handbook.

For running this playbook create an inventory file, e.g.:

```
[masters]
node0.eu-west-1.compute.amazonaws.com

[nodes]
node1.eu-west-1.compute.amazonaws.com
node2.eu-west-1.compute.amazonaws.com
node3.eu-west-1.compute.amazonaws.com


[firstmaster]
node0.eu-west-1.compute.amazonaws.com

[all:vars]
ansible_ssh_user=ubuntu
ansible_python_interpreter=/usr/bin/python
```
Make sure all systems have a public certificate installed for a user which ca su to root.
Before running this playbook you can add the private certificate for this user using:
```
ssh-add private-key.pem
```
Run the playbook using:

```
ansible-playbook full_cluster.yml -i ./inventory -v
```