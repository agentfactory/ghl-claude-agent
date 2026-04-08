# Technical Facts Sheet: GoHighLevel MCP Integration
## Agent 1 Output - Research & Architecture
**Compiled:** 2026-04-07

---

## GHL MCP Version & Status

- **Project:** GoHighLevel MCP Server (community-built, open source)
- **Repo:** github.com/mastanley13/GoHighLevel-MCP
- **License:** ISC
- **Status:** Active, foundational/base-level project
- **Tech stack:** Node.js 18+ (TypeScript), Express.js 5.x, MCP SDK ^1.12.1, Axios, Jest
- **Official GHL MCP endpoint:** `https://services.leadconnectorhq.com/mcp/`
- **Note:** GHL also has a native/official MCP server at the endpoint above, separate from the community GitHub repo

---

## Full Tool Categories (269 Tools Total)

| Category | Count | Key Capabilities |
|---|---|---|
| Contact Management | 31 | Create, search, get, update, delete contacts; manage tags, tasks, notes; upsert; workflow integration; follower management |
| Messaging & Conversations | 20 | Send SMS/email; search conversations; manage messages; call recordings; transcriptions; live chat |
| Blog Management | 7 | Create/update posts; retrieve sites, authors, categories; URL slug validation |
| Opportunity Management | 10 | Search opportunities; manage pipelines; create/update/delete; follower management |
| Calendar & Appointments | 14 | Manage calendars; check availability; create/update/delete appointments; time blocking |
| Email Marketing | 5 | Campaign management; template creation/management |
| Location Management | 24 | Manage sub-accounts; tag systems; custom fields; templates; timezone handling |
| Social Media | 17 | Post management; account integration; bulk operations (Google Business, Facebook, Instagram, LinkedIn, Twitter, TikTok) |
| Custom Objects | 9 | Schema management; record operations; advanced search |
| Association Management | 10 | Relationship mapping between objects |
| Custom Fields V2 | 8 | Field management; folder organization |
| Workflow Management | 1 | Workflow discovery |
| Survey Management | 2 | Survey and response management |
| Store Management | 18 | Shipping zones/rates; carriers; store settings |
| Products Management | 10 | Product operations; pricing; inventory; collections |
| Payments Management | 20 | Order management; transaction tracking; subscriptions; coupon system |
| Invoices & Billing | 39 | Templates; recurring invoices; invoice management; estimates |
| Email Verification | 1 | Email verification |
| Media Library | 3 | Media file management |

---

## Required GHL Private Integration Scopes

### Safe Starting Set (for beginner guide)

These scopes cover the four main use cases in the product (lead qualification, follow-ups, pipeline management, appointments):

| Scope | Purpose |
|---|---|
| contacts.readonly | Read contact data for qualification |
| contacts.write | Tag contacts, add notes |
| conversations.readonly | Read conversation history for follow-ups |
| conversations.write | Send messages, draft replies |
| opportunities.readonly | View pipeline stages and opportunities |
| opportunities.write | Move contacts through pipeline stages |
| calendars.readonly | Check calendar availability |
| calendars.write | Book appointments |
| locations.readonly | Access location/sub-account info |
| workflows.readonly | View available workflows |
| users.readonly | View team member info |

### Extended Scopes (for power users, not in beginner guide)

| Scope | Purpose |
|---|---|
| blogs.readonly / blogs.write | Blog management |
| custom_objects.readonly / custom_objects.write | Custom object operations |
| invoices.readonly / invoices.write | Invoice management |
| payments.readonly | Payment tracking |
| products.readonly / products.write | Product management |
| campaigns.readonly | Email campaign access |

### Official GHL Scope List (from help article)

- View/Edit Contacts
- View/Edit Conversations
- View/Edit Conversation Messages
- View/Edit Opportunities
- View Calendars & Calendar Events
- View Locations
- View Payment Orders & Transactions
- View Custom Fields
- View Forms
- Check/Create/Update Blog Posts
- View Blog Authors & Categories
- Create/Update/Delete/View Email Templates
- View Social Media Accounts & Statistics
- Edit/View Social Media Posts

---

## PIT Token Generation Steps (Exact)

1. Log into your GoHighLevel account
2. Navigate to **Settings** (gear icon, bottom-left)
3. Click **Integrations** in the left sidebar
4. Click **Private Integrations** tab
5. Click **"+ Create New"** button
6. Name it: `MCP Server Integration`
7. Leave **Webhook URL** blank
8. Under **Scopes**, check the boxes for each scope you need (see Safe Starting Set above)
9. Click **Save**
10. **Copy the generated Private API Key immediately** (you cannot view it again after leaving the page)

**IMPORTANT:** This is a Private Integration Token (PIT), NOT a regular API key. Regular API keys will not work.

---

## Location ID Retrieval Steps (Exact)

1. Log into your GoHighLevel account
2. Navigate to **Settings** (gear icon, bottom-left)
3. Click **Company** in the left sidebar (or **Business Info** depending on account type)
4. Your **Location ID** is displayed on this page
5. Copy the Location ID string (format: a long alphanumeric string like `abc123def456...`)

**Alternative:** The Location ID also appears in your browser URL bar when logged into a sub-account. It's the string after `/location/` in the URL.

---

## Connection Methods

### Method 1: Official GHL MCP Endpoint (Simplest)

Configure your MCP client (Claude Desktop, Claude Code, etc.) to connect to:

**Endpoint:** `https://services.leadconnectorhq.com/mcp/`

**Required Headers:**
- `Authorization: Bearer YOUR_PIT_TOKEN`
- `locationId: YOUR_LOCATION_ID`

**Protocol:** HTTP POST with JSON payload, Server-Sent Events (SSE) for streaming

### Method 2: Community GitHub Repo (Self-Hosted)

**Environment Variables:**
```
GHL_API_KEY=your_private_integrations_api_key
GHL_BASE_URL=https://services.leadconnectorhq.com
GHL_LOCATION_ID=your_location_id
NODE_ENV=production
PORT=8000
CORS_ORIGINS=*
LOG_LEVEL=info
```

**Note:** The .env.example also includes `OPENAI_API_KEY` (optional, for enhanced features).

### Claude Desktop Configuration (using community repo locally)

Add to `claude_desktop_config.json` (Windows path: `%APPDATA%\Claude\claude_desktop_config.json`):

```json
{
  "mcpServers": {
    "ghl-mcp-server": {
      "command": "node",
      "args": ["C:\\path\\to\\GoHighLevel-MCP\\dist\\server.js"],
      "env": {
        "GHL_API_KEY": "your_private_integrations_api_key",
        "GHL_BASE_URL": "https://services.leadconnectorhq.com",
        "GHL_LOCATION_ID": "your_location_id"
      }
    }
  }
}
```

### Claude Code Configuration

Add to `.mcp.json` in your project root or `~/.claude/.mcp.json` globally:

```json
{
  "mcpServers": {
    "ghl": {
      "command": "node",
      "args": ["C:\\path\\to\\GoHighLevel-MCP\\dist\\server.js"],
      "env": {
        "GHL_API_KEY": "your_pit_token_here",
        "GHL_BASE_URL": "https://services.leadconnectorhq.com",
        "GHL_LOCATION_ID": "your_location_id_here"
      }
    }
  }
}
```

---

## Windows-Compatible Setup Commands (PowerShell)

```powershell
# Clone the repo
git clone https://github.com/mastanley13/GoHighLevel-MCP.git
cd GoHighLevel-MCP

# Install dependencies
npm install

# Copy environment template
Copy-Item .env.example .env

# Edit .env with your credentials
notepad .env

# Build the project
npm run build

# Start the server (HTTP mode for web apps)
npm start

# OR start in stdio mode (for Claude Desktop direct connection)
npm run start:stdio
```

### Health Check Commands

```powershell
# Test server is running
Invoke-RestMethod -Uri "http://localhost:8000/health"

# List available tools
Invoke-RestMethod -Uri "http://localhost:8000/tools"

# Test SSE endpoint
Invoke-WebRequest -Uri "http://localhost:8000/sse" -Headers @{"Accept"="text/event-stream"}
```

---

## Known Issues & Gaps

1. **No native npx package yet** - The official GHL roadmap mentions an upcoming npx package for clients without native HTTP support. Not available at time of writing.
2. **Rate limiting** - GHL enforces API rate limits. Heavy usage (bulk operations, rapid queries) may hit limits. No specific rate numbers documented.
3. **Full API access warning** - The MCP connection provides FULL access to all sub-account APIs matching your scopes. There is no granular per-tool permission control.
4. **Memory/recall safety** - If an agent does not have proper guardrails, it can perform unintended actions (e.g., deleting contacts, sending messages without review).
5. **OPENAI_API_KEY in .env** - The community repo optionally uses OpenAI for enhanced features. This is NOT required for basic MCP functionality.
6. **OAuth not yet supported** - The official roadmap lists OAuth support as a planned feature. Currently PIT-only.
7. **No built-in undo** - Actions taken through MCP (contact edits, message sends, pipeline moves) cannot be automatically reversed.
8. **Account type unclear** - Neither the repo nor the official docs specify minimum GHL account tier required (Agency Pro vs. Agency Starter vs. SaaS mode).

---

## Official GHL MCP Roadmap

From the official help article:
- Individual MCP servers for specific services (more granular control)
- npx package for broader client compatibility
- OAuth support (replacing/supplementing PIT tokens)
- Expansion to 250+ tools (already at 269 in community repo)
- Complete coverage across all GoHighLevel modules

---

## Deployment Options (Community Repo)

| Platform | Cost | Notes |
|---|---|---|
| Local (recommended for guide) | Free | Best for Claude Desktop/Code direct connection |
| Railway | $5/mo credit | Simple deploy, auto-scaling |
| Render | Free tier | Auto-deploy from GitHub, built-in SSL |
| Docker | Free (local) | `docker build` + `docker run` available |
| Vercel | Free tier | One-click deploy (repo recommends this) |

**For the beginner guide:** Recommend local setup with Claude Desktop or the official GHL endpoint directly. No server deployment needed for the simplest path.

---

## Mintlify Docs Setup Notes

- **Free tier:** Available, sufficient for this project
- **Setup:** Connect GitHub repo, install GitHub App, auto-deploys on push to default branch
- **Config:** `mint.json` in repo root defines navigation, colors, logos, CTAs
- **Requires:** Node.js v20.17.0+ for local CLI preview
- **Auto-generate from repo:** Mintlify can scaffold docs from a GitHub repo, but for this project we will manually structure the MDX files per the CLAUDE.md spec
- **Deployment:** Push to GitHub, Mintlify auto-builds and deploys

---

## Key Facts for Content Creation

### For the Free Guide (Agent 2)
- Simplest path: Use the official GHL MCP endpoint directly (no server setup needed)
- Fallback path: Clone the community repo and run locally
- The 4 core use cases map to specific tool categories: Contacts (31 tools), Conversations (20 tools), Opportunities (10 tools), Calendars (14 tools)
- Total: 75 tools cover all four use cases

### For the YouTube Video (Agent 3)
- Hook stat: "269 tools, zero Zapier, zero Make"
- Live demo angle: Move a contact through a pipeline stage using only natural language
- Blue ocean confirmed: No beginner-friendly GHL MCP video content exists
- Visual: GHL dashboard + Claude chat side by side

### For the Product Pack (Agent 4)
- Agent configs need these tool categories: contacts, conversations, opportunities, calendars
- Placeholder variables should match GHL field names where possible
- Include safety warnings: review before sending, test with a single contact first

### For the Ad Creative (Agent 5)
- Key differentiator: Direct connection, no middleware (no Zapier, no Make, no n8n)
- Price anchor: ~~$197~~ $97
- Trust element: "269 tools" specificity
- Objection handler: "No developer needed. 15 minutes."

---

*Research complete. All agents may proceed.*
