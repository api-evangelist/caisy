# Caisy GraphQL API

Caisy's entire content API is GraphQL-native, built on the Relay specification. Every project gets its own dedicated GraphQL endpoint.

## Endpoint

```
https://cloud.caisy.io/api/e/v4/{CAISY_PROJECT_ID}/graphql
```

Replace `{CAISY_PROJECT_ID}` with the unique ID found in the Caisy dashboard for the target project.

## Authentication

All requests require a Bearer token in the `Authorization` header:

```http
Authorization: Bearer {CAISY_API_TOKEN}
```

Tokens are generated per-project from the Caisy dashboard under **Settings > API Keys**.

## Core Capabilities

- **Flexible queries**: Filter, sort, and paginate across any content type defined by the project's blueprints.
- **Nested document referencing**: Traverse related content in a single query using Relay-style connections.
- **Rich text as AST**: Rich text fields are returned as a typed Abstract Syntax Tree (AST) for framework-agnostic rendering.
- **Mutations**: Create, update, and delete content entries programmatically.
- **Real-time**: The API reflects content changes immediately without cache invalidation steps.

## Example Query

```graphql
query GetBlogPosts($first: Int, $after: String) {
  allBlogPost(first: $first, after: $after) {
    edges {
      node {
        id
        title
        slug
        publishedAt
        author {
          name
        }
        body {
          json  # Rich text as AST
        }
      }
    }
    pageInfo {
      hasNextPage
      endCursor
    }
  }
}
```

## Filtering & Sorting

Caisy's GraphQL schema exposes filter and sort arguments on collection queries:

```graphql
query FilteredPosts {
  allBlogPost(
    where: { publishedAt: { gte: "2026-01-01" } }
    sort: { publishedAt: DESC }
    first: 10
  ) {
    edges {
      node {
        title
        slug
      }
    }
  }
}
```

## SDK & Code Generation

Caisy provides TypeScript SDKs and supports `graphql-code-generator` for typed client generation.

- SDK documentation: https://caisy.io/developer/docs/libraries/graphql-code-generator
- GitHub organization (examples and libraries): https://github.com/caisy-io

## Rate Limits

| Plan       | Requests/Second |
|------------|-----------------|
| Free       | 5               |
| Growth     | 35              |
| Enterprise | 50+ (custom)    |

Exceeding the rate limit returns HTTP 429. See `rate-limits/caisy-rate-limits.md` for full details.

## Further Reading

- Developer documentation: https://caisy.io/developer/docs
- GraphQL introduction post: https://caisy.io/blog/introduction-to-graphql2
- Astro integration guide: https://docs.astro.build/en/guides/cms/caisy/
