***************
Engagement Plan
***************

Preliminaries
-------------
In order to fully benefit from the platform, customers are required to provide their stock and transaction data to the platform. This document explains the data requirements for different types of integration and illustrates different interface options, each with an example enabling customers to estimate related efforts.

Integration types, examples and efforts
---------------------------------------
The depth of an integration can depend on the customer specific requirements and varies from less complex manual data uploads using the UI or FTP up to automated and seamless interfaces via web services. This chapter illustrates integration types including examples, provides estimations for the efforts of integration and characterizes a typical integration project in scope and staff.

Integration type 1: Minimal integration – manual upload of files
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
To allow access to all core functionalities (e.g., request FMVs, trade inventory) of the platform, customers may use the manual file upload functionality (xml, csv, …) by using the graphical user interface. This enables a provision of the customer’s historical data which will be repeated at specific intervals.

Customers using additional functionalities, such as the connector for trading purposes, will need to provide their most recent demand information or supply information, or both. This information can also be uploaded manually using the file upload functionality on the platform.

Using the manual upload functionality, customers can start working with the platform immediately without establishing a technical interface first.

The efforts related to this minimal integration typically do not exceed more than 2-4 weeks, which includes familiarizing with the platform and data preparation.

Integration type 2: Seamless integration – automated interface
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Customers using additional functionalities of the platform (e.g., analytics, long-term-planning, maintenance events optimization, etc.) typically require an automated interface. In particular for customers using the connector functionality for optimized trading purposes, it is relevant to dynamically update the customer’s current part supply and/or demand on the platform. In addition to mandatory data sets (transaction data), further information is required, e.g., maintenance events, certificates, part history and information.

In order to ensure a seamless update process, customers typically require a tailor-made or standardized interface to their ERP system or a related middleware. The efforts related to this integration type depend on the customer’s individual IT and business requirements. The chapter "Technical interfaces" provides details of all available services from which the customer may estimate their individual complexity.

The efforts related to this seamless integration normally do not exceed more than 2-4 months.

Data processing and anonymization
---------------------------------
In order to ensure the commercial confidentiality of all customers, data that has been uploaded to the platform is pre-processed, validated, and anonymized before it is used to improve the evaluation of parts. During the processing step, various consistency checks are applied and a quality assurance process takes place. Such a restrictive validation process ensures that resulting values are correct and not distorted by skewed input data. Personal information such as customer name are not relevant for the FMV (Fair Market Value) calculation process. Therefore, any data provided by customers will be anonymized. Hereby it is not possible to refer to any individual data provided via the platform.

Processing, validation and enrichment of provided customer data takes place on servers in Germany.

Integration project
-------------------
The actual scope and effort for an integration project depends on the individual agreement between customers and Opremic and the targeted integration depth.

Staff
-----
Depending on the depth of integration a typical project team on the customer's side consists of a project manager, a business expert, and an IT expert.

On side of Opremic, irrespective of the integration type and related efforts, an individual project manager for each customer project is assigned. This project manager acts as single point of contact for the customer during the entire integration project.

Scope and efforts
-----------------
An integration project typically consists of the following phases:

:Kick-off: determination of targeted interface, required data vs. available data, project team, timeline
:Data quality and consistence assurance: based on the agreed integration model, the customer provides a test data set, creation of test cases
:Implementation: interface adaption/set up on customer and provider side
:Testing: process, quality and logic tests, support and troubleshooting
:Go-Live: deployment

The majority of required tasks will be performed by Opremic staff. A reliable project timeline highly depends on the depth of integration. Although a minimum input concerning data provision and IT and business support is required from the customer, the existing interfaces to the platform are adaptable to the customer’s needs in order to reduce potential integration efforts to a minimum.
