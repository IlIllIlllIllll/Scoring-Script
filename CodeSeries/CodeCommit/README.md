## Scoring-Script
---
### CodeCommit
### Check CodeCommit Name
```
aws codecommit list-repositories
```

<br>

### Check CodeCommit Branch Name
```
aws codecommit get-branch --repository-name wsi-repo --branch-name master --query branch.branchName
```