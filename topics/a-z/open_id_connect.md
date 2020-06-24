# OpenID Connect

- Identity layer on top of OAuth2.0 protocol so flows are same
- Allows clients to verify end users, based on authentication that was performed by an authorization server
- Used to obtain basic profile information about the end user
- Defines a standardized identity token referred as `ID token`
- Identity token is sent to application, so that it can validate who the user is.
- Defines the endpoint to get identity information for that user, such as name or email address
- It can be used with authorization code grant and implict grant
- 