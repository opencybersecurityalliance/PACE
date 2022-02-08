# PACE Architecture

PACE systems have 3 components:
- Posture Collection Service/System (PCS)
- Posture Attribute Repository (PAR)
- Posture Evaluation Service/System (PES)

The PCS is used in the use cases which collect posture attributes
and store those attributes in the PAR.

The PES is used in those use cases which obtain posture attributes
from the PAR and analyze the data.
The results of the analysis may be returned to the requesting
system or may be stored in the PAR as another type of attribute.

The PAR stores posture attributes.

Several PACE architectures are possible,
depending on an organizations needs.

## PACE Component Architecture
![Figure 1](./pace_arch_1.png)

In this architecture,
the 3 components sit on the integration bus
directly and interact directly
with the decision making and sensing components.
This architecture allows for different vendors/implementations
for the different components.
With only a single instantiation of each component
(alternatives in later section),
each component must handle all types of posture attributes.

## Monolithic PACE Architecture
![Figure 2](./pace_arch_2.png)

In this architecture,
the PACE system as an whole entity
sits on the integration bus.
PCS, PES, and PAR are not directly exposed.
However, if the PACE system implements all of the interfaces
in the previous section,
then this would be transparent to rest of the system.
This architecture might be favored by certain vendors
with an integrated solution.
Similar to the previous section,
with only a single instantiation
(alternatives in later section),
each component must handle all types of posture attributes.

## Multi-PACE
![Figure 3](./pace_arch_3.png)

It is unrealistic for a single component
or a single integrated PACE system
to handle all possible posture attributes.
Therefore many organizations instantiating PACE
will have a mix of multiple component instantiations
and multiple monolithic PACE systems.

One reason might be different attributes
(e.g one for SBOM/VEX/NVD, one for situational awareness,
and one for data classification).

Another reason might be different vendors/open-source-projects.
P1-P14 are fourteen different products (e.g. from a vendor)
or projects (e.g. built from open source).

Yet another reason might be geographical.
E.g. One PCS for each of five regions.

In Figure 3 above, there are five PCS, four PAR, three PES and
two monolithic PACE systems,
each with there own interface to the integration bus.
Note the monolithic systems (P1,P2) interface as if they
were component systems as the monolithic API is just the
combined PCS/PAR/PES APIs.
