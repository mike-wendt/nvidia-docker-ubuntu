# Setting up an Ubuntu host for Docker CE and nvidia-docker

## Prereqs

* Installed NVIDIA drivers
* Ansible 2.2+

### Ansible Install

To use these scripts we need the latest version of Ansible along with Git, the one line installer is below
```
sudo apt-get update && sudo apt-get install software-properties-common git -y && sudo apt-add-repository -y ppa:ansible/ansible && sudo apt-get update && sudo apt-get install ansible -y
```

## Installation

**NOTE:** This installer will remove previous versions of docker if installed

### Running Remotely

Run the following command
```
sudo ansible-pull -U https://github.com/mike-wendt/nvidia-docker-ubuntu.git 
```

### Running Locally

1. Clone this repo locally <br>`git clone https://github.com/mike-wendt/nvidia-docker-ubuntu.git`
2. Change directory <br>`cd nvidia-docker-ubuntu`
3. Run the Ansible script <br>`sudo ansible-playbook local.yml`

