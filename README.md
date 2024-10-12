# project-ansible
Repository for Ansible playbooks and roles used for automating application deployments in the project.



# Pre-Requisites
1. Create SG to allow SSH from internet `allow-ssh` .
2. Create one IAM role with admin privilege - `admin-role`.
* Create one aws vm as workstation and attach the admin IAM role and SG.
* Then install ansible on the workstation vm - `sudo yum install ansible -y`
* Launch 10 VMs in AWS, one for each component.
* Create A records for each VM (component) with their private IPs.
* Replace the existing A records in the config files with the newly created ones.





* Command to run the ansible playbook
`ansible-playbook -i frontend-dev.learntechnology.cloud, -e ansible_user=centos -e ansible_password=DevOps321 frontend.yml`
