# TRE Actors and Roles

Drawing from a number of sources we can create a consolidated list of system actors and roles they 
can take in working with TREs. Different [TRE archetypes]() can have different relationships between
these roles, but the roles themselves are consistent across all archetypes.

As an example, a Data Manager role may be taken by an Information Governance actor, or in other archetypes
may be delegated or otherwise assigned to a Project Principal Investigator.

## Sources

We draw from the following sources:

 1. <a id="ref-1"> [DARE UK Federated Architecture Blueprint v2.2](https://zenodo.org/records/14192786), 
	especially section 4.2.
 2. <a id="ref-2"> [Francis Crick Institute LATTICE](https://doi.org/10.25418/crick.28759961.v2), 
	chapter 3.
 3. <a id="ref-3"> [UCL/SATRE Standard Architecture for TREs](https://zenodo.org/records/10053383), 
	the architectural model behind the SATRE specification v1.0.

## Identified actors and roles

### DARE UK FAB v2.2

From [[1]](#ref-1):

 * **Public**: 
   * **Data Provider**: In the TRE domain, the Public can take the role of Data Providers, ultimate providers 
	of their data for research in the public benefit.
 * **Researcher**: Researchers (actors) take on a number of roles within the overall federated system.
   * **Project Member**: A Researcher may become an approved and authorised member of one or more Projects, and 
	in that role (and in the context of these Projects) will interact with specially provided project 
	environments within one or more TREs. Access to data within a TRE is granted to a Researcher in their 
	role as a Project Member, on the basis of their individual project authorisations. 
   * **Job Submitter**: In contrast to the direct interaction of a Project Member, the Job Submitter role 
	interacts indirectly with TREs through externally accessible Job Submission and Software services.
	(Possibly a sub-role of Project Member.)  
   * **Catalogue Searcher**: The Catalogue Searcher role interacts with externally accessible data discovery 
	and catalogue services. In this role the Researcher need not be a member of an existing project, 
	and thus may not have approvals to access sensitive data of any sort. 
 * **Information Governance**: Information Governance (IG) is a shorthand for the team of people charged with 
	overseeing a TRE and the research that happens within it. The Information Governance actor takes 
	a number of data-related roles. They may also take the role of TRE Operator, or may delegate it.
   * **Data Manager**: This role covers a wide range of data management tasks within a TRE, from curating 
	and maintaining long-term copies of research-ready data, to receiving data extracts from other 
	Data Managers in other TREs, linking them and providing them onwards to research Project Members 
	within the TRE. The Data Manager role will typically work closely with the Data Custodian role. 
	(This role could be further broken down into finer-grained sub-roles.)
   * **Output Approver**: Output Approvers are responsible for checking any and all research outputs 
	to be released from the TRE to the “outside world” (rather than sent to another TRE). 
   * **Job Approver**: Job Approvers review computational jobs submitted by Researchers 
	(in their roles as Job Submitters) for their safety and suitability to run inside the Job Approver’s TRE.
 * **Indexers** and **Linkers**: Provide services to join different datasets together, particularly 
	individual-level datasets that need to be joined using individual-level keys. These roles may be a 
	subset of IG; certainly they are accountable to IG and to data controllers
* **Data Controller**: Responsible for guarding access to public data, complying with data protection 
	law and ethical guidance, and accountable to the public for the uses of their data
  * **Data Custodian**: In the TRE domain, Data Controllers take the role of Data Custodians, releasing 
	data approved for research to projects via TRE Data Managers. 
* **TRE Operator**: (actor) 
   * **TRE Operator**: (role) The TRE Operator runs the TRE technical service day-to-day. 
	This role may be taken by the Information Governance actor, or it may be delegated by them 
	to a different actor (the TRE Operator actor) under their direction. 
* **Federation Operator**: Responsible for running the technical services that connect TREs and 
	data services together to form \[a\] federation. This responsibility extends to all the security 
	controls required by the overall federation IG.


Notes:
 * 'Project' means a defined context for an approved research activity, including the Project Members involved, 
	information about the data they are authorised to use, the TRE that hosts it, its duration and so on. 
	A Project defines an authorisation context which provides a key piece of information for overall 
	\[federation\] governance.


### Crick LATTICE v2

From [[2]](#ref-2):

 * **Data Loader**: Has write privileges to the Data Library account to replicate 
	external data into the account but cannot create new objects within the 
	account. 
 * **Data Processor**: Can create new views and data objects from those already 
	within the account, but cannot add new data objects from outside 
 * **Data Sharer**: someone how is authorised to approve the share of data within the 
	account to other facilities on the same data fabric.
 * **Data Curator**: Has the ability to prepare data into a database within the 
	account, but cannot create any other data objects. 
 * **Experimenter / Investigator**: lie a data processor can create new data objects 
	but not add any external data to the space (this has to come through a sourcing 
	data loader account and shared to the Project account. 

Notes:
 * 'Data Library' means a data asset of interest to researchers, typically created as a 
	product of some earlier research project.
 * 'Data Library account' means some location in a digital environment authorised to process
	the Data Library data asset.
 * 'Project' means a research project wanting to use the pre-existing assets of one or more Data Libraries.
 * 'Project account' means some location in a digital environment authorised to process data assets
	shared to it from Data Library accounts.

### SATRE v1

From section [Roles in SATRE spec v1.0.0](https://satre-specification.readthedocs.io/en/latest/roles.html).

 * **Data Consumer**: (synonymous with Researcher) General term for any individuals who will be provided 
	access to data via a TRE.
 * **Project Manager**: The person in charge of coordinating other roles for the duration of a specific TRE project. 
 * **Project Team**: Refers to the team of data analysts and project manager(s) working on a specific project 
	that uses a TRE.
 * **Data Steward**: People who ensure data within a TRE is maintained and processed in ways useful to 
	data analysts, including providing data extracts. May also be known as Data Wranglers, Data Engineers or 
	Data Cleaners.
 * **Information Asset Owner**: General term for custodians or owners of a datasets, projects or other 
	information assets within a TRE. For example, the owner of a dataset who has liaised with a 
	TRE Operator on secure data ingress to the TRE.
 * **Output Checker**: People responsible for checking the disclosure risk of project outputs, before egress, 
	as part of the disclosure control process. 
 * **(TRE) Operator**: People responsible for the management of the TRE’s IT infrastructure and general processes 
	documented throughout the SATRE specification. Examples include carrying out data ingress/egress 
	and managing user access. TRE operators should expect to have access to documentation regarding all 
	processes they are required to carry out, developed by themselves or (in partnership with) the 
	TRE Developers. This documentation should be comprehensive and include troubleshooting steps.
 * **(TRE) Developer**: People responsible for building the software infrastructure that can be used as a TRE. 
	These could be Research Software Engineers, whose job involves applying professional software 
	engineering expertise to challenges in scientific research. Alternatively, these could be developers 
	who are contracted to build a TRE for a given institution or project. TRE developers include people 
	creating bespoke platforms catering to the specific requirements of a project or dataset, as well 
	as developers building generalisable solutions to TRE provision that can be configured based on 
	the research context.
 * **(TRE) Builder**: People responsible for carrying out the Infrastructure Deployment Process. This role 
	could be taken on by either the TRE Operators or the TRE Developers.
 * **Information Governance Manager**: People responsible for writing and/or compiling the correct operating 
	procedures and policies for the TRE.
 * **Quality Manager**: People responsible for ensuring the TRE is operating correctly, and all procedures 
	and policies are being followed by other roles and work effectively.
 * **Top Management**: People who lead and control an organisation at the highest level. 
	This definition is taken from ISO 9000:2015 and in this context refers to the most senior 
	governance official who own the risks associated with TRE research, can make decisions and 
	allocate resources.
 * **Data Protection Manager**: People responsible for data protection at the organisation hosting the TRE.
 * **Auditor**: General IT term for people who evaluate an organisation’s IT systems on whether they meet 
	technology or cybersecurity regulatory requirements. For TREs, this may include requirements around 
	sensitive data handling and information security controls. Auditors can be internal, or external 
	people working for a consulting firm.
 * **Lay Panel**: Members of the public charged with oversight of TRE operational decisions on behalf of 
	parties affected by data usage.
 * **Data Subject**: People who are identifiable by data being used for research, e.g. patients in healthcare


## Mapping of actors and roles

### Notes

 * Not all actors and roles from [[3]](#ref-3) are currently represented below.
 * "Information Governance" was originally an actor in both [[1]](#ref-1) and [[3]](#ref-3). We remodel it as a role.
 * We regard "Researcher" and "Data Consumer" as synonyms and use the former as the principal user actor.
 * We regard "Project Team" as a collective for "Project Member" and use the latter as the name for the specific role.

![Actors and roles](Images/TRE_Actors_Roles.drawio.png)

