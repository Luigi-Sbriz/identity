# Security Considerations

There are some cautionary points regarding security that need to be considered.
- Integrity and resilience are the most critical parameters. The integrity of the messages is fundamental to guarantee the authenticity of the identity, while the availability of the authentication service is the basis for ensuring the feasibility of the entire process.
- Symmetric authentication contrast the risk of man-in-the-middle attack because it should successfully attack both message flows at the same time.
- The trustee is a critical component and must be subjected to rigorous checks on compliance with the standards.
- The relying party and the resourse server should be on different servers using a dedicated communication channel.

Referring to the term identification, we mean at least three different types, the device, the digital user and the individual.

- The ***device*** is identified with technical methods suited to the various needs. For example, geolocalization using International Mobile Equipment Identity (IMEI) [ITU1] and Integrated Circuit Card ID (ICCID) [ITU2].
- The ***digital user*** is well managed by [RFC6749] but inside the digital ecosystem. To manage users of multiple domains, either the user registrations are duplicated for each domain involved, or the domains involved are joined in a trust relationship.
- The ***individual***, or natural person, is well managed with classic physical methods (e.g. photo ID) but the link with the digital identity needs to be improved because the quality is not satisfactory. This topic is beyond the scope of this specification and it was explored for example in [LS3].

An in-depth defense system SHOULD consider all the components involved and in this case not just the pure digital authentication of the user. In this document only the digital user is treated but extensions applicable to mixed situations with multiple types are certainly welcome to improve the overall security profile.

## User registration

It is important to control the amount of data exchanged during the authentication process but also that the data required to issue a new digital identity are the only ones strictly necessary. To assign access credentials to a protected resource to a user, a process of recording the user's identification and contact data is necessary, as they are necessary for the authentication of the digital identity and for the attribution of access rights to the resource. Data provided or exchanged with IdPs MUST comply with the need-to-know principle. Three ways of recording are required.

### Registration with an identity custodian (IdC).
The IdC has the legal authority to retain all personal data essential to complete the process of recognizing the real individual. Consequently it also has full authority over digital identity data and registration is subject to the law of the individual's country of origin.

### Registration with an identity provider (IdP).
The IdP has to guarantee the authenticity of the digital identity and the collection of personal data SHOULD be limited to the sole purpose of this operation. For the registration of a natural person, the IdP requests confirmation from the IdC of the real identity of the applicant before issuing the digital identity. The process is completely online and does not require any physical recognition. For legal entities, the data is provided by the owner or a delegate.

### Registration with a service provider (SP).
The service provider SHOULD know only the data necessary to build the authorization roles to govern access to resources and nothing more. These are provided directly by the user or by an ID token, in addition to those received automatically from their IdP relating to digital identity.
