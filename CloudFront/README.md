## Scoring-Script
---
### CloudFront
### Select CloudFront Name Check
```
aws cloudfront list-distributions --query "DistributionList.Items[].Id"
```

### Select CloudFront Origin Name Check
```
aws cloudfront list-distributions --query "DistributionList.Items[].Origins.Items[]" | jq ".[].DomainName" | grep <Service Name>
```

### Select CloudFront Deploy Price Class Check
```
cloudfront_id=$(aws cloudfront list-distributions --query "DistributionList.Items[].Id" --output text)

aws cloudfront get-distribution-config --id $cloudfront_id --query "DistributionConfig.PriceClass" --output text
```
> CloudFront Deploy Price Class -  https://docs.aws.amazon.com/ko_kr/AmazonCloudFront/latest/DeveloperGuide/PriceClass.html

### Select CloudFront Domain Name Check
```
aws cloudfront list-distributions --query "DistributionList.Items[].DomainName"
```

### Select CloudFront Header Check
```
cloudfront_url=$(aws cloudfront list-distributions --query "DistributionList.Items[].DomainName" --output text)

curl -I -s $cloudfront_url | grep X-Cache
```