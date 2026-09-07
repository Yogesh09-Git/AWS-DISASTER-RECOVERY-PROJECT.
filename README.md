AWS Multi-Region Disaster Recovery Project

Project Overview

This project demonstrates a multi-region disaster recovery architecture on AWS. The primary application runs in the Mumbai region, while the Singapore region is configured as the disaster recovery environment.

AWS Services Used

- Amazon VPC
- Amazon EC2
- Amazon RDS
- Amazon Route 53
- AWS Security Groups
- Amazon RDS Read Replica

Architecture

The project uses two AWS regions:

Primary Region — Mumbai

- EC2 Web Server
- MySQL RDS Database
- VPC with public and private subnets

Disaster Recovery Region — Singapore

- EC2 DR Web Server
- RDS Read Replica
- Route 53 Failover

Disaster Recovery Flow

1. Users access the application through Route 53.
2. Route 53 checks the health of the primary Mumbai server.
3. Under normal conditions, traffic goes to the Mumbai EC2 server.
4. The Mumbai RDS database replicates data to the Singapore RDS Read Replica.
5. If the Mumbai server becomes unavailable, Route 53 redirects traffic to the Singapore DR server.
6. The Singapore RDS Read Replica can be promoted to a standalone database during a disaster.

Regions

Region| Purpose
Mumbai (ap-south-1)| Primary
Singapore (ap-southeast-1)| Disaster Recovery

Disaster Recovery Features

- Multi-region architecture
- EC2-based web servers
- RDS database replication
- Route 53 health checks
- DNS failover
- Backup disaster recovery environment

Project Result

The project demonstrates how an application can continue operating from a secondary AWS region when the primary region/server becomes unavailable.

Conclusion

This project provides a basic multi-region disaster recovery solution using AWS services. It improves application availability and helps reduce downtime during a failure.
