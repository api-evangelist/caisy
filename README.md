# Caisy

GraphQL-native headless CMS with a real-time GraphQL content API, rich text as AST, multi-site support, and component-based content blueprints.

- **Website**: https://caisy.io/
- **Documentation**: https://caisy.io/developer/docs
- **Pricing**: https://caisy.io/pricing
- **GitHub**: https://github.com/caisy-io
- **LinkedIn**: https://www.linkedin.com/company/cyclus-digital
- **Changelog**: https://caisy.io/changelog

## About

Caisy is an API-first headless CMS built around a fully fledged GraphQL API following the Relay specification. It is designed for developers, agencies, and enterprise teams who need to deliver content across multiple platforms and sites from a single source of truth.

Key capabilities include:

- **GraphQL content API**: Every project exposes a dedicated GraphQL endpoint at `https://cloud.caisy.io/api/e/v4/{PROJECT_ID}/graphql`.
- **Rich text as AST**: Rich text fields return a typed Abstract Syntax Tree for framework-agnostic rendering.
- **Component-based blueprints**: Define content models (blueprints) with a schema builder; connect models to create typed relationships.
- **Multi-site support**: Manage content for multiple sites and locales from a single organization.
- **Image optimization**: Built-in CDN-backed image transformation without additional tooling.
- **TypeScript SDKs**: First-class TypeScript support with generated GraphQL clients via `graphql-code-generator`.

## Plans

| Plan       | Price             | API Calls/month | Rate Limit |
|------------|-------------------|-----------------|------------|
| Free       | $0                | 1M              | 5 RPS      |
| Growth     | $49/month         | 10M             | 35 RPS     |
| Enterprise | From $1,499/month | Custom          | 50+ RPS    |

See [plans/caisy-plans.md](plans/caisy-plans.md) for full feature comparison and overage pricing.

## Repository Contents

```
apis.yml                        # APIs.json / apis.io catalog entry
plans/caisy-plans.md            # Plan tiers, features, and overage pricing
rate-limits/caisy-rate-limits.md # API rate limits and monthly call quotas
finops/caisy-finops.md          # Cost drivers and optimization strategies
graphql/caisy-graphql.md        # GraphQL API reference and examples
```

## Maintainer

Kin Lane — kin@apievangelist.com
