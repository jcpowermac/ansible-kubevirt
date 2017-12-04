### ansible-kubevirt

This project is a testing ground for creating automation to deploy kubevirt.

#### What does project accomplish?

- Creates local CentOS virtual machines via QCOW2 cloud image (optionally)
  - Increase root partition / file system size
- Install Docker and configure secondary disk for OverlayFS
- Configure networking
- Install kubeadm prerequisites
- Install and configure kubeadm with weave.
- Install kubevirt


#### Inventory

Add a single master and multiple nodes to `inventory/hosts.ini`.
There are a number of options within `inventory/group_vars/all.yml`


|Variable|Example|Description|
|--------|-------|-----------|
|dns4|"192.168.122.1"|DNS servers for virtual machines|
|gateway|192.168.122.1|Default GW for virtual machines|
|mask|24|netmask for virtual machines|
|domain_name|"example.com"|Domain name for virtual machines|
|configure_partition|boolean|Expand the partition for virtual machines|
|configure_docker|boolean|Install and configure OverlayFS on vdb|
|configure_networking|boolean|Configure static IP address|
|install_kubeadm|boolean|Install and run kubeadm|
|create_local_vm|boolean|Create local virtual machines|
|wait_kubevirt_rollout|boolean|Install Ansible Kubernetes modules;wait for kubevirt todeploy|

#### Installation
[![asciicast](https://asciinema.org/a/150886.png)](https://asciinema.org/a/150886)


#### Create and interact with kubevirt virtual machine
[![asciicast](https://asciinema.org/a/150889.png)](https://asciinema.org/a/150889)

