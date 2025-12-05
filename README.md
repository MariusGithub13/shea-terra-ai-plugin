# shea-terra-ai-plugin

AI plugin for Shea Terra Organics – schema for LLMs like ChatGPT, Gemini, and Perplexity.

## Overview

This repository contains an OpenAI-compatible AI plugin that enables Large Language Models (LLMs) like ChatGPT to interact with Shea Terra Organics product data.

## Structure

```
├── .well-known/
│   └── ai-plugin.json    # Plugin manifest for ChatGPT and other LLMs
├── openapi.yaml          # OpenAPI 3.0 specification for the product API
├── netlify.toml          # Netlify deployment configuration
└── logo.png              # Plugin logo (512x512 recommended)
```

## Plugin Manifest

The `.well-known/ai-plugin.json` file contains:

- **name_for_human**: Shea Terra Organics
- **name_for_model**: shea_terra_organics
- **description**: Discover premium organic skincare, haircare, and body products
- **auth**: No authentication required
- **contact**: support@sheaterra.com

## API Endpoints

### GET /api/products

Retrieves a list of organic skincare, haircare, and body products.

**Query Parameters:**
- `category` (optional): Filter by category (skincare, haircare, body)
- `limit` (optional): Maximum number of products to return (default: 10, max: 100)

**Response:**
```json
{
  "products": [
    {
      "id": "string",
      "name": "string",
      "description": "string",
      "price": 0.00,
      "category": "string",
      "url": "string"
    }
  ],
  "total": 0
}
```

## Deployment

This plugin is configured for Netlify deployment. Simply connect your repository to Netlify and it will automatically deploy.

### Manual Deployment

1. Push this repository to GitHub
2. Connect the repository to Netlify
3. The site will be available at your Netlify URL
4. Update the URLs in `ai-plugin.json` and `openapi.yaml` to match your deployment URL

## Testing

To test the plugin locally:

1. Serve the files with a local server:
   ```bash
   npx serve .
   ```

2. Verify the manifest is accessible at:
   - `http://localhost:3000/.well-known/ai-plugin.json`
   - `http://localhost:3000/openapi.yaml`

## License

MIT License - see [LICENSE](LICENSE) for details.
