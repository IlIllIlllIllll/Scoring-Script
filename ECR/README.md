## Scoring-Script
---
### ECR
### Select ECR Name
```
aws ecr describe-repositories --repository-name <ECR Name> --query "repositories[].repositoryName"
```

### Select ECR Image Name
```
aws ecr list-images --repository-name <ECR Name> --query "imageIds[].imageTag"
```

### Select ECR Image Scanning Status
```
aws ecr describe-image-scan-findings --repository-name <ECR Name> --image-id imageTag=latest --query "imageScanFindings.findingSeverityCounts"
```