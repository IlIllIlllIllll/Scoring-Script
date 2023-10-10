## Scoring-Script
---
### Glue
### Check Glue Crawler Name
```
aws glue get-crawler --name <Glue Crawler Name> --query "Crawler.Name"
```

<br>

### Check Glue DataBase Name
```
aws glue get-database --name <Glue DB Name> --query "Database.Name"
```

<br>

### Check Glue Table Column
```
aws glue get-table --database-name <Glue DB Name> --name <Glue Table Name> --query "Table.StorageDescriptor.Columns[].Name"
```

<br>

### Check Glue Job Name
```
aws glue get-job --job-name <Glue Job Name> --query "Job.Name"
```

<br>

### Check Glue Workflow Resoruce
```
aws glue delete-table --database-name <Glue DB Name> --name <Glue Table Name>
aws glue start-workflow-run --name <Glue Workflow name>
aws glue get-table --database-name <Glue DB Name> --name <Glue Table Name> --query "Table.StorageDescriptor.Columns[].Name"
```