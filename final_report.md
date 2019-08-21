# BTCR 2019 Hackathon Report

[See Hackathon details and daily reports](https://weboftrustinfo.github.io/btcr-hackathon-2019)

## BTCR Method Behavior Clarifications 

- Transaction signing key is granted DID Auth and VC Signing default capabilities [See Issue 8]( https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/8)
- Clarification of resolver behavior on ambiguous forms:
    - Fail fast when output index is 0 and short form isn't used [See Issue 5](https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/5)
    - "key-1" (transaction signing key) cannot be removed or replaced [See Issue 7](https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/7)


## Tools/Artifacts Produced
- BTCR playground retrofitted on coinb.in; [See BTCR Playground](https://weboftrustinfo.github.io/btcr-tx-playground.github.io)
- Electron demo updated; [See btcr-electron source](https://github.com/AnthonyRonning/btcr-electron)
- Got btcd node on linode [See Details in Issue 17](https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/17)
- Consolidated [BTCR references](https://github.com/w3c-ccg/didm-btcr/blob/gh-pages/resources.md)
- DIF Interop prototype using BTCR DIDs for claims issuer
    - demo linking BTCR DIDs to domains using [.well-known uri](https://github.com/decentralized-identity/well-known)
        - [Example](http://well-known.transmute-did.com/)
    - [JSON-LD VC using BTCR](https://github.com/decentralized-identity/lds-ecdsa-secp256k1-2019.js)
- BTCR Tutorial in Satyrn
    - Satyrn is a JavaScript tutoiral sandbox http://github.com/satyrnjs/satyrn
    - Draft framework for full tutorial on DIDs, BTCR, and BTC (offline)
    - Ultimately focused on just the DID section
    - Raised questions about canonical BTCR format
- Deprecated [txref-conversion-java](https://github.com/WebOfTrustInfo/txref-conversion-java) in favor of newly created [btc-tx-lookup-java](https://github.com/WebOfTrustInfo/btc-tx-lookup-java).
    - Uses [libbech32-java](https://github.com/dcdpr/libbech32-java) and [libtxref-java](https://github.com/dcdpr/libtxref-java) as dependencies.
    - Used by [BTCR driver](https://github.com/decentralized-identity/universal-resolver/tree/master/drivers/btcr/) of DIF Universal Resolver.

## Struggles; still in progress
- Authoring Verifiable Credentials, even simple "knows" claim [See issue 12](https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/12)
- VC signing tooling (key format mismatch) [See issue 15](https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/15)
- DID metadata vs DID resolution metadata (e.g. Satoshi Audit Trail) [See issue 9](https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/9)
- Naming :( [See Issue 10](https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/10)
- BTCR golang service errors [See Issue 11](https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/11)
- Progress on actions from [day 5](https://github.com/WebOfTrustInfo/btcr-hackathon-2019/blob/master/daily/day5.md)


