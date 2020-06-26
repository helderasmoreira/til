# Rails will perform caching on **all** SQL queries

Despite MySQL specifically [not caching some queries](https://dev.mysql.com/doc/refman/5.7/en/query-cache-operation.html) (queries include some functions such as `NOW()`, `UUID()` or `RAND()`)
 Rails will not care about this and will [cache](https://guides.rubyonrails.org/caching_with_rails.html#sql-caching) all queries.

 This means that one needs to be careful when running queries with these functions more than once in the scope of a controller action.

 One can workardound it by specifically avoiding the SQL cache for a specific query: `User.uncached { User.all }`. Other, worse, workarounds could be executing the query manually using the connection or invalidating the SQL cache manually for the action.
