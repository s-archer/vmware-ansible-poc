Run this playbook using the inventory (./inventory) as follows:

ansible-playbook ./playbooks/main-create-playbook.yaml --ask-vault-pass -e @./vars/vmware_creds.yaml -vvvv -i inventory

You will need to create a credentials file (or files) containing the following variables, ideally protected with vault:

    ./vars/vmware_creds.yaml

    vcenter_user: "<username>"
    vcenter_pass: "<password>"

    ./vars/vmware_creds.yaml
    
    vm_admin_pass: "<username>"
    vm_root_pass: "<password>"
