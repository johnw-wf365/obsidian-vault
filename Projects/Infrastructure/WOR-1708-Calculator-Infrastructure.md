# WOR-1708 — Infrastructure, Deployment & DevOps Pipeline

**Date:** 2026-09-14
**Author:** Max (Cloud Ops Engineer)
**Status:** In Review — Awaiting Plan Approval

## Summary

Complete infrastructure plan for the WorkForce365.ai calculator platform targeting US, UK, CA, AU markets with £100/mo budget cap.

**Estimated monthly cost: ~£28** (well under budget)

## Architecture

- **CDN/DNS/SSL:** Cloudflare Free Tier
- **Production:** UpCloud 2xCPU-4GB (~£18/mo)
- **Staging:** UpCloud 1xCPU-2GB (~£10/mo)
- **Database:** Self-hosted PostgreSQL on production server (free)
- **CI/CD:** GitHub Actions (free tier)
- **Monitoring:** Netdata + UptimeRobot + Sentry (all free tiers)

## Deliverables Completed

### 1. Infrastructure Setup
- Cloud hosting plan (UpCloud)
- DNS configuration (Cloudflare)
- CDN setup (Cloudflare)
- SSL certificates & security headers (Cloudflare Origin CA + Nginx hardening)
- Database provisioning (PostgreSQL)

### 2. CI/CD Pipeline
- GitHub Actions CI workflow (typecheck, test, build on PR)
- Staging deployment (auto-deploy main branch)
- Production deployment (tag-based with rollback)
- Rollback procedures (automated + manual script)

### 3. Monitoring & Alerting
- Uptime monitoring (UptimeRobot free — 50 monitors)
- Error tracking (Sentry free — 5k events/mo)
- Performance monitoring (Netdata self-hosted)
- Security monitoring (Fail2ban + UFW)

### 4. Scaling Plan
- Phase 1: Single server, self-hosted (current)
- Phase 2: Separate DB server
- Phase 3: Horizontal scaling with load balancer
- Phase 4: Multi-region (CA, AU)

## Files Created

```
infrastructure/calculator/
├── README.md                 # Architecture overview
├── rollout-plan.md           # Step-by-step rollout
├── terraform/
│   ├── main.tf               # UpCloud resources
│   └── cloud-init.yml        # Server bootstrap
├── github-actions/
│   ├── ci.yml                # PR validation
│   ├── deploy-staging.yml    # Staging deploy
│   └── deploy-prod.yml       # Production deploy + rollback
├── monitoring/
│   └── nginx-security.conf   # Security headers + SSL
└── scripts/
    ├── setup-server.sh       # Initial server setup
    ├── deploy.sh             # Deployment script
    └── rollback.sh           # Rollback script
```

## Blockers — Human Action Required

| Blocker | Owner | Action |
|---------|-------|--------|
| UpCloud API credentials | Human | Create account, provide API access |
| Domains (.com, .co.uk) | Human | Purchase domains |
| Cloudflare account | Human | Create account, set up zones |
| GitHub repo for calculator | Human | Create repo, add Secrets |
| Sentry account | Human | Create org, provide DSN |

## Cost Breakdown (Monthly)

| Service | Cost |
|---------|------|
| Production Server (2xCPU-4GB) | ~£18 |
| Staging Server (1xCPU-2GB) | ~£10 |
| PostgreSQL | £0 (self-hosted) |
| Cloudflare CDN + SSL | £0 |
| GitHub Actions | £0 |
| UptimeRobot | £0 |
| Sentry | £0 |
| **Total** | **~£28/mo** |

## Related

- [[WOR-1703]] — Company Direction Change (parent issue)
- [[Infrastructure-Overview]] — Current infrastructure
- [[Max]] — Max's profile
