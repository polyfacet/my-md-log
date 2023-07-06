# SQL Deadlock in Aras
<div class='editDate'>Created/Updated: 2023-06-29</div>

> *Transaction (Process ID 51) was deadlocked on lock resources with another process and has been chosen as the deadlock victim. Rerun the transaction. in SQL: ...*

If you have ever encountered a message like in Aras I have seen two different solutions to this.

1. Wrap the code in "reruns".
2. Setting the database in snapshot mode

The former of this does not solve third party implementations and is in my opinion an ugly solution.

Setting the database in snapshot mode has in my experience been successful even though it was not recommended - for unspecified reasons - by Aras.

``` sql
ALTER DATABASE <database_name>
SET ALLOW_SNAPSHOT_ISOLATION ON 
```

``` sql
ALTER DATABASE <database_name>
SET READ_COMMITED_SNAPSHOT ON
GO
```

With the query

``` sql
SELECT name, snapshot_isolation_state_desc, is_read_committed_snapshot_on from sys.databases 
```

you can check that/if they are enabled or not.

More info about snapshot isolation  
<https://docs.microsoft.com/en-us/donet/framework/data/adonet/sql/snapshot-isolation-in-sql-server>
