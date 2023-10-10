## Scoring-Script
---
### CloudFormation
### Check Subnet Name Tag - Text : CloudFormation
```
aws ec2 describe-subnets --filter Name=tag:Name,Values=<Subnet Name> --query "Subnets[].Tags[]"
```

<br>

### Deploy CloudFormation Stack
```
aws cloudformation deploy --template-file '<Tempalte Path>' --stack-name <Stack Name>
```

<br>

### Check Subnet Name Tag - <aws:cloudformation>:<Stack ID>
```
aws ec2 describe-subnets --filter Name=tag:Name,Values=<Subnet Name> --query "Subnets[].Tags[]"
```