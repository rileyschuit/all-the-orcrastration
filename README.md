## My Orchestration playbooks and roles

_SUMMARY_: This is an ongoing project to programmatically show/user samples of playbooks for my AWS and local service management in my home.  These playbooks are aimed to be idiot proof.  

Provisioning playbook (Sets up s3, vpc, subnets, routing, security group, ec2).  It will ask you for ec2 credentials for building your instances:  
```
ansible-playbook aws-provision.yml

MY_HOST:all-the-orcrastration schuit$ ansible-playbook aws-provision.yml
[WARNING]: No inventory was parsed, only implicit localhost is available

[WARNING]: provided hosts list is empty, only localhost is available. Note that the implicit localhost does not match 'all'

What is the shell username you want: appuser
What is the shell user password? REQUIRED for EC2:
```

Manual testing of aws ec2 computer playbook (for use in SSM):  
```
ansible-playbook -i <IF_OF_HOST>, aws-ec2-maintenance.yml --extra-vars "ansible_user=<WHAT_YOU_SPECIFIED_YOUR_APPUSER> ansible_password=<PASSWORD>"
```

### TODOs:  
- Make better tasks for VPC ACLs
- Consider using ansible galaxy to share and pull roles
- Create nuke option for wiping out whole environment
- Ignore terminated instances when it comes to counting desired number of instances
- IAM users, groups
