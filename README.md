 Implementation of #Virtual Private Cloud (vpc) with servers in private subnets and NAT used in Production environment.


 ![private subnet](https://github.com/pavan-pedditi/AWS-vpc_project/assets/162891338/7dc66c13-1a17-4e7f-8cd3-5177df7d516e)

✅ Things Done:
 1.To improve resiliency, deployed the servers in two Availability Zones, by using an Auto Scaling group and an Application Load Balancer.
 2.For additional security, deployed the servers in private subnets. The servers receive requests through the load balancer.
 3.The servers can connect to the internet by using a NAT gateway. To improve resiliency, deploy the NAT gateway in both Availability Zones.

 Step of Project:-
  step -1:-
   creating vpc in two availabilty zones. with two public subnets and two private subnets
   and attaching one nat gateway to each availability zone withno s3 Gateway
  step-2:-
   create launch template and auto scalling group
   create a launch template
   ⦁	i has selected ami as ubuntu and selected  type t2.micro
   ⦁	create a security group with ssh and port required to acess application and selected vpc i  have created 
   auto Scaling Group
   ⦁	i have created two ec2 instances in two private subnets
   ⦁	set desired group size as 2. minimum group size as 1. and maximum size as 4
   This created two Ec2 instances in two private subnets 
  step-3:-
   I have created bastion host Ec2 instance in the same Vpc's public Subnet to acess private subnets 
  step-4:-
   ⦁	I copied pem.key to bastion host unsing scp shell command
   ⦁	command:- scp -i <pemkey path>  <pemkey path> ubuntu@bastion-ip
   ⦁	I have accesed the instance in  private subnets with pem.file i have copied
  step-5:-
   ⦁	create target group and allow port u want to acess in my case it port 8000
   ⦁	select VPC we created  and select instances which we want to acess click on select pending below create a target group
  step-6:-
   ⦁	create a Load Balancer with internet facing with network mapping vpc already created and select both Public Subnets in both availability zones
   ⦁	select security group and allow port we are trying to access in Load Balancer
   ⦁	Add  target group to Load Balancer and create Load balancer
  step-7:-
   login to private subnet as we did in Step-3 create Html and run the python3 application in port 8000
   python3 -m http.server 8000
  Step-8:-
   copy DNS of load balance and paste in browser we have to see output.




