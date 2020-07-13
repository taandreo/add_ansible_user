# Add Ansible User

## add_ansible_user.yml

Playbook used for create a ansible user.

Variables:

`user`: The user that will be created in the remote host.
`key_file`: Path to the public key file.

Tasks performed:

1. Create a user with no password.
2. Copy the ssh_key from local host to the remote host, in .ssh/authorized_keys file.
3. Enable sudo without password for the created user.

## ansible.cfg

Set some specific settings for playing the playbook.

Among them, some can be highlighted:

`ask_pass = true`: Initiate a prompt to collect the login password from the remote host.  
`become_ask_pass = true`: Initiate a prompt to collect the sudo password from the remote host. 

## inventory

inventory with the list of hosts, in ini format.

## Usage
```
ansible-playbook add_ansible_user.yml -u user
```
