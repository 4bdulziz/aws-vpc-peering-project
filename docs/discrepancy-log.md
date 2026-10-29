# Discrepancy log

Source hierarchy used: EWB brief > screenshots > draft report > supplied diagram > AWS documentation.

| # | Where | Conflicting claim | Strongest evidence | Resolution |
|---|---|---|---|---|
| D1 | Original diagram vs screenshots | Original diagram lists VPC A/B as vpc-0a1234567890abcd / vpc-00cbf775f9bd43383; peering pcx-0abc1234; IGW igw-0def5678; placeholder subnet and instance IDs | Screenshots show vpc-0e2bca34602e78401, vpc-055190c346eacb6e2, pcx-029955b9450e10c12, igw-08dc44b91e4be2768 and the subnet/instance IDs in the inventory. vpc-00cbf775f9bd43383 is the default VPC | Resolved: original diagram not used; new diagram built from screenshot values |
| D2 | Original diagram vs brief/draft | Original shows ewb-sg-bastion SSH from 0.0.0.0/0 | Brief requires your /32; draft records admin IPv4 (redacted)/32 | Resolved in favour of brief/draft; bastion rule remains unverified by screenshot |
| D3 | Original diagram | Shows 0.0.0.0/0 '(No route)' row in rt-b-private and omits ewb-rt-a-private; private subnet IDs differ from the screenshots | E10/E11/E06/E07 | Resolved: corrected in new diagram |
| D4 | Draft report section 7 | States App-A's SG ICMP rule permits the return path of the A-to-B ping | Security groups are stateful; replies to permitted traffic are allowed automatically (brief p.6). App-A's ICMP rule governs pings that App-B initiates | Resolved: explanation corrected |
| D5 | Draft report | Marks forward ping, recovery and controlled failure as 'screenshot saved by user' | Only the failure (E04) and the reverse ping (E03) were supplied | Unresolved: forward-ping and recovery screenshots missing |
| D6 | Draft report | Cleanup 'pending'; instances running | Author now reports all cleanup done | Unresolved: no cleanup evidence; report states cleanup as reported |
| D7 | Brief p.6 vs screenshot E13 | Brief specifies Custom ICMP IPv4 Echo request (type 8) | E13 shows 'All ICMP - IPv4' (ICMP, All) scoped to a /32 | Open deviation: broader ICMP type than the brief; still restricted to one source host |
| D8 | Brief p.8 vs evidence | Brief shows SSH config with ProxyJump | Screenshots use ssh -o ProxyCommand=... -W %h:%p | Resolved: functionally equivalent bastion hop; ProxyCommand documented |
| D9 | File name rt-a-public_routes.png | Name implies a Routes tab | Image shows the Details tab only | Resolved: renamed E09 ..._details-tab; public routes marked unverified |
| D10 | Brief p.2 baseline | Requires a failed test before peering | No baseline capture supplied | Unresolved: requirement not captured |
| D11 | Draft: 'Last updated' / date | Draft says completion pending | E04 shows 'Last login Sat Oct 24 11:50:04 2026' from the instance clock | Resolved: testing date 24 Oct 2026 (instance clock, time zone not shown); completion/cleanup date not evidenced |
| D12 | Screenshots E08-E13 | Lists include default-VPC IGW, route tables and security groups | These are not project resources | Resolved: excluded from the project inventory; listed separately |
