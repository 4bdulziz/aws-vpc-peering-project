# Troubleshooting notes

## Ping fails while peering is Active

An Active peering connection only confirms that the connection exists. Check, in order:

1. The source subnet's associated route table has a route to the peer CIDR via the peering connection.
2. The destination VPC has a return route to the source CIDR.
3. The destination instance security group allows the initiating protocol from the correct source IP.
4. The target private IP is correct and the host is running.

The controlled test reported that App-B's inbound ICMP rule was temporarily removed; E04 shows the resulting App-A-to-App-B ping failure. The rule removal itself was not captured.

## Immediate retry after restoring a rule

The project record says the first ping after restoring the rule failed, while a later retry succeeded. A brief propagation delay is plausible but was not measured, so it remains an explanation rather than a confirmed cause.

## SSH through the bastion

The bastion initiates the onward SSH connection. Private instances therefore see the bastion's private IP (`10.10.1.10`) as the SSH source. Keep private keys on the administrator's workstation and do not copy them to the bastion or application instances.
