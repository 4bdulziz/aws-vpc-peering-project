# Cleanup record

The author reports that the project EC2 instances were terminated and the project subnets, VPC peering connection, Internet Gateway, and VPCs were deleted after evidence collection. No cleanup screenshots were supplied, so these final actions are documented as reported rather than independently verified.

| Resource | Reported final state |
|---|---|
| `ewb-bastion`, `ewb-app-a`, `ewb-app-b` | Terminated |
| `ewb-a-public`, `ewb-a-private`, `ewb-b-private` | Deleted |
| `ewb-a-b-peer` / `pcx-029955b9450e10c12` | Deleted |
| `ewb-igw-a` / `igw-08dc44b91e4be2768` | Deleted |
| `ewb-vpc-a`, `ewb-vpc-b` | Deleted |
| Custom route tables and security groups | Reported removed with their VPCs |
| Key pair, EBS volumes, Elastic IPs, tags | Final state not established in the project record |

The architecture is historical documentation, not a currently deployed environment.
