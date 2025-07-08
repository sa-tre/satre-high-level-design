# Governance Extension for FRIDGE

**FRIDGE: Federated Research Infrastructure by Data Governance Extension**

Artificial Intelligence (AI) models can help enhance research to solve complex problems in society, but this requires access to sensitive data on large-scale, shared AI supercomputers, like the UK’s AI Research Resource (AIRR).

## 1. Purpose

Using sensitive data to develop AI models involves carefully isolating parts of large AI supercomputers as Trusted Research Environments (TREs) so that only approved researchers can safely access them for their research. FRIDGE aims to explore this possibility by creating a ready-to-use TRE that meets the SATRE specification (developed as part of the DARE UK Phase 1 Driver Projects and enhanced by TREvolution) on the AIRR. This will enable the secure use of sensitive data to develop AI models for research that benefits the public while ensuring strict information governance.

By establishing a robust governance framework, FRIDGE will enable AIRR to host secure TREs, ensuring that large-scale AI research can operate within secure, compliant environments and providing a testbed for other TREvolution capabilities.

This document sets out the high-level architecture for this extended governance in order to clearly distinguish between areas of responsibilities and provide a framework for the federated computation delivered by FRIDGE.

## 2. FRIDGE Architecture

![Zoomed Out Architecture](./FRIDGE_Images/Fridge_Zoomed_Out.drawio.svg)

The above view shows the highest-level architecture for FRIDGE consisting of:

- A front door TRE where the researcher operates. There is an interface TRE software for analysis and research data. The front door TRE will provide the capabilities and contain components found in the [SATRE Architecture](https://satre-specification.readthedocs.io/en/stable/architecture.html).
- A FRIDGE TRE where large scale AI research is worked on. Within the FRIDGE TRE there is a job processor, super computing hardware (AI) to provide compute capacity and an analysis-ready copy of the research data.

The researcher works within the front door TRE and submits jobs and receives results from the FRIDGE TRE. 

# 2. Roles

Roles Catalogue

|Role | Source / Definition | Specialization|
|------|---------|--------------|
|Data Consumer (synonymous with Researcher)| [SATRE](https://satre-specification.readthedocs.io/en/latest/roles.html#project-roles)| NA |
|Job submitter | [DARE UK Federated Blueprint](https://zenodo.org/records/14192786)| Within the scope of the FRIDGE architecture this role requires the data consumer role |
|TRE Operator Organisation | The lead organisation providing the TRE all Infrastrcture Management and Governance defined in [SATRE](https://satre-specification.readthedocs.io/en/latest/roles.html#project-roles)  sit within this org.| NA
|Top Management | [SATRE](https://satre-specification.readthedocs.io/en/stable/roles.html#governance-roles) | Within the scope of FRIDGE this role the "Organisation" covered by top management includes the extended governance boundary.|
|Hosting Organisation | The organisation which provides the platform on which the TRE is hosted | There are specializations:<br>* **Public Cloud** hosting org. (E.G. AWS, GCP, Azure)<br>* **Private Cloud** Cloud provide by the TRE Operator Org.<br>* **National Facility** (E.G. [AIRR](https://www.ukri.org/news/300-million-to-launch-first-phase-of-new-ai-research-resource/))




## 2. Boundaries

The figure below shows the external boundary FRIDGE and internal boundaries between component parts of the system.

![FRIDGE Boundaries](./FRIDGE_Images/Fridge_Boundaries.drawio.svg)

## 2.1 Governance Boundary

**Top Management is accountable for the governance boundary**. The governance boundary denotes the scope of risk and control across the entire system. This boundary may be synonymous with an ISO 27001 scope or similar and possibly commonly an extension of an existing scope defined by the Front Door TRE Hosting organisation. The extension of an existing scope is likely to require changes to the information governance framework as shown below.

## 2.2 Front Door TRE Hosting Boundary

**The hosting organisation (Public or Private Cloud) is accountable for the TRE Hosting Boundary**. The TRE hosting boundary is responsible for the "Security of the Cloud" and therefore responsible for protecting the infrastructure that runs all of the services offered in the AWS Cloud. This infrastructure is composed of the hardware, software, networking, and facilities. See [AWS](https://aws.amazon.com/compliance/shared-responsibility-model/), [Azure](https://learn.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility), [GCP](https://cloud.google.com/architecture/framework/security/shared-responsibility-shared-fate) for public cloud. UCL's TRE on private cloud supports a similar [shared responsibility model](https://isms.arc.ucl.ac.uk/rism02-roles_and_responsibilities/#6shared-responsibility-model) with the private cloud being part of the "UCL supporting Services".

## 2.3 Front Door TRE Boundary

**The hosting organisation (Public or Private Cloud) is accountable for the TRE Hosting Boundary**. 