# Day 5

## Agenda
- Standup/Demos
    - Identify blockers so we can capture them
- Discussion
    - Steps related to resolver infrastructure
        - in order for a resolver to work
            - bitcoind doesn't fully index UTXO address
                - could take 15 secs per transaction, and a resolution may involve multiple transactions.
                - A fully indexed bitcoind on mainnet may require 1TB+ of disk space.
            - btcd does index UTXO addresses
                - there may be some others that fully index
                - there are patches to bitcoind that fully index
                    - all bitcoin explorers have those patch but few open source
                    - blockstream may be available
            - put on more explorer-like APIs but optimed BTCR
    - Layers
        - Bitcoin [returns transactions]: bitcoin consensus
        - BTCR explorer [returns tip results and audit trail]: following the tip (kulpreet's API) AKA dereferencing multiple transactions.
            - MAYBE: some load balancing / distrubtion of explorer services like Electrum Wallet does
                - Blockchain Commons is willing to pay/host at least 1 server
                - .onion service at some point
        - BTCR-only DID resolver [returns DID Document and audit trail]: can do bitcoin consensus and do exploration itself, or
            - call one or more BTCR explorers
        - DID general resolvers [returns DID Document and audit trail](works with multiple DID methods): all the above themselves, or they call an BTCR explorer
            - metadata format is issue #9
    - BTCR Explorer API
        - all of javascript tools have been using APIs from bitcoin explorers
            - lots of variety
            - most have load/rate limits
        - Kulpreet drafted an API optimized for BTCR
            - https://github.com/kulpreet/btcr-service
            - https://github.com/kulpreet/btcr-service/blob/master/btcr-service.go#L82
        - Review this vs other bitcoin explorer APIs for best practices
            - Blockstream Explorer was released should review
                - https://github.com/Blockstream/esplora
    - Talk about dlongley's VC
        - discussion
        - ACTION: Gave Matt & Anthony private WIF testnet key for sample implicit DID key did:btcr:xyv2-xzpq-q9wa-p7t#satoshi so that they can create real BTCR-based VCs in their demo.
        - ACTION: Put "WoT" context in each VC, will do URL based one later.
        - ACTION: Ask @dlongley to look at what it would take to put VP into credential that verifies that Alice has confirmed that Bob has possession of private key
    - implicit DID example #4
- Next steps to close this week
- keeping community development going
    - repos
        - multiple hackathon repos (2 in RWOT and 1 in CCG)
        - spec is CCG
            - keep this one focused on method spec
        - Github BTCR Organzization repo?
            - lots of repos vs group
            - ACTION: Create BTCR Organization github and set initials
            - ACTION: What repos should moved? How?
            - ACTION: Move this hackathon issues as appropriate
    - Who is coming to RWOT?
        - Christopher, Kim, Yancy, Anthony, Ryan
    - More regular phone/zoom/standup meetings?
        - bi-weekly
        - ACTION: @ChristopherA Doodle to pick times
    - how do coordinate a virtual community?
    - culture
        - keep the process continuous
        - keep some bitcoin-core culture?
        - overall governance structure?
            - bitcoin-core isn't completely anarchic, but close
        - licensing bitcoin-core (BSD3)?
            - patent questions? Apache? (DIF & Linux Foundation?)
                - arguments against GPLv3?
        - Keep open-source focused org, different other VC-backed ecosystem (variety)
        - ACTION: Mission Statement, Contributors guide, Global accessible (multiple)
        - ACTION: Announce community
    - Asyncronous comm? or purely community repo issues? Keep RWOT discourse in reserve.

## Standup

Anthony Ronning: added labels (to label DIDs). Experimenting with VC issuing tool. 

Michael Hawkins: progress on playground. UI Improvements. Will create PR against BTCR playground
    
Matt Collier: got @dlongley's input on sample "knows" VC

Yancy Ribben: stand up linode, Kulpreet stood up 

Christopher: Puzzling through construction of VC (how do we know what we know). Also talking with Ryan about "controller"

Shivam + Mahendra: 
- debugging DID creation code (chain.so APIs)
- btcd libraries are out of date
    - ChristopherA: there's context for that claim. Debatable.
- will set up node to avoid 3rd party code
    
Kim: BTCR Method Spec, ran into problems due to #4

## Issues/Blockers

- https://github.com/w3c-ccg/didm-btcr/issues/19
