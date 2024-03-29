# Deep munge

Rails will automatically do some magic to "clean" empty arrays and hashes from `params`.
This is to fix security holes caused by the unintentional generation of SQL queries with
`IS NULL` or `IN ('foo', NULL')`.

For example, all of the following JSON:

```javascript
{ "foo": [null] }
{ "foo": [null, null, ...] }
```

will be turned into this Ruby hash:

```ruby
{ foo: [] }
```

`null` values are also cleaned out of arrays. The following JSON:

```javascript
{ "foo": ["bar", null] }
```

is parsed to to:

```ruby
{ foo: ["bar"] }
```

Rails invokes a method called `deep_munge` to do this work. Further reading [here](https://guides.rubyonrails.org/security.html#unsafe-query-generation).
