## Scoring-Script
---
### VPC
### Select VPC CIDR
```
aws ec2 describe-vpcs --filter Name=tag:Name,Values=<VPC Name> --query "Vpcs[].CidrBlock"
```

<br>

### Select Subnet CIDR
```
aws ec2 describe-subnets --filter Name=tag:Name,Values=<Subnet Name> --query "Subnets[].CidrBlock"
```

<br>

### Select Subnet AZ
```
aws ec2 describe-subnets --filter Name=tag:Name,Values=<Subnet Name> --query "Subnets[].AvailabilityZone"
```

<br>

### Select Internet Gateway
```
aws ec2 describe-route-tables --filter Name=tag:Name,Values=<Route Table Name> --query "RouteTables[].Routes[].GatewayId"
```

<br>

### Select NAT Gateway
```
aws ec2 describe-route-tables --filter Name=tag:Name,Values=<Route Table Name> --query "RouteTables[].Routes[].NatGatewayId"
```