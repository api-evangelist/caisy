# Caisy Rate Limits

Caisy enforces rate limits on the GraphQL content API per project. Limits are set at the plan level and measured in requests per second (RPS).

## API Rate Limits by Plan

| Plan       | Rate Limit (requests/second) |
|------------|------------------------------|
| Free       | 5 RPS                        |
| Growth     | 35 RPS                       |
| Enterprise | 50+ RPS (customizable)       |

## GraphQL Endpoint

Each Caisy project exposes a unique GraphQL endpoint:

```
https://cloud.caisy.io/api/e/v4/{CAISY_PROJECT_ID}/graphql
```

Where `{CAISY_PROJECT_ID}` is the unique identifier for the project. Authentication is handled via a Bearer token passed in the `Authorization` header.

## Monthly API Call Limits

In addition to per-second rate limits, each plan has a monthly ceiling on total API calls:

| Plan       | Monthly API Calls |
|------------|-------------------|
| Free       | 1,000,000         |
| Growth     | 10,000,000        |
| Enterprise | Custom quota      |

Growth and Enterprise plans support overage billing for API calls beyond the included quota.

## Bandwidth Limits

| Plan       | Monthly Bandwidth |
|------------|-------------------|
| Free       | 100 GB            |
| Growth     | 500 GB            |
| Enterprise | Custom quota      |

Additional bandwidth on Growth and Enterprise is billed at $60 per 1 TB.

## Notes

- Rate limits apply per project, not per user or per organization.
- Exceeding the requests/second limit will result in HTTP 429 responses.
- Enterprise customers can negotiate higher RPS limits and custom SLAs.

Source: https://caisy.io/pricing and https://caisy.io/for-developers
