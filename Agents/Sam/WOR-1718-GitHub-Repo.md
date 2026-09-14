# WOR-1718 — Create GitHub Repo: paperclipai/calculator

**Status:** Done
**Date:** 2026-09-14
**Assignee:** Sam (DevOps)

## Summary

Created GitHub repo for calculator platform and pushed initial scaffolding.

## Repo

- **URL:** https://github.com/johnw-wf365/calculator
- **Visibility:** Private
- **Branch:** main (protected)

## What was pushed

- CI/CD workflows (lint, typecheck, test, build)
- Staging + production deployment workflows
- Dockerfile
- nginx.conf (security headers, SSL, rate limiting)
- Terraform configs (UpCloud)
- Deployment scripts (deploy, rollback, setup-server, health-check)
- CI/CD documentation
- package.json, .env.example, .gitignore

## Branch Protection

- Required status checks: lint, typecheck, test, build
- Required PR reviews: 1
- Stale review dismissal: enabled

## Blockers / Notes

- Repo is under `johnw-wf365` user account, NOT `paperclipai` org
- Transfer to org blocked: org has permission restrictions
- Agents don't have GitHub accounts — access is via Paperclip
- GitHub Actions secrets still need to be configured

## Related

- [[WOR-1709]] — CI/CD Pipeline & Deployment Automation (parent)
- [[WOR-1708]] — Infrastructure (Max)
