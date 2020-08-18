# MySQL does not support partial indexes

MySQL as of version 8.0 does not support partial indexes - an index to filter a specific range or subset of the table.

This functionality would be called a [filtered index](https://docs.microsoft.com/en-us/sql/relational-databases/indexes/create-filtered-indexes?redirectedfrom=MSDN&view=sql-server-ver15) in SQL Server and a [partial index](https://www.postgresql.org/docs/current/indexes-partial.html) in Postgres.

One way to work around this is to "partition" the table based on the given condition and use an auxiliary table to store the records, only indexing in one of the tables.
