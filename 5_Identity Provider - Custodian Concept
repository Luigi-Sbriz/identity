# Identity Provider - Custodian Concept

The relationship between digital and physical identity should be managed only by a particular identity provider, called ***identity custodian (IdC)***, who has the legal authority to manage the personal data of the natural person. Only in this way it will be the perfect candidate to guarantee the identity provider the validity of the request for the release of a new digital identity, without having to disclose the physical identity to the IdP. Guaranteeing the digital identity of a user corresponding to a legal entity will not be the task of the identity custodian but of an authority or a process compliant with the law of the country to which the legal entity belongs. The identity token contains the indication between users of a natural person or a legal entity. The identity token makes it possible to distinguish the user of a natural or legal person and to know who has guaranteed the physical identity. An identity custodian can also act as an identity trustee, keeping roles distinct in communication protocols.

## General schema

The identity custodian certifies that it is a real identity that requires the digital identity but can also provide personal data to identity trustee with the consent of the data subject. The identity trustee provides the authentication service for its digital ecosystem. A use case describing the relationship between identity custodian, identity trustee, and digital identity is provided in figure 4. A SVG image is available [here](https://raw.githubusercontent.com/Luigi-Sbriz/identity/main/images/4_Identity-custodian-concept.svg).

    ............................              ............................
    : Real ecosystem X         :              :         Real ecosystem Y :
    :              ...................  ...................              :
    :              :Digital          :  :          Digital:              :
    :              :ecosystem A      :  :      ecosystem B:              :
    :              :  ┌───────────┐  :  :  ┌───────────┐  :              :
    :              :  │  Digital  │  :  :  │  Digital  │  :              :
    :      ┌──────────┤           ├────────┤           ├──────────┐      :
    :      │       :  │Identity A │  :  :  │Identity B │  :       │      :
    :      │       :  └─────┬─────┘  :  :  └─────┬─────┘  :       │      :
    :      │       :        │        :  :        │        :       │      :
    :      │       :        │        :  :        │        :       │      :
    :┌─────┴─────┐ :  ┌─────┴─────┐  :  :  ┌─────┴─────┐  : ┌─────┴─────┐:
    :│ Identity  │ :  │ Identity  │  :  :  │ Identity  │  : │ Identity  │:
    :│           ╞════╡           ╞════════╡           ╞════╡           │:
    :│Custodian X│ :  │Provider A │  :  :  │Provider B │  : │Custodian Y│:
    :└───────────┘ :  └───────────┘  :  :  └───────────┘  : └───────────┘:
    : Real         :                 :  :                 :         Real :
    : identity A   :.................:  :.................:   identity B :
    :                          :              :                          :
    :..........................:              :..........................:
    
    Figure 4: The Identity Custodian Use Case

Generally, identity provider must carry out the recognition and registration of the user's personal data before being able to guarantee its identity. The collection of the data of the natural person must be carried out in accordance with the protection provided for by the regulations in force. To ensure that the processing of personal data is restricted and controlled, it is useful to divide the set of IdPs into two categories. In the first, there will be IdPs (also called trustees) that only manage digital identity operations, and in the second, IdCs (identity custodians) that guarantee trustees that the applicant's identity is real. The IdC's category should operate under the responsibility of the legal authority that manages the real identity of the individual (i.e. who issues the identity card). 

Through the identity custodian, each individual can request the issuing of a new digital identity to their trusted IdP. It will be the trusted IdP who will ask for confirmation of the applicant's authenticity directly from the IdC. The applicant must send an ID token with their IdC contact information to initiate the request. The request will be managed entirely online and will not require any personal data from the data subject but, subject to consent, everything will be sent by the IdC. The new identity will be useful to meet the typical needs of transactions on the Internet, with the right confidentiality for the holder and an added value for the authority, being able to identify the real person. The digital legal identity to sign contracts should be managed directly by IdC.

In short the roles involved in the trust-based authentication system.
- The ***identity custodian*** is the guarantor of the existence of the natural person and has the ability to uniquely identify it but only following a formal request from the legitimate authority.  
- The ***identity provider*** receives the identification data that the data subject has decided to provide and will match these to the digital identity.  
- The ***service provider*** will have the guarantee that the user is linked to a real person for security, contractual or legal reasons.  
- The ***data subject*** can provide personal information according to their need, also maintaining anonymity.  
- The ***public authority*** that manages the real data will be able to identify the individual with certainty in case of violations of the law (i.e. to protect the service provider).

### Issuing of a New Digital Identity

The request for a new digital identity is activated by the natural person towards the chosen trustee. The trustee will request confirmation from the identity custodian if the request lawfully came from a real person. In case of confirmation, it will record the personal data that the data subject has authorized IdC to transfer. A use case describing the request of a new digital identity is provided in figure 5. A SVG image is available [here](https://raw.githubusercontent.com/Luigi-Sbriz/identity/main/images/5_New-identity-use-case.svg).

                      ┌───────────┐        ┌───────────┐
                      │Identity   │        │Identity   │
                      │           │        │           │
                      │Custodian  │        │Provider   │
                      └─────┬─────┘        └─────┬─────┘
                      IdC   │              IdP   │
                   ecosystem│           ecosystem│
                   .........│.........  .........│.........
                   :  ┌─────┴─────┐  :  :  ┌─────┴─────┐  :
                   :  │Authorizat.│  :  :  │Authorizat.│  :
                   :  │           ╞════════╡           │  :
                   :  │Server IdC │  :  :  │Server IdP │  :
                   :  └─────┬─────┘  :  :  └─────┬─────┘  :
                   :        │        :  :        │        :
                   :        │        :  :        │        :
    ┌───────────┐  :  ┌─────┴─────┐  :  :  ┌─────┴─────┐  :
    │Data       │  :  │User       │  :  :  │Relying    │  :
    │           ├─────┤           ├────────┤           │  :
    │Subject    │  :  │Agent      │  :  :  │Party  IdP │  :
    └───────────┘  :  └───────────┘  :  :  └───────────┘  :
                   :.................:  :.................:
    
    Figure 5: Abstract of New Digital Identity Request

Figure 6 shows the abstract representation of the message exchange sequence to request a new digital identity. A SVG image is available [here](https://raw.githubusercontent.com/Luigi-Sbriz/identity/main/images/6_New-identity-sequence-diagram.svg).

    ┌───────────┐      ┌───────────┐      ┌───────────┐      ┌───────────┐
    │Data       │      │User       │      │Authorizat.│      │Relying    │
    │           │      │           │      │           │      │           │
    │Subject    │      │Agent      │      │Server IdC │      │Party  IdP │
    └───────────┘      └─────┬─────┘      └─────┬─────┘      └─────┬─────┘
          |                  |                  |                  |
          ├-(1)-Request New->+-(2)--Send New Identity Request----->|
          |     Identity     |                  |                  |
          |                  |<--(3)--Return IdP Token-------------┘
          |                  |                  |
          |                  ├(4)--Request IdC  |
          |                  |     Token & Send |
          |                  |     IdP Token--->|
          |                  |                  |
          |<-(5)-Request Credentials via UA-----┤
          |                  |                  |
          └-(6)--Present Credentials via UA---->|
                             |                  |
                             └<--(7)--Return    |
                                      IdC Token-┘
    ┌───────────┐      ┌───────────┐      ┌───────────┐      ┌───────────┐
    │User       │      │Authorizat.│      │Authorizat.│      │Relying    │
    │           │      │           │      │           │      │           │
    │Agent      │      │Server IdC │      │Server IdP │      │Party  IdP │
    └─────┬─────┘      └─────┬─────┘      └─────┬─────┘      └─────┬─────┘
          |                  |                  |                  |
          ├-(8)--Request New Identity & Send IdC Token------------>|
          |                  |                  |                  |
          |                  |<--(10)--Send IdC |<--(9)--Send IdC  |
          |                  |         Token----┤        Token-----┤
          |                  |                  |                  |
          |                  ├-(11)--Return IdP |                  |
          |                  |     Token & Send |                  |
          |                  |     ID Token---->|                  |
          |                  |                  |                  |
          └<-(12)---Return   |                  └-(13)---Return    |
                    ID Token-┘                     Client Token--->┘
    ┌───────────┐                ┌───────────┐               ┌───────────┐
    │Data       │                │User       │               │Relying    │
    │           │                │           │               │           │
    │Subject    │                │Agent      │               │Party  IdP │
    └─────┬─────┘                └─────┬─────┘               └─────┬─────┘
          |                            |                           |
          └<-(15)------Return ID Token-┘<-(14)-Return Client Token-┘
    
    Figure 6: New Digital Identity Request - Sequence diagram

(1) - (3)	The ***data subject*** requests the new digital identity via the user agent to the identity provider. The ***UA*** activates the authentication process by requesting the new identity to the ***RP***, which responds by providing the IdP token (access token from IdP's AS).  
(4) - (7)	The ***UA*** requests the IdC token (access token from the custodian's AS) to its ***AS***, sending also the IdP token received from ***RP***. The custodian's ***AS*** requests credentials from the ***data subject*** and returns the IdC token to the ***UA***.  
(8) - (9)	The ***UA*** requests the new digital identity from the ***RP*** by sending the IdC token. Then, relying party requests to identity provider's AS to verify the IdC token.  
(10) - (11)	Both authentication servers must verify that the tokens received match the originals. If required by data subject, the custodian's AS will send an additional ID token with personal data.  
(12) - (13)	Custodian's AS informs the ***UA*** of the outcome and, if required, sends also a copy of the ID token. The identity provider's AS sends to the ***RP*** the client token (related the new identity provided by IdP).  
(14) - (15) The ***RP*** sends the client token to ***UA***, which then informs the ***data subject*** of the outcome and, if required, sends a readable copy of the ID token to check the personal information shared.

***Notes regarding some steps:***  
(3) If the relying party does not have the IdP token available, this will be requested from the authentication server after step (2).  
(4) IdC token does not contains any real identity information as default. If requested, an ID token with a standard set of real information can be included during this step.

Any new digital identity with legal value is issued according to the rules defined by the relevant authority. It is presumable that there is also physical recognition of the data subject before the provision of credentials but no reference model is defined in this document.
