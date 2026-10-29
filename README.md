# AWS VPC Peering Project

**Author:** Abdul Aziz  
**Batch:** EWB AWS Cloud computing Internship — Batch 1  
**Region:** Asia Pacific (Mumbai), `ap-south-1`  
**Submission date:** 27/10/26

## Project brief

This project connects two non-overlapping AWS VPCs using VPC peering. App-A and App-B remain on private IPv4 addresses. A public bastion in VPC A provides SSH administration.

## Architecture

![AWS VPC peering architecture](architecture/architecture.png)

- [Architecture diagram (SVG)](architecture/architecture.svg)
- [Traffic-flow diagram (PNG)](architecture/traffic-flow.png)
- [Traffic-flow source (Mermaid)](diagrams/traffic-flow.mmd)

| Resource | CIDR / address |
|---|---|
| VPC A (`ewb-vpc-a`) | `10.10.0.0/16` |
| Public subnet (`ewb-a-public`) | `10.10.1.0/24` |
| Private subnet A (`ewb-a-private`) | `10.10.2.0/24` |
| VPC B (`ewb-vpc-b`) | `10.20.0.0/16` |
| Private subnet B (`ewb-b-private`) | `10.20.1.0/24` |
| Bastion (`ewb-bastion`) | `10.10.1.10` + public IPv4 |
| App-A (`ewb-app-a`) | `10.10.2.10`, no public IPv4 |
| App-B (`ewb-app-b`) | `10.20.1.10`, no public IPv4 |

## What was configured

- Two VPCs and three subnets with explicit route-table associations.
- One Internet Gateway attached to VPC A.
- VPC peering and routes in both directions.
- Security groups restricting SSH and ICMP to the lab hosts.
- Bastion-based SSH access to private instances.

## Evidence

The `evidence/` folder contains the available console and terminal screenshots. See [Evidence notes](evidence/README.md) and [test results](docs/test-results.md) for what the screenshots support and what was reported but not independently captured.

## Repository contents

- `architecture/` — diagrams
- `evidence/` — screenshots used in the report
- `inventory/` — historical resource, subnet, route-table and security-group records
- `docs/` — test results, troubleshooting and verification notes
- `cleanup/` — cleanup record

## Status and safety

This is a historical lab report, not a live deployment. The AWS resources were reported as cleaned up after testing; cleanup was not independently verified by a screenshot. Do not upload private keys, credentials, or access tokens. Check the AWS console and Billing before assuming all chargeable resources are gone.
