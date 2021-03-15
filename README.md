# AWS Blueprints
The AWS Blueprints enables the AWS partners to quickly deploy, manage and, monitor solutions for their Small and Medium Business (SMB) customers in the AWS cloud. SMB
customers typically have a small technical team and usually seek support from an AWS partner to get started in their cloud journey. Many of these AWS partners who support the SMB customers themselves need assistance with transforming their practice and build solutions in AWS for their SMB customers. These partners are seeking solutions and support
that will get them to market faster, meet the rapidly changing needs of their customers, and enable them to deliver to their customers at high velocity.

AWS Blueprints offers a “1-Click solution deployment” framework (Figure 1) that the partners can use instantly to deploy SMB focused solutions to their customers in a repeatable, scalable and cost-efficient fashion. The SMB solutions that are included in this AWS Blueprints covers diverse SMB customer use cases starting with business applications (Magento, WordPress & SharePoint), end user computing (Amazon Workspaces), business continuity (Veeam backup solution), and data analytics (AWS Data Lake foundation). AWS solutions built by the AWS partners and the Independent Software Vendors (ISV) for other use cases can also be easily added to this “1-Click-Deployment” framework. AWS partners supporting SMB customers can add their value-added services (e.g., networking, database management services) as part of the AWS Blueprints deployment which will provide the customers with ongoing support

AWS Control Tower (CT), AWS Organization, AWS Service Catalog and AWS Cloud Formation are some of the core AWS services used to build this AWS Blueprints framework

![image](https://user-images.githubusercontent.com/78975381/111203527-21483880-8593-11eb-92e8-d8134f1f9bef.png)
# Solution Features

**SMB partner reference implementation:** AWS partners can leverage this AWS Blueprints out-of-the box, or as a reference implementation that the partners can customize to meet the unique solution and support needs from the SMB customers.

**SMB focused solutions:** The solutions that are specific to SMB customers are included as individual products under AWS service catalog portfolio.  We will continue to develop and add more products to this portfolio. The partners also can develop and add their own products in to the portfolio and also add products directly from the AWS Marketplace.

**One-click solution deployment:** The products in the AWS service catalog portfolio can be deployed by a partner or a customer in a simple one step process. The portfolios can also be easily shared across an AWS account or an AWS organization.

**Automation & efficiency:** Leverage the pre-built service catalog portfolio for deploying products and customize it as needed for your needs.

**Flexible deployment models:** Deploy AWS blueprints under partner or customer managed AWS accounts. This flexibility allows this AWS Blueprints to be easily adapted by Managed service providers (MSP), value added resellers (VARs), distributors and customers
# Architecture Overview
As an AWS partner supporting SMB customers, setting up the AWS Control Tower in your
management account is the first step and is the foundational block for this framework.
Launching AWS Control Tower will deploy the following:

- 2 organizational units, one for your shared accounts and one for accounts that will be
provisioned by your users.

- 3 shared accounts, which are the management account and isolated accounts for log
archive and security audit.

- A native cloud directory with preconfigured groups and single sign-on access.

- 20 preventive guardrails to enforce policies and 2 detective guardrails to detect
configuration violations
![image](https://user-images.githubusercontent.com/78975381/111206305-32467900-8596-11eb-9383-4de72a949aa4.png)

Deploying the Blueprints CloudFormation template (included in this solution) in the
management account will set up the following as shown in Figure 2:

- Service Catalog portfolio for business applications: Bitnami WordPress and Magento

- Service catalog portfolio for End user computing: Amazon Workspaces and AWS
directory service with simple AD

- Service catalog portfolio for backup and disaster recovery: Veeam Backup for AWS
Free Edition

Once the different portfolios are deployed into the management account, they can readily be
shared and assigned to the different member accounts. The management account is usually
the partners account and the member accounts are usually the customer accounts. The
customers can deploy their respective solutions assigned to them by the partner. More on
this topic is discussed in the deployment models section.
# Deployment Models
AWS Blueprints framework provides an AWS partner to choose an appropriate deployment and delivery models based on the type of partner and their business model. In this context, an AWS partner is defined as anyone who is a direct reseller of or an indirect reseller of AWS services to the end customers. In the industry, the former is typically referred to as an “AWS partner” and the latter is referred to as an “AWS distributor”. AWS distributors have their own portfolio of partners who buy AWS services from the distributor and sell it to their customers.

Deployment model is defined as a framework or architecture that AWS partners and distributors can implement in their management account to manage customer AWS accounts for billing, access management, policies etc. We will discuss single-tier and two-tier architectures that can be respectively used by AWS partners and distributors.

Delivery model is defined as a mechanism by which the AWS partners and distributors deliver their value-added services like Managed services to their customers as part of this deployment.
## Direct Reseller Model
Direct reseller model also referred to as the model used by “AWS partners” is a single-tier deployment model where the partner owns the control tower management account. (herein referred as management account). As illustrated in Figure 3, an Organizational Unit (OU) acts as a virtual layer to segregate different customers for the purpose of account management, consolidated billing, service control policies etc. It has to be noted that the partners can potentially create more than one OU for the same customer, however, a customer account can be part of only one OU at any point in time. Customer accounts that already exists can be invited to join this partner’s AWS organization and can be assigned an OU.

AWS Blueprints cloud formation template once deployed in the management account will create the list of portfolios and products in the AWS Service Catalog of this account (for the list of portfolios, refer to the previous section). These portfolios can be selectively shared across various customer AWS accounts through the OU’s. The individual products (e.g., WordPress) under these portfolios can then be launched by the customer or by the partner. For instance, when the customer wants to manage and deploy the portfolios, partners can create a delegated admin with Identity and Access Management (IAM) for that customer who can then manage portfolio assignments to users under that OU.
![image](https://user-images.githubusercontent.com/78975381/111212769-06c78c80-859e-11eb-9cc2-83c6cfeb5ddb.png)
## Indirect Reseller Model
Indirect reseller model also referred to as the model used by “AWS distributors” is a two-tier deployment model where the distributor owns the control tower management account and manages multiple partner account under them at scale. As illustrated in Figure 4, an Organizational Unit (OU) acts as a virtual layer to segregate different partners and their associated customer AWS accounts, for the purpose of account management, consolidated billing, service control policies etc. In this model, the customers buy AWS services from the partners rather than directly from the distributor.  It has to be noted that the distributors can potentially create more than one OU for the same partner, however, a customer account can be part of only one OU at any point in time. A partner can invite the customer accounts that already exists to join their OU.

AWS Blueprints cloud formation template once deployed in the distributor’s management account will create the list of portfolios and products in the AWS Service Catalog of this account (for the list of portfolios, refer to the previous section). These portfolios can be selectively shared across various partners at scale through the respective OUs that are assigned to each partner. The individual products (e.g., WordPress) under these portfolios can then be launched by the customer or by the partner.
![image](https://user-images.githubusercontent.com/78975381/111212835-1ba42000-859e-11eb-852b-a6c4a95f00fe.png)
## Delivery Model
Delivery model works in conjunction with the deployment model and it is a mechanism by which the service catalog portfolios are launched in the customer’s accounts and eventually managed.  For example, in the scenario 1 referenced below in Table 1, an AWS partner not only shares the service catalog portfolio with the customer, but also launches them in their account and manages them on an ongoing basis. While the former is classified as a consulting work performed by an AWS partner, the latter (ongoing management) is classified as value-added services provided by the partner.

In Table 1, we have shown possible delivery model scenarios that an AWS partner and distributor can adapt for the direct and indirect reseller deployment models. It has to be noted that in scenario 5, the customer assumes responsibility for both deploying and managing the individual products under a service catalog portfolio. In this case, the AWS partner will delegate the administrator permissions to the customer for their respective account. Delegated administrator can then import the portfolios assigned by the partner into their AWS account (customer account). The delegated administrator can also assign the IAM permissions to the users in this account to give access to launch the products under the imported portfolios.

![image](https://user-images.githubusercontent.com/78975381/111212952-42625680-859e-11eb-9a6c-e0322bf2a5ee.png)

# Before You Begin
- The AWS partner should have a basic understanding of core AWS technologies, including Amazon Virtual Private Cloud (VPC) Amazon Elastic Compute Cloud (Amazon EC2), Security Groups, Network Access Control Lists, subnetting, and routing, Cloud Formation, Service Catalog, Multi account structure, and IAM.
- 	The AWS partner should have knowledge of business applications like WordPress, Magento, SharePoint.
- 	An AWS account and console access with sufficient privileges to manipulate the required resources 
-	Multi account structure is setup using Control Tower. If customer has already multi account structure is setup, same can be used


# Deployment
This solution uses AWS CloudFormation to automate the deployment of the Blueprints Service Catalog Portfolio framework in the AWS Cloud.
## Prerequisites
If you are deploying in a Control Tower account and you should have IAM administrator access to the Management Payer Account. Follow this link to deploy Control Tower if not exists.
https://aws.amazon.com/blogs/aws/aws-control-tower-set-up-govern-a-multi-account-aws-environment/

The initial CloudFormation Template launch requires few parameters as below described. These parameters do not have default values and you will need to provide them.

*	Distributor: Specify a name to relate this solution
*	Owner: It can be same as Distributor.
*	Support Description: It can be the description of Service catalog team or Partner team. This parameter is optional, you may leave it blank.
*	Support Email: Specify an email address to reach for the support of the products deployed in the portfolio, example can be the partner AWS administrators or service catalog owner account team Email address. This parameter is optional, you may leave it blank.
*	Support Url: It can be Url to reach the support team, a ticketing system or helpdesk support. This parameter is optional, you may leave it blank.

## Launch the stack
ServiceCatalogue-BlueprintTemplate.yml is the  automated AWS CloudFormation template that deploys the AWS Blueprints Service Catalog portfolios in AWS Cloud. Please make sure that you’ve gathered all the necessary information spcified in Prerequisites for the parameters before launching the stack.<br/>
* Login to AWS console of Management account
* Open CloudFormation and click on Create Stack
* Select Upload template and provide CloudFormation template ServiceCatalogue-BlueprintTemplate.yml under deployments folder
* Enter stack name and optional parameters of the stack, run through rest of the wizard and launch the template
* Open Service Catalog, click on “Portfolio” on the left-hand side, select the portfolio that you want to assign
* Open the product “Portfolio”, click on “Groups, roles and Users” tab, click on “Add Groups, roles and Users”
* Assign users/groups/role to the portfolio

Copyright 2019 Amazon.com, Inc. or its affiliates. All Rights Reserved.

Licensed under the Apache License Version 2.0 (the "License"). You may not use this file except in compliance with the License. A copy of the License is located at

    http://www.apache.org/licenses/

or in the "license" file accompanying this file. This file is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, express or implied. See the License for the specific language governing permissions and limitations under the License.
