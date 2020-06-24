# JSON Web Tokens (JWT)

- Well defined `JSON schema` or format to describe the tokens involved in a data exchange process
- Can be used to authenticate the request, without using OpenID and OAuth2.0
- `OpenID Connect` is an authentication layer on top of OAuth2.0 (an authorization framework)
- Contains information about issuer and recipient, along with the identity of the sender
- Tokens are assigned symmetric or assymetric keys which means that when a receiver trusts the issuer of the tocken, it can also trust the information inside it
- Components: Header, Payload, and Signature
- 