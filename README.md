# ansible-playbook
### Prerequisites

1. python and ansible is installed if not then checkout [this link](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
2. SSH key is setup in remote system check out [this guide](https://kerneltalks.com/howto/establish-passwordless-ssh-between-two-servers/) if not done

## running ansible plabook
1. First make sure you have both files ready (`playbook.yml` and `host.ini`)
2. Updateing host file
 - adding new server ip
   ```
   [all] <- Group name
   x.x.x.x <- IP
   ```
 - adding remote username and password for authencation too see all available options use this [link](https://docs.ansible.com/ansible/latest/inventory_guide/intro_inventory.html)
   ```
   [all]
   x.x.x.x
   [all:vars] <- add group specific variables follow this syntex
   ansible_user=YOUR_USERNAME
   ansible_password=YOUR_SUPER_SECURE_PASSWORD
   ansible_ssh_private_key_file=/absulate/path/to/keyfile

   ```
3. Running playbook [ansible docs](https://docs.ansible.com/ansible/latest/network/getting_started/first_playbook.html) to see all options

`ansible-playbook -i host.ini playbook.yml`

- `-i` to speify hostfile
