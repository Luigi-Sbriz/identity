# Identity Trust System
Everything related to the **identity trust system** is here included.

It is an **identity authentication system** that does not require federation of authentication domains. The main components are a symmetric authentication protocol and a specific infrastructure to ensure trust in the identity providers. The narrative was exposed in some my articles published on ISACA Journal (see [LS1], [LS2], [LS3], [LS4]). Regarding the components:
1. Symmetric authentication protocol - Both entities must make themselves known and are authenticated by their identity provider according to a symmetric scheme. This protocol builds on and extends the OAuth Authorization Framework [RFC6749].
2. Trustees’ network - A special network dedicated to creating a protected channel for exchanging authentication messages between IdPs constitutes the infrastructure to avoid domain federation.
3. Custodian concept - To better protect personal data IdPs are divided into two types. A generic IdP (trustee) for pure digital authentication and a specific IdP (custodian) under the control of the authority with legal right to the individual's real data, to guarantee physical identity.

Figure 1 shows a use case describing the components of the classic identity recognition method with asymmetry in the authentication process [RFC6749].

![Figure 1 Authorization Flow – Asymmetrical]("images/1 Asymmetric depiction.svg")  
Figure 1: Authorization Flow – Asymmetrical

Figure 2 shows a use case describing the components necessary to enable the identity authentication process in a symmetrical way that can operate in digital ecosystems other than your own.

![Figure 2 Authorization Flow – Symmetrical]("images/2 Symmetric depiction.svg")  
Figure 2: Authorization Flow – Symmetrical

The two representations are very similar to each other but it is noted that the symmetric protocol introduces direct communication between the identity providers' authentication servers to allow the circular transit of authentication messages. This direct communication between IdPs allows you to avoid trust between domains.
[//]: # (This may be the most platform independent comment)

# References

[LS1]: "https://www.isaca.org/resources/isaca-journal/issues/2022/volume-2/a-symmetrical-framework-for-the-exchange-of-identity-credentials-based-on-the-trust-paradigm-part-1"
    L. Sbriz,
      "A Symmetrical Framework for the Exchange of Identity Credentials Based on the Trust Paradigm, Part 1: Identity Trust Abstract Model",
      ISACA Journal, 2022-04, vol.2
  
[LS2]: "https://www.isaca.org/resources/isaca-journal/issues/2022/volume-2/a-symmetrical-framework-for-the-exchange-of-identity-credentials-based-on-the-trust-paradigm-part-2"
    L. Sbriz,
      "A Symmetrical Framework for the Exchange of Identity Credentials Based on the Trust Paradigm, Part 2: Identity Trust Service Implementation",
      ISACA Journal, 2022-04, vol.2
    
[LS3]: "https://www.isaca.org/resources/isaca-journal/issues/2023/volume-1/how-to-digitally-verify-human-identity"
    L. Sbriz,
      "How to Digitally Verify Human Identity: The Case of Voting",
      ISACA Journal, 2023-01, vol.1
    
[LS4]: "https://www.isaca.org/resources/isaca-journal/issues/2023/volume-6"
    L. Sbriz,
      "Modeling an Identity Trust System", ISACA Journal, 2023-11, vol.6
