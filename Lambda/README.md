## Scoring-Script
---
### Lambda
### Check Lambda Function Name
```
aws lambda list-functions --query 'Functions[*].FunctionName' --region <Region>
```

### Check Lambda Function Handler Name
```
aws lambda get-function --function-name <Lambda Name> --region <Region> | jq .Config uration.Handler
```

### Check Lambda Function RumTime 
```
aws lambda get-function --function-name <Lambda Name> --region <Region> | jq .Configuration.Runtime
```