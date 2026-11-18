# BB04: Trustworthy AI Assessement : Overview

The aim of this document is to explain the choice that led to the proposal of a toolbox made up of 3 complementary tools to address the issue of trustworthy AI assessment via the Building Block #4 (BB04) of the EDGE-Skills project.

Indeed, this BB brings together 3 organizations that take complementary approaches with different perspectives.

The 3 tools are

1. CARiSMA (CompliAnce, Risk, and Security ModelAnalyzer): a software developed by the University of Koblenz and the Fraunhofer Institute for Software and Systems Engineering ISST, which is not originally intended exclusively for AI technologies. The software is a comprehensive open source suite that enables system designers and security experts to perform automated compliance, risk and security analyses of software and system models. It can be applied to analyze models of AI scenarios and to generate meaningful insights and reports to fulfill compliance obligations.

2. LOLA (Open Laboratory of Leaning Analytics): another laboratory prototype developed by LORIA/Université de Lorraine, originally intended for auditing AI algorithms, on data provided by French national education partners offering educational resources involving AI technologies.

3. ALT-AI (AffectLog’s Trustworthy AI):  a commercial product developed by AffectLog for analyzing the performance and behavior of AI algorithms using test data provided by customers. It focuses on interpreting machine learning models, providing insights into feature importance, prediction outcomes, and fairness metrics. ALT-AI is designed to support organizations in understanding how their AI systems operate in real-world conditions, offering transparency and trustworthiness in AI-driven decision-making processes. 

##  Challenges
 
###  General context

The new AI legislation recently adopted by the EU aims to guarantee its citizens AI applications and services they can trust.
 
This new law offers companies a legal framework that promotes trustworthy AI.
Depending on the level of risk identified for an AI-enabled application, risk reduction and transparency obligations will be imposed on economic players.
 
Applications in the field of education are generally considered to be of high or at least limited risk, which leads EdTech companies to require a conformity assessment before a given AI system is commissioned or placed on the market.
 
The aim of BB04 is to help EdTech companies adopt appropriate and targeted risk management measures to mitigate the risks identified for AI use cases, by proposing automated assessment tools that apply right from the system design stage and throughout its lifecycle.
 
### Trust and transparency
 
The tools we propose in BB04 are defined as automated evaluation tools.
They are used at different points in an application's lifecycle, and rely on different inputs.
 But their common purpose is to produce trust-related quality indicators in the form of audit reports that can be shared by companies, thus creating the necessary conditions of transparency.
 
## Use cases in EDGE Skills

In this section, we summarize how the tools can be used, and how they can contribute to improving the quality of an AI-based service.
As mentioned above, the three tools have in common the assessment of risks in the context of the use of AI.
There are several types of risks and the three tools are limited to risks that can rely on an automated assessment process.
Each of them is specialized to a particular category of risks that we present in this section.

### CARiSMA

CARiSMA is a comprehensive software suite that enables system designers and security experts to perform automated compliance analysis, risk analysis and security analysis of software and system models.
It is a generic tool that can be used for systems that incorporate AI, and a fortiori in the field of education.
The tool is used during the design phase of a system, when certain privacy and security related requirements must be formally specified.
In particular, it enables security and privacy constraints to be verified, helping a company to understand (and show, in a transparent approach) how personal data is used in the context of an AI service to be analyzed.

### LOLA
LOLA takes the form of a platform for a community made up of educational data providers on the one hand, and AI providers on the other.
This makes it possible to evaluate algorithms as closely as possible to the needs of the services envisaged, by combining the two contributions.
As a result, LOLA can produce indicators that are highly dependent on the service being deployed.

###  ALT-AI
ALT-AI provides tools for explaining and visualizing machine learning models, focusing on models that are already built and operational. It is intended for use in auditing AI systems, helping organizations understand how their models make decisions. ALT-AI produces analysis related to model interpretability, with a focus on feature importance and how different inputs affect predictions. This is achieved using test data supplied by the organization, allowing for a clear understanding of the factors driving model outputs.

## Users

In this section, we focus on the notion of user of the BB04 toolbox.
At the general level, the need is driven by an EdTech organization that wishes to integrate services that integrate AI technologies.
They therefore represent the project management.
But depending on the choice of the tool to be used, the skills of the stakeholders who will use them differ.
It should be noted that the stakeholders can be partners or service providers of the company behind the initiative.
This is what we will specify in this section

### CARiSMA

A CARiSMA user in the context of EDGE-SKILLS is an AI expert of a use case lead or an AI expert acting on behalf of a use case lead.
During the design phase, they specify the expected properties of a system in a formal language such as UML.
The formalism can be enriched with certain properties, e.g. concerning AI risks, such as those required by the [EU’s AI Act](https://www.europarl.europa.eu/topics/en/article/20230601STO93804/eu-ai-act-first-regulation-on-artificial-intelligence). By this, a use case leads will be enabled to analyze their planned scenario, to check for potential compliance issues and to create reports that support different compliance obligations.

###  LOLA

For the LOLA platform, we distinguish 3 types of users:

- Data providers: these are companies with educational data that they wish to exploit as part of an AI-based service.

We can imagine two types of situation: 1) the company is looking for an algorithm that will effectively meet its needs, or, 2) the company wants to improve its own algorithm.

- AI provider: these are organizations specialized in AI and wishing to demonstrate the performance of their algorithms on a scenario defined by a company that has supplied the data.

- Scenario designer: a scenario is an experimentation template that defines the assessment methods, in particular the metrics specific to the service context.
A scenario is independent of data and algorithms.
A scenario designer is therefore a partner of the platform operator.

### ALT-AI

For ALT-AI, the skills expected from users regarding AI and Machine Learning. We can summarize them under the term MLOps
MLOps is a core function of Machine Learning engineering, focused on streamlining the process of taking machine learning models to production, and then maintaining and monitoring them.

## Input

Due to the nature of the different processing of each tools, the inputs are also very different as we detail in this section.

### CARiSMA

Carisma's input data is a formal specification of a system integrating AI-specific properties.
The recommended standard to create a specification is the Unified Modeling Language (UML) with specific extensions (UML profiles).

###  LOLA

Data are different depending on the user's role.

For data providers, LOLA expects dataset in xAPI format.

xAPI is a standard specific to education and is also adopted by several EdTect companies, petners of the EDGE project.
It can be used both to capture learner behavior and to describe 
describe the resources involved in learning platforms.

In an AI exploitation process, this data will be used both to select test dataset and training dataset.
Access to this data is via the PDC, in line with the EDGE Skills project's dataspace architecture.

For AI providers (eg. ompanies specializing in AI, or public research organizations wishing to challenge their algorithms), the input is algorithms.
These users interact directly with the platform by depositing their software on it.
The required standards are Git, docker and dockerCompose.

### ALT-AI

ALT-AI is designed to work with structured, tabular datasets and pre-trained machine learning models, typically used for classification and regression tasks. It supports data formats such as CSV, JSON, and Pandas DataFrames, and can analyze models built with common Python-based libraries.

The tool is not suitable for unstructured data types such as video, images, or audio, and does not support models for computer vision, natural language processing, or time-series analysis. Inputs should be clean, with no missing values, and the models provided should be pre-trained, as ALT-AI focuses on post-training analysis.

ALT-AI evaluates the performance of a model by analyzing feature importance, providing interpretability insights, and generating performance metrics using the supplied test data and models.

## Output

All three tools are designed to audit systems and, consequently, their respective results are intended to be compiled in a report to facilitate their analysis.

It should be noted that these tools produce qualitative and quantitative measures that are intended to help in the analysis of the system to be evaluated.
Therefore, their integration into a report requires the intervention of an auditor who will have the task of interpreting and possibly graphically presenting the computed metrics.

### CARiSMA

CARiSMA establishes a set of compliance analyses based on the AI security properties defined in the system specifications.
These properties concern users, systems, data, processing and risk properties.
A connection to the visualization BB is envisaged to finalize a report.

### LOLA

For each execution of a scenario on a given dataset and algorithm, LOLA provides, in JSON format, a set of performance indicators specific to the scenario.
These outputs are intended to be compiled in a report in the form of metrics, properties, curves and tables according to the indicators for better readability.

### ALT-AI

ALT-AI given the complete feasibility and context along with dataset and model access in a valid input format produces a variety of outputs in JSON format to provide detailed insights into machine learning models. These include feature importance scores, prediction explanations, partial dependence plots, and performance metrics across different segments. Additionally, it can provide fairness analysis results, model comparison reports, and residual diagnostics to assess model accuracy. Visualizations and data summaries can be included to help users interpret the results, offering a comprehensive view of model behavior, including any biases, anomalies, or patterns observed during the analysis.

## Summary comparison table

In this section we present a comparison table that gives a synthetic view of the BB04.

![Comparison table](comparison-tab.png)


## Conclusion

This document only offers an overview of the construction of the BB04 as a toolbox composed of three elements.
We invite the reader to discover each of them in detail in the following respective documents:

- [LORIA's LOLA platform](https://prometheus-x-association.github.io/docs/t-ai-lola/)
- [AffectLog's AffectLog360 platform](https://prometheus-x-association.github.io/docs/t-ai-affectlog/)
- [University of Koblenz's CARiSMA platform](https://prometheus-x-association.github.io/docs/t-ai-carisma/)
