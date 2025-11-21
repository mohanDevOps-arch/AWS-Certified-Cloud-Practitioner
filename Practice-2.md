# AWS Cloud Practitioner Practice Exam - Set 2

## Practice Exam Questions 1-65

### Question 1
A company wants to migrate their on-premises Oracle database to AWS while minimizing changes to their application code. Which AWS service should they use?
- A. Amazon DynamoDB
- B. Amazon Aurora
- C. Amazon RDS for Oracle
- D. Amazon Redshift

**Answer: C** - RDS for Oracle provides a managed Oracle database, allowing migration with minimal application changes



### Question 2
Which AWS service allows you to run code in response to HTTP requests without provisioning servers?
- A. Amazon EC2
- B. AWS Lambda
- C. Amazon ECS
- D. AWS Elastic Beanstalk

**Answer: B** - AWS Lambda is serverless and can be triggered by HTTP requests via API Gateway



### Question 3
A company needs to ensure that their AWS architecture can handle the failure of an entire Availability Zone. What is the MINIMUM number of Availability Zones they should deploy across?
- A. 1
- B. 2
- C. 3
- D. 4

**Answer: B** - Deploying across at least 2 AZs ensures resilience if one AZ fails



### Question 4
Which AWS service provides a fully managed NoSQL database with built-in security, backup and restore, and in-memory caching?
- A. Amazon RDS
- B. Amazon ElastiCache
- C. Amazon DynamoDB
- D. Amazon Neptune

**Answer: C** - DynamoDB is a fully managed NoSQL database with built-in security, backups, and optional DAX for caching



### Question 5
A startup wants to deploy a web application quickly without managing infrastructure. They need automatic scaling and load balancing. Which service is MOST appropriate?
- A. Amazon EC2 with manual configuration
- B. AWS Lambda
- C. AWS Elastic Beanstalk
- D. Amazon Lightsail

**Answer: C** - Elastic Beanstalk automatically handles deployment, scaling, and load balancing for web applications



### Question 6
Which AWS service enables you to create a private, isolated section of the AWS Cloud where you can launch resources in a virtual network?
- A. Amazon VPC
- B. AWS Direct Connect
- C. Amazon CloudFront
- D. AWS Transit Gateway

**Answer: A** - Amazon VPC allows you to create an isolated virtual network within AWS



### Question 7
A company needs to store infrequently accessed data that must be retrieved within milliseconds when needed. Which S3 storage class is MOST appropriate?
- A. S3 Standard
- B. S3 Standard-IA (Infrequent Access)
- C. S3 One Zone-IA
- D. S3 Glacier Instant Retrieval

**Answer: B** - S3 Standard-IA provides millisecond retrieval for infrequently accessed data at lower cost than S3 Standard



### Question 8
Which AWS support plan provides 24/7 access to Cloud Support Engineers via email, chat, and phone?
- A. Basic Support
- B. Developer Support
- C. Business Support
- D. All support plans include this

**Answer: C** - Business Support and Enterprise Support provide 24/7 technical support via multiple channels



### Question 9
A company wants to provide laptop computers to contractors with secure access to AWS resources. The laptops must not store credentials locally. What is the BEST solution?
- A. IAM users with access keys
- B. Root account credentials
- C. IAM Identity Center (AWS SSO) with temporary credentials
- D. Hardcoded passwords in applications

**Answer: C** - IAM Identity Center provides centralized access management with temporary credentials, no local credential storage



### Question 10
Which AWS service helps you optimize costs by identifying idle and underutilized resources?
- A. AWS Budgets
- B. AWS Cost Explorer
- C. AWS Trusted Advisor
- D. AWS CloudWatch

**Answer: C** - AWS Trusted Advisor provides recommendations including cost optimization checks for idle resources



### Question 11
A company needs to process batch jobs that can tolerate interruptions and have flexible start times. What is the MOST cost-effective EC2 pricing option?
- A. On-Demand Instances
- B. Reserved Instances
- C. Spot Instances
- D. Dedicated Hosts

**Answer: C** - Spot Instances offer significant discounts for interruptible workloads with flexible timing



### Question 12
Which AWS database service is designed for graph use cases such as social networks and recommendation engines?
- A. Amazon DynamoDB
- B. Amazon Neptune
- C. Amazon RDS
- D. Amazon DocumentDB

**Answer: B** - Amazon Neptune is a fully managed graph database service



### Question 13
A company wants to detect and respond to security threats in their AWS environment using machine learning. Which service should they use?
- A. AWS Shield
- B. AWS WAF
- C. Amazon GuardDuty
- D. AWS Security Hub

**Answer: C** - Amazon GuardDuty uses machine learning to detect threats and unusual behavior



### Question 14
Which feature of Amazon S3 automatically replicates objects to another AWS Region for disaster recovery?
- A. S3 Versioning
- B. S3 Cross-Region Replication (CRR)
- C. S3 Transfer Acceleration
- D. S3 Lifecycle policies

**Answer: B** - S3 Cross-Region Replication automatically replicates objects across regions



### Question 15
A developer needs to deploy and version control APIs with features like throttling and authorization. Which AWS service is designed for this?
- A. Amazon Route 53
- B. AWS Lambda
- C. Amazon API Gateway
- D. Elastic Load Balancing

**Answer: C** - Amazon API Gateway enables creating, deploying, and managing APIs with built-in security and throttling



### Question 16
What is the primary benefit of AWS Regions being independent of each other?
- A. Lower costs
- B. Fault isolation and stability
- C. Faster performance
- D. Easier management

**Answer: B** - Regional independence provides fault isolation, so issues in one region don't affect others



### Question 17
A company needs to run Windows-based applications in the cloud. Which compute service supports Windows operating systems?
- A. AWS Lambda only
- B. Amazon EC2
- C. Amazon ECS with Linux containers only
- D. AWS Fargate with Linux only

**Answer: B** - Amazon EC2 supports both Windows and Linux operating systems



### Question 18
Which AWS service provides centralized governance and management across multiple AWS accounts?
- A. AWS IAM
- B. AWS Organizations
- C. AWS Control Tower
- D. AWS Systems Manager

**Answer: B** - AWS Organizations enables central management and governance of multiple AWS accounts



### Question 19
A company wants to implement DDoS protection for their web application. Which AWS service provides this at no additional cost?
- A. AWS WAF
- B. AWS Shield Standard
- C. AWS Shield Advanced
- D. Amazon GuardDuty

**Answer: B** - AWS Shield Standard provides automatic DDoS protection at no additional cost



### Question 20
Which AWS service allows you to run MySQL and PostgreSQL databases with up to 5 times better performance than standard implementations?
- A. Amazon RDS
- B. Amazon Aurora
- C. Amazon DynamoDB
- D. Amazon Redshift

**Answer: B** - Amazon Aurora is MySQL and PostgreSQL-compatible with enhanced performance



### Question 21
A company needs to store and share files that multiple EC2 instances can access simultaneously. Which storage service should they use?
- A. Amazon EBS
- B. Amazon S3
- C. Amazon EFS (Elastic File System)
- D. Instance Store

**Answer: C** - Amazon EFS provides shared file storage accessible by multiple EC2 instances simultaneously



### Question 22
Which AWS service enables you to provision infrastructure using declarative templates written in JSON or YAML?
- A. AWS OpsWorks
- B. AWS CloudFormation
- C. AWS CodeDeploy
- D. AWS Systems Manager

**Answer: B** - AWS CloudFormation uses JSON or YAML templates for infrastructure as code



### Question 23
A company wants to analyze clickstream data from their website in real-time. Which service combination is MOST suitable?
- A. S3 + Athena
- B. Kinesis Data Firehose + S3 + Redshift
- C. RDS + Lambda
- D. DynamoDB + ElastiCache

**Answer: B** - Kinesis Firehose captures streaming data, stores in S3, and loads into Redshift for analysis



### Question 24
What is the maximum duration for a single AWS Lambda function execution?
- A. 5 minutes
- B. 15 minutes
- C. 30 minutes
- D. 1 hour

**Answer: B** - AWS Lambda functions can run for a maximum of 15 minutes



### Question 25
Which AWS service provides a managed message broker service compatible with Apache ActiveMQ and RabbitMQ?
- A. Amazon SQS
- B. Amazon SNS
- C. Amazon MQ
- D. Amazon Kinesis

**Answer: C** - Amazon MQ is a managed message broker supporting ActiveMQ and RabbitMQ



### Question 26
A company needs to ensure their S3 data is protected against accidental deletion. Which feature should they enable?
- A. S3 Lifecycle policies
- B. S3 Versioning
- C. S3 Transfer Acceleration
- D. S3 Replication

**Answer: B** - S3 Versioning maintains multiple versions of objects, protecting against accidental deletion



### Question 27
Which AWS service provides recommendations for improving security, performance, cost optimization, and fault tolerance?
- A. AWS Config
- B. AWS Trusted Advisor
- C. AWS Inspector
- D. AWS Personal Health Dashboard

**Answer: B** - AWS Trusted Advisor provides best practice recommendations across multiple categories



### Question 28
A company wants to deploy containerized applications without managing servers. Which service provides serverless containers?
- A. Amazon ECS on EC2
- B. Amazon EKS
- C. AWS Fargate
- D. AWS Lambda

**Answer: C** - AWS Fargate runs containers without managing underlying servers (serverless containers)



### Question 29
Which AWS service helps you track and categorize AWS costs by assigning metadata to resources?
- A. AWS Budgets
- B. Cost Allocation Tags
- C. AWS Cost Explorer
- D. AWS Organizations

**Answer: B** - Cost Allocation Tags allow categorizing and tracking costs by assigning custom tags to resources



### Question 30
A development team needs isolated environments that are quick to set up and tear down for testing. Which service is MOST appropriate?
- A. Amazon EC2 with manual configuration
- B. AWS CloudFormation
- C. AWS OpsWorks
- D. Amazon Lightsail

**Answer: B** - CloudFormation templates enable quick, repeatable environment provisioning and deletion



### Question 31
Which AWS service provides a fully managed Apache Kafka-compatible event streaming platform?
- A. Amazon Kinesis Data Streams
- B. Amazon MSK (Managed Streaming for Apache Kafka)
- C. Amazon SQS
- D. Amazon EventBridge

**Answer: B** - Amazon MSK provides fully managed Apache Kafka clusters



### Question 32
A company needs to migrate a large dataset to AWS but has limited bandwidth. The data is stored on NFS shares. Which service should they use?
- A. AWS Storage Gateway
- B. AWS Snowcone
- C. AWS DataSync
- D. S3 Transfer Acceleration

**Answer: B** - AWS Snowcone is a small, portable device for edge computing and data transfer, suitable for limited bandwidth scenarios



### Question 33
Which AWS service provides automated vulnerability assessments and compliance scanning for container images?
- A. Amazon Inspector
- B. Amazon ECR image scanning
- C. AWS Security Hub
- D. Amazon GuardDuty

**Answer: B** - Amazon ECR includes image scanning to detect vulnerabilities in container images



### Question 34
A company wants to forecast future AWS costs based on historical usage. Which tool should they use?
- A. AWS Budgets
- B. AWS Cost Explorer with forecasting
- C. AWS Pricing Calculator
- D. AWS Trusted Advisor

**Answer: B** - AWS Cost Explorer includes forecasting capabilities based on historical usage patterns



### Question 35
Which AWS service allows you to run code at AWS edge locations in response to CloudFront events?
- A. AWS Lambda
- B. Lambda@Edge
- C. Amazon CloudFront Functions
- D. Both B and C

**Answer: D** - Both Lambda@Edge and CloudFront Functions run code at edge locations, with different use cases and capabilities



### Question 36
A company needs to store objects larger than 5 TB. Which AWS service supports this?
- A. Amazon S3
- B. Amazon EBS
- C. Amazon EFS
- D. All of the above

**Answer: D** - All three services can store objects/volumes larger than 5 TB (S3 max object is 5TB but bucket size unlimited)



### Question 37
Which AWS service provides managed Denial of Service (DDoS) protection with 24/7 DDoS Response Team support?
- A. AWS Shield Standard
- B. AWS Shield Advanced
- C. AWS WAF
- D. Amazon GuardDuty

**Answer: B** - AWS Shield Advanced includes 24/7 DDoS Response Team (DRT) support



### Question 38
A company wants to implement a serverless data warehouse for analytics. Which service should they use?
- A. Amazon RDS
- B. Amazon Redshift Serverless
- C. Amazon Aurora Serverless
- D. Amazon Athena

**Answer: B** - Amazon Redshift Serverless provides a serverless data warehouse without infrastructure management



### Question 39
Which AWS service enables you to discover, prepare, and combine data for analytics and machine learning?
- A. AWS Glue
- B. Amazon EMR
- C. AWS Data Pipeline
- D. Amazon Athena

**Answer: A** - AWS Glue is a serverless data integration service for ETL workloads



### Question 40
A company needs to store encryption keys with hardware security modules (HSMs) for compliance. Which service should they use?
- A. AWS KMS
- B. AWS CloudHSM
- C. AWS Secrets Manager
- D. AWS Certificate Manager

**Answer: B** - AWS CloudHSM provides dedicated hardware security modules for regulatory compliance



### Question 41
Which AWS service provides a content delivery network (CDN) that caches content at edge locations worldwide?
- A. Amazon Route 53
- B. Amazon CloudFront
- C. AWS Global Accelerator
- D. Elastic Load Balancing

**Answer: B** - Amazon CloudFront is AWS's CDN service for content delivery



### Question 42
A company wants to manage and rotate database credentials automatically. Which service should they use?
- A. AWS KMS
- B. AWS Secrets Manager
- C. AWS Systems Manager Parameter Store
- D. AWS IAM

**Answer: B** - AWS Secrets Manager automatically rotates credentials and manages secrets



### Question 43
Which AWS service provides a managed blockchain network using Hyperledger Fabric and Ethereum?
- A. Amazon QLDB
- B. Amazon DynamoDB
- C. Amazon Managed Blockchain
- D. AWS Blockchain Gateway

**Answer: C** - Amazon Managed Blockchain supports Hyperledger Fabric and Ethereum frameworks



### Question 44
A company needs a fully managed ledger database that provides a cryptographically verifiable transaction log. Which service should they use?
- A. Amazon DynamoDB
- B. Amazon QLDB (Quantum Ledger Database)
- C. Amazon RDS
- D. Amazon Timestream

**Answer: B** - Amazon QLDB provides an immutable, cryptographically verifiable ledger



### Question 45
Which AWS service enables you to deploy machine learning models for inference without managing infrastructure?
- A. Amazon SageMaker
- B. AWS Lambda
- C. Amazon EC2
- D. AWS Batch

**Answer: A** - Amazon SageMaker provides fully managed ML model deployment and inference



### Question 46
A company wants to build a time-series database for IoT applications. Which purpose-built database should they use?
- A. Amazon DynamoDB
- B. Amazon Timestream
- C. Amazon RDS
- D. Amazon Redshift

**Answer: B** - Amazon Timestream is purpose-built for time-series data from IoT and operational applications



### Question 47
Which AWS service provides DNS and domain registration services?
- A. AWS Direct Connect
- B. Amazon Route 53
- C. Amazon CloudFront
- D. AWS Global Accelerator

**Answer: B** - Amazon Route 53 provides DNS services and domain registration



### Question 48
A company needs to orchestrate multiple AWS services into serverless workflows. Which service should they use?
- A. AWS Lambda
- B. AWS Step Functions
- C. Amazon SQS
- D. AWS Batch

**Answer: B** - AWS Step Functions coordinates multiple AWS services into serverless workflows



### Question 49
Which AWS service provides recommendations for optimizing EC2 instance types and sizes based on utilization?
- A. AWS Cost Explorer
- B. AWS Trusted Advisor
- C. AWS Compute Optimizer
- D. AWS Budgets

**Answer: C** - AWS Compute Optimizer analyzes utilization and recommends optimal instance types



### Question 50
A company needs to create private connectivity between their VPC and AWS services without using the internet. Which feature should they use?
- A. Internet Gateway
- B. NAT Gateway
- C. VPC Endpoints
- D. VPN Connection

**Answer: C** - VPC Endpoints enable private connectivity to AWS services without internet access



### Question 51
Which AWS service provides a fully managed in-memory data store compatible with Redis and Memcached?
- A. Amazon DynamoDB
- B. Amazon ElastiCache
- C. Amazon RDS
- D. Amazon DocumentDB

**Answer: B** - Amazon ElastiCache supports both Redis and Memcached engines



### Question 52
A company wants to set spending limits and receive alerts when AWS costs approach those limits. Which service should they use?
- A. AWS Cost Explorer
- B. AWS Budgets
- C. AWS Billing Dashboard
- D. AWS Organizations

**Answer: B** - AWS Budgets allows setting custom cost and usage budgets with alerts



### Question 53
Which AWS service provides a fully managed ETL (Extract, Transform, Load) service?
- A. AWS Data Pipeline
- B. AWS Glue
- C. Amazon EMR
- D. AWS Database Migration Service

**Answer: B** - AWS Glue is a fully managed serverless ETL service



### Question 54
A company needs to monitor API calls made to AWS services for security auditing. Which service logs this information?
- A. Amazon CloudWatch
- B. AWS CloudTrail
- C. AWS Config
- D. VPC Flow Logs

**Answer: B** - AWS CloudTrail logs all API calls made to AWS services



### Question 55
Which AWS service provides a scalable search service based on Apache Lucene?
- A. Amazon CloudSearch
- B. Amazon OpenSearch Service (formerly Elasticsearch)
- C. Amazon Kendra
- D. Amazon Athena

**Answer: B** - Amazon OpenSearch Service provides managed search and analytics based on Apache Lucene



### Question 56
A company wants to implement disaster recovery with the lowest cost and can tolerate several hours of downtime. Which DR strategy is MOST appropriate?
- A. Multi-Site Active/Active
- B. Warm Standby
- C. Pilot Light
- D. Backup and Restore

**Answer: D** - Backup and Restore is the lowest cost DR strategy, suitable when several hours of downtime is acceptable



### Question 57
Which AWS service provides intelligent document processing using machine learning to extract data from documents?
- A. Amazon Textract
- B. Amazon Rekognition
- C. Amazon Comprehend
- D. Amazon Transcribe

**Answer: A** - Amazon Textract extracts text and data from scanned documents using ML



### Question 58
A company needs to connect their on-premises network to multiple VPCs in different AWS Regions. Which service provides a centralized hub for this?
- A. VPC Peering
- B. AWS Transit Gateway
- C. AWS Direct Connect
- D. VPN Connection

**Answer: B** - AWS Transit Gateway acts as a central hub to connect VPCs and on-premises networks



### Question 59
Which AWS service provides natural language processing to analyze text for sentiment, entities, and key phrases?
- A. Amazon Polly
- B. Amazon Transcribe
- C. Amazon Comprehend
- D. Amazon Lex

**Answer: C** - Amazon Comprehend uses NLP to analyze and extract insights from text



### Question 60
A company wants to convert text to lifelike speech. Which AWS service should they use?
- A. Amazon Transcribe
- B. Amazon Polly
- C. Amazon Translate
- D. Amazon Lex

**Answer: B** - Amazon Polly converts text into natural-sounding speech



### Question 61
Which AWS service provides automated backup services for AWS resources across multiple services?
- A. AWS Backup
- B. Amazon S3
- C. AWS Storage Gateway
- D. AWS DataSync

**Answer: A** - AWS Backup provides centralized, automated backup across multiple AWS services



### Question 62
A company needs to build conversational interfaces using voice and text. Which AWS service provides this capability?
- A. Amazon Polly
- B. Amazon Lex
- C. Amazon Connect
- D. Amazon Transcribe

**Answer: B** - Amazon Lex builds conversational chatbots and voice assistants



### Question 63
Which AWS storage service provides a file gateway that enables on-premises applications to access cloud storage via NFS and SMB protocols?
- A. Amazon EFS
- B. Amazon FSx
- C. AWS Storage Gateway
- D. AWS DataSync

**Answer: C** - AWS Storage Gateway provides hybrid cloud storage with file gateway supporting NFS/SMB



### Question 64
A company wants to deploy Windows File Server with fully managed shared file storage. Which service should they use?
- A. Amazon EFS
- B. Amazon FSx for Windows File Server
- C. Amazon S3
- D. AWS Storage Gateway

**Answer: B** - Amazon FSx for Windows File Server provides fully managed Windows-native shared file storage



### Question 65
Which AWS service provides a managed Apache Cassandra-compatible database?
- A. Amazon DynamoDB
- B. Amazon Keyspaces
- C. Amazon DocumentDB
- D. Amazon Neptune

**Answer: B** - Amazon Keyspaces is a managed Cassandra-compatible database service



## Answer Summary

**Questions 1-65 Answer Key:**
1. C  2. B  3. B  4. C  5. C  6. A  7. B  8. C  9. C  10. C  
11. C  12. B  13. C  14. B  15. C  16. B  17. B  18. B  19. B  20. B  
21. C  22. B  23. B  24. B  25. C  26. B  27. B  28. C  29. B  30. B  
31. B  32. B  33. B  34. B  35. D  36. D  37. B  38. B  39. A  40. B  
41. B  42. B  43. C  44. B  45. A  46. B  47. B  48. B  49. C  50. C  
51. B  52. B  53. B  54. B  55. B  56. D  57. A  58. B  59. C  60. B  
61. A  62. B  63. C  64. B  65. B

#
- Study hybrid cloud connectivity options
