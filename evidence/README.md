# Evidence index

The files below are the supplied AWS console screenshots, replacing the earlier cropped/redacted copies. The console header is kept visible for verification, including the signed-in name **Abdul Aziz**, AWS account ID **696504865937**, and Region **Asia Pacific (Mumbai) / ap-south-1**. Public IPs shown in the supplied screenshots are retained as captured. Evidence identifiers E01–E13 map screenshots to the report.

| ID | File | What it supports | Notes |
|---|---|---|---|
| E01 | [Bastion SSH login](connectivity/E01_bastion_ssh_login.png) | Successful SSH login to the bastion; Amazon Linux 2023 | Workstation command line is masked; key contents were not present. |
| E02 | [App-A SSH via bastion](connectivity/E02_app-a_ssh_via_bastion.png) | SSH to App-A and its private address | Local path/username fragments are masked. |
| E03 | [App-B SSH and ping to App-A](connectivity/E03_app-b_ssh_via_bastion_and_ping_to_app-a.png) | SSH to App-B and 4/4 ping replies from App-B to App-A | No timestamp visible. |
| E04 | [Controlled ICMP failure](failure-recovery/E04_app-a_ping_to_app-b_100pct_loss.png) | App-A ping to App-B: 100% loss | Rule removal is reported, not shown. |
| E05 | [Bastion instance details](compute/E05_ec2_ewb-bastion_details.png) | Bastion instance inventory and private address | Public IPv4 address, signed-in name, AWS account ID, and Mumbai Region visible in the full console capture. |
| E06 | [App-A instance details](compute/E06_ec2_ewb-app-a_details.png) | App-A has no public IPv4 address | Signed-in name, AWS account ID, and Mumbai Region visible in the full console capture. |
| E07 | [App-B instance details](compute/E07_ec2_ewb-app-b_details.png) | App-B has no public IPv4 address | Signed-in name, AWS account ID, and Mumbai Region visible in the full console capture. |
| E08 | [Internet Gateway](networking/E08_internet_gateway_ewb-igw-a.png) | Project IGW attached to VPC A | Signed-in name, AWS account ID, and Mumbai Region visible in the full console capture. |
| E09 | [Public route-table details](networking/E09_route_table_ewb-rt-a-public_details-tab.png) | Public route table and subnet association | Routes tab not captured. |
| E10 | [App-A private route table](networking/E10_route_table_ewb-rt-a-private_routes.png) | Local and peering routes in VPC A private table | Subnet association ID is truncated in source capture. |
| E11 | [App-B private route table](networking/E11_route_table_ewb-rt-b-private_routes.png) | Local and return peering routes in VPC B private table | Subnet association ID is truncated in source capture. |
| E12 | [VPC peering Active](networking/E12_vpc_peering_ewb-a-b-peer_active.png) | Peering connection ID, VPCs and Active status | Signed-in name, AWS account ID, and Mumbai Region visible; status is at capture time only. |
| E13 | [App-A inbound rules](security/E13_sg_ewb-sg-app-a_inbound_rules.png) | App-A SSH and ICMP inbound rules | Does not show inbound rules for all other security groups. |
