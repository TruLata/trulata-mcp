# TruLata MCP server

TruLata is AI marketing software for service businesses. It writes and publishes your content, runs your ads and answers your leads. This remote MCP server lets an AI assistant work with your TruLata account: read your leads, find one by email or phone, update its status, add a new one, and see your published blog posts.

**Server URL:** `https://api.trulata.com/mcp` (Streamable HTTP)

**Sign in:** OAuth. Your client opens TruLata's sign in page, you approve, and the connection opens your own account. There is no key to paste. You need a TruLata account: [start one here](https://login.trulata.com/signup).

## Tools

| Tool | What it does |
|---|---|
| `get_account` | The account this connection opens: company name, plan and dashboard link |
| `list_leads` | Your leads, newest first, with contact details, message, source and status |
| `find_lead` | Find leads from the last year by exact email address or phone number |
| `create_lead` | Add a lead to your Leads tab, the way a website form message arrives |
| `set_lead_status` | Mark a lead contacted, quoted, won, lost or not a lead, with an optional note |
| `list_posts` | Your published blog posts, newest first |

## Connect

**Claude:** add TruLata from [Claude's connector directory](https://claude.ai/directory/trulata), or add a custom connector with the server URL above.

**Cursor, VS Code and other MCP clients:**

```json
{
  "mcpServers": {
    "trulata": { "url": "https://api.trulata.com/mcp" }
  }
}
```

**Gemini CLI:**

```bash
gemini extensions install https://github.com/TruLata/trulata-mcp
```

**Any client that runs local servers only:**

```bash
npx -y mcp-remote https://api.trulata.com/mcp
```

## More

- How the connector works: https://trulata.com/product/api#mcp
- The REST API and webhooks: https://trulata.com/product/api
- Help: support@trulata.com
