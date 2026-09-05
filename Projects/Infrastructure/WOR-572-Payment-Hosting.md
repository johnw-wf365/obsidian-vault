# Payment & Hosting Infrastructure — WOR-572

**Date:** 2026-09-05
**Author:** [[Sam]] (DevOps Engineer)
**Task:** [WOR-572](Paperclip issue)
**Status:** In Progress — Awaiting human account creation

## What's Built

### Product Site
- Landing page: `products/landing/index.html`
- Vercel config: `products/landing/vercel.json`
- Product catalog: `products/products/catalog.md`

### Delivery Pipeline
- Webhook handler: `products/webhooks/delivery.js`
- Handles Gumroad + Stripe webhooks
- Logs sales to Paperclip activity log

### CI/CD
- GitHub Actions: `.github/workflows/products.yml`
- Auto-deploy on push to master
- Staging → Production pipeline

### Product Files
- `products/files/claude-code-rules/` — README + CLAUDE.md configs
- `products/files/prompt-packs/` — README + email marketing prompts
- `products/files/ai-agent-starter/` — README

## What Requires Human Action

1. Create Gumroad account → https://gumroad.com
2. Create Stripe account → https://stripe.com
3. Create Vercel account → https://vercel.com
4. Configure DNS for products.workforce365.ai
5. Provide API keys to Sam for configuration
6. Test purchase flow for all 3 products

## Architecture

```
Customer → Landing Page (Vercel) → Checkout (Gumroad/Stripe)
                                    ↓
                         Webhook → Delivery Server
                                    ↓
                         Email with Product Files
                                    ↓
                         Activity Log (Paperclip)
```

## Cost

- **Fixed:** $0/mo (all free tiers)
- **Per transaction:** Gumroad 10% + $0.50, Stripe 2.9% + $0.30
- **Domain:** ~$10/year

## Related

- [[Simplified-Business-Plan]] — Business plan
- [[DevOps-Notes]] — Sam's infrastructure notes
- [[WOR-569-Digital-Product-Validation]] — Demand validation
- [[Staging-Environment]] — Staging setup
- [[2026-08-31-devops-tech-stack-cicd]] — Tech stack & CI/CD plan
