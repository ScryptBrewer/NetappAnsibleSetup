# netapp_ansible_setup
Use to install required settings and validate configuration using collections with NetApp collections modules. The netapp_ansible_setup_play.yml may be modified to include mulitple clusters to accept ansible commands. The ssh process requires that you provide the admin password while the play is running. 

Once the setup has been executed you can use the aggrinfo_test_play.yml to test to see if ansible is able to gather facts from the NetApp cluster. 

## Setup 
Review all yal files to get basic understanding of functionality. 
To complete a base setup of the collections modules and required storage and python modules. 
To use:
git clone https://github.com/ScryptBrewer/NetappAnsibleSetup.git

## Example commands
ansible-playbook netapp_ansible_setup_play.yml --extra-vars="netapp_hosts=[10.10.10.1]" 

ansible-playbook netapp_ansible_setup_play.yml 

To update ansible hosts modules only
ansible-playbook netapp_ansible_setup_play.yml --skip-tags="setup_ontap"

### run the play with a update aggrinfo_test_play.yml file
ansible-playbook aggrinfo_test_play.yml 

Will return the aggreagate names if successful. 


## Addtional Info for updates to aggrinfo_test_play.yml
To test after setting up collections use
update the aggrinfo_test_play.yml 
  netapp_user: "admin"
  netapp_password: "Secret1"
  netapp_hosts: "10.10.10.1"

