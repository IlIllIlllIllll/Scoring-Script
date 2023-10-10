## Scoring-Script
---
### ECS
### Select ECS Cluster Name
```
aws ecs describe-clusters --cluster <ECS Cluster Name> --query "clusters[].clusterName"
```

<br>

### Select ECS Cluster Type
```
aws ecs describe-clusters --cluster <ECS Cluster Name> --query "clusters[].capacityProviders"
```

<br>

### Select ECS Taskdefinition Binding Port Check
```
aws ecs describe-task-definition --task-definition <ECS Taskdefinition Name> --query "taskDefinition.containerDefinitions[].portMappings[].containerPort"
```

<br>

### Select ECS Taskdefinition Image Name Check
```
aws ecs describe-task-definition --task-definition <ECS Taskdefinition Name> --query "taskDefinition.containerDefinitions[].image"
```

<br>

### Select ECS Container Disabled Public IP Check
```
aws ecs describe-services --cluster <ECS Cluster Name> --services <ECS Service Name> --query "services[].networkConfiguration.awsvpcConfiguration.assignPublicIp"
```

<br>

### Select ECS Service Type Check
```
aws ecs describe-services --cluster <ECS Cluster Name> --services <ECS Service Name> --query "services[].launchType"
```

<br>

### Select ECS Service Status Check
```
aws ecs describe-services --cluster <ECS Cluster Name> --services <ECS Service Name> --query "services[].status"
```

<br>

### Select Count ECS Contaienr
```
aws ecs describe-clusters --cluster <ECS Cluster Name> --query "clusters[].runningTasksCount"
```

<br>

### Select ECS Count Service Subnet Check
```
aws ecs describe-services --cluster <ECS Cluster Name> --services <ECS Service Name> --query "services[].networkConfiguration.awsvpcConfiguration[].subnets[]"
```

<br>

### Select ECS Service Security Group Source IP Check
```
aws elbv2 describe-load-balancers --query "LoadBalancers[].SecurityGroups[]"

aws ec2 describe-security-groups --query "SecurityGroups[?GroupName=='<ECS Security Group Name>'].IpPermissions[].UserIdGroupPairs[].GroupId"
```