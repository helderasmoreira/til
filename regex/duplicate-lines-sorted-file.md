# Remove duplicate lines in a sorted file

Easy way to find duplicate lines in a sorted file in perhaps in your editor of choice:

```regex
^(.*)(\n\1)+$
```

If you want to remove both, replace with nothing.
If you then want to just keep one of them, replace with `$1` and voilá.
