---
dep: 1
title: DEP Purpose and Guidelines
status: Active
type: Meta
created: 2020-03-24
updated: 2020-04-02
---

## What is a DEP?

DEP stands for Debrief Enhancement Proposal. A DEP is a design document providing information to the Debrief community, or describing a new feature for Debrief or its processes or environment. The DEP should provide a concise technical specification of the feature and a rationale for the feature. The DEP author is responsible for building consensus within the community and documenting dissenting opinions.

## DEP Rationale

We intend DEPs to be the primary mechanisms for proposing new features, for collecting community technical input on an issue, and for documenting the design decisions that have gone into Debrief. Because the DEPs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

For Debrief implementers, DEPs are a convenient way to track the progress of their implementation. Ideally each implementation maintainer would list the DEPs that they have implemented. This will give end users a convenient way to know the current status of a given implementation or library.

## DEP Types

There are three types of DEP:

- A **Standard Track DEP** describes any change that affects most or all Debrief implementations, such as a change to the network protocol, a change in block or transaction validity rules, proposed application standards/conventions, or any change or addition that affects the interoperability of applications using Debrief. Furthermore Standard DEPs can be broken down into the following categories. Standards Track DEPs consist of three parts, a design document, implementation, and finally if warranted an update to the [formal specification].
  - **Core** - improvements requiring a consensus fork, as well as changes that are not necessarily consensus critical but may be relevant to “core dev” discussions (for exampl the miner/node strategy changes).
  - **Networking** - includes improvements around devp2p, as well as proposed improvements to network protocol specifications of related applications.
  - **Interface** - includes improvements around client [API/RPC] specifications and standards, and also certain language-level standards like method names and [contract ABIs]. The label “interface” aligns with the [interfaces repo] and discussion should primarily occur in that repository before a DEP is submitted to the DEPs repository.
  - **DRC** - application-level standards and conventions, including contract standards such as wallet formats, library/package formats, token standards, name registries, and URI schemes.
- A **Meta DEP** describes a process surrounding Debrief or proposes a change to (or an event in) a process. Process DEPs are like Standards Track DEPs but apply to areas other than the Debrief protocol itself. They may propose an implementation, but not to Debrief's codebase; they often require community consensus; unlike Informational DEPs, they are more than recommendations, and users are typically not free to ignore them. 
- An **Informational DEP** describes an Debrief design issue, or provides general guidelines or information to the Debrief community, but does not propose a new feature. Informational DEPs do not necessarily represent Debrief community consensus or a recommendation, so users and implementers are free to ignore Informational DEPs or follow their advice.

It is highly recommended that a single DEP contain a single key proposal or new idea. The more focused the DEP, the more successful it tends to be. A change to one client doesn't require a DEP; a change that affects multiple clients, or defines a standard for multiple apps to use, does.

A DEP must meet certain minimum criteria. It must be a clear and complete description of the proposed enhancement. The enhancement must represent a net improvement. The proposed implementation, if applicable, must be solid and must not complicate the protocol unduly.

## DEP Work Flow

Before you begin writing a formal DEP, you should vet your idea. In addition, it will be your role as the author to make your idea clear to reviewers and interested parties, as well as inviting editors, developers and community to give feedback on the aforementioned channels. You should try and gauge whether the interest in your DEP is commensurate with both the work involved in implementing it and how many parties will have to conform to it. 

### Core DEPs

For Core DEPs, given that they require client implementations to be considered **Final** (see "DEPs Process" below), you will need to either provide an implementation for clients or convince clients to implement your DEP. 


### DEP Process 

Following is the process that a successful non-Core DEP will move along:

```
[ WIP ] -> [ DRAFT ] -> [ LAST CALL ] -> [ FINAL ]
```

Following is the process that a successful Core DEP will move along:

```
[ IDEA ] -> [ DRAFT ] -> [ LAST CALL ] -> [ ACCEPTED ] -> [ FINAL ]
```

The DEP editors will process these requests as per the conditions below.

* **Idea** -- Once the champion has asked the Debrief community whether an idea has any chance of support, they will write a draft DEP as a [pull request]. Consider including an implementation if this will aid people in studying the DEP.
  * :arrow_right: Draft -- If agreeable, DEP editor will assign the DEP a number (generally the issue or PR number related to the DEP) and merge your pull request. The DEP editor will not unreasonably deny a DEP.
  * :x: Draft -- Reasons for denying draft status include being too unfocused, too broad, duplication of effort, being technically unsound, not providing proper motivation or addressing backwards compatibility, or not in keeping with the Debrief philosophy.
* **Draft** -- Once the first draft has been merged, you may submit follow-up pull requests with further changes to your draft until such point as you believe the DEP to be mature and ready to proceed to the next status. A DEP in draft status must be implemented to be considered for promotion to the next status (ignore this requirement for core DEPs).
  * :arrow_right: Last Call -- If agreeable, the DEP editor will assign Last Call status and set a review end date.
  * :x: Last Call -- A request for Last Call status will be denied if material changes are still expected to be made to the draft.
* **Last Call** -- 
  * :x: -- A Last Call which results in material changes or substantial unaddressed technical complaints will cause the DEP to revert to Draft.
  * :arrow_right: Accepted (Core DEPs only) -- A successful Last Call without material changes or unaddressed technical complaints will become Accepted.
  * :arrow_right: Final (Non-Core DEPs) -- A successful Last Call without material changes or unaddressed technical complaints will become Final.
* **Accepted (Core DEPs only)** -- This status signals that material changes are unlikely and Debrief developers should consider this DEP for inclusion. Their process for deciding whether to encode it into their clients as part of a hard fork is not part of the DEP process.
  * :arrow_right: Draft -- The Core Devs can decide to move this DEP back to the Draft status at their discretion. E.g. a major, but correctable, flaw was found in the DEP.
  * :arrow_right: Rejected -- The Core Devs can decide to mark this DEP as Rejected at their discretion. E.g. a major, but uncorrectable, flaw was found in the DEP.
  * :arrow_right: Final -- Standards Track Core DEPs must be implemented in at least three viable Debrief clients before it can be considered Final. When the implementation is complete and adopted, the status will be changed to “Final”.
* **Final** -- This DEP represents the current state-of-the-art. A Final DEP should only be updated to correct errata.

Other exceptional statuses include:

* **Active** -- Some Informational and Process DEPs may also have a status of “Active” if they are never meant to be completed. E.g. DEP 1 (this DEP).
* **Abandoned** -- This DEP is no longer pursued by the original authors or it may not be a (technically) preferred option anymore.
  * :arrow_right: Draft -- Authors or new champions wishing to pursue this DEP can ask for changing it to Draft status.
* **Rejected** -- A DEP that is fundamentally broken or a Core DEP that was rejected by the Core Devs and will not be implemented. A DEP cannot move on from this state.
* **Superseded** -- A DEP which was previously Final but is no longer considered state-of-the-art. Another DEP will be in Final status and reference the Superseded DEP. A DEP cannot move on from this state.

## What belongs in a successful DEP?

Each DEP should have the following parts:

- Preamble - RFC 822 style headers containing metadata about the DEP, including the DEP number, a short descriptive title (limited to a maximum of 44 characters), and the other details. 
- Abstract - A short (~200 word) description of the technical issue being addressed.
- Motivation (*optional) - The motivation is critical for DEPs that want to change the Debrief protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the DEP solves. DEP submissions without sufficient motivation may be rejected outright.
- Specification - The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Debrief platforms.
- Rationale - The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.
- Backwards Compatibility - All DEPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The DEP must explain how the author proposes to deal with these incompatibilities. DEP submissions without a sufficient backwards compatibility treatise may be rejected outright.
- Test Cases - Test cases for an implementation are mandatory for DEPs that are affecting consensus changes. Other DEPs can choose to include links to test cases if applicable.
- Implementations - The implementations must be completed before any DEP is given status “Final”, but it need not be completed before the DEP is merged as draft. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of “rough consensus and running code” is still useful when it comes to resolving many discussions of API details.
- Security Considerations - All DEPs must contain a section that discusses the security implications/considerations relevant to the proposed change. Include information that might be important for security discussions, surfaces risks and can be used throughout the life cycle of the proposal. E.g. include security-relevant design decisions, concerns, important discussions, implementation-specific guidance and pitfalls, an outline of threats and risks and how they are being addressed. DEP submissions missing the "Security Considerations" section will be rejected. A DEP cannot proceed to status "Final" without a Security Considerations discussion deemed sufficient by the reviewers.


## DEP Formats and Templates

DEPs should be written in [markdown] format.
Image files should be included in a subdirectory of the `assets` folder for that DEP as follows: `assets/dep-N` (where **N** is to be replaced with the DEP number). When linking to an image in the DEP, use relative links such as `../assets/dep-1/image.png`.


## Auxiliary Files

DEPs may include auxiliary files such as diagrams. Such files must be named DEP-XXXX-Y.ext, where “XXXX” is the DEP number, “Y” is a serial number (starting at 1), and “ext” is replaced by the actual file extension (e.g. “png”).


## History

This document was derived heavily from [Ethereum's BIP-1] which in turn was derived from Bitcoin's BIP-001 which derived from [Python's PEP-0001]. In many places text was simply copied and modified. Although the PEP-0001 text was written by Barry Warsaw, Jeremy Hylton, and David Goodger, they are not responsible for its use in the Debrief Enhancement Process, and should not be bothered with technical questions specific to Debrief or the DEP.



## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).