## VPC Notes - aCloud Guru

#### Amazon definition of VPC

  - Logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network you define.

  - Customize the network configuration of your VPC. Public and private facing subnets.

  - Hardware VPN to corporate data centers

  Can connect to a VPN using an internet gateway or Virtual Private Gateway:
    - Both gateways connect through the router, hit the route table, connect to the network access control list (ACL), check security groups for permissions then have access to the instances.

  Launch instances in the subnet of our choice
  Assign custom IP address ranges in each subnet
  Configure route tables between subnets
  Create internet gateway and attach it to our VPC
  Much better security control over your AWS resources (Subnet security, network ACLs, private subnets, security groups)

  What is the difference between a default VPC and custom?
    - Default is set up to your account allowing you to immediately deploy instances
    - All subnets in default VPC have a route out to the internet
    - Custom VPC with private subnet will not a public IP address by default

#### VPC Peering
   - Allow you to connect one VPC with another via a direct network route using private IP addresses
   - Instances behave as if they were on the same network
   - You can peer VPCs with other AWS accounts as well as with other VPCs on the same AWS accounts

#### VPC Exam Tips
  - Think of a VPC as a logical datacenter in AWS
  - Consists of Virtual Private Gateways, route tables, network access control lists, subnets and security groups
  - 1 subnet = 1 AZ
  - Security groups are stateful while NACLs are stateless (opening both inbound and outbound ports on the NACL is required)
  - No transitive peering

#### Network Access Control Lists (NACLs) and Security Groups (SGs)
  - NACLs can only be deployed into one VPC
  - NACLs - all traffic is denied on both inbound and outbound ports, SGs open outbound traffic on ports that are opened for inbound traffic
  - Ephemeral Ports
    - Port range from which port is selected when a client connects
  - Rules are evaluated in numerical order
  - NACLs are evaluated before security groups.
  - VPC automatically comes with default NACL that allows all outbound and inbound traffic
  - Each subnet must be associated with a NACL (defaults to default NACL)
  - Subnet can only be associated with one NACL at a time (applying a new NACL to subnet removes the previous NACL) however one NACL can have multiple subnets associated with it.
  - Allow ephemeral ports on outbound rules only

#### Load Balancers
  - Three types of LBs (application load balance, network load balancer and classic load balancer)
  - Use Network Load Balancers for static ips and/or ultra high performance
  - Selecting the VPC for the load balancer reveals the AZs the VPC exists within
  - The load balancer will balance traffic to your VPC across two or more subnets

#### VPC Flow Logs
  - Flow logs is a feature that enables you to capture network traffic to your VPC
  - Three levels: VPC, Subnet, Network Interface Level
  - Select VPC > Actions > Create Flow Log > Select Filter > Add Role (Log to Cloudwatch) > Set Destination Log Group (Cloudwatch > Create Log Group)
  - Can stream the logs to Lambda or Elasticsearch
  - Cannot enable flow logs from VPCs from a different account
  - No tagging

#### NAT vs Bastion Servers
  - NAT instance acts as a proxy to route internet traffic to our instances in private subnet
  - Bastions are used for administration access to instance in a private subnet
  - Lock down Bastion server to only your IP and SSH into your private subnet/instances through the Bastion server.
  - Bastions > NAT instances (Don't use NAT instances)
  - How do you make a Bastion instance highly available?
  - Use auto scaling group to relaunch bastion server if it goes down (ensure high availability for the bastion server)

#### VPC Endpoint
  - Creating and internal gateway to access S3 without reaching out to the internet
  - Attaching S3 role to an instance gives it access to S3 without going to the internet
  - VPC endpoint allows you to securely connect your VPC to another service. (AWS S3 Gateway)
  - VPC Endpoint uses AWS private network to access AWS services

## VPC Lesson Finale
  - NAT instances
    - Disable Source/Destination check on the instance
    - Must be in the public subnet
    - Must be a route out of the private subnet
    - Amount of traffic the instance supports depends on the size of the instance
    - Can create high availability using auto-scaling groups
    - Always behind a security groups
  - NAT Gateways
    - Preferred by enterprise
    - Scale to 10bps automatically
    - Not associated with SGs
    - Obtain public IP Automatically
    - Remember to update route tables
    - No need to disable Source/Destination checks
  - NACLS
    - VPC automatically comes with default NACL with traffic open
    - Can create custom NACL and all traffic is denied
    - Must open both inbound and outbound ports
    - Subnet can only have one NACL but NACL can be associated to multi subnets
  - ALBs
    - At least two public subnets to deploy an Application load balancer
    - Cannot peer VPCs from different accounts with an ALB
  - VPC Flow Log
    - Not all traffic is monitored:
       - Amazon DNS
       - Amazon windows license activation
       - Traffic to and from 169.254.169.254 (instance metadata)
       - DHCP traffic
       - Traffic to the reserved IP address for the default VPC router
  - VPC Endpoint
    - Connects the VPC to AWS services without reaching out to the internet
