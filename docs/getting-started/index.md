---
title: Getting Started
---

# Getting Started

Welcome to the SportShop API. This platform provides developers with a robust set of tools to integrate athletic equipment, apparel, and customer order management into their applications. Whether you're building a custom storefront or an internal inventory tool, this guide will help you get up and running.

## Base URL

All API requests are made to the following base URL:

```text
https://api.example.com
```

## Your First Request

To verify your connection, you can retrieve a list of available products. No authentication is required for this initial test in the sandbox environment.

{% code-group %}
```bash {% title="Request" %}
curl -X GET "https://api.example.com/products" \
     -H "Accept: application/json"
```

```json {% title="Response" %}
[
  {
    "id": "e3b0c442-98fc-11eb-a8b3-0242ac130003",
    "name": "Pro Marathon Running Shoes",
    "brand": "SpeedRun",
    "price": 129.99,
    "category": "footwear",
    "tags": ["running", "marathon", "breathable"]
  },
  // ...
]
```
{% /code-group %}

## Next Steps

Once you've made your first request, you're ready to dive deeper into the SportShop ecosystem:

- **[Set up Authentication](/docs/getting-started/authentication)**: Learn how to secure your requests using API keys.
- **[Manage Orders](/docs/guides/orders-and-checkout)**: Understand the full checkout flow from cart to completion.
- **[Explore the Catalog](/docs/guides/catalog-management)**: Use advanced filtering to find specific gear.

### Resources

- [SportShop API Reference](/apis/openapi.yaml)
