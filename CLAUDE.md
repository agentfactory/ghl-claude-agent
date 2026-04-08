# GHL x Claude Integration Product
## Claude Code Multi-Agent Project

**Project owner:** Denis Laflamme, The Agent Factory / Claude Academy  
**Version:** 1.0  
**Date:** 2026-04-07  
**Target launch:** 7 days from project start

---

## Project Overview

Build and ship a complete commercial product that teaches GoHighLevel users how to connect Claude directly to their GHL account using MCP. The product has two tiers:

- **Free tier:** A professional documentation site (Mintlify) with a step-by-step guide, gated by joining the Claude Academy Skool community (free)
- **Paid tier:** A done-for-you agent pack sold at $97 (special launch price), delivered via Skool paid community

The full launch includes: documentation site, video script, produced YouTube video, paid ad copy, and a packaged downloadable product. All agents run in parallel where possible.

---

## Tech Stack

| Layer | Tool |
|---|---|
| Docs site | Mintlify (pointed at community GHL MCP GitHub repo) |
| Agent framework | Claude Code multi-agent (this file) |
| Video production | YouTube Pipeline skill + Gemini Nano Banana |
| Ad creative | Direct Response Copy skill |
| Community / gating | Skool (Claude Academy) |
| Hosting | Mintlify free tier (docs.claudeacademy.ai or similar) |
| Source repo | github.com/mastanley13/GoHighLevel-MCP |

**Never use:** n8n, Vercel, WSL, em dashes.  
**Always use:** Windows-compatible commands (PowerShell/CMD), Railway if a server is needed, plain English in all public-facing copy.  
**Never say:** "AI" or "automation" in any public-facing materials. Use: assistant, skills, agent, connected system.

---

## Agent Roster

This project uses five specialized agents running in parallel after Agent 1 completes its research pass.

```
Agent 1: Research & Architecture (runs first, feeds all others)
Agent 2: Documentation Site (Mintlify setup + guide content)
Agent 3: YouTube Video Package (script, voiceover, thumbnail, SEO)
Agent 4: Paid Product Package (sales page, deliverable files, Skool setup brief)
Agent 5: Ad Creative (Facebook/Instagram ad copy + YouTube pre-roll script)
```

---

## Agent 1: Research & Architecture

**Role:** Project brain. Gathers all technical facts before other agents write a single word.

**Run this agent first. Block all others until Agent 1 completes.**

### Tasks

1. Fetch and read the GoHighLevel MCP GitHub repo README:
   - `https://github.com/mastanley13/GoHighLevel-MCP`
   - Extract: full tool list, setup steps, required permissions, known limitations, PIT token instructions

2. Fetch the official GHL MCP support article:
   - `https://help.gohighlevel.com/support/solutions/articles/155000005741-how-to-use-the-highlevel-mcp-server`
   - Extract: official scope list, roadmap items, any warnings

3. Fetch the Mintlify auto-generate docs tool:
   - Replace `github.com` with `mintlify.com` in the GHL MCP repo URL
   - Document what gets generated (page structure, nav, sections)

4. Compile a **Technical Facts Sheet** (JSON or Markdown) containing:
   - GHL MCP version and status
   - Full list of available tool categories (from the 269+ tools)
   - Required GHL Private Integration scopes (safe starting set)
   - PIT token generation steps (exact)
   - Location ID retrieval steps (exact)
   - Confirmed Windows-compatible setup commands (PowerShell only)
   - Known issues or gaps (e.g., no native Claude Desktop npx package yet)
   - Official GHL roadmap items

5. Output file: `research/technical-facts.md`

### Handoff

Pass `research/technical-facts.md` to all remaining agents before they begin.

---

## Agent 2: Documentation Site

**Role:** Build the free guide that lives on Mintlify and drives Skool signups.

**Input:** `research/technical-facts.md`

### Site Structure

```
docs/
  index.mdx           (Welcome + what this guide covers)
  quickstart.mdx      (The 15-minute setup, step by step)
  concepts/
    what-is-mcp.mdx   (Plain English: what MCP actually does)
    ghl-agent.mdx     (What your Claude agent can now do in GHL)
  setup/
    step-1-pit.mdx    (Create your Private Integration + PIT token)
    step-2-location.mdx (Find your Location ID)
    step-3-connect.mdx  (Connect Claude Desktop or Claude Code)
    step-4-test.mdx     (Run your first live test)
  use-cases/
    lead-qualifier.mdx  (Prompt: qualify a new lead)
    follow-up.mdx       (Prompt: write a personalized follow-up)
    pipeline-mover.mdx  (Prompt: move a contact through stages)
    appointment.mdx     (Prompt: book an appointment)
  community.mdx       (CTA: join Claude Academy free + what you get)
  paid-pack.mdx       (CTA: upgrade to the $97 agent pack)
```

### Writing Rules

- Every page must be readable by a GHL agency owner with no developer background
- No code blocks longer than 10 lines without a plain-English explanation above them
- Every step must include a "What you should see" confirmation sentence
- Maximum 3 screenshots or visual references per page (note them as [SCREENSHOT: description])
- Windows-first: all terminal commands are PowerShell, not bash
- Tone: calm, direct, like a knowledgeable colleague explaining over Slack

### Mintlify Config

Generate a `mint.json` file with:

```json
{
  "name": "Claude Academy: GHL Agent Guide",
  "logo": {
    "light": "/logo/claude-academy-light.png",
    "dark": "/logo/claude-academy-dark.png"
  },
  "favicon": "/favicon.png",
  "colors": {
    "primary": "#E8671B",
    "light": "#F59E4F",
    "dark": "#C45510"
  },
  "topbarLinks": [
    { "name": "Claude Academy", "url": "https://skool.com/claude-academy" }
  ],
  "topbarCtaButton": {
    "name": "Get the $97 Pack",
    "url": "https://skool.com/claude-academy/paid"
  },
  "navigation": [
    {
      "group": "Start Here",
      "pages": ["index", "quickstart"]
    },
    {
      "group": "Understand the Setup",
      "pages": ["concepts/what-is-mcp", "concepts/ghl-agent"]
    },
    {
      "group": "Step-by-Step Setup",
      "pages": ["setup/step-1-pit", "setup/step-2-location", "setup/step-3-connect", "setup/step-4-test"]
    },
    {
      "group": "Use Cases",
      "pages": ["use-cases/lead-qualifier", "use-cases/follow-up", "use-cases/pipeline-mover", "use-cases/appointment"]
    },
    {
      "group": "Join the Community",
      "pages": ["community", "paid-pack"]
    }
  ],
  "footerSocials": {
    "youtube": "https://youtube.com/@claudeacademy"
  }
}
```

### Community Gate (Bottom of every page)

Every page ends with this block:

```mdx
---

## Want the done-for-you version?

This guide shows you how to set it up yourself.

If you want pre-built agent configurations, tested prompts for the 4 most common GHL workflows, and a private community to ask questions, the Claude Academy Agent Pack has everything ready to go.

**[Join Claude Academy free](https://skool.com/claude-academy)** to get this guide plus the resource library.

**[Get the $97 Agent Pack](https://skool.com/claude-academy/paid)** for the complete done-for-you setup.
```

### Output Files

- All `.mdx` files in the `docs/` folder structure above
- `mint.json`
- `README.md` for the GitHub repo (2-paragraph summary of what the site is)

---

## Agent 3: YouTube Video Package

**Role:** Produce the complete video package that drives traffic to the free guide and the $97 paid pack.

**Input:** `research/technical-facts.md`

**Run the full 6-phase YouTube Pipeline on this topic:**

```
RUN PIPELINE: How to Connect Claude to GoHighLevel Using MCP (No Zapier, No Make, No Code)
```

### Specific Constraints for This Video

- Target length: 8-12 minutes (enough depth to demonstrate real value)
- Hook angle: "I gave Claude full access to my GoHighLevel account. Here's what happened."
- Blue Ocean gap: No one has made a beginner-friendly video on the GHL native MCP. Most content is either for developers or buried in documentation.
- CTA in video: Drive to the free Mintlify guide, then to the $97 pack
- One live demo segment must be scripted: Claude moving a contact through a pipeline stage using only natural language
- End screen: Link to next video (TBD) and subscribe

### Thumbnail Brief Override

Thumbnail concept: Split screen. Left side: GHL dashboard with pipeline. Right side: Claude chat bubble giving instructions. Text overlay: "CLAUDE RUNS GHL" in bold white on dark background.

Nano Banana Pro prompt for thumbnail:
```
YouTube thumbnail, 16:9 aspect ratio, split screen design, left half shows GoHighLevel CRM pipeline dashboard on a laptop screen with glowing UI elements, right half shows a Claude.ai chat interface with a text bubble visible, dark background with orange and white accent colors, bold white text overlay reading "CLAUDE RUNS GHL" in the center-top area, high contrast, mobile-readable, professional and clean, no faces, tech aesthetic
```

### Output File

`video/YT-Package-GHL-Claude-MCP-2026-04-07.md`

Follows the standard YouTube Pipeline output format (all 6 phases).

---

## Agent 4: Paid Product Package

**Role:** Build everything that goes inside the $97 paid product and the Skool sales brief.

**Input:** `research/technical-facts.md`

### What the $97 Pack Contains

Generate all of the following files:

#### 4A: Agent Configuration Pack

File: `product/agent-configs.md`

Four pre-built Claude system prompts, each formatted as a ready-to-paste configuration:

1. **Lead Qualifier Agent**
   - System prompt that instructs Claude to: pull a new contact from GHL, assess their info against a qualification checklist, tag them as Hot/Warm/Cold, and add a note summarizing the assessment
   - Includes placeholder variables the buyer fills in: `[YOUR_QUALIFICATION_CRITERIA]`, `[YOUR_HOT_TAG]`, etc.

2. **Follow-Up Writer Agent**
   - System prompt that instructs Claude to: pull a contact's conversation history from GHL, write a personalized follow-up message in the user's voice, and either save it as a draft or send it
   - Includes a "Voice Profile" placeholder: `[PASTE 3 EXAMPLES OF YOUR FOLLOW-UP STYLE HERE]`

3. **Pipeline Manager Agent**
   - System prompt that instructs Claude to: review all contacts in a specified pipeline stage, identify who hasn't been touched in X days, move stalled contacts to a "Needs Attention" stage, and generate a summary report
   - Includes configurable: `[STAGE_NAME]`, `[DAYS_THRESHOLD]`

4. **Appointment Setter Agent**
   - System prompt that instructs Claude to: check GHL calendar availability, respond to a lead's appointment request with available slots, and book the appointment when confirmed
   - Includes configurable: `[CALENDAR_ID]`, `[YOUR_TIMEZONE]`

#### 4B: Quick-Start Checklist

File: `product/quickstart-checklist.md`

A single-page PDF-ready checklist (Markdown formatted) with:
- Pre-flight (GHL account type requirements, API access confirmation)
- Setup (PIT token, Location ID, connection test)
- Agent deployment (paste prompt, name the agent, test with one contact)
- Go-live (permission review, backup workflow reminder)

#### 4C: Prompt Library

File: `product/prompt-library.md`

20 ready-to-use Claude prompts organized by GHL function:
- Contacts (5 prompts): create, search, tag, update, merge
- Conversations (4 prompts): summarize, draft reply, flag urgent, archive
- Pipeline (4 prompts): move stage, list stalled, generate report, bulk tag
- Calendar (4 prompts): check availability, book appointment, reschedule, cancel
- Reporting (3 prompts): weekly pipeline summary, lead source breakdown, team activity report

Each prompt follows this format:
```
**Prompt Name:** [Name]
**Use when:** [One sentence trigger]
**Prompt:**
[The actual prompt with [PLACEHOLDER] variables]
**Expected output:** [What Claude will return]
```

#### 4D: Skool Sales Page Brief

File: `product/skool-sales-brief.md`

A brief for Denis to configure the Skool paid community sales page, including:

- **Headline:** "Connect Claude to GoHighLevel in 15 Minutes. Then Let It Run Your CRM."
- **Subheadline:** "The done-for-you agent pack for GHL users who want Claude handling lead qualification, follow-ups, pipeline management, and booking. No Zapier. No Make. No developer."
- **Price display:** ~~$197~~ $97 (Launch Special)
- **What's included bullet list** (5 items max, plain English)
- **Guarantee language:** "If you follow the setup guide and it doesn't work, message us in the community and we'll fix it with you."
- **FAQ:** 5 questions (write them)
- **Urgency/scarcity note:** "Launch pricing. Price goes to $197 when the promo ends."

---

## Agent 5: Ad Creative

**Role:** Generate all paid ad copy to drive traffic to the free guide and the $97 pack.

**Input:** `research/technical-facts.md` + `product/skool-sales-brief.md` (from Agent 4)

### Ad Set 1: Free Guide (Lead Gen, drives to Mintlify site / Skool free signup)

#### Facebook/Instagram Ad (3 variations)

Format each as:
```
VARIATION [A/B/C]
Hook (first line, must stop the scroll):
Body (2-4 sentences, no em dashes):
CTA button text:
```

Angles to use:
- A: Pain/problem angle ("Your GHL has Claude in it. You're just not using it.")
- B: Curiosity angle ("I gave Claude full control of my GoHighLevel. Here's the screenshot.")
- C: Result angle ("Lead qualified. Follow-up written. Pipeline updated. Claude did all of it.")

#### YouTube Pre-Roll Script (30 seconds, non-skippable format)

```
[0-5 sec]: Pattern interrupt / hook (must work before skip button appears)
[5-20 sec]: Problem + solution setup
[20-25 sec]: Social proof or specificity ("269 tools, zero Zapier")
[25-30 sec]: CTA with URL
```

### Ad Set 2: Paid Pack (Conversion, drives to $97 Skool purchase)

#### Facebook/Instagram Ad (2 variations)

- Variation A: Direct offer ("$97 gets you 4 pre-built Claude agents for your GHL account.")
- Variation B: Objection-handling ("You don't need a developer. You don't need Zapier. You need this prompt pack and 15 minutes.")

#### Retargeting Ad (1 variation, shown to people who visited the free guide but didn't buy)

```
Hook: They already know the problem. Lead with the solution and the price.
Body: Ultra short. Price. What they get. Link.
CTA: "Get the Pack"
```

### Nano Banana Prompts for Ad Images

Generate 3 Nano Banana 2 image prompts for the ad creative:

1. Split-screen concept (GHL dashboard + Claude chat)
2. Before/after concept (overwhelmed CRM vs. clean pipeline with Claude note)
3. Phone mockup concept (GHL app on phone, Claude message visible)

### Output File

`ads/ad-creative-package.md`

---

## File Structure

```
project/
  CLAUDE.md                         (this file)
  research/
    technical-facts.md              (Agent 1 output)
  docs/                             (Agent 2 output - Mintlify site)
    mint.json
    README.md
    index.mdx
    quickstart.mdx
    concepts/
    setup/
    use-cases/
    community.mdx
    paid-pack.mdx
  video/                            (Agent 3 output)
    YT-Package-GHL-Claude-MCP-2026-04-07.md
  product/                          (Agent 4 output)
    agent-configs.md
    quickstart-checklist.md
    prompt-library.md
    skool-sales-brief.md
  ads/                              (Agent 5 output)
    ad-creative-package.md
```

---

## Execution Order

```
Phase 1 (blocking): Run Agent 1 only. Do not proceed until technical-facts.md exists.

Phase 2 (parallel): Run Agents 2, 3, 4, and 5 simultaneously using technical-facts.md as shared input.
  Agent 4 must complete skool-sales-brief.md before Agent 5 can finalize ad copy.
  All other agents are fully independent.

Phase 3 (review): Denis reviews all outputs. Mark each file APPROVED or NEEDS REVISION.
```

---

## Quality Standards

Every file produced must pass these checks before being marked complete:

- No em dashes anywhere
- No use of "AI" or "automation" in public-facing text (use: agent, assistant, skills, connected system)
- No Vercel references
- All terminal/CLI commands are Windows PowerShell compatible
- No sentences over 25 words in public-facing copy
- Every CTA points to the correct URL (Skool free or Skool paid)
- Tone throughout: calm, direct, competent. Not hype. Not robotic.

---

## Success Criteria

| Deliverable | Done when |
|---|---|
| `technical-facts.md` | All GHL MCP setup steps verified and documented |
| Mintlify docs site | 10 pages complete, mint.json valid, deployable |
| YouTube video package | All 6 phases complete, quality check APPROVED |
| Agent config pack | 4 system prompts written and tested with placeholder variables |
| Prompt library | 20 prompts written in standard format |
| Skool sales brief | Headline, body, pricing, FAQ complete |
| Ad creative package | 5 ad variations + 3 Nano Banana prompts |

---

## Notes for Claude Code

- If you encounter a GHL API endpoint that requires a scope not in the safe starting set, flag it in the research file and do not include it in the beginner guide.
- If the Mintlify auto-generate URL returns an error or unusable output, proceed with manually structured MDX files using the file structure above.
- The Skool community URLs are placeholders. Denis will replace them with live URLs before publish.
- The $97 price point is final for launch. Do not suggest alternatives.
- All four agent system prompts in the product pack must be tested by prompting Claude with a sample GHL scenario and confirming the output makes sense. Document any prompt that fails with a "NEEDS REVIEW" flag.
