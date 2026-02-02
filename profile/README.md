# Inji
**Open-Source Verifiable Credentialing Stack for Digital Trust**

Inji is an **open-source, modular verifiable credential (VC) stack** that enables governments, institutions, and ecosystems to issue, hold, present, and verify digital credentials in a secure, interoperable, and privacy-preserving manner.

Built as part of the broader **Digital Public Infrastructure (DPI)** ecosystem, Inji supports global standards and real-world deployments across sectors such as identity, education, agriculture, mobility, and public services.


# What is Inji?
Inji provides a **complete end-to-end VC lifecycle**, including:

- Credential Issuance 
- Wallets for Holders (Web & Mobile)
- Verification & Presentation 
- Cryptographic Trust & Key Management 
- Interoperability across issuers, wallets, and verifiers

Inji is designed to work across **jurisdictions, sectors, and ecosystems**, while remaining configurable for local legal and policy contexts.


# Inji Stack Components

Below is an overview of Inji’s key modules, their purposes, functionalities, key features, and links to their respective GitHub repositories.

## 1. Inji Certify
### Purpose
Credential issuance service for creating and managing verifiable credentials.

### Functionality
- Enables authorities to create and issue verifiable credentials.
- Supports various credential formats (e.g., W3C Verifiable Credentials(LDP_VC), IETF SD-JWT, MSO-MDOC).

### Key Features
- Support different cryptographic suites for signing credentials.
- Integration with external identity providers for authentication.
- Plugin-based implementation for extensibility.
  - If any existing service which issues Verifiable Credential is to be integrated, a plugin can be created for the same.
    - Refer [VCIIssuance Plugin](https://github.com/inji/digital-credential-plugins/blob/master/mosip-identity-certify-plugin/src/main/java/io/mosip/certify/mosipid/integration/service/IdaVCIssuancePluginImpl.java#L51)
  - If any existing service which manages the data which can be converted Verifiable Credential, a plugin can be created for the same.
    - Refer DataProvider Plugin
      - If data is in csv, [CSVDataProviderPlugin](https://github.com/inji/digital-credential-plugins/blob/master/mock-certify-plugin/src/main/java/io.mosip.certify.mock.integration/service/MockCSVDataProviderPlugin.java) can be referred.
      - If data is in postgres, [PostgresDataProviderPlugin](https://github.com/inji/digital-credential-plugins/blob/master/postgres-dataprovider-plugin/src/main/java/io/mosip/certify/postgresdataprovider/integration/service/PostgresDataProviderPlugin.java#L20) can be referred.
- User-friendly interface for data entry.
- Appointment scheduling and notifications.
- Data pre-verification to minimize errors during registration.

### GitHub Repository
- [Reference plugins](https://github.com/inji/digital-credential-plugins)
- [Inji Certify](https://github.com/inji/inji-certify)


## 2. Inji Wallet
### Purpose
Holder wallets (Web & Mobile) that allow users to:
- Store credentials securely
- Share credentials with consent
- Present credentials using OpenID4VP

### Functionality
- Enables holders/users to download and store verifiable credentials.
- Supports various credential formats (e.g., W3C Verifiable Credentials(LDP_VC), IETF SD-JWT, MSO-MDOC).

### GitHub Repository
- [Inji Wallet - Mobile](https://github.com/inji/inji-wallet)
- [Inji Wallet - Web](https://github.com/inji/inji-web)
- [Mimoto](https://github.com/inji/mimoto) - Backend for Inji Wallet


## 3. Inji Verify
### Purpose
Verifier services and SDKs for:
- Requesting credential presentations
- Verifying signatures, schemas, and trust 
- Supporting registry-backed trust (e.g., DeDi integration)


### Functionality
- Support various credential formats (e.g., W3C Verifiable Credentials(LDP_VC), IETF SD-JWT)
- Enables verifiers to request and verify credential presentations.


### GitHub Repository
[Inji Verify](https://github.com/inji/inji-verify)


## 4. Inji Libraries & SDKs
### Purpose
Inji is built using modular libraries and SDKs that can be reused across different components or integrated into third-party applications.
Reusable libraries for:
- OpenID4VCI & OpenID4VP
- Cryptographic operations
- QR-code–based credentials (Claim 169)
- Key discovery and VC verification

## Trust & Interoperability
Inji supports **standards-based trust models**, including:
- DID-based key discovery (DID Web)
- OpenID4VCI & OpenID4VP 
- Optional integration with global trust registries (e.g., DeDi Global)
- Policy-driven, configurable verification flows

This enables **cross-domain, cross-border, and cross-ecosystem trust** without centralization.

## Use Cases
Inji supports a wide range of real-world use cases, including:
- National & foundational identity credentials 
- Education certificates & skill credentials 
- Farmer registries & agricultural programs
- Health, insurance, and social benefit access


## Community & Contribution
Inji is built **with and for the community**.
We welcome contributions across:
- Development
- Testing & QA
- Documentation
- UX & Design
- Architecture & Standards

👉 **Get started by exploring issues or raising a PR**

👉 **Join discussions on community channels**

## Documentation & Resources
- Technical Design Documentation
  - [Inji Certify](https://github.com/inji/inji-certify/tree/master/docs) 
  - [Inji Mobile Wallet](https://github.com/inji/inji-wallet/tree/master/docs) 
  - [Inji Web Wallet](https://github.com/inji/inji-web/tree/master/docs) 
  - [Inji Verify](https://github.com/inji/inji-verify/tree/master/docs)
- Functional Documentation:
  - [Inji Certify](https://docs.inji.io/inji-certify/overview) 
  - [Inji Mobile Wallet](https://docs.inji.io/inji-wallet/inji-mobile) 
  - [Inji Web Wallet](https://docs.inji.io/inji-wallet/inji-web) 
  - [Inji Verify](https://docs.inji.io/inji-verify/overview)
- Standards & Specifications:
  - **OpenID for Verifiable Credential Issuance (OpenID4VCI) - Draft 13**
    - 🔗 Specification (Draft 13): https://openid.net/specs/openid-4-verifiable-credential-issuance-1_0-13.html
  - **OpenID for Verifiable Presentations (OpenID4VP) - Draft 23**
    - 🔗 Specification (Draft 23): https://openid.net/specs/openid-4-verifiable-presentations-1_0-23.html
  - **Selective Disclosure for JWTs (SD-JWT)**
    - 🔗 IETF Internet-Draft: https://datatracker.ietf.org/doc/html/draft-ietf-oauth-selective-disclosure-jwt
  - **ISO/IEC 18013-5:2021 – Mobile Driving Licence (mDL)**
    - 🔗 ISO 18013-5 Overview: https://www.iso.org/standard/69084.html
    - ⚠️ Note: ISO documents are paid standards; only summaries are public.
  - **W3C Verifiable Credentials Data Model v1.1**
    - 🔗 W3C Recommendation: https://www.w3.org/TR/vc-data-model-1.1/
  - **W3C Verifiable Credentials Data Model v2.0**
    - 🔗 W3C Working Draft (latest): https://www.w3.org/TR/vc-data-model-2.0/
  - **Bitstring Status List v2.0**
    - 🔗 W3C Specification: https://www.w3.org/TR/vc-bitstring-status-list/
    - 🔗 Status List vocabulary: https://www.w3.org/ns/credentials/status/
  - Claim169 - QR Code based Verifiable Credentials
    - 🔗 169 - QR Code Specifications: https://docs.mosip.io/1.2.0/readme/standards-and-specifications/mosip-standards/169-qr-code-specification


## Governance & Roadmap
Inji follows an **open governance model** with:
- Transparent roadmaps 
- Public design discussions 
- Community-led enhancements

## Related Ecosystem Projects
- **[MOSIP](https://docs.mosip.io/1.2.0/)** – Foundational Identity Platform 
- **[Sunbird](https://www.sunbird.org/)** – Digital Public Goods for registries & platforms 
- **[DeDi Global](https://dedi-global.gitbook.io/docs)** – Trust registries & network-of-networks

## Stay Connected
- 💬 [Community Updates & Advisories](https://community.mosip.io/)
- 🐙 [GitHub Discussions](https://github.com/orgs/inji/discussions)


## License
All core Inji modules are licensed under the [Mozilla Public License 2.0](https://www.mozilla.org/en-US/MPL/2.0/).
All reference Inji modules are licensed under the [MIT License](https://mit-license.org/). 
Please look at the individual repositories for the correct license.

**Inji — enabling trusted digital credentials, everywhere.**