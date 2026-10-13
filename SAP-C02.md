# SAP-C02 In-Scope Services: One-Liners

Source: official [SAP-C02 In-Scope AWS Services](https://docs.aws.amazon.com/aws-certification/latest/solutions-architect-professional-02/sap-02-in-scope-services.html) list (non-exhaustive, subject to change). Checked 13 Oct 2026.

Legend: ⭐ = your weak area (analytics, security, IAM), study deeper. ⚠️ = still on the exam list, but AWS has closed it to new customers (Maintenance), set an end date (Sunset), or shut it down. Status checked against the [AWS Lifecycle Changes](https://docs.aws.amazon.com/general/latest/gr/service-lifecycle.html) pages on 13 Oct 2026. Know what these services do, but expect the exam to favour their replacements.

---

## Analytics ⭐

| Service | One-liner |
|---|---|
| Amazon Athena | Serverless SQL directly on S3 data; pay per data scanned, so partition and use Parquet. |
| AWS Data Exchange | Find, subscribe to, and consume third-party datasets straight into S3, Redshift, or via API. |
| Amazon Data Firehose | Zero-admin delivery of streaming data to S3, Redshift, OpenSearch, Splunk, with buffering and transforms; near real time, not replayable. |
| Amazon EMR | Managed Hadoop/Spark/Hive/Presto clusters (EC2, EKS, or Serverless) for big data processing when you need framework control. |
| AWS Glue | Serverless ETL (Spark) plus the Data Catalog that Athena, EMR, and Redshift Spectrum share as a metastore. |
| Amazon Kinesis Data Streams | Real-time, ordered (per shard), replayable stream with multiple consumers; think "SQS you can rewind and fan out." |
| AWS Lake Formation | Governance layer over the Glue Catalog for fine-grained (table, column, row, cell) data lake permissions and cross-account sharing. |
| Amazon Managed Service for Apache Flink | Stateful real-time stream processing (windows, joins, aggregations) over Kinesis or MSK. |
| Amazon MSK | Managed Apache Kafka; pick it when the scenario already uses Kafka or needs Kafka APIs. |
| Amazon OpenSearch Service | Managed search and log analytics (full-text search, dashboards); common Firehose destination. |
| Amazon QuickSight | Serverless BI dashboards with row-level security; now branded Amazon Quick Sight inside Amazon Quick (formerly Quick Suite). |

## Application Integration

| Service | One-liner |
|---|---|
| Amazon AppFlow | No-code data transfer between SaaS apps (Salesforce, SAP, Zendesk) and AWS services like S3 or Redshift. |
| AWS AppSync | Managed GraphQL (and real-time pub/sub) API layer over DynamoDB, Lambda, and other sources, with offline sync. |
| Amazon EventBridge | Serverless event bus with content-based routing, cross-account buses, SaaS sources, Pipes, and Scheduler. |
| Amazon MQ | Managed ActiveMQ/RabbitMQ; the lift-and-shift answer when apps use JMS, AMQP, MQTT, or STOMP. |
| Amazon SNS | Pub/sub fan-out to SQS, Lambda, HTTP, email, and SMS; pair with SQS for durable fan-out. |
| Amazon SQS | Fully managed queue for decoupling; Standard for throughput, FIFO for ordering and exactly-once processing. |
| AWS Step Functions | Serverless state machine orchestration with retries, branching, and human approval; Standard vs Express workflows. |

## Blockchain

| Service | One-liner |
|---|---|
| Amazon Managed Blockchain ⚠️ | Managed Hyperledger Fabric and Ethereum networks for multi-party ledgers; in Sunset, end of support 29 Sep 2027. |

## Business Applications

| Service | One-liner |
|---|---|
| Amazon SES | Scalable transactional and marketing email sending and receiving. |

## Cloud Financial Management

| Service | One-liner |
|---|---|
| AWS Budgets | Cost, usage, and RI/Savings Plans budgets with alerts and automated actions (for example, apply an SCP). |
| AWS Cost and Usage Report | Most granular billing data delivered to S3, queried with Athena or QuickSight for chargeback. |
| AWS Cost Explorer | Visualize and forecast spend, and get RI and Savings Plans purchase recommendations. |
| Savings Plans | 1 or 3 year $/hour commitment; Compute SP flexes across EC2, Fargate, and Lambda, EC2 Instance SP is cheaper but narrower. |

## Compute

| Service | One-liner |
|---|---|
| AWS App Runner ⚠️ | Source code or container to a running HTTPS web service with no infrastructure to manage; closed to new customers (Maintenance, Mar 2026). |
| AWS Auto Scaling | Unified scaling plans across EC2, ECS, DynamoDB, and Aurora resources. |
| AWS Batch | Managed batch job queues and scheduling on EC2, Spot, or Fargate. |
| AWS Elastic Beanstalk | PaaS that deploys web apps onto EC2, ELB, and Auto Scaling for you; supports blue/green via URL swap. |
| Amazon EC2 | Virtual servers; know purchase options (On-Demand, Spot, RI, SP, Dedicated Hosts) and placement groups. |
| Amazon EC2 Auto Scaling | Scale EC2 fleets with target tracking, step, scheduled, or predictive policies; warm pools and lifecycle hooks. |
| AWS Fargate | Serverless compute engine for ECS and EKS tasks; no instances to patch. |
| AWS Lambda | Event-driven functions up to 15 minutes; know concurrency, provisioned concurrency, and VPC access. |
| Amazon Lightsail | Simple fixed-price VPS bundles for small apps; rarely the answer at enterprise scale. |
| AWS Outposts | AWS hardware in your data center for low latency or data residency with AWS APIs. |
| AWS Wavelength | Compute at 5G carrier edge for single-digit millisecond mobile latency. |

## Containers

| Service | One-liner |
|---|---|
| Amazon ECR | Private container registry with image scanning and cross-Region/cross-account replication. |
| Amazon ECS | AWS-native container orchestration on EC2 or Fargate. |
| Amazon ECS Anywhere | Run ECS tasks on your on-premises servers, managed from the ECS control plane. |
| Amazon EKS | Managed Kubernetes control plane; pick when the scenario says Kubernetes or portability. |
| Amazon EKS Anywhere | Run and manage Kubernetes clusters on your own infrastructure using EKS tooling. |
| Amazon EKS Distro | The open-source Kubernetes distribution EKS uses, self-managed anywhere. |

## Database

| Service | One-liner |
|---|---|
| Amazon Aurora | MySQL/PostgreSQL compatible, 6 copies across 3 AZs, up to 15 replicas, Global Database for cross-Region DR. |
| Amazon Aurora Serverless | Aurora that scales capacity automatically; fits spiky or unpredictable workloads. |
| Amazon DocumentDB | Managed MongoDB-compatible document database. |
| Amazon DynamoDB | Serverless key-value NoSQL at any scale; Global Tables, DAX, Streams, PITR, on-demand vs provisioned. |
| Amazon ElastiCache | Managed Redis/Valkey or Memcached for caching, sessions, and leaderboards. |
| Amazon Keyspaces | Serverless Apache Cassandra-compatible database. |
| Amazon Neptune | Managed graph database for relationships (social, fraud, knowledge graphs). |
| Amazon RDS | Managed relational engines (MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, Db2); Multi-AZ for HA, read replicas for scale. |
| Amazon Redshift | Columnar data warehouse; Spectrum queries S3, Serverless option, data sharing across accounts. |
| Amazon Timestream | Time-series database for IoT and operational metrics; Timestream for LiveAnalytics is closed to new customers, Timestream for InfluxDB is the active option. |

## Developer Tools

| Service | One-liner |
|---|---|
| AWS CodeArtifact | Managed package repository (npm, Maven, PyPI) with upstream proxying. |
| AWS CodeBuild | Serverless build and test runner. |
| AWS CodeDeploy | Automated deployments to EC2, on-premises, Lambda, and ECS with in-place, blue/green, or canary. |
| Amazon CodeGuru ⚠️ | ML-powered code review (Reviewer) and runtime profiling (Profiler); CodeGuru Reviewer is closed to new customers. |
| AWS CodePipeline | CI/CD orchestration chaining source, build, test, approval, and deploy stages. |
| AWS X-Ray | Distributed tracing to find latency and errors across microservices. |

## End User Computing

| Service | One-liner |
|---|---|
| Amazon AppStream 2.0 | Stream individual desktop applications to a browser; renamed Amazon WorkSpaces Applications in Nov 2025. |
| Amazon WorkSpaces | Managed persistent virtual desktops (DaaS). |

## Frontend Web and Mobile

| Service | One-liner |
|---|---|
| AWS Amplify | Build and host full-stack web and mobile apps with managed backends and CI/CD hosting. |
| Amazon API Gateway | Managed REST, HTTP, and WebSocket APIs with throttling, auth, caching, and private endpoints. |
| AWS Device Farm | Test apps on real mobile devices and browsers. |
| Amazon Pinpoint ⚠️ | Multichannel customer engagement (campaigns, SMS, push); in Sunset, end of support 30 Oct 2026, features moving to AWS End User Messaging and Amazon Connect. |

## Internet of Things (IoT)

| Service | One-liner |
|---|---|
| AWS IoT Core | Managed MQTT broker and rules engine connecting devices to AWS services. |
| AWS IoT Device Defender | Audit IoT fleets for security misconfigurations; the Detect (anomaly monitoring) feature is closed to new customers. |
| AWS IoT Device Management | Onboard, organize, monitor, and remotely update devices at scale (OTA jobs). |
| AWS IoT Events ⚠️ | Detected state changes in sensor data; fully shut down 20 May 2026. |
| AWS IoT Greengrass | Run Lambda, containers, and ML inference on edge devices, even offline; use V2 (V1 reached end of support 7 Oct 2026). |
| AWS IoT SiteWise | Collect and model industrial equipment data at scale. |
| AWS IoT Things Graph ⚠️ | Visual tool to connect devices into workflows; fully shut down 9 Nov 2022. |
| AWS IoT 1-Click ⚠️ | Simple devices that triggered Lambda with one click; fully shut down 29 Jan 2025. |

## Machine Learning

| Service | One-liner |
|---|---|
| Amazon Comprehend | NLP for sentiment, entities, key phrases, language, and PII detection in text. |
| Amazon Fraud Detector ⚠️ | Managed fraud detection models for payments and fake accounts; closed to new customers since Nov 2025. |
| Amazon Kendra ⚠️ | ML-powered enterprise search across documents; closed to new customers (Maintenance, Jun 2026). |
| Amazon Lex | Conversational chatbots with speech and text (the engine behind Alexa). |
| Amazon Personalize | Real-time personalized recommendations without ML expertise. |
| Amazon Polly | Text to lifelike speech. |
| Amazon Rekognition | Image and video analysis: objects, faces, moderation, text. |
| Amazon SageMaker AI | Build, train, and deploy custom ML models end to end. |
| Amazon Textract | Extract text, forms, and tables from scanned documents (beyond plain OCR). |
| Amazon Transcribe | Speech to text, including call analytics and PII redaction. |
| Amazon Translate | Neural machine translation between languages. |

## Media Services

| Service | One-liner |
|---|---|
| Amazon Elastic Transcoder ⚠️ | Legacy media transcoding; fully shut down 13 Nov 2025, replaced by AWS Elemental MediaConvert. |
| Amazon Kinesis Video Streams | Ingest, store, and process video streams from cameras for playback and analytics. |

## Management and Governance ⭐

| Service | One-liner |
|---|---|
| AWS CloudFormation | Infrastructure as code; StackSets deploy across accounts and Regions in an Organization. |
| AWS CloudTrail | Records API calls for audit; use an organization trail to a central, locked-down log archive bucket. |
| Amazon CloudWatch | Metrics, alarms, dashboards, and cross-account observability. |
| Amazon CloudWatch Logs | Centralized log storage, Logs Insights queries, subscription filters to Kinesis or Lambda. |
| AWS CLI | Command line control of AWS services and scripting. |
| AWS Compute Optimizer | ML rightsizing recommendations for EC2, ASG, EBS, Lambda, and ECS on Fargate. |
| AWS Config | Records resource configuration history and evaluates compliance rules with auto-remediation; aggregators for multi-account. |
| AWS Control Tower | Automated multi-account landing zone with guardrails (SCPs and Config rules) and Account Factory. |
| AWS Health Dashboard | Personalized view of AWS events affecting your resources; organizational view across accounts. |
| AWS License Manager | Track and enforce software license usage (BYOL) across accounts. |
| Amazon Managed Grafana | Managed Grafana dashboards over multiple data sources. |
| Amazon Managed Service for Prometheus | Managed Prometheus-compatible metrics monitoring for containers. |
| AWS Management Console | Web UI for AWS. |
| AWS Organizations | Multi-account management: OUs, consolidated billing, SCPs, RCPs, and delegated administrators. |
| AWS Proton ⚠️ | Platform teams published standard templates for self-service deployment; reached end of support 7 Oct 2026. |
| AWS Service Catalog | Curated, approved CloudFormation products end users can launch without broad IAM permissions. |
| Service Quotas | View and request increases to service limits centrally, including quota templates for new accounts. |
| AWS Systems Manager | Ops hub for EC2 and on-prem: Session Manager, Patch Manager, Run Command, Parameter Store, Automation. |
| AWS Trusted Advisor | Best-practice checks across cost, security, fault tolerance, performance, and quotas. |
| AWS Well-Architected Tool | Review workloads against the six Well-Architected pillars and track improvement plans. |

## Migration and Transfer

| Service | One-liner |
|---|---|
| AWS Application Discovery Service ⚠️ | Discover on-prem servers, utilization, and dependencies to plan migrations; closed to new customers (Maintenance, Oct 2025), and its Discovery Connector is shut down. |
| AWS Application Migration Service (MGN) | Block-level replication for lift-and-shift rehosting of servers to EC2 with minimal downtime. |
| AWS DMS | Migrate and continuously replicate (CDC) databases with minimal downtime, homogeneous or heterogeneous. |
| AWS DataSync | Online, accelerated file and object transfer between on-prem (NFS, SMB, HDFS) and S3, EFS, or FSx. |
| AWS Migration Hub ⚠️ | Single place to track migration progress across tools; closed to new customers (Maintenance, Nov 2025). |
| AWS SCT | Converts database schema and code between engines (for example, Oracle to Aurora PostgreSQL); pair with DMS. |
| AWS Snow Family ⚠️ | Physical devices for offline bulk transfer and edge compute; Snowball Edge is existing customers only, Snowcone and Snowmobile are gone (see Part 4). |
| AWS Transfer Family | Managed SFTP, FTPS, FTP, and AS2 endpoints backed by S3 or EFS. |

## Networking and Content Delivery

| Service | One-liner |
|---|---|
| Amazon CloudFront | Global CDN with edge caching, OAC for private S3, Lambda@Edge and CloudFront Functions. |
| AWS Direct Connect | Dedicated private link from on-prem to AWS; consistent latency, use VPN backup or dual DX for resiliency. |
| Elastic Load Balancing | ALB (L7, path/host routing), NLB (L4, static IP, extreme performance), GWLB (inline appliances). |
| AWS Global Accelerator | Anycast static IPs routing over the AWS backbone for fast, non-HTTP-friendly multi-Region failover. |
| AWS PrivateLink | Expose a service privately to other VPCs or accounts via interface endpoints, without peering or overlapping CIDR issues. |
| Amazon Route 53 | DNS with routing policies (latency, failover, weighted, geolocation), health checks, and Resolver for hybrid DNS. |
| AWS Transit Gateway | Hub-and-spoke router for thousands of VPCs and on-prem networks; share across accounts with RAM. |
| Amazon VPC | Isolated network: subnets, route tables, SGs (stateful), NACLs (stateless), endpoints, peering (non-transitive). |
| AWS VPN | Encrypted IPsec Site-to-Site VPN over the internet, plus Client VPN for remote users. |

## Security, Identity, and Compliance ⭐

| Service | One-liner |
|---|---|
| AWS Artifact | Download AWS compliance reports (SOC, PCI, ISO) and accept agreements like the BAA. |
| AWS Audit Manager ⚠️ | Continuously collect evidence and map it to compliance frameworks; closed to new customers (Maintenance, Mar 2026). |
| AWS Certificate Manager (ACM) | Free public TLS certificates with auto-renewal for ELB, CloudFront, and API Gateway; private CA option. |
| AWS CloudHSM | Single-tenant, FIPS 140 validated HSMs where you exclusively control the keys. |
| Amazon Cognito | User pools (sign-up and sign-in for app users) and identity pools (temporary AWS credentials). |
| Amazon Detective | Investigate root cause of security findings using graph analysis of logs. |
| AWS Directory Service | Managed Microsoft AD or AD Connector (proxy to on-prem AD); Simple AD is closed to new customers. |
| AWS Firewall Manager | Centrally deploy WAF, Shield Advanced, SG, and Network Firewall policies across an Organization. |
| Amazon GuardDuty | Managed threat detection from CloudTrail, VPC Flow Logs, DNS logs, and more; delegated admin for the org. |
| AWS IAM Identity Center | Central workforce SSO and permission sets across all Organization accounts, federated to your IdP. |
| AWS IAM | Users, roles, and policies; know evaluation logic: explicit deny beats allow, plus SCPs, boundaries, and session policies. |
| Amazon Inspector | Automated vulnerability scanning for EC2, ECR images, and Lambda. |
| AWS KMS | Managed encryption keys; key policies, grants, multi-Region keys, and cross-account key sharing. |
| Amazon Macie | ML discovery of sensitive data (PII) in S3. |
| AWS Network Firewall | Managed stateful network firewall and IPS for VPC traffic inspection, often in a centralized inspection VPC. |
| AWS RAM | Share resources (TGW, subnets, Resolver rules) across accounts or the Organization. |
| AWS Secrets Manager | Store and automatically rotate secrets like DB credentials; choose over Parameter Store when rotation is needed. |
| AWS Security Hub | Aggregate and prioritize findings plus run security standard checks across accounts and Regions. |
| AWS STS | Issues temporary credentials via AssumeRole, the backbone of cross-account access and federation. |
| AWS Shield | DDoS protection; Standard is free, Advanced adds L7 response team support and cost protection. |
| AWS WAF | Layer 7 filtering (SQLi, XSS, rate limits, geo) on CloudFront, ALB, API Gateway, and AppSync. |

## Storage

| Service | One-liner |
|---|---|
| AWS Backup | Centralized, policy-based backups across services and accounts, with Vault Lock and cross-Region copy. |
| Amazon EBS | Block storage for EC2 in one AZ; gp3, io2, snapshots, and Fast Snapshot Restore. |
| AWS Elastic Disaster Recovery | Continuous block replication for low RPO/RTO DR of servers into AWS. |
| Amazon EFS | Elastic, multi-AZ NFS file system for Linux, shared across many instances. |
| Amazon FSx | Managed Windows File Server, Lustre (HPC), NetApp ONTAP, and OpenZFS file systems. |
| Amazon S3 | Durable object storage; storage classes, lifecycle, replication (CRR/SRR), Object Lock, access points. |
| Amazon S3 Glacier | Low-cost archive storage classes (Instant, Flexible, Deep Archive); the old vault-based Glacier API is closed to new customers, so use the S3 storage classes. |
| AWS Storage Gateway | Hybrid access to cloud storage: S3 File, FSx File, Volume, and Tape Gateway. |

---

# Part 2: Look-Alike Service Comparisons

These are the pairs and triples the exam deliberately puts side by side as distractors.

### Cognito User Pool vs Identity Pool ⭐
| | User Pool | Identity Pool |
|---|---|---|
| Answers | "Who are you?" (authentication) | "What AWS resources can you touch?" (authorization) |
| Output | JWT tokens (ID, access, refresh) | Temporary AWS credentials via STS |
| Use for | Sign-up/sign-in, social and SAML login for app users | Letting app users call S3 or DynamoDB directly |
| Together | User Pool logs the user in, Identity Pool exchanges that token for an IAM role |

### SCP vs IAM Policy vs Permission Boundary vs Resource Policy ⭐
| | Grants access? | Scope | Exam cue |
|---|---|---|---|
| SCP | No, only sets the maximum | Every principal in an account or OU (not the management account) | "Prevent any account from leaving a Region / disabling CloudTrail" |
| RCP | No, only sets the maximum | Resources in member accounts | "Data perimeter: no external principal can access our S3 or KMS" |
| Permission boundary | No, only sets the maximum | One IAM user or role | "Let developers create roles without escalating privilege" |
| Identity policy | Yes | Attached to user, group, or role | Normal permissions |
| Resource policy | Yes | Attached to resource (S3, KMS, SQS) | Cross-account access without assuming a role |

Evaluation order: explicit Deny anywhere wins, then every applicable limiter (SCP, RCP, boundary, session policy) must allow, then an identity or resource policy must allow.

### Secrets Manager vs Systems Manager Parameter Store ⭐
| | Secrets Manager | Parameter Store |
|---|---|---|
| Built-in rotation | Yes (native for RDS, Redshift, DocumentDB) | No (DIY with Lambda) |
| Cost | Per secret per month | Standard tier free |
| Cross-Region replication | Yes | No |
| Pick when | "Rotate DB credentials automatically" | "Store config values cheaply" |

### Kinesis Data Streams vs Data Firehose vs SQS vs MSK ⭐
| | Kinesis Data Streams | Data Firehose | SQS | MSK |
|---|---|---|---|---|
| Latency | Real time (~200 ms) | Near real time (buffered) | Real time | Real time |
| Replay | Yes (retention) | No | No (deleted on consume) | Yes |
| Consumers | Many, each reads all | Delivers to a destination | Competing consumers, one gets each message | Many |
| Ops effort | Shards or on-demand | Zero | Zero | Brokers to size |
| Exam cue | "Multiple apps process the same stream" | "Load streaming data into S3/Redshift with no code" | "Decouple, buffer work" | "Existing Kafka" |

### SNS vs SQS vs EventBridge
| | SNS | SQS | EventBridge |
|---|---|---|---|
| Model | Push pub/sub | Pull queue | Event bus with rules |
| Filtering | Message attribute filter | None | Rich content-based patterns |
| Pick when | High-throughput fan-out | Buffering and retries | SaaS or AWS service events, cross-account routing, schedules |

### VPC Peering vs Transit Gateway vs PrivateLink vs Cloud WAN
| | VPC Peering | Transit Gateway | PrivateLink | Cloud WAN |
|---|---|---|---|---|
| Topology | 1:1, non-transitive | Hub and spoke, transitive | Service consumer to provider | Global managed WAN |
| Overlapping CIDRs | Not allowed | Not allowed | Allowed | Not allowed |
| Cost | No hourly fee, cheapest data path | Hourly per attachment plus per GB | Per endpoint hour plus per GB | Highest |
| Exam cue | "Few VPCs, lowest cost" | "Hundreds of VPCs plus on-prem" | "Expose one service to many accounts / overlapping IPs" | "Multi-Region global network with central policy" |

### Gateway Endpoint vs Interface Endpoint
| | Gateway Endpoint | Interface Endpoint |
|---|---|---|
| Services | S3 and DynamoDB only | Most AWS services and PrivateLink services |
| Mechanism | Route table entry | ENI with private IP in your subnet |
| Cost | Free | Hourly plus per GB |
| Reachable from on-prem | No | Yes (via DX or VPN) |

### Site-to-Site VPN vs Direct Connect
| | Site-to-Site VPN | Direct Connect |
|---|---|---|
| Path | Encrypted IPsec over internet | Private dedicated fibre |
| Setup time | Minutes | Weeks to months |
| Bandwidth | Up to 1.25 Gbps per tunnel (ECMP to aggregate on TGW) | 1, 10, 100, 400 Gbps dedicated; hosted from 50 Mbps |
| Encryption | Built in | Not by default, add MACsec (10/100/400 Gbps, select locations) or VPN over DX |
| Exam cue | "Quick, cheap, temporary or backup" | "Consistent latency, high throughput, large daily data" |

### ALB vs NLB vs GWLB
| | ALB | NLB | GWLB |
|---|---|---|---|
| Layer | 7 (HTTP/HTTPS/gRPC) | 4 (TCP/UDP/TLS) | 3 (GENEVE) |
| Key feature | Path, host, header routing, OIDC auth, WAF | Static or Elastic IP, millions of rps, ultra-low latency, PrivateLink provider | Inserts third-party firewalls and IDS transparently |

### CloudFront vs Global Accelerator
| | CloudFront | Global Accelerator |
|---|---|---|
| Caches content | Yes | No |
| Protocols | HTTP/HTTPS | TCP/UDP (any) |
| Entry point | DNS name | 2 static anycast IPs |
| Exam cue | "Static and dynamic web content, edge caching" | "Gaming, VoIP, IoT; static IP; fast Regional failover" |

### DataSync vs Storage Gateway vs Transfer Family vs Snowball
| | DataSync | Storage Gateway | Transfer Family | Snowball Edge |
|---|---|---|---|---|
| Purpose | One-time or scheduled bulk copy | Ongoing hybrid access with local cache | SFTP/FTPS/AS2 endpoint for partners | Offline transfer when network is too slow |
| Exam cue | "Migrate NFS/SMB/HDFS to S3/EFS/FSx" | "On-prem apps keep using file, volume, or tape interface" | "Partners upload via SFTP, no server changes for them" | "Limited bandwidth, hundreds of TB" (existing customers only, see numbers) |

### MGN vs DMS vs SCT vs Elastic Disaster Recovery
| | MGN | DMS | SCT | DRS |
|---|---|---|---|---|
| Moves | Whole servers (rehost) | Database data, with CDC | Schema and stored procedures | Servers for DR, not migration |
| Exam cue | "Lift and shift 500 VMs, minimal downtime" | "Migrate DB with minimal downtime" | "Oracle to Aurora PostgreSQL (heterogeneous)" | "Low RPO/RTO DR for on-prem servers" |

### DR Strategies
| Strategy | RPO/RTO | Cost | What runs in DR Region |
|---|---|---|---|
| Backup and restore | Hours | $ | Only backups |
| Pilot light | Tens of minutes | $$ | Data replicated, core infra off |
| Warm standby | Minutes | $$$ | Scaled-down full stack running |
| Multi-site active/active | Near zero | $$$$ | Full production in both |

### Aurora Global Database vs RDS Cross-Region Read Replica vs DynamoDB Global Tables
| | Aurora Global DB | RDS Cross-Region Replica | DynamoDB Global Tables |
|---|---|---|---|
| Replication | Storage-level, typically under 1 s lag, up to 10 secondary Regions | Async engine-level | Multi-active, all Regions writable |
| Failover | Managed, about a minute | Manual promotion | No failover needed |
| Exam cue | "Relational, lowest RPO across Regions" | "Cheaper, tolerates more lag" | "Multi-Region writes, NoSQL" |

### EFS vs FSx Family vs EBS
| | EBS | EFS | FSx Windows | FSx Lustre | FSx ONTAP |
|---|---|---|---|---|---|
| Protocol | Block | NFS | SMB, AD integrated | Lustre (HPC) | NFS, SMB, iSCSI |
| Shared | Single instance (Multi-Attach io1/io2 only) | Thousands of Linux clients | Windows clients | HPC clusters, S3-linked | Multi-protocol, NetApp features |

### Security Detection Services ⭐
| Service | Looks at | One-word job |
|---|---|---|
| GuardDuty | CloudTrail, VPC Flow Logs, DNS logs, EKS, S3 events | Threats |
| Inspector | EC2, ECR images, Lambda code | Vulnerabilities (CVEs) |
| Macie | S3 objects | Sensitive data (PII) |
| Detective | Findings plus logs as a graph | Investigation |
| Security Hub | Findings from all of the above plus standards | Aggregation |
| Config | Resource configuration | Compliance |
| CloudTrail | API calls | Audit |

### Shield Standard vs Shield Advanced
| | Standard | Advanced |
|---|---|---|
| Cost | Free, automatic | Monthly subscription per org |
| Layers | 3 and 4 | 3, 4, and 7 (with WAF) |
| Extras | None | Shield Response Team, DDoS cost protection, health-based detection |

### Organizations vs Control Tower
Organizations is the engine (accounts, OUs, SCPs, consolidated billing). Control Tower is the opinionated landing zone built on top (Account Factory, log archive and audit accounts, preventive and detective controls). Exam cue: "set up a governed multi-account environment quickly with best practices" means Control Tower.

### Savings Plans vs Reserved Instances vs Spot
| | Compute SP | EC2 Instance SP | Standard RI | Convertible RI | Spot |
|---|---|---|---|---|---|
| Flexibility | Any family, Region, OS, Fargate, Lambda | Any size and OS within one family and Region | Fixed attributes | Can exchange | Can be interrupted |
| Discount | Up to 66% | Up to 72% | Up to 72% | Lower than Standard (sources quote 54% to 66%) | Up to 90% |
| Exam cue | "Steady spend, changing tech" | "Committed to one family" | "Need capacity reservation (zonal)" | "Might change family" | "Fault-tolerant, stateless, batch" |

---

# Part 3: Keyword Cheatsheet (Scenario Phrase to Answer)

### Hybrid connectivity
| If the scenario says | Think |
|---|---|
| Connect on-prem quickly, encrypted, low cost | Site-to-Site VPN |
| Consistent latency, dedicated bandwidth, large data transfers | Direct Connect |
| DX must be encrypted | MACsec (10/100/400 Gbps dedicated, select locations) or IPsec VPN over DX |
| DX highly resilient | Two DX connections at two different DX locations ("maximum resiliency": 4 connections, 2 locations) |
| Cost-effective DX backup | Site-to-Site VPN as backup to DX |
| On-prem to many VPCs in many Regions over DX | Direct Connect Gateway plus Transit Gateway (transit VIF) |
| VPN bandwidth above 1.25 Gbps | Multiple VPN tunnels with ECMP on Transit Gateway |
| On-prem DNS resolves AWS private names (or reverse) | Route 53 Resolver inbound / outbound endpoints and forwarding rules |
| Share Resolver rules across accounts | AWS RAM |
| Branch offices connect to each other via AWS | VPN CloudHub (VGW) or Transit Gateway |

### Multi-account and governance ⭐
| If the scenario says | Think |
|---|---|
| Prevent all accounts from doing X | SCP |
| No one outside our org can access our resources | Data perimeter: RCPs, `aws:PrincipalOrgID`, VPC endpoint policies |
| New accounts automatically get baseline guardrails | Control Tower Account Factory (or Account Factory for Terraform) |
| Single sign-on to all accounts with corporate IdP | IAM Identity Center with SAML/SCIM |
| Developers create roles but cannot escalate | Permission boundaries |
| Access another account's resources | Cross-account IAM role with `sts:AssumeRole` (plus External ID for third parties) |
| Deploy stack to every account in an OU | CloudFormation StackSets (service-managed) |
| Central security tooling | Delegated administrator for GuardDuty, Security Hub, Config in a security account |
| Share subnets, TGW, or License configs across accounts | AWS RAM |
| Chargeback per team | Cost allocation tags, CUR plus Athena, AWS Budgets |
| Users only launch approved products | Service Catalog |

### Data and analytics ⭐
| If the scenario says | Think |
|---|---|
| Query data in S3 with SQL, no infrastructure | Athena (plus Glue Data Catalog) |
| Column or row level permissions on the data lake | Lake Formation |
| Ingest clickstream into S3 with no code | Data Firehose |
| Real-time analytics over a stream with windows | Managed Service for Apache Flink |
| Existing Hadoop/Spark jobs | EMR |
| Data warehouse, complex joins, BI | Redshift (Spectrum for S3 data) |
| Discover schema automatically | Glue crawler |
| Log search and dashboards | OpenSearch Service |
| BI dashboards for business users | QuickSight |

### Migration
| If the scenario says | Think |
|---|---|
| Discover servers and dependencies first | Application Discovery Service (classic exam answer; closed to new customers since Oct 2025, AWS now points to AWS Transform) |
| Rehost with minimal downtime | Application Migration Service (MGN) |
| Database with minimal downtime | DMS with CDC (plus SCT if engines differ) |
| Large file shares, network available | DataSync |
| Too much data for the network | Snowball Edge for existing customers; new customers use Data Transfer Terminal or partners |
| Keep on-prem apps, back with S3 | Storage Gateway |
| Retire mainframe or legacy batch | Modernize to containers or serverless (Batch, Step Functions) |
| VMware workloads with no change | VMware Cloud on AWS, or MGN |

### Resilience and performance
| If the scenario says | Think |
|---|---|
| Static IPs for global users, fast failover | Global Accelerator |
| DNS failover between Regions | Route 53 failover routing plus health checks |
| Reduce DB read load | Read replicas or ElastiCache |
| Sudden traffic spikes on relational DB | Aurora Serverless v2, RDS Proxy for connection storms |
| Lambda exhausting DB connections | RDS Proxy |
| Decouple and absorb spikes | SQS between tiers |
| Sessions survive instance loss | ElastiCache or DynamoDB for session state |
| Spiky unknown traffic on DynamoDB | On-demand capacity mode |
| Microsecond DynamoDB reads | DAX |

### Security ⭐
| If the scenario says | Think |
|---|---|
| Customer must control and own HSM keys, FIPS 140 Level 3 | CloudHSM (or KMS custom key store) |
| Encrypt at rest with audit of key use | KMS customer managed key plus CloudTrail |
| Share encrypted snapshot or AMI cross-account | Re-encrypt with a CMK and grant the other account in the key policy |
| Block SQLi, XSS, rate limit by IP | WAF |
| Centrally manage WAF rules across accounts | Firewall Manager |
| Inspect east-west and egress traffic | Network Firewall in a centralized inspection VPC |
| Find PII in S3 | Macie |
| SSH/RDP without bastions or open ports | Systems Manager Session Manager |
| Rotate database passwords | Secrets Manager |
| Detect compromised instances | GuardDuty |
| Auto-remediate non-compliant resources | Config rule plus SSM Automation remediation |
| Immutable backups, ransomware protection | AWS Backup Vault Lock, S3 Object Lock (compliance mode) |

### Cost
| If the scenario says | Think |
|---|---|
| Rightsize EC2, Lambda, EBS | Compute Optimizer |
| Steady usage, flexible families | Compute Savings Plans |
| Interruptible batch | Spot (with capacity-optimized allocation) |
| Infrequently accessed S3 with unknown pattern | S3 Intelligent-Tiering |
| Reduce NAT Gateway cost to S3 | S3 Gateway endpoint |
| Cross-AZ data transfer cost high | Keep chatty components in same AZ, or use VPC endpoints |
| Alert or block on overspend | AWS Budgets with Budget Actions |

---

# Part 4: Numbers to Memorize

Verified 13 Oct 2026 against AWS documentation. Rows marked ✅ were checked against AWS documentation or AWS announcements; the few unmarked values are stable, long-standing figures. Exam questions may lag behind recent limit increases, so know both old and new values where shown.

### Snow Family (status changed: read this first) ✅
| Device | Status | Key specs |
|---|---|---|
| Snowcone (8 TB HDD / 14 TB SSD) | Discontinued Nov 2024, support ended Nov 2025 | Older exam questions may still mention it |
| Snowmobile (100 PB) | Retired March 2024 | Classic "exabyte-scale" answer, now gone |
| Snowball Edge Storage Optimized 210 TB | Existing customers only since 7 Nov 2025 | 210 TB NVMe, up to 1.5 GB/s transfer |
| Previous generation (80 TB, 52 vCPU, GPU) | Shut down 12 Nov 2025 | Often quoted in older practice exams |
| Snowball Edge Compute Optimized | Existing customers only since 7 Nov 2025 | 104 vCPUs, 416 GB RAM, 28 TB NVMe |
| Replacements | New customers | DataSync (online), AWS Data Transfer Terminal (physical), Outposts (edge compute) |

Rule of thumb for "network vs device": 1 Gbps moves roughly 10 TB per day at full utilization, so 100 TB takes about 10 days on a saturated 1 Gbps link.

### Networking ✅
| Item | Number |
|---|---|
| Site-to-Site VPN per tunnel | Up to 1.25 Gbps, 2 tunnels per connection |
| Transit Gateway VPC attachment | Up to 100 Gbps per AZ (older material says 50 Gbps) |
| Transit Gateway attachments | 5,000 per TGW |
| TGW Connect (GRE) peer | Up to 5 Gbps, 4 peers per attachment (20 Gbps) |
| Direct Connect dedicated ✅ | 1, 10, 100, 400 Gbps (400 Gbps at select locations) |
| Direct Connect hosted ✅ | 50 Mbps to 25 Gbps (one VIF per hosted connection) |
| Direct Connect LAG ✅ | Up to 4 links below 100 Gbps, or 2 links at 100/400 Gbps |
| VPC and subnet CIDR size ✅ | /16 to /28 |
| Reserved IPs per subnet ✅ | 5 (first four plus the last) |
| Security group rules ✅ | 60 inbound plus 60 outbound by default (adjustable) |

### Compute and serverless ✅
| Item | Number |
|---|---|
| Lambda timeout | 900 s (15 min), cannot be raised |
| Lambda memory | 128 MB to 10,240 MB |
| Lambda /tmp | 512 MB to 10,240 MB |
| Lambda sync payload | 6 MB request and response |
| Lambda async payload | 1 MB (was 256 KB) |
| Lambda scaling | 1,000 execution environments per 10 s per function |
| API Gateway integration timeout | 29 s default; Regional and private REST APIs can request more (up to 5 min) |
| Step Functions Standard ✅ | Up to 1 year duration, exactly-once |
| Step Functions Express ✅ | Up to 5 minutes, at-least-once (async) |

### Messaging and streaming
| Item | Number |
|---|---|
| SQS message size ✅ | 1 MiB (was 256 KiB until Aug 2025; Extended Client Library with S3 for larger) |
| SQS retention ✅ | Up to 14 days (default 4 days) |
| SQS visibility timeout ✅ | Up to 12 h (default 30 s) |
| SQS delay / long poll | Delay up to 15 min ✅; long poll up to 20 s |
| SQS FIFO ✅ | 300 TPS per API action, 3,000 msg/s with batching; high-throughput mode up to 70,000 TPS in the largest Regions |
| Kinesis shard ✅ | 1 MB/s or 1,000 records/s in, 2 MB/s out (enhanced fan-out 2 MB/s per consumer) |
| Kinesis retention ✅ | 24 h default, up to 365 days |
| Firehose buffer | Delivers on size or time interval, whichever first (near real time) |

### Storage
| Item | Number |
|---|---|
| S3 object max ✅ | 50 TB since Dec 2025 (was 5 TB; older questions use 5 TB); single PUT 5 GB; use multipart above 100 MB |
| S3 request rate ✅ | At least 3,500 PUT/COPY/POST/DELETE and 5,500 GET/HEAD per second per prefix |
| S3 durability | 11 nines |
| Glacier Instant Retrieval ✅ | Milliseconds |
| Glacier Flexible Retrieval ✅ | Expedited 1 to 5 min, Standard 3 to 5 h, Bulk 5 to 12 h (free) |
| Glacier Deep Archive ✅ | Standard within 12 h, Bulk within 48 h |
| Minimum storage duration ✅ | Standard-IA / One Zone-IA 30 days, Glacier IR and Flexible 90 days, Deep Archive 180 days |
| EBS io2 Block Express ✅ | Up to 256,000 IOPS, 4,000 MB/s, 64 TiB; Multi-Attach to up to 16 Nitro instances |
| EBS gp3 ✅ | 3,000 IOPS and 125 MiB/s baseline at any size; now up to 80,000 IOPS and 2,000 MB/s (older material says 16,000 and 1,000) |

### Database
| Item | Number |
|---|---|
| Aurora ✅ | 6 copies across 3 AZs, up to 15 replicas |
| Aurora Global Database ✅ | Typically under 1 s lag, up to 10 secondary Regions (was 5 until May 2025); primary readers plus secondary clusters cannot exceed 15 |
| RDS Multi-AZ | Synchronous standby, automatic failover typically 60 to 120 s (Multi-AZ DB cluster: typically under 35 s) |
| RDS read replicas ✅ | Up to 15 per source (MySQL, MariaDB, PostgreSQL); 5 for Oracle and SQL Server; 3 for Db2 |
| DynamoDB item size ✅ | 400 KB (attribute names count) |
| DynamoDB PITR ✅ | 1 to 35 days, configurable per table (default 35) |
| RDS / Aurora automated backups ✅ | Up to 35 days retention |
| ElastiCache | Redis/Valkey for persistence and replication; Memcached for simple multithreaded cache |

### Identity and security ⭐
| Item | Number |
|---|---|
| IAM role session ✅ | 15 min to the role's maximum (1 h to 12 h); role chaining capped at 1 h |
| SCPs ✅ | Up to 10 attached per root, OU, or account; 10,240 characters each (raised from 5 and 5,120 in May 2026, so older questions use the old values) |
| KMS Encrypt API ✅ | Up to 4,096 bytes with a symmetric key; larger data uses envelope encryption with data keys |
| KMS key deletion ✅ | 7 to 30 day waiting period (default 30) |
| CloudTrail ✅ | 90 days of management events in free Event history; use a trail to S3 for longer retention |
| Config | Continuous recording; aggregator for multi-account, multi-Region view |

---

## Sources
- [SAP-C02 In-Scope AWS Services](https://docs.aws.amazon.com/aws-certification/latest/solutions-architect-professional-02/sap-02-in-scope-services.html)
- [AWS Snowball Edge availability change](https://docs.aws.amazon.com/snowball/latest/developer-guide/snowball-edge-availability-change.html) and [device specifications](https://docs.aws.amazon.com/snowball/latest/developer-guide/device-differences.html)
- [AWS Snow device updates (Storage Blog)](https://aws.amazon.com/blogs/storage/aws-snow-device-updates)
- [Transit Gateway quotas](https://docs.aws.amazon.com/vpc/latest/tgw/transit-gateway-quotas)
- [Lambda quotas](https://docs.aws.amazon.com/lambda/latest/dg/gettingstarted-limits.html)
- [SQS 1 MiB payload announcement](https://aws.amazon.com/about-aws/whats-new/2025/08/amazon-sqs-max-payload-size-1mib)
- [API Gateway timeout beyond 29 s](https://aws.amazon.com/about-aws/whats-new/2024/06/amazon-api-gateway-integration-timeout-limit-29-seconds/)
- AWS Lifecycle Changes: [Maintenance](https://docs.aws.amazon.com/general/latest/gr/maintenance_services.html), [Sunset](https://docs.aws.amazon.com/general/latest/gr/sunset_services.html), [Full Shutdown](https://docs.aws.amazon.com/general/latest/gr/full_shutdown_services.html)
- [Aurora Global Database: 10 secondary Regions](https://aws.amazon.com/about-aws/whats-new/2025/05/amazon-aurora-global-database-support-10-secondary-region-clusters/)
- [Direct Connect features](https://aws.amazon.com/directconnect/features/)
- [S3 maximum object size 50 TB](https://aws.amazon.com/about-aws/whats-new/2025/12/amazon-s3-maximum-object-size-50-tb/)
- [AWS Organizations quotas](https://docs.aws.amazon.com/general/latest/gr/ao.html) and [higher SCP quotas (May 2026)](https://aws.amazon.com/de/about-aws/whats-new/2026/05/aws-organizations-increased-scp-quotas/)
- [SQS message quotas](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/quotas-messages.html), [Kinesis quotas](https://docs.aws.amazon.com/streams/latest/dev/service-sizes-and-limits.html), [EBS volume types](https://aws.amazon.com/ebs/volume-types/), [VPC quotas](https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Appendix_Limits.html)

AWS raises limits often (several changed in 2025 and 2026), so confirm any number before you rely on it in a real design.
