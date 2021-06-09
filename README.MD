# Simple JS Application based on keycloak JavaScript adapter

# Steps
- Create or use existing 3scale application with Openid Connect Integration
- Add CORS policy (first in chain) in 3Scale; Allow CORS requests from http://localhost:8080
- Configure Openid Connect Client
 - Set Access Type of the OIDC client to public
 - Set callback URL to http://localhost:8080
 - Set "Advanced Settings" > "Proof Key for Code Exchange Code Challenge Method" to "S256"
 - Set correct values in keycloak.json
- Start server
```
$ npm install http-server -g
$ http-server
```
- Browse to http://localhost:8080
- Try "Call Test API (Hello Service)" before and after login

> Caution: Do not use regenerate client secret in 3scale, as it removes the callback url of the client

# Reference
1. https://github.com/keycloak/keycloak/tree/master/examples/js-console
