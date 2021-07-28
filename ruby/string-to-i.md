# Converting strings to integers is tricky business

Ruby strings evaluate to zero, unless they start with a number.

```ruby
> 'nine to five'.to_i
 => 0
> '9 to 5'.to_i
 => 9
```
