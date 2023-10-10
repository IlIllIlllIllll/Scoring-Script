## Scoring-Script
---
### S3
### Check S3 Bucket File Name
```
aws s3api list-buckets --query “Buckets[],Name”
```

