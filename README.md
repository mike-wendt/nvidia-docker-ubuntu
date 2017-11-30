# Setting up an Ubuntu host for Docker CE and nvidia-docker

## Prereqs

* Installed NVIDIA drivers
* Ansible 2.2+

### Ansible Install & Configure

To use we need the latest version of Ansible along with Git, this script will
install all necessary dependencies and configure Ansible
```
sudo apt-get update && \
sudo apt-get install software-properties-common git -y && \
sudo apt-add-repository -y ppa:ansible/ansible && \
sudo apt-get update && \
sudo apt-get install ansible -y && \
echo 'localhost ansible_connection=local' | sudo tee /etc/ansible/hosts
```

## Installation

**NOTE:** This installer will remove previous versions of docker if installed

### Running Remotely

Run the following command
```
sudo ansible-pull -U https://github.com/kkraus14/nvidia-docker-ubuntu.git 
```

### Running Locally

1. Clone this repo locally <br>`git clone https://github.com/kkraus14/nvidia-docker-ubuntu.git`
2. Change directory <br>`cd nvidia-docker-ubuntu`
3. Run the Ansible script <br>`sudo ansible-playbook local.yml`

## Troubleshooting

If you see this error `ERROR! Could not find a playbook to run.` run this 
command to fix:
```
echo 'localhost ansible_connection=local' | sudo tee /etc/ansible/hosts
```
