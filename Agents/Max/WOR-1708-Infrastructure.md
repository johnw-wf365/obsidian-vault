# WOR-1708: Infrastructure, Deployment & DevOps Pipeline

**Status:** in_review (infrastructure code committed, awaiting human blockers)
**Agent:** [[Max]] (Cloud Ops Engineer)
**Date:** 2026-09-14
**Commit:** bfc9f920f

## Overview

Infrastructure for WorkForce365.ai calculator platform targeting US, UK, CA, AU markets.

**Budget:** Under £100/mo — **Estimated: ~£28/mo**

## Architecture

- **CDN/DNS/SSL:** Cloudflare Free Tier
- **Production:** UpCloud 2xCPU-4GB (~£18/mo)
- **Staging:** UpCloud 1xCPU-2GB (~£10/mo)
- **Database:** Self-hosted PostgreSQL on production server
- **CI/CD:** GitHub Actions (free tier)
- **Monitoring:** Netdata + UptimeRobot + Sentry (all free tiers)

## Files Created

All in `infrastructure/calculator/`:

```
├── README.md, rollout-plan.md
├── terraform/ (8 files)
│   ├── provider.tf, variables.tf, networking.tf
│   ├── production.tf, staging.tf, main.tf
│   ├── cloud-init.yml, outputs.tf
├── github-actions/
│   ├── ci.yml, deploy-staging.yml, deploy-prod.yml
├── monitoring/
│   ├── nginx-security.conf, uptime-robot.json
│   ├── netdata.conf.md, alerts.yml
└── scripts/
    ├── setup-server.sh, deploy.sh, rollback.sh
    ├── health-check.sh, ecosystem.config.cjs
```

## Blockers — Human Action Required

1. UpCloud API credentials
2. Domain purchase (.com, .co.uk)
3. Cloudflare account
4. GitHub repo for calculator code
5. Sentry account

## Related Issues

- [[WOR-1703]] — Parent: Company Direction Change
- [[WOR-1709]] — DevOps: CI/CD Pipeline (Sam)
- [[WOR-1718]] — Create GitHub Repo (done)

## Notes

- Issue moved to `in_review` with pending `ask_user_questions` interaction
- Push to origin failed (credentials) — local commit bfc9f920f is safe
- Once blockers cleared, will provision via Terraform
