---
title: Authentication
---

# Authentication

To ensure the security of our commerce platform and protect customer data, all requests to the SportShop API must be authenticated. This guide explains how to obtain and use your API keys.

## API Keys

The SportShop API uses API keys to identify and authorize requests. Each key is associated with a specific environment (Sandbox or Production) and carries permissions based on your account level.

{% admonition type="info" name="Security First" %}
Keep your API keys secure. Do not share them in public repositories, client-side code, or insecure communication channels. If a key is compromised, revoke it immediately through the developer dashboard.
{% /admonition %}

## Obtaining a Key

To get started, you'll need to generate a key in your developer portal:

1. Log in to your SportShop account.
2. Navigate to the **Developer Settings** section.
3. Click on **API Keys**.
4. Select **Create New Key**.
5. Give your key a descriptive name (e.g., "Development Sandbox") and save it.

## Using your Key

The SportShop API expects the API key to be sent in the `X-API-Key` custom HTTP header for every request.

```bash
curl -X GET "https://api.example.com/products" \
  -H "X-API-Key: YOUR_API_KEY"
```

If the header is missing or the key is invalid, the API returns a `401 Unauthorized` response.

### Example Response (Unauthorized)

```json
{
  "error": "unauthorized",
  "message": "Invalid or missing API key. Please include a valid X-API-Key header."
}
```

---

## Resources

- [API Reference](/apis/openapi.yaml)
