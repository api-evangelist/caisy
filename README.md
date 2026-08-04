# Caisy

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
