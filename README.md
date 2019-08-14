Run this playbook using the inventory (./inventory) as follows:

ansible-playbook ./playbooks/main-create-playbook.yaml --ask-vault-pass -e @./vars/vmware_creds.yaml -vvvv -i inventory
