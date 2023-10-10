## Scoring-Script
---
### Kinesis Data Stream
### Check Kinesis Data Stream Name
```
aws kinesis describe-stream --stream-name <KDS Name> --query "StreamDescription.StreamName"
```

<br>

### Check Shard Count
```
aws kinesis list-shards --stream-name <KDS Name> --query "Shard[].Sharld" | wc -l
```