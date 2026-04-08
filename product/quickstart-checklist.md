# Claude Academy Agent Pack: Quick-Start Checklist

Print this page. Work through each section in order. Check each box as you go.

---

## Phase 1: Pre-Flight

Complete these checks before touching any configuration.

- [ ] **GHL account is active** on a plan that includes API access (Pro or above)
- [ ] **You can access Settings > Integrations** in your GHL sub-account
- [ ] **You have admin-level permissions** on the sub-account you want to connect
- [ ] **Claude Desktop or Claude Code is installed** on your computer
- [ ] **You have a Claude account** with an active subscription (Pro or Team)

If any box above is unchecked, resolve it before continuing.

---

## Phase 2: Setup

Create your Private Integration and connect it to Claude.

### Step 2A: Create Your Private Integration Token (PIT)

- [ ] Go to **Settings > Integrations > Private Integrations** in GHL
- [ ] Click **Create New Integration**
- [ ] Name it something clear (e.g., "Claude Agent Connection")
- [ ] Enable these scopes:
  - [ ] contacts.readonly
  - [ ] contacts.write
  - [ ] conversations.readonly
  - [ ] conversations.write
  - [ ] opportunities.readonly
  - [ ] opportunities.write
  - [ ] calendars.readonly
  - [ ] calendars.write
  - [ ] locations.readonly
  - [ ] workflows.readonly
  - [ ] users.readonly
- [ ] Click **Save** and copy the PIT token
- [ ] Store the token somewhere safe (password manager recommended)

### Step 2B: Find Your Location ID

- [ ] Go to **Settings > Business Profile** in your GHL sub-account
- [ ] Copy the **Location ID** from the URL bar or the Business Info section
- [ ] Save it alongside your PIT token

### Step 2C: Connect Claude to GHL

- [ ] Open your Claude Desktop config file or Claude Code MCP settings
- [ ] Add the GHL MCP server configuration:

```json
{
  "mcpServers": {
    "ghl": {
      "url": "https://services.leadconnectorhq.com/mcp/",
      "headers": {
        "Authorization": "Bearer YOUR_PIT_TOKEN_HERE",
        "locationId": "YOUR_LOCATION_ID_HERE"
      }
    }
  }
}
```

- [ ] Replace `YOUR_PIT_TOKEN_HERE` with your actual PIT token
- [ ] Replace `YOUR_LOCATION_ID_HERE` with the Location ID from Step 2B
- [ ] Restart Claude Desktop (or reload Claude Code)

### Step 2D: Test the Connection

- [ ] Open Claude and type: "List my GHL contacts"
- [ ] **What you should see:** Claude returns a list of contacts from your GHL account
- [ ] If you see an error, double-check your PIT token and scopes

**Connection test passed?** Move to Phase 3.

---

## Phase 3: Agent Deployment

Deploy your first agent configuration.

- [ ] **Pick one agent to start with** (we recommend the Lead Qualifier)
- [ ] Open the `agent-configs.md` file from this pack
- [ ] Read the "Before You Start" section for your chosen agent
- [ ] Complete all prerequisites listed there
- [ ] **Copy the system prompt** from the agent configuration
- [ ] **Fill in all placeholder variables** (marked with [BRACKETS])
- [ ] Paste the configured prompt into Claude as a system instruction or project prompt
- [ ] **Run the test scenario** described in the "How to Test It" section
- [ ] **What you should see:** Claude performs the described action on a real contact
- [ ] Review the results in your GHL account directly
- [ ] **Results look correct?** The agent is working.

---

## Phase 4: Go-Live

Final checks before using agents on real client data.

### Permission Review

- [ ] Confirm your PIT token only has the scopes listed in Step 2A
- [ ] Confirm no unnecessary write permissions are enabled
- [ ] Verify that the agent is not set to auto-send messages (drafts only to start)

### Backup Precautions

- [ ] Export your current GHL contacts as a CSV backup
- [ ] Note your current pipeline stage counts (screenshot or write them down)
- [ ] Set a calendar reminder to review agent activity after 24 hours

### First Live Run

- [ ] Run your agent on 3-5 real contacts
- [ ] Check each result in GHL manually
- [ ] Confirm tags, notes, messages, or bookings are correct
- [ ] If everything looks good, expand to larger batches

### Ongoing Maintenance

- [ ] Review agent output weekly for the first month
- [ ] Adjust placeholder variables as you learn what works
- [ ] Add new prompts from the Prompt Library as needed
- [ ] Visit the Claude Academy community if you hit a snag

---

## Troubleshooting Quick Reference

| Problem | Fix |
|---|---|
| "Tool not found" error | Restart Claude Desktop after adding the MCP config |
| "Unauthorized" error | Regenerate your PIT token and update the config |
| Claude returns no contacts | Confirm your Location ID is correct |
| Agent applies wrong tags | Check that your tag names match GHL exactly (case-sensitive) |
| Calendar shows no availability | Verify availability windows are configured in GHL Calendar Settings |
| Messages are not sending | Check that conversations.write scope is enabled |

---

## You Are Set

Once you complete this checklist, your Claude agent is live and connected to your GHL account. Start with one agent, test it thoroughly, then add more as you get comfortable.

Need help? Post in the Claude Academy community and tag your question with #agent-pack.

**[Claude Academy Community](https://skool.com/claude-academy)**
