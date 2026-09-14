# Deployment Status — CalcSuite

**Last Updated:** 2026-09-14
**Status:** BLOCKED — Awaiting Human Action

## Summary

The CalcSuite calculator platform is code-complete and build-passing. Production deployment is blocked on external account creation that requires human action.

## What's Ready

- Next.js 15 app with 10 calculators
- Production build passing (40+ static pages)
- 19 unit tests passing
- `vercel.json` configured
- `.env.example` with all required variables
- Code committed to git (branch `master`)

## Blockers

See: [[WOR-1730]] — Create deployment prerequisites (GitHub, Vercel, Domains, Credentials)

### Required Human Actions

1. **Create GitHub repo** `paperclipai/calculator`
2. **Create Vercel account + project**
3. **Purchase domains** — `calculators.com` + `calculators.co.uk`
4. **Create Cloudflare account** — For DNS + CDN + SSL
5. **Provide credentials** — Database, Stripe, SMTP, NextAuth secret

## Deployment Steps (Once Unblocked)

1. Push code to new GitHub repo
2. Import project in Vercel
3. Set environment variables
4. Add domains → auto SSL
5. Configure DNS

## Related

- [[WOR-1724]] — Deploy to production (Vercel + custom domains)
- [[WOR-1706]] — Technical Architecture & MVP Calculator Build
- [[WOR-1708]] — Infrastructure, Deployment & DevOps Pipeline
- [[CalcSuite-README]] — Project overview
- [[CalcSuite-ARCHITECTURE]] — Technical architecture
