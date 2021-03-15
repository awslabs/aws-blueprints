# AWS Blueprints
The AWS Blueprints enables the AWS partners to quickly deploy, manage and, monitor solutions for their Small and Medium Business (SMB) customers in the AWS cloud. SMB
customers typically have a small technical team and usually seek support from an AWS partner to get started in their cloud journey. Many of these AWS partners who support the SMB customers themselves need assistance with transforming their practice and build solutions in AWS for their SMB customers. These partners are seeking solutions and support
that will get them to market faster, meet the rapidly changing needs of their customers, and enable them to deliver to their customers at high velocity.

AWS Blueprints offers a “1-Click solution deployment” framework (Figure 1) that the partners can use instantly to deploy SMB focused solutions to their customers in a repeatable, scalable and cost-efficient fashion. The SMB solutions that are included in this AWS Blueprints covers diverse SMB customer use cases starting with business applications (Magento, WordPress & SharePoint), end user computing (Amazon Workspaces), business continuity (Veeam backup solution), and data analytics (AWS Data Lake foundation). AWS solutions built by the AWS partners and the Independent Software Vendors (ISV) for other use cases can also be easily added to this “1-Click-Deployment” framework. AWS partners supporting SMB customers can add their value-added services (e.g., networking, database management services) as part of the AWS Blueprints deployment which will provide the customers with ongoing support

AWS Control Tower (CT), AWS Organization, AWS Service Catalog and AWS Cloud Formation are some of the core AWS services used to build this AWS Blueprints framework

![image](https://user-images.githubusercontent.com/78975381/111203527-21483880-8593-11eb-92e8-d8134f1f9bef.png)
# Solution Features

SMB partner reference implementation: AWS partners can leverage this AWS Blueprints out-of-the box, or as a reference implementation that the partners can customize to meet the unique solution and support needs from the SMB customers.
SMB focused solutions: The solutions that are specific to SMB customers are included as individual products under AWS service catalog portfolio.  We will continue to develop and add more products to this portfolio. The partners also can develop and add their own products in to the portfolio and also add products directly from the AWS Marketplace.
One-click solution deployment: The products in the AWS service catalog portfolio can be deployed by a partner or a customer in a simple one step process. The portfolios can also be easily shared across an AWS account or an AWS organization.
Automation & efficiency: Leverage the pre-built service catalog portfolio for deploying products and customize it as needed for your needs.
Flexible deployment models: Deploy AWS blueprints under partner or customer managed AWS accounts. This flexibility allows this AWS Blueprints to be easily adapted by Managed service providers (MSP), value added resellers (VARs), distributors and customers

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
