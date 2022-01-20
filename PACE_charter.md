# OCA Subproject Charter for Posture Attribute Evaluation and Collection (PACE)
This information is a copy of the forms submitted to the OCA PGB
to initiate the PACE subproject.
It was copied from the attachment to
https://lists.oasis-open-projects.org/g/oca-pgb/topic/posture_attribute_collection/86296436?p=,,,20,0,0,0::recentpostdate/sticky,,,20,2,0,86296436,previd=1634934194220224110,nextid=1632463213447063679&previd=1634934194220224110&nextid=1632463213447063679

### Project Name
Posture Attribute Evaluation and Collection (PACE)

### Project Use Case (Value in one sentence)
Reference and/or production-ready code demonstrating
posture assessment of computing resources
using a communication fabric and multiple payload formats.

### Project Description (Detailed)
Posture assessment generally consists of understanding,
for a given computing resource (or set of computing resources),
software load, composition of that software load, patch levels,
vulnerability (implied to be software vulnerability), and configuration state.
Together, these attributes of a computing resource
represent its cybersecurity posture.
PACE will leverage and/or contribute to
Open Cybersecurity Alliance (OCA) Ontology and OpenC2 for command and control.
PACE will be an instantiation of the
IETF Security Automation and Continuous Monitoring (SACM) group’s architecture.

Initially, the project intends to focus on building the
pipes and connectors between components, leveraging existing
payload formats such as SCAP/OVAL, SBOM, etc.
Later phases of the project may consider updating
payload formats to include other types (i.e. NETCONF/RESTCONF, InSpec, Puppet, Ansible, etc.)

### Project value to end user
The intent of this project is to begin making available
production-ready code that software vendors can leverage for posture assessment.
This will be community-maintained code that no one vendor needs to duplicate.
End users (i.e. users who interact with posture assessment software)
will benefit by having more software available that is
interoperable out of the box, which reduces integration costs,
and helps them get (and keep) their security program running.

Posture attributes will be stored in repositories that can be accessed by non-posture-assessment software.
An example of this would be a threat hunting/intelligence software
that needs to understand what state a particular configuration item
had at time t for a given resource.
Provided that attribute is collected as part of posture assessment,
the value is known and available to other security program workflows.

The expected extensibility of the project to accommodate
similar security program workflow details
(i.e. posture assessment of network devices, mobile devices,
cloud environments, etc.)
will continue to add value not only for software vendors,
but end users as well –
we want to maximize the ability to efficiently expand coverage.

### Project contribution to OCA goals and [mission](https://opencybersecurityalliance.org/mission/)
The PACE project will advance the state of the art for posture assessment
by supporting a modern architecture enabling
such software to interoperate with other software used
in the course of operating a security program.
Additionally, the project will contribute to the OCA Ontology,
thereby empowering other projects to integrate
with posture assessment capabilities.

### Why, in your opinion, is the OCA the most appropriate host for this project?
Being straightforward, PACE is a revitalization and replacement
of the SCAPv2 Endpoint Data Collection (EDC) effort
to further incorporate open standards into
the development process of posture assessment.
The EDC work was intended to be an instantiation of the SACM architecture,
and now under PACE, will extend the effort to review
OpenC2 actuator profiles necessary to invoke collection and evaluation.
The PACE project aligns well with OCAs mission and has the same goals in mind.

### What support are you looking for from OCA members?
Candidly, feedback and participation.
We do not expect OCA to provide resources,
but we do expect the other communities to be responsive
when we engage with them (within reason).
Part of the goal we have for PACE is to have the
implementation inform the specification,
meaning we need the implementation (and therefore feedback from others)
to help drive what we write as part of the SACM architecture.

### Is this an existing project? If so, link to web page / repo
Yes, though it is in its infancy.
We already have an OCA repository here.
The IETF SACM Architecture draft is here.

### Does this project integrate with any existing OCA projects or deliverables?
PACE uses OpenDXL, intends to use and contribute to the OCA Ontology,
and is interested in integration points with other OCA projects.

### Project Implementation Details
Please see the IETF SACM Architecture draft here.

### Existing / Proposed Open Source License (<link to approved OP licenses>)
TBD

### Implementation Language(s)
PACE is not tied to any one specific language.
At present both Python and Java/Groovy are utilized,
depending on the specific component.

### Dependency Technologies
None. PACE uses OpenDXL as a message fabric
but is not inherently tied to OpenDXL.
Similarly, the project intends to integrate
with many data collection and analytic tools
but will not be dependent upon any individual tool.

## Project Management & Governance

### Primary Project Sponsor(s)
- Center for Internet Security
- NSA
- McAfee

### How will this project be resourced on an ongoing basis?
The project currently has a small team of developers,
pulled from a diverse group of interested organizations.
This team is expected to be persistent/durable for the foreseeable future.
Additionally, we intend to leverage OCA (and sponsor)
marketing/engagement efforts to recruit contributors.

### What is the scope (expected lifespan of this project’s development lifecycle)?
Presently unknown.
Best guess for Phase I (laying pipes and building connectors)
is by the end of the first half 2022,
and Phase II by the same time in 2022.
We hope to be able to bring this timeline in,
as able, and will also push it out if necessary.
