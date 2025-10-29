# IN161 - Modernize and transform your integration to the cloud

## Description

This repository contains the material for the SAP TechEd 2025 session called IN161 - Modernize and transform your integration to the cloud.

## Overview

This session introduces attendees to the migration assessment and migration tool supporting you in the transformation from SAP Process Orchestration to SAP Integration Suite.

The [Migration Assessment](https://help.sap.com/docs/integration-suite/sap-integration-suite/migration-assessment) capability of SAP Integration Suite lets you evaluate how various integration scenarios might be migrated and allows you to estimate the technical efforts involved in the migration process.

After having finished the assessment of the current SAP Process Orchestration landscape, the next step is the actual migration. The goal of the [Migration Tooling](https://help.sap.com/docs/integration-suite/sap-integration-suite/migration-tooling) is to provide a semi-automated migration where interfaces in the Cloud Integration capability of SAP Integration Suite will be automatically created based on SAP Process Orchestration information, so that ideally 60-70% of technical migration efforts are automated. The migration of scenarios is based on a pattern approach, which means that integration flow templates following a specific pattern are used as skeleton to migrate the content and create the final integration flows.

In this exercise, we will leverage the so called [Pipeline](https://help.sap.com/docs/migration-guide-po/migration-guide-for-sap-process-orchestration/pipeline-concept) for Cloud Integration which is supported within the migration tooling. The Pipeline for Cloud Integration allows you to set up your integration scenarios in Cloud Integration similarly to how messages are processed in SAP Process Orchestration, in pipelines. As such, it helps you accelerating the transition to the cloud. It can be seen as framework which allows you to handle asynchronous messages in a common way with out-of-the-box support for exactly once delivery, error handling and sophisticated restart capabilities. For an introduction to the Pipeline for Cloud Integration, check out this [blog post](https://community.sap.com/t5/technology-blog-posts-by-sap/introducing-the-new-pipeline-concept-in-cloud-integration/ba-p/13639651).

## Requirements

The requirements to follow the exercises in this repository are...


## Access to SAP Integration Suite tenant

For running through the exercises, we provide the following SAP Integration Suite tenants. The instructors will let you know which of the tenants are actually used for the exercises.

Tenants in EU:
- Option 1: [**Workshop tenant eu-02a**](https://workshop-eu-02a.integrationsuite-cpi033.cfapps.eu10-005.hana.ondemand.com/shell/home).
- Option 2: [**Workshop tenant eu-02b**](https://workshop-eu-02b.integrationsuite-cpi035.cfapps.eu20-001.hana.ondemand.com/shell/home).

Tenants in US:
- Option 3: **User00-User30**: [**Workshop tenant us-01b**](https://workshop-us-01b.integrationsuite.cfapps.us20.hana.ondemand.com/shell/home).
- Option 4: **User31-User60**: [**Workshop tenant us-01c**](https://workshop-us-01c.integrationsuite.cfapps.us30.hana.ondemand.com/shell/home).

Access:
- Use the user **userXX** with **XX** your ID and password provided by the instructors.

## Prerequisites

As a prerequisite for the migration tooling exercises, you first need to run through the following preparation steps.
- [Exercise 0 - Prepare the Migration Exercises](exercises/ex0/)

## Exercises

In the following, the complete list of exercise steps are listed. You can use this section as an index or table of contents. Use the breadcrumb navigation on top of the pages to go back to the Table of Contents.

If you are interested in how the **Migration Assessment** works, start with the first exercise. Note, this exercise is optional. You can run through the migration tooling exercises independent of the migration assessment exercise.
- [Optional Exercise 1 - Migration Assessment](exercises/ex1/)

For running through the **Migration Tooling**, continue with the second exercise.
- [Exercise 2 - Migrate a Content-Based-Routing Scenario](exercises/ex2/)

To extend the generated integration flows using the **Pipeline's extention points**, run through the following exercises.
- [Exercise 3 - Configure Custom Header Properties](exercises/ex3/)
- [Exercise 4 - Set up Custom Receiver Determination](exercises/ex4/)


## Contributing
Please read the [CONTRIBUTING.md](./CONTRIBUTING.md) to understand the contribution guidelines.

## Code of Conduct
Please read the [SAP Open Source Code of Conduct](https://github.com/SAP-samples/.github/blob/main/CODE_OF_CONDUCT.md).

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (c) 2024 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
