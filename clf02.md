# Architecture Practice Questions


---

## Module 1: AWS Architecture (20 Questions)

### Question 1
A company needs to design a three-tier web application architecture that is highly available and can handle variable traffic loads. The application consists of a web tier, application tier, and database tier. Which architecture design best meets these requirements?

**Options:**

A. Deploy all tiers in a single Availability Zone with Auto Scaling enabled.

B. Deploy the web tier in public subnets across multiple Availability Zones with an ALB, application tier in private subnets with Auto Scaling, and use Amazon RDS Multi-AZ for the database.

C. Deploy all tiers in public subnets with Network Load Balancers.

D. Use AWS Lambda for all tiers and Amazon DynamoDB for the database.

**Answer:** B. Deploy the web tier in public subnets across multiple Availability Zones with an ALB, application tier in private subnets with Auto Scaling, and use Amazon RDS Multi-AZ for the database.

**Explanation:** This architecture follows AWS best practices by separating tiers, using multiple Availability Zones for high availability, placing the application tier in private subnets for security, and using Multi-AZ RDS for database redundancy.

---

### Question 2
An organization wants to implement a hybrid cloud architecture that connects their on-premises data center to AWS. They require consistent network performance with low latency. Which combination of services should be used?

**Options:**

A. AWS VPN and VPC Peering

B. AWS Direct Connect and Virtual Private Gateway

C. AWS Transit Gateway and internet gateway

D. AWS Site-to-Site VPN and NAT Gateway

**Answer:** B. AWS Direct Connect and Virtual Private Gateway

**Explanation:** Direct Connect provides a dedicated private connection between on-premises and AWS, offering consistent network performance and low latency compared to internet-based VPN connections.

---

### Question 3
A solutions architect needs to design a VPC architecture for a new application. The application requires public-facing web servers, private application servers, and highly secure database servers. How should the VPC be designed?

**Options:**

A. Create one public subnet for all resources and use security groups for isolation.

B. Create public subnets for web servers, private subnets for application servers, and isolated subnets (no route to NAT) for database servers across multiple Availability Zones.

C. Create separate VPCs for each tier and connect them using VPC Peering.

D. Place all resources in private subnets and use a bastion host for access.


**Answer:** B. Create public subnets for web servers, private subnets for application servers, and isolated subnets (no route to NAT) for database servers across multiple Availability Zones.

**Explanation:** This design implements defense in depth by placing resources in appropriate subnet tiers based on their internet access requirements, with databases in the most restricted isolated subnets.

---

### Question 4
A company needs to architect a solution that provides low-latency access to static content for users distributed globally. The content is stored in an S3 bucket in the us-east-1 region. What architecture should be implemented?

**Options:**

A. Enable S3 Transfer Acceleration

B. Create S3 buckets in multiple regions and manually replicate content

C. Implement Amazon CloudFront with the S3 bucket as the origin

D. Use AWS Global Accelerator with S3


**Answer:** C. Implement Amazon CloudFront with the S3 bucket as the origin

**Explanation:** CloudFront is a CDN that caches content at edge locations worldwide, providing low-latency access to static content for global users without requiring multiple S3 buckets.

---

### Question 5
An application requires a shared file system that can be accessed concurrently by multiple EC2 instances across different Availability Zones. Which storage solution meets this requirement?

**Options:**

A. Amazon EBS with Multi-Attach enabled

B. Amazon EFS (Elastic File System)

C. Amazon S3 with versioning

D. Instance store volumes


**Answer:** B. Amazon EFS (Elastic File System)

**Explanation:** EFS provides a managed NFS file system that can be mounted by multiple EC2 instances simultaneously across multiple Availability Zones, making it ideal for shared storage requirements.

---

### Question 6
A solutions architect is designing an architecture for a video processing application. Videos are uploaded to S3, processed by EC2 instances, and the output is stored back in S3. The processing jobs are unpredictable and sporadic. What is the most cost-effective compute solution?

**Options:**

A. EC2 On-Demand instances with Auto Scaling

B. EC2 Reserved Instances

C. EC2 Spot Instances with Spot Fleet

D. AWS Lambda with ECS


**Answer:** C. EC2 Spot Instances with Spot Fleet

**Explanation:** Spot Instances offer significant cost savings (up to 90%) for fault-tolerant, flexible workloads like video processing that can handle interruptions, making them ideal for sporadic workloads.

---

### Question 7
A company wants to implement a microservices architecture using containers. They need a fully managed service that handles container orchestration, scaling, and patching. Which service combination should be used?

**Options:**

A. Amazon ECS with EC2 launch type

B. Amazon EKS with self-managed worker nodes

C. Amazon ECS with Fargate launch type

D. EC2 instances with Docker installed


**Answer:** C. Amazon ECS with Fargate launch type

**Explanation:** ECS with Fargate provides serverless container orchestration without managing the underlying infrastructure, handling scaling, patching, and orchestration automatically.

---

### Question 8
An application needs to store user session data that requires sub-millisecond latency and automatic expiration of old sessions. Which database service is most appropriate?

**Options:**

A. Amazon RDS for MySQL

B. Amazon DynamoDB with TTL enabled

C. Amazon ElastiCache for Redis

D. Amazon Aurora


**Answer:** C. Amazon ElastiCache for Redis

**Explanation:** ElastiCache for Redis provides in-memory caching with sub-millisecond latency and native support for session storage with TTL (time-to-live) capabilities for automatic expiration.

---

### Question 9
A solutions architect needs to design a network architecture that allows multiple VPCs across different AWS accounts and regions to communicate with each other. What is the most scalable solution?

**Options:**

A. VPC Peering between all VPCs

B. AWS Transit Gateway with Resource Access Manager

C. AWS Direct Connect Gateway

D. Multiple Site-to-Site VPN connections


**Answer:** B. AWS Transit Gateway with Resource Access Manager

**Explanation:** Transit Gateway acts as a central hub for connecting multiple VPCs across accounts and regions, eliminating the need for complex peering relationships and providing better scalability.

---

### Question 10
A company requires a solution to route traffic between different versions of their application based on weights (90% to version 1, 10% to version 2) for canary deployments. Which service provides this capability?

**Options:**

A. Application Load Balancer with weighted target groups

B. Network Load Balancer with cross-zone load balancing

C. Amazon Route 53 with weighted routing policy

D. AWS Global Accelerator with traffic dials


**Answer:** A. Application Load Balancer with weighted target groups

**Explanation:** ALB supports weighted target groups, allowing traffic distribution based on specified weights, which is ideal for canary deployments and blue/green testing.

---

### Question 11
An organization needs to design a disaster recovery architecture with an RTO of 1 hour and RPO of 15 minutes for a critical database application. Which DR strategy is most appropriate?

**Options:**

A. Backup and Restore

B. Pilot Light

C. Warm Standby

D. Multi-Site Active-Active


**Answer:** C. Warm Standby

**Explanation:** Warm Standby maintains a scaled-down version of a fully functional environment in another region, which can be scaled up quickly to meet the 1-hour RTO while maintaining recent backups for the 15-minute RPO.

---

### Question 12
A solutions architect is designing a serverless architecture for a data processing pipeline. Files uploaded to S3 need to trigger processing, which writes results to DynamoDB. What is the most appropriate architecture?

**Options:**

A. S3 → SNS → Lambda → DynamoDB

B. S3 Event Notification → Lambda → DynamoDB

C. S3 → SQS → EC2 → DynamoDB

D. S3 → EventBridge → Step Functions → Lambda → DynamoDB


**Answer:** B. S3 Event Notification → Lambda → DynamoDB

**Explanation:** S3 Event Notifications directly triggering Lambda provides the simplest serverless architecture for this use case, with Lambda processing files and writing to DynamoDB.

---

### Question 13
A company needs to implement a bastion host architecture for secure SSH access to EC2 instances in private subnets. What is the most secure design?

**Options:**

A. Place bastion hosts in public subnets with unrestricted security group rules

B. Place bastion hosts in public subnets with security groups restricting SSH to specific IP ranges, and enable Systems Manager Session Manager

C. Allow direct SSH access to private instances through NAT Gateway

D. Use VPN with no bastion host


**Answer:** B. Place bastion hosts in public subnets with security groups restricting SSH to specific IP ranges, and enable Systems Manager Session Manager

**Explanation:** This approach combines traditional bastion architecture with IP restrictions and AWS Systems Manager Session Manager for enhanced security and audit capabilities.

---

### Question 14
An application requires a message queue that guarantees message ordering and exactly-once processing for financial transactions. Which service should be used?

**Options:**

A. Amazon SQS Standard Queue

B. Amazon SQS FIFO Queue

C. Amazon SNS

D. Amazon Kinesis Data Streams


**Answer:** B. Amazon SQS FIFO Queue

**Explanation:** SQS FIFO queues guarantee message ordering and exactly-once processing through deduplication, making them suitable for financial transactions requiring strict ordering.

---

### Question 15
A solutions architect needs to design an architecture for a content management system that serves both static and dynamic content. Static content should be cached globally, while dynamic content requires real-time processing. What architecture should be implemented?

**Options:**

A. CloudFront with S3 for all content

B. CloudFront with S3 for static content and ALB for dynamic content as custom origin

C. S3 with Transfer Acceleration for both content types

D. Multiple S3 buckets across regions with cross-region replication


**Answer:** B. CloudFront with S3 for static content and ALB for dynamic content as custom origin

**Explanation:** CloudFront can cache static content from S3 while routing dynamic requests to ALB as a custom origin, providing optimal performance for both content types.

---

### Question 16
A company is designing a big data analytics architecture that needs to process streaming data in real-time and store it for long-term analysis. Which combination of services is most appropriate?

**Options:**

A. Amazon Kinesis Data Streams → Lambda → S3 → Athena

B. Amazon SQS → EC2 → RDS → QuickSight

C. AWS IoT Core → DynamoDB → Redshift

D. Amazon MSK → EMR → Glacier


**Answer:** A. Amazon Kinesis Data Streams → Lambda → S3 → Athena

**Explanation:** Kinesis Data Streams ingests real-time data, Lambda processes it, S3 stores it cost-effectively, and Athena enables serverless querying for analysis.

---

### Question 17
A company completed a lift-and-shift migration to AWS but now wants to optimize costs and modernize. What post-migration optimization strategy should they follow?

**Options:**

A. Keep everything as migrated

B. Right-size instances using AWS Compute Optimizer, implement Reserved Instances/Savings Plans, containerize suitable applications, adopt managed services for databases

C. Migrate back on-premises

D. Increase all instance sizes


**Answer:** B. Right-size instances using AWS Compute Optimizer, implement Reserved Instances/Savings Plans, containerize suitable applications, adopt managed services for databases

**Explanation:** Post-migration optimization involves right-sizing based on actual usage, leveraging pricing models for predictable workloads, modernizing through containerization, and using managed services to reduce operational overhead.

---



### Question 18
A solutions architect needs to design a network architecture that allows EC2 instances in private subnets to access AWS services (like S3 and DynamoDB) without traversing the internet. What should be implemented?

**Options:**

A. NAT Gateway with S3 and DynamoDB access policies

B. VPC Endpoints (Gateway Endpoints for S3 and DynamoDB)

C. Internet Gateway with security group rules

D. AWS Direct Connect


**Answer:** B. VPC Endpoints (Gateway Endpoints for S3 and DynamoDB)

**Explanation:** VPC Gateway Endpoints for S3 and DynamoDB allow private access to these services without internet traversal, improving security and reducing data transfer costs.

---

### Question 19
A company needs to design an architecture for a mobile application backend that handles millions of concurrent users with unpredictable traffic patterns. Which architecture is most suitable?

**Options:**

A. EC2 Auto Scaling with RDS

B. API Gateway + Lambda + DynamoDB

C. ECS with Application Load Balancer and Aurora

D. Elastic Beanstalk with RDS Multi-AZ


**Answer:** B. API Gateway + Lambda + DynamoDB

**Explanation:** This serverless architecture automatically scales to handle millions of concurrent requests without capacity planning, with DynamoDB providing seamless scalability for the database tier.

---

### Question 20
An organization wants to implement a hub-and-spoke network architecture where multiple VPCs need to access shared services hosted in a central VPC. What is the most efficient design?

**Options:**

A. Full mesh VPC Peering between all VPCs

B. AWS Transit Gateway with separate route tables for different VPC groups

C. AWS Direct Connect to each VPC

D. Site-to-Site VPN connections between all VPCs


**Answer:** B. AWS Transit Gateway with separate route tables for different VPC groups

**Explanation:** Transit Gateway simplifies hub-and-spoke architectures by providing a central routing point, with separate route tables enabling fine-grained control over which VPCs can communicate.

---

## Module 2: API & Deployment Strategies (18 Questions)

### Question 1
A company is deploying a REST API using Amazon API Gateway. They need to implement request throttling to prevent abuse while allowing burst traffic. Which API Gateway feature should be configured?

**Options:**

A. Resource policies

B. Usage plans with API keys and throttle settings

C. AWS WAF integration

D. Lambda authorizers


**Answer:** B. Usage plans with API keys and throttle settings

**Explanation:** API Gateway usage plans allow you to define throttle limits (rate and burst) per API key, providing fine-grained control over API consumption while handling burst traffic.

---

### Question 2
A solutions architect needs to implement blue/green deployment for a web application running on EC2 instances behind an Application Load Balancer. What is the most efficient approach?

**Options:**

A. Create two separate Auto Scaling groups, shift traffic using weighted target groups on the ALB

B. Use Route 53 weighted routing between two separate environments

C. Deploy both versions on the same instances using different ports

D. Manually swap Elastic IP addresses between environments


**Answer:** A. Create two separate Auto Scaling groups, shift traffic using weighted target groups on the ALB

**Explanation:** ALB weighted target groups allow gradual traffic shifting between blue and green environments, providing quick rollback capability and minimizing risk during deployment.

---

### Question 3
An organization wants to implement canary deployments for their Lambda-based API. What is the best approach using AWS services?

**Options:**

A. API Gateway with multiple Lambda versions and stage variables

B. Lambda aliases with weighted traffic shifting

C. Deploy to multiple regions and use Route 53 failover

D. Use AWS CodeDeploy with Lambda traffic shifting configuration


**Answer:** D. Use AWS CodeDeploy with Lambda traffic shifting configuration

**Explanation:** AWS CodeDeploy provides native support for Lambda canary deployments with automated traffic shifting, rollback on CloudWatch alarms, and deployment hooks.

---

### Question 4
A company needs to deploy a REST API that requires custom authentication logic based on JWT tokens stored in a third-party identity provider. Which API Gateway authorization method should be used?

**Options:**

A. IAM authorization

B. Amazon Cognito User Pools

C. Lambda authorizer (custom authorizer)

D. API keys


**Answer:** C. Lambda authorizer (custom authorizer)

**Explanation:** Lambda authorizers allow custom authentication logic, enabling validation of JWT tokens from any identity provider and implementing complex authorization policies.

---

### Question 5
A solutions architect is designing a deployment strategy for a containerized application using ECS. The deployment must ensure zero downtime and automatic rollback on failure. Which deployment type should be configured?

**Options:**

A. Rolling update deployment

B. Blue/green deployment with CodeDeploy

C. Recreate deployment

D. All-at-once deployment


**Answer:** B. Blue/green deployment with CodeDeploy

**Explanation:** Blue/green deployment with CodeDeploy provides zero-downtime deployments, automatic rollback based on CloudWatch alarms, and quick recovery to the previous version if needed.

---

### Question 6
An API Gateway REST API needs to integrate with multiple backend services (Lambda, HTTP endpoints, and AWS services). The architect wants to minimize latency. Which integration type should be prioritized?

**Options:**

A. Lambda proxy integration for all endpoints

B. AWS service integration with mapping templates for AWS services, Lambda proxy for functions

C. HTTP proxy integration for all backends

D. Mock integrations with request/response transformation


**Answer:** B. AWS service integration with mapping templates for AWS services, Lambda proxy for functions

**Explanation:** AWS service integrations enable direct service invocation without Lambda intermediaries, reducing latency, while Lambda proxy integration provides flexibility for custom business logic.

---

### Question 7
A company wants to implement A/B testing for their web application by routing 20% of traffic to a new version. The application runs on EC2 instances behind an ALB. What is the most appropriate solution?

**Options:**

A. Use Route 53 weighted routing policy

B. Configure ALB listener rules with weighted target groups

C. Deploy both versions and manually adjust Auto Scaling

D. Use CloudFront with Lambda@Edge for routing decisions


**Answer:** B. Configure ALB listener rules with weighted target groups

**Explanation:** ALB weighted target groups enable precise traffic distribution percentages between versions, making A/B testing straightforward without DNS propagation delays.

---

### Question 8
A solutions architect needs to implement API versioning strategy for a public REST API that will have multiple versions running simultaneously. What is the best practice approach?

**Options:**

A. Use different domain names for each version

B. Use API Gateway stages with stage variables to route to different backend versions

C. Include version in URL path (/v1/, /v2/) with separate integrations

D. Use HTTP headers for version specification


**Answer:** C. Include version in URL path (/v1/, /v2/) with separate integrations

**Explanation:** URL path versioning is explicit, discoverable, and cache-friendly, allowing different versions to coexist with clear separation and independent lifecycle management.

---

### Question 9
An organization is deploying a microservices application using AWS Elastic Beanstalk. They need to deploy multiple services independently with different scaling policies. What is the recommended approach?

**Options:**

A. Deploy all microservices in a single Elastic Beanstalk environment

B. Create separate Elastic Beanstalk environments for each microservice

C. Use a single EC2 instance with all microservices

D. Deploy microservices using CloudFormation only


**Answer:** B. Create separate Elastic Beanstalk environments for each microservice

**Explanation:** Separate Elastic Beanstalk environments for each microservice enable independent deployment, scaling, and management, following microservices best practices.

---

### Question 10
A company needs to implement request/response transformation in API Gateway to convert XML requests to JSON before sending to Lambda functions. What feature should be used?

**Options:**

A. Lambda proxy integration with custom transformation code

B. Mapping templates with VTL (Velocity Template Language)

C. AWS Lambda layers

D. API Gateway request validators


**Answer:** B. Mapping templates with VTL (Velocity Template Language)

**Explanation:** API Gateway mapping templates using VTL enable request/response transformation without additional Lambda code, reducing latency and cost.

---

### Question 11
A solutions architect is implementing a deployment pipeline using AWS CodePipeline for a three-tier application. Manual approval is required before production deployment. How should this be configured?

**Options:**

A. Add a manual approval action in CodePipeline before the production deployment stage

B. Use SNS notifications and manually trigger the pipeline

C. Configure CloudWatch Events with Lambda for approval

D. Use AWS Step Functions for approval workflow


**Answer:** A. Add a manual approval action in CodePipeline before the production deployment stage

**Explanation:** CodePipeline manual approval actions provide native integration for human approval gates with SNS notifications and IAM-based approval permissions.

---

### Question 12
An API Gateway API experiences high latency during peak traffic. The backend Lambda functions execute quickly. What is the most likely cause and solution?

**Options:**

A. Lambda cold starts - increase provisioned concurrency

B. API Gateway throttling - increase account-level throttle limits

C. Insufficient Lambda memory - increase memory allocation

D. API Gateway integration timeout - increase timeout value


**Answer:** B. API Gateway throttling - increase account-level throttle limits

**Explanation:** If Lambda executes quickly but API latency is high during peaks, API Gateway throttling is likely the bottleneck. Account-level throttle limits may need adjustment.

---

### Question 13
A company wants to implement progressive delivery for their ECS Fargate application, starting with 10% of traffic, then 50%, then 100% over 30 minutes with automatic rollback if errors increase. Which service combination achieves this?

**Options:**

A. AWS App Mesh with Envoy proxy

B. AWS CodeDeploy with ECS blue/green deployment and CloudWatch alarms

C. Application Load Balancer weighted target groups with manual adjustment

D. Route 53 health checks with failover routing


**Answer:** B. AWS CodeDeploy with ECS blue/green deployment and CloudWatch alarms

**Explanation:** CodeDeploy supports linear and canary traffic shifting configurations for ECS with automated rollback based on CloudWatch alarms, perfect for progressive delivery.

---

### Question 14
A solutions architect needs to implement caching for an API Gateway REST API to reduce backend load. Different endpoints have different cache requirements (1 minute to 1 hour). How should caching be configured?

**Options:**

A. Enable caching at stage level with TTL override per method

B. Use CloudFront in front of API Gateway

C. Implement caching in Lambda functions

D. Use ElastiCache with API Gateway integration


**Answer:** A. Enable caching at stage level with TTL override per method

**Explanation:** API Gateway allows stage-level cache enablement with per-method TTL overrides, providing flexible caching configuration for different endpoints.

---

### Question 15
An organization is deploying infrastructure using AWS CloudFormation. They need to deploy the same stack across multiple regions with region-specific parameters. What is the best approach?

**Options:**

A. Create separate templates for each region

B. Use CloudFormation StackSets with parameter overrides

C. Manually deploy to each region using CLI

D. Use AWS CDK with custom regions loop


**Answer:** B. Use CloudFormation StackSets with parameter overrides

**Explanation:** CloudFormation StackSets enable deploying a single template across multiple regions and accounts with parameter overrides for region-specific configurations.

---

### Question 16
A company needs to implement request validation for their API Gateway API to reject malformed requests before they reach backend services. What should be configured?

**Options:**

A. Lambda authorizers with validation logic

B. API Gateway request validators with JSON Schema models

C. AWS WAF with custom rules

D. Application Load Balancer with Lambda for validation


**Answer:** B. API Gateway request validators with JSON Schema models

**Explanation:** API Gateway request validators check request parameters and body against JSON Schema models, rejecting invalid requests at the gateway level without invoking backend services.

---

### Question 17
A solutions architect is implementing a deployment strategy for Lambda functions that requires testing in production with real traffic before full rollout. What deployment configuration should be used?

**Options:**

A. Lambda versions with manual alias updates

B. AWS CodeDeploy with Lambda linear traffic shifting (Linear10PercentEvery3Minutes)

C. API Gateway stages with stage variables

D. Multiple Lambda functions with API Gateway canary deployments


**Answer:** B. AWS CodeDeploy with Lambda linear traffic shifting (Linear10PercentEvery3Minutes)

**Explanation:** CodeDeploy linear traffic shifting gradually increases traffic to the new version while monitoring CloudWatch metrics, enabling safe production testing with automatic rollback.

---

### Question 18
An API Gateway REST API needs to throttle requests differently for premium and standard tier customers. How should this be implemented?

**Options:**

A. Create separate API stages for each tier

B. Use usage plans with different throttle limits for different API keys

C. Implement throttling logic in Lambda authorizers

D. Use AWS WAF rate-based rules


**Answer:** B. Use usage plans with different throttle limits for different API keys

**Explanation:** API Gateway usage plans allow assigning different API keys to different plans with specific throttle limits, enabling tier-based request throttling.

---

## Module 3: Optimizations & Recovery (20 Questions)

### Question 1
A company's RDS MySQL database is experiencing high read latency during peak hours. Write operations are minimal. What is the most cost-effective solution to improve read performance?

**Options:**

A. Upgrade to a larger RDS instance type

B. Create Read Replicas and distribute read traffic using application logic or Aurora with reader endpoints

C. Enable Multi-AZ deployment

D. Migrate to DynamoDB


**Answer:** B. Create Read Replicas and distribute read traffic using application logic or Aurora with reader endpoints

**Explanation:** Read Replicas offload read traffic from the primary instance, improving performance for read-heavy workloads at a lower cost than scaling the primary instance.

---

### Question 2
An organization needs to optimize S3 storage costs for log files. Files are accessed frequently for 30 days, occasionally for the next 60 days, and rarely thereafter, but must be retained for 7 years for compliance. What lifecycle policy should be implemented?

**Options:**

A. Transition to S3 IA after 30 days, then to S3 Glacier after 90 days

B. Transition to S3 Intelligent-Tiering immediately

C. Transition to S3 Standard-IA after 30 days, S3 Glacier Flexible Retrieval after 90 days, and S3 Glacier Deep Archive after 1 year

D. Keep in S3 Standard for the entire retention period


**Answer:** C. Transition to S3 Standard-IA after 30 days, S3 Glacier Flexible Retrieval after 90 days, and S3 Glacier Deep Archive after 1 year

**Explanation:** This lifecycle policy optimizes costs by moving data to appropriate storage classes based on access patterns, with Deep Archive providing the lowest cost for long-term retention.

---

### Question 3
A web application running on EC2 instances experiences CPU spikes during flash sales. The spikes are predictable (known sale times) but scaling takes too long, causing performance issues. What optimization should be implemented?

**Options:**

A. Use larger EC2 instances

B. Implement scheduled scaling with Auto Scaling scheduled actions

C. Use Spot Instances

D. Increase the Auto Scaling cooldown period


**Answer:** B. Implement scheduled scaling with Auto Scaling scheduled actions

**Explanation:** Scheduled scaling proactively adds capacity before known traffic spikes, eliminating the lag time of reactive scaling and ensuring resources are available when needed.

---

### Question 4
A company's disaster recovery plan requires an RTO of 4 hours and RPO of 1 hour for a critical application. The primary site is in us-east-1. What is the most cost-effective DR strategy?

**Options:**

A. Multi-Site Active-Active in us-west-2

B. Warm Standby in us-west-2 with automated backups every hour

C. Pilot Light in us-west-2 with hourly snapshots

D. Backup and Restore using S3 cross-region replication


**Answer:** C. Pilot Light in us-west-2 with hourly snapshots

**Explanation:** Pilot Light maintains minimal infrastructure (database and core components) with the ability to rapidly provision full infrastructure, meeting the 4-hour RTO while being more cost-effective than warm standby.

---

### Question 5
An application uses DynamoDB and experiences throttling during peak traffic despite having sufficient provisioned capacity. What is the likely cause and solution?

**Options:**

A. Overall table capacity is insufficient - increase provisioned capacity

B. Hot partition due to poor partition key design - redesign partition key or enable DynamoDB Adaptive Capacity

C. Global secondary index capacity is too low - increase GSI capacity

D. Network latency - use VPC endpoints


**Answer:** B. Hot partition due to poor partition key design - redesign partition key or enable DynamoDB Adaptive Capacity

**Explanation:** Throttling despite sufficient table-level capacity typically indicates a hot partition. DynamoDB Adaptive Capacity can help temporarily, but fixing partition key design provides a long-term solution.

---

### Question 6
A company wants to optimize costs for EC2 instances running batch processing jobs that can tolerate interruptions and run for 2-4 hours daily. What purchasing option should be used?

**Options:**

A. On-Demand Instances

B. Reserved Instances with 1-year term

C. Spot Instances with Spot Fleet

D. Dedicated Hosts


**Answer:** C. Spot Instances with Spot Fleet

**Explanation:** Spot Instances offer up to 90% cost savings for interruptible workloads like batch processing, with Spot Fleet maintaining capacity across multiple instance types and AZs.

---

### Question 7
An RDS database requires automated backups with point-in-time recovery capability, and backup retention must be extended to 90 days. The default RDS automated backup retention is 7 days. How can this requirement be met?

**Options:**

A. Increase automated backup retention period to 35 days (maximum), then use AWS Backup for longer retention

B. Use manual RDS snapshots

C. Export snapshots to S3 using Lambda

D. Use third-party backup tools


**Answer:** A. Increase automated backup retention period to 35 days (maximum), then use AWS Backup for longer retention

**Explanation:** RDS automated backups support up to 35 days retention. AWS Backup can manage longer retention periods and provides centralized backup management across AWS services.

---

### Question 8
A Lambda function processes S3 events but occasionally times out during processing of large files. The function is already set to maximum timeout (15 minutes). What optimization should be implemented?

**Options:**

A. Increase Lambda memory allocation

B. Redesign using Step Functions to orchestrate multiple Lambda invocations for parallel processing

C. Use EC2 instances instead

D. Increase Lambda timeout beyond 15 minutes


**Answer:** B. Redesign using Step Functions to orchestrate multiple Lambda invocations for parallel processing

**Explanation:** For processing that exceeds Lambda's 15-minute limit, Step Functions can orchestrate multiple Lambda invocations to process large files in parallel or sequentially.

---

### Question 9
An application serves images stored in S3 to global users. CloudFront is configured but cache hit ratio is low (30%). What optimization can improve cache effectiveness?

**Options:**

A. Increase CloudFront TTL values

B. Enable query string forwarding

C. Use S3 Transfer Acceleration

D. Add more edge locations


**Answer:** A. Increase CloudFront TTL values

**Explanation:** Low cache hit ratio often results from short TTLs causing frequent cache invalidation. Increasing TTL keeps content cached longer at edge locations, improving hit ratio.

---

### Question 10
A company needs to implement cross-region disaster recovery for an application using Aurora MySQL. The recovery time objective is 1 minute. What solution meets this requirement?

**Options:**

A. Aurora Multi-AZ within the same region

B. Aurora Global Database with managed failover

C. Scheduled Aurora snapshots to another region

D. Aurora Read Replicas in another region with manual promotion


**Answer:** B. Aurora Global Database with managed failover

**Explanation:** Aurora Global Database provides cross-region replication with typical lag under 1 second and managed failover capability, meeting the aggressive 1-minute RTO requirement.

---

### Question 11
An EC2 Auto Scaling group frequently scales up and down due to fluctuating load, causing instance churn and affecting application performance. What optimization should be implemented?

**Options:**

A. Increase minimum capacity

B. Implement target tracking scaling with appropriate target value and adjust cooldown periods

C. Disable scale-in operations

D. Use step scaling instead


**Answer:** B. Implement target tracking scaling with appropriate target value and adjust cooldown periods

**Explanation:** Target tracking with optimized cooldown periods and appropriate target values prevents rapid scaling oscillations, providing more stable scaling behavior.

---

### Question 12
A company's CloudFront distribution serves dynamic content from an ALB origin. Response times are slower than direct ALB access. What optimization should be implemented?

**Options:**

A. Enable CloudFront compression

B. Configure CloudFront to forward all headers and query strings to origin, and reduce TTL to 0 for dynamic content

C. Use Lambda@Edge for content generation

D. Add more origin servers


**Answer:** B. Configure CloudFront to forward all headers and query strings to origin, and reduce TTL to 0 for dynamic content

**Explanation:** For dynamic content, CloudFront should forward all necessary headers and query strings, with TTL set to 0 to prevent caching, while still benefiting from CloudFront's global network.

---

### Question 13
A DynamoDB table is experiencing high costs due to frequent reads. Analysis shows that 80% of reads are for the same items. What optimization should be implemented?

**Options:**

A. Increase DynamoDB provisioned read capacity

B. Implement DynamoDB Accelerator (DAX) for caching

C. Switch to on-demand capacity mode

D. Create a Global Secondary Index


**Answer:** B. Implement DynamoDB Accelerator (DAX) for caching

**Explanation:** DAX provides microsecond latency for repeated reads by caching frequently accessed items, reducing costs by decreasing read operations against the table.

---

### Question 14
An application's EBS volumes are experiencing I/O performance bottlenecks. CloudWatch metrics show high queue depth and wait time. What is the most effective optimization?

**Options:**

A. Increase EBS volume size 

B. Change to Provisioned IOPS (io2) volumes with higher IOPS allocation

C. Add more EBS volumes with striping

D. Migrate to instance store volumes


**Answer:** B. Change to Provisioned IOPS (io2) volumes with higher IOPS allocation

**Explanation:** High queue depth indicates insufficient IOPS. Provisioned IOPS volumes allow you to specify exact IOPS requirements, eliminating performance bottlenecks for I/O-intensive applications.

---

### Question 15
A company needs to implement automated disaster recovery testing for their multi-tier application without impacting production. What is the best approach?

**Options:**

A. Manually create snapshots and test in a separate account quarterly

B. Use AWS Elastic Disaster Recovery (DRS) with isolated recovery testing

C. Schedule CloudFormation stack creation in DR region monthly

D. Use AWS Backup with cross-region replication only


**Answer:** B. Use AWS Elastic Disaster Recovery (DRS) with isolated recovery testing

**Explanation:** AWS DRS provides continuous replication and non-disruptive recovery testing in an isolated environment, enabling regular DR testing without production impact.

---

### Question 16
An RDS PostgreSQL instance is running out of storage space. The database size is unpredictable. What feature should be enabled to prevent storage issues?

**Options:**

A. Increase storage manually when needed

B. Enable RDS Storage Auto Scaling with maximum storage threshold

C. Migrate to Aurora Serverless

D. Enable automated backups with longer retention


**Answer:** B. Enable RDS Storage Auto Scaling with maximum storage threshold

**Explanation:** RDS Storage Auto Scaling automatically increases storage when free space drops below 10%, preventing outages due to storage exhaustion while controlling maximum costs.

---

### Question 17
A Lambda function experiences cold start latency affecting user experience. The function is invoked sporadically throughout the day. What optimization provides the best cost-performance balance?

**Options:**

A. Increase Lambda memory to maximum

B. Configure Provisioned Concurrency for expected baseline load

C. Keep the function warm using CloudWatch Events every minute

D. Rewrite the function in a compiled language


**Answer:** B. Configure Provisioned Concurrency for expected baseline load

**Explanation:** Provisioned Concurrency keeps function instances warm and ready to respond instantly, eliminating cold starts for the configured capacity while being more cost-effective than constant invocation.

---

### Question 18
A company's backup strategy uses daily RDS snapshots, but the recovery process takes too long. They need to reduce recovery time from 2 hours to 15 minutes. What should be implemented?

**Options:**

A. Increase snapshot frequency to hourly

B. Implement RDS Multi-AZ deployment for automatic failover instead of relying on snapshot restoration

C. Use faster instance types for restoration

D. Keep a standby database manually synchronized


**Answer:** B. Implement RDS Multi-AZ deployment for automatic failover instead of relying on snapshot restoration

**Explanation:** Multi-AZ provides automatic failover in minutes rather than hours required for snapshot restoration, meeting the 15-minute recovery objective.

---

### Question 19
An application uses NAT Gateways in multiple Availability Zones, resulting in high data transfer costs. Traffic analysis shows most traffic is to S3 and DynamoDB. What optimization reduces costs?

**Options:**
A. Use a single NAT Gateway instead of multiple

B. Implement VPC Gateway Endpoints for S3 and DynamoDB

C. Reduce the number of Availability Zones

D. Use VPN instead of NAT Gateway


**Answer:** B. Implement VPC Gateway Endpoints for S3 and DynamoDB

**Explanation:** Gateway Endpoints eliminate NAT Gateway data processing charges for S3 and DynamoDB traffic by routing traffic privately within AWS, significantly reducing costs.

---

### Question 20
A CloudWatch dashboard shows that an Auto Scaling group frequently launches instances that are immediately terminated. What is likely causing this and how should it be resolved?

**Options:**

A. Instances are unhealthy - fix application health check endpoint and increase health check grace period

B. Scaling policies are conflicting - remove one policy

C. Instance type is unavailable - change instance type

D. AMI is corrupted - rebuild AMI


**Answer:** A. Instances are unhealthy - fix application health check endpoint and increase health check grace period

**Explanation:** Rapid launch-terminate cycles indicate instances are failing health checks before application startup completes. Increasing grace period allows time for application initialization.

---

## Module 4: Designing Architecture (20 Questions)

### Question 1
A financial services company needs to design a highly secure architecture for processing sensitive customer data. The architecture must comply with PCI-DSS requirements. Which design principles should be implemented?

**Options:**

A. Deploy all resources in public subnets with security groups

B. Use VPC with private subnets, encryption at rest and in transit, AWS WAF, CloudTrail logging, and data tokenization

C. Use a single security group for all resources

D. Store sensitive data in S3 with public access


**Answer:** B. Use VPC with private subnets, encryption at rest and in transit, AWS WAF, CloudTrail logging, and data tokenization

**Explanation:** PCI-DSS compliance requires defense-in-depth: network isolation (private subnets), encryption, web application firewall, audit logging, and data protection techniques like tokenization.

---

### Question 2
A startup is designing a serverless e-commerce platform that must handle flash sales with unpredictable traffic spikes from 100 to 100,000 concurrent users. Which architecture best meets this requirement?

**Options:**

A. EC2 Auto Scaling with RDS

B. API Gateway + Lambda + DynamoDB + SQS for order processing + S3/CloudFront for static assets

C. ECS Fargate with Aurora Serverless

D. Elastic Beanstalk with RDS Multi-AZ


**Answer:** B. API Gateway + Lambda + DynamoDB + SQS for order processing + S3/CloudFront for static assets

**Explanation:** This fully serverless architecture automatically scales to handle extreme traffic variations without capacity planning, with SQS buffering orders during spikes and DynamoDB providing consistent performance.

---

### Question 3
A healthcare company needs to design an architecture for storing and processing medical images (DICOM files). Images must be retained for 10 years, accessed frequently in the first 3 months, and rarely thereafter. What storage architecture should be designed?

**Options:**

A. Store all images in S3 Standard for the entire 10 years

B. S3 with Intelligent-Tiering for automatic optimization

C. S3 Standard for 90 days, transition to S3 Glacier Flexible Retrieval, then to Glacier Deep Archive after 1 year, with metadata in DynamoDB

D. EFS for active files, manual archival to Glacier


**Answer:** C. S3 Standard for 90 days, transition to S3 Glacier Flexible Retrieval, then to Glacier Deep Archive after 1 year, with metadata in DynamoDB

**Explanation:** This architecture optimizes costs using S3 lifecycle policies while maintaining quick access to recent images, with DynamoDB storing searchable metadata for all images regardless of storage tier.

---

### Question 4
An IoT company needs to design an architecture for ingesting data from 1 million devices sending telemetry every 10 seconds. Data must be processed in real-time for alerts and stored for analytics. What architecture should be designed?

**Options:**

A. Devices → API Gateway → Lambda → S3

B. Devices → AWS IoT Core → Kinesis Data Streams → Lambda for alerts + Kinesis Firehose → S3 → Athena

C. Devices → ALB → EC2 → RDS

D. Devices → SQS → Lambda → DynamoDB


**Answer:** B. Devices → AWS IoT Core → Kinesis Data Streams → Lambda for alerts + Kinesis Firehose → S3 → Athena

**Explanation:** AWS IoT Core handles device connectivity and security, Kinesis processes streaming data at scale, Lambda enables real-time alerting, and Firehose provides efficient S3 loading for analytics.

---

### Question 5
A media company is designing a video streaming platform. Videos must be transcoded to multiple formats, stored efficiently, and delivered globally with low latency. Design the architecture.

**Options:**

A. Users upload to EC2, transcode manually, serve via S3

B. S3 for upload → EventBridge → MediaConvert for transcoding → S3 with Intelligent-Tiering → CloudFront with signed URLs

C. EFS for storage, EC2 for transcoding, CloudFront for delivery

D. Glacier for storage, Lambda for transcoding, S3 for delivery


**Answer:** B. S3 for upload → EventBridge → MediaConvert for transcoding → S3 with Intelligent-Tiering → CloudFront with signed URLs

**Explanation:** This architecture uses managed services: MediaConvert for professional transcoding, Intelligent-Tiering for cost optimization, CloudFront for global delivery, and signed URLs for access control.

---

### Question 6
A gaming company needs to design a leaderboard system handling millions of score updates per second with real-time ranking queries. What database architecture should be designed?

**Options:**

A. RDS MySQL with read replicas

B. DynamoDB with Global Secondary Index on score, using DynamoDB Streams to update cached rankings in ElastiCache

C. Aurora with parallel query

D. Redshift for analytical queries


**Answer:** B. DynamoDB with Global Secondary Index on score, using DynamoDB Streams to update cached rankings in ElastiCache

**Explanation:** DynamoDB handles high write throughput, GSI enables efficient score-based queries, and ElastiCache maintains real-time leaderboard rankings for ultra-fast reads.

---

### Question 7
A company is designing a multi-tenant SaaS application where customer data must be strictly isolated for compliance. What architecture pattern should be used?

**Options:**

A. Single database with tenant_id column for all customers

B. Separate VPC and complete infrastructure stack per tenant (silo model)

C. Pool model with separate databases per tenant using RDS Proxy for connection management, with VPC isolation for sensitive tenants

D. Single application with row-level security


**Answer:** C. Pool model with separate databases per tenant using RDS Proxy for connection management, with VPC isolation for sensitive tenants

**Explanation:** This hybrid approach balances isolation with operational efficiency: separate databases ensure data isolation, RDS Proxy manages connections efficiently, and VPC isolation is available for tenants requiring it.

---

### Question 8
A logistics company needs to design an architecture for a real-time package tracking system that updates locations every 30 seconds for millions of packages. Customers query package status via mobile app. Design the architecture.

**Options:**

A. Kinesis Data Streams for ingestion → Lambda for processing → DynamoDB for storage → AppSync GraphQL API for real-time queries with subscriptions

B. SQS → EC2 → RDS → REST API

C. Direct database writes → polling API

D. S3 for storage → Athena for queries


**Answer:** A. Kinesis Data Streams for ingestion → Lambda for processing → DynamoDB for storage → AppSync GraphQL API for real-time queries with subscriptions

**Explanation:** Kinesis handles high-velocity ingestion, DynamoDB provides fast key-value lookups, and AppSync with GraphQL subscriptions enables real-time updates pushed to mobile clients.

---

### Question 9
A company is designing an architecture for a document management system. Documents must be indexed for full-text search, with version control and access auditing. What architecture should be designed?

**Options:**

A. S3 for storage only

B. S3 with versioning → EventBridge → Lambda → Amazon OpenSearch Service for indexing, with CloudTrail for access auditing

C. EFS with manual indexing

D. RDS with full-text search


**Answer:** B. S3 with versioning → EventBridge → Lambda → Amazon OpenSearch Service for indexing, with CloudTrail for access auditing

**Explanation:** S3 versioning maintains document history, OpenSearch provides powerful full-text search capabilities, Lambda automates indexing, and CloudTrail logs all access for compliance.

---

### Question 10
A financial application needs to design an architecture for processing transactions that must be exactly-once and maintain strict ordering. Failed transactions must be automatically retried with exponential backoff. Design the architecture.

**Options:**

A. Standard SQS queue with Lambda

B. SQS FIFO queue → Lambda with reserved concurrency of 1, DLQ for failed messages, Step Functions for retry orchestration

C. Kinesis Data Streams with multiple shards

D. Direct database writes


**Answer:** B. SQS FIFO queue → Lambda with reserved concurrency of 1, DLQ for failed messages, Step Functions for retry orchestration

**Explanation:** FIFO queue ensures ordering and deduplication, reserved concurrency of 1 maintains order during processing, DLQ captures failures, and Step Functions implements sophisticated retry logic.

---

### Question 11
A company needs to design a data lake architecture for storing structured, semi-structured, and unstructured data from multiple sources, with governance and access control. What architecture should be designed?

**Options:**

A. Single S3 bucket with folders

B. S3 data lake with AWS Lake Formation for governance, Glue for ETL and cataloging, Athena for querying, and IAM + Lake Formation permissions for access control

C. RDS for all data types

D. Multiple independent databases


**Answer:** B. S3 data lake with AWS Lake Formation for governance, Glue for ETL and cataloging, Athena for querying, and IAM + Lake Formation permissions for access control

**Explanation:** This comprehensive architecture provides centralized data storage, automated governance, unified catalog, serverless querying, and fine-grained access control for enterprise data lakes.

---

### Question 12
A social media company is designing an architecture for user feeds that must display personalized content in real-time from multiple sources (posts, ads, recommendations). Design a scalable architecture.

**Options:**

A. Single RDS database with complex joins

B. Fan-out pattern using DynamoDB for user feeds, EventBridge for content events, Lambda for feed assembly, ElastiCache for caching compiled feeds, AppSync for real-time delivery

C. Polling-based approach with EC2

D. Store complete feeds in S3


**Answer:** B. Fan-out pattern using DynamoDB for user feeds, EventBridge for content events, Lambda for feed assembly, ElastiCache for caching compiled feeds, AppSync for real-time delivery

**Explanation:** This event-driven architecture pre-computes and caches personalized feeds for instant delivery, using DynamoDB for storage, Lambda for composition, and AppSync for real-time updates.

---

### Question 13
A company is designing a CI/CD architecture for deploying microservices to EKS clusters across multiple environments (dev, staging, prod) with automated testing and approval gates. Design the pipeline architecture.

**Options:**

A. Manual deployments using kubectl

B. CodePipeline → CodeBuild for tests → CodeDeploy to EKS with blue/green, separate pipelines per environment with manual approval before prod, parameter store for environment configs

C. Single EC2 instance running scripts

D. Direct Git pushes to production


**Answer:** B. CodePipeline → CodeBuild for tests → CodeDeploy to EKS with blue/green, separate pipelines per environment with manual approval before prod, parameter store for environment configs

**Explanation:** This architecture provides automated testing, safe deployments with blue/green strategy, environment separation, manual controls for production, and centralized configuration management.

---

### Question 14
A company needs to design an architecture for a real-time bidding platform for online advertising. Bid requests must be processed in under 100ms with high availability. Design the architecture.

**Options:**

A. API Gateway → Lambda → DynamoDB with DAX caching, read replicas across regions, Global Accelerator for routing

B. Single region EC2 with RDS

C. S3 for bid storage with batch processing

D. SQS with delayed processing


**Answer:** A. API Gateway → Lambda → DynamoDB with DAX caching, read replicas across regions, Global Accelerator for routing

**Explanation:** This low-latency architecture uses Lambda for fast processing, DynamoDB with DAX for microsecond data access, global tables for multi-region availability, and Global Accelerator for optimal routing.

---

### Question 15
A company is designing an event-driven architecture for order processing where orders trigger inventory updates, shipping notifications, and billing processes. Design a decoupled architecture.

**Options:**

A. Synchronous REST API calls between services

B. EventBridge as event bus → multiple rules routing to different targets (Lambda for billing, Step Functions for fulfillment, SQS for notifications), with DLQs for failed events

C. Single monolithic application

D. Direct database triggers


**Answer:** B. EventBridge as event bus → multiple rules routing to different targets (Lambda for billing, Step Functions for fulfillment, SQS for notifications), with DLQs for failed events

**Explanation:** EventBridge provides flexible event routing, enabling loose coupling between services, with each service processing events independently and DLQs ensuring no events are lost.

---

### Question 16
A company needs to design a secure architecture for a mobile banking application. The app requires user authentication, transaction processing, and PII protection. Design a secure architecture.

**Options:**

A. EC2 with no encryption

B. Cognito for authentication with MFA, API Gateway with Lambda authorizer, Lambda for business logic, RDS with encryption at rest, VPC private subnets, AWS WAF, Secrets Manager for credentials

C. Public database with simple passwords

D. Single EC2 instance handling everything


**Answer:** B. Cognito for authentication with MFA, API Gateway with Lambda authorizer, Lambda for business logic, RDS with encryption at rest, VPC private subnets, AWS WAF, Secrets Manager for credentials

**Explanation:** This defense-in-depth architecture implements multiple security layers: strong authentication, API security, encrypted data storage, network isolation, web application firewall, and secrets management.

---

### Question 17
A company is designing an architecture for a machine learning pipeline that trains models on large datasets nightly and serves predictions via API during the day. Design a cost-optimized architecture.

**Options:**
A. Keep large instances running 24/7

B. S3 for data storage → EventBridge scheduled rule → SageMaker Training with Spot instances at night → model artifacts to S3 → SageMaker Serverless Inference endpoints during day

C. Single EC2 instance for all tasks

D. Lambda for training (won't work due to limits)


**Answer:** B. S3 for data storage → EventBridge scheduled rule → SageMaker Training with Spot instances at night → model artifacts to S3 → SageMaker Serverless Inference endpoints during day

**Explanation:** This architecture minimizes costs using Spot instances for training, serverless inference that scales to zero when not needed, and S3 for cost-effective storage.

---

### Question 18
A media company needs to design an architecture for live video streaming to millions of concurrent viewers with support for adaptive bitrate streaming. Design the architecture.

**Options:**

A. Single EC2 streaming server

B. MediaLive for encoding → MediaPackage for packaging/origin → CloudFront for CDN delivery with HLS/DASH, S3 for VOD storage

C. Store videos on EC2 and serve directly

D. Use RDS for video storage


**Answer:** B. MediaLive for encoding → MediaPackage for packaging/origin → CloudFront for CDN delivery with HLS/DASH, S3 for VOD storage

**Explanation:** This architecture uses AWS managed services for professional-grade live streaming: MediaLive for encoding, MediaPackage for adaptive bitrate packaging, and CloudFront for global distribution.

---

### Question 19
A company needs to design an architecture for a content recommendation engine that analyzes user behavior in real-time and updates recommendations. Design a scalable architecture.

**Options:**

A. Batch processing daily

B. Kinesis Data Streams for clickstream → Kinesis Data Analytics for real-time analysis → Lambda to update recommendations → DynamoDB for user profiles → Personalize for ML recommendations

C. Manual analysis

D. Single database with complex queries


**Answer:** B. Kinesis Data Streams for clickstream → Kinesis Data Analytics for real-time analysis → Lambda to update recommendations → DynamoDB for user profiles → Personalize for ML recommendations

**Explanation:** This real-time architecture ingests behavioral data via Kinesis, analyzes patterns in real-time, leverages Amazon Personalize for ML-powered recommendations, and stores personalized profiles in DynamoDB.

---

### Question 20
A company is designing an architecture for a collaborative document editing platform (like Google Docs) that requires real-time synchronization between users, version control, and offline capability. Design the architecture.

**Options:**

A. Polling RDS database every second

B. AppSync with GraphQL subscriptions for real-time sync, DynamoDB for document storage with conflict resolution, S3 for version history, Cognito Sync for offline data

C. File sharing via email

D. Single server with WebSocket connections


**Answer:** B. AppSync with GraphQL subscriptions for real-time sync, DynamoDB for document storage with conflict resolution, S3 for version history, Cognito Sync for offline data

**Explanation:** AppSync provides real-time synchronization via GraphQL subscriptions, DynamoDB handles concurrent edits with conflict resolution, S3 stores version history, and Cognito Sync enables offline-first architecture.

---

## Module 5: Migration (18 Questions)

### Question 1
A company wants to migrate a 500TB on-premises database to AWS RDS. The migration must complete within 2 weeks with minimal downtime. Network bandwidth is limited to 100 Mbps. What migration strategy should be used?

**Options:**

A. AWS Database Migration Service over internet

B. AWS Snowball Edge to transfer database backup, then restore to RDS and use DMS for ongoing replication to minimize downtime

C. Direct Connect then DMS

D. Manual export/import using scripts


**Answer:** B. AWS Snowball Edge to transfer database backup, then restore to RDS and use DMS for ongoing replication to minimize downtime

**Explanation:** With 500TB and limited bandwidth, online transfer would take months. Snowball Edge physically transfers the bulk data quickly, then DMS replicates ongoing changes for minimal downtime cutover.

---

### Question 2
A company is migrating a monolithic application to AWS. They want to gradually decompose it into microservices. What migration strategy should be used?

**Options:**

A. Rehost (lift and shift) immediately to microservices

B. Rehost the monolith first to EC2, then gradually refactor components into Lambda/ECS microservices using the Strangler Fig pattern

C. Rewrite the entire application before migration

D. Stay on-premises


**Answer:** B. Rehost the monolith first to EC2, then gradually refactor components into Lambda/ECS microservices using the Strangler Fig pattern

**Explanation:** The Strangler Fig pattern allows gradual migration by routing new features to microservices while maintaining the monolith, reducing risk and enabling continuous delivery during modernization.

---

### Question 3
A company needs to migrate 100 applications from on-premises to AWS. They need to discover dependencies between applications before migration. Which service should be used?

**Options:**

A. Manual documentation

B. AWS Application Discovery Service (Agentless or Agent-based discovery) to map dependencies, then AWS Migration Hub for tracking

C. Trial and error migration

D. CloudWatch for discovery


**Answer:** B. AWS Application Discovery Service (Agentless or Agent-based discovery) to map dependencies, then AWS Migration Hub for tracking

**Explanation:** Application Discovery Service automatically discovers on-premises applications, their configurations, and dependencies, providing critical information for migration planning and execution tracking via Migration Hub.

---

### Question 4
A company is migrating a SQL Server database to AWS. They want to minimize licensing costs while maintaining compatibility. What target should they migrate to?

**Options:**
A. RDS for SQL Server with License Included

B. Aurora MySQL (requires application changes)

C. RDS for SQL Server using BYOL (Bring Your Own License), or consider Aurora PostgreSQL with Babelfish for SQL Server compatibility

D. Keep on-premises


**Answer:** C. RDS for SQL Server using BYOL (Bring Your Own License), or consider Aurora PostgreSQL with Babelfish for SQL Server compatibility

**Explanation:** BYOL reduces costs by using existing licenses, or Babelfish enables SQL Server applications to run on Aurora PostgreSQL, eliminating SQL Server licensing costs entirely.

---

### Question 5
A company is migrating VMware workloads to AWS and wants to use existing VMware management tools. What migration solution should be used?

**Options:**

A. Convert VMs to AMIs manually

B. VMware Cloud on AWS for seamless migration using vMotion, maintaining VMware tooling and skills

C. Rebuild all VMs as EC2 instances

D. Stay on-premises


**Answer:** B. VMware Cloud on AWS for seamless migration using vMotion, maintaining VMware tooling and skills

**Explanation:** VMware Cloud on AWS provides a managed VMware SDDC in AWS, enabling live migration using existing VMware tools like vMotion without re-platforming.

---

### Question 6
A company needs to migrate a large Oracle database (50TB) to AWS Aurora PostgreSQL. They need to minimize downtime and handle schema conversion. What migration approach should be used?

**Options:**

A. Manual export/import

B. AWS Schema Conversion Tool (SCT) to convert schema, then DMS with ongoing replication for minimal downtime migration

C. Backup and restore only

D. AWS Snowball for migration


**Answer:** B. AWS Schema Conversion Tool (SCT) to convert schema, then DMS with ongoing replication for minimal downtime migration

**Explanation:** SCT automates Oracle to PostgreSQL schema and code conversion, while DMS performs initial full load and continuous replication, enabling minimal downtime cutover.

---

### Question 7
A company is migrating a file server with 200TB of data to AWS. Users need to access files during migration. What solution provides seamless migration?

**Options:**

A. Stop file server and copy all data before cutover

B. AWS Storage Gateway File Gateway (SMB/NFS) caching frequently accessed files locally while migrating data to S3

C. Manual file copying over weekends

D. AWS Snowball only


**Answer:** B. AWS Storage Gateway File Gateway (SMB/NFS) caching frequently accessed files locally while migrating data to S3

**Explanation:** File Gateway provides transparent migration by presenting an SMB/NFS interface, caching active data locally, and asynchronously migrating to S3, allowing continued user access during migration.

---

### Question 8
A company wants to migrate a disaster recovery site to AWS and needs to replicate on-premises servers continuously. What service should be used?

**Options:**
A. Manual snapshots

B. AWS Elastic Disaster Recovery (CloudEndure Disaster Recovery) for continuous replication and quick failover/failback

C. Scheduled backups to S3

D. rsync scripts


**Answer:** B. AWS Elastic Disaster Recovery (CloudEndure Disaster Recovery) for continuous replication and quick failover/failback

**Explanation:** AWS DRS provides continuous block-level replication of on-premises servers to AWS, enabling RPO of seconds and RTO of minutes, with automated orchestration for failover and failback.

---

### Question 9
A company is migrating a web application to AWS and wants to test it in production with a small percentage of real traffic before full migration. What migration technique should be used?

**Options:**

A. Big bang migration

B. Blue/green migration with Route 53 weighted routing, starting with 5% traffic to AWS

C. Migrate all at once

D. Keep everything on-premises


**Answer:** B. Blue/green migration with Route 53 weighted routing, starting with 5% traffic to AWS

**Explanation:** Weighted routing enables gradual traffic shifting from on-premises (blue) to AWS (green), allowing real-world validation with minimal risk before full cutover.

---

### Question 10
A company needs to migrate multiple heterogeneous databases (Oracle, SQL Server, MySQL) to AWS with minimal manual effort. What approach should be used?

**Options:**

A. Manual migration one by one

B. Use AWS DMS with SCT for heterogeneous migrations, migrating multiple databases in parallel using DMS replication instances

C. Export/import for each database

D. Stay on-premises


**Answer:** B. Use AWS DMS with SCT for heterogeneous migrations, migrating multiple databases in parallel using DMS replication instances

**Explanation:** DMS with SCT supports heterogeneous database migrations at scale, with parallel migration capabilities and ongoing replication for minimal downtime.

---

### Question 11
A company is migrating a legacy application that requires specific IP addresses to be maintained. How can this be achieved in AWS?

**Options:**

A. Use Elastic IPs for EC2 instances

B. Bring Your Own IP (BYOIP) to AWS, advertising the IP range via BGP

C. Use random AWS IPs and update all references

D. Cannot maintain IPs in AWS


**Answer:** B. Bring Your Own IP (BYOIP) to AWS, advertising the IP range via BGP

**Explanation:** BYOIP allows migrating publicly routable IP address blocks to AWS, maintaining the same IPs after migration, critical for legacy applications with hardcoded IP dependencies.

---

### Question 12
A company wants to migrate a mainframe application to AWS. The application has complex dependencies and business logic. What migration strategy is most appropriate?

**Options:**

A. Rehost directly

B. Refactor/re-architect using modern AWS services, potentially using AWS Mainframe Modernization for automated conversion

C. Keep on mainframe forever

D. Manual rewrite without tools


**Answer:** B. Refactor/re-architect using modern AWS services, potentially using AWS Mainframe Modernization for automated conversion

**Explanation:** Mainframe migration requires re-architecture due to fundamental platform differences. AWS Mainframe Modernization provides tools for automated code conversion and runtime environments.

---

### Question 13
A company is migrating to AWS and needs to understand their current total cost of ownership (TCO) to justify the migration. What tool should they use?

**Options:**

A. Manual spreadsheet calculations

B. AWS Pricing Calculator and AWS Migration Evaluator (formerly TSO Logic) for TCO analysis

C. Guess based on current costs

D. Use on-premises costs as-is


**Answer:** B. AWS Pricing Calculator and AWS Migration Evaluator (formerly TSO Logic) for TCO analysis

**Explanation:** Migration Evaluator analyzes on-premises infrastructure usage data to create accurate TCO comparisons and AWS cost projections, providing business case justification.

---

### Question 14
A company is migrating 1,000 servers to AWS. They need to minimize the migration timeframe and want to automate as much as possible. What approach should be used?

**Options:**

A. Manual migration one server at a time

B. AWS Application Migration Service (MGN) for automated replication and orchestration at scale, with Migration Hub for tracking

C. Create AMIs manually for each server

D. Physical server shipping


**Answer:** B. AWS Application Migration Service (MGN) for automated replication and orchestration at scale, with Migration Hub for tracking

**Explanation:** MGN (formerly CloudEndure Migration) automates lift-and-shift migrations at scale with continuous replication, automated conversion, and orchestrated testing, significantly accelerating large migrations.

---

### Question 15
A company needs to migrate a shared file system that is accessed by multiple on-premises servers to AWS. During migration, both on-premises and AWS resources need concurrent access. What solution should be used?

**Options:**

A. Copy files to S3 and change all applications

B. AWS Storage Gateway Volume Gateway or File Gateway to provide concurrent access during migration

C. Stop all access during migration

D. Manual file synchronization


**Answer:** B. AWS Storage Gateway Volume Gateway or File Gateway to provide concurrent access during migration

**Explanation:** Storage Gateway acts as a bridge, providing on-premises applications with local access while synchronizing data to AWS, enabling phased migration without disruption.

---

### Question 16
A company is migrating a multi-tier application and wants to migrate each tier independently over several months. What migration strategy supports this approach?

**Options:**

A. Big bang migration

B. Phased migration using hybrid connectivity (Direct Connect or VPN) allowing tiers to communicate across on-premises and AWS

C. Migrate all tiers simultaneously

D. Cannot migrate tiers separately


**Answer:** B. Phased migration using hybrid connectivity (Direct Connect or VPN) allowing tiers to communicate across on-premises and AWS

**Explanation:** Hybrid connectivity enables gradual migration by allowing application tiers in AWS to communicate with tiers remaining on-premises, supporting a phased approach.

---

### Question 17
A company completed a lift-and-shift migration to AWS but now wants to optimize costs and modernize. What post-migration optimization strategy should they follow?

**Options:**

A. Keep everything as migrated

B. Right-size instances using AWS Compute Optimizer, implement Reserved Instances/Savings Plans, containerize suitable applications, adopt managed services for databases

C. Migrate back on-premises

D. Increase all instance sizes


**Answer:** B. Right-size instances using AWS Compute Optimizer, implement Reserved Instances/Savings Plans, containerize suitable applications, adopt managed services for databases

**Explanation:** Post-migration optimization involves right-sizing based on actual usage, leveraging pricing models for predictable workloads, modernizing through containerization, and using managed services to reduce operational overhead.

---

### Question 18
A company needs to migrate a SAP HANA environment to AWS with high availability and disaster recovery. What architecture should be implemented?

**Options:**

A. Single EC2 instance

B. SAP-certified EC2 instances (X1, X1e, or High Memory) with Multi-AZ deployment using HANA System Replication, EBS snapshots for backup, optional DR in another region

C. RDS for SAP

D. Lambda for SAP workloads


**Answer:** B. SAP-certified EC2 instances (X1, X1e, or High Memory) with Multi-AZ deployment using HANA System Replication, EBS snapshots for backup, optional DR in another region

**Explanation:** SAP HANA requires certified large-memory instances with HANA System Replication for HA, EBS snapshots for backup/recovery, and optional cross-region replication for DR according to SAP best practices on AWS.

---

### Question 19
A company is migrating a content management system with 10TB of media files stored on NFS. They need minimal disruption during migration. What's the best migration approach?

**Options:**

A. Copy all files manually over VPN

B. AWS DataSync to automate and accelerate NFS migration to S3 or EFS with incremental transfers and validation

C. Use Snowball for one-time transfer only

D. FTP transfer


**Answer:** B. AWS DataSync to automate and accelerate NFS migration to S3 or EFS with incremental transfers and validation

**Explanation:** DataSync automates data transfer with up to 10x faster speeds than open-source tools, handles incremental synchronization, validates data integrity, and minimizes disruption during migration.

---

### Question 20
A company wants to migrate their e-commerce application to AWS but needs to maintain their existing SSL certificates and domain names. How should this be handled?

**Options:**

A. Purchase new certificates and domains in AWS

B. Import existing SSL certificates into AWS Certificate Manager or IAM, update DNS records in Route 53 or current DNS provider to point to AWS resources

C. Cannot use existing certificates in AWS

D. Use only AWS-issued certificates


**Answer:** B. Import existing SSL certificates into AWS Certificate Manager or IAM, update DNS records in Route 53 or current DNS provider to point to AWS resources

**Explanation:** Existing SSL certificates can be imported into ACM or IAM for use with AWS services, and DNS records can be gradually updated to point to AWS, maintaining continuity during migration.

---

## Summary

This comprehensive practice question set covers all 5 modules:

- Module 1: AWS Architecture  - VPC design, hybrid architectures, storage solutions, compute options, and architectural best practices
- Module 2: API & Deployment Strategies  - API Gateway, deployment patterns, CI/CD, blue/green deployments, canary releases
- Module 3: Optimizations & Recovery - Performance optimization, cost optimization, disaster recovery, scaling, backup strategies
- Module 4: Designing Architecture  - Industry-specific architectures, event-driven design, security patterns, real-time systems, ML pipelines
- Module 5: Migration  - Migration strategies, database migration, large-scale migrations, mainframe modernization, hybrid scenarios


Each question follows AWS Solutions Architect exam format with:
- Real-world scenarios
- Multiple choice options
- Clear correct answers
- Detailed explanations
- AWS best practices
