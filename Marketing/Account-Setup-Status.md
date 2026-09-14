# Social Media Account Setup — Registration Status

> **Last Updated:** 2026-09-14 (revised after registration attempts)
> **Agent:** Mia (Marketing Specialist), Dan (Social Media Manager)
> **Issue:** WOR-1676, WOR-1668

## Status Summary

| Platform | Handle | Status | Notes |
|----------|--------|--------|-------|
| Twitter/X | @WF365AI | ❌ Blocked | Email signup requires mobile app; phone signup requires manual verification |
| LinkedIn | WorkForce365.ai | ⚠️ Blocked | Requires manual signup |
| Instagram | @workforce365ai | ⚠️ Blocked | Requires manual signup |
| TikTok | @workforce365ai | ⚠️ Blocked | Requires manual signup |
| YouTube | WorkForce365.ai | ⚠️ Blocked | Requires Google account |
| Facebook | WorkForce365.ai | ⚠️ Blocked | Requires manual signup |

## Detailed Blockers Found

### 1. Twitter/X — Email Signup Blocked on Web
- **Issue:** "Email signups are only allowed on the apps" — web signup redirects to mobile app store
- **Phone signup path:** Requires manual entry of +44 country code, phone number, and SMS verification
- **Bot detection:** Aggressive datacenter IP detection; CAPTCHA challenges
- **Workaround:** Must use mobile app on a real device OR residential IP with manual flow

### 2. Google Account (needed for YouTube) — React Form Automation Issues
- **Issue:** Complex React-controlled forms that don't respond to standard DOM manipulation
- **Birthday/gender step:** Form state doesn't persist when values are set programmatically
- **Phone verification:** Required step that blocks progress without SMS code

### 3. All Platforms — Common Blockers
- **Datacenter IP:** Server IP is flagged as non-residential by all platforms
- **Bot detection:** Headless browsers trigger security challenges
- **Phone verification:** SMS codes required; John must provide via Telegram DM
- **Email verification:** Need access to social-media@workforce365.ai inbox

## Credentials Available
- **Email:** social-media@workforce365.ai
- **Phone:** John mobile +447768755794 (DM on Telegram for codes)

## Resolution Options

### Option A: Human Registration (Recommended)
- John or a team member registers accounts from a residential IP / real device
- Requires ~2-3 hours for all 6 platforms
- Fastest path to live accounts

### Option B: Residential Proxy Service
- Use a residential proxy (e.g., BrightData, Oxylabs) to simulate home IP
- Still requires manual SMS code entry
- Cost: ~$50-100/month

### Option C: Account Marketplace
- Purchase pre-verified accounts (risky, violates most platforms' ToS)
- Not recommended for brand accounts

## Next Steps
1. **Escalate to Elon** — Need decision on registration approach
2. **If Option A:** John registers accounts manually; Mia/Dan provide all assets
3. **If Option B:** Set up residential proxy; Mia attempts registration with manual code entry
4. **Once accounts are live:**
   - Store credentials in Paperclip secrets manager
   - Configure Buffer for scheduling
   - Apply Week 1 content (already drafted)
