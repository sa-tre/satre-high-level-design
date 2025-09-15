# TRE Provider Archetypes
## 1. Purpose

Across the UK there are a wide variety of TREs. the SATRE [architecture and specification](https://satre-specification.readthedocs.io/en/stable/index.html) defines commonalities for the capabilities they deliver and the controls used to do so safely.

The following patterns describe the two primary TRE provider archetypes including the variation in the roles and responsibilities of each.

1. Data Provider archetype
2. Bring your own data archetype

## 2. Definitions

Definition of zones will be added to the [UK TRE glossary](https://glossary.uktre.org/en/latest).
<!-- include any definitions of elements in the design. Wherever possible add links to external definitions in in places like the glossary https://glossary.uktre.org/en/latest/ or SATRE https://satre-specification.readthedocs.io/en/stable/ -->

## 3. Pattern 1 - Data Provider Archetype

The first is most commonly owner by a single data provider, providing the data and the environment for researchers to use for analysis. Examples of such TREs include the NHS SDEs, ONS secure research service and the UKDS SecureLab. Such TREs generally provide a curated data set to researchers and a secure environment to work within. These TRE providers have greater responsibility for ensuring all 5 of the 5 Safes including Safe Data (e.g. de-identification of source data sets and curated extracts) and Safe Outputs (e.g. providing output checking service).

![data provider archetype](/Docs/Images/Data_Provider.drawio.svg)
*The project boundary only exists within the research analytics zone.*


### Responsibility Model

![Data provider responsibility model](/Docs/Images/TREvolution_Archetypes-Data-Provider-responsibility_model.drawio.svg)


## 4. Pattern 2 - Bring Your Own Data Archetype

The second archetype is commonly used in Universities and operates under a “bring your own data” model. Researchers acquire data from a 3rd party or generate data through their research (or both) and use the TRE to store, manage and process those data. Such TREs provide segregated secure storage (a data management zone) for each project to support medium-long term storage and retention of the source data.

In such TREs the TRE provider (often research IT within the university) is only responsible for the safe setting. The wider organization is responsible for the other 4 safes with these usually delegated in part to the research teams themselves. Examples of such TREs are UCL ARC TRE, Turing Data Safe Haven and Kings College’s CREATE platform.

![bring your own data archetype](/Docs/Images/Bring_your_Own_Data.drawio.svg)
*The project boundary spans both the secure data and research analytics zones.* 

### Responsibility Model

An information asset owner (usually the PI) is accountable for the management of the source data, any extracts and the research conducted. Safe Outputs from the environment may also be under the control of the asset administrator or their delegate.

![BYOData responsibility model](/Docs/Images/TREvolution_Archetypes-BYO_data_responsibility_model.drawio.svg)


