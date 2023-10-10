## Scoring-Script
---
### EC2
### Select EC2 Instance ID
```
aws ec2 describe-instances --filter Name=tag:Name,Values=<EC2 Name> --query "Reservations[].Instances[].InstanceId"
```

<br>

### Select EC2 Elastic IP
```
aws ec2 describe-instances --filter Name=tag:Name,Values=<EC2 Name> --query "Reservations[].Instances[].PublicIpAddress"

aws ec2 describe-addresses --query "Addresses[].PublicIp"
```

<br>

### Select EC2 Binding SSH Port
```
sudo netstat -lnp | grep ssh
```