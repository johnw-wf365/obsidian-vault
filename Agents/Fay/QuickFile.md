# QuickFile Integration

**Company:** WorkForce365.ai  
**Account Number:** 7131416580  
**API Key:** 6b06x622lD7PZrKTNlb9f5cVd307B59204OSk4STzV1NSd1WS0n0ry060i72R4sh  
**Application ID:** fay-agent  
**API Base URL:** https://api.quickfile.co.uk/1_2/  
**Auth Method:** MD5(AccountNumber + APIKey + SubmissionNumber)

## Status

- Token accepted by server (MD5 auth works)
- JSON endpoints: serializer needs specific wrapper structure
- XML endpoints: method names unclear without official docs
- Recommended: Deploy marcusquinn/quickfile-mcp with legacy credentials

## Chart of Accounts

Approved by user (2026-09-15). See [[WOR-1925]] for full chart.

## Bank Feeds

- UK banks via Open Banking (50+ institutions)
- £15 + VAT/year for automated feeds
- PayPal/Stripe via integration

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
