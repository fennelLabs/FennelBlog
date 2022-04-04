---
layout: post
title: Fennel Protocol - A Framework for Decentralized Communication
author: Sean Batzel, Mateusz Plaza, Isaac Adams, Ed Hertzog
---
The final phase of the Fennel Protocol grant has wrapped up, completing the first iteration of our chain-parallel messaging system, our on-chain signal pallet, and a minimum viable Rust implementation of the Whiteflag Protocol’s message encoding and decoding features.

Whiteflag’s specification includes a carefully-designed compression scheme used to pack messages into a blockchain-optimized binary string, suitable for committing to the chain without seriously impacting the speed of consensus. The goal of keeping our on-chain activity lightweight has persisted through every phase of this grant, with the target being an extremely fast and inexpensive average transaction.

Whiteflag will use a set of extrinsics we designed to present information to the chain without bogging down storage with a ton of extra material. Rather than storing message packets in on-chain storage, we take a binary signal packet as an extrinsic argument, which will of course be reflected in the blockchain’s history, and emit it immediately as an event so that any applications listening for new signals can easily extract them without having to crawl the chain’s state history to catch up. Overall the implementation is similar to Substrate’s internal “remark” concept, which serves to remind of how easy it actually is to commit small pieces of one-off information to chain state without needing to worry about managing storage when any significant mass of messages starts coming through. This will let users post brief, time-sensitive messages such as Whiteflag signals or encrypted announcements of what IP address a particular resource might be (temporarily) found at.

Our chain-parallel messaging system matured considerably during this milestone as well. We completed support for all final identity- and key-management functions in fennel-lib and completed a full server/client pair providing an interface for all of the above. A user can now open a terminal and carry out all simple Fennel Protocol actions, from creating an identity and announcing a public key to sending simple Whiteflag signals and sending short asynchronous messages to other users of the protocol (providing they all use the same server, at the moment). The CLI makes use of every cryptographic function completed in the last two milestones, allowing for RSA and AES encryption schemes as well as Diffie-Hellman key negotiation.

Downloading the fennelLabs/fennel-dist repository will provide four submodules: fennel-cli, fennel-server, Fennel-Protocol, and fennel-lib. fennel-lib can effectively be ignored, as fennel-cli and fennel-server both include it in their Cargo.toml files. Run fennel-server and Fennel-Protocol in parallel to provide all network features that the fennel-cli program will need.

Visit Fennel Protocol’s wiki at https://github.com/fennelLabs/Fennel-Protocol/wiki for more information on how to use our software distribution.
