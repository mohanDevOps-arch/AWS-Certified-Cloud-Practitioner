# AWS Cloud Practitioner Practice Exam - 01

## Practice Exam Questions 1-65

### Question 1
A company wants to host a web application on AWS. The application needs to handle sudden traffic spikes during product launches while minimizing costs during normal operations. Which combination of AWS services would be MOST appropriate? (Choose TWO)
- A. Amazon EC2 with Auto Scaling
- B. Amazon EC2 Reserved Instances only
- C. Elastic Load Balancing
- D. AWS Direct Connect
- E. Amazon CloudFront with AWS WAF

**Answer: A, C** - Auto Scaling handles traffic variations automatically, and ELB distributes traffic across instances



### Question 2
An organization needs to comply with regulations requiring all API calls to AWS services to be logged and stored for 5 years. The logs must be tamper-proof. Which solution meets these requirements?
- A. Enable AWS CloudTrail and store logs in an S3 bucket with versioning
- B. Enable AWS CloudTrail with log file validation and store logs in S3 with Object Lock
- C. Use Amazon CloudWatch Logs with log retention set to 5 years
- D. Enable AWS Config and store configuration history in S3

**Answer: B** - CloudTrail captures API calls, log file validation ensures integrity, and S3 Object Lock prevents deletion/modification



### Question 3
A financial institution needs to run a compliance report that analyzes all security group configurations across multiple AWS accounts. Which AWS service would provide this capability with the LEAST operational overhead?
- A. AWS CloudTrail
- B. Amazon CloudWatch
- C. AWS Config
- D. AWS Systems Manager

**Answer: C** - AWS Config tracks resource configurations across accounts and can run compliance checks against security group rules



### Question 4
A startup is building a serverless application. They need to store user session data that expires after 24 hours and can handle thousands of reads and writes per second with single-digit millisecond latency. Which service should they use?
- A. Amazon RDS with automatic backups
- B. Amazon DynamoDB with TTL (Time To Live) enabled
- C. Amazon S3 with lifecycle policies
- D. Amazon ElastiCache for Memcached

**Answer: B** - DynamoDB provides low-latency NoSQL storage, TTL automatically expires items, and it scales for high throughput



### Question 5
A company has a three-tier web application with web servers, application servers, and database servers. They want to ensure the database servers cannot be accessed directly from the internet but can communicate with application servers. How should they configure their VPC?
- A. Place all servers in a public subnet with security groups
- B. Place web servers in a public subnet and application/database servers in a private subnet
- C. Place web and application servers in a public subnet and database servers in a private subnet
- D. Use a single subnet with Network ACLs to control access

**Answer: C** - Web servers need internet access (public subnet), application servers need internet for updates (public with NAT), database servers should be isolated (private subnet)



### Question 6
An organization is migrating a 50 TB database to AWS. They have a 100 Mbps internet connection and need to complete the migration within 2 weeks. Which service would be MOST appropriate?
- A. AWS Direct Connect
- B. AWS DataSync over internet
- C. AWS Snowball
- D. AWS Database Migration Service over VPN

**Answer: C** - With 100 Mbps, transferring 50 TB would take approximately 46 days. Snowball is designed for large data transfers when network transfer is impractical



### Question 7
A company wants to implement a disaster recovery strategy for their critical application with an RTO of 4 hours and RPO of 1 hour. The solution must be cost-effective. Which DR strategy should they choose?
- A. Backup and Restore
- B. Pilot Light
- C. Warm Standby
- D. Multi-Site Active/Active

**Answer: B** - Pilot Light maintains minimal critical resources running, can meet 4-hour RTO and 1-hour RPO, and is more cost-effective than Warm Standby or Multi-Site



### Question 8
A media company stores video files that are frequently accessed for the first 30 days, occasionally accessed for the next 60 days, and rarely accessed afterward but must be retained for 7 years. What is the MOST cost-optimized storage strategy?
- A. Store all data in S3 Standard for 7 years
- B. Use S3 Intelligent-Tiering for all data
- C. Use S3 Lifecycle policies: S3 Standard for 30 days, S3 Standard-IA for 60 days, then S3 Glacier Flexible Retrieval
- D. Store directly in S3 Glacier Deep Archive

**Answer: C** - Lifecycle policies automatically transition objects between storage classes based on access patterns, optimizing costs at each stage



### Question 9
A development team needs temporary AWS credentials to access resources in a production account from their development account. What is the MOST secure way to provide this access?
- A. Share IAM user credentials between accounts
- B. Create an IAM role in the production account with a trust policy allowing the development account to assume it
- C. Use AWS Organizations to merge the accounts
- D. Create identical IAM users in both accounts

**Answer: B** - Cross-account IAM roles with assume role permissions provide temporary credentials without sharing long-term credentials



### Question 10
A company receives thousands of sensor data points per second that need to be processed in real-time and stored for analysis. Which combination of services would be MOST suitable? (Choose TWO)
- A. Amazon Kinesis Data Streams for ingestion
- B. Amazon SQS for ingestion
- C. AWS Lambda for processing
- D. Amazon EC2 for processing
- E. Amazon RDS for storage

**Answer: A, C** - Kinesis Data Streams handles real-time streaming data at scale, Lambda processes data serverlessly with automatic scaling



### Question 11
An e-commerce company wants to analyze customer behavior patterns from their web application logs. They need to run complex SQL queries without managing infrastructure. Which service should they use?
- A. Amazon RDS
- B. Amazon Redshift
- C. Amazon Athena
- D. Amazon EMR

**Answer: C** - Amazon Athena allows SQL queries directly on S3 data without infrastructure management, perfect for log analysis



### Question 12
A healthcare application must encrypt all data at rest and in transit. The encryption keys must be rotated annually and access to keys must be audited. Which solution meets these requirements?
- A. Use AWS KMS with automatic key rotation and CloudTrail logging
- B. Use S3 server-side encryption with Amazon S3-managed keys
- C. Implement application-level encryption with keys stored in the code
- D. Use EBS encryption with default AWS-managed keys

**Answer: A** - KMS provides key management with automatic rotation, and CloudTrail logs all key usage for audit compliance



### Question 13
A company wants to ensure their EC2 instances are patched regularly and compliant with security baselines. Which service automates this process?
- A. AWS Config
- B. AWS Systems Manager Patch Manager
- C. AWS CloudTrail
- D. Amazon Inspector

**Answer: B** - Systems Manager Patch Manager automates the patching process for EC2 instances and on-premises servers



### Question 14
An organization has multiple departments, each with their own AWS account. They want to share a centrally managed Amazon VPC across all accounts. Which service enables this?
- A. VPC Peering
- B. AWS Transit Gateway
- C. AWS Resource Access Manager (RAM)
- D. AWS Direct Connect Gateway

**Answer: C** - AWS RAM allows sharing of VPCs and subnets across AWS accounts within an organization



### Question 15
A company's application uses Amazon RDS for MySQL. They need to ensure the database can automatically failover to another Availability Zone if the primary fails. What should they enable?
- A. Read Replicas
- B. Multi-AZ deployment
- C. Automated backups
- D. Manual snapshots

**Answer: B** - Multi-AZ deployment provides automatic failover to a standby instance in another AZ



### Question 16
A global company needs to ensure users are routed to the nearest AWS Region to minimize latency. Which service provides this capability?
- A. Amazon CloudFront
- B. Amazon Route 53 with geolocation routing
- C. AWS Global Accelerator
- D. Elastic Load Balancing

**Answer: C** - AWS Global Accelerator uses the AWS global network to route users to the optimal endpoint based on geography, health, and routing policies



### Question 17
A startup needs to send transactional emails (order confirmations, password resets) to customers. Which AWS service is designed for this purpose?
- A. Amazon SNS
- B. Amazon SES (Simple Email Service)
- C. Amazon SQS
- D. AWS Lambda with third-party email API

**Answer: B** - Amazon SES is specifically designed for sending transactional and marketing emails



### Question 18
A company wants to analyze their AWS spending and identify opportunities for cost optimization. They need recommendations on right-sizing resources. Which tool should they use?
- A. AWS Cost Explorer
- B. AWS Budgets
- C. AWS Trusted Advisor
- D. AWS Compute Optimizer

**Answer: D** - AWS Compute Optimizer analyzes resource utilization and provides right-sizing recommendations; Trusted Advisor (C) also provides some cost optimization but Compute Optimizer is more specific to right-sizing



### Question 19
An application requires a message queue that guarantees each message is processed exactly once and in the order sent. Which service meets these requirements?
- A. Amazon SQS Standard Queue
- B. Amazon SQS FIFO Queue
- C. Amazon SNS
- D. Amazon Kinesis Data Streams

**Answer: B** - SQS FIFO queues provide exactly-once processing and maintain message order



### Question 20
A company needs to run Docker containers without managing the underlying infrastructure. Which service should they use?
- A. Amazon ECS on EC2
- B. Amazon EKS
- C. AWS Fargate
- D. AWS Lambda

**Answer: C** - AWS Fargate is serverless compute for containers, eliminating infrastructure management



### Question 21
A development team wants to deploy code automatically to EC2 instances whenever changes are pushed to their Git repository. Which service combination enables this? (Choose TWO)
- A. AWS CodeCommit
- B. AWS CodeDeploy
- C. AWS CodeBuild
- D. Amazon S3
- E. AWS CodePipeline

**Answer: B, E** - CodePipeline orchestrates the CI/CD workflow, and CodeDeploy automates deployment to EC2 instances



### Question 22
A company needs to implement a web application firewall to protect against SQL injection and cross-site scripting attacks. Which service should they use?
- A. AWS Shield
- B. AWS WAF
- C. Amazon GuardDuty
- D. Network ACLs

**Answer: B** - AWS WAF protects web applications from common web exploits like SQL injection and XSS



### Question 23
An organization wants to grant third-party auditors temporary access to specific S3 buckets for compliance review. What is the MOST secure approach?
- A. Create an IAM user with permanent credentials
- B. Share the root account credentials
- C. Create an IAM role with time-limited session tokens
- D. Make the S3 bucket public temporarily

**Answer: C** - IAM roles with temporary credentials provide time-limited, secure access without permanent credentials



### Question 24
A company stores sensitive data in DynamoDB and needs to ensure data is encrypted at rest with keys they control and can rotate. Which encryption option should they choose?
- A. DynamoDB default encryption
- B. AWS KMS customer managed keys (CMK)
- C. Client-side encryption before storing in DynamoDB
- D. No encryption needed as DynamoDB is secure

**Answer: B** - KMS customer managed keys give full control over key rotation and access policies



### Question 25
A machine learning team needs high-performance computing with GPU instances for training models. The training jobs take 8-12 hours and can tolerate interruptions. What is the MOST cost-effective option?
- A. On-Demand GPU instances
- B. Reserved GPU instances
- C. Spot GPU instances
- D. Dedicated GPU hosts

**Answer: C** - Spot instances offer up to 90% discount and are ideal for fault-tolerant workloads that can handle interruptions



### Question 26
A company wants to monitor all changes to their AWS resources and receive alerts when security group rules are modified. Which combination should they use? (Choose TWO)
- A. AWS Config
- B. Amazon CloudWatch Events
- C. AWS CloudTrail
- D. Amazon SNS
- E. AWS X-Ray

**Answer: A, D** - AWS Config monitors resource configurations and can trigger SNS notifications when changes occur



### Question 27
An application needs to store session state data that multiple EC2 instances can access with sub-millisecond latency. Which service is MOST appropriate?
- A. Amazon S3
- B. Amazon EFS
- C. Amazon ElastiCache
- D. Amazon RDS

**Answer: C** - ElastiCache provides in-memory caching with sub-millisecond latency, perfect for session data



### Question 28
A company is migrating to AWS and wants to understand which AWS services they are responsible for securing versus what AWS secures. What should they review?
- A. AWS Service Level Agreement (SLA)
- B. AWS Shared Responsibility Model
- C. AWS Acceptable Use Policy
- D. AWS Well-Architected Framework

**Answer: B** - The Shared Responsibility Model defines security responsibilities between AWS and the customer



### Question 29
A startup needs to deploy a MongoDB database on AWS without managing infrastructure. Which service should they use?
- A. Amazon RDS
- B. Amazon DocumentDB
- C. Amazon DynamoDB
- D. MongoDB on EC2 instances

**Answer: B** - Amazon DocumentDB is a fully managed MongoDB-compatible database service



### Question 30
A company wants to prevent accidental deletion of critical S3 objects. Which feature should they enable?
- A. S3 Versioning
- B. S3 Object Lock
- C. S3 Cross-Region Replication
- D. S3 Lifecycle policies

**Answer: B** - S3 Object Lock prevents object deletion for a specified retention period (though Versioning (A) also helps by retaining deleted versions)



### Question 31
An application generates 200 MB of log data per minute that needs to be analyzed in real-time for security threats. Which architecture is MOST suitable?
- A. Store logs in S3 and analyze with Athena hourly
- B. Stream logs to Kinesis Data Streams, process with Lambda, and alert via SNS
- C. Store logs in CloudWatch Logs and manually review daily
- D. Send logs to SQS and process with EC2 instances

**Answer: B** - Kinesis handles real-time streaming, Lambda processes data as it arrives, SNS sends immediate alerts



### Question 32
A company needs to deploy infrastructure across multiple AWS accounts with consistent configurations. What is the MOST efficient approach?
- A. Manually configure each account
- B. Use AWS CloudFormation StackSets
- C. Use AWS CLI scripts
- D. Use AWS Management Console templates

**Answer: B** - CloudFormation StackSets deploy stacks across multiple accounts and regions from a single operation



### Question 33
An organization wants to ensure all EC2 instances have approved software installed and no unauthorized software. Which service provides this capability?
- A. AWS Config
- B. Amazon Inspector
- C. AWS Systems Manager Inventory
- D. AWS CloudTrail

**Answer: C** - Systems Manager Inventory collects metadata about software and configurations on your instances



### Question 34
A web application experiences traffic primarily during business hours (9 AM - 5 PM) on weekdays. Which EC2 pricing strategy would be MOST cost-effective?
- A. On-Demand Instances only
- B. Reserved Instances with scheduled scaling
- C. Spot Instances only
- D. A mix of Reserved Instances for baseline and Auto Scaling with On-Demand for peak hours

**Answer: D** - Reserved Instances for predictable baseline load, Auto Scaling adds On-Demand capacity during business hours



### Question 35
A financial services company needs to ensure their AWS environment complies with PCI DSS requirements. Where can they find AWS compliance documentation?
- A. AWS Trusted Advisor
- B. AWS Artifact
- C. AWS Security Hub
- D. AWS Config

**Answer: B** - AWS Artifact provides access to compliance reports and agreements including PCI DSS



### Question 36
A company wants to run automated security assessments of EC2 instances to identify vulnerabilities. Which service should they use?
- A. AWS Config
- B. Amazon Inspector
- C. AWS Shield
- D. Amazon GuardDuty

**Answer: B** - Amazon Inspector performs automated security assessments and identifies vulnerabilities in EC2 instances



### Question 37
An application needs to process messages from a queue, but if processing fails, the message should be retried after a delay. Which service feature supports this?
- A. Amazon SQS with visibility timeout
- B. Amazon SQS with dead-letter queue
- C. Amazon SNS with retry policy
- D. Amazon Kinesis with checkpointing

**Answer: B** - Dead-letter queues capture messages that fail processing after maximum retries for later analysis



### Question 38
A company wants to provide their developers with temporary AWS console access using their existing corporate credentials. Which service enables this?
- A. AWS IAM users
- B. AWS IAM roles with SAML federation
- C. AWS Organizations
- D. AWS Directory Service

**Answer: B** - IAM roles with SAML federation allow single sign-on using corporate identity providers



### Question 39
A data analytics team needs to query large datasets stored in S3 using SQL without moving the data. Which service should they use?
- A. Amazon Redshift
- B. Amazon RDS
- C. Amazon Athena
- D. AWS Glue

**Answer: C** - Amazon Athena allows SQL queries directly on S3 data without data movement or infrastructure



### Question 40
A company needs to establish a dedicated, private network connection from their on-premises data center to AWS with consistent bandwidth. Which service should they use?
- A. AWS VPN
- B. AWS Direct Connect
- C. Amazon CloudFront
- D. AWS Transit Gateway

**Answer: B** - AWS Direct Connect provides dedicated, private connectivity with consistent network performance



### Question 41
An application requires a database that can scale horizontally to handle millions of requests per second with single-digit millisecond latency. Which database service is MOST appropriate?
- A. Amazon RDS
- B. Amazon Aurora
- C. Amazon DynamoDB
- D. Amazon Redshift

**Answer: C** - DynamoDB is designed for massive scale with predictable, single-digit millisecond latency



### Question 42
A company wants to cache frequently accessed data from their database to reduce database load and improve response times. Which service should they use?
- A. Amazon CloudFront
- B. Amazon ElastiCache
- C. AWS Global Accelerator
- D. Amazon S3

**Answer: B** - ElastiCache provides in-memory caching for databases to improve application performance



### Question 43
A startup is building a mobile app and needs to handle user authentication, including social sign-in (Google, Facebook). Which service provides this functionality?
- A. AWS IAM
- B. Amazon Cognito
- C. AWS Directory Service
- D. AWS Single Sign-On

**Answer: B** - Amazon Cognito provides user authentication and authorization for mobile and web apps, including social identity providers



### Question 44
A company needs to transfer 500 GB of data to AWS weekly for backup purposes. Which service would be MOST cost-effective and appropriate?
- A. AWS Snowball
- B. AWS DataSync
- C. AWS Transfer Family
- D. Manual S3 uploads

**Answer: B** - AWS DataSync is optimized for regular, automated data transfers to AWS over the network



### Question 45
An organization wants to receive notifications when their monthly AWS bill exceeds $1,000. How can they configure this?
- A. Use AWS Cost Explorer reports
- B. Configure AWS Budgets with an alert threshold
- C. Enable CloudWatch billing alarms
- D. Both B and C are correct

**Answer: D** - Both AWS Budgets and CloudWatch billing alarms can send notifications when spending thresholds are exceeded



### Question 46
A company needs to analyze petabytes of data using Apache Spark. They want a managed service without managing clusters. Which service should they use?
- A. Amazon EC2 with Apache Spark installed
- B. Amazon EMR
- C. AWS Glue
- D. Amazon Athena

**Answer: B** - Amazon EMR is a managed big data platform that supports Apache Spark without infrastructure management



### Question 47
A web application needs to serve content to users globally with the lowest possible latency. Static assets include images, videos, and JavaScript files. Which service is MOST appropriate?
- A. Amazon S3 with Transfer Acceleration
- B. Amazon CloudFront
- C. AWS Global Accelerator
- D. Amazon Route 53

**Answer: B** - CloudFront is a CDN that caches content at edge locations worldwide for low-latency delivery



### Question 48
A company wants to ensure all S3 buckets in their organization are never publicly accessible. What is the MOST effective way to enforce this?
- A. Create an IAM policy for all users
- B. Use AWS Config rules to detect public buckets
- C. Enable S3 Block Public Access at the organization level in AWS Organizations
- D. Manually audit buckets monthly

**Answer: C** - S3 Block Public Access at the organization level prevents public access across all accounts



### Question 49
An application running on EC2 needs to access AWS services (like S3) securely without embedding credentials in the code. What is the BEST practice?
- A. Store credentials in the application code
- B. Store credentials in environment variables
- C. Attach an IAM role to the EC2 instance
- D. Use AWS Secrets Manager to store credentials

**Answer: C** - IAM roles provide temporary credentials to EC2 instances without embedding long-term credentials



### Question 50
A company needs to run a scheduled batch job every night at 2 AM that takes approximately 2 hours. What is the MOST cost-effective compute option?
- A. Run EC2 On-Demand instances continuously
- B. Use AWS Lambda functions
- C. Use EC2 instances with scheduled Auto Scaling
- D. Use Reserved Instances

**Answer: C** - Scheduled Auto Scaling starts instances before the job and terminates them after, paying only for used hours



### Question 51
A development team needs to test different versions of their application simultaneously to compare performance. Which AWS service helps with this?
- A. AWS CodeDeploy
- B. AWS CloudFormation
- C. AWS Elastic Beanstalk
- D. AWS CodeBuild

**Answer: C** - Elastic Beanstalk supports multiple environment deployments and makes it easy to run different versions



### Question 52
A company stores customer data that must be retained for 10 years for compliance. The data is rarely accessed but must be available within 12 hours when needed. Which S3 storage class is MOST cost-effective?
- A. S3 Standard
- B. S3 Standard-IA
- C. S3 Glacier Flexible Retrieval
- D. S3 Glacier Deep Archive

**Answer: C** - S3 Glacier Flexible Retrieval (formerly Glacier) offers retrieval within hours and is cost-effective for long-term archival



### Question 53
An application needs to send messages to multiple subscribers, where each subscriber receives all messages. Which service should they use?
- A. Amazon SQS
- B. Amazon SNS
- C. Amazon Kinesis
- D. AWS Step Functions

**Answer: B** - Amazon SNS supports pub/sub messaging where multiple subscribers receive each message



### Question 54
A company wants to monitor unusual API activity in their AWS account that might indicate a security threat. Which service automatically detects this?
- A. AWS CloudTrail
- B. Amazon CloudWatch
- C. Amazon GuardDuty
- D. AWS Config

**Answer: C** - GuardDuty uses machine learning to detect unusual activity and potential security threats



### Question 55
An organization needs to create isolated network environments for development, testing, and production within the same AWS account. What should they use?
- A. Multiple AWS accounts
- B. Multiple VPCs
- C. Multiple subnets in one VPC
- D. Multiple security groups

**Answer: B** - Multiple VPCs provide network isolation within a single account



### Question 56
A company needs to ensure their EC2 instances are launched only in specific AWS Regions. How can they enforce this across their organization?
- A. Use IAM policies
- B. Use Service Control Policies (SCPs) in AWS Organizations
- C. Use AWS Config rules
- D. Manually monitor each account

**Answer: B** - SCPs in AWS Organizations can restrict which regions can be used across all accounts



### Question 57
An application stores user-uploaded images that need to be resized automatically when uploaded. Which serverless approach is MOST suitable?
- A. Upload to S3, trigger Lambda function via S3 event notification to resize images
- B. Upload to EC2, use scheduled cron jobs to resize
- C. Upload to EBS, use Auto Scaling to resize
- D. Upload to CloudFront, use Lambda@Edge to resize

**Answer: A** - S3 event notifications trigger Lambda functions automatically when objects are uploaded, enabling serverless image processing



### Question 58
A company wants to implement infrastructure as code to manage their AWS resources. Which service is specifically designed for this?
- A. AWS OpsWorks
- B. AWS CloudFormation
- C. AWS Systems Manager
- D. AWS Elastic Beanstalk

**Answer: B** - CloudFormation uses templates to provision and manage AWS infrastructure as code



### Question 59
A media company needs to transcode video files uploaded by users into multiple formats. Which AWS service is purpose-built for this?
- A. AWS Lambda
- B. Amazon Elastic Transcoder
- C. AWS Elemental MediaConvert
- D. AWS Batch

**Answer: C** - AWS Elemental MediaConvert is a file-based video transcoding service (MediaConvert is newer and more feature-rich than Elastic Transcoder)



### Question 60
A company needs to analyze streaming data from IoT devices and trigger alerts when certain conditions are met. Which service combination is MOST appropriate? (Choose TWO)
- A. Amazon Kinesis Data Streams
- B. Amazon SQS
- C. AWS IoT Core
- D. Amazon RDS
- E. AWS Lambda

**Answer: A, E** - Kinesis Data Streams ingests IoT data in real-time, Lambda processes data and triggers alerts



### Question 61
An application requires consistent, single-digit millisecond latency for read operations from a relational database. Which solution meets this requirement?
- A. Amazon RDS with Multi-AZ
- B. Amazon RDS with Read Replicas
- C. Amazon RDS with ElastiCache in front
- D. Amazon Aurora Serverless

**Answer: C** - ElastiCache provides in-memory caching for sub-millisecond read latency



### Question 62
A company wants to grant permissions to AWS services (like EC2) to access other AWS services (like S3) on their behalf. What should they create?
- A. IAM users
- B. IAM groups
- C. IAM roles
- D. IAM policies only

**Answer: C** - IAM roles are designed for AWS services to access other AWS services



### Question 63
A development team uses AWS CodeCommit for version control. They want to automatically build and test code on every commit. Which service should they use?
- A. AWS CodeDeploy
- B. AWS CodeBuild
- C. AWS CodePipeline
- D. AWS CloudFormation

**Answer: B** - AWS CodeBuild compiles source code, runs tests, and produces deployable artifacts



### Question 64
A company needs to provide secure, temporary access to S3 objects for their web application users. What is the BEST approach?
- A. Make S3 bucket public
- B. Generate pre-signed URLs with expiration
- C. Share IAM credentials
- D. Create an IAM user for each application user

**Answer: B** - Pre-signed URLs provide temporary, secure access to specific S3 objects without making buckets public



### Question 65
An organization wants to automatically remediate non-compliant resources (like unencrypted EBS volumes). Which combination of services enables this? (Choose TWO)
- A. AWS Config with remediation actions
- B. AWS CloudTrail
- C. AWS Systems Manager Automation
- D. Amazon CloudWatch Logs
- E. AWS Lambda

**Answer: A, C** - AWS Config detects non-compliant resources and can trigger Systems Manager Automation documents to remediate automatically



## Answer Summary

**Questions 1-65 Answer Key:**
1. A,C  2. B  3. C  4. B  5. C  6. C  7. B  8. C  9. B  10. A,C  
11. C  12. A  13. B  14. C  15. B  16. C  17. B  18. D  19. B  20. C  
21. B,E  22. B  23. C  24. B  25. C  26. A,D  27. C  28. B  29. B  30. B  
31. B  32. B  33. C  34. D  35. B  36. B  37. B  38. B  39. C  40. B  
41. C  42. B  43. B  44. B  45. D  46. B  47. B  48. C  49. C  50. C  
51. C  52. C  53. B  54. C  55. B  56. B  57. A  58. B  59. C  60. A,E  
61. C  62. C  63. B  64. B  65. A,C

## Exam Tips

**Key Areas to Focus:**
- AWS Shared Responsibility Model
- Core services: EC2, S3, RDS, VPC, IAM
- Security best practices and services
- Cost optimization strategies
- High availability and disaster recovery
- AWS Global Infrastructure (Regions, AZs, Edge Locations)
- Billing and pricing models

**During the Exam:**
- Read questions carefully, especially "MOST" and "LEAST" qualifiers
- Eliminate obviously wrong answers first
- For "Choose TWO/THREE" questions, all selections must be correct
- Watch for scenario-based questions requiring multiple AWS services
- Time management: Don't spend too long on any single question
