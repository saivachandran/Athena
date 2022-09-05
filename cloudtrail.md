# create table 

[Athena table creation ](https://docs.aws.amazon.com/athena/latest/ug/cloudtrail-logs.html)

# view user all api acivity
```
SELECT * FROM  yout-table-name WHERE useridentity.type  = 'IAMUser' AND useridentity.username LIKE 'username';
```

# Display all recorded AWS API activity for a specific access key
```
SELECT eventTime, eventName, userIdentity.principalId
FROM your_athena_tablename 
WHERE userIdentity.accessKeyId like 'access_key_id'
```




