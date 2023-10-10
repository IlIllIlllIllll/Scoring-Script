## Scoring-Script
---
### ELB
### Check ELB Name
```
aws elbv2 describe-load-balancers --query "LoadBalancers[?LoadBalancerName=='<ELB Name>'].LoadBalancerName"
```

<br>

### Check ELB Scheme Type
```
aws elbv2 describe-load-balancers --query "LoadBalancers[?LoadBalancerName=='<ELB Name>'].Scheme"
```

<br>

### Check ELB Type
```
aws elbv2 describe-load-balancers --query "LoadBalancers[?LoadBalancerName=='<ELB Name>'].Type"
```

<br>

### Check ELB AZ
```
aws elbv2 describe-load-balancers --query "LoadBalancers[?LoadBalancerName=='<ELB Name>'].AvailabilityZones[].ZoneName"
```

<br>

### Check ELB DNS
```
aws elbv2 describe-load-balancers --names <ELB Name> --query "LoadBalancers[].DNSName"
```

<br>

### Check ELB Listener Protocol
```
alb_arn=$(aws elbv2 describe-load-balancers --query "LoadBalancers[?LoadBalancerName=='<ELB Name>'].LoadBalancerArn" --output text)

aws elbv2 describe-listeners --load-balancer-arn $alb_arn --query "Listeners[].Protocol"
```

<br>

### Check ELB Listener Port
```
alb_arn=$(aws elbv2 describe-load-balancers --query "LoadBalancers[?LoadBalancerName=='<ELB Name>'].LoadBalancerArn" --output text)

aws elbv2 describe-listeners --load-balancer-arn $alb_arn --query "Listeners[].Port"
```

<br>

### Check ELB Target Group Status
```
alb_tg_arn=$(aws elbv2 describe-target-groups --names <ELB Target Group Name> --query "TargetGroups[].TargetGroupArn" --output text)

aws elbv2 describe-target-health --target-group-arn $alb_tg_arn --query "TargetHealthDescriptions[].TargetHealth.State"
```

<br>

### Check ELB Target Group AZ
```
alb_tg_arn=$(aws elbv2 describe-target-groups --names wsi-ecs-tg --query "TargetGroups[].TargetGroupArn" --output text)

aws elbv2 describe-target-health --target-group-arn $alb_tg_arn --query "TargetHealthDescriptions[].Target.AvailabilityZone"
```