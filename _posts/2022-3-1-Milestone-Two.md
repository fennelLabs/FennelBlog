---
layout: post
title: Fennel Protocol - Encryption and Security Management
author: Sean Batzel, Mateusz Plaza, Isaac Adams, Ed Hertzog, Patrick Gryczka
---
The second development phase for Fennel Protocol, and the most critical in the long-term, is the creation of tools that give applications and end-users the ability to exchange information that shouldn't be public knowledge. The core development team completed this development phase over the past month. Most of these changes were targeted directly at building out the tools used to interact with the protocol and connect end-users.

Two encryption mechanisms, RSA and Diffie-Hellman-powered AES, are provided in this release, along with on-chain storage ties allowing RSA public keys and Diffie-Hellman public key factors to be broadcasted to the chain. Once encryption and signature resources are submitted to the chain, actors across the network can leverage the existing identity and trust mechanisms to create encrypted channels between themselves and other members of the network.

A major addition during this milestone is a client/server pair intended to operate in parallel with the blockchain node and allow easy self-hosting of Fennel-enabled encrypted message servers. The command-line client includes a set of functions for sending and retrieving important information to and from the Fennel blockchain and integrating it with messaging and content-sharing features available in the off-chain components.

The major step for the next month is to turn our focus to Whiteflag Protocol and fully build out their guidelines for a minimum viable implementation of the specification. This includes implementing authentication leveraging Fennel Protocol’s identity and key management features as authentication anchors, and the basic mechanisms for managing on-chain signals adhering to the Whiteflag standard.
