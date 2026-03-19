# rede — theoretical specification

> this document is a scaffold. sections marked with `[fill in]` need your description.
> sections marked with `[open question]` are design decisions left for contributors.

---

## introduction

`rede` is an open and free alternative to the web. it should allow anyone to
host their code and show it to world as long as they help others do the same.

---

## core principles

- every user is both a client and a server, running the network code and distributing stored files
- resource contribution (storage/processing) proportionally grants storage/processing usage rights and voting power
- the network is hierarchical: sub-networks run their own code on top of the parent network's code
- new users can only join when there is available capacity
- vote power is decided by amount of contribution to the network
- sub-networks contributing >1% of parent resources can vote to add code to the parent (2/3 majority required)
- sub-networks contributing >10% of parent resources can vote to replace parent code (2/3 majority required)
- the root network provides storage/hosting with a JIT compiler to run the network code

---

## node identity

[open question]
<!-- how do nodes identify themselves?
     consider:
       - public/private keypair: identity = public key, actions are signed with the private key.
         standard approach, no central authority needed.
       - something else?
     describe:
       - how is an identity created? (key generation on first run?)
       - how is it stored? (local keyfile?)
       - how is it used? (sign commits, votes, messages?)
       - can a user have multiple identities?
-->

---

## peer discovery

[open question]
<!-- how does a new node find and join the network?
     consider:
       - bootstrap nodes: a hardcoded or user-provided list of known entry points.
         new nodes connect to bootstrap nodes to get an initial peer list.
       - after bootstrap: how does the node maintain and update its peer table?
         (DHT? gossip protocol? something else?)
     describe:
       - the full join flow from first launch to being an active participant
       - what information does a node announce about itself? (capacity, address, identity)
       - what happens when a bootstrap node goes offline?
-->

---

## data model

[open question]
<!-- how are files stored and addressed on the network?
     consider:
       - content-addressed: files are identified by a hash of their contents.
         integrity is guaranteed, deduplication is automatic. used by git, IPFS, BitTorrent.
       - name-addressed: files are identified by <identity>/<name>.
         more human-readable but requires a lookup layer.
       - hybrid: content-addressed storage with a named index on top.
     describe (or mark as open):
       - the object model for repositories (analogous to git's blob/tree/commit objects)
       - how file integrity is verified
       - replication: how many nodes hold each file? how is that decided?
       - what happens to files when a node goes offline?
-->

---

## version control

[fill in]
<!-- rede aims to be a full VCS replacement. describe:
     - repository structure: what is a repo? how is it identified? (<identity>/<name>?)
     - commits: how are snapshots recorded? what metadata does a commit carry?
       (author identity, timestamp, parent commit(s), content reference, message?)
     - branches: how are named pointers to commits managed?
       who can create/move/delete a branch?
     - history: is history immutable? can commits be amended or force-pushed?
-->

[open question: collaboration model]
<!-- how does a contributor propose changes to someone else's repository?
     consider:
       - "proposal" objects: a signed object pointing to a set of commits,
         submitted to the target repo owner's node. similar to a pull request.
       - direct push with owner approval: contributor pushes to a shared staging area,
         owner merges.
       - something else?
     describe the full flow: fork → change → propose → review → merge (or reject)
-->

---

## protocol

[open question]
<!-- what operations must the rede protocol support?
     consider at minimum:
       - peer discovery / announce
       - file/object request and transfer
       - commit and branch sync
       - vote broadcast and tally
       - sub-network registration
     describe:
       - the full list of protocol operations for v0
       - are operations request/response, or event-driven/gossip?
-->

[open question: transport and wire format]
<!-- what should the protocol run over, and how should messages be serialized?
     options:
       - transport: TCP, QUIC, WebRTC (QUIC is modern and handles NAT traversal well)
       - wire format: protobuf (compact, typed), msgpack (compact, schemaless), JSON (human-readable)
     leave as open question if undecided — list what tradeoffs matter most to you
-->

---

## resource model

[fill in]
<!-- describe the relationship between contribution and rights:
     - what counts as a contribution? (storage space offered, processing time, bandwidth?)
     - how does contribution translate to usage rights?
       (e.g., contribute X GB of storage → use up to X GB of storage)
     - how does contribution translate to voting power?
       (time-weighted: contributing longer increases weight?)
-->

[open question: verification]
<!-- how does the network verify that a node is actually contributing what it claims?
     this is a hard problem. candidate approaches:
       - periodic storage challenges: the network asks nodes to prove they hold specific data
       - reputation + penalty: nodes self-report, but lying leads to ejection after detection
       - economic staking: nodes put up a stake that is slashed if they fail challenges
     mark as open question if undecided — briefly describe which tradeoffs matter
-->

---

## governance

[fill in]
<!-- the README describes the threshold rules (1% to propose additions,
     10% to propose replacements, 2/3 majority to approve). expand on:
     - how is a vote initiated? (what does the proposal object look like?)
     - how is it broadcast to the network?
     - how long does voting last? what determines the end of a vote?
     - how are votes tallied? (weighted by contribution? one-node-one-vote?)
     - what happens to a rejected proposal?
     - can a proposal be resubmitted? after how long?
     - what prevents spam proposals?
-->

---

## root network v0 — minimal bootstrap spec

[fill in]
<!-- list the minimum features the first implementation must have for the network
     to exist and be self-sustaining. everything else is left for sub-networks or future votes.
     suggested candidates (edit as needed):
       1. node identity (keypair generation and signing)
       2. peer discovery (bootstrap + peer table)
       3. file store and retrieve (content-addressed objects)
       4. repository objects (blob, tree, commit, branch ref)
       5. resource accounting (even if self-reported / unverified in v0)
       6. voting mechanism
       7. network code hosting (the network stores and distributes its own code)
     for each item, describe what "done" looks like at the v0 level.
-->

---

## open questions

[fill in]
<!-- list every design decision that is deliberately left open for contributors
     to propose solutions and vote on. format each as a question, with brief context
     on why it matters.
     start from the open questions scattered through this document and add any others.
-->

---

## how to contribute

[fill in]
<!-- describe:
     - what kind of help is needed right now?
       (protocol design, reference implementation, security analysis, documentation?)
     - what background is useful? (distributed systems, cryptography, systems programming?)
     - where should contributors reach out or discuss? (add links when available)
-->
