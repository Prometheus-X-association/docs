AffectLog's Trustworthy AI (ALT-AI) - Design Document
=====================================================

AffectLog's Trustworthy AI (ALT-AI) provides a set of tools for explaining, visualizing, and understanding complex machine learning models. It aims to facilitate model transparency, interpretability, and aid compliance with emerging regulatory standards (e.g., GDPR, EU AI Act). ALT-AI helps data scientists, analysts, and stakeholders interpret model predictions, identify feature importance, assess fairness, and evaluate whether models align with ethical and legal requirements. 

Technical Usage Scenarios & Features
------------------------------------

ALT-AI supports both global (overall model behavior) and local (individual predictions) explanations. It helps users understand which features influence model outcomes the most, compare different models for performance and fairness, and ensure that no demographic group is disproportionately affected. The toolbox is designed to be flexible and scalable, while prioritizing privacy, security, and compliance. 

### Features/Main Functionalities

-   Model Explanation: Provides global and local explanations to clarify how models derive their predictions.

-   Feature Importance: Quantifies each feature's impact, aiding interpretability and better feature selection/engineering decisions.

-   Model Comparison: Compares different models based on predefined metrics and segments, helping select the most suitable model.

-   Fairness Analysis: Evaluates models for fairness and potential biases across sensitive groups.

### Technical Usage Scenarios

-   Model Development & Validation: Data scientists can use ALT-AI to ensure models meet business, ethical, and regulatory standards before deployment.

-   Audit & Compliance: ALT-AI facilitates documentation and transparency required for audits, potentially aiding with GDPR adherence and upcoming EU AI Act considerations.

-   Feature Engineering: By understanding feature importance, practitioners can refine and enhance their model inputs.

Requirements
------------

-   R1: MUST support integration with popular Python-based ML frameworks, including scikit-learn, and, where feasible, TensorFlow and PyTorch models via wrappers. Also supports numpy, pandas for data handling, and onnxruntime for ONNX models.

-   R2: MUST provide APIs for generating explanations, feature importance scores, and model comparisons.

-   R3: MUST ensure data privacy, security, and must not require access to raw personal data for explanation generation.

-   R4: SHOULD leverage partner infrastructure for scalability and handle large datasets and complex models efficiently.

-   Timeline: Feasibility discussions (e.g., integration with Decentralized AI Training BB) are tentatively planned for Q1 2025. After these discussions, a more precise project timeline and roadmap will be established. A high-level work plan has been shared with the relevant Building Block (BB) and Work Package leader for consideration.

Integrations
------------

### Direct Integrations with Other BBs

-   Decentralized AI Training BB: ALT-AI may integrate with models produced by Decentralized AI Training BB to provide post-training analyses. This integration is subject to a feasibility discussion with the Decentralized AI Training BB team. The intent is to securely retrieve the resulting trained models---under appropriate consent and policy enforcement via the PDC---and then perform AI risk assessment and explainability tasks. If deemed feasible, ALT-AI would operate on aggregated model artifacts rather than raw data, preserving privacy.

### Integrations via Connector

-   Decentralized AI Training BB: If deemed feasible after discussions with the Decentralized AI Training BB, ALT-AI could access trained models through the Prometheus-X Data Space Connector (PDC) via a secure connector. The PDC enforces ODRL policies and consent protocols, ensuring compliance with privacy and GDPR requirements. Once authorized, ALT-AI can retrieve model artifacts---without exposing raw personal data---to perform its explainability and fairness assessments. This data-minimized integration helps maintain trust, auditability, and adherence to data governance standards, while keeping the solution's decentralized and privacy-preserving ethos intact.

Relevant Standards
------------------

-   Data Format Standards: Adheres to common data exchange formats such as JSON and CSV for input and output data, ensuring compatibility with a wide range of data sources and systems.

-   Model Cards: Following the template by Mitchell et al. (2019), documenting model purpose, performance, and ethical considerations. ALT-AI can reference these model cards to contextualize explanation outputs, highlight known limitations, and align results with stated use cases.

-   Data Cards (Datasheets for Datasets): Following Gebru et al. (2018), describing dataset provenance, collection methods, preprocessing steps, and known data biases. ALT-AI can incorporate insights from these datasheets to inform fairness metrics, point out potential risk areas, and improve the interpretability of results.

-   GDPR Compliance: ALT-AI operates on aggregated model artifacts and anonymized datasets, avoiding raw personal identifiers.

-   EU AI Act Alignment: While the EU AI Act is still evolving, ALT-AI's design principles emphasize fairness, transparency, and explainability. Once the Act's requirements are fully defined, ALT-AI can be adjusted or extended to meet any additional mandates, such as performing mandatory impact assessments or continuous monitoring.

-   PDC Integration (If Feasible): Through the Prometheus-X Data Space Connector (PDC), ALT-AI ensures that only authorized and policy-compliant model artifacts are fetched. It respects ODRL policies and user consent frameworks, thus aligning with existing and forthcoming regulations.

-   Interoperability Standards: Follows guidelines from the Data Space Support Centre (DSSC) to ensure interoperability within data spaces, promoting seamless integration with other systems and frameworks.

Input / Output Data
-------------------

Supported Model Types

-   Scikit-learn Models: Directly supported via joblib or pickle serialization.

-   ONNX Models: Supported with a wrapper that provides scikit-learn-like methods (predict, predict_proba), enabled by onnxruntime.

-   TensorFlow/Keras & PyTorch Models: Supported by creating lightweight wrappers that expose a scikit-learn-like interface. These wrappers should handle model input/output so ALT-AI can treat the model uniformly (e.g., a predict method returning consistent formats).

Supported Data Formats

-   Tabular Data (Preferred): Pandas DataFrames or NumPy arrays are the primary input formats for explanations.

-   Source Formats (CSV, JSON, Parquet): Datasets originating in CSV, JSON, or Parquet can be converted into DataFrames or arrays for ingestion. Non-tabular modalities (text, images, video) must be vectorized or embedded into tabular form before explanation.

-   The approach to data ingestion is flexible, but it is expected that data producers will preprocess data into these supported formats. ALT-AI's explanation logic relies on structured inputs for consistent metrics and fairness evaluations.

Architecture
------------

The ALT-AI comprises several components:

-   Model Adapter: Adapts various types of machine learning models to a standardized format for analysis.

-   Explanation Generator: Core component that utilizes ALT-AI functions to generate explanations, feature importances, and model comparisons.

-   Results Processor: Formats and organizes explanation results for easy consumption and visualization.

-   Security Layer: Ensures data privacy and security throughout the explanation process.

![Class Diagram](classDiagram-v1.1.png)

Dynamic Behaviour
-----------------

Sequence diagram for generating model explanations:

![Sequence Diagram](sequenceDiagram-v1.1.png)

Configuration and Deployment Settings
-------------------------------------

-   Configuration options include model type, explanation type (global or local), and computational resources allocation.

-   Logging operations include tracking of explanation generation processes, error handling, and performance metrics. Error scenarios might involve unsupported model types or data formats, and insufficient computational resources for large datasets.

-   Usage limits are defined based on the computational complexity of the models being explained and the size of the dataset. For instance, a limit on the number of features or records that can be processed in a single explanation request may be set to ensure optimal performance.

Third Party Components & Licenses
---------------------------------

-   Pandas/Numpy: BSD-3-Clause

-   scikit-learn: BSD-3-Clause

-   TensorFlow: Apache-2.0

-   PyTorch: BSD-style

-   ONNX & onnxruntime: MIT License

Implementation Details
----------------------

ALT-AI is built with flexibility, compliance, and scalability in mind. The feasibility of integrating with the Decentralized AI Training BB will be assessed in Q1 2025. Post-feasibility, a detailed timeline and roadmap will be provided. A high-level work plan has already been shared with relevant stakeholders.

Partners & Roles
----------------

-   Prometheus-X Organization: Provides governance and infrastructure frameworks.

-   AffectLog: Develops and maintains ALT-AI.

-   Data Providers & Model Developers: Supply data and models with corresponding Data/Model Cards.

-   End Users: Data scientists, analysts, and regulators rely on ALT-AI for interpretable AI insights and compliance checks.

Usage In The Dataspace
----------------------

-   Interoperability: Uses standard formats and recognized documentation templates for smooth integration.

-   Data Governance: Relies on privacy-preserving infrastructure (like PDC) if integrated with Decentralized AI Training BB.

-   Scalability & Regulatory Readiness: Capable of handling large datasets and complex models while staying adaptable to evolving regulatory landscapes such as the EU AI Act.

Leveraging AffectLog in Organizational Skill Gap Analysis

AffectLog's Trustworthy AI (ALT-AI) can interpret models used for skill gap analysis, providing insights into key factors driving skill shortages and ensuring fairness. If the models are trained via decentralized methods (feasibility pending), privacy and compliance are further guaranteed. By using ALT-AI, organizations can:

-   Model Explanation and Feature Importance: Understand the factors contributing to skill gaps by analyzing predictions from AI models. This helps in identifying key areas for employee development.

-   Fairness Analysis: Ensure that the AI models used for skill gap analysis do not introduce biases, promoting fair and inclusive development programs.

-   Model Comparison: Compare different analytical models to determine the most effective approach for skill gap analysis.

OpenAPI Specification
---------------------

Future iterations may offer an OpenAPI specification for endpoints handling model submission, explanation retrieval, and integrated compliance reporting referencing Model/Data Cards. 

Test Specification
------------------

-   Model Adapter Test (ONNX): Ensure ONNX models wrapped with onnxruntime produce correct predictions.

-   Explanation Generation with Model Cards: Verify that explanations reference model cards to contextualize performance and limitations.

-   Fairness Analysis (Sensitive Feature): Confirm that fairness metrics highlight insights from Data Cards if imbalance or known biases are noted.

-   Compliance and Privacy Checks: Test retrieval from PDC-compliant environments (if integrated) to ensure no raw personal data is exposed and that GDPR and future EU AI Act guidelines are followed.

-   Performance Test (Large Dataset): Validate that large datasets are processed efficiently with no degradation in explanation quality.

Disclaimers
-----------

-   The integration of AffectLog's ALT-AI into the Organizational Skill Gap Analysis process requires a detailed feasibility study to ensure technical compatibility and resource availability.

-   Prior to implementation, discussions with relevant stakeholders are necessary to align objectives, contextual feasibility, and privacy considerations.

This comprehensive test specification aims to ensure that the ALT-AI operates reliably and efficiently, providing valuable insights into machine learning model behavior while maintaining high standards of usability, security, and compliance.
