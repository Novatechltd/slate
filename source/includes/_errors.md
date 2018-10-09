# Errors

> Any errors will be returned in the following JSON format:

```json
{
    "msg": "HTTP 415 Unsupported Media Type",
    "code": 415,
    "timestamp": "2018-10-09 10:09:17",
    "status": "Unsupported Media Type"
}
```

> If the error relates to JSON Objects failing validation i.e a field is too long or has an invalid quantity then the JSON will be structed like this:

```json
{
    "code": 400,
    "errors": [
        "deliverTo.name size must be between 5 and 30",
        "orderLineList[0].quantity must be greater than or equal to 1"
    ],
    "timestamp": "2018-10-09 10:13:19",
    "status": "Bad Request"
}
```

The Novatech API uses the following error codes:

Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your Token is invalid / expired / missing
404 | Not Found -- The URL is invalid, or the order / SKU you are attempting to look up does not exist
405 | Method Not Allowed -- You tried to access an endpoint with an invalid method.
415 | Unsupported Media Type -- You requested a format that isn't json.
500 | Internal Server Error -- We had a problem with our server. Try again later.
