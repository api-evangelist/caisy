# Caisy FinOps

This document covers cost structure, usage-based levers, and optimization strategies for Caisy deployments.

## Plan Pricing Summary

| Plan       | Monthly Cost        | Best For                                      |
|------------|---------------------|-----------------------------------------------|
| Free       | $0                  | Prototypes, personal projects, evaluation     |
| Growth     | $49/month           | Production apps, growing teams (up to 12 users) |
| Enterprise | From $1,499/month   | Large organizations, custom SLAs, on-premise  |

Billing is monthly via Stripe (credit card). No annual commitment listed for standard plans.

## Primary Cost Drivers

### 1. Content Entries
The number of content documents (entries) stored determines which plan is required and triggers overage fees on Growth.

- Free cap: 5,000 entries
- Growth cap: 20,000 entries — overage: $20 per additional 10,000 entries

### 2. Users / Seats
Team size is a meaningful cost driver on Growth.

- Free: 3 users included
- Growth: 12 users included — overage: $10/user/month
- Enterprise: Custom

### 3. Bandwidth / Traffic
Content delivery and image optimization consume bandwidth against the monthly quota.

- Free: 100 GB — no overage (plan upgrade required)
- Growth: 500 GB — overage: $60 per additional 1 TB
- Enterprise: Custom

### 4. Locales (Internationalization)
Each additional language/locale beyond the plan quota incurs an overage charge on Growth.

- Free: 2 locales
- Growth: 4 locales — overage: $15/locale/month

### 5. Blueprints (Content Models)
Blueprints define content structure. Heavy use of modular content models can push usage toward the cap.

- Free: 30 blueprints
- Growth: 60 blueprints — overage: $10 per 10 additional blueprints

### 6. API Calls
Monthly API call volume determines both plan fit and overage exposure.

- Free: 1 million calls/month
- Growth: 10 million calls/month
- Enterprise: Custom

## Cost Optimization Strategies

- **Cache aggressively**: Caisy's GraphQL responses are cacheable. Adding a CDN layer (e.g., Cloudflare, Fastly) in front of the API reduces raw API call counts and bandwidth consumption directly.
- **Consolidate projects**: Free plan is limited to 3 projects; structure content in fewer projects where possible to stay within Free tier.
- **Audit blueprints**: Unused content models (blueprints) count against the quota; remove obsolete ones to avoid unnecessary upgrades.
- **Use image optimization parameters**: Caisy's built-in image optimizer serves resized/formatted images to minimize bandwidth per request.
- **Monitor locale count**: Adding locales is cheap in effort but adds $15/month each past the Growth quota; audit active translations before adding new ones.
- **Evaluate entry archival**: Archive or delete stale content entries to stay within plan limits rather than paying overage on entries.

## Enterprise Considerations

Enterprise pricing starts at $1,499/month with custom quotas across all dimensions. The notable additions that may justify the step-up cost include:

- 99.9% SLA (not available on lower tiers)
- On-premise hosting (avoids third-party data residency concerns)
- Custom SSO (reduces user management overhead at scale)
- Content workflows (enables editorial approval chains without third-party tooling)
- Dedicated account manager (accelerates support resolution)

Source: https://caisy.io/pricing
