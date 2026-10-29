# Connectivity test results

| Test | Result | Evidence basis |
|---|---|---|
| SSH to bastion | Successful | E01 |
| SSH to App-A through bastion | Successful | E02 |
| Baseline ping before peering | Expected to fail because no peering path/route existed | Not captured |
| App-A → App-B ping | 4/4 replies, 0% loss reported | Terminal screenshot not supplied |
| App-B → App-A ping | 4 transmitted, 4 received, 0% loss | E03 |
| SSH to App-B through bastion | Successful | E03 |
| Private-only application instances | No public IPv4 address shown for App-A and App-B | E06–E07 |
| Controlled App-A → App-B ICMP failure | 4 transmitted, 0 received, 100% loss; ICMP-rule removal reported | E04 shows failure output, not the console edit |
| Recovery after restoring ICMP | A later retry reportedly succeeded after an immediate retry failed | No screenshot supplied |
| Cleanup | Project resources reported terminated/deleted | No cleanup screenshots supplied |

A successful ping confirms reachability for that direction at the time of the test. It does not independently verify every route or security-group rule.
