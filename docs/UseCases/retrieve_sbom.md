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
- if a transformation was necessary (eg json to xml, or SPDX to CycloneDX) that is a PES function instead of a pure data retrieval
- there are security issues with direct access to the PAR data store. These are mitigated if the authentication/authorization resides entirely within the PCS or PES components

The first issue is particularly relevant to the architectural flow
because the sender must know where to direct the command and it
shouldn't be dependent on the contents of the command
(ie whether it is requesting data in same format/serialization
originally received by PAR).
Therefore the following flow is proposed even for the
'no transformation' case.

<p align="center">Figure 1</p>

![retrieve_sbom_01](./Images/retrieve_sbom_01.png)

A similar use case is a Posture Evaluation System (PES)
requests that same CycloneDX JSON SBOM
(ie original format and serialization).

<p align="center">Figure 2</p>

![retrieve_sbom_02](./Images/retrieve_sbom_02.png)

## Format/serialization Conversions
Some PACE systems will have the ability to transform
the format or the serialization of the SBOM.
The flows would be the same as in Figures 1,2.

There are 4 classes of transformations in figure 3:

<p align="center">Figure 3</p>

![retrieve_sbom_03](./Images/retrieve_sbom_03.png)

Descriptions of each transformation follow.
Examples of tools that can do each transformation are listed.
It is not an exhaustive tool list
and no validation has been done.
Some tools are open source and some are commercial.

- cdx2cdx - convert between CycloneDx serializations (eg between JSON and XML). Examples of tools which can do this include:
   + cyclonedx-cli https://github.com/CycloneDX/cyclonedx-cli
   + Cybeats SBOM Studio https://www.cybeats.com/sbom-studio
   + ?
- spdx2spdx - convert between SPDX serializations (eg between JSON and RDF). Examples of tools that can do this include:
   + SPDX Online Tool https://tools.spdx.org/app/convert/
   + Cybeats SBOM Studio https://www.cybeats.com/sbom-studio
   + ?
- cdx2spdx - convert from CycloneDX to SPDX. Examples of tools that can do this include:
   + cyclonedx-cli https://github.com/CycloneDX/cyclonedx-cli
   + Cybeats SBOM Studio https://www.cybeats.com/sbom-studio
   + ?
- spdx2cdx - convert from SPDX to CycloneDX. Examples of tools that can do this include:
   + cyclonedx-cli https://github.com/CycloneDX/cyclonedx-cli
   + swiftBOM https://democert.org/sbom/
   + Cybeats SBOM Studio https://www.cybeats.com/sbom-studio
   + ?

## Subset of SBOM data

All of the above is for the entire SBOM.
It is a separate use case for individual fields in the SBOM
to be requested instead of the entire SBOM.
Ie request 'data from the SBOM' instead of the entire SBOM.
See NeedToFillIn.

## SBOM evaluation
It is also a separate use case to request evaluation of the data
from the SBOM.
See NeedToFillIn.
