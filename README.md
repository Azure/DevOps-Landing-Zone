# DevOps Landing Zone for accelerating CI/CD deployment of your Azure projects

[English](./README.md) | [日本語](./README.ja.md)

---

## Overview

This repository provides a comprehensive, modular infrastructure-as-code solution for deploying and managing Azure resources with using Terraform and CI/CD workflows. This is designed to support both Azure DevOps and GitHub-based CI/CD workflows, enabling organizations to automate the provisioning of secure, scalable, and policy-compliant cloud environments using infrastructure as code, versioned with Git.
The project Git repository which is provisined by this module is designed to be used in enterprise environments and follows Azure and Terraform best practices.

![High-level DevOps Landing Zone Architecture Overview](/docs/images/devops-landing-zone-architecture.png)

Key features include:

- **Modular Terraform Architecture**: Reusable modules for common Azure and DevOps patterns.
- **Support for Azure DevOps and GitHub**: Provisioning of projects, repositories, pipelines, and self-hosted agents/runners.
- **Secure State and Secret Management**: Uses Azure Storage and Key Vault for managing Terraform state and sensitive information.
- **Enterprise-Ready**: Implements best practices for secure closed network, identity, and repository policy enforcement for deployment task executions.
- **Extensible and Customizable**: Easily adaptable to various organizational requirements and cloud governance models.

The `infra/terraform` directory contains all core infrastructure code, organized for clarity and scalability. This structure allows teams to bootstrap foundational resources, deploy landing zones, and manage project-specific DevOps resources in a consistent and automated manner.

> [!NOTE]
> Currently we only support GitHub projects.
>
> We are planning to support Azure DevOps projects in the near future.

## Azure Reference Architecture

The architecture including Azure network is shown in the diagram below. This diagram shows a configuration where a private virtual network is enabled and a GitHub self-hosted runners are hosted in Azure Container App jobs and execute CI/CD workflow jobs in an event-driven manner using KEDA scaling.

It also shows a configuration where a project for a Microsoft Dev Box is deployed so that developers can work for Azure projects using a secure development environment. The Dev Box virtual desktop is connected to a private virtual network, so it can securely access Terraform state management files and deploy and manage Azure resources.

![Azure Architecture of DevOps Landing Zone](./docs/images/devops-landing-zone-azure-network-architecture-with-aca.png)

## Getting Started

Please follow the instructions in the [Getting Started](./docs/Get-Started.md) documentation.

## Acknowledgements

This project is inspired by the [Azure Landing Zone Accelerator](https://github.com/Azure/alz-terraform-accelerator) project. While the [Azure Landing Zone Accelerator](https://github.com/Azure/alz-terraform-accelerator) project focuses on CI/CD deployment of the Azure Landing Zone platform foundation for Enterprise, this project focuses on CI/CD deployment of general Azure projects by generalizing the architecture and modules. Thanks to [Jared Holgate](https://github.com/jaredfholgate) and all the project contributors and team members of [Azure Landing Zone Accelerator](https://github.com/Azure/alz-terraform-accelerator) project.

## Contributing

This project welcomes contributions and suggestions. Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit [Contributor License Agreements](https://cla.opensource.microsoft.com).

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft
trademarks or logos is subject to and must follow
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
