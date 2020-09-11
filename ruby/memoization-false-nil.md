# Memoization can be tricky when `false` or `nil`

When using memoization (`||=`) one needs to be careful about methods that can return `false` or `nil`.

Since both these values are `falsey`, the right hand side expression of the memoization will always be executed.
This can be particularly tricky if you're using memoization in combination with, let's say, `ActiveRecord` to do something like this:

```ruby
def user
  @user ||= User.find_by(...)
end
```

The (potentially expensive) query will run every time until a user is found.

Another example with `false` this time:

```ruby
def exists
  @exists ||= User.exists(...)
end
```

Same problem.

To sum up, `||=` is too good to forget about it, but when doing memoization, just think if the result may be boolean (`false` particularly) or `nil`, and if yes, use `defined?` instead.

```ruby
def user
  return @user if defined?(@user)

  @user = User.find_by(...)
end
```
