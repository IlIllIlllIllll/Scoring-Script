## Scoring-Script
---
### CodeDeploy
### Check CodeDeploy Application Name
``` 
aws deploy get-application --application-name <CodeDeplyo App Name> --query "application.applicationName"
```
<br>

### Check CodeDeploy Application Type
```
aws deploy get-application --application-name <CodeDeplyo App Name> --query application.computePlatform
```

<br>

### Check CodeDeploy Type
```
aws deploy get-deployment-group --application-name <CodeDeploy App Name> --deployment-group-name <Deployment Group Name> --query deploymentGroupInfo.deploymentStyle.deploymentType
```

<br>

### Checl CodeDeploy ECS Check
```
aws deploy get-deployment-group --application-name <CodeDeploy App Name> --deployment-group-name <Deployment Group Name> --query deploymentGroupInfo.ecsServices
```

<br>

### Check CodeDeploy Target Group Name
```
aws deploy get-deployment-group --application-name <CodeDeploy App Name> --deployment-group-name <Deployment Group Name> --query "deploymentGroupInfo.loadBalancerInfo.targetGroupPairInfoList[].targetGroups[]"
```