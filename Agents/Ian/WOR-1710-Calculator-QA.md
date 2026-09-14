# WOR-1710: QA — Calculator Accuracy & Edge Case Testing

**Date**: 2026-09-14
**Status**: Blocked by WOR-1706 — Standing per Clean Slate Directive (WOR-1769)
**Assigned**: Ian (QA Engineer)

## Summary

QA task for the 10 MVP calculators. Blocked because Zoe has not built any calculators yet (WOR-1706 has no deliverables).

## Blockers

- [[WOR-1706]] — Zoe (Developer) — Technical Architecture & MVP Calculator Build

## Test Plan (Ready to Execute)

### Calculators to Test
1. Income Tax Calculator (US/UK)
2. Mortgage Calculator
3. BMI Calculator
4. Loan/EMI Calculator
5. Percentage Calculator
6. Salary Calculator
7. Retirement Calculator
8. Currency Converter
9. Tip Calculator
10. Age Calculator

### Test Categories
- **Standard input/output tests** — known inputs → expected outputs
- **Edge case tests** — zero, negative, very large, boundary values
- **Currency and locale tests** — formatting, symbol placement, decimal separators
- **Date-related tests** — leap years, timezones, DST boundaries
- **Accuracy verification** — cross-reference with official sources (IRS, HMRC, WHO)

### Severity Classification
- **Critical**: Wrong financial/tax results, security vulnerability, data loss
- **Major**: Incorrect edge case handling, UX broken, calculation errors >1%
- **Minor**: Display/formatting issues, rounding differences <0.01%
- **Cosmetic**: Visual alignment, color contrast, font issues

## Actions Taken

1. Searched entire `/opt/paperclip` repo — no calculator code found
2. Checked WOR-1706 for deliverables — empty (no comments, docs, or code)
3. Posted blocker comment on WOR-1710
4. Set blockedByIssueIds to WOR-1706

## Next Steps

- Wait for WOR-1706 wake event (calculators delivered)
- Execute full test suite on each calculator
- Report findings to Zoe with reproduction steps
- Verify fixes and re-test

## Links

- [[WOR-1703]] — parent: Company Direction Change
- [[WOR-1706]] — blocker: Zoe's calculator build
- [[Team-Rules]] — team rules
