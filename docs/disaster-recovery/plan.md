# Disaster Recovery Plan

## **Automatic Failover Triggers**
1. **Route 53 Health Checks** → Failover if primary region is unhealthy.
2. **RDS Multi-AZ** → Automatic primary-replica switch.
3. **S3 CRR** → Data syncs to secondary region in near real-time.

## **Manual Failover Steps**
1. **Promote RDS Read Replica** (in secondary region):
   ```sql
   CALL mysql.rds_promote_read_replica;