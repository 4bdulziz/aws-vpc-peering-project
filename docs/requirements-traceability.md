# Evidence and verification notes

This document summarizes evidence coverage without a separate pass/fail requirements matrix.

## Screenshot-supported observations

- **E01:** SSH login to the bastion succeeded; Amazon Linux 2023 prompt identifies the host as `10.10.1.10`.
- **E02:** SSH to App-A through the bastion succeeded; App-A reports `10.10.2.10/24`.
- **E03:** SSH to App-B through the bastion succeeded; App-B pinged App-A with 4 replies and 0% loss.
- **E04:** App-A's ping to App-B returned 100% packet loss during the controlled failure.
- **E05–E07:** The EC2 inventory shows the bastion and two private application instances; App-A and App-B have no public IPv4 address.
- **E08:** The project Internet Gateway was attached to VPC A.
- **E09:** The public route table and explicit public-subnet association are shown; its Routes tab was not captured.
- **E10–E11:** Both private-subnet route tables show the local route and the peering route, Active.
- **E12:** The VPC peering connection was Active at capture time.
- **E13:** App-A's inbound rules show SSH from the bastion private IP and All ICMP from App-B.

## Reported outcomes and actions

The project record reports successful App-A-to-App-B ping, restoration of connectivity after the App-B ICMP rule was restored, and cleanup of the project resources. The supplied screenshot set does not independently show those outcomes/actions. It also does not include the pre-peering baseline ping, the public route-table Routes tab, or complete inbound-rule captures for every security group.

The report distinguishes screenshot-supported observations from reported results. No screenshots or AWS states have been reconstructed.
