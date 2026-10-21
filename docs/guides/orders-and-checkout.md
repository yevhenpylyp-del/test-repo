---
title: Orders and Checkout
---

# Orders and Checkout

The SportShop API provides a streamlined workflow for managing shopping carts and processing orders. This guide walks you through adding items to a cart and finalizing a purchase.

## Managing the Cart

Before placing an order, customers add items to their shopping cart. Use the `/cart` endpoint to manage these selections.

```bash
curl -X POST "https://api.example.com/cart" \
     -H "Content-Type: application/json" \
     -d '{
       "productId": "e3b0c442-98fc-11eb-a8b3-0242ac130003",
       "quantity": 2
     }'
```

This request adds two pairs of running shoes to the current session's cart.

## Placing an Order

To complete a purchase, send a `POST` request to the `/orders` endpoint with the customer's items and shipping details.

```json
{
  "items": [
    {
      "productId": "e3b0c442-98fc-11eb-a8b3-0242ac130003",
      "quantity": 2
    }
  ],
  "shippingAddress": {
    "street": "123 Sprint Lane",
    "city": "Olympia",
    "postalCode": "98501",
    "country": "USA"
  }
}
```

{% admonition type="info" %}
Ensure all product IDs in the order items match valid products in the catalog and are currently in stock.
{% /admonition %}

## Order Status

You can retrieve a history of orders for a customer to track delivery progress or review past purchases.

```bash
curl -X GET "https://api.example.com/orders" \
     -H "X-API-Key: YOUR_API_KEY"
```

The response returns an array of order objects, including their current processing status and tracking numbers if available.

### Resources

- [Orders API Reference](/apis/openapi.yaml)
