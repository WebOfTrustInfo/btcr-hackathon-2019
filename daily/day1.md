# BTCR Hackathon Day 1 
August 5, 2019

## Table of Contents


* [Agenda](#agenda)
* [BTCR Orientation](#btcr-orientation)
* [Introductions](#introductions)
* [Q&A and Prioritization Discussion](#q-a-and-prioritization-discussion)
  + [Big issues](#big-issues)
  + [Misc.](#misc)
* [Goals for the week](#goals-for-the-week)
  + [What's needed to achieve Goal 1](#what-s-needed-to-achieve-goal-1)
  + [What's needed to achieve Goal 2](#what-s-needed-to-achieve-goal-2)
  + [Other possible tasks](#other-possible-tasks)
* [Action Items](#action-items)
  + [Everyone, for today](#everyone--for-today)
  + [Specific action items](#specific-action-items)
* [Plan for the week](#plan-for-the-week)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>

## Agenda 
1. BTCR orientation (5 minutes)
2. Brief introductions to understand everyone's background and interests (20 minutes)
3. Q&A + Priorities (25 minutes)
    - https://medium.com/@kimdhamilton/btcr-did-method-updates-d0fd14386139
    - BTCR as an issuer DID method for DIF's interop-athon
    - Others?
      - https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/1
  - Multiple iOS wallets
  - Electron wallet
4. Plan for the week (10 minutes)

## BTCR Orientation 

[BTCR References](../resources.html)

Getting up to speed references:
- Current state: 
https://medium.com/@kimdhamilton/btcr-did-method-updates-d0fd14386139
- BTCR Method Spec: https://w3c-ccg.github.io/didm-btcr/
- Amira use case: https://w3c-ccg.github.io/amira/

Libraries:
 - Bech32 (c++): https://github.com/dcdpr/libbech32
 - Bech32 (java): https://github.com/dcdpr/libbech32-java
 - txref (c++): https://github.com/dcdpr/libtxref
 - txref (java): https://github.com/WebOfTrustInfo/txref-conversion-java
 - txref (java): https://github.com/dcdpr/libtxref-java
 - txref(javascript):  https://github.com/WebOfTrustInfo/txref-conversion-js
 - BTCR command line tools (c++): https://github.com/dcdpr/btcr-DID-method
 - BTCR service (go): https://github.com/kulpreet/btcr-service
 - VC library
 
## Introductions

Kim Hamilton: @kimdhamilton co-chair w3c-ccg. got involved several years ago, because other did methods were bound to bespoke blockchains, which obfuscates many of the design aspects of DIDs. It is becoming important that independent DIDs. Having it nailed as self-sovereign standard, not dominated by huge companies, is important.

Christopher Allen: https://github.com/ChristopherA co-chair w3c-ccg. This is the first DID method. We figured out how to resolve complications by establishing it's possible on bitcoin. This helped inform other permissionless blockchain-based implementations and permissioned. Implementation has lagged because there's no VC-backing. Because we are close to fundamentals of bitcoin, there's a lot of great work we can do. Advantages: We can take advantage of censorship resistance properties of Bitcoin. Also can help enable e.g. Amira use case (see link above) as a representative use case.

Matt Collier: https://github.com/mattcollier/ mcollier@digitalbazaar.com @mattcollier on the discourse group.  Back room person for Digital Bazaar. Here today to help with verifiable credentials. We've thrown together a VC command-line tool that supports bitcoin keys. We are a javascript shop, so we have a repository for [did-io](https://github.com/digitalbazaar/did-io/tree/development) that has drivers and methods for did resolving. maybe a plugin for btcr?

Michael Hawkins: https://github.com/hawkmauk/ @hawkmauk Based in the UK. Interests are human rights, privacy, bitcoin. Following for ~last few years after encountering hyperledger indy project. BTCR stood out as a good implementation. Investigated lightning approach. Background: professional services rather than dev. Enthusiastic contributor. Python, Java background, learning C++. Hope to learn about BTCR this week

Brett Doffing: https://github.com/doffing81. Slapping together an iOS wallet for learning purposes :)

Anthony Ronning: https://github.com/anthonyronning software engineer at learning machine, digital credentials for blockcerts. last year created an [electron wallet](https://github.com/AnthonyRonning/btcr-electron), interested in additional librarys, pythod, javascript c#, etc. 

Muharem Hrnjadovic: https://github.com/al-maisan, have skills in Python and Go, did quite a bit of backend development. Have knowledge of BTC, never wrote software in the crypto space though. Based in CH, philosophically aligned with self-sovereignty and interested in contributing.

Dan Pape: https://github.com/danpape @danpape I've been involved with #RWOT and BTCR for a couple years, and when I started there was a need for a reference implementation of bech32 and txref to support BIP136. I helped pushed through the changes on that BIP--we wanted to add a few extra bits to the spec so that we can point to UTXO output in a specific transaction. Been working on command line apps, working on various other utilities. Over last six month, there have been some issues of best representation of DID document. Been working on a JSON-LD implementation. Excited to help out.

Ryan Grant: https://github.com/dcdpr I heard about DIDs in 2016, the BTCR one sounded solid but need a specification (was on whiteboard) at subsequent RWOT we got parts of it on paper. Background in python and C++. Goals this week to work on the spec text a bit more. Not setting high programming goals this week, but hopes to get a server running Kulpreet's bitcoin explorer Go code.

Markus Sabadello: @peacekeeper In Vienna, now coeditor of DID spec, implemented an early driver for BTCR the DIF Universal Resolver and Universal Registrar, did my own implementation of a number of things that probably need revision. I can do round trip of creating/resolving BTCR DIDs, but not sure that they are up to date. Resolving BTCR DIDs should following the tip, but he doesn't have support for update and deactivate.

Shivam: From India, currently working as blockchain consultant. Doing research on DIDs, which is how he learned about W3C. Currently working on DID-based method on sawtooth. Golang, experience in Identity and Access Mgmt

Yancy Ribbens: Software engineer at Credly. For hackathon, interested in working on getting working implemenetation. If anything to help with re update resolution, happy to help. Interested in Cryptography, Lightning. BTCR is one of the most decentralized methods. In working group for VCs.

Joe Andrieu: https://github.com/jandrieu another ccg cochair. At last RWOT he worked on Jupyter-inspired notebook for showing how BTCR works, Satyrn, at https://github.com/satyrnjs/satyrn. I'll be working on a Satyrn tutorial for BTCR.

## Q&A and Prioritization Discussion
### Big issues
* tip explorer/server (Kulpreet's old code for btcd (go implementation of bitcoin), maybe making scripts to stand that up easier
    * document did tip explorer API so that other implementors can conform to it.
* txref changed - old examples need updating BIP136
* We have a new javascript VC library and we need to make all of our examples up-to-date.

### Misc.
* ChristopherA can share Wolf's bitcoin wallet code for iOS
* To perform lookups we need, you need txindex, which requires rebuilt of node. On bitcoin roadmap, but not been a high priority.
    * Kulpreet's did but not open and live. We need this
* Matt can help with signing of DID documents

## Goals for the week

* Goal 1: We all have a testnet DID with a functioning BTCR DID document in each of our githubs, and one or more verifiable claims saying that we "know" each other. (Note: Connection to help goals of DIF interop-athon)
* Goal 2: At least one implementation supporting update/revoke ("tip following")

### What's needed to achieve Goal 1

* Need to ensure we can create testnet DIDs. 
  * Problem: Our current BTCR DID creation page needs an overhaul (https://weboftrustinfo.github.io/btcr-tx-playground.github.io/create.html)
    * Difficult to use
    * Everyone has to get testnet faucet funds
  * Possible improvements:
    * share testnet coins (faucet and spend return)?
    * easier hosted javascript to generate a testnet BTCR did given a bitcoin tx 
    * investigate using Merkle Wallet
    * investigate using Joe's Satyrn tool for this
    * explore signet as testnet alternative: https://en.bitcoin.it/wiki/Signet
* Need to ensure we can issue VCs
  * We have command line tool we need to ensure works. This library doesn't generically sign DID documents, maybe extract the signing code to sign them.
  * Useful librarues:
    * https://github.com/digitalbazaar/jsonld-signatures
    * https://github.com/digitalbazaar/did-context
    * https://github.com/w3c-ccg/did-spec
    * https://github.com/WebOfTrustInfo/btcr-did-tools-js
    * https://json-ld.org/playground/ (should be updated for latest JSON-LD cli signing)
    * Code for JSON-LD playground here: https://github.com/json-ld/json-ld.org/tree/master/playground
    
 ### What's needed to achieve Goal 2
 - Ideally, get golang service running. This way all consumers can use it
 - Need to be able to create and sign a "continuation" DID document
 - Update BTCR utilities to allow update/revocation
 - Update resolvers to "follow the tip"
    
### Other possible tasks    
 - Do we need a special BTCR JSON-LD context?   
 - OP_RETURN pointing to github as claims storage, but not continuation doc. 
   - I.e. a tx points to github. There's no continuation doc, but VCs are stored there

## Action Items

### Everyone, for today
- Sign up for Discourse at https://weboftrustinfo.discourse.group/
- Read the links in BTCR Orientation (specifically first two)
- Experiment with getting VC tool up and running (https://github.com/WebOfTrustInfo/btcr-hackathon-2019/issues/1)
- Identify codebase you'd like to work in
- Consider finding a bitcoin wallet that support testnet coins. Get yourself some testnet coins from a faucet. 
- Identify gaps in understanding so you can request any knowledge transfer sessions tomorrow

### Specific Action Items 
* Ensure DID Document samples are up to date
* Create BTCR LD context? Just the basics?
* [DONE] @kimdhamilton ensure everyone is added to github repo
* [DONE] @kimdhamilton Update article with Kulpreet's code link https://github.com/kulpreet/btcr-service
* [DONE] @ChristopherA and @kimdhamilton: goal coordination 
* [DONE] @kimdhamilton Make sure diagrams are linked in BTCR DID method
    
## Plan for the week
- Daily checkins (zoom) to talk about progress and any questions
    - document what we've done
    - discuss future plans
- Use CCG IRC for chat (irc.w3.org/?channels=ccg)
- Discourse for asynchronous or longer topics (i.e. replacement for email) (https://weboftrustinfo.discourse.group/)
