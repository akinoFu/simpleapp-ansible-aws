# Ansible for AWS
This is a school project in Computer Information Technology program at British Columbia Institute of Technology. When main_playbook.yml is run, it deploys a simple application consisting of two services (frontend&backend, and DB) on **AWS** using **Ansible**.

## Roles
### aws
- Creates the following objects on AWS
	- a VPC
	- subnets
	- security groups
	- an EC2 instance for the frontend&backend services
	- an EC2/RDS instance for DB 
### application
- Setup the application on the EC2 instance for frontend&backend
### database
- Setup MySQL on the EC2 instance (only when the *rds_database* variable is false)
## How to Run
1. Clone the repo to local
2. Create a key pair named "***ansible.pem***" on AWS
3. Place the key under the local repo directory
4.  Create an IAM user who belongs to a role having "***AdministratorAccess***" on AWS
5.  Create a file named "***aws_keys***" under the locl repo directory with the following contents:  
		export  AWS_ACCESS_KEY_ID=*access_key_id*  
		export  AWS_SECRET_ACCESS_KEY=*access_key*  
		export  AWS_DEFAULT_REGION=us-west-2  
6. Run the command
	```
	ansible-playbook main_playbook.yml
	```



