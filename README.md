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

