# Symmetric authentication protocol

The symmetric authentication flow is conceptually not too dissimilar from the classic one referring to the single ecosystem [RFC5234], except that the authentication is dual because the two flows reflect the same operations symmetrically. Both the **client** (*resource owner*) and the **server** (*service provider*) MUST authenticate their identity through their IdP. The details of each basic operation in the symmetric process are the same as the corresponding single ecosystem specification [RFC6749] and MUST maintain alignment with it over time.

The authentication sequence between a consumer and a resource provider operating in different environments will be:

***1.*** Entities exchange the access tokens received from their authentication server with each other.  
***2.*** Entities send the received token to their authentication server.  
***3.*** Authentication servers exchange access tokens with each other.  
***4.*** Authentication servers verify tokens with their original.  
***5.*** Authentication servers send the result to their own entity.  
***6.*** Entities are authenticated and can now exchange information.

Conceptually, in a client-server schema, the authentication process begins with the resource owner requesting access to the protected resource to the service provider. Both respond with their access tokens and request their IdP to validate the received token. The IdPs exchange tokens for validation and send the result to their entity. On success, access to the resource is allowed.

Figure 3 shows the abstract depiction of the symmetric authentication sequence. A SVG image is available [here](https://raw.githubusercontent.com/Luigi-Sbriz/identity/main/images/3_Symmetric-sequence-diagram.svg).

![Figure 3 Symmetric Authentication Protocol - Sequence diagram](images/3_Symmetric-sequence-diagram.svg)  
***Figure 3***: Symmetric Authentication Protocol - Sequence diagram

(1) - (2)	The ***RP*** requests authentication to its ***AS*** (marked "S" as server) and receives the server token (access token from the service provider's AS). The relying party must be provided with its own access token to resolve multiple requests.  
(3) - (5)	The ***RO*** requests access to the protected resource via the user agent. The ***UA*** activates the authentication process by requesting access to the ***RP***, which responds by providing the server token. The response may also include the server ID token.  
(6) - (9)	The ***UA*** requests the client token (access token from the client's AS) to its ***AS*** (marked "C" as client), sending also the server token received from ***RP***. The client's ***AS*** requests credentials from the ***RO*** and returns the client token to the ***UA***.  
(10) - (11)	The ***UA*** requests the protected resource from the ***RP*** by sending the client token. Then, relying party requests to service provider's AS to verify the client token.  
(12) - (15)	Both authentication servers must verify that the tokens received match the originals. Then, client's AS informs the ***UA*** of the outcome and the same is done by the service provider's AS to the ***RP***. The outcome sent to the relying party may also include the client ID token.  
(16) - (17)	The ***RP*** notifies the ***RS*** of the legitimate request of '***UA***. The ***RS*** returns the protected resource to ***RP***.  
(18) - (19) The ***RP*** sends the protected resource to ***UA***, which then presents it to the requester ***RO***.

***Notes regarding some steps:***  
(4) If the server token is not available at this time, sequence (1) - (2) will be executed between steps (4) and (5) to provide the server token. Additionally, this change may also be necessary for a periodic refresh of the server token or if the entities are both clients.  
(6) The client's authorization could be performed in advance and the client token stored securely by the user agent for handling multiple authentication requests. This means performing only the server token communication here, avoiding the following steps (7) - (9) because already done.

The verification of the authenticity of the tokens is carried out by the IdPs who exchange messages on a dedicated network to reduce the risk of intrusion. Security is strengthened by the presence of two interfaces for the exchange of tokens, one is for the party in trust and the other is for the opposing party. If one is compromised, the other interrupts the flow avoiding authorization. The trust placed in the mutual validation of messages avoids having to merge authentication domains, leaving great flexibility to the system as a whole.

Identity recognition information resides only with a trusted identity provider. This reduces the need to store too much personal information in Internet registrations. Furthermore, to easily identify which IdP holds the entity's authentication credentials, it can be easily extracted from the username structure if this is defined following the same technique used to compose an email address [RFC5322], that means an username, an @ sign, and a domain name.
