# OTTO RETAIL-API - Getting Started

## Introduction
The OTTO Retail-API uses standard [HTTP semantics](https://httpwg.org/http-core/draft-ietf-httpbis-semantics-latest.html) as well as OAuth 2.0 for authentication and authorization and returns [JSON-encoded](http://www.json.org/) responses.
We support secure communication and require client applications to implement TLS 1.2 or higher.

With this [endpoint](https://keycloak.apps.otto.de/sec-api/auth/realms/retailapi-prod/.well-known/openid-configuration) for [OAuth 2.0 endpoint discovery](https://tools.ietf.org/html/draft-ietf-oauth-discovery-06) 
you can use the returned information to obtain details about the OAuth 2.0 authorization server, such as endpoints for token and user information, as well as the supported OAuth 2.0 flows.

## Environments

In order to implement and test the OTTO Retail-API we offer a sandbox environment. Using this sandbox enviroment you can test your implementation without affecting or interacting with your live data.

The base URL for your requests determines whether the request is executed in the production or sandbox environment.

The following base URLs are available for all resources:

* Sandbox environment base URL: https://retail-api-sandbox.otto.de
* Production base URL: https://retail-api.otto.de

Please only use the production environment AFTER succesfully testing your implementation in the sandbox environment.

## Authentication

You can find the information about the authentication [here](01_authentication.md).

## Scopes

You can find the information about the different scopes we offer [here](02_scopes.md).


