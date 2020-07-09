# Infrastructure as a Code (IaC)

There are some tools to automate your infrastructure:

- [AWS CLI](https://aws.amazon.com/cli/) - AWS Command Line Interface
- [Cloudformation](https://aws.amazon.com/cloudformation/) - Language model to provision AWS resources
- [AWS CDK](https://aws.amazon.com/cdk/) - AWS Cloud Development Kit
- [Ansible](https://docs.ansible.com/ansible/latest/scenario_guides/guide_aws.html) - Orchestration engine to automate configuration
- [Terraform](https://www.terraform.io/docs/providers/aws/index.html) - Infrastructure as Code to provision and manage any cloud, infrastructure, or service


# How to architect and choose the best solution?
1. Figure out what the factors that are important to the organization are (it's rarely "cheapest possible" or "latest hype" option)

    1. If it is an improvement to an existing product, think about the existing project stakeholders and how the change will affect them
    
    2. If it is a new project, think about how the product will be used in production

2. Define and compare several approaches, follow [KISS principle](https://en.wikipedia.org/wiki/KISS_principle)

3. You might want to follow [Well-Architected Framework](https://wa.aws.amazon.com/index.en.html) but take it with a grain of salt, use [YAGNI principle](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it)


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
1. DynamoDB - the service allows backups of all data (and moderately easy restoration) as well as global tables (replication within seconds)
2. EC2 - Same instance types are available across multiple regions, EBS volumes can be backed up and restored
3. Route 53/CloudFront - enable you to switch regions within seconds/minutes
4. Kinesis - cross-region replication can be easily written

Examples of services that provide bad DR _stories_:
1. Cognito - service stores users within a region, authentication endpoints are region-bound, user backups with password hashes are not available
2. QLDB - _[Amazon QLDB does not support a backup and restore feature](https://aws.amazon.com/qldb/faqs#Backup_and_Restore)_...


# Software Development Kit (SDK)

AWS maintains SDK for many programming languages:

- C++ 
    - AWS SDK for [C++](https://aws.amazon.com/sdk-for-cpp/)

- Go 
    - AWS SDK for [Go](https://aws.amazon.com/sdk-for-go/)

- Java 
    - AWS SDK for [Java](https://aws.amazon.com/sdk-for-java/)
    - AWS IoT Device SDK for [Java](https://github.com/aws/aws-iot-device-sdk-java/blob/master/README.md)

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

- Node.js 
    - AWS SDK for [Node.js](https://aws.amazon.com/sdk-for-node-js/)

- PHP 
    - AWS SDK for [PHP](https://aws.amazon.com/sdk-for-php/)

- Python 
    - AWS SDK for [Python](https://aws.amazon.com/sdk-for-python/)
    - AWS Mobile SDK for [Python](https://github.com/aws/aws-iot-device-sdk-python/blob/master/README.rst)

- Ruby 
    - AWS SDK for [Ruby](https://aws.amazon.com/sdk-for-ruby)

# Serverless Framework

There are some frameworks to help Serverless applications deploys:

- AWS Serverless Application Model [AWS SAM](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/what-is-sam.html)
- Middy for [Node.js](https://github.com/middyjs/middy)
- Claudia.js for [Node.js](https://claudiajs.com/)
- Chalice for [Python](https://github.com/aws/chalice)
- Zapp for [Python](https://github.com/Miserlou/Zappa)
- Sparta for [Go](http://gosparta.io/)
- Bref for [PHP](https://bref.sh/)
- [Serverless](https://www.serverless.com/) Framework
