## Error responses

If an API returns an error, the response body contains a [problem detail encoded in json](https://www.rfc-editor.org/rfc/rfc7807).
This section contains the structure of the used problem detail types.

### Problem detail object

Every problem detail type has the following properties:

```json-schema
{
  "type": "object",
  "children": {
    "type": {
      "type": "string",
      "required": true,
      "description": "See [RFC7807, Section 3.1.](https://www.rfc-editor.org/rfc/rfc7807#section-3.1) and [RFC7807, Section 4.2.](https://www.rfc-editor.org/rfc/rfc7807#section-4.2)",
      "example": "about:blank"
    },
    "title": {
      "type": "string",
      "required": true,
      "description": "See [RFC7807, Section 3.1.](https://www.rfc-editor.org/rfc/rfc7807#section-3.1)",
      "example": "Not Found"
    },
    "status": {
      "type": "number",
      "required": true,
      "description": "See [RFC7807, Section 3.1.](https://www.rfc-editor.org/rfc/rfc7807#section-3.1)",
      "example": 404
    },
    "detail": {
      "type": "string",
      "required": false,
      "description": "See [RFC7807, Section 3.1.](https://www.rfc-editor.org/rfc/rfc7807#section-3.1)",
      "example": "Could not find requested resource. Please check if the provided URI is correct."
    },
    "instance": {
      "type": "string",
      "required": false,
      "description": "See [RFC7807, Section 3.1.](https://www.rfc-editor.org/rfc/rfc7807#section-3.1)",
      "example": "https://retail-api.otto.de/products/d8d3d27e-ce16-4920-83dc-f5ee0791a5ab"
    }
  }
}
```

### Example problem detail object

```json
{
  "type": "about:blank",
  "title": "Forbidden",
  "status": 403,
  "detail": "You are not allowed to view account details of others.",
  "instance": "/account/12345/"
}
```
