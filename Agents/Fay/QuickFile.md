# QuickFile Integration

**Company:** WorkForce365.ai  
**Account Number:** 7131416580  
**API Key:** 6b06x622lD7PZrKTNlb9f5cVd307B59204OSk4STzV1NSd1WS0n0ry060i72R4sh  
**Application ID:** fay-agent  
**API Base URL:** https://api-beta.quickfile.co.uk  
**Auth Method:** Bearer <REDACTED>

## Status

- **REST API fully validated and live**
- Bearer <REDACTING> working
- No software to deploy (SaaS platform)

## Account Details

| Field | Value |
|---|---|
| Business Name | WORKFORCE365.AI |
| Type | Limited Company |
| Address | 30 Lestrange Street, Cleethorpes, United Kingdom, D 35TH 7HQ |
| VAT Registered | No |
| Year End Date | 2027-04-05 |
| Created | 2026-09-15 |

## Bank Accounts

| ID | Name | Nominal | Type |
|---|---|---|---|
| 88289 | Current Account | 1200 | current |
| 88290 | Directors Loan Account | 1201 | loan |
| 88291 | Bank Reserve Account | 1210 | reserve |
| 88292 | Petty Cash | 1230 | petty |
| 88293 | Credit Card | 1250 | creditcard |

## Existing Nominal Codes (32 total)

**Assets:** 100, 1100, 1200-1250  
**Liabilities:** 2100, 2200, 2300  
**Equity:** 3000, 3200  
**Revenue:** 4000, 4100, 4200, 4400, 4900  
**Purchases:** 5000, 5100, 5200  
**Overheads:** 6000-8200  
**Tax:** 8500  

## Current State (2026-09-15)

- No clients
- No suppliers
- No invoices (sales or purchase)
- No journal entries

## What's Available via REST API

- Clients/Suppliers CRUD
- Sales invoices, Purchase invoices
- Payments, Journals
- Reports (P&L, Balance Sheet, VAT, Aged Debtors)
- Bank transactions
- Document uploads

## What Requires Manual User Action

- Bank feeds (Open Banking consent in QuickFile web UI)
- Stripe/PayPal payment integrations (configure in web UI)

## Approved Chart of Accounts (2026-09-15)

| Code | Account Name | Type |
|---|---|---|
| 0011 | Intangible Assets - Software Development | Fixed Asset |
| 0012 | Tangible Assets - Computer Equipment | Fixed Asset |
| 1010 | Debtors Control | Current Asset |
| 1020 | Prepayments | Current Asset |
| 1030 | Cash at Bank - Current Account | Current Asset |
| 1031 | Cash at Bank - Savings | Current Asset |
| 1040 | PayPal/Stripe Clearing | Current Asset |
| 2010 | Trade Creditors | Current Liability |
| 2020 | VAT Control | Current Liability |
| 2030 | PAYE/NIC Control | Current Liability |
| 2040 | Corporation Tax Payable | Current Liability |
| 2050 | Accruals | Current Liability |
| 3010 | Called Up Share Capital | Equity |
| 3020 | Retained Earnings | Equity |
| 4010 | AI Services Revenue | Revenue |
| 4020 | Consulting Revenue | Revenue |
| 4030 | Subscription Revenue | Revenue |
| 5010 | API Costs (OpenAI, Anthropic, etc.) | Direct Cost |
| 5020 | Cloud Infrastructure (Vercel, AWS, etc.) | Direct Cost |
| 5030 | Data Processing Costs | Direct Cost |
| 6010 | Software Licenses | Overhead |
| 6020 | Professional Fees (Accountant/Legal) | Overhead |
| 6030 | Bank Charges | Overhead |
| 6040 | Office Costs | Overhead |
| 6050 | Travel & Subsistence | Overhead |
| 6060 | Marketing & Advertising | Overhead |
| 6070 | Insurance | Overhead |
| 6080 | Website & Hosting | Overhead |
| 6090 | Telecommunications | Overhead |
| 7010 | Bank Interest Receivable | Finance |
| 7020 | Bank Interest Payable | Finance |
| 8010 | Corporation Tax | Tax |

## Sync Policy

Per company policy: QuickFile configuration changes must be tracked in this Obsidian note AND synced to memory. Any agent making changes to QuickFile setup should update this note immediately.
