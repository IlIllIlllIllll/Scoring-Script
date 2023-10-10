## Scoring-Script
---
### CodePipeline
### Check CodePipeline Name
```
aws codepipeline list-pipelines --query "pipelines[].name"
```

<br>

### Check Pipeline Stage
```
aws codepipeline get-pipeline --name <CodePipeline Name> --query "pipeline.stages[0].actions[].configuration.RepositoryName"
```