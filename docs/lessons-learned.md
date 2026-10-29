# Lessons learned

1. **Peering is a link, not a merge.** Both VPCs need a route to the other's CIDR, and the destination needs a permitting security-group rule.
2. **Longest-prefix match decides.** In the public route table 10.20.0.0/16 -> peering wins over 0.0.0.0/0 -> IGW for traffic to VPC B.
3. **Security groups are stateful.** An inbound rule matters for the side that *starts* the connection; replies are allowed automatically. App-A's ICMP rule governs pings that App-B starts.
4. **Active is not reachable.** The controlled failure (E04) showed that an Active peering plus routes does not deliver traffic without the destination rule.
5. **Bastions keep servers private.** Private instances were administered with no public IPv4; the proxied SSH source is the bastion's private IP.
6. **A single immediate failure after a change is not conclusive.** Retest before drawing conclusions.
7. **Capture evidence at each checkpoint.** The baseline, forward-success, recovery and cleanup captures were not available, which left four requirements below PASS.
8. **Clean up after evidence.** Instances and public IPv4 addresses incur cost; delete in dependency order (instances, peering routes and peering, subnets and route tables, IGW, VPCs).
