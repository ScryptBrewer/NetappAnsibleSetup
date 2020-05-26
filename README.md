# netapp_ansible_setup
Use to install required settings and validate configuration using collections with NetApp collections modules. The netapp_ansible_setup_play.yml may be modified to include mulitple clusters to accept ansible commands. The ssh process requires that you provide the admin password while the command is running. 

Once the setup has been executed you can use the aggrinfo_test_play.yml to test to see if ansible is able to gather facts from the NetApp cluster. 

To complete a base setup of the collections modules and required storage and python modules. 
To use:
git clone https://github.com/ScryptBrewer/NetappAnsibleSetup.git

ansible-playbook netapp_ansible_setup_play.yml --extra-vars="netapp_hosts=[10.10.10.1]" OR update the netapp_ansible_setup_play.yml to your site configurations. 

The setup play can be run at any time to force a update to the collections versions. Use the --skip-tags="setup_ontap" to prevent ontap steps. 

To test after setting up collections use
update the aggrinfo_test_play.yml 
  netapp_user: "admin"
  netapp_password: "Secret1"
  netapp_hosts: "10.10.10.1"

ansible-playbook aggrinfo_test_play.yml 
