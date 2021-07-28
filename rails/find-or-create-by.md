# Find or create with additional attributes

You can use `find_or_create_by` to find a resource and, if not found, create one with additional attributes.

```ruby
User.find_or_create_by(first_name: 'John') do |user|
  user.last_name = 'Doe'
end
```

This will find a user with `first_name = Joe` and if it doesn't find one will create a user also setting the last name to `Doe`. I've been using this for a while but was quite pleased and surprised when I found it so decided it would warrant a TIL snippet.
