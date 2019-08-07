# BTCR Day 3

## Status, Checkin

Joe: Satyrn, focusing on scope reduction 

Shivam + Mahendra: BTCR on signet. Had problems (Note: we decided testnet)

Matt Collier: Working on canonical DID document

Anthony: Working to update BTCR electron app to have latest js tools. Added basic wallet support to generate testnet addresses

ChristopherA: review Matt's canonical implicit DID, need a signing tool to make final DIDs

Dan Pape: DID/txref discussions. TODO update c++ libraries. See https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/5

Markus Sabadello: see https://weboftrustinfo.discourse.group/t/txref-conversion-java/177

Micheal Hawkins: looking at playgrounds, also looking at coinb.in (pure browser javascript wallet) which doesn't do testnet yet. This can be run offline and doesn't rely on external bitcoin libraries

Yancy Ribbens: looking at kulpreet's github, has some build errors. setting up a linode

Fausto Woelflin: joining for the first time today, interested to learn

# Agenda
- Anthony demo of BTCR Electron app with wallet functionality: https://github.com/AnthonyRonning/btcr-electron
- Canonical implicit DID Document: https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/4
    - Service descriptors slipped in there at some point which I assume would not be part of an `implicit` DID document.
    - audit trail, time stamp, version (we seem to be covering this now)
- Review of afternoon discussion
    - https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/7
    - https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/5
- Candidate tasks
    - https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues
- Christopher, if you have the vc-js-cli tool running on your system, perhaps you could give a demo, time permitting?


# Issues
- golang code build errors
- owner -> controller
- need to add VC signing capability to implicit document
    - how to represent this?
- satoshi audit trail is part of DID resolution metadata
- key id pattern
- update issue #7 in light of today's discussion
- Service "types" in canonical BTCR DID doc
- Resolver needs to pluck out only the continuation DID doc from the return json object array
- Check with Orie (DIF) about json-ld / jwt signing on DID Document vs Claims 
- Naming discussion
    - continuation/final/constructed DID Document
    - implicit DID Document
    - service/proof purpose
    - audit trail generic vs specific (aka satoshi)
