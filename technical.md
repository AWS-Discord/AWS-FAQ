# Infrastructure as a Code (IaC)

There are some tools to automate your infrastructure:

- [AWS CLI](https://aws.amazon.com/cli/) - AWS Command Line Interface
- [Cloudformation](https://aws.amazon.com/cloudformation/) - Language model to provision AWS resources
- [AWS CDK](https://aws.amazon.com/cdk/) - AWS Cloud Development Kit
- [Ansible](https://docs.ansible.com/ansible/latest/scenario_guides/guide_aws.html) - Orchestration engine to automate configuration
- [Terraform](https://www.terraform.io/docs/providers/aws/index.html) - Infrastructure as Code to provision and manage any cloud, infrastructure, or service

## How to move infrastructure to code?
- [terraformer](https://github.com/GoogleCloudPlatform/terraformer)
- [former2](https://github.com/iann0036/former2)
- [AWSConsoleRecorder](https://github.com/iann0036/AWSConsoleRecorder)
- [AWS CloudFormation: Bringing existing resources into CloudFormation management](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/resource-import.html) - requires creating a CF template manually before the import

# How to architect and choose the best solution?
1. Figure out what the factors that are important to the organization are (it's rarely "the cheapest possible" or "latest hype" option)
    1. If it is an improvement to an existing product, think about the existing project stakeholders and how the change will affect them
    2. If it is a new project, think about how the product will be used in production
2. Define and compare several approaches, follow [KISS principle](https://en.wikipedia.org/wiki/KISS_principle)
3. You might want to follow [Well-Architected Framework](https://wa.aws.amazon.com/index.en.html) but take it with a grain of salt, use [YAGNI principle](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it)

## Real World Examples
1. Amazon’s [This Is My Architecture](https://aws.amazon.com/this-is-my-architecture/)
2. [AWS Solutions Implementations](https://aws.amazon.com/solutions/implementations)
3. [The Amazon Builders' Library](https://aws.amazon.com/builders-library/)
4. [AWS Cloud Adoption Framework](https://aws.amazon.com/professional-services/CAF/)
5. Take Care [About Costs](https://www.reddit.com/r/aws/comments/g1ve18/i_am_charged_60k_on_aws_without_using_anything/) 
6. AWS services in [plain English](https://expeditedsecurity.com/aws-in-plain-english/)
7. [AWS Well-Architected Lenses](https://aws.amazon.com/architecture/well-architected#AWS_Well-Architected_Lenses)

## Diagramming tools
1. [diagrams.net](https://www.diagrams.net/)
2. [Lucidchart](https://www.lucidchart.com/)
3. [Cloudcraft](https://cloudcraft.co/)
3. [mingrammer/diagrams](https://diagrams.mingrammer.com/)

# Creating Disaster Recovery plans
[Disaster Recovery](https://en.wikipedia.org/wiki/Disaster_recovery) planning is _hard_ and should be treated as a process, not one-time activity. Here are some steps that can help with DR planning:

1. Collect initial requirements like SLA documents, ISMS documentation of your critical workloads
2. Determine what is a disaster. It can be a natural disaster, failure of hardware or an attack and not only in cloud but also of your on-prem DC
3. Determine [Recovery Time Objective (RTO)](https://www.ibm.com/services/business-continuity/rto) and [Recovery Point Objective (RPO)](https://www.ibm.com/services/business-continuity/rpo) of your critical workloads
4. Talk with business to balance costs vs risks of the DR plans
5. If you have budget, you can look at  commercial tools like CloudEndure
6. Useful materials:
    1. [AWS re:Invent 2019: Backup-and-restore and disaster-recovery solutions with AWS (STG208)
](https://www.youtube.com/watch?v=7gNXfo5HZN8)
    2. [10 Tips for Developing an AWS Disaster Recovery Plan](https://medium.com/@eddies_47682/10-tips-for-developing-an-aws-disaster-recovery-plan-a708f899a442)
    3. [WA REL 9: How do you plan for disaster recovery?](https://wa.aws.amazon.com/wat.question.REL_9.en.html)

7. Use chaos engineering for automation of testing platform resiliency

## DR and AWS services
Although some services provide good scenarios for DR planning, some are making such plans complicated. When a system requires a DR plans, you must analyze used services and how they will support the plans.

Examples of services that have good DR _stories_:
1. DynamoDB - Allows backups of all data (and moderately easy restoration) as well as provides global tables (replication within seconds)
2. EC2 - Same instance types are available across multiple regions, EBS volumes can be backed up and restored
3. Route 53/CloudFront - Enables you to switch regions within seconds/minutes
4. Kinesis - cross-region replication can be easily written

Examples of services that provide bad DR _stories_:
1. Cognito - Service stores users within a region, authentication endpoints are region-bound, [user replication](https://forums.aws.amazon.com/message.jspa?messageID=916282) or backups [with password hashes](https://github.com/awslabs/multi-region-application-architecture#layers-overview) are not available
2. QLDB - _[Amazon QLDB does not support a backup and restore feature](https://aws.amazon.com/qldb/faqs#Backup_and_Restore)_...


# Software Development Kit (SDK)

AWS maintains SDK for many programming languages:

- C++ 
    - AWS SDK for [C++](https://aws.amazon.com/sdk-for-cpp/)
- Go 
    - AWS SDK for [Go](https://aws.amazon.com/sdk-for-go/)
    - AWS X-Ray SDK for [Go](https://docs.aws.amazon.com/xray/latest/devguide/xray-sdk-go.html)
- Java 
    - AWS SDK for [Java](https://aws.amazon.com/sdk-for-java/)
    - AWS IoT Device SDK for [Java](https://github.com/aws/aws-iot-device-sdk-java/blob/master/README.md)
    - AWS X-Ray SDK for [Java](https://docs.aws.amazon.com/xray/latest/devguide/xray-sdk-java.html)
- JavaScript 
    - AWS SDK for [JavaScript](https://aws.amazon.com/sdk-for-browser/)
    - AWS Mobile SDK for [JavaScript](https://docs.amplify.aws/)
    - AWS IoT Device SDK for [JavaScript](https://github.com/aws/aws-iot-device-sdk-js/blob/master/README.md)
- .NET 
    - AWS SDK for [.NET](https://aws.amazon.com/sdk-for-net/)
    - AWS Unity Mobile SDK for [.NET](https://docs.aws.amazon.com/mobile/sdkforunity/developerguide/what-is-unity-plugin.html)
    - AWS Xamarim Mobile SDK for [.NET](https://docs.aws.amazon.com/mobile/sdkforxamarin/developerguide/Welcome.html)
    - AWS Unity Mobile SDK for [.NET](https://docs.aws.amazon.com/mobile/sdkforunity/developerguide/what-is-unity-plugin.html)
    - AWS Toolkit for [Visual Studio Team Services](https://aws.amazon.com/vsts/)
    - AWS X-Ray SDK for [.NET](https://docs.aws.amazon.com/xray/latest/devguide/xray-sdk-dotnet.html)
- Node.js 
    - AWS SDK for [Node.js](https://aws.amazon.com/sdk-for-node-js/)
    - AWS X-Ray SDK for [Node.js](https://docs.aws.amazon.com/xray/latest/devguide/xray-sdk-nodejs.html)
- PHP 
    - AWS SDK for [PHP](https://aws.amazon.com/sdk-for-php/)
- Python 
    - AWS SDK for [Python](https://aws.amazon.com/sdk-for-python/)
    - AWS Mobile SDK for [Python](https://github.com/aws/aws-iot-device-sdk-python/blob/master/README.rst)
    - AWS X-Ray SDK for [Python](https://docs.aws.amazon.com/xray/latest/devguide/xray-sdk-python.html)
- Ruby 
    - AWS SDK for [Ruby](https://aws.amazon.com/sdk-for-ruby)
    - AWS X-Ray SDK for [Ruby](https://docs.aws.amazon.com/xray/latest/devguide/xray-sdk-ruby.html)


# How to use cloud in highly regulated industries?
Very often organizations that operate on regulated data like health care information or financial data might be very reluctant to move to a public cloud. They can be biased with thinking a public cloud is less secure than an in-house Data Center, cloud will not reduce costs of development and operations and in overall, it won't enable the organization to have more products in their portfolio.

Public cloud provides services to a wide range of customers and provides solutions for companies that focus on preventive controls. The cloud helps  to drive culture of innovation, comes with the widest set of tools for automation and in overall reduces costs of the technology teams.

Useful resources:
- [AWS re:Invent 2019: [REPEAT 2] The fundamentals of AWS cloud security (SEC205-R2)](https://www.youtube.com/watch?v=QMBkq6MrT2w)
- [Best practices for securing sensitive data in AWS data stores
](https://aws.amazon.com/blogs/database/best-practices-for-securing-sensitive-data-in-aws-data-stores/)
- [AWS re:Invent 2018: Architecting for Healthcare Compliance on AWS (HLC301-i)](https://www.youtube.com/watch?v=wNB5gu7klUo)
- [AWS re:Invent 2019: National Australia Bank: Automating governance in Financial Services (SEC352)](https://www.youtube.com/watch?v=ll50dAiKPoI)
- [Financial Services Industry Lens – AWS Well-Architected](https://docs.aws.amazon.com/wellarchitected/latest/financial-services-industry-lens/welcome.html)

# How to create AWS networks?
1. [Amazon VPC console wizard configurations](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_wizard.html)
2. [AWS Client VPN - Scenarios and examples](https://docs.aws.amazon.com/vpn/latest/clientvpn-admin/scenario.html)
3. [Transit Gateway](https://medium.com/@heycasey/creating-a-transit-gateway-6e3df814a07a) - ([Paul Casey](https://www.linkedin.com/in/heycasey/))
4. [autovpn](https://github.com/ttlequals0/autovpn) for on demand disposable OpenVPN endpoints
5. [AWS Systems Manager Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html)/[Bastillion](https://github.com/bastillion-io/Bastillion) to connect to EC2 instances

# Serverless

## Serverless Frameworks

There are some frameworks to help Serverless applications deploys:

- AWS Serverless Application Model [AWS SAM](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/what-is-sam.html)
- Middy for [Node.js](https://github.com/middyjs/middy)
- Claudia.js for [Node.js](https://claudiajs.com/)
- Chalice for [Python](https://github.com/aws/chalice)
- Zapp for [Python](https://github.com/Miserlou/Zappa)
- Sparta for [Go](http://gosparta.io/)
- Bref for [PHP](https://bref.sh/)
- [Serverless](https://www.serverless.com/) Framework

## Useful Serverless links

Serverless world is growing and there are many interesting articles and repositories:

- Serverless [Data Pipeline](https://anishdalal.me/aws/2020/06/26/serverless-data-pipeline.html)
- Serverless [Reference Architecture](https://www.jeremydaly.com/serverless-reference-architectures/)
- [Overcoming](https://talkingserverless.com/2020/07/05/overcoming-serverless-limitations/) Serverless limitations
- The Stanford [Builder](https://github.com/StanfordSNR/gg) using AWS Lambda - Amazing project
- AWS Lamba [abuse](https://luminousmen.com/post/aws-lambda-abuse)
- Load testing a web application’s [serverless backend](https://aws.amazon.com/blogs/compute/load-testing-a-web-applications-serverless-backend/)
- AWS Lambda [powertools](https://github.com/awslabs/aws-lambda-powertools-python)
- Building [COBOL](https://github.com/BluAge/ServerlessCOBOLforAWS) applications on Lambda
- [Complete Guide to Lambda Triggers](https://dashbird.io/blog/complete-guide-lambda-triggers-design-patterns-part-1/) and Design Patterns (Part 1)
- [Managing backend requests](https://aws.amazon.com/blogs/compute/managing-backend-requests-and-frontend-notifications-in-serverless-web-apps/) and frontend notifications in serverless web apps
- [AWS Lambda offline development](https://www.vittorionardone.it/en/2020/05/12/aws-lambda-offline-development-with-docker/) with Docker
- Serverless: a backend thing that gives [superpowers to frontend developers](https://dev.to/aws-heroes/serverless-a-backend-thing-that-gives-superpowers-to-frontend-developers-163c)
- [CDK Patterns](https://cdkpatterns.com/)
