## Scoring-Script
---
### RDS
### Check RDS Name, CPU, DBMS, DBMS Version, User Name
```
aws rds describe-db-instances | jq '.DBInstances[0] | [{Name:.DBInstanceIdentifier, CPU: .DBInstanceClass, DBMS: .Engine, DBMS_ver: .EngineVersion},{Master: .MasterUsername, Vpc: .DBSubnetGroup.VpcId}]'
```

<br>

### RDS Subnet AZ Check
```
aws rds describe-db-instances | jq ".DBInstances[0].DBSubnetGroup.Subnets[] | {SubnetId: .SubnetIdentifier, AZ:.SubnetAvailabilityZone.Name}"
```

<br>

### Check RDS Multi Region
```
aws rds describe-db-instances | jq ".DBInstances[0].MultiAZ"
```

<br>

### Check DataBase Table Column
<!-- MySQL-->
```
mysql -h <RDS MySQL Writer Endpoint> -P <Port> -u <User Name> -p -skills123

desc <Table Name>;
```

<!-- PostgreSQL-->
```
psql --host=<RDS PostgreSQL Writer Endpoint> --port=<Port> --username=<User Name> --password --dbname=<DataBase Name>

desc <Table Name>
```