# Retrieve SBOM

Although this is a very straight forward use case -
to obtain the previously stored SBOM data -
there are many subtle variants.

The most obvious is to retrieve the SBOM in the same
format and serialization which was originally provided to PACE.
For example a CycloneDX JSON SBOM was collected
from a particular device,
and decision-maker
requests a CycloneDX JSON SBOM.

![retrieve_sbom_01](./Images/retrieve_sbom_01.png)

A similar use case is a Posture Evaluation System (PES)
requests that same CycloneDX JSON SBOM.

![retrieve_sbom_02](./Images/retrieve_sbom_02.png)

Some PACE systems will have the ability to transform
the format or the serialization of the SBOM.

There are 4 classes of transformations in this figure:

![retrieve_sbom_03](./Images/retrieve_sbom_03.png)

- S1 - convert between CycloneDx serializations (eg between JSON and XML)
- S2 - convert between SPDX serializations (eg between JSON and RDF)
- F1 - convert from CycloneDX to SPDX
- F2 - convert from SPDX to CycloneDX

Althought the commands remain identical as in the previous diagrams,
the flow may be different.

Architectural question - will this transformation be done
as part of the PAR or is it a PES function.
This text is proposing it is part of PAR function so that PAR is data only.
This means that when a transformation is required,
the flow would be:

![retrieve_sbom_04](./Images/retrieve_sbom_04.png)

All of the above is for the entire SBOM.
It is a separate use case for individual fields in the SBOM
to be requested instead of the entire SBOM.
Ie request 'data from the SBOM' instead of the entire SBOM.
It is also a separate use case to request evaluation of the data
from the SBOM.
