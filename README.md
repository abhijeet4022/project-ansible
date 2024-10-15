# project-ansible
Repository for Ansible playbooks and roles used for automating application deployments in the project.



# Pre-Requisites
1. Create a security group named `allow-ssh` to allow SSH access from the internet.
2. Create an IAM role with admin privileges named `admin-role`.
3. Launch a new EC2 instance as your workstation and attach both the `admin-role` IAM role and the `allow-ssh` security group to the instance.
4. Install Ansible on the workstation:
   * `sudo yum install ansible -y`
5. Create SG named `allow-all` and allow all port from internet.
6. Launch 10 EC2 instances in AWS, each representing a component of the Roboshop project and use `allow-all` SG.
7. Create A Records for each VM with their private IPs.
8. Update Configuration Files
   1. Replace existing A records in the following configuration files with the newly created ones:
      - `1-reverse-proxy.conf`
      - `cart.service`
      - `catalogue.service`
      - `payment.service`
      - `shipping.service`
      - `user.service`
      - `schema_setup.yml`
      - `mysql_schema_setup.yml`
* Important: Update the RabbitMQ user password in the `payment.service` file.

9. Use the following command to run the playbook for a specific component:
   - `ansible-playbook -i <host>, -e component=<component_name> -e ansible_user=<username> -e ansible_password=<password> main.yml
   `
   * Parameters:
     - <host>: The hostname or inventory file for the targeted VMs.
     - <component_name>: The specific component you want to deploy (e.g., cart, payment, catalogue).
     - <username>: The username to SSH into the VMs (e.g., centos).
     - <password>: The SSH password for the VMs.