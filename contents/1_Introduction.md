# Introduction

The typical model of access to Internet protected resources requires that the identity of the user, i.e. the ***resource owner***, be authenticated by the resource manager, i.e. the ***service provider***. The authentication process is not the primary task of the service provider and therefore can be entrusted to a third party shared between the user and the service provider, known as an ***identity provider***. A popular authentication mechanism is defined by [RFC6749].

This mechanism is asymmetric, only the resource owner must be recognized but not vice versa. Furthermore, the digital identity has value only within the digital ecosystem of the identity provider, i.e. its authentication domain or in a set of domains in a relationship of trust between them. It follows that when the digital ecosystem changes, the resource owner needs a new user to be recognized in the new digital environment. Instead, with a symmetric authentication scheme, the new user is no longer necessary. Moreover, it is not even necessary to create a trust relationship between domains. Trust is assigned only to the entity that guarantees identity authentication process, i.e. the identity provider that guarantees the inviolability and truthfulness of the authentication messages exchanged.

The concept used to build symmetric authentication is the request for equal dignity in recognition, i.e. each entity must be recognized by the other. To achieve this equal relationship, an identity recognition process based on a mirrored sequence of messages exchanged is necessary. Consequently, basing this symmetric process on the trust assigned to the identity provider has a great advantage, it is no longer necessary to define a specific trust between domains or create new users to be able to operate in an ecosystem different from that of belonging.

To implement this solution it is necessary to modify the authentication protocol to support the symmetric exchange of identification messages, and also implement a similar message exchange mechanism between identity providers. For security reasons, an infrastructure dedicated to identity providers is required. Furthermore, dividing IdPs into two categories reduces the amount of personal data used in registrations. The first category will be made up of those who are only authorized to recognize digital identity. The second category consists of those with the legal authority to also manage the real identity. The second category will act as a guarantor of the authenticity of the identity used in registration on the providers of the first category.

## Use cases of both authentication schemes

Figure 1 depicts the use case of the classic identity recognition method with asymmetry in the process of exchanging authentication messages [RFC6749]. A SVG image is available [here](https://raw.githubusercontent.com/Luigi-Sbriz/identity/main/images/1_Asymmetric-depiction.svg). The scenario depicted represents a resource owner who needs to retrieve a resource from the service provider. The identity provider MUST verify the identity of the resource owner before accessing the resource server. The relying party who manages the resource does not provide any information about its identity, it provides the resource only to authorized requests.

                      ┌───────────┐
                      │Identity   │
                      │           │
                      │Provider   │
                      └─────┬─────┘
                    Digital │ecosystem
                   .........│..............................
                   :  ┌─────┴─────┐                       :
                   :  │Authorizati│                       :
                   :  │           ├──────────────┐        :
                   :  │on Server  │              │        :
                   :  └─────┬─────┘              │        :
                   :        │                    │        :
    ┌───────────┐  :  ┌─────┴─────┐        ┌─────┴─────┐  :  ┌───────────┐
    │Resource   │  :  │User       │        │Relying    │  :  │Service    │
    │           ├─────┤           ├────────┤           ├─────┤           │
    │Owner      │  :  │Agent      │        │Party      │  :  │Provider   │
    └───────────┘  :  └───────────┘        └─────┬─────┘  :  └───────────┘
                   :                             │        :
                   :                       ┌─────┴─────┐  :
                   :                       │Resource   │  :
                   :                       │           │  :
                   :                       │Server     │  :
                   :                       └───────────┘  :
                   :......................................:
    
    Figure 1: Use case of the authorization flow - Asymmetrical Case

Figure 2 depicts the use case with the components needed to enable the identity authentication process in a symmetric manner capable of operating in different digital ecosystems. A SVG image is available [here](https://raw.githubusercontent.com/Luigi-Sbriz/identity/main/images/2_Symmetric-depiction.svg). The new scenario depicts two different ecosystems, one for the resource owner (client accessing the resource) and the other for the service provider (server managing the resource). This means that any entity involved in the authentication process will have its own identity provider, and they will interact with each other to ensure the completion of the symmetric authentication process.

                      ┌───────────┐        ┌───────────┐
                      │Identity   │        │Identity   │
                      │           │        │           │
                      │Provider C │        │Provider S │
                      └─────┬─────┘        └─────┬─────┘
                    Digital │ecosystem   Digital │ecosystem
                            │C                   │S
                   .........│.........  .........│.........
                   :  ┌─────┴─────┐  :  :  ┌─────┴─────┐  :
                   :  │Authorizati│  :  :  │Authorizati│  :
                   :  │           ╞════════╡           │  :
                   :  │on Server C│  :  :  │on Server S│  :
                   :  └─────┬─────┘  :  :  └─────┬─────┘  :
                   :        │        :  :        │        :
    ┌───────────┐  :  ┌─────┴─────┐  :  :  ┌─────┴─────┐  :  ┌───────────┐
    │Resource   │  :  │User       │  :  :  │Relying    │  :  │Service    │
    │           ├─────┤           ├────────┤           ├─────┤           │
    │Owner      │  :  │Agent      │  :  :  │Party      │  :  │Provider   │
    └───────────┘  :  └───────────┘  :  :  └─────┬─────┘  :  └───────────┘
                   :                 :  :        │        :
                   :                 :  :  ┌─────┴─────┐  :
                   :                 :  :  │Resource   │  :
                   :                 :  :  │           │  :
                   :                 :  :  │Server     │  :
                   :                 :  :  └───────────┘  :
                   :.................:  :.................:
    
    Figure 2: Use case of the authorization flow - Symmetrical Case

The two representations are very similar to each other but note that the symmetric protocol requires direct communication between the identity providers' authentication servers to allow the circular transit of authentication messages. Therefore, no trust between domains or new users is necessary. This idea was first exposed in some articles published on ISACA Journal (see [LS1], [LS2], [LS3], [LS4]) with some specific use cases and examples of potential implementations.
