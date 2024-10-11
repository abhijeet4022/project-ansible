# project-ansible
Repository for Ansible playbooks and roles used for automating application deployments in the project.

# To install ansible
`sudo yum install ansible -y`

# Create one aws vm as workstation and attache the admin IAM role.

* Command to run the ansible playbook
`ansible-playbook -i frontend-dev.learntechnology.cloud, -e ansible_user=centos -e ansible_password=DevOps321 frontend.yml`
