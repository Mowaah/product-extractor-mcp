# Installing the Product Page Extractor MCP server

This is a remote (hosted) MCP server. There's nothing to clone, build or install.

1. Add this entry to the MCP settings file (for Cline: `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "product-extractor": {
      "url": "https://product-extractor.mohamed-bahaa53000.workers.dev/demo/mcp",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

2. No API key is needed for the demo endpoint (10 tool calls per IP per day).
3. For production use, the user can subscribe on RapidAPI (https://rapidapi.com/MohamedBahaa/api/product-page-extractor) and switch the url to `https://product-page-extractor.p.rapidapi.com/mcp` with headers `X-RapidAPI-Key` (their key) and `X-RapidAPI-Host: product-page-extractor.p.rapidapi.com`.
4. Verify by calling `extract_product` with `{"url": "https://www.allbirds.com/products/mens-tree-runners"}`. It should return a product with `price_source: "json-ld"`.
