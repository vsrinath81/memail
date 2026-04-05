# memáil — Product Roadmap
*Last updated: April 5, 2026*

---

## The Vision

**"Email is the exhaust pipe of your life — memáil reads that exhaust and builds a living model of who you are."**

The moat isn't better email. It's intimacy. Gemini has data. memáil has context — the stuff that lives in your head, not in metadata. It knows Shrutha is your 7th grader at Harmony, not just that emails come from harmonytx.org. It knows you bought a home in Katy in 2022, so Zillow is entertainment not action. It knows you're at HCLTech but open to the right senior role.

That context compounds over time. After 6 months, memáil knows you better than any assistant you've ever had.

---

## What's Live Today (v0.1)

- ✅ Real Gmail connected via OAuth (multi-account)
- ✅ Gmail tabs — Primary, Social, Promotions, Updates
- ✅ Topic-cluster memory engine — correlates emails across time
- ✅ Personalized memory strip — "Hey Srinath..."
- ✅ Family-aware AI — knows Shrutha (Harmony), Shristhi (Olga Leonard), Varsha
- ✅ School newsletter action extraction — STAAR prep, homework, field trips
- ✅ Spam classifier — skips AI for MSN, Domino's, GitHub notifications
- ✅ Sender learning — Always analyse / Hide sender rules
- ✅ Minimize button on related emails timeline
- ✅ Multi-account switcher (vsrinath81 + flashblade)
- ✅ Profile with life context
- ✅ AI draft replies
- ✅ Auto-deploy pipeline (GitHub Actions + Cloudflare Worker)

---

## Roadmap

### Phase 1 — Persistent Memory (next session)
*What makes users come back daily*

- [ ] **Session-persistent memory store** — insights survive browser close
  - Store sender profiles, relationship notes, decisions in localStorage
  - Index: person → history of interactions, tone, commitments made
  - Each email opened adds to the model, never resets

- [ ] **Commitment tracker** — extract and track promises
  - "I'll follow up by Friday" → flagged in Needs Action
  - "Let me know if you need anything" → tracked, surfaced if no reply in 7 days
  - Shows in sidebar: "3 commitments pending"

- [ ] **Relationship health scores**
  - Track response times, email frequency, tone trends
  - Flag cooling relationships: "You haven't replied to Hiroshi in 12 days"
  - Flag warming: "Ben from StartEngine has emailed 3x this week"

---

### Phase 2 — Family Dashboard (session 3)
*The feature Gemini cannot build*

- [ ] **Shrutha's school card**
  - All Harmony Public Schools emails in one view
  - PBA award count and trend chart
  - Upcoming: STAAR dates, field trips, permission slips due
  - Teacher notes from newsletters (Sevda Rahymov / 7A)

- [ ] **Shristhi's school card**
  - Olga Leonard Elementary emails
  - Separate from Shrutha — memáil knows they're different kids

- [ ] **Family timeline**
  - Week view: what's happening for each family member
  - Color coded: Shrutha (green), Shristhi (blue), Varsha (amber), Srinath (default)
  - Pulled from email content — no manual entry needed

---

### Phase 3 — Weekly Digest (session 4)
*The feature that creates irreversible lock-in*

- [ ] **Sunday morning letter to Srinath**
  - Generated every Sunday at 8am (triggered by first open of the week)
  - Written as a personal narrative, not a list
  - Covers: family highlights, things that need action, relationship nudges, career pulse
  - Example:
    > *"Hey Srinath — big week. Shrutha picked up her 5th PBA award (Perseverance again — she's really owning that one). Shristhi has a field trip permission slip due Tuesday. Your vehicle registration expires in 6 weeks. Hiroshi hasn't heard back in 12 days. The Microsoft TPM role on LinkedIn is the strongest match in 3 months.*
    >
    > *This week needs: Shristhi's permission slip, the Hiroshi reply, DMV renewal.*
    >
    > *— memáil"*

- [ ] **Digest customization**
  - User can say "always include school updates" or "skip job alerts"
  - Learns from what you act on vs ignore

---

### Phase 4 — Life Context Boxes (session 5)
*Inbox organized by your life, not by sender*

- [ ] **Shrutha box** — everything Harmony Public Schools
- [ ] **Shristhi box** — everything Olga Leonard
- [ ] **Just Browsing box** — Zillow (bought home 2022), market alerts
- [ ] **Finance box** — Bank of America, Coinbase, CoinTracker, receipts
- [ ] **Career box** — LinkedIn alerts, HCLTech, job opportunities
- [ ] **Action Needed box** — emails where Srinath owes a reply or decision
- [ ] **Family box** — Varsha, family group threads

Boxes defined by life context, not by sender domain.
User tells memáil once → it sorts automatically forever.

---

### Phase 5 — Intelligence Layer (future)
*memáil thinks ahead*

- [ ] **Proactive nudges** — "Shrutha's STAAR is in 3 weeks. Her teacher mentioned prep starting. Want to set a study reminder?"
- [ ] **Decision memory** — "You decided to go with option 3 on the Q4 launch in March. Sarah is bringing it up again."
- [ ] **Pattern detection** — "You've missed 3 of Hiroshi's last 4 emails. His tone is cooling."
- [ ] **Life milestones** — track anniversaries, renewals, subscription endings from email history
- [ ] **Voice briefing** — morning audio summary while getting ready

---

## The Metric That Matters

**Not open rate. Not emails processed.**

The metric: *Does Srinath open memáil before Gmail on Sunday morning?*

When the weekly digest becomes the first thing you read on Sunday — that's when memáil is intertwined with your life. That's the lock-in Gemini can't replicate. Because Gemini doesn't know your family. You'd have to tell it everything, every time. memáil already knows. And it gets to know you better every week.

---

## Technical Stack

| Component | Where | Status |
|---|---|---|
| App (index.html) | github.com/vsrinath81/memail | ✅ Live |
| Worker (CORS proxy + deploy) | github.com/vsrinath81/memail-worker | ✅ Live |
| Live URL | vsrinath81.github.io/memail | ✅ Live |
| Cloudflare Worker | bold-lake-b876.vsrinath81.workers.dev | ✅ Live |
| Google Cloud Project | helical-theater-384402 | ✅ Active |
| AI Model | Claude Sonnet (via Anthropic API) | ✅ Active |
| Auto-deploy | GitHub Actions → Cloudflare | ✅ Automated |

---

## The Tagline

*"Email is the largest knowledge base about your life that you've never been able to read. memáil reads it for you."*


---

## Additional Vision (April 5, 2026 — Srinath's notes)

### Sent Email Memory
*"The other half of every conversation"*

- [ ] **One-time permission scan of Sent folder** — on first connect, ask user to permit a full sent mail scan
- [ ] Sent emails reveal:
  - Commitments YOU made ("I'll send that by Friday")
  - Your relationships — who you reach out to vs who reaches out to you
  - Your writing style — used to make AI drafts sound like YOU
  - Decisions you've made — referenced when same topic comes up again
  - Your priorities — who you reply to fast vs slow reveals what matters
- [ ] Combine sent + received to build TRUE relationship graph
  - Not just "Sarah emails you" but "you and Sarah have a 2-day average response cycle, usually about project timelines"
- [ ] Privacy: only scan sent mail with explicit first-time permission, clearly explained

---

### Life Events Dashboard
*"Your life's calendar — extracted from email automatically"*

Beyond just email summaries — memáil should surface LIFE EVENTS hiding in your inbox:

- [ ] **Medical** — doctor appointments, lab results, prescription renewals, insurance claims pending
- [ ] **Automotive** — car service reminders, registration renewals, insurance renewals
- [ ] **Financial** — subscription renewals, bill due dates, policy renewals, tax documents
- [ ] **Family health** — kids' checkups, dental appointments, school physicals due
- [ ] **Home** — HOA dues, utility bills, home warranty renewals, pest control schedules

**Calendar integration:**
- [ ] Read Google Calendar entries (with permission) to add context
- [ ] Birthdays and anniversaries from contacts + calendar
- [ ] "Varsha's birthday is in 12 days — no email activity suggesting you've planned anything yet"
- [ ] "Your parents' anniversary is next week"
- [ ] Friend and family birthdays surfaced 2 weeks in advance with gift/plan nudge

**Dashboard view:**
- Week ahead: all life events in one place
- Color coded by category: Medical (red), Auto (amber), Finance (blue), Family (green)
- Each event links to the source email for full context
- One-click to reply, schedule, or archive

---

### Privacy & Content Filters
*"memáil knows when to look away"*

Hard rules — never analyse, never store, never surface:

- [ ] **Intimate/personal content** — photos, romantic conversations, anything flagged as private
- [ ] **Medical diagnoses** — symptoms, test results stored locally only, never in summaries
- [ ] **Financial account details** — account numbers, passwords, SSN references ignored
- [ ] **Legal communications** — attorney-client emails flagged as confidential, not summarised
- [ ] **Grief/loss** — death notices, condolence threads handled with extra sensitivity, no "action items" extracted

**User-controlled privacy zones:**
- [ ] Mark any sender as "Private — never analyse"
- [ ] Mark any thread as "Off limits"
- [ ] "Sensitive mode" — strips all personal context before sending to AI

**The principle:** memáil should feel like a trusted family assistant who knows when to step out of the room. Not everything needs to be indexed. The user decides what's fair game.

---

## Revised North Star

memáil isn't an email client.

**It's the first AI that knows your whole life — not because you told it, but because it paid attention.**

Every email you've ever sent or received is a data point. Your relationship with your daughter's school. Your car's service history. Your wife's birthday. Your career ambitions. Your family's health. It's all there — buried in your inbox, invisible to you, but legible to memáil.

The product that wins is the one that makes people say:
*"I don't know how I managed without this."*

That's the bar. Build to that.

