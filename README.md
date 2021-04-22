# AWS Blueprints
The AWS cloud provides many of the building blocks required to help customers implement a secure, flexible self-serving solution to launch AWS services and solutions. This solution in intended to address customers pain point around the need to have sophisticated AWS builders and developers to develop a solution that is needed for their business. This solution automatically configures the core AWS foundational blocks that include a multi-account AWS environment, account factory to create new AWS accounts in a click, security and governance already built in for these accounts. This solution also adds a catalog where new AWS services, solutions are added and can be readily shared within an account or to a different account.

AWS control tower (CT) is leveraged to create an automated landing zone that employs best-practices such as configuring multi-account structure using AWS Organizations, managing user identities and federated access with AWS Single Sign-on, enabling account provisioning through AWS Service Catalog, and creating a centralized log archive using AWS CloudTrail and AWS Config. AWS Guardrail is used for ongoing governance, pre-configured guardrails can be enabled to clearly define rules for security, operations, and compliance which prevents deployment of resources that don’t conform to policies and continuously monitor deployed resources for nonconformance.

Finally, AWS CloudFormation (CF) templates are used to add new products, portfolios to the AWS Service Catalog. The CF templates can be custom developed by an organization or adopted from the AWS Quick starts which can be readily launched by the customers. There are thousands of Independent Software Vendor (ISV) products available via AWS Marketplace offered by AWS partners that can be deployed as a service catalog product to quickly extend the solution offerings in your AWS account.


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
