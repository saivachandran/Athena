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

# Display any console logins over the last 24 hours
```
SELECT useridentity.username, sourceipaddress, eventtime, additionaleventdata
FROM your_athena_tablename 
WHERE eventname = 'ConsoleLogin'
and eventtime >= '2017-02-17T00:00:00Z'
and eventtime < '2017-02-18T00:00:00Z';
```

# Display any failed console sign-in attempts over the last 24 hours

SELECT useridentity.username, sourceipaddress, eventtime, additionaleventdata
FROM your_athena_tablename
WHERE eventname = 'ConsoleLogin'
and useridentity.username = 'HIDDEN_DUE_TO_SECURITY_REASONS'
and eventtime >= '2017-02-17T00:00:00Z'
and eventtime < '2017-02-18T00:00:00Z';








