### Here is the network design:

![Network design](image/Diagram.jpg)

### List of all assumptions for the design:

- **Route 53** 
- **Regions & AZ**
- **Load Balancer**
- **S3/CDN**
- **VPC**
- ***Internet Gateway**
- **NAT**
- **Subnets**
- **Security Groups**
- **VPN/Jump box/SSH** 

### summary 

**project details** 
This project is design for a real estate company. It is design like it can take data/inputs from 3rd party in a secure way. Depelopers can work smothly via SSH and users can access from the interenet. This application deploy in 2 different regions and each regions have 2 diffent available zones. So the application serve their service smothly even in any disester.

**architecture decisions**
In this project I use route 53 for control the trafics from internet and send them to the closer region. and I kept frontend in s3/CDN for better serve although it is a public app and security here is 0. I create a VPC and 2 subnets for separate backend and Database/caches from internet and keep them  isolated from each other. then set security rules to prevent unwanted access and keep them in control communications. I use Nat and IG for access the internets safely.

**reasoning and networking components used and their use case**
- **Route 53**: For routing users to appropriate destination 
- **Regions & AZ**: For apply application in different regions and AZ for better performance and keep live the system even in disester
- **Load Balancer**: It will help the system auto scalling
- **S3/CDN**: For better and fast static files serve
- **VPC**: For secure the system we need VPC, it will protect trafic from internet
- ***Internet Gateway**: For access the system to internet 
- **NAT**: This will allow a subnet to get trafic from internet. it is network address translator.
- **Subnets**: In VPC we need to separete our vital system from others. It will separate systems in VPC
- **Security Groups**: For allow/deny what exactly need in networks, instances
- **VPN/Jump box/SSH** For allow developers to work their developement inside networks, system
