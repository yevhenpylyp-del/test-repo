---
title: Catalog Management
---

# Catalog Management

The SportShop API provides comprehensive endpoints for browsing our product catalog and checking real-time availability. This guide covers how to retrieve product lists, filter by category, and verify stock levels.

## Browsing Products

To retrieve a list of all available products, use the `GET /products` endpoint. This returns an array of product objects containing details such as brand, price, and category.

```bash
curl https://api.example.com/products \
  -H "X-API-Key: YOUR_API_KEY"
```

A typical product response looks like this:

```json
[
  {
    "id": "123e4567-e89b-12d3-a456-426614174000",
    "name": "Air Max Runner",
    "brand": "Nike",
    "price": 129.99,
    "category": "footwear",
    "tags": ["running", "breathable"]
  }
]
```

## Filtering by Category

You can narrow down your search by using the `category` query parameter. This is particularly useful for building category-specific pages in your storefront.

To filter for footwear, append the query parameter to your request:

```bash
curl "https://api.example.com/products?category=footwear" \
  -H "X-API-Key: YOUR_API_KEY"
```

Valid categories include `footwear`, `apparel`, `equipment`, and `accessories`.

## Checking Inventory

Before allowing a customer to add an item to their cart, it is best practice to check current stock levels using the `GET /inventory/{sku}` endpoint.

```bash
curl https://api.example.com/inventory/SKU-456 \
  -H "X-API-Key: YOUR_API_KEY"
```

The response provides the current availability for that specific SKU:

```json
{
  "sku": "SKU-456",
  "available": 42
}
```

## Resources

- [SportShop API Reference](/apis/openapi.yaml)
