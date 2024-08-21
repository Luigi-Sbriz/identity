# Conventions and Definitions

{::boilerplate bcp14-tagged}

Some terms are used with a precise meaning.

- "***resource owner***": 
An entity capable of granting access to a protected resource. When the resource owner is a person, it is also referred to as "***end user***", "***consumer***" or "***individual***". This is sometimes abbreviated as "***RO***".
- "***service provider***": 
An entity capable of managing access to a protected resource. It is generally a legal person. This is sometimes abbreviated as "***SP***".
- "***identity provider***": 
An entity capable of managing and recognizing the identity of registered entities. The set of all entities registered by the identity provider is also known as the IdP's digital ecosystem. This is sometimes abbreviated as "***IdP***".
- "***resource server***": 
The server hosting the protected resources, capable of accepting and responding to protected resource requests using access tokens. The resource server is often accessible via an API. This is sometimes abbreviated as "***RS***".
- "***client***", for software is also referred to as "***user agent***": 
An application making protected resource requests on behalf of the resource owner and with its authorization. The term "client" does not imply any particular implementation characteristics (e.g., whether the application executes on a server, a desktop, or other devices).
- "***relying party***": 
An application making protected resource authorization on behalf of the service provider and also managing its identity. The "relying party" acts as the "client" but on service provider side. This is sometimes abbreviated as "***RP***".
- "***authorization server***": 
The server issuing access tokens to the client after successfully authenticating the resource owner and obtaining authorization. This is sometimes abbreviated as "***AS***".
- "***access token***": 
The concept is the same of the [RFC6749], a tiny piece of code that contains the necessary authentication data, issued by the authorization server.
- "***identity token***" or "***ID token***": 
The structure is similar to access token but it is used as proof that the user has been authenticated. The ID token may have additional information about the user and, it is signed by the issuer with its private key. To verify the token, the issuer's public key is used.
- "***digital ecosystem***": 
Internet environment composed of all entities based on the same identity provider.

The detail of the information exchanged or protocols in the interactions between the authorization server and the requesting client, or between relying party and resource server, or the composition of tokens, is beyond the scope of this specification.
