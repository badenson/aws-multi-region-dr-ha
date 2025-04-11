# 🌍 AWS Multi-Region Disaster Recovery & High Availability Architecture

**Enterprise-grade resilience for your cloud workloads**  
*Automated failover, zero-data-loss recovery, and cross-region redundancy using native AWS services*

[![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?logo=amazon-aws&logoColor=white)](https://aws.amazon.com)
[![Terraform](https://img.shields.io/badge/Terraform-7B42BC?logo=terraform&logoColor=white)](https://www.terraform.io)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/badenson/aws-multi-region-dr-ha/graphs/commit-activity)

## 🚀 Key Features

- **Multi-Region Active/Passive DR** - RTO < 15 minutes, RPO ≈ 0  
- **Automated Failover** - Route 53 health checks + Lambda orchestration  
- **Data Synchronization** - Cross-region replication for:
  - **Databases** (Aurora Global Database, DynamoDB Global Tables)
  - **Storage** (S3 CRR, EBS Snapshots)
  - **Configuration** (Parameter Store Cross-Region replication)
- **Cost-Optimized** - Minimal passive-region footprint with auto-scaling triggers
- **Compliance-Ready** - Pre-configured for HIPAA, PCI DSS, and GDPR

## 📊 Architecture Diagram
![DR Architecture](https://github.com/badenson/aws-multi-region-dr-ha/raw/main/docs/architecture.png?raw=true)
*Fig 1. Active-Passive deployment with automated failover triggers*

## 🛠️ How It Works

1. **Continuous Replication**:  
   - Database: Aurora Global Database (1-2 sec replication lag)  
   - Storage: S3 Cross-Region Replication (CRR) with 15-minute SLA  
   - Configuration: SSM Parameter Store → DR region every 5 minutes

2. **Health Monitoring**:  
   - CloudWatch Synthetic Canaries test endpoint availability  
   - Regional health dashboards with anomaly detection

3. **Failover Automation**:  
   ```mermaid
   graph TD
     A[Region Failure Detected] --> B[EventBridge Event]
     B --> C[Lambda: Validate Failure]
     C --> D[Promote Standby RDS]
     D --> E[Update Route53 Weighting]
     E --> F[Scale DR ASGs to 100%]



# AWS Multi-Region Disaster Recovery & High Availability

![AWS](https://img.shields.io/badge/AWS-Cloud-blue?logo=amazon-aws)
![CFN](https://img.shields.io/badge/IaC-CloudFormation-orange)

A **production-grade** disaster recovery (DR) and high availability (HA) setup using:
- **Route 53** (DNS failover)
- **AWS Global Accelerator** (low-latency routing)
- **RDS Multi-AZ** (automatic failover)
- **S3 Cross-Region Replication (CRR)** (data redundancy)
- **CloudFormation** (Infrastructure as Code)

## **Architecture**
![DR Architecture](./docs/architecture/dr-architecture.png)

## **Features**
✅ **Automatic failover** (Route 53 health checks)  
✅ **Cross-region replication** (S3 CRR, RDS read replicas)  
✅ **Low-latency routing** (Global Accelerator)  
✅ **Automated recovery plans** (CloudFormation + Lambda)  

## **Deployment**
```bash
./scripts/deploy.sh

