# YouTube Video Package
## How to Connect Claude to GoHighLevel Using MCP (No Zapier, No Make, No Code)

**Package Date:** 2026-04-07
**Target Length:** 8-12 minutes
**Channel:** Claude Academy

---

# PHASE 1: RESEARCH & POSITIONING

## Target Audience Profile

| Attribute | Detail |
|-----------|--------|
| **Primary** | GHL agency owners, age 25-55 |
| **Technical level** | Non-developer. Comfortable with SaaS dashboards but not code. |
| **Pain point** | Spending hours on manual CRM tasks: qualifying leads, writing follow-ups, moving pipeline stages, booking appointments |
| **Current tools** | GoHighLevel, maybe Zapier or Make for basic connections |
| **Desire** | A smarter assistant inside their CRM that handles the repetitive work |
| **Objection** | "I'm not technical enough" / "This sounds like it needs a developer" |
| **Where they hang out** | YouTube, Skool communities, Facebook groups for GHL users |

## Blue Ocean Analysis

**What exists today:**
- Developer-focused MCP tutorials aimed at engineers
- Generic "What is MCP?" explainer videos with no GHL context
- GHL tutorial channels that cover native features but not Claude integration
- A handful of Zapier/Make integration videos for GHL (outdated approach)

**What is missing:**
- A beginner-friendly walkthrough connecting Claude directly to GHL
- A video that shows the native MCP connection (no middleware)
- Real demonstrations of Claude performing CRM tasks in plain English
- Content that positions this as a 15-minute setup, not a dev project

**Our angle:**
Claude now connects directly to GoHighLevel through MCP. No Zapier. No Make. No developer. This video is the first to show a non-technical GHL user exactly how to set it up and what it looks like in action.

## Competitor Video Audit

| # | Video/Channel | Views | Gap We Fill |
|---|--------------|-------|-------------|
| 1 | "What is MCP? Model Context Protocol Explained" (various channels) | 50K-200K | Too abstract. No GHL context. No live demo. |
| 2 | "GoHighLevel Zapier Integration Tutorial" (GHL community channels) | 10K-30K | Uses middleware. More expensive. More fragile. |
| 3 | "Claude Desktop MCP Setup" (dev channels) | 5K-15K | Developer audience. Terminal commands. No CRM use case. |
| 4 | "GoHighLevel API Tutorial" (GHL power users) | 8K-20K | Requires coding knowledge. API keys, Postman, JSON. |
| 5 | "Make.com + GoHighLevel Workflows" (Make community) | 15K-40K | Middleware dependency. Monthly cost. Complex scenario builder. |

**Key gap:** Nobody has made a "here is Claude talking directly to your GHL account" video for agency owners. We own this topic.

## Search Intent Mapping

| Search Query | Monthly Volume (Est.) | Intent | Our Match |
|-------------|----------------------|--------|-----------|
| "GoHighLevel MCP" | Rising (new term) | Informational | Direct match |
| "connect Claude to GoHighLevel" | Low but growing | How-to | Exact match |
| "GoHighLevel automation without Zapier" | Medium | Solution-seeking | Strong match |
| "Claude MCP setup" | Medium | How-to | Partial match |
| "GoHighLevel CRM assistant" | Medium | Solution-seeking | Strong match |
| "MCP server GoHighLevel" | Low | Technical | Match |
| "Claude for business CRM" | Medium | Exploratory | Good match |
| "GoHighLevel lead qualification" | High | Feature-seeking | Use case match |
| "no code CRM automation" | High | Solution-seeking | Strong match (but avoid "automation" in our copy) |

---

# PHASE 2: FULL SCRIPT

## Pre-Production Notes

- **Total runtime target:** 9-10 minutes
- **Pacing:** Conversational, not rushed. Pause after key moments.
- **Camera:** Talking head for hook, problem, and CTA sections. Screen recording for setup and demo.
- **B-roll:** Minimal. Clean cuts between talking head and screen.

---

### HOOK (0:00 - 0:30)

**[CAMERA: Talking head, medium shot, clean background]**

I gave Claude full access to my GoHighLevel account. Here is what happened.

**[SCREEN: Quick montage, 2 seconds each: Claude chat window typing a command, GHL pipeline updating, a contact moving stages, a follow-up message appearing]**

It qualified a lead. Wrote a follow-up. Moved contacts through my pipeline. Booked an appointment. All from a single chat window.

No Zapier. No Make. No code. Just Claude connected straight to GHL.

**[CAMERA: Back to talking head]**

In this video, I will show you exactly how to set this up in about 15 minutes. And I will show you what it looks like when Claude runs your CRM for you.

---

### PROBLEM (0:30 - 1:30)

**[CAMERA: Talking head]**

If you run an agency on GoHighLevel, you already know the daily grind.

New leads come in. You have to look at each one. Decide if they are worth pursuing. Write a follow-up. Move them through your pipeline. Check if someone booked. Follow up again if they did not.

**[B-roll: GHL dashboard with a full pipeline, lots of contacts, unread messages indicator]**

It is repetitive. It is time-consuming. And honestly, it is the kind of work that does not need you personally doing it every single time.

Now, most people try to solve this with Zapier or Make. You set up a trigger, connect some steps, and hope it works.

**[B-roll: Quick flash of a Zapier/Make workflow with multiple nodes]**

But those tools are middleware. They sit between your systems. They cost money every month. They break when something changes. And they cannot think. They just follow a flowchart.

What if your CRM had an actual assistant built in? One that understands what you are asking in plain English?

That is what this setup gives you.

---

### SOLUTION INTRO (1:30 - 3:00)

**[CAMERA: Talking head]**

GoHighLevel now supports something called MCP. It stands for Model Context Protocol. But you do not need to remember that.

Here is what matters: MCP is a direct connection between Claude and your GHL account. No middleman. No extra tools. Claude can read your contacts, update your pipeline, send messages, check calendars, and more.

**[SCREEN: Show the GHL MCP documentation page briefly]**

There are over 269 tools available across 19 categories. That covers contacts, conversations, calendars, opportunities, workflows, and a lot more.

**[CAMERA: Talking head]**

Think of it like giving Claude a set of keys to your GHL account. You decide which doors those keys open. Claude can only do what you give it permission to do.

And the best part? The setup takes about 15 minutes. You need three things:

One. A Private Integration Token from your GHL account.
Two. Your Location ID.
Three. Claude Desktop or Claude Code on your computer.

That is it. Let me walk you through each step right now.

---

### SETUP WALKTHROUGH (3:00 - 6:00)

**[SCREEN: GHL dashboard, logged in]**

#### Step 1: Create Your Private Integration Token (3:00 - 4:15)

**[SCREEN: Navigate to Settings in GHL]**

First, we need to create a Private Integration Token. This is how Claude authenticates with your GHL account.

Go to Settings, then Integrations, then Private Integrations.

**[SCREEN: Click through each menu item]**

Click "Create New Integration." Give it a name. I am calling mine "Claude Assistant."

**[SCREEN: Show the naming field, type "Claude Assistant"]**

Now we need to set the scopes. These are the permissions. Start with these safe defaults:

- contacts.readonly
- contacts.write
- conversations.readonly
- conversations.write
- opportunities.readonly
- opportunities.write
- calendars.readonly
- calendars.write
- locations.readonly
- workflows.readonly
- users.readonly

**[SCREEN: Check each scope as you mention it]**

That gives Claude enough access for the four main use cases: lead qualification, follow-ups, pipeline management, and appointment booking.

Click Save. Now copy your Private Integration Token. Keep it somewhere safe. You will need it in a moment.

**[SCREEN: Show the token generated, highlight the copy button. Blur the actual token value.]**

**What you should see:** A long string of characters. That is your PIT. Do not share it publicly.

#### Step 2: Find Your Location ID (4:15 - 4:45)

**[SCREEN: GHL dashboard, navigate to Settings > Business Profile or Company]**

Your Location ID tells Claude which GHL sub-account to connect to.

Go to Settings. Click on Business Profile. Your Location ID is right here in the URL bar, or listed on the page.

**[SCREEN: Highlight the Location ID in the URL or on the settings page]**

Copy that. You now have both pieces you need.

**What you should see:** A string that looks something like "abc123XYZ." That is your Location ID.

#### Step 3: Connect Claude Desktop (4:45 - 6:00)

**[SCREEN: Open Claude Desktop settings/config file]**

Now open Claude Desktop. Go to Settings, then the MCP configuration.

You are going to add a new MCP server entry. Here is what it looks like:

**[SCREEN: Show the configuration being typed/pasted]**

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

Replace YOUR_PIT_TOKEN_HERE with the token you copied. Replace YOUR_LOCATION_ID_HERE with the Location ID from the previous step. Save the file. Restart Claude Desktop.

**[SCREEN: Show saving and restarting]**

When Claude restarts, you should see a small hammer icon or a tools indicator showing that MCP tools are connected.

**[SCREEN: Point to the MCP tools indicator in Claude Desktop]**

**What you should see:** The tools indicator showing 269 available tools. If you see that, you are connected.

That is it. Three steps. Your Claude now has direct access to your GoHighLevel account.

---

### LIVE DEMO (6:00 - 8:30)

**[CAMERA: Talking head, brief]**

Now let me show you what this actually looks like. I am going to give Claude a simple task in plain English and you will see it happen live in GHL.

**[SCREEN: Claude Desktop chat window, empty conversation]**

#### Demo 1: Moving a Contact Through the Pipeline (6:15 - 7:15)

I am going to type a simple request.

**[SCREEN: Type into Claude chat]**

> Move Sarah Thompson from the "New Lead" stage to the "Qualified" stage in my sales pipeline.

**[SCREEN: Show Claude processing, calling the GHL MCP tools]**

Watch what happens. Claude finds Sarah Thompson in my contacts. It identifies the correct pipeline. It locates the "New Lead" stage and the "Qualified" stage. And it moves her.

**[SCREEN: Claude responds with confirmation, something like: "Done. I moved Sarah Thompson from New Lead to Qualified in your Sales Pipeline. She is now in the Qualified stage."]**

Let me verify that in GHL.

**[SCREEN: Switch to GHL, open the Sales Pipeline, show Sarah Thompson now sitting in the Qualified column]**

There she is. Qualified. One sentence in Claude. Done.

#### Demo 2: Writing a Follow-Up (7:15 - 8:00)

Let me try another one.

**[SCREEN: Back to Claude chat]**

> Look at my last conversation with James Parker and write a personalized follow-up message. Do not send it yet. Just draft it.

**[SCREEN: Claude processes, pulls conversation history, writes a draft]**

Claude pulls the conversation history from GHL. It reads what was discussed. And it writes a follow-up that actually references the specifics.

**[SCREEN: Show Claude's drafted message, which references details from the conversation]**

That is not a generic template. Claude read the actual conversation and wrote something relevant.

#### Demo 3: Quick Pipeline Summary (8:00 - 8:30)

One more.

**[SCREEN: Claude chat]**

> How many contacts are in each stage of my Sales Pipeline right now?

**[SCREEN: Claude responds with a breakdown: New Lead: 12, Qualified: 8, Proposal Sent: 3, Won: 5]**

Instant pipeline report. No dashboard clicking. No exports. Just ask.

**[CAMERA: Talking head]**

That is what a connected assistant looks like. You talk to it like a person. It does the work inside your CRM.

---

### RESULTS + CTA (8:30 - 10:00)

**[CAMERA: Talking head]**

So here is what we just did.

In about 15 minutes, we connected Claude directly to GoHighLevel. No Zapier subscription. No Make scenarios. No developer.

And Claude can now:
- Qualify leads based on your criteria
- Write personalized follow-ups using real conversation history
- Move contacts through your pipeline
- Check calendar availability and book appointments
- Give you instant reports on your pipeline

**[B-roll: Quick recap montage of the three demos]**

If you want to follow along step by step, I built a free guide that walks through everything we just covered, with screenshots and troubleshooting tips.

**[SCREEN: Show docs.claudeacademy.ai landing page]**

Go to docs.claudeacademy.ai. The full guide is there. Free. No email required. Just join the Claude Academy community on Skool to access it.

**[CAMERA: Talking head]**

And if you want the done-for-you version, I put together an agent pack with four pre-built Claude configurations for the most common GHL workflows. Lead qualifier. Follow-up writer. Pipeline manager. Appointment setter. Each one is ready to paste and go.

That is the Claude Academy Agent Pack. It is 97 dollars during launch week. Link is in the description.

**[SCREEN: Show the Skool paid pack page briefly]**

---

### OUTRO (10:00 - 10:30)

**[CAMERA: Talking head]**

This is just the beginning. GHL is adding more MCP capabilities, including OAuth support soon. I will be covering every update on this channel.

If this was helpful, subscribe. Hit the bell. And drop a comment telling me what you want Claude to do in your GHL account. I read every one.

**[SCREEN: End screen with subscribe button, next video card, and link to free guide]**

I will see you in the next one.

---

# PHASE 3: SEO & METADATA

## Title

**Connect Claude to GoHighLevel with MCP (Free Setup)**

(57 characters, includes primary keywords: Claude, GoHighLevel, MCP)

## Description

```
Connect Claude directly to your GoHighLevel account using MCP. No Zapier. No Make. No code. This step-by-step tutorial shows you exactly how to set it up in 15 minutes and gives you a live demo of Claude managing your CRM.

FREE STEP-BY-STEP GUIDE: https://docs.claudeacademy.ai
JOIN CLAUDE ACADEMY (FREE): https://skool.com/claude-academy
GET THE $97 AGENT PACK: https://skool.com/claude-academy/paid

What you will learn:
- How to create a Private Integration Token (PIT) in GoHighLevel
- How to find your Location ID
- How to configure Claude Desktop to connect to GHL via MCP
- Live demos: moving contacts through pipelines, writing follow-ups, generating pipeline reports

Claude can now access 269+ tools across 19 categories inside GoHighLevel. That means contacts, conversations, calendars, pipelines, workflows, and more. All controlled through plain English in a chat window.

This video covers the official GHL MCP endpoint and does not require any middleware, third-party connectors, or developer skills.

TIMESTAMPS:
0:00 - Hook: What happens when Claude gets GHL access
0:30 - The problem with manual CRM work
1:30 - What MCP is and why it matters
3:00 - Step 1: Create your Private Integration Token
4:15 - Step 2: Find your Location ID
4:45 - Step 3: Connect Claude Desktop
6:00 - Live Demo: Moving a contact through a pipeline
7:15 - Live Demo: Writing a personalized follow-up
8:00 - Live Demo: Instant pipeline report
8:30 - What Claude can do in your GHL account
9:30 - Free guide and agent pack
10:00 - What is coming next

RESOURCES:
- GHL MCP GitHub Repo: https://github.com/mastanley13/GoHighLevel-MCP
- GHL MCP Official Docs: https://help.gohighlevel.com/support/solutions/articles/155000005741
- Claude Desktop: https://claude.ai/download

This is a Claude Academy production. We teach business owners how to use Claude as a real working assistant, not a chatbot.

#GoHighLevel #Claude #MCP #CRM #GHL
```

(Approx. 1,850 characters)

## Tags

1. GoHighLevel
2. Claude
3. MCP
4. Model Context Protocol
5. GoHighLevel MCP
6. Claude MCP setup
7. connect Claude to GoHighLevel
8. GHL CRM
9. GoHighLevel tutorial
10. Claude Desktop
11. GHL assistant
12. CRM assistant
13. GoHighLevel agent
14. no code CRM
15. GoHighLevel no Zapier
16. Claude for business
17. GHL pipeline
18. lead qualification
19. CRM follow up
20. GoHighLevel setup
21. Claude Academy
22. GHL API
23. Private Integration Token
24. Claude tools
25. GHL workflows
26. CRM management
27. GoHighLevel tips
28. Claude tutorial
29. MCP server setup
30. business CRM tools

## Hashtags

#GoHighLevel #Claude #MCP #CRM #GHL

## Category Recommendation

**Science & Technology** (Category ID: 28)

Secondary consideration: Education, but Science & Technology reaches the right audience for this type of software walkthrough content.

## Publish Timing Recommendation

**Day:** Tuesday or Wednesday
**Time:** 9:00 AM EST

Reasoning: B2B SaaS audience is most active mid-week during morning hours. GHL users tend to be agency owners who plan their week on Tuesday/Wednesday mornings. Avoid Monday (inbox overload) and Friday (winding down).

---

# PHASE 4: THUMBNAIL BRIEF

## Primary Concept

**Visual:** Split screen. Left half shows a GHL dashboard with a pipeline view. Right half shows a Claude chat window with a visible text bubble.
**Text overlay:** "CLAUDE RUNS GHL" in bold white on dark background.
**Color scheme:** Dark background with orange (#E8671B) and white accent colors.
**Style:** High contrast, mobile-readable, professional and clean. No faces.

### Nano Banana Pro Prompt (Primary)

```
YouTube thumbnail, 16:9 aspect ratio, split screen design, left half shows GoHighLevel CRM pipeline dashboard on a laptop screen with glowing UI elements, right half shows a Claude.ai chat interface with a text bubble visible, dark background with orange and white accent colors, bold white text overlay reading "CLAUDE RUNS GHL" in the center-top area, high contrast, mobile-readable, professional and clean, no faces, tech aesthetic
```

## Alternative Concept A: The Command

**Visual:** Claude chat window taking up 70% of the frame. A single typed message visible: "Move Sarah to Qualified." Below it, a GHL pipeline snapshot showing the move happening.
**Text overlay:** "ONE MESSAGE" in bold orange at the top.

### Nano Banana Pro Prompt (Alt A)

```
YouTube thumbnail, 16:9 aspect ratio, dark navy background, large Claude.ai chat window taking up most of the frame with a visible typed message "Move Sarah to Qualified" in white text, below the chat window a small GoHighLevel pipeline bar showing a contact card moving between stages with an orange arrow, bold orange text overlay reading "ONE MESSAGE" at the top center, clean minimalist design, high contrast, mobile-readable, no faces, tech aesthetic
```

## Alternative Concept B: Before/After

**Visual:** Left side labeled "BEFORE" showing a messy GHL dashboard with unread notifications and a cluttered pipeline. Right side labeled "AFTER" showing a clean pipeline with a Claude chat bubble in the corner indicating work is done.
**Text overlay:** "BEFORE" (red) on left, "AFTER" (green) on right, with "CLAUDE + GHL" centered at the bottom.

### Nano Banana Pro Prompt (Alt B)

```
YouTube thumbnail, 16:9 aspect ratio, split screen before and after comparison, left half labeled BEFORE in red text showing a cluttered CRM dashboard with many notifications and messy pipeline stages, right half labeled AFTER in green text showing a clean organized CRM pipeline with a small Claude chat bubble in the corner, dark background, bold white text reading "CLAUDE + GHL" centered at the bottom, orange accent highlights, high contrast, mobile-readable, professional, no faces, tech aesthetic
```

## Thumbnail A/B Test Plan

- Test Primary vs. Alt A first (split screen vs. single command concept)
- Run for 48 hours, measure CTR difference
- Winner faces Alt B in round two
- Target CTR benchmark: 6-8% for this niche

---

# PHASE 5: CONTENT REPURPOSING PLAN

## Short-Form Clips (YouTube Shorts / TikTok / Reels)

### Clip 1: "The Pipeline Move"
- **Timestamp:** 6:15 - 7:15
- **Hook:** "Watch Claude move a contact through my GHL pipeline with one sentence."
- **Format:** Screen recording only, text overlay hook at top, fast-paced
- **Duration:** 45-55 seconds

### Clip 2: "The Follow-Up Writer"
- **Timestamp:** 7:15 - 8:00
- **Hook:** "Claude just read my GHL conversation and wrote a better follow-up than I would."
- **Format:** Screen recording with reaction-style text overlays
- **Duration:** 40-50 seconds

### Clip 3: "15 Minutes, 269 Tools"
- **Timestamp:** 1:30 - 3:00 (edited down to key points)
- **Hook:** "I connected Claude to GoHighLevel in 15 minutes. It now has access to 269 tools."
- **Format:** Talking head with quick cuts, stats on screen
- **Duration:** 30-40 seconds

## Twitter/X Thread Outlines

### Thread 1: "The Setup Thread"

1/ I connected Claude directly to my GoHighLevel account yesterday. No Zapier. No Make. No developer. Here is exactly what I did and what happened (thread):

2/ GoHighLevel now supports MCP natively. That means Claude can talk directly to your CRM. 269 tools across 19 categories. Contacts, conversations, pipelines, calendars, workflows.

3/ Setup took 3 steps: Create a Private Integration Token in GHL. Find your Location ID. Add one config block to Claude Desktop. Total time: about 15 minutes.

4/ First test: I asked Claude to move Sarah Thompson from "New Lead" to "Qualified" in my sales pipeline. One sentence. Done. Verified it in GHL. She moved.

5/ Second test: Asked Claude to read my last conversation with a lead and draft a follow-up. It pulled the actual conversation, referenced specific details, and wrote something I would send.

6/ Third test: Asked for a pipeline summary. Instant breakdown of how many contacts are in each stage. No dashboard clicking.

7/ Full free guide with screenshots and config code: docs.claudeacademy.ai. If you want pre-built prompts for the 4 main use cases, the Claude Academy Agent Pack is $97 during launch.

### Thread 2: "The Why It Matters Thread"

1/ Every GHL agency owner I talk to has the same problem. They spend more time managing their CRM than growing their business. Here is why that changes now.

2/ The old way: Lead comes in. You check it. You qualify it. You write a follow-up. You move the pipeline stage. You check the calendar. You book the call. Repeat 20 times a day.

3/ The middleware way: Set up Zapier or Make. Build a scenario. Test it. Fix it when it breaks. Pay $30-100/month for the privilege. Still cannot handle nuance.

4/ The new way: Claude connects directly to GHL through MCP. You type "qualify this lead." Claude reads their info, applies your criteria, tags them, and adds a note. One sentence.

5/ The difference: middleware follows a flowchart. Claude understands context. It reads conversations. It makes judgment calls based on criteria you set. It handles the nuance.

6/ Full setup guide (free): docs.claudeacademy.ai

## LinkedIn Post Draft

**Headline:** I gave Claude direct access to my GoHighLevel CRM. Here is what a Tuesday morning looks like now.

**Body:**

Last week I spent about 15 minutes connecting Claude to my GHL account through MCP (Model Context Protocol).

No Zapier. No Make. No developer. Just a direct connection.

Now when a new lead comes in, I open Claude and type: "Check this lead against my qualification criteria and tag them."

Claude pulls their info from GHL. Reviews it. Tags them as Hot, Warm, or Cold. Adds a note explaining why.

When I need a follow-up, I type: "Read my last conversation with this contact and draft a follow-up in my voice."

Claude reads the actual conversation. References what was discussed. Writes something I would actually send.

Pipeline check? "How many contacts are in each stage right now?" Instant answer.

This is not about replacing your team. It is about removing the repetitive CRM tasks that eat your mornings.

The setup guide is free: docs.claudeacademy.ai

If you want pre-built agent configurations for the four most common GHL workflows, the Claude Academy Agent Pack is available at skool.com/claude-academy.

## Blog Post Outline (for claudeacademy.ai)

**Title:** How to Connect Claude to GoHighLevel Using MCP: The Complete Guide

1. **Introduction** - What this guide covers and who it is for
2. **What is MCP?** - Plain English explanation, no jargon
3. **Why direct connection beats middleware** - Zapier/Make comparison
4. **What Claude can do inside GHL** - Overview of 269 tools, 19 categories
5. **Prerequisites** - GHL account type, Claude Desktop or Claude Code
6. **Step 1: Create your Private Integration Token** - Screenshots, scope recommendations
7. **Step 2: Find your Location ID** - Where to look, what it looks like
8. **Step 3: Configure Claude Desktop** - Config code, save, restart
9. **Step 4: Test your connection** - First command to run, what to expect
10. **Four practical use cases with prompts** - Lead qualification, follow-ups, pipeline management, appointments
11. **Troubleshooting common issues** - Token errors, scope problems, connection drops
12. **What is coming next** - OAuth support, expanded tools, roadmap
13. **Free resources and next steps** - Link to docs site, community, agent pack

---

# PHASE 6: PERFORMANCE TRACKING

## KPIs to Track

| Metric | Target (30 days) | Tool |
|--------|------------------|------|
| **CTR (Click-Through Rate)** | 6-8% | YouTube Studio |
| **Average View Duration** | 55%+ of total length (5+ min) | YouTube Studio |
| **Views (first 48 hours)** | 500+ | YouTube Studio |
| **Views (first 30 days)** | 3,000+ | YouTube Studio |
| **Docs site visits from YouTube** | 200+ clicks | UTM tracking via analytics |
| **Skool free signups from YouTube** | 50+ | Skool dashboard + UTM |
| **$97 pack purchases from YouTube** | 10+ | Skool dashboard + UTM |
| **Subscribe rate** | 3-5% of viewers | YouTube Studio |
| **Comments** | 30+ in first week | YouTube Studio |
| **Shares** | 20+ in first 30 days | YouTube Studio |

## UTM Parameters

Use these on all links in the description:

- Docs site: `docs.claudeacademy.ai?utm_source=youtube&utm_medium=video&utm_campaign=ghl-mcp-launch`
- Skool free: `skool.com/claude-academy?utm_source=youtube&utm_medium=video&utm_campaign=ghl-mcp-launch`
- Skool paid: `skool.com/claude-academy/paid?utm_source=youtube&utm_medium=video&utm_campaign=ghl-mcp-launch`

## A/B Test Recommendations

### Thumbnail Test
- **Test 1:** Primary (split screen) vs. Alt A (single command)
- **Duration:** 48 hours minimum
- **Decision metric:** CTR
- **Action:** Winner becomes default. Test winner vs. Alt B at day 7.

### Title Test
- **Option A:** "Connect Claude to GoHighLevel with MCP (Free Setup)"
- **Option B:** "I Gave Claude My GHL Account. Here Is What Happened."
- **Option C:** "Claude + GoHighLevel: Full Setup in 15 Minutes"
- **Test duration:** 7 days each
- **Decision metric:** CTR + Average View Duration (title affects expectations, which affects retention)

## 30/60/90 Day Review Checkpoints

### Day 30 Review
- [ ] Pull YouTube Studio analytics: views, CTR, AVD, traffic sources
- [ ] Pull UTM data: docs site visits, Skool signups, pack purchases
- [ ] Calculate cost per acquisition if running paid ads to the video
- [ ] Review comments for content ideas and objections to address
- [ ] Identify top-performing timestamp segments (retention graph)
- [ ] Decide: does this video need a follow-up or update?

### Day 60 Review
- [ ] Compare to Day 30 numbers (growth trend or plateau?)
- [ ] Check search ranking for "GoHighLevel MCP" and "connect Claude to GHL"
- [ ] Review if GHL has shipped OAuth or new MCP features (update video if needed)
- [ ] Assess whether short-form clips drove additional views back to the main video
- [ ] Evaluate Skool community growth tied to this video's traffic

### Day 90 Review
- [ ] Full ROI calculation: video production time vs. revenue generated (pack sales + community value)
- [ ] Decide: create Part 2 (advanced use cases) or update this video?
- [ ] Review competitive landscape (has anyone else made a similar video?)
- [ ] Plan next quarter's content based on what performed in this video
- [ ] Archive performance data for future benchmarking

---

# PRODUCTION CHECKLIST

- [ ] Script approved by Denis
- [ ] Screen recordings captured (GHL dashboard, Claude Desktop, live demos)
- [ ] Talking head segments filmed
- [ ] B-roll footage captured
- [ ] Thumbnail designed (primary + 2 alternatives)
- [ ] Video edited with timestamps, text overlays, and transitions
- [ ] Description written with UTM links
- [ ] Tags and metadata entered in YouTube Studio
- [ ] End screen configured (next video + subscribe)
- [ ] Cards added at CTA moments (link to docs site, link to Skool)
- [ ] Pinned comment drafted (free guide link + agent pack link)
- [ ] Short-form clips cut and scheduled
- [ ] Twitter thread drafted and scheduled
- [ ] LinkedIn post drafted and scheduled
- [ ] Publish on target day/time (Tuesday or Wednesday, 9:00 AM EST)

---

*Package prepared for Claude Academy. All content follows brand guidelines: no em dashes, no "AI" or "automation" in public-facing text, no sentences over 25 words, calm and direct tone throughout.*
