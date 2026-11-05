# TruLata MCP server

TruLata is AI marketing software for service businesses. It writes and publishes your content, runs your ads and answers your leads. This remote MCP server lets an AI assistant work with your TruLata account: your leads, dashboard numbers, website, articles, brand assets, Google and Meta ads, team and support.

**Server URL:** `https://api.trulata.com/mcp` (Streamable HTTP)

**Sign in:** OAuth. Your client opens TruLata's sign in page, you approve, and the connection opens your own account. There is no key to paste. You need a TruLata account: [start one here](https://login.trulata.com/signup).

## Tools

24 tools, read live from the server. Anything that spends money, publishes or emails a person runs only after the owner says yes in the conversation.

### Account and data
| Tool | What it does |
|---|---|
| `get_account` | The account this connection opens: company name, plan and dashboard link |
| `get_account_state` | Plan and what it includes, seats, connections, what is failing right now, open tickets, recent ad changes, reviews waiting for a reply |
| `read_dashboard_data` | Any section of the dashboard, untrimmed: Google searches and pages, GA4, lead sources, AI visibility, ads, social, email |
| `refresh_dashboard` | Pull fresh numbers from the connected sources now |
| `save_business_settings` | Save what the business does, where, for whom, its voice, website and target searches |

### Leads
| Tool | What it does |
|---|---|
| `list_leads` | Your leads, newest first, with contact details, message, source and status |
| `search_leads` | Leads by name, email, phone, town, word or source over a window, with the count against the period before |
| `find_lead` | Find leads from the last year by exact email or phone |
| `create_lead` | Add a lead to your Leads tab, the way a website form message arrives |
| `set_lead_status` | Mark a lead contacted, engaged, quoted, won, lost or not a lead, with a note |
| `mark_lead` | Record what happened with a lead, exactly like the buttons on the Leads tab |

### Website and content
| Tool | What it does |
|---|---|
| `list_websites` | Your TruLata websites with live and preview links and recent form messages |
| `edit_website` | Have the website builder's agent make a change in plain words; edits the draft and returns a preview link |
| `list_posts` | Your published blog posts, newest first |
| `draft_article` | Queue a new researched article; it lands as a draft in the Content tab |
| `publish_article` | Publish one draft article (after the owner's yes) |
| `make_brand_asset` | An email signature, a print-ready business card or a PowerPoint template in your brand |

### Ads
| Tool | What it does |
|---|---|
| `list_ad_campaigns` | Your Google Ads campaigns live: status, daily budget, last 30 days of spend, clicks and conversions |
| `set_campaign_status` | Pause or turn on one Google Ads campaign (after the owner's yes) |
| `set_daily_budget` | Set one Google Ads campaign's daily budget (after the owner's yes) |
| `preview_meta_campaign` | Check a new Facebook and Instagram campaign plan and get the summary to approve; creates nothing |
| `create_meta_campaign` | Create the approved Meta campaign in your ad account, paused unless you say launch |

### Team and help
| Tool | What it does |
|---|---|
| `invite_teammate` | Give a teammate their own sign-in (after the owner's yes) |
| `open_support_ticket` | Open a real support ticket the TruLata team sees at once |

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
