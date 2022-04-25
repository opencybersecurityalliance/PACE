# PACE Frequently Asked Questions

## Introduction
This is for answering frequently asked questions (FAQ)
about PACE.
Initially it will just a random list of questions
that we will organize later

## What does PACE stand for?
PACE is an ancronym for Posture Attribute Collection & Evaluation

## What is PACE?
Need something pithy here with a reference link to something more complete

## Is PACE and open source or standards effort?
Good question.
The objective is to meet the OCA goal of
"making standards-based interoperable cybersecurity".
The plan to achieve that goal wrt PACE is to
have one or more open source reference implementations
and to define the interfaces,
which would eventually be standardized.

## How does PACE relate to OCA?
PACE is a subproject of OCA just like Stixshifter and Kestrel.

## What does "posture" mean wrt PACE?
tbd

## What does "posture attributes" mean wrt PACE?
tbd

## What are examples of posture attributes?
give examples and reference other docs for more

## What is "collection" wrt PACE?
tbd

## What is "evaluation" wrt PACE?

## What is the PACE architecture?
ref arch

## How is PACE used?
ref PACE use cases

## How does PACE relate to Stixshifter?
tbd

## How does PACE relate to Kestrel?
tbd

## How does PACE relate to OCA Ontology?
tbd

## How do SBOMs relate to PACE?
tbd

## How do VEXs relate to PACE?
tbd

## How do NVD and CVE's relate to PACE?
tbd

## How does PACE relate to OpenC2?
[OpenC2](https://openc2.org) is a standard command & control (C2)
language for cybersecurity.
PACE uses OpenC2 for sending commands.
See {need to add link to arch or example or ...}

## How does CACAO relate to PACE?
[Collaborative Automated Course of Action Operations](https://docs.oasis-open.org/cacao/security-playbooks/v1.0/security-playbooks-v1.0.html)
(CACAO) playbooks contain decision points and actions to be taken.
Many of the decision points will use security posture,
i.e. PACE data,
to decide on the course of action.

## How does PACE relate to the Security Content
Automation Protocol (SCAP)?
tbd

## How does PACE relate to Security Automation and Continuous Monitoring (SACM)?
tbd

## How does PACE relate to the Situational Awareness Reference Architecture (SARA)?
The
[Situational Awareness Reference Architecture](http://ics-isac.org/sara/)
(SARA) was created by the ICS-ISAC "for industrial facility owners and operators as an open source guide to establishing and maintaining situational awareness." They break SARA into 4 components:
- Identity
- Inventory
- Activity
- Sharing

PACE is for collecting and evaluating security posture attributes.
PACE can serve as part of SARA sharing -
i.e. SARA can create security posture attributes
to be collected by PACE.
In addition security posture provided by PACE
can be input to SARA.

## What is PACE scope of work?
https://github.com/opencybersecurityalliance/PACE/issues/7
2022-01-31: During the PACE meeting it was thought that scope of work should speak to what we are actually looking to build.  Scope indicates what PACE will specify and develop.  

Scope will be broken apart into several children issues such as Asset Inventory, Hardware BOM, open source software repo's within PACE (ie. on OCA open project), SBOM-preferred ala STIX-preferred, PAR, etc.

## Will the SACM architecture draft be pulled into this group?
https://github.com/opencybersecurityalliance/PACE/issues/22
SACM architecture ID is foundation / inspiration for the prototyping work to be done under OCA PACE.  As the focus of the PACE effort is prototyping, the SCAM Architecture draft will not need to be updated, revised, or expanded.  PACE results should inform any future reincarnation of the SACM draft.

## How do we want to organize code repositiories?
https://github.com/opencybersecurityalliance/PACE/issues/24
The PGB decided at the Feb meeting to delegate repo permission to the TSC and the projects (ie project proposes, TSC approves).  Any PACE member can propose a new repo, it can be discussed at a Monday meeting, and unless there are objections, the repo could be created (after TSC approves).

## Is Asset Inventory within in PACE scope?
https://github.com/opencybersecurityalliance/PACE/issues/28
Asset Inventory is out of scope.  IT Asset Management, e.g., https://www.solarwinds.com/solutions/it-asset-management, is outside the PACE boundary but must be in-scope for both the architecture (#31) and even a first / minimum-viable prototype. In order to get started on a prototype, we will at least need a spreadsheet of "Components whose architecture is assessed", but in order to make even a spreadsheet realistic we'll need to learn what data is maintained in ITAM products (e.g., https://snipeitapp.com/). Hardware and software versions might or might not be included.  

## Is Hardware BOM within in PACE scope?
https://github.com/opencybersecurityalliance/PACE/issues/29
Hardware BOMs are currently out of scope. 

## What "query language(s)" should be used for PACE?
https://github.com/opencybersecurityalliance/PACE/issues/42


## Should pace "pick a winner" for PAR database?
https://github.com/opencybersecurityalliance/PACE/issues/43
Consensus is to not pick a winner.  Spcifying interfaces may way in on the implementation.


## Can there be more than one OCA PACE reference implementations?
https://github.com/opencybersecurityalliance/PACE/issues/44
Yes, there should be multiple implementations.  

