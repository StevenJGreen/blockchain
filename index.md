---

copyright:
  years: 2017, 2019
lastupdated: "2019-04-23"

subcollection: blockchain

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:note: .note}
{:important: .important}
{:tip: .tip}
{:pre: .pre}

# Getting started with {{site.data.keyword.blockchainfull_notm}} Platform
{: #get-started-ibp}

{{site.data.keyword.blockchainfull}} Platform provides a managed and full stack blockchain-as-a-service (BaaS) offering that allows you to deploy blockchain components in environments of your choice. The environment can be {{site.data.keyword.cloud_notm}}, on-premises through {{site.data.keyword.cloud_notm}} Private, and third-party clouds, such as Amazon Web Services (AWS). In this tutorial, we'll take you through the general process to set up a basic blockchain network with {{site.data.keyword.blockchainfull_notm}} Platform.
{:shortdesc}

**Important:** Before you use an {{site.data.keyword.blockchainfull_notm}} Platform offering, read the technical and support information in the [Disclaimer](/docs/services/blockchain/needtoknow.html#disclaimer) section.


## Before you begin
{: #get-started-ibp-prereqs}

{{site.data.keyword.blockchainfull_notm}} Platform provides different offerings to help all types of users get started on their blockchain journey and move their applications into production. You need to decide your environment and the offering that you will use. Figure 1 lists the capabilities, target audiences, pricing, and cloud platforms for different offerings. For more information about each offering, click the offering in the following table.

| **Offerings** | **What's included** | **Billing policy** | **Cloud platform** |
| ------------------------- |-----------|-----------|-----------|-----------|
| [**{{site.data.keyword.blockchainfull_notm}} Platform Extension for VSCode**](/docs/services/blockchain?topic=blockchain-develop-vscode#develop-vscode) | Developers can start with the IDE that provides an explorer and commands accessible from the command palette for developing smart contracts quickly. | Free | Runs on your local machine |
| [**Starter Plan**](/docs/services/blockchain/starter_plan.html#starter-plan-about) | {{site.data.keyword.IBM_notm}}-managed network with basic service levels, development, and testing environment | Monthly subscription | {{site.data.keyword.cloud_notm}} |
| [**Enterprise Plan**](/docs/services/blockchain/enterprise_plan.html#enterprise-plan-about) | {{site.data.keyword.IBM_notm}}-managed network with advanced service levels and enterprise production ready environment | Monthly subscription | {{site.data.keyword.cloud_notm}} |
| [**{{site.data.keyword.blockchainfull_notm}} Platform free 2.0 beta**](/docs/services/blockchain/howto/ibp-console.html#ibp-console-overview) | {{site.data.keyword.blockchainfull_notm}} Platform console to deploy and manage blockchain components in your {{site.data.keyword.cloud_notm}} Kubernetes cluster | Free for Beta | {{site.data.keyword.cloud_notm}} |
| [**{{site.data.keyword.blockchainfull_notm}} Platform for {{site.data.keyword.cloud_notm}} Private**](/docs/services/blockchain/ibp-for-icp-about.html#ibp-icp-about) | Deployable CA, Orderer, and Peer Helm charts | [VPC pricing](/docs/services/blockchain/ibp-for-icp-about.html#ibp-icp-about-pricing) and Free Community Edition | {{site.data.keyword.cloud_notm}} Private |
| [**{{site.data.keyword.blockchainfull_notm}} Platform for AWS**](/docs/services/blockchain/howto/remote_peer.html#remote-peer-aws-about) | AWS Quick Start Template to deploy remote peers that are outside {{site.data.keyword.cloud_notm}} | Free | AWS |

*Figure 1. {{site.data.keyword.blockchainfull_notm}} Platform offerings*

Do not use Starter Plan or the free 2.0 beta for production usage. It is a development and testing environment, and is not suitable for production workloads.
{: important}

## Step one: Get an offering
{: #get-started-ibp-step1}

Ensure that you have the cloud account or PPA license to get an {{site.data.keyword.blockchainfull_notm}} Platform offering.

* **{{site.data.keyword.blockchainfull_notm}} Platform Extension for VSCode**

  This VSCode extension is available for free in the [Visual Studio Marketplace ![External link icon](images/external_link.svg "External link icon")](https://marketplace.visualstudio.com/items?itemName=IBMBlockchain.ibm-blockchain-platform "{{site.data.keyword.blockchainfull_notm}} Platform Extension for VSCode") and can be used to develop, debug, and test smart contracts for eventual deployment into {{site.data.keyword.blockchainfull_notm}}.

* **Starter Plan**, **Enterprise Plan**, and **{{site.data.keyword.blockchainfull_notm}} Platform free 2.0 beta**

  These offerings are available in {{site.data.keyword.cloud_notm}} and you can locate them in the [Catalog dashboard ![External link icon](images/external_link.svg "External link icon")](https://cloud.ibm.com/catalog "Catalog") of {{site.data.keyword.cloud_notm}}.

* **{{site.data.keyword.blockchainfull_notm}} Platform for {{site.data.keyword.cloud_notm}} Private**

  This offering is delivered as a deployable Helm chart and has both paid edition and free Community edition. You can download the Enterprise Edition from [Passport Advantage Online ![External link icon](images/external_link.svg "External link icon")](https://www.ibm.com/software/passportadvantage/pao_customer.html) or download the free Community edition from [GitHub ![External link icon](images/external_link.svg "External link icon")](https://github.com/IBM/charts/blob/master/repo/stable/ibm-blockchain-platform-dev-1.0.2.tgz).

* **{{site.data.keyword.blockchainfull_notm}} Platform for AWS**

  This offering is available in AWS and you can deploy a blockchain peer in AWS by using the [Quick Start template ![External link icon](images/external_link.svg "External link icon")](https://aws.amazon.com/quickstart/architecture/ibm-blockchain-platform/).

## Step two: Deploy {{site.data.keyword.blockchainfull_notm}} Platform
{: #get-started-ibp-step2}

* **Starter Plan**, **Enterprise Plan**, and **{{site.data.keyword.blockchainfull_notm}} Platform free 2.0 beta**

  Log in to {{site.data.keyword.cloud_notm}} and create a service instance with the offering. If you use Starter Plan, you can get a blockchain network with default configuration immediately after you [create the service instance](/docs/services/blockchain/get_start_starter_plan.html#getting-started-with-starter-plan). If you use Enterprise Plan or {{site.data.keyword.blockchainfull_notm}} Platform free 2.0 beta, you need to follow the wizard to complete initial configuration for your network. For more information, see [Creating an Enterprise Plan network](/docs/services/blockchain/get_start.html#getting-started-with-enterprise-plan-create-network) or [Deploying {{site.data.keyword.blockchainfull_notm}} Platform on {{site.data.keyword.cloud_notm}} Kubernetes Service](/docs/services/blockchain/howto/ibp-v2-deploy-iks.html#ibp-v2-deploy-iks).

* **{{site.data.keyword.blockchainfull_notm}} Platform for {{site.data.keyword.cloud_notm}} Private**

  Before you deploy a network, you need to [import the Helm chart to your {{site.data.keyword.cloud_notm}} Private](/docs/services/blockchain/howto/helm_install_icp.html#helm-install). Then, you can [deploy your network components starting from a CA](/docs/services/blockchain/ibp_for_icp_deployment_guide.html#step-three-set-up-your-cas) to build your network.

* **{{site.data.keyword.blockchainfull_notm}} Platform for AWS**

  This offering is available in AWS and you can deploy a blockchain peer in AWS by using the [Quick Start template ![External link icon](images/external_link.svg "External link icon")](https://aws.amazon.com/quickstart/architecture/ibm-blockchain-platform/).

## Next steps
{: #get-started-ibp-next-steps}

After you deploy {{site.data.keyword.blockchainfull_notm}} Platform in the environment of your choice, you can set up the network with consortium, nodes, channels, smart contracts, and start transactions on it. For more information, see the task topics under the **HOW TO** section in the left navigation of this documentation.

## Getting support
{: #get-started-ibp-getting-support}

{{site.data.keyword.IBM_notm}} offers various support options on {{site.data.keyword.IBM_notm}}-implemented blockchain solutions. For more information about {{site.data.keyword.blockchainfull_notm}} Platform support, see [Getting support](/docs/services/blockchain/ibmblockchain_support.html#blockchain-support).
