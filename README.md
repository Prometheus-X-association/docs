# Project Overview
The Prometheus-X project revolves around the concept of a human-centric data ecosystem, where individuals have full control over their data and their destiny. The goal is to provide tools that empower people and organizations, enabling them to securely share and utilize data in a trustworthy manner. Prometheus-X aims to establish an open and decentralized data sharing infrastructure at scale, serving as a digital commons for this purpose.

The project focuses on creating an open ecosystem that facilitates data and service sharing, starting with use cases in the education and skills sector. Prometheus-X aims to provide a marketplace of interoperable technologies, offering data empowerment, intermediation, storage, and processing capabilities. Participants in the ecosystem will have the ability to share data in a trustworthy manner, independent of any single entity's control.

All building blocks within the Prometheus-X ecosystem adhere to the same trust and interoperability specifications, following the guidelines set out by the International Data Spaces Association (IDSA) and GAIA-X. The project provides open-source building blocks that enable anyone to deploy and operate these services. Prometheus-X does not operate these services directly, it only ensures a fair and common governance and funding of the necessary building blocks. This approach ensures the absence of an unchangeable dominant player, fostering the creation of open ecosystems while maintaining trust and transparency.

# Goals and objectives
The primary objective of this technical specifications document is to provide a comprehensive framework and guidelines for the creation of Prometheus-X's building blocks. By documenting the necessary technical details, functionalities, and requirements, this document serves as a resource for the development, implementation, and maintenance of the catalog, contract and consent management building blocks needed to deploy human-centric data ecosystems.

## Enabling the creation of Human-Centric Data Spaces
The technical specifications outlined in this document aim to facilitate the establishment of human-centric data spaces thanks to Prometheus-X's building blocks. These data spaces act as a secure and controlled environment where individuals can manage and control their own data. 

## Establishing Data Ecosystems
One of the key objectives is to enable the creation of data ecosystems within the personal data space, following the best practices and guidelines established by IDSA and GAIA-X. These ecosystems foster the secure sharing and utilization of data among individuals and trusted organizations. The technical specifications document outlines the necessary components, interfaces, and standards to ensure the interoperability and smooth functioning of data ecosystems within the data space.

## Implementing Catalogs for Data Sharing
To facilitate efficient data management in line with IDSA and GAIA-X principles, the technical specifications document provides guidelines for the implementation of catalogs within the data space. Catalogs serve as repositories of data ecosystems, datasets and services, enabling organizations to organize, categorize, and search for specific data and service resources as well as join and browse data ecosystems. The document specifies the required functionalities for the implementation of a catalog.

## Enabling Data Sharing Contractualization
Prometheus-X emphasizes the importance of data sharing contractualization to ensure trust and compliance in data exchanges. This document outlines the necessary components and functionalities to support data sharing contractualization within the data spaces. It provides guidelines for the implementation of contract registries, contract generation, policy enforcement along with standards to follow.

## Incorporating End-User Consents for Data Exchanges
Respecting individual privacy and consent is a core principle of Prometheus-X. This document guides the implementation of consent management functionalities within the personal data space. It defines the necessary components, consent verification processes, and revocation services to ensure that data exchanges occur with explicit end-user consent.

# Scope
## Scope of the project
The scope of the project outlines the boundaries and extent of the work involved in creating the data space. It encompasses the specific areas and functionalities that will be addressed in the creation of a Data Ecosystem.

### Catalog
The scope covers the development of catalog functionality within the data space. The catalog will provide features for the management of data ecosystems, datasets & services. These include resource registration, formats and standards to follow for resources, resource discovery and ways to communicate with the catalog components.

### Contract
The project includes the implementation of contract functionalities to support data sharing contractualization within the data space. This involves defining the necessary components, interfaces and mechanisms for creating, managing and enforcing data sharing agreements within the data space.

### Consent
The scope encompasses the incorporation of end-user consent management capabilities within the data space. This includes designing and implementing features for obtaining, verifying, revoking and logging consent for data exchanges.

## Constraints, limitations & assumptions to consider
While developing the data space, certain constraints, limitations and assumptions need to be considered.

### Regulatory Compliance
The project must comply with applicable data protection regulations, such as the General Data Protection Regulation (GDPR) and the Data Governance Act (DGA) in the European Union. The technical specifications and implementation should align with these regulations to ensure privacy and data protection.

### Interoperability
To promote seamless data sharing, the personal data space should be designed with interoperability in mind. It should support standard data formats, protocols, and interfaces to facilitate compatibility with external systems and enable smooth integration with other data ecosystems.

### Scalability
The personal data space should be designed to handle varying scales of data and user demands. Considerations should be made to ensure the system's scalability, allowing it to accommodate increasing volumes of data and user interactions without compromising performance or functionality.

### Security and Privacy
The project must prioritize robust security measures to protect the personal data stored within the personal data space. This includes implementing encryption, access controls, authentication mechanisms, and auditing functionalities to ensure data confidentiality, integrity, and availability.

### User Experience
The personal data space should be designed with a user-centric approach, focusing on providing a seamless and intuitive user experience. Considerations should be made to ensure usability, accessibility, and user satisfaction throughout the design and implementation process.

### Other limitations
The Technical Specifications document primarily focuses on the Catalog, Contract, and Consent aspects of the system. While aspects related to identity, such as Decentralized Identifiers (DIDs), Verifiable Credentials (VCs), and other protocols, are mentioned in the technical details, this document does not delve into the comprehensive details of these identity-related components. The emphasis remains on providing detailed information about the Catalog, Contract, and Consent functionalities within the system.

# Functional requirements
The data space forms the foundation for secure and interoperable data sharing among participants. It enables individuals and organizations to connect, collaborate, and exchange data in a trusted and efficient manner. By leveraging the functionalities of the data ecosystem catalog, contract, and consent, participants can unlock the full potential of data-driven collaborations while adhering to governance rules and obtaining explicit end-user consents.

## Data Ecosystem

### Describe a Data Ecosystem
An ecosystem administrator, in accordance with the SITRA Rulebook, is required to properly describe a data ecosystem. The Sitra Rulebook serves as a comprehensive governance framework that describes an organization’s legal, business, technical and governance principles within a data ecosystem. By incorporating the guidelines outlined in the SITRA Rulebook, the ecosystem administrator can provide detailed documentation that describes the governance, business and value of the data ecosystem, along with the purposes, goals and requirements.

Following the SITRA Rulebook guidelines ensures that organizations have a standardized framework in place for data governance, making it easier to establish and maintain effective data ecosystems. Additionally, it emphasizes the importance of end-user consent in data sharing within the data ecosystem, as well as the need for business or client-related justifications when sharing data.

### Defining the needs of a Data Ecosystem
The system allows the data ecosystem orchestrator to define the specific needs and requirements of the data ecosystem. This functionality involves identifying the types of data, services and participants that are essential for the functioning of the ecosystem.

### Setting Roles and Responsibilities
The system provides the data ecosystem orchestrator with the ability to define and assign roles and responsibilities within the ecosystem. This ensures clarity regarding the obligations, privileges and scope of each participant’s role. Additionally, the data ecosystem orchestrator can access a database of standardized roles & obligations that are pre-set, enabling them to easily configure and assign these roles to participants. This database serves as a valuable resource, offering a collection of established roles and corresponding obligations that can be readily utilized, reducing the complexity and effort required for role assignment and configuration.

### Manage Accession Requests
The data ecosystem orchestrator should be able to manage requests from entities seeking to join the data ecosystem. This functionality includes implementing a review and approval process based on predefined criteria and compatibility with the ecosystem’s objectives.

## Catalog

### Registering Services and Data Offerings
Entities, such as service providers and data providers, have the capability to register their services and data offerings within the Catalog. This functionality enables these entities to describe and provide detailed information about their services, including terms and conditions, technical specifications, and other relevant details. By registering their offerings in the catalog, entities contribute to the ecosystem by making their services and data resources discoverable to other participants. This enhances collaboration and enables users to find and access the relevant services and data offerings that align with their needs and objectives.

### Discovery of Resources
The Catalog provides users with the capability to discover and browse resources available within the data space. Through intuitive search and navigation features, users can explore the catalog to find relevant services, data offerings, and data ecosystems. They can utilize search filters, keywords, and categorization to narrow down their search and discover resources that align with their specific requirements. This functionality enhances the user experience by facilitating the efficient discovery and exploration of available resources within the catalog. Users can easily access comprehensive information about each resource, including descriptions, terms and conditions, and technical specifications, enabling them to make informed decisions and effectively leverage the diverse range of services and data offerings provided by participants in the data ecosystem.

### Recommendations for Services and Data Offerings
Entities who have registered resources or have described an ecosystem in the catalog should receive recommendations for matching services and data offerings or matching data ecosystems. The system enables custom matching logic to provide such recommendations to participants through the catalog User Interface.

### Access Standard Descriptions
The system allows participants to access a set of standard descriptions, including business models, data types, roles, obligations and purposes. This functionality assists participants in understanding the and aligning with the guidelines and requirements of the catalog.

### Contract

### Ensuring Data Governance Enforcement
The Data Ecosystem Contract functionality ensures the enforcement of data governance rules within the ecosystem. A data ecosystem orchestrator can implement mechanisms to uphold the agreed-upon governance principles and regulations. This includes defining and enforcing policies, access controls, and data usage guidelines to maintain compliance and data integrity.

### Managing Accession Requests
The Data Ecosystem Contract provides the capability for the data ecosystem orchestrator to manage requests for accession to the data ecosystem. It can review and process access requests from organizations or individuals seeking to join the ecosystem. This includes verifying the eligibility of participants, assessing their compliance with contractual obligations, and granting access based on predefined criteria.

### Access Standard Clauses
The Data Ecosystem Contract provides participants with access to a set of standard clauses that describe commonly used terms and conditions. These standard clauses cover various aspects, including security, confidentiality, privacy, data ownership, and data sharing rights. Participants can utilize these standard clauses as a starting point for creating their own contractual agreements, ensuring consistency and legal compliance across the ecosystem.

### Contract Generator
The Contract Generator is a vital functional requirement of the Data Ecosystem Contract within Prometheus-X. This functionality empowers the data ecosystem orchestrator to generate standardized contract templates based on predefined rules and parameters. By leveraging the Contract Generator, the orchestrator can streamline and automate the process of creating contractual agreements within the ecosystem. The Contract Generator should have the capability to dynamically populate contract templates with relevant information, such as participant details, data usage rights, and contractual obligations. This functionality ensures consistency and efficiency in generating contracts, saving time and effort for the orchestrator and participants. Moreover, the Contract Generator should support customization options, allowing the orchestrator to tailor the generated contracts to specific requirements or specific use cases within the data ecosystem.

Policy Enforcement and Decision Points
This functionality enables the implementation of policy enforcement mechanisms and decision points to govern data sharing and access within the ecosystem. The Policy Enforcement Point (PEP) acts as the enforcement component, responsible for intercepting and evaluating requests for data access or usage. The Policy Decision Point (PDP) serves as the central authority for making access control decisions based on predefined policies and rules. The Policy Execution Point (PXP) executes the decisions made by the PDP, allowing or denying access to data based on the evaluated policies. Together, these components ensure that data sharing activities within the ecosystem adhere to the established contractual agreements and regulatory requirements. The PEP, PDP, and PXP functionalities provide a robust framework for policy enforcement, access control, and decision-making, enhancing the security, compliance, and trustworthiness of data exchanges within the data ecosystem.

## Consent
Consent functionalities play a critical role in ensuring transparent and ethical data exchange within the data ecosystem.

### Giving, Reviewing and Revoking Consents
Individual end users have the ability to manage their consents within the data ecosystem. This functionality allows users to give their explicit consent for data sharing between participants, review their existing consents at any time, and revoke consent if desired. By centralizing the consent management process, users can make informed decisions, stay informed about their data sharing agreements, and exercise control over the usage of their personal data within the ecosystem.

### Consent Verification & Personal Data Intermediaries
Personal Data Intermediaries (PDIs) are consent management components that facilitate consent management for end-users and the verification of consent during data exchanges within the ecosystem. PDIs provide user interfaces (UIs) or APIs through which end-users can manage their consents, including giving, reviewing, and revoking consent for data sharing. These PDIs also play a crucial role in verifying the validity of consent during data exchanges between participants. By leveraging PDIs, participants can ensure that the necessary consent has been obtained from the individual end-user before accessing or utilizing their personal data. This functionality promotes transparency, accountability, and compliance with data protection regulations, enhancing the trust and integrity of data exchanges within the data ecosystem.

### Consent Statistics
The data ecosystem orchestrator can visualize statistics on generated consents across the ecosystem. This functionality provides insights into consent patterns, trends, and the overall consent landscape within the ecosystem. By accessing consent statistics, the orchestrator can gain a comprehensive understanding of consent-related activities, monitor compliance, and identify areas for improvement.

### Consent Logging
The system captures and logs consent-related activities, including consent given, revoked, and modified. This functionality ensures a comprehensive audit trail of consent activities within the ecosystem. Consent logging helps in maintaining transparency, accountability, and compliance with data protection regulations.

# Non-Functional Requirements

## Usability & Compatibility

### User-Friendly Interface
The user interface (UI) of the system should be intuitive, well-designed, and user-friendly. It should provide a seamless and efficient user experience, enabling users to easily navigate and interact with the system's functionalities.

### Accessibility
The system should be accessible to a diverse range of users, including those with disabilities. It should comply with accessibility standards and guidelines, ensuring equal access and usability for all individuals.

### Cross-Platform Compatibility
The system should be compatible with various platforms and devices, including desktop computers, mobile devices, and tablets. It should be responsive and capable of delivering a consistent user experience across different platforms and screen sizes.

### Interoperability
The system should support interoperability with external systems and technologies. It should adhere to industry standards and protocols, allowing for seamless integration and data exchange with other systems or data ecosystems.

## Regulatory & compliance requirements

### Data Protection Regulations
The system should comply with relevant data protection regulations, such as the General Data Protection Regulation (GDPR) or other applicable privacy laws. It should ensure the secure handling, storage, and processing of personal data, and provide mechanisms to obtain and manage user consents appropriately.

### Security
The system should implement robust security measures to protect data and ensure the confidentiality, integrity, and availability of information. This includes encryption, access controls, authentication mechanisms, and regular security audits to identify and mitigate potential vulnerabilities.

### Compliance Reporting
The system should provide capabilities to generate compliance reports and logs. This functionality assists in demonstrating regulatory compliance and supporting auditing processes.

### Data Governance
The system should support effective data governance practices. It should include mechanisms for defining and enforcing data governance policies, access controls, and data lifecycle management, ensuring compliance with regulatory requirements and internal policies.

### Auditability
The system should maintain comprehensive audit trails of data transactions, consent management activities, and system events. These audit logs help in tracing data flows, detecting unauthorized access, and supporting regulatory compliance audits.

# Components

## Core
- [Catalog API](catalog-api/)
- [Catalog Registry](catalog-registry/)
- [Consent Manager](consent-manager/)
- [Consent/contracts Negotiating Agent](contract-consent-agent/)
- [Contract Manager](contract-manager/)
- [Data Processing Chain Protocol](data-processing-chain-protocol/)
- [PTX Dataspace Connector](dataspace-connector/)

## Trustworthy Data Sharing
- [Decentralized AI Training](decentralized-ai-training/)
- [Edge Computing - AI Processing](edge-computing/)
- [Trustworthy AI: Algorithm assessment](t-ai/)
  - [AffectLog's Trustworthy AI (ALT-AI)](t-ai-affectlog)
  - [LORIA's Trustworthy AI (LOLA)](t-ai-lola/)
  - [University of Koblenz's CARiSMA platform](t-ai-carisma/)

## Data Transformation
- [Data Alignment, Aggregation and Vectorisation (DAAV)](daav/)
- [Edge Translators](edge-translators/)
- [Learning Object Metadata Crowd Tagging (LOMCT)](lomct/)
- [Learning Records Converter](learning-records-converter/)
- [Learning Traces From VR Activities](learning-traces/)
- [Personal Learning Record Store (PLRS)](plrs/)
- [Web Analytics Learning Records Universal Connector (WALRUC)](walruc/)

## Utility
- [Data Value Chain Tracker](data-value-chain-tracker/)
- [Data Veracity Assurance](data-veracity/)
- [Distributed Datavisualization](distributed-datavis/)
