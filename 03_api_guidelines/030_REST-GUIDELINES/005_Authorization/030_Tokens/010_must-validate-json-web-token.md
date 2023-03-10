---
type: MUST
id: R000050
---

# validate JSON Web Token

Each endpoint must validate the JWT that the API client has passed along as the access token for its request.

This includes:

- the cryptographic signature of the token
- the expiration date of the token
- the scopes encoded in the token (if they match the endpoint)
- that the subject (`sub`-claim) has sufficient rights to access a user-specific resource. This is especially important for tokens that have been granted using the OAuth 2.0 authorization code flow.

If either of these are not valid the request is to be denied with an appropriate [status code](../../010_HTTP/030_Status-codes/000_index.md) and [error message](../../040_Errors/010_Error-handling/000_index.md).
