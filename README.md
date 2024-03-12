Implementation of #Virtual Private Cloud (vpc) with servers in private subnets and NAT used in Production environment.


![private subnet](https://github.com/pavan-pedditi/AWS-vpc_project/assets/162891338/7dc66c13-1a17-4e7f-8cd3-5177df7d516e)

✅ Things Done:
1.To improve resiliency, deployed the servers in two Availability Zones, by using an Auto Scaling group and an Application Load Balancer.
2.For additional security, deployed the servers in private subnets. The servers receive requests through the load balancer.
3.The servers can connect to the internet by using a NAT gateway. To improve resiliency, deploy the NAT gateway in both Availability Zones.


Project Presenation:-


