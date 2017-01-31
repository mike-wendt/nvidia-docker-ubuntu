# Setting up a host for nvidia-docker containers

## Prereqs

* Installed NVIDIA drivers

## Usage

1. Install Ansible
 `sudo apt-add-repository ppa:ansible/ansible && sudo apt-get update && sudo apt-get install ansible -y`
2. Run the following to install to localhost
 `sudo ansible-pull -U https://github.com/mike-wendt/nvidia-docker-ubuntu.git`
