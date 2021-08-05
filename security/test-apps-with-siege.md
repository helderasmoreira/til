[`Siege`](https://www.joedog.org/siege-home/) is an HTTP load testing and benchmarking utility. It was designed to let web developers measure their code under duress, to see how it will stand up to load on the internet. Siege supports basic authentication, cookies, HTTP, HTTPS and FTP protocols. It lets its user hit a server with a configurable number of simulated clients. Those clients place the server “under siege.”

Be sure to check it out the next time you wonder how your website or your API might behave under stress or under race conditions.

Quick example:

The following command will create 50 concurrent connections and POST plain text data to the URL specified:

```bash
siege --concurrent=50 --content-type="text/plain" 'http://example.com/api POST plain-text-content-here'
```

If your API accepts JSON instead of plain text, use the following command instead:

```bash
siege --concurrent=50 --content-type="application/json" 'http://example.com/api POST {"key1":"value1","key2":"value2"}'
```

You can stop the command at any time and it will output a report.
Alternatively, specify a time to run the test with the `--time` command line switch.
