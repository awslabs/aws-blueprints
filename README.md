# AWS Blueprints
AWS Blueprints consists of portfolios of tested and validated AWS services and third-party
applications that AWS Distributors (which include managed service providers (MSPs) and
value-added resellers (VARs)) and AWS Solution Providers can use to deploy, manage, and
monitor solutions for their small and medium business (SMB) customers in the AWS Cloud.
As shown in Figure 1, this solution deploys repeatable, scalable portfolios using AWS Service
Catalog, which includes a mix of AWS services and third-party applications. Additionally,
AWS Distributors and AWS Solution Providers can extend this solution by integrating their
own value-added capabilities.

This solution offers the following features:
* Customizable and extensible pre-packaged portfolios: As shown in Figure 1, AWS
Distributors and AWS Solution Providers can use this solution as a reference
implementation to customize the catalog of services that will meet the unique demands
of SMB customers. AWS Distributors and AWS Solution Providers can develop and add
their own products to the portfolio and also add products directly from AWS Marketplace.
This solution deploys AWS services and applications organized into portfolios, including
Digital Presence, Data & Analytics, and Remote Work & Collaboration.Additionally, Independent Software Vendor (ISV) products from AWS Marketplace can be
created in custom portfolios. Three examples are shown in Figure 1, including Veeam
Backup for AWS Free Edition, Veritas Backup Exec™ for AWS, and Trend Micro Deep
Security.
* SMB focused solutions: This solution deploys AWS services and third-party
applications using AWS Service Catalog that are SMB-focused.
* Automated solution deployment: AWS Distributors and AWS Solution Providers can
deploy multiple configurations of the AWS services and third-party applications in the
AWS Service Catalog portfolio using an automated process. The portfolio can be shared
across AWS accounts or within AWS Organizations for a customer account.
Additionally, this solution offers flexible deployment and delivery models to AWS Distributors
and AWS Solution Providers when deploying to customer-managed AWS accounts. For
information about these flexible models, refer to the Deployment models and Delivery model
sections in this guide.

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
