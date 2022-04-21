# Retrieve SBOM

Although this is a very straight forward use case -
to obtain the previously stored SBOM data -
there are many subtle variants.

## Retrieve SBOM as provided
The simplest, most obvious retrieval case
is to retrieve the SBOM in the same
format and serialization which was originally provided to PACE.
For example a CycloneDX JSON SBOM was collected
from a particular device,
and decision-maker
requests that CycloneDX JSON SBOM.

Although direct access to the PAR would meet the need
for this simple retrieval,
there are several issues:
- if a transformation was necessary (eg json to xml, or SPDX to CycloneDX), that is a PES function instead of a pure data retrieval
- there are security issues with direct access to the PAR data store. These are mitigated if the authentication/authorization resides entirely within the PCS or PES components

The first issue is particularly relevant to the architectural flow
because the sender must know where to direct the command and it
shouldn't be dependent on the contents of the command
(ie whether it is requesting data in same format/serialization
originally received by PAR).
Therefore the following flow is proposed even for the
'no transformation' case.

<p align="center">Figure 1</p>

![retrieve_sbom_01](./Images/retrieve_sbom_02.png)

A similar use case is a Posture Evaluation System (PES)
requests that same CycloneDX JSON SBOM
(ie original format and serialization).

<p align="center">Figure 2</p>

![retrieve_sbom_02](./Images/retrieve_sbom_01b.png)

## Format/serialization Conversions
Some PACE systems will have the ability to transform
the format or the serialization of the SBOM.

<p align="center">Figure 3</p>

![retrieve_sbom_02](./Images/retrieve_sbom_02.png)

There are 4 classes of transformations in this figure:

<p align="center">Figure 4</p>

![retrieve_sbom_03](./Images/retrieve_sbom_03.png)

- S1 - convert between CycloneDx serializations (eg between JSON and XML)
- S2 - convert between SPDX serializations (eg between JSON and RDF)
- F1 - convert from CycloneDX to SPDX
- F2 - convert from SPDX to CycloneDX

Although the commands remain identical as in the previous diagrams,
the flow may be different.

There are potential security issues with direct access
to the PAR in the first figure above.
Thinking at the moment is to limit access to the PAR
to only the PCS and PES.
This would result in the simple case above being handled the
same way as a PES use case.

Architectural question - will this transformation be done
as part of the PAR or is it a PES function.
This text is proposing it is part of PAR function so that PAR is data only.
This means that when a transformation is required,
the flow would be:

<p align="center">Figure 5</p>

![retrieve_sbom_04](./Images/retrieve_sbom_04.png)

## Retrieve SBOM as provided - reprise
The concept of direct access
to the PAR API
from outside the PACE system
is still open to debate.
Reasons to consider always using the architecture
in Figure 5 (even for the case of Figure 1)
If the authentication/authorization resides entirely
with the PCS or PES components,
then the simple retrieve SBOM case of Figure 1
would use the architecture of Figure 3.

## Subset of SBOM data

All of the above is for the entire SBOM.
It is a separate use case for individual fields in the SBOM
to be requested instead of the entire SBOM.
Ie request 'data from the SBOM' instead of the entire SBOM.
See NeedToFillIn.

## SBOM evaluation
It is also a separate use case to request evaluation of the data
from the SBOM.
See NeedToFillIn/
