pbullian.EC2
=========

Creates a security group and EC2 servers for farming!.

Requirements
------------

boto package is required.

Role Variables
--------------

 ec2_server_instcount: 1 # quantity of servers to create
 
 ec2_server_instance_type: 'm3.medium' # size of the instance, see: https://aws.amazon.com/ec2/instance-types/
 
 ec2_server_image: 'ami-9a562df2'  # AMI image id, see: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/finding-an-ami.html
 
 ec2_server_ansible_ssh_user: '' # 
 
 ec2_server_region: 'sa-east-1' # location, see: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html 
 
 ec2_server_pem_path: '' 
 
 ec2_server_group_name: 'ec2_server_hosts' # set group name, see: http://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/what-are-resource-groups.html
 
   
 ec2_server_keypair: '' # key pair id, see: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html
 
 ec2_server_access_key: '{{ lookup("env","AWS_ACCESS_KEY") }}' # export AWS_ACCESS_KEY="XXXXXXXXXXX"
 
 ec2_server_secret_key: '{{ lookup("env","AWS_SECRET_KEY") }}' # export AWS_SECRET_KEY="XXXXXXXXXXXXXXXXXXXX"
 
 ec2_server_name: '' # server name
 
 ec2_server_security_group: '' # server security group

Dependencies
------------

none

Example Playbook
----------------

    - hosts: localhost #runs "locally"
      connection: local
      gather_facts: False
      tags: provisioning

      roles:
         - { role: pbullian.ec2 }

License
-------

GPLv3

Author Information
------------------

pbullian [at] unsam.edu.ar
