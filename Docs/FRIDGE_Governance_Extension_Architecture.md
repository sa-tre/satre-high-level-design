# Governance Extension for FRIDGE

**FRIDGE: Federated Research Infrastructure by Data Governance Extension**

Artificial Intelligence (AI) models can help enhance research to solve complex problems in society, but this requires access to sensitive data on large-scale, shared AI supercomputers, like the UK’s AI Research Resource (AIRR). FRIDGE will leverage the compute capacity provided by AI supercomputers by extending the security management system from a primary of "Front Door" TRE onto these facilities.

## 1. Purpose

Using sensitive data to develop AI models involves carefully isolating parts of large AI supercomputers as Trusted Research Environments (TREs) so that only approved researchers can safely access them for their research. FRIDGE aims to explore this possibility by creating a ready-to-use TRE that meets the [SATRE specification](https://satre-specification.readthedocs.io/en/stable/) (developed as part of the DARE UK Phase 1 Driver Projects and enhanced by TREvolution) on the AIRR. This will enable the secure use of sensitive data to develop AI models for research that benefits the public while ensuring strict information governance.

This document sets out the high-level architecture for this extended governance in order to clearly distinguish between areas of responsibilities and provide a framework for the federated computation delivered by FRIDGE.

## 2. FRIDGE Architecture

![Zoomed Out Architecture](./FRIDGE_Images/Fridge_Zoomed_Out.drawio.svg)

The above view shows the highest-level architecture for FRIDGE consisting of:

- A front door TRE where the researcher operates. There is an interface TRE software for analysis and research data. The front door TRE will provide the capabilities and contain components found in the [SATRE Architecture](https://satre-specification.readthedocs.io/en/stable/architecture.html).
- A FRIDGE TRE where large scale AI compute is available. Within the FRIDGE TRE there is a job processor, super computing hardware (AI) and an analysis-ready copy of the research data.

The researcher works within the front door TRE and, if they have the job submitter role, can send jobs to and receives results from the FRIDGE TRE. 

## 2. Roles

Roles Catalogue

|Role | Source / Definition | Specialization|
|------|---------|--------------|
|Data Consumer (synonymous with Researcher)| [SATRE](https://satre-specification.readthedocs.io/en/latest/roles.html#project-roles)| NA |
| Information Asset Owner | [SATRE](https://satre-specification.readthedocs.io/en/stable/roles.html#data-management-roles)| NA
|Job submitter | [DARE UK Federated Blueprint](https://zenodo.org/records/14192786)| Within the scope of the FRIDGE architecture this role requires the data consumer role |
|TRE Operator Organisation | The lead organisation providing the TRE all Infrastrcture Management and Governance defined in [SATRE](https://satre-specification.readthedocs.io/en/latest/roles.html#project-roles)  sit within this org.| NA
|Top Management | [SATRE](https://satre-specification.readthedocs.io/en/stable/roles.html#governance-roles) | Within the scope of FRIDGE this role the "Organisation" covered by top management includes the extended governance boundary.|
|Hosting Organisation | The organisation which provides the platform on which the TRE is hosted | There are specializations:<br>* **Public Cloud** hosting org. (E.G. AWS, GCP, Azure)<br>* **Private Cloud** Cloud provide by the TRE Operator Org.<br>* **National Facility** (E.G. [AIRR](https://www.ukri.org/news/300-million-to-launch-first-phase-of-new-ai-research-resource/))




## 2. Boundaries

The figure below shows the external boundaries for the extended governance of FRIDGE and the internal boundaries between component parts of the system.

![FRIDGE Boundaries](./FRIDGE_Images/Fridge_Boundaries.drawio.svg)

### 2.1 Governance Boundary

**Top Management is accountable for the governance boundary**. The governance boundary denotes the scope of risk and control across the entire system. This boundary may be synonymous with an ISO 27001 scope or similar and commonly an extension of an existing scope defined by the Front Door TRE Hosting organisation. The extension of an existing scope is likely to require [changes to the information governance framework](FRIDGE_Governance_Extension_Architecture.md#3-governance-of-the-fridge-federation) as shown below.


### 2.2 Front Door TRE Hosting Boundary

**The hosting organisation (Public or Private Cloud) is accountable for the TRE Hosting Boundary**. The TRE hosting boundary ensures the security of the underlying cloud platform hosting the TRE. The hosting org is therefore responsible for protecting the infrastructure that runs all of the cloud services. This infrastructure is composed of the hardware, software, networking, and facilities. See [AWS](https://aws.amazon.com/compliance/shared-responsibility-model/), [Azure](https://learn.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility), [GCP](https://cloud.google.com/architecture/framework/security/shared-responsibility-shared-fate) for public cloud. UCL's TRE on private cloud supports a similar [shared responsibility model](https://isms.arc.ucl.ac.uk/rism02-roles_and_responsibilities/#6shared-responsibility-model) with the private cloud being part of the "UCL supporting Services".



### 2.3 Front Door TRE Boundary

**The TRE Operator Organisation is accountable for the Front Door TRE Boundary**. The Front Door TRE boundary ensures the security of the TRE. The boundary is made up of technical controls for capabilities such as [Infrastructure Management](https://satre-specification.readthedocs.io/en/stable/pillars/computing_technology.html#infrastructure-management) and process controls for [study management](https://satre-specification.readthedocs.io/en/stable/pillars/information_governance.html#study-management).

### 2.4 TRE Project Boundary

**The Project boundary responsibility is shared between the TRE operator organisation and the Information Asset Owner**. Applicable technical controls as documented in the [Computing Technology and Information Security pillar](https://satre-specification.readthedocs.io/en/stable/pillars/computing_technology.html#computing-technology-and-information-security) of SATRE are the responsibility of the TRE operator organisation. Controls within the Information Governance pillar of SATRE will largely be the responsibility of the Information Asset Owner.

The degree to which these controls are delegated down to research teams themselves will be dependant on the ["TRE Archetype"](https://github.com/sa-tre/satre-high-level-design/blob/main/Docs/TRE_Architypes.md). [Data provider archetypes](https://github.com/sa-tre/satre-high-level-design/blob/main/Docs/TRE_Architypes.md#21-data-provider-archetype) will take a much greater role in ensuring the security of the project boundary as they are the TRE platform and data provider. [Bring your own data archetype](https://github.com/sa-tre/satre-high-level-design/blob/main/Docs/TRE_Architypes.md#22-bring-your-own-data-archetype) operators delegate the security fo the project down to the the project team (usually a primary investigator).

### 2.5 FRIDGE TRE Hosting Boundary

<!--Need to add-->

### 2.6 FRIDGE TRE Boundary

**The FRIDGE TRE boundary responsibility is shared between the TRE operator and the FRIDGE Hosting Organisation.** 

Only part of the hosting organisation is within the governance boundary and therefore the TRE(s) inherit residual risk from the hosting organisation. Where there are shared components additional controls must be applied by the TRE operator organisation. For example encryption applied and managed by the TRE operator organisation applied to shared storage.

Information and data, accounts and identity, encryption and applications are the responsibility of the TRE organisation with network controls and resource allocation shared between the TRE operator and the FRIDGE hosting organisation.

![FRIDGE TRE Boundary Shared Responsibility Model](./FRIDGE_Images/Fridge_Shared_Responsibility_Model.drawio.svg)

The TRE operator is responsible for defining the requirements for resource allocation and network controls and the FRIDGE hosting organisation is responsible for ensuring the correct implementation. An agreed processes must be established and quality data be created and maintained to ensure manual and automated changes are correctly implemented. 


### 2.7 Code Repository Boundary

<!--Need to add-->

### 2.8 Private Network Boundary

<!--Need to add-->

## 3. Governance of the FRIDGE Federation

As the governance for the front door TRE is extended into the FRIDGE hosting organisation the security of the overall system may be affected by changes to the hosting organisation's environment. For that reason an ongoing operational management group should be instantiated to ensure the concerns of the TRE operator organisation are considered. 

![IG Framework](./FRIDGE_Images/FRIDGE_IGFramework.drawio.svg)

