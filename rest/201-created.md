# 201 Created should respond just with an header

The `201 Created` status code indicates that the request has been fulfilled and has resulted in one or more new resources being created.

An appropriate payload on such a response would be to include a `Location` header that would include the URL where one could find the newly created resource. This is a better approach than returning the resource in the body for instance.
