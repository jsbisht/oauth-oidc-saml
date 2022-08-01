# OAuth-OIDC-SAML

## OAuth and OpenID Connect

Based on delegated authorizatiom

OAuth Terminalogy

- Resource Owner
- Client
- Authorisation Server (Knows the resource owner)
- Resource Server
- Redirect Uri
- Response Type (eg. code)
- Scope (Read Contact, Read Email)
- Consent
- Client ID
- Client Secret
- Authorization Grant 
	- Authorization Code
	- Client Credential
- Access Token
- Refresh Token

OpenID Connect (OIDC) Terminalogy

- Authorization
- Authentication
- Identity Provider
- Single SignOn
- ATM Card Analogy
- End User
- ID Token
- JWT & JWT Claims

Why do we need get Authorization Code and then Access Token?

- Front Channel
- Back Channel

Refer: https://youtu.be/996OiexHze0?t=1575

## OAuth 2.0 flow

The usual OAuth 2.0 grant flow looks like this:

Client requests authorization from the resource owner (usually the user).
If the user gives authorization, the client passes the authorization grant to the authorization server (in this case Okta).
If the grant is valid, the authorization server returns an access token, possibly alongside a refresh and/or ID token.
The client now uses that access token to access the resource server.

### Detailed flow

https://developer.okta.com/docs/guides/oin-oidc-protocols/main/




## OAuth Concepts



### Authorization Server

An authorization server is simply an OAuth 2.0 token minting engine. Each authorization server has a unique issuer URI and its own signing key for tokens to keep a proper boundary between security domains. In the context of this guide, Okta is your authorization server.

## OAuth 2.0 vs OpenID Connect

OAuth 2.0 enables you to delegate authorization, while OIDC enables you to retrieve and store authentication information about your end users.

OAuth 2.0 protocol provides API security through scoped access tokens.

OIDC extends OAuth 2.0 by providing user authentication and single sign-on (SSO) functionality.

## OpenID Connect Concepts
OpenID Connect is used to au
thenticate users with a web app. The app uses the ID token that is returned from the authorization server to know if a user is authenticated and to obtain profile information about the user, such as their username or locale.


### Outh and OpenID References

- [An Illustrated Guide to OAuth and OpenID Connect](https://www.youtube.com/watch?v=t18YB3xDfXI)
- [OAuth 2.0: An Overview](https://www.youtube.com/watch?v=CPbvxxslDTU)
- [OAuth 2.0 and OpenID Connect (in plain English)](https://www.youtube.com/watch?v=996OiexHze0)

## Okta

The type of OAuth 2.0 flow depends on what kind of client that you are building.

- If you are doing a redirect flow to an Okta-hosted sign-in page, the Authorization Code flow with PKCE is recommended. 
- If you want to embed the sign-in experience, the Interaction Code flow is recommended.
- If your client application is running on a server with no direct end user, then it can be trusted to handle credentials and use them responsibly. 
- If your client application is only doing machine-to-machine interaction, then you should use the Client Credentials flow.
- If you own both the client application and the resource that it's accessing, then your application can be trusted to handle your end user's username and password. These types of apps are considered "high-trust". Because of the high degree of trust required, you should only use the Resource Owner Password flow if other flows aren't viable.

### Authorization Code flow with PKCE

PKCE is an extension to the regular Authorization Code flow, so the flow is very similar, except that PKCE elements are included at various steps in the flow.

 PKCE was originally designed to protect the authorization code flow in mobile apps, but its ability to prevent authorization code injection makes it useful for every type of OAuth client, even web apps that use a client secret. 

 ![img](https://developer.okta.com/img/authorization/oauth-auth-code-pkce-grant-flow.png)
 

### Interaction Code flow

The Interaction Code flow is an extension to the OAuth 2 and OIDC standard, and is available when using Identity Engine orgs. It requires clients to pass a client ID, as well as a Proof Key for Code Exchange (PKCE), to keep the flow secure. The user can start the request with minimal information, relying on the client to facilitate the interactions with the Identity Engine component of the Okta Authorization Server to progressively authenticate the user.


![img](https://developer.okta.com/img/authorization/oauth_grant_flowchart.png)

- [Single Sign-On with Spring Boot & Okta | OAuth 2.0 | Java Techie](https://www.youtube.com/watch?v=yB9kEMx7fxE)

## SAML

Before OAuth SSO was done through SAML

