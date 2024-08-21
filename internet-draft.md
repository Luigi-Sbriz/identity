---
> stand_alone: true
ipr: trust200902
area: SEC
wg: Web Authorization Protocol
submissiontype: IETF

> title: Identity Trust System
abbrev: Identity Trust
docname: draft-sbriz-identity-trust-system-02
cat: std
lang: en

> author:
  ins: L. Sbriz
  name: Luigi Sbriz
  org: Cybersecurity & Privacy Senior Consultant
  email: luigi@sbriz.eu

> normative:
  RFC6749:
  RFC5322:
  RFC5321:
  RFC5234:

informative:
  ITU1:
    target: "https://www.itu.int/dms_pub/itu-t/opb/tut/T-TUT-CCICT-2020-PDF-E.pdf"
    title: >
      QTR-RLB-IMEI - Reliability of International Mobile Station Equipment Identity (IMEI), Technical Report
    author:
      org: International Telecommunications Union
    date: 2020-07
  ITU2:
    target: "https://www.itu.int/rec/T-REC-E.118"
    title: "E.118: The International Telecommunication Charge Card"
    author:
      org: International Telecommunications Union
    date: 2006-05
  LS1:
    target: "https://www.isaca.org/resources/isaca-journal/issues/2022/volume-2/a-symmetrical-framework-for-the-exchange-of-identity-credentials-based-on-the-trust-paradigm-part-1"
    title: >
      A Symmetrical Framework for the Exchange of Identity Credentials Based on the Trust Paradigm,
      Part 1: Identity Trust Abstract Model, ISACA Journal, vol.2
    author:
      ins: L. Sbriz
      name: Luigi Sbriz
    date: 2022-04
  LS2:
    target: "https://www.isaca.org/resources/isaca-journal/issues/2022/volume-2/a-symmetrical-framework-for-the-exchange-of-identity-credentials-based-on-the-trust-paradigm-part-2"
    title: >
      A Symmetrical Framework for the Exchange of Identity Credentials Based on the Trust Paradigm,
      Part 2: Identity Trust Service Implementation, ISACA Journal, vol.2
    author:
      ins: L. Sbriz
      name: Luigi Sbriz
    date: 2022-04
  LS3:
    target: "https://www.isaca.org/resources/isaca-journal/issues/2023/volume-1/how-to-digitally-verify-human-identity"
    title: >
      How to Digitally Verify Human Identity: The Case of Voting, ISACA Journal, vol.1
    author:
      ins: L. Sbriz
      name: Luigi Sbriz
    date: 2023-01
  LS4:
    target: "https://www.isaca.org/resources/isaca-journal/issues/2023/volume-6/modeling-an-identity-trust-system"
    title: >
      Modeling an Identity Trust System, ISACA Journal, vol.6
    author:
      ins: L. Sbriz
      name: Luigi Sbriz
    date: 2023-11

<!-- --- abstract -->
# Abstract

This document defines an identity trust system, which is a general digital identity authentication system that requires no federation of authentication domains. The main components of the authentication process between two entities are:

1. Symmetric authentication protocol - Both entities must recognize each other and are authenticated by their identity provider according to a symmetric message exchange scheme. It builds on and extends the OAuth Authorization Framework RFC6749.
2. Trustees' network - A special network, dedicated to creating a protected environment for exchanging authentication messages between Identity Providers (IdPs), constitutes the infrastructure to avoid domain federation.
3. Custodian concept - IdPs are divided into two typologies to better protect personal data and link digital identity to physical one. A generic IdP (called trustee) to manage digital authentication only and a specific IdP (called custodian), with the legal right to process the individual's real data and under the control of country's authority, to manage the physical identity and the link with the digital one.

--- middle
