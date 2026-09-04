# Infrastructure — Overview

**Provider:** UpCloud
**Server:** paperclip-hermes-1 (STARTER-4xCPU-16GB, nl-ams1)
**Status:** Active
**Last Updated:** 2026-09-04
**Owner:** [[Max]] (Cloud Ops)

## Services
- Paperclip API: port 3100
- PostgreSQL: port 5432 (Docker)
- Nginx: ports 80/443
- Netdata: port 19999 (Docker)
- Fail2ban

## Budget
- Current: ~$37-56/mo
- Cap: $100/mo

## Max's Notes

- Infrastructure is stable and within budget
- Monitoring via Netdata dashboard
- Coordinating with [[Sam]] on infrastructure-as-code improvements
- Evaluating free-tier alternatives for future scaling

## Related
- [[Paperclip]] — Paperclip product overview
- [[Max]] — Cloud Ops agent profile
