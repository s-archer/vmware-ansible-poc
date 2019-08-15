Requires: 

 - f5-sdk (pip install f5-sdk)
 - cot 
 - pyvmomi

Before deploying to VMware, you must prepare the OVA file - we insert empty custom attributes into the OVA using cot.  Download the f5 OVA file from downloads.f5.com.  Then update the vmware_vars.yaml to point to the downloaded OVA file and then use the ova-modify-playbook to make the required modifications.  You only need to do this once for each OVA file you want to use.


Run the 'main-create-playbook' using the inventory (./inventory) as follows:

ansible-playbook ./playbooks/main-create-playbook.yaml -i inventory

( or if using vault to protect your credentials, ansible-playbook ./playbooks/main-create-playbook.yaml --ask-vault-pass -e @./vars/vmware_creds.yaml -vvvv -i inventory|)

You will need to create a credentials file (or files) containing the following variables, ideally protected with vault:

    ./vars/vmware_creds.yaml

    vcenter_user: "<username>"
    vcenter_pass: "<password>"

    ./vars/vmware_creds.yaml
    
    vm_admin_pass: "<username>"
    vm_root_pass: "<password>"

Notes:

- variable names should only contain [a-zA-Z0-9_] 

Overwrite local copy of repo:

git fetch --all
git reset --hard origin/master
