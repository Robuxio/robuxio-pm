# Robuxio Lifecycle Flows
## Complete Guide: How Work Moves Through the System

---

## Purpose of This Document

The PM Bible defines the **rules**. This document shows the **flow** — what actually happens from the moment someone has an idea until the work is done, including what to do when things go wrong.

---

# Part 1: The Big Picture

## Work Hierarchy

```
┌─────────────────────────────────────────────────────────────────┐
│                         PROJECT                                  │
│   (Large initiative, multiple sprints, e.g., "Client Portal")   │
│                                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │                      EPIC                                │   │
│   │   (Feature set, 1-2 sprints, e.g., "User Dashboard")    │   │
│   │                                                          │   │
│   │   ┌─────────────┐  ┌─────────────┐  ┌─────────────┐     │   │
│   │   │   STORY     │  │   STORY     │  │    BUG      │     │   │
│   │   │ (Feature)   │  │ (Feature)   │  │  (Defect)   │     │   │
│   │   └─────────────┘  └─────────────┘  └─────────────┘     │   │
│   │                                                          │   │
│   │   ┌─────────────┐  ┌─────────────┐                      │   │
│   │   │   TASK      │  │   SPIKE     │                      │   │
│   │   │ (Technical) │  │ (Research)  │                      │   │
│   │   └─────────────┘  └─────────────┘                      │   │
│   │                                                          │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

# Part 2: Epic Lifecycle

## What is an Epic?

An Epic is a **large body of work** that can be broken down into smaller stories/tasks. It typically spans 1-2 sprints.

**Examples:**
- "Factsheet Automation"
- "TWR Calculation Refactor"
- "Client Dashboard Redesign"

---

## Epic Flow Diagram

```
                            EPIC LIFECYCLE
                            
     ┌──────────────────────────────────────────────────────────┐
     │                                                          │
     ▼                                                          │
┌─────────┐                                                     │
│  IDEA   │  ← Pavel/Dries has a business need                  │
└────┬────┘                                                     │
     │                                                          │
     │ PM triages within 48h                                    │
     │ • Is this a real need?                                   │
     │ • Is it a duplicate?                                     │
     │ • Who needs to be involved?                              │
     │                                                          │
     ▼                                                          │
┌─────────┐                                                     │
│  DRAFT  │  ← Shape the problem, NOT the solution              │
└────┬────┘                                                     │
     │                                                          │
     │ Business Alignment Meeting                               │
     │ • Dries: What's the client need?                         │
     │ • Pavel: What's the business priority?                   │
     │ • Deneb: Is this technically feasible?                   │
     │ • Olda: Any trading implications?                        │
     │                                                          │
     ▼                                                          │
┌─────────────────────────┐                                     │
│ READY FOR CLARIFICATION │  ← Define scope, break into stories │
└────────────┬────────────┘                                     │
             │                                                  │
             │ PM + relevant approvers work on:                 │
             │ • What's in scope?                               │
             │ • What's out of scope?                           │
             │ • What stories does this break into?             │
             │ • What's the Definition of Done for the Epic?    │
             │                                                  │
             ▼                                                  │
┌─────────┐                                                     │
│  READY  │  ← Epic is defined, stories can be created          │
└────┬────┘                                                     │
     │                                                          │
     │ Create child stories/tasks                               │
     │ Each follows its own lifecycle                           │
     │                                                          │
     ▼                                                          │
┌─────────────┐                                                 │
│ IN PROGRESS │  ← At least one child story is in progress      │
└──────┬──────┘                                                 │
       │                                                        │
       │ Track progress:                                        │
       │ • Are stories completing?                              │
       │ • Any blockers at epic level?                          │
       │ • Scope creep detected?                                │
       │                                                        │
       ▼                                                        │
┌─────────┐                                                     │
│  DONE   │  ← All child stories complete                       │
└─────────┘    Epic acceptance criteria met                     │
               Demo delivered to stakeholders                   │
```

---

## Epic Example: "Factsheet Automation"

### Stage 1: IDEA
```
Who: Dries
When: Week 1 Monday

"We need to automate the factsheet generation. Currently it takes 
2 hours manually and we make mistakes."

PM Action: 
- Tag as source:coo
- Check for duplicates (none found)
- Move to Draft
```

### Stage 2: DRAFT
```
Business Alignment Meeting:
- Dries: Clients need monthly factsheets, current process is error-prone
- Deneb: We can automate this with PDF generation library
- Olda: Need to verify TWR/NAV calculations are correct in output

Outcome:
- Priority: P1 (affects client deliverables)
- Target: Next sprint
- Approvers: Deneb + Olda (trading-related)
```

### Stage 3: READY FOR CLARIFICATION
```
Epic broken into stories:
1. "Design factsheet template" - needs Dries input
2. "Implement PDF generation" - pure technical
3. "Integrate TWR/NAV data" - needs Olda verification
4. "Add scheduling/automation" - needs infra decision

Missing items identified:
- [ ] Example of current manual factsheet
- [ ] List of required data fields
- [ ] TWR calculation formula verification

Assigned clarifications:
- Dries: Provide example factsheet (due: Wed)
- Olda: Verify TWR formula (due: Thu)
```

### Stage 4: READY
```
All clarifications received:
- [x] Example factsheet provided
- [x] Data fields documented
- [x] TWR formula verified by Olda

Epic Acceptance Criteria:
1. PDF matches approved template
2. TWR/NAV values match manual calculation
3. Factsheet generates in < 30 seconds
4. Scheduled to run monthly

Approvals:
- Deneb: ✅ Approved (technical)
- Olda: ✅ Approved (trading logic)
```

### Stage 5: IN PROGRESS
```
Stories pulled into sprint:
- Story 1: "Design template" → Leo (In Progress)
- Story 2: "PDF generation" → Waiting for Story 1
- Story 3: "TWR/NAV integration" → Azara (Ready)
- Story 4: "Scheduling" → Erro (Ready)

Progress tracked via child story statuses.
```

### Stage 6: DONE
```
All stories complete:
- [x] Template approved by Dries
- [x] PDF generates correctly
- [x] TWR/NAV values verified by Olda
- [x] Automation running monthly

Demo delivered at Sprint Review.
Epic closed.
```

---

# Part 3: Story Lifecycle

## What is a Story?

A Story is a **single piece of deliverable work** that provides value. It should be completable within a sprint (ideally within days).

**Examples:**
- "As a client, I can view my TWR on the dashboard"
- "Generate PDF factsheet from template"
- "Add fee breakdown to client report"

---

## Story Flow Diagram (The Happy Path)

```
                           STORY LIFECYCLE (Happy Path)
                            
┌─────────┐
│  IDEA   │  ← Created from Epic breakdown or standalone request
└────┬────┘
     │
     │ PM triage (48h)
     ▼
┌─────────┐
│  DRAFT  │  ← Problem defined, not solution
└────┬────┘
     │
     │ Add: Outcome, Scope, AC
     ▼
┌─────────────────────────┐
│ READY FOR CLARIFICATION │  ← Checklist items being completed
└────────────┬────────────┘
             │
             │ All 11 Start Gate items checked?
             │ All approvers explicitly approved?
             ▼
┌─────────┐
│  READY  │  ← START GATE PASSED ✅
└────┬────┘
     │
     │ Dev pulls ticket (WIP = 1)
     │ Dev posts plan + assumptions
     ▼
┌─────────────┐
│ IN PROGRESS │  ← Active development
└──────┬──────┘
       │
       │ Code complete
       │ Tests passing
       ▼
┌───────────┐
│ IN REVIEW │  ← Acceptance criteria verification
└─────┬─────┘
      │
      │ All AC met? Reviewer approved?
      ▼
┌─────────┐
│  DONE   │  ← Can be demoed, value delivered
└─────────┘
```

---

## Story Flow Diagram (With Problems)

```
                    STORY LIFECYCLE (Reality - With Blockers)
                            
┌─────────┐
│  IDEA   │
└────┬────┘
     │
     ▼
┌─────────┐
│  DRAFT  │
└────┬────┘
     │
     ▼
┌─────────────────────────┐
│ READY FOR CLARIFICATION │◄─────────────────────────────────────┐
└────────────┬────────────┘                                      │
             │                                                   │
             │ Missing items?──────Yes───► Assign clarifier      │
             │      │                      Wait for input        │
             │      No                     (can take days)       │
             │      │                            │               │
             │      ▼                            │               │
             │ All approved?───────No────► Tag approvers         │
             │      │                      Wait for approval     │
             │      │                      (silence = blocked!)  │
             │     Yes                           │               │
             │      │                            │               │
             ▼      ▼                            │               │
┌─────────┐                                      │               │
│  READY  │                                      │               │
└────┬────┘                                      │               │
     │                                           │               │
     │ Dev pulls ticket                          │               │
     ▼                                           │               │
┌─────────────┐                                  │               │
│ IN PROGRESS │                                  │               │
└──────┬──────┘                                  │               │
       │                                         │               │
       │                                         │               │
       ├───── Scope unclear? ──────Yes──────────►│               │
       │             │                           │               │
       │            No                           │               │
       │             │                           │               │
       ├───── Scope changed? ─────Yes───────────►┘               │
       │             │                                           │
       │            No                                           │
       │             │                                           │
       ├───── No progress 24h? ──Yes──►┌─────────┐               │
       │             │                 │ BLOCKED │               │
       │            No                 └────┬────┘               │
       │             │                      │                    │
       │             │         ┌────────────┘                    │
       │             │         │                                 │
       │             │         │ Blocker resolved?               │
       │             │         │     │                           │
       │             │         │    Yes──► Back to In Progress   │
       │             │         │     │                           │
       │             │         │    No───► PM escalates same day │
       │             │         │           │                     │
       │             │         │           └─► Escalation path:  │
       │             │         │              Tech → Deneb       │
       │             │         │              Trading → Olda     │
       │             │         │              Client → Dries     │
       │             │         │              Priority → Pavel   │
       │             │         │                                 │
       ▼             │         │                                 │
┌───────────┐        │         │                                 │
│ IN REVIEW │◄───────┘         │                                 │
└─────┬─────┘                  │                                 │
      │                        │                                 │
      ├─── AC not met? ──Yes──►│ Back to In Progress             │
      │         │              │ (rework needed)                 │
      │        No              │                                 │
      │         │              │                                 │
      ├─── Wrong approach? Yes►┘ Back to Clarification           │
      │         │                (scope was wrong)               │
      │        No                                                │
      ▼                                                          │
┌─────────┐                                                      │
│  DONE   │                                                      │
└─────────┘                                                      │
```

---

## Story Example: "Display TWR on Dashboard"

### IDEA
```
Source: Dries (COO)
Request: "Clients need to see their TWR on the main dashboard"

PM triage:
- Type: Story
- Domain: Client/Trading-related
- Priority: P1
- Approvers needed: Deneb + Olda (TWR is trading logic)
- Check duplicates: None found
→ Move to Draft
```

### DRAFT
```
Problem Statement:
Clients currently can't see their TWR without requesting a report.
This creates support overhead and client frustration.

Initial scope discussion:
- Where on dashboard? (needs Dries input)
- How to calculate TWR? (needs Olda input)
- Real-time or cached? (needs Deneb input)

→ Move to Ready for Clarification
```

### READY FOR CLARIFICATION
```
Checklist status:

[x] Outcome: "When done, clients can see their TWR on dashboard without asking support"
[x] In Scope:
    - Display TWR on main dashboard
    - Show TWR for current period
    - Update daily (not real-time)
[x] Out of Scope:
    - Historical TWR comparison
    - TWR breakdown by asset
    - Export functionality
[x] Acceptance Criteria:
    1. TWR displays on dashboard homepage
    2. TWR value matches backend calculation (verified by Olda)
    3. TWR updates daily at 6 AM
    4. Shows "Calculating..." if data not ready
    5. Works on mobile view
[x] Dependencies: TWR calculation endpoint exists (confirmed)
[x] Example: [Figma mockup attached by Dries]
[x] Approvers: Deneb, Olda
[ ] Approvals: WAITING ← Blocking!

PM Action:
- Tag @Deneb @Olda in Discord: "[NEEDS-DECISION] Please review and approve PROJ-123"
- Set deadline: EOD tomorrow

Next day:
- Deneb: "Approved ✅" (commented in Jira)
- Olda: "Approved ✅ - TWR formula verified" (commented in Jira)

[x] All approvals received
→ Move to Ready
```

### READY
```
Start Gate: ALL ITEMS CHECKED ✅

Available for sprint planning.

Sprint Planning:
- Azara pulls ticket (capacity available)
- Estimated: 3 days
- Sprint Goal: "Clients can see key metrics on dashboard"

→ Move to In Progress
```

### IN PROGRESS
```
Day 1 - Azara starts work:

Comment posted:
"## Plan
- Create TWR component
- Connect to existing API endpoint
- Add to dashboard layout
- Test with sample data

## Assumptions
- TWR endpoint returns correct format
- Dashboard layout has space for new widget

## Risks
- API might be slow for large portfolios"

Daily update:
"Next step: Building TWR component
Blocker: None
ETA Confidence: High"
```

```
Day 2 - Problem discovered:

Daily update:
"Next step: Connecting to API
Blocker: API returns different format than expected
ETA Confidence: Low"

PM Action:
- Ticket moved to BLOCKED
- Comment added: 
  "What: API format mismatch
   Who: Deneb (API owner)
   Decision: Should we update API or adapt frontend?"
- Discord: "@Deneb [BLOCKER] PROJ-123 needs API decision"
```

### BLOCKED
```
Same day - Deneb responds:

"Adapt frontend - API format is correct per spec. 
Frontend assumption was wrong. This is a 30-min fix."

Resolution:
- Blocker resolved same day
- Move back to In Progress
- Azara adjusts approach
```

### IN PROGRESS (continued)
```
Day 3:

Daily update:
"Next step: Final testing
Blocker: None
ETA Confidence: High"

Code complete:
- Component built
- API connected
- Tests passing
- PR created

→ Move to In Review
```

### IN REVIEW
```
Reviewer: Deneb (technical) + Olda (TWR correctness)

Review checklist:
[x] TWR displays on dashboard homepage
[x] TWR value matches backend calculation - Olda verified
[x] Updates daily at 6 AM
[x] Shows "Calculating..." state works
[x] Mobile view works

Deneb: "Code approved ✅"
Olda: "TWR values correct ✅"

→ Move to Done
```

### DONE
```
Story complete:
- Merged to develop
- Deployed to staging
- Demoed at Sprint Review
- Dries confirms it meets need

Value delivered! 🎉
```

---

# Part 4: Spike Lifecycle

## What is a Spike?

A Spike is a **time-boxed investigation** to answer a question or reduce uncertainty. It produces **knowledge**, not code.

**When to use:**
- Requirements are unclear
- Technical approach is unknown
- We need to evaluate options
- Estimation is impossible without research

---

## Spike Flow Diagram

```
                            SPIKE LIFECYCLE
                            
┌──────────────────────────────────────────────────────────────────┐
│ TRIGGER: Someone says "I don't know how to estimate this"        │
│          or "We're not sure if this is possible"                 │
│          or "Requirements are too vague to start"                │
└────────────────────────────┬─────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                      CREATE SPIKE                                │
│                                                                  │
│  Title: "Spike: [Question to answer]"                           │
│  Timebox: 2-6 hours (HARD LIMIT)                                │
│  Parent: Link to blocked/unclear ticket                         │
│                                                                  │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                    SPIKE IN PROGRESS                             │
│                                                                  │
│  Developer investigates:                                         │
│  • Research options                                              │
│  • Prototype if needed                                           │
│  • Document findings                                             │
│  • DO NOT build production code                                  │
│                                                                  │
│  ⏰ TIMEBOX IS STRICT                                            │
│  If time runs out → stop and document what you learned           │
│                                                                  │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                      SPIKE DONE                                  │
│                                                                  │
│  Required deliverables:                                          │
│  1. Written findings summary                                     │
│  2. Recommended approach (or "not feasible")                     │
│  3. Updated acceptance criteria for parent ticket                │
│  4. Estimation for parent ticket (if now possible)               │
│                                                                  │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                   PARENT TICKET UPDATED                          │
│                                                                  │
│  Parent ticket now has:                                          │
│  • Clear approach                                                │
│  • Realistic estimation                                          │
│  • Can pass Start Gate                                           │
│                                                                  │
│  → Parent moves to Ready                                         │
└─────────────────────────────────────────────────────────────────┘
```

---

## Spike Example: "How to Generate PDF Factsheets?"

### Trigger
```
Story: "Generate PDF factsheet from template"
Problem: Leo says "I don't know how to estimate this. 
         I've never done PDF generation in our stack."

PM Decision: Create a Spike before this story can be Ready.
```

### Spike Created
```
Title: Spike: Evaluate PDF generation approaches for factsheets

Question to Answer:
What's the best way to generate PDF factsheets in our stack?

Timebox: 4 hours

Context:
- We need to generate monthly PDF factsheets
- Must match our brand template
- Must include charts and tables
- Must be automated (no manual steps)

Required Output:
- [ ] List of evaluated options
- [ ] Recommended approach with reasoning
- [ ] Rough complexity estimate
- [ ] Any risks or dependencies identified

Parent Ticket: PROJ-100 "Generate PDF factsheet"
Owner: Leo
```

### Spike In Progress
```
Leo's investigation (4 hours):

Hour 1-2: Research options
- Option A: Puppeteer (headless Chrome)
- Option B: PDFKit (JavaScript library)
- Option C: External API (DocRaptor, etc.)

Hour 3: Quick prototype
- Tested Puppeteer with simple template
- Tested PDFKit with basic table

Hour 4: Document findings
```

### Spike Done
```
## Spike Findings: PDF Generation for Factsheets

### Options Evaluated

| Option | Pros | Cons | Effort |
|--------|------|------|--------|
| Puppeteer | Full HTML/CSS support, charts work | Heavy dependency, slow | Medium |
| PDFKit | Lightweight, fast | Limited styling, charts hard | High |
| DocRaptor | Best quality, easy | Monthly cost ($$$), external dependency | Low |

### Recommendation
Use **Puppeteer** because:
1. We already use Chrome in our stack
2. Can reuse existing HTML templates
3. Charts render correctly
4. No external cost

### Risks
- PDF generation is slow (~3-5 seconds per file)
- Need to handle timeout for large factsheets

### Updated Estimation for Parent Ticket
- Template setup: 1 day
- PDF generation logic: 2 days
- Integration + testing: 1 day
- Total: 4 days (was "unknown")

### Dependencies Identified
- Need Puppeteer installed on server
- Need example factsheet data for testing
```

### Parent Ticket Updated
```
Story "Generate PDF factsheet" now has:

[x] Clear approach: Use Puppeteer
[x] Realistic estimate: 4 days
[x] Dependencies: Puppeteer server setup
[x] Risks documented: Slow generation

→ Parent ticket can now pass Start Gate
→ Move to Ready
```

---

# Part 5: Bug Lifecycle

## Bug Flow Diagram

```
                              BUG LIFECYCLE
                            
┌──────────────────────────────────────────────────────────────────┐
│ TRIGGER: Something that worked before is now broken              │
│          Or: Behavior doesn't match specification                │
└────────────────────────────┬─────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                         BUG REPORTED                             │
│                                                                  │
│  Required info:                                                  │
│  • What is broken?                                               │
│  • Steps to reproduce                                            │
│  • Expected vs actual behavior                                   │
│  • Screenshots/logs                                              │
│                                                                  │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                       PM TRIAGE                                  │
│                                                                  │
│  Determine severity:                                             │
│                                                                  │
│  CRITICAL (P0) ──► Trading/money affected                       │
│       │            → Immediate, drop everything                  │
│       │                                                          │
│  MAJOR (P1) ────► Core functionality broken                     │
│       │            → This sprint                                 │
│       │                                                          │
│  MINOR (P2) ────► Workaround exists                             │
│       │            → Backlog                                     │
│       │                                                          │
│  TRIVIAL ───────► Cosmetic only                                 │
│                    → Nice to have                                │
│                                                                  │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             │ Is it reproducible?
                             │
              ┌──────No──────┴──────Yes──────┐
              │                              │
              ▼                              ▼
┌─────────────────────┐        ┌─────────────────────────┐
│ NEED MORE INFO      │        │ READY                   │
│                     │        │ (Bugs skip Start Gate   │
│ Ask reporter for:   │        │  if reproducible)       │
│ • More details      │        │                         │
│ • Logs              │        └───────────┬─────────────┘
│ • Steps to repro    │                    │
└─────────────────────┘                    ▼
                             ┌─────────────────────────┐
                             │ IN PROGRESS             │
                             │                         │
                             │ Dev fixes the bug       │
                             └───────────┬─────────────┘
                                         │
                                         ▼
                             ┌─────────────────────────┐
                             │ IN REVIEW               │
                             │                         │
                             │ Verify fix works        │
                             │ Verify no regression    │
                             └───────────┬─────────────┘
                                         │
                                         ▼
                             ┌─────────────────────────┐
                             │ DONE                    │
                             │                         │
                             │ Bug fixed, deployed     │
                             └─────────────────────────┘
```

---

## Critical Bug (P0) Example: "TWR Showing Wrong Values"

```
MINUTE 0: Bug reported
━━━━━━━━━━━━━━━━━━━━━━
Reporter: Dries
"Client called - their TWR shows -50% but should be +5%"

MINUTE 5: PM triage
━━━━━━━━━━━━━━━━━━━━━━
Severity: CRITICAL (P0) - Trading/money related
Action: DROP EVERYTHING

PM immediately:
- Creates Jira ticket with all info
- Tags in Discord: "@Deneb @Olda [P0 BLOCKER] TWR showing wrong values"
- All other work paused

MINUTE 15: Investigation starts
━━━━━━━━━━━━━━━━━━━━━━
Deneb + Olda on call
Azara checking code

Finding: Formula change last week broke edge case

MINUTE 45: Fix identified
━━━━━━━━━━━━━━━━━━━━━━
Root cause: Division by zero not handled
Fix: Add guard clause

HOUR 1: Fix deployed
━━━━━━━━━━━━━━━━━━━━━━
- Code fixed
- Tested by Olda (values now correct)
- Deployed to production
- Client notified

HOUR 2: Post-mortem logged
━━━━━━━━━━━━━━━━━━━━━━
- Why did this happen?
- How do we prevent it?
- Added to retro agenda

Bug closed. Normal work resumes.
```

---

# Part 6: Blocker Resolution Flows

## Types of Blockers

```
┌─────────────────────────────────────────────────────────────────┐
│                       BLOCKER TYPES                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  1. TECHNICAL BLOCKER                                           │
│     "I can't proceed because of a technical issue"              │
│     → Escalate to: Deneb                                        │
│     → Examples: API not working, missing access, bug in         │
│                 dependency                                       │
│                                                                  │
│  2. REQUIREMENTS BLOCKER                                        │
│     "I don't understand what to build"                          │
│     → Escalate to: PM → Dries/Pavel                             │
│     → Examples: Unclear AC, missing mockup, conflicting         │
│                 requirements                                     │
│                                                                  │
│  3. TRADING LOGIC BLOCKER                                       │
│     "I don't know if this calculation is correct"               │
│     → Escalate to: Olda                                         │
│     → Examples: TWR formula unclear, fee calculation,           │
│                 NAV definition                                   │
│                                                                  │
│  4. APPROVAL BLOCKER                                            │
│     "I'm waiting for someone to approve"                        │
│     → Escalate to: PM → specific approver                       │
│     → Examples: Waiting for Deneb review, waiting for           │
│                 Olda sign-off                                    │
│                                                                  │
│  5. DEPENDENCY BLOCKER                                          │
│     "I need something else to be done first"                    │
│     → Escalate to: PM → owner of dependency                     │
│     → Examples: Waiting for another ticket, waiting for         │
│                 external service                                 │
│                                                                  │
│  6. PRIORITY BLOCKER                                            │
│     "I'm being asked to do conflicting things"                  │
│     → Escalate to: PM → Pavel                                   │
│     → Examples: Two P0s assigned, scope creep from              │
│                 business                                         │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Blocker Resolution Flow

```
                        BLOCKER RESOLUTION
                            
┌─────────────────────────────────────────────────────────────────┐
│ TRIGGER: Dev has no progress for 24h                            │
│          OR: Dev explicitly says "I'm blocked"                  │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                    STEP 1: DOCUMENT BLOCKER                      │
│                                                                  │
│  Dev moves ticket to BLOCKED and adds comment:                   │
│                                                                  │
│  "## What is blocking                                            │
│   [Describe the specific issue]                                  │
│                                                                  │
│   ## Who must unblock                                            │
│   [Name the specific person]                                     │
│                                                                  │
│   ## What decision/action is needed                              │
│   [Be specific about what you need]"                             │
│                                                                  │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                    STEP 2: PM NOTIFIED                           │
│                                                                  │
│  PM sees blocked ticket (checks daily)                           │
│  PM tags responsible person in Discord:                          │
│                                                                  │
│  "@Deneb [BLOCKER] PROJ-123 needs your input on API format.      │
│   Azara is blocked. Please respond today."                       │
│                                                                  │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                    STEP 3: RESOLUTION                            │
│                                                                  │
│  Responsible person responds:                                    │
│                                                                  │
│  Option A: Quick answer ──► Dev unblocked, back to In Progress   │
│                                                                  │
│  Option B: Needs meeting ──► PM schedules 15-min sync            │
│                                                                  │
│  Option C: Can't be resolved quickly ──► See Step 4              │
│                                                                  │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             │ If blocker persists > 24h
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                    STEP 4: ESCALATION                            │
│                                                                  │
│  PM escalates up the chain:                                      │
│                                                                  │
│  Tech issue:     Dev → Deneb → Pavel                             │
│  Trading issue:  Dev → Olda → Deneb → Pavel                      │
│  Business issue: Dev → PM → Dries → Pavel                        │
│  Priority issue: Dev → PM → Pavel                                │
│                                                                  │
│  At each level:                                                  │
│  • Explain impact of delay                                       │
│  • Give deadline for decision                                    │
│  • Document in Jira                                              │
│                                                                  │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                    STEP 5: RESOLUTION                            │
│                                                                  │
│  Blocker resolved:                                               │
│  1. Update Jira with resolution                                  │
│  2. Move ticket back to In Progress                              │
│  3. Dev continues work                                           │
│                                                                  │
│  If blocker cannot be resolved:                                  │
│  1. Document why                                                 │
│  2. Cancel or de-prioritize ticket                               │
│  3. Communicate to stakeholders                                  │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## Blocker Example: "API Format Mismatch"

```
TIMELINE

Monday 10:00 - Dev starts work
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Azara pulls ticket "Display TWR on dashboard"
Posts plan in Jira

Monday 14:00 - Problem discovered
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
API returns: { "twr": "5.2%" }
Expected:    { "twr": 0.052 }

Azara can't proceed without knowing which is correct.

Monday 14:15 - Blocker documented
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Ticket moved to BLOCKED

Comment:
"## What is blocking
API returns TWR as string "5.2%" but I expected number 0.052

## Who must unblock
@Deneb - API owner

## What decision needed
Should I:
A) Update frontend to parse string?
B) Is API format wrong and needs fix?"

Monday 14:20 - PM notified
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PM (Azara) sees own ticket is blocked. 
Since conflict of interest, tags Deneb directly:

Discord: "@Deneb [BLOCKER] PROJ-123 - API format question. 
          I'm blocked on my own ticket. Need decision today."

Monday 16:00 - Resolution
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Deneb responds in Jira:

"API format is correct per documentation. 
String format is intentional for display purposes.
Frontend should parse if number needed for calculations.
This is a 30-min adjustment."

Monday 16:15 - Unblocked
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Azara updates ticket:
"Blocker resolved. Will parse string on frontend.
Moving back to In Progress."

Total blocked time: 2 hours
Resolution: Same day ✅
```

---

# Part 7: Sprint Lifecycle

## Sprint Flow Overview

```
                           MONTHLY SPRINT LIFECYCLE
                            
WEEK -1 (Last week of previous sprint)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

┌─────────────────────────────────────────────────────────────────┐
│ PREPARATION PHASE                                                │
│                                                                  │
│ Day 1-2: Business Alignment Meeting                             │
│ • Azara + Pavel/Dries                                           │
│ • Review upcoming priorities                                     │
│ • Identify next sprint's focus                                   │
│ • NO technical discussion                                        │
│                                                                  │
│ Day 3-4: Backlog Refinement (mostly async)                      │
│ • PM prepares candidate tickets                                  │
│ • Ensures Start Gate items are filled                           │
│ • Gets approvals where possible                                  │
│ • Flags items needing dev input                                  │
│                                                                  │
│ Day 5: Sprint Planning Preparation                              │
│ • All candidate tickets in "Ready" or "Ready for Clarification" │
│ • Capacity known for each dev                                    │
│ • Priorities clear                                               │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘

WEEK 1 (Sprint starts)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

┌─────────────────────────────────────────────────────────────────┐
│ PLANNING + START                                                 │
│                                                                  │
│ Day 1: Sprint Planning (2 hours)                                │
│ • Dev team only                                                  │
│ • Review prioritized backlog                                     │
│ • Start Gate check for each ticket                              │
│ • Estimate and commit                                            │
│ • Define Sprint Goal                                             │
│                                                                  │
│ Day 2-5: Development begins                                     │
│ • Devs pull tickets (WIP = 1)                                   │
│ • Daily async updates                                            │
│ • Blockers surfaced immediately                                  │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘

WEEKS 2-3 (Execution)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

┌─────────────────────────────────────────────────────────────────┐
│ DEVELOPMENT PHASE                                                │
│                                                                  │
│ Daily:                                                           │
│ • Async updates from each dev                                    │
│ • PM checks for blocked tickets                                  │
│ • PM acts on blockers same day                                   │
│                                                                  │
│ Weekly:                                                          │
│ • Check sprint progress vs commitment                            │
│ • Flag any at-risk tickets                                       │
│ • Adjust if needed (with team agreement)                         │
│                                                                  │
│ ⚠️ MID-SPRINT SCOPE CHANGES                                      │
│ • Discouraged unless critical                                    │
│ • If P0 bug: handle immediately                                  │
│ • If new request: goes to next sprint                            │
│ • If scope creep: ticket back to Clarification                   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘

WEEK 4 (Sprint ends)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

┌─────────────────────────────────────────────────────────────────┐
│ CLOSING PHASE                                                    │
│                                                                  │
│ Day 1-3: Wrap up development                                    │
│ • Complete in-progress work                                      │
│ • Move incomplete to next sprint                                 │
│ • Final reviews and merges                                       │
│                                                                  │
│ Day 4: Sprint Review (1.5 hours)                                │
│ • Demo completed work to business                                │
│ • Delivered vs committed comparison                              │
│ • Business feedback collected                                    │
│ • Celebrate wins!                                                │
│                                                                  │
│ Day 5: Retrospective (1 hour)                                   │
│ • Dev team only                                                  │
│ • What caused blockers?                                          │
│ • What caused rework?                                            │
│ • 1-2 improvement actions for next sprint                        │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘

REPEAT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Next sprint begins immediately.
Preparation for sprint N+1 happens during Week 4 of sprint N.
```

---

# Part 8: Quick Reference Flows

## Decision Tree: What Status Should This Be?

```
START: Is this ticket...
          │
          ├── A new idea/request?
          │         │
          │         └──► IDEA
          │
          ├── Being shaped (not ready to build)?
          │         │
          │         └──► DRAFT
          │
          ├── Missing any Start Gate items?
          │         │
          │         └──► READY FOR CLARIFICATION
          │
          ├── All Start Gate items complete + all approvals?
          │         │
          │         └──► READY
          │
          ├── A dev is actively working on it?
          │         │
          │         └──► IN PROGRESS
          │
          ├── No progress for 24h OR explicitly stuck?
          │         │
          │         └──► BLOCKED
          │
          ├── Code complete, waiting for review?
          │         │
          │         └──► IN REVIEW
          │
          └── All acceptance criteria met?
                    │
                    └──► DONE
```

---

## Decision Tree: I'm Stuck - What Do I Do?

```
START: I'm stuck because...
          │
          ├── I don't understand the requirements
          │         │
          │         ├── Can I figure it out from ticket? ──Yes──► Keep going
          │         │         │
          │         │        No
          │         │         │
          │         └──► Move to BLOCKED
          │              Comment: What's unclear
          │              Tag: PM + business owner
          │
          ├── I don't know the technical approach
          │         │
          │         ├── Can I research/prototype in < 2h? ──Yes──► Do it
          │         │         │
          │         │        No
          │         │         │
          │         └──► Create SPIKE
          │              Timebox: 2-6 hours
          │              Parent ticket waits
          │
          ├── I need a decision from someone
          │         │
          │         └──► Move to BLOCKED
          │              Comment: What decision, from whom
          │              Tag: Person in Discord with [NEEDS-DECISION]
          │
          ├── I'm waiting for another ticket
          │         │
          │         └──► Move to BLOCKED
          │              Comment: Which ticket, who owns it
          │              Tag: PM + ticket owner
          │
          ├── Something is broken / not working
          │         │
          │         ├── Is it my code? ──Yes──► Debug it
          │         │         │
          │         │        No
          │         │         │
          │         └──► Move to BLOCKED
          │              Comment: What's broken
          │              Tag: Owner of broken thing
          │
          └── I'm being asked to do conflicting things
                    │
                    └──► Move to BLOCKED
                         Comment: What's the conflict
                         Tag: PM → Pavel for priority decision
```

---

## Timeline: Healthy vs Unhealthy Ticket

```
HEALTHY TICKET TIMELINE
━━━━━━━━━━━━━━━━━━━━━━━━

Day 0:  IDEA created
Day 1:  PM triages → DRAFT
Day 2:  Shaped with stakeholders → READY FOR CLARIFICATION
Day 3:  Start Gate items filled
Day 4:  Approvals received → READY
Day 5:  Sprint planning → committed
Day 6:  Dev pulls → IN PROGRESS
Day 7:  [development]
Day 8:  [development]
Day 9:  Code complete → IN REVIEW
Day 10: Approved → DONE

Total: 10 days (expected)
Blocked time: 0 days ✅


UNHEALTHY TICKET TIMELINE (What we used to do)
━━━━━━━━━━━━━━━━━━━━━━━━

Day 0:   IDEA created
Day 1:   [sits in IDEA]
Day 7:   PM finally triages → DRAFT
Day 8:   [sits in DRAFT - unclear who shapes it]
Day 14:  Pushed to IN PROGRESS (skipping Start Gate!) ❌
Day 15:  Dev starts, realizes requirements unclear
Day 16:  Dev tries to figure it out alone
Day 21:  Dev still stuck, hasn't told anyone
Day 28:  PM asks for update, discovers problem
Day 29:  Requirements clarified
Day 30:  Dev restarts work
Day 35:  Scope changed mid-work → rework
Day 42:  Finally done

Total: 42 days (6 weeks!)
Should have been: ~10 days (3 days of actual work)
Hidden blocked time: ~30 days ❌

THIS IS WHY WE HAVE THE START GATE.
```

---

# Part 9: Lifecycle Checklist Summary

## For Every Ticket Type

| Stage | What Must Happen | Who | Max Time |
|-------|------------------|-----|----------|
| **IDEA** | Triage: tag, classify, duplicate check | PM | 48h |
| **DRAFT** | Shape problem, identify stakeholders | PM + Business | 1 week |
| **READY FOR CLARIFICATION** | Fill all Start Gate items, get approvals | PM + Approvers | 1 week |
| **READY** | Available for sprint planning | - | Until planned |
| **IN PROGRESS** | Active development, daily updates | Dev | Per estimate |
| **BLOCKED** | Document + escalate same day | Dev + PM | Resolve < 24h |
| **IN REVIEW** | Verify acceptance criteria | Reviewer | 2 days |
| **DONE** | Can be demoed, value delivered | - | - |

---

## Red Flags to Watch For

| Red Flag | What It Means | Action |
|----------|---------------|--------|
| Ticket in IDEA > 2 days | PM not triaging | PM: triage now |
| Ticket in DRAFT > 1 week | Problem not being shaped | PM: escalate or close |
| Ticket in CLARIFICATION > 1 week | Approvers not responding | PM: escalate to Pavel |
| Ticket in PROGRESS > 3 days no update | Dev not communicating | PM: check in immediately |
| Ticket in BLOCKED > 24h | Blocker not being resolved | PM: escalate up chain |
| Ticket in REVIEW > 2 days | Reviewer bottleneck | PM: reassign or escalate |
| Same ticket blocked multiple times | Scope unclear | Create Spike or close |

---

*This document shows how work should flow. The PM Bible shows the rules. Together, they define how Robuxio executes.*

**Version:** 1.0  
**Last Updated:** January 2026  
**Owner:** Azara (Interim PM)
