# Automated software install to Ubuntu 18.04

This repository contains Ansible playbooks for automatically
install and configure various application combinations on
Ubuntu 18.04 system.

## Usage

Copy your ssh public key to the server's root's .ssh/authorized_keys manually,
if it doesn't exist there yet. You can also use a regular user with sudo rights.

Run ansible-playbook on remote server using command:

```
# Set hostname variable
export REMOTEHOST=yourserver.example.org

# Install and configure basics
ansible-playbook -vv -i fvh-inventory.yml -u root server.yml --extra-vars "hostname=citylogistiikka.fvh.io"
# ansible-playbook -vv -i "${REMOTEHOST}," -u root server.yml --extra-vars "hostname=${REMOTEHOST}" -e 'ansible_python_interpreter=/usr/bin/python3'
```
