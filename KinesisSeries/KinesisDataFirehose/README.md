## Scoring-Script
---
### Kinesis Data Firehose
### Check Kinesis Data Firehose Name
```
aws firehose describe-delivery-stream --delivery-stream-name <KDF Name> --query "DeliveryStreamDescription.DeliveryStreamName"
```

<br>

### Check Kiensis Data Firehose Source
```
aws firehose describe-delivery-stream --delivery-stream-name <KDF Name> --query "DeliveryStreamDescription.DeliveryStreamType"
```

<br>

### Check Kinesis Data Firehose S3 Bucket
```
aws firehose describe-delivery-stream --delivery-stream-name <KDF Name> --query "DeliveryStreamDescription.Destinations[].S3DestinationDescription.BucketARN"
```

<br>

### Check Kinesis Data Firehose Save S3 Path
```
aws firehose describe-delivery-stream --delivery-stream-name <KDF Name> --query "DeliveryStreamDescription.Destinations[].S3DestinationDescription.Prefix"
```