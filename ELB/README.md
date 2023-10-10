## Scoring-Script
---
### ELB
### Select ELB Name Check
```
aws elbv2 describe-load-balancers --query "LoadBalancers[?LoadBalancerName=='<ELB Name>'].LoadBalancerName"
```

### Select ELB Scheme Type Check
```
aws elbv2 describe-load-balancers --query "LoadBalancers[?LoadBalancerName=='<ELB Name>'].Scheme"
```
### Select ELB Type Check
```
aws elbv2 describe-load-balancers --query "LoadBalancers[?LoadBalancerName=='<ELB Name>'].Type"
```

### Select ELB AZ Check
```
aws elbv2 describe-load-balancers --query "LoadBalancers[?LoadBalancerName=='<ELB Name>'].AvailabilityZones[].ZoneName"
```

### Select ELB DNS Check
```
aws elbv2 describe-load-balancers --names <ELB Name> --query "LoadBalancers[].DNSName"
```

### Select ELB Listener Protocol Check
```
alb_arn=$(aws elbv2 describe-load-balancers --query "LoadBalancers[?LoadBalancerName=='<ELB Name>'].LoadBalancerArn" --output text)

aws elbv2 describe-listeners --load-balancer-arn $alb_arn --query "Listeners[].Protocol"
```

### Select ELB Listener Port Check
```
alb_arn=$(aws elbv2 describe-load-balancers --query "LoadBalancers[?LoadBalancerName=='<ELB Name>'].LoadBalancerArn" --output text)

aws elbv2 describe-listeners --load-balancer-arn $alb_arn --query "Listeners[].Port"
```

### Select ELB Target Group Status Check
```
alb_tg_arn=$(aws elbv2 describe-target-groups --names <ELB Target Group Name> --query "TargetGroups[].TargetGroupArn" --output text)
aws elbv2 describe-target-health --target-group-arn $alb_tg_arn --query "TargetHealthDescriptions[].TargetHealth.State"
```

### Select ELB Target Group AZ Check
```
alb_tg_arn=$(aws elbv2 describe-target-groups --names wsi-ecs-tg --query "TargetGroups[].TargetGroupArn" --output text)

aws elbv2 describe-target-health --target-group-arn $alb_tg_arn --query "TargetHealthDescriptions[].Target.AvailabilityZone"
```