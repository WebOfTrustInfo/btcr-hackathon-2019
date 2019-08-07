# BTCR Hackathon Day 2

## Discussion

Our discussion revolved around:
1. Clarifying concepts and terminology
2. Continued Goal Elaboration
3. Q&A

Details are in the [Day 2 Hack MD](https://hackmd.io/2ugDa7azSm-Jm4dxVE9i7A)

## Decisions
- JSON-LD Context
  - BTCR JSON-LD context to be stored in [W3C CCG BTCR Repo](https://github.com/w3c-ccg/didm-btcr)
  - Create a permaid to point to it; see [PermaID Repo](https://github.com/perma-id/w3id.org)
  - context value needs to be an array. Must include common DID context (current link below) and BTCR DID context
    - Current common DID context is: https://w3id.org/did/v0.11
- Signet looks interesting, but lack of library support is a dealbreaker at the moment
- Reminder that `EcdsaSecp256k1VerificationKey2019` is the correct key type to use in BTCR DID Documents (for the signing key)
  
## Action Items
[Issue tracker](https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues)

## Various links

- BTCR common resources extracted to [permanent location](https://github.com/w3c-ccg/didm-btcr/blob/gh-pages/resources.md)
- [BTCR v0.1 design decisions](https://github.com/WebOfTrustInfo/rwot7-toronto/blob/master/final-documents/btcr_0_1.pdf)
  - We discussed "wallet requirements and functionality"
- Possible tool for tracking utxo’s for specific wallets https://github.com/dgarage/NBXplorer/blob/master/docs/API.md
