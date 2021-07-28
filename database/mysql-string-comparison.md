# MySQL does case insensitive string comparison by default

By default, MySQL string comparison is case-insensitive.

To force case-sensitive comparison, use `BINARY`:

```sql
SELECT * FROM posts where BINARY title = 'SenSiTIVe sTrInG';
```

See [the documentation](https://dev.mysql.com/doc/refman/8.0/en/cast-functions.html#operator_binary).
