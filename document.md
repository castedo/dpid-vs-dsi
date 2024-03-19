---
title: DeSci dPID vs Document Succession Identifier
date: 2024-03-19
abstract: |
  [Document Succession Identifiers](https://perm.pub/1wFGhvmv8XZfPx0O5Hya2e9AyXo/) (DSIs)
  and the infrastructure developed by [DeSci Labs](https://desci.com) both implement
  [Persistent IDentifiers](https://en.wikipedia.org/wiki/Persistent_identifier) (PIDs).
  This document summarizes the basic similarities and differences between the two.
---

Terminology
-----------

| DeSci Concept | Similar DSI Concept |
| :---: | :---: |
| dPID & root hash | base DSI |
| node | Baseprint document succession |
| Alias registry | N/A |
| Research object (version of) | Baseprint document snapshot |
| IPFS directory | Git tree |
| IPFS CID | SWHID & Git hash |
| Ceramic stream | Git history in DSGL |
| DID | SSH signing key |

### dPID & root hash vs base DSI

A base DSI is a DSI without an edition number. For example:

> `VGajCjaNP1Ugz58Khn1JWOEdMZ8`

A dPID can be drastically shorter and more human-friendly, for example:

> `46`

A dPID is assigned to a root hash, which is primarily for internal use and usually not
seen by a user.
A base DSI is a hash but is shorter than a DeSci node's root hash.

A dPID and root hash are designed to fill different needs with different trade-offs. A DSI
is a compromise designed to only partially satisfy the objectives of a dPID and a root hash.

### DeSci Node vs Baseprint document succession

Both DeSci nodes and Baseprint document successions track versions of digitally encoded
snapshots of a research object. A Baseprint document is a narrow type of research
object.

Versioning in DeSci Nodes is done with positive integers, whereas a document succession
can use multi-level edition numbers, similar to semantic versioning of software packages.

### DeSci Alias Registry

A dPID is an alias to the root hash of a DeSci node.
dPIDs can be very short and human-friendly because they rely on a decentralized alias registry,
which makes a dPID an [extrinsic identifier](
https://www.softwareheritage.org/2020/07/09/intrinsic-vs-extrinsic-identifiers/).
In contrast, a DSI is an intrinsic identifier, which does not require a registry
at the cost of being longer and less human-friendly than a dPID.

### DeSci research object vs Baseprint document snapshot

As of 2023, DSI are only used for a very narrow type of research object,
specifically static research documents (that are JATS XML based) stored in
[Document Succession Git Layout](https://perm.pub/VGajCjaNP1Ugz58Khn1JWOEdMZ8/) (DSGL).
Like JATS XML packages as found in PubMed Central, these research documents are not intended to exceed tens of megabytes and are typically much smaller.

DeSci Nodes are designed for a much more general type of research object that
brings manuscripts, data, and code together in one place.
DeSci Nodes are designed to handle vastly larger research objects, even ones that are hundreds of gigabytes.

### IPFS directory vs Git tree

A DeSci research object is digitally encoded in an IPFS directory, whereas a Baseprint
document snapshot is encoded in a Git tree.

### IPFS CID vs SWHID & Git hash

An IPFS directory (or fixed version of) is identified by a CID (content identifier),
whereas a Git tree is identified by a Git hash or SWHID (Software Hash IDentifier).

A CID has a self-describing format, whereas a Git hash does not.


### Ceramic stream vs Git history in DSGL

A Git history in DSGL ([Document Succession Git
Layout](https://perm.pub/VGajCjaNP1Ugz58Khn1JWOEdMZ8)) serves a role to DSI similar to
the role [Ceramic](https://developers.ceramic.network/) streams serve for a dPID.

A Git history in DSGL is stored in Git repositories or git-compatible archives such
as the Software Heritage Archive, whereas Ceramic streams of DeSci
Nodes use IPFS and the Ethereum blockchain.

### DID vs SSH signing key

Both Git histories in DSGL and Ceramic streams require a mechanism such that only
certain entities (such as authors) can update the distributed research objects.

DeSci Nodes uses DIDs (Decentralized Identifiers), whereas DSGL uses SSH signing keys
for this function.

