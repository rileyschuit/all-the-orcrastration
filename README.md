## My Orchestration playbooks and roles

_SUMMARY_: This is an ongoing project to programmatically show/use samples of playbooks for my AWS and local service management in my home.  These playbooks are aimed to be idiot proof.  

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
ansible-playbook -i 192.168.1.11, onprem-install-ssm.yml -u pi --ask-pass --extra-vars 'ssm_id=b4e5cb07-efa9-464a-bfba-WORD_TO_YOUR_MOTHER code_id=SUPER_SERCRET_STUFF ssm_region=us-east-1'"
```

Example of using local vagrant file
```
ansible-playbook -i localhost, playbooks/install_opensprinkler.yml -e ansible_user=vagrant -e ansible_ssh_port=2222 --ask-pass
```

### TODOs:  
- Make better tasks for VPC ACLs
- Create nuke option for wiping out whole environment
- Ignore terminated instances when it comes to counting desired number of instances
- OnPrem machine management, once that is figured out - get greengrass going
