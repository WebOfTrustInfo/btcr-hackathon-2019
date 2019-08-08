# BTCR Hackathon Day 4

## Agenda

1. Standup, check around for progres, demos
2. Candidate tasks
3. DID Document Discussion

## Standup

Michael Hawkins
- merging playground and coinbin wallet
- VC command line tool requires base58 encoding
- screenshare 

Matt Collier
- Worked with Christopher to get command line tool going
- He and Anthony can sign credentials with that tool

Ryan Grant
- Discussions about Satoshi audit trail (see also: https://hackmd.io/p5OZs9ENTC6X682W2trGoQ?edit)
- Getting servers to use for Kulpreet's service, coordinate with Yancy

Yancy Ribbens
- created golang library issues
- mismatches in dependent libraries
- Kulpreet planning to look into this
- Can take a look at signing with c++ tool
    - Matt: it's a significant lift
    - https://github.com/digitalbazaar/rdf-canonize-native

Shivam Sethi / Mahendra
- Looking into making it easier to have a source of testnet funding
- I.e. incorporating faucet into playground
- ChristopherA feedback
    - propose using coinbin tool instead of existing playground creation tool
    - separate faucet creation
    - We can give Shivam rpc into so he can start working on faucet 
- rgrant feedback
    - propose adding this to golang tool

Christopher Allen
- Playing with VC CLI tool
- Note private key is in base58
- Has demo VC
    - Note: DID isn't btcr
- Working on "knows" claim. See issue #12
- Working on implicit DID #4 (scroll to bottom)

Kim Duffy
- Administrivia

Joe Andrieu
- https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/16
- Scope: do exercise for DID parser in Satyrn
- What about colons in query part of DID string?
    - Kim: this is a broader question. Need to check in with Markus


## Candidate Tasks

- txref "x"/"8" issue, need playground javascript to do right thing https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/5
    - https://github.com/WebOfTrustInfo/btcr-did-tools-js
    - Note that btcr-did-tools-js gets browserified and copied into playground
    - See issue https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/13
- WIF & base58 issue
    - https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/15
- look at the implicit did https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/4
- "knows" claim template https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/12
- "audit" https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/9
- c++ based json-ld signing https://github.com/digitalbazaar/rdf-canonize-native
    - tracked here: https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/14
    > Longley did mention that we do have a C++ implementation of the RDF
    > Dataset Canonize function, which means that if you got a C++
    > implementation of JSON-LD .expansion() and .toRdf(), that's all you'd
    > need to do native BTCR and native mobile development... that's more of an uplift
- How to deal with hyphens/colons
    - https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/16
        - bech32 & txref

