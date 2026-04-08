# Claude Academy Agent Pack: Prompt Library

20 ready-to-use prompts for Claude connected to GoHighLevel through MCP. Copy, paste, fill in the placeholders, and run.

---

## Contacts (5 Prompts)

### 1. Create a New Contact

**Prompt Name:** Quick Contact Create

**Use when:** You have a new lead's information and want to add them to GHL without opening the dashboard.

**Prompt:**
```
Create a new contact in my GHL account with the following details:

First name: [FIRST_NAME]
Last name: [LAST_NAME]
Email: [EMAIL]
Phone: [PHONE]
Tags: [TAG_1], [TAG_2]
Source: [LEAD_SOURCE]

After creating the contact, confirm the contact ID and show me the full record.
```

**Expected output:** Claude creates the contact and returns a confirmation with the new contact's ID, name, email, phone, tags, and source field populated.

---

### 2. Search for a Contact

**Prompt Name:** Contact Lookup

**Use when:** You need to find a specific person in your GHL account by name, email, or phone.

**Prompt:**
```
Search my GHL contacts for anyone matching "[SEARCH_TERM]". Show me their full name, email, phone, tags, and last activity date. If there are multiple matches, list all of them.
```

**Expected output:** Claude returns a list of matching contacts with their key fields. If no match is found, Claude says so and suggests broadening the search.

---

### 3. Tag a Contact

**Prompt Name:** Quick Tag

**Use when:** You want to add one or more tags to a contact without navigating to their record in GHL.

**Prompt:**
```
Add the following tags to the contact [CONTACT_NAME_OR_EMAIL] in my GHL account:

Tags to add: [TAG_1], [TAG_2], [TAG_3]

Do not remove any existing tags. Only add these new ones. Confirm when done.
```

**Expected output:** Claude adds the tags and confirms by listing all current tags on the contact (old and new).

---

### 4. Update Contact Information

**Prompt Name:** Contact Update

**Use when:** A contact's details have changed and you need to update their record.

**Prompt:**
```
Update the following fields for contact [CONTACT_NAME_OR_EMAIL] in my GHL account:

[FIELD_1]: [NEW_VALUE_1]
[FIELD_2]: [NEW_VALUE_2]

Show me the updated record after making the changes.
```

**Expected output:** Claude updates the specified fields and returns the full updated contact record for verification.

---

### 5. Merge Duplicate Contacts

**Prompt Name:** Duplicate Finder and Merge

**Use when:** You suspect duplicate contacts exist and want Claude to find and flag them.

**Prompt:**
```
Search my GHL contacts for potential duplicates. Look for contacts that share the same email address or phone number but have different contact IDs.

For each duplicate set found, show me:
- Contact names and IDs
- Which fields differ between them
- Which record has more complete information

Do not merge anything yet. Just show me the report so I can decide.
```

**Expected output:** Claude returns a list of duplicate sets with field comparisons. No changes are made until you approve a specific merge.

---

## Conversations (4 Prompts)

### 6. Summarize a Conversation

**Prompt Name:** Conversation Summary

**Use when:** You need a quick overview of your message history with a contact.

**Prompt:**
```
Pull the full conversation history with [CONTACT_NAME_OR_EMAIL] from my GHL account.

Summarize it in this format:
- Total messages: [number]
- Date range: [first message] to [last message]
- Key topics discussed: [bullet list]
- Open questions or unresolved items: [bullet list]
- Last message was from: [you or the contact]
- Suggested next step: [one sentence]
```

**Expected output:** Claude pulls the conversation and returns a structured summary with all fields filled in.

---

### 7. Draft a Reply

**Prompt Name:** Smart Reply Draft

**Use when:** A contact has messaged you and you want Claude to draft a reply based on context.

**Prompt:**
```
Read the latest conversation with [CONTACT_NAME_OR_EMAIL] in my GHL account.

Draft a reply that:
- Addresses their most recent message directly
- Keeps the tone [TONE: professional/casual/friendly]
- Includes a clear next step or question
- Stays under 100 words

Show me the draft. Do not send it.
```

**Expected output:** Claude shows a draft reply based on the conversation context. The message is not sent until you approve it.

---

### 8. Flag Urgent Conversations

**Prompt Name:** Urgent Message Scan

**Use when:** You want to identify conversations that need immediate attention.

**Prompt:**
```
Review my recent GHL conversations from the last [NUMBER] days.

Flag any conversation as urgent if:
- The contact asked a direct question that has not been answered
- The last message was from the contact and it has been more than [HOURS] hours
- The message contains words like "urgent," "ASAP," "cancel," or "problem"

For each flagged conversation, show: contact name, last message preview, and hours since that message.
```

**Expected output:** Claude returns a list of urgent conversations sorted by time since last contact message, with a preview of each.

---

### 9. Archive Old Conversations

**Prompt Name:** Conversation Cleanup

**Use when:** You want to identify and close out stale conversations.

**Prompt:**
```
Find all conversations in my GHL account where:
- The last message is older than [DAYS] days
- The conversation status is still open

List them with: contact name, last message date, and last message preview.

Do not close or archive anything yet. Just show me the list so I can review it.
```

**Expected output:** Claude returns a list of stale open conversations. No changes are made until you specify which ones to close.

---

## Pipeline (4 Prompts)

### 10. Move a Contact to a New Stage

**Prompt Name:** Stage Mover

**Use when:** You want to advance (or move back) a contact in your pipeline.

**Prompt:**
```
Move the opportunity for [CONTACT_NAME_OR_EMAIL] in the [PIPELINE_NAME] pipeline from their current stage to [NEW_STAGE_NAME].

Add a note on the contact: "Moved to [NEW_STAGE_NAME] on [today's date]. Reason: [REASON]."

Confirm the move and show me the updated opportunity record.
```

**Expected output:** Claude moves the opportunity, adds the note, and confirms with the updated pipeline stage.

---

### 11. List Stalled Opportunities

**Prompt Name:** Stalled Pipeline Report

**Use when:** You want to see which deals have gone quiet.

**Prompt:**
```
Review all opportunities in the [PIPELINE_NAME] pipeline.

For each opportunity, check when the last activity occurred (note, message, or stage change).

List all opportunities where the last activity was more than [DAYS] days ago.

Show: contact name, current stage, last activity date, and days since last activity. Sort by most stalled first.
```

**Expected output:** Claude returns a sorted list of stalled opportunities with activity data.

---

### 12. Pipeline Health Report

**Prompt Name:** Pipeline Overview

**Use when:** You want a snapshot of how your pipeline is performing right now.

**Prompt:**
```
Generate a pipeline report for [PIPELINE_NAME] in my GHL account.

Include:
- Total number of opportunities
- Count per stage (show every stage, even if zero)
- Total estimated value (if opportunity values are set)
- Average time in current stage per opportunity
- Top 3 opportunities by value

Format it as a clean summary I can share with my team.
```

**Expected output:** Claude returns a formatted pipeline health report with counts, values, and highlights.

---

### 13. Bulk Tag by Stage

**Prompt Name:** Stage Tagger

**Use when:** You want to tag all contacts in a specific pipeline stage.

**Prompt:**
```
Find all contacts with opportunities in the [STAGE_NAME] stage of the [PIPELINE_NAME] pipeline.

Add the tag "[TAG_NAME]" to each contact. Do not remove any existing tags.

After tagging, confirm:
- Total contacts tagged
- List of contact names that were tagged
```

**Expected output:** Claude adds the tag to all contacts in the specified stage and returns a confirmation list.

---

## Calendar (4 Prompts)

### 14. Check Availability

**Prompt Name:** Open Slots

**Use when:** Someone asks when you are free and you want to check your GHL calendar quickly.

**Prompt:**
```
Check my GHL calendar [CALENDAR_ID] for available appointment slots over the next [NUMBER] business days.

Show available times grouped by date, in [YOUR_TIMEZONE]. Only show slots during business hours ([START_TIME] to [END_TIME]).
```

**Expected output:** Claude returns a list of available slots organized by date and time of day.

---

### 15. Book an Appointment

**Prompt Name:** Quick Book

**Use when:** A lead has confirmed a time and you want to book it in GHL.

**Prompt:**
```
Book an appointment with the following details:

Contact: [CONTACT_NAME_OR_EMAIL]
Calendar: [CALENDAR_ID]
Date: [DATE]
Time: [TIME]
Timezone: [TIMEZONE]
Duration: [MINUTES] minutes
Notes: [APPOINTMENT_NOTES]

Confirm the booking and show me the appointment details.
```

**Expected output:** Claude creates the appointment and returns a confirmation with all details and the appointment ID.

---

### 16. Reschedule an Appointment

**Prompt Name:** Reschedule

**Use when:** A contact needs to move their existing appointment to a new time.

**Prompt:**
```
Find the upcoming appointment for [CONTACT_NAME_OR_EMAIL] on my GHL calendar.

Reschedule it to: [NEW_DATE] at [NEW_TIME] [TIMEZONE].

Add a note to the contact record: "Appointment rescheduled from [old date/time] to [new date/time]."

Confirm the change.
```

**Expected output:** Claude cancels the old slot, books the new one, adds a note, and confirms with updated details.

---

### 17. Cancel an Appointment

**Prompt Name:** Cancel Booking

**Use when:** An appointment needs to be removed from the calendar.

**Prompt:**
```
Find the upcoming appointment for [CONTACT_NAME_OR_EMAIL] on my GHL calendar.

Cancel it and add a note to the contact: "Appointment on [date] at [time] cancelled. Reason: [REASON]."

Confirm the cancellation.
```

**Expected output:** Claude cancels the appointment, adds the note, and confirms it has been removed from the calendar.

---

## Reporting (3 Prompts)

### 18. Weekly Pipeline Summary

**Prompt Name:** Weekly Pipeline Digest

**Use when:** It is the end of the week and you want a summary of pipeline activity.

**Prompt:**
```
Generate a weekly pipeline summary for [PIPELINE_NAME] covering the last 7 days.

Include:
- New opportunities added this week (count and list)
- Opportunities that changed stages this week (from where to where)
- Opportunities closed/won this week (count and total value)
- Opportunities closed/lost this week (count and reasons if noted)
- Current total pipeline value
- One-paragraph assessment of the week

Format this as a report I can paste into a team update.
```

**Expected output:** Claude returns a formatted weekly digest with all metrics and a plain-language summary.

---

### 19. Lead Source Breakdown

**Prompt Name:** Source Report

**Use when:** You want to see which lead sources are producing the most contacts or opportunities.

**Prompt:**
```
Analyze my GHL contacts created in the last [DAYS] days.

Group them by lead source and show:
- Source name
- Number of contacts from that source
- Number that have entered a pipeline
- Number that have been tagged as [HOT_TAG]

Sort by total contacts, highest first. Include an "Unknown" row for contacts with no source set.
```

**Expected output:** Claude returns a source breakdown table with counts and pipeline conversion data.

---

### 20. Team Activity Report

**Prompt Name:** Team Activity Check

**Use when:** You want to see what has been happening across your GHL account recently.

**Prompt:**
```
Generate an activity report for my GHL account covering the last [DAYS] days.

Include:
- Total new contacts created
- Total conversations started
- Total messages sent
- Total appointments booked
- Total opportunities created
- Total opportunities moved to a new stage
- Total notes added

If possible, break down by user/team member. Present as a clean summary table.
```

**Expected output:** Claude returns an activity summary table covering all major GHL actions for the specified period.

---

## Tips for Using These Prompts

1. **Fill in every placeholder.** Prompts with blank placeholders produce vague results.
2. **Start with read-only prompts.** Use search, summary, and report prompts before running any that modify data.
3. **Combine prompts as you get comfortable.** For example, run the Stalled Pipeline Report first, then use Stage Mover on specific contacts from the results.
4. **Save your favorites.** Copy your most-used prompts (with placeholders filled in) to a text file or Claude Project for quick access.
5. **Share what works.** Post your best custom prompts in the Claude Academy community to help others.
