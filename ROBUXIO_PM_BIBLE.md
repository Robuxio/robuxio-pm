# Robuxio PM Bible
## Pragmatic Execution for a Distributed Team
### Version 2.0 – Post-Hakan Era

---

## Why This Version Exists

**What We Learned the Hard Way:**

| Problem | What Happened | Cost |
|---------|---------------|------|
| **6 weeks → 3 days** | Work started without being startable | Factsheet disaster, trust lost |
| **Silence = Approval** | People assumed no reply meant yes | Wrong work built |
| **CTO as Safety Net** | Devs waited for Deneb instead of solving | Single point of failure |
| **PM as Coordinator** | Hakan tracked status but didn't drive outcomes | Process existed but didn't work |
| **Part-time Reality Ignored** | Framework assumed full-time commitment | Ceremonies couldn't happen |

**This Bible merges hard lessons with Azara's pragmatic approach.**

---

## Current Team Structure

### Interim PM: Javier Azara

| Attribute | Reality |
|-----------|---------|
| **Role** | PM-Light + Active Developer |
| **Time** | ~16 hours/month PM duties + development work |
| **Authority** | Can block unclear work, cannot hire/fire |
| **Limitation** | Cannot attend all meetings, must prioritize |

> ⚠️ **Conflict of Interest Acknowledgment:** Azara is both a developer AND the PM. When his own tickets need review, CTO (Deneb) acts as process enforcer.

---

### The Robuxio Team

| Role | Person | Responsibility | Approves |
|------|--------|----------------|----------|
| **CEO** | Pavel | Business priority, strategic decisions | Strategic items |
| **COO** | Dries | Client-facing tools, business context | Client/UX correctness |
| **CTO** | Deneb | Technical architecture, feasibility | All tickets (technical) |
| **Quant** | Olda | Trading logic, financial correctness | Trading tickets |
| **PM-Light** | Azara | Flow, clarity, process enforcement | Nothing (enforces process) |
| **Developers** | Deneb, Leonardo, Jamolpe, Erro, Azara | Delivery | Nothing (execute) |

---

## Part 1: The 10 Non-Negotiable Rules

These rules exist because we broke them and paid the price.

### Rule 1: Jira Is the Only Place Work Exists

- All requests start as Jira tickets
- No execution based on Discord, email, or meetings alone
- Meeting outcomes logged in Jira
- **If it's not in Jira, it does not exist**

> 🔴 **We learned:** Voice notes and scattered documents caused the factsheet disaster.

---

### Rule 2: Silence Is NOT Approval

- Approval happens **explicitly** in Jira (comment or status change)
- No work starts because "I didn't get a reply"
- If approval is needed and not given → ticket is **Blocked**
- Approvers must say "Approved" or "Not Approved" — silence blocks

> 🔴 **We learned:** Implicit approvals led to building the wrong things.

---

### Rule 3: Work Does Not Start Without the Start Gate

Every ticket needs **ALL** of these before "In Progress":

| Required | Description |
|----------|-------------|
| **Outcome** | "When this is done, we can ___" |
| **In Scope** | 2-5 bullets of what we WILL do |
| **Out of Scope** | Explicit exclusions |
| **Acceptance Criteria** | 3-7 testable conditions |
| **Owner** | Single person responsible |
| **Approvers** | Assigned AND have explicitly approved |
| **Dependencies** | Listed |
| **Example/Mock** | Screenshot, example data, expected output |

**Missing ANY = ticket stays in "Ready for Clarification"**

> 🔴 **We learned:** The "6 weeks → 3 days" factsheet failure happened because work started without passing this gate.

---

### Rule 4: One Developer, One Ticket (WIP = 1)

- Each developer works on **one ticket at a time**
- No parallel work (context switching kills productivity)
- Finish before pulling the next
- Exception: Only if blocked AND blocker takes >24h to resolve

> 🔴 **We learned:** Part-time developers with multiple tickets never finish any of them.

---

### Rule 5: Scope Changes Go Back

- Any change to scope mid-work → ticket goes back to "Ready for Clarification"
- This is not punishment; this is protection
- If scope is unclear → **stop and clarify before continuing**
- "Agility" means controlled change, not constant drift

---

### Rule 6: Uncertainty Is Escalated Same Day

- If a developer is unsure → escalate **the same workday**
- Uncertainty is not a personal failure
- **Silence is the failure**
- Ambiguity is never "worked around" – it is surfaced

> 🔴 **We learned:** Devs absorbed ambiguity instead of escalating. Problems discovered weeks late.

---

### Rule 7: 24 Hours Without Progress = Blocked

- No real progress in 24h → ticket moves to **Blocked**
- When blocked, must state:
  - What is blocking
  - Who must unblock
  - What decision is needed
- PM acts immediately (same day)

> 🔴 **We learned:** Blocked work was invisible for days/weeks.

---

### Rule 8: Trading Tickets Require Dual Approval

For ANY ticket touching trading logic (TWR, NAV, exposure, signals, fees):

| Role | Must Approve |
|------|--------------|
| **Deneb (CTO)** | Technical correctness |
| **Olda (Quant)** | Financial/trading correctness |

**Both must explicitly approve BEFORE development starts.**

> 🔴 **We learned:** Trading-related tickets shipped with bugs because only one person reviewed.

---

### Rule 9: Developers Can (and Must) Refuse Unclear Work

- If requirements are garbage, say "I can't start until I have X, Y, Z"
- Do NOT "start anyway and figure it out"
- Create a **Spike** (2-6h investigation) if truly unclear
- The power to refuse is protection, not defiance

> 🔴 **We learned:** Devs started unclear work, then blamed requirements. Both sides lost.

---

### Rule 10: The CTO Is Not the Safety Net

- Deneb is for **architecture and technical direction**, not daily problem-solving
- First ask: "Can I solve this myself?"
- Second ask: "Can I find the answer in docs/code?"
- Third ask: "Ask the team"
- Last resort: "Ask Deneb"

> 🔴 **We learned:** Devs defaulted to "ask Deneb" → CTO became bottleneck, devs stopped growing.

---

## Part 2: Sprint Structure (Monthly Cadence)

### Why Monthly Sprints

| Reason | Explanation |
|--------|-------------|
| **Part-time reality** | Weekly sprints impossible with fragmented availability |
| **Reduced overhead** | Fewer ceremonies = more development time |
| **Better predictability** | Longer planning horizon for business |
| **Buffer for life** | Day jobs, vacations, unexpected issues have room |

### Sprint Flow

```
Week 0 (Last Week of Previous Sprint)
├── Business Alignment Meeting (Azara + Robuxio)
├── Backlog Refinement (mostly async)
└── Jira Preparation

Week 1 (Sprint Start)
├── Sprint Planning (Dev Team Only)
└── Development begins

Weeks 2-3
├── Daily async updates
├── Standups (flexible, not rigid)
└── Development continues

Week 4
├── Development wraps up
├── Sprint Review (with business)
└── Retrospective (dev team)
```

---

## Part 3: Ceremonies (Minimal, High Impact)

### 3.1 Business Alignment Meeting (Pre-Planning)

| Attribute | Value |
|-----------|-------|
| **Purpose** | Align on priorities before technical planning |
| **Participants** | Azara + Pavel/Dries |
| **Frequency** | Once per month, before sprint planning |
| **Duration** | ~1 hour |
| **Language** | English |

**Outcome:**
- Prioritized list of business deliverables
- Clear understanding of business goals and urgency
- **NO technical discussion** – that happens in planning

---

### 3.2 Sprint Planning (Development Only)

| Attribute | Value |
|-----------|-------|
| **Purpose** | Define what can realistically be delivered |
| **Participants** | Dev team only (Deneb, Leo, Jamolpe, Erro, Azara) |
| **Duration** | ~2 hours |
| **Business attends** | NO – input already consolidated |

**Agenda:**
1. Presentation of prioritized deliverables (by Azara)
2. Review of epics and tasks in Jira
3. **Start Gate Check** for each candidate ticket
4. Estimation and capacity check
5. Commitment to sprint scope
6. Define Sprint Goal

**Output:** Sprint backlog with ONLY tickets that pass Start Gate.

---

### 3.3 Daily Updates (Async-First)

| Attribute | Value |
|-----------|-------|
| **Purpose** | Early detection of blockers |
| **Participants** | All developers |
| **Frequency** | Once per workday |
| **Format** | Jira comment or Discord |

**Daily Update Format:**
```
Next step: [what I'm working on]
Blocker: [none / describe]
ETA Confidence: [High / Medium / Low]
```

**Sync Standups:** Only when needed (not forced daily). If everyone updates async, skip the meeting.

---

### 3.4 Backlog Refinement (Mostly Async)

| Attribute | Value |
|-----------|-------|
| **Purpose** | Prepare upcoming work for efficient planning |
| **Who Does It** | Azara (with dev input when needed) |
| **Frequency** | 3-5 days before planning |
| **Duration** | ~1.5 hours (mostly async) |

**PM Refinement Checklist:**
- [ ] Each delivery maps to an Epic
- [ ] Tasks exist in Jira and are linked to Epic
- [ ] Tickets have clear titles and basic context
- [ ] Check for duplicates
- [ ] Assign domain labels
- [ ] Flag tickets needing dev clarification

---

### 3.5 Sprint Review (With Business)

| Attribute | Value |
|-----------|-------|
| **Purpose** | Demonstrate completed work, collect feedback |
| **Participants** | Dev team + Pavel + Dries |
| **Duration** | 1-1.5 hours |
| **Rule** | If it can't be demoed, it's not "Done" |

**Format:**
- Live demos of completed work
- Review: delivered vs planned
- Business validation and feedback
- Identify what needs follow-up

---

### 3.6 Retrospective (Dev Team Only)

| Attribute | Value |
|-----------|-------|
| **Purpose** | Improve team processes |
| **Participants** | Dev team only |
| **Duration** | 1 hour max |
| **Output** | 1-2 concrete improvement actions |

**Questions:**
1. What caused blockers this sprint?
2. What caused rework?
3. What rule should we change?

> ⚠️ **We will NOT skip retros.** Past failure: "1.5 months without retro" meant problems compounded.

---

## Part 4: The Jira Workflow

### Status Flow

```
┌─────────┐
│  IDEA   │ ← All requests start here
└────┬────┘
     │ PM Triage (within 48h)
     ▼
┌─────────┐
│  DRAFT  │ ← Shaping the problem, not solving it
└────┬────┘
     │ Ready to formalize?
     ▼
┌─────────────────────────┐
│ READY FOR CLARIFICATION │ ← ⚠️ STOP ZONE - Most critical status
└────────────┬────────────┘
             │ ALL fields complete + ALL approvers approved?
             ▼
┌─────────┐
│  READY  │ ← START GATE PASSED - Work can begin
└────┬────┘
     │ Dev pulls ticket
     ▼
┌─────────────┐     ┌─────────┐
│ IN PROGRESS │◄───►│ BLOCKED │ ← 24h no progress = move here
└──────┬──────┘     └─────────┘
       │ Code complete?
       ▼
┌───────────┐
│ IN REVIEW │
└─────┬─────┘
      │ Acceptance criteria met?
      ▼
┌─────────┐
│  DONE   │
└─────────┘
```

---

### Status Definitions

#### IDEA
- **Purpose:** Capture raw requests from any source
- **Who Creates:** Anyone
- **PM Action:** Triage within 48h (tag source, classify type, check duplicates)
- **Exit:** Accept → Draft, Reject → Closed

#### DRAFT
- **Purpose:** Shape the problem (NOT solve it)
- **Contributors:** Dries (client), Olda (trading), Deneb (architecture)
- **NOT Allowed:** Development work
- **Exit:** Ready to formalize → Ready for Clarification

#### READY FOR CLARIFICATION ⚠️
- **Purpose:** **STOP ZONE** – Prevent unclear work from starting
- **This is where the "6 weeks → 3 days" failure happened**
- PM identifies what's missing, assigns who must clarify
- **Exit:** ALL mandatory fields complete AND ALL approvers explicitly approved → Ready

#### READY (Start Gate Passed)
- **Purpose:** Ticket is STARTABLE
- **Requirements:** All 8 Start Gate items checked off
- **Exit:** Dev pulls ticket → In Progress

#### IN PROGRESS
- **Purpose:** Active development
- **Rules:** WIP = 1 per dev
- **Before Starting:** Dev posts plan + assumptions
- **Exit:** Code complete → In Review

#### BLOCKED
- **Triggered By:** No progress in 24h, missing decision, dependency unresolved
- **Required:** What's blocking, who must unblock, what decision needed
- **PM Action:** Act immediately (same day)

#### IN REVIEW
- **Purpose:** Validate against acceptance criteria
- **Reviewers:** Trading → Olda, Technical → Deneb, Client → Dries
- **Exit:** All criteria verified → Done

#### DONE
- **Criteria:** ALL acceptance criteria met
- **NOT "almost done"** – it works or it doesn't

---

## Part 5: Approval Matrix

| Ticket Type | Required Approvers | Must Both Approve? |
|-------------|-------------------|-------------------|
| **Core Trading** (engine, signals, risk) | Deneb + Olda | ✅ Yes |
| **Trading-Related** (TWR, NAV, fees, factsheets) | Deneb + Olda | ✅ Yes |
| **Client/Support/UX** (dashboards, support tools) | Deneb + Dries | ✅ Yes |
| **Pure Infra** (cloud, deployment) | Deneb only | N/A |
| **Strategic/High-Risk** | + Pavel | All listed |

### Approval Rules

1. **Silence ≠ Approval** – Must see "Approved" in Jira
2. Approval happens **BEFORE** status changes to "Ready"
3. For trading tickets, **BOTH Deneb AND Olda must approve**
4. Approvals are visible in ticket history (audit trail)

---

## Part 6: Business → Development Communication

### Dedicated Discord Channel

**Rules:**
- Only business stakeholders submit requests
- No technical discussions in this channel
- PM monitors and converts to Jira tickets

**Request Format:**
```
Title: [Short descriptive title]
Business Goal: [What we're trying to achieve]
Description: [Details]
Urgency: [High / Medium / Low]
```

### No Request Enters Sprint Without:
1. Being converted to Jira ticket
2. Going through refinement
3. Passing Start Gate
4. Being included in sprint planning

---

## Part 7: Definition of Ready (DoR) – Start Gate Checklist

A ticket is ready **ONLY IF** all boxes are checked:

- [ ] Linked to an Epic
- [ ] **Outcome** defined ("When done, we can ___")
- [ ] **In-scope** written (2-5 bullets)
- [ ] **Out-of-scope** written (explicit exclusions)
- [ ] **Acceptance criteria** (3-7 testable conditions)
- [ ] **Dependencies** listed
- [ ] **Example/mock** provided
- [ ] Correct **approvers** assigned
- [ ] All approvers have **explicitly approved** in Jira
- [ ] **Priority** defined (P0/P1/P2)
- [ ] **Owner** assigned (single dev)

> **Missing ANY item = ticket cannot move to "Ready"**

---

## Part 8: Definition of Done (DoD)

A ticket is Done **ONLY IF**:

- [ ] All acceptance criteria are met (verified, not assumed)
- [ ] Code is merged to develop branch (if applicable)
- [ ] Tested (unit tests, manual testing as appropriate)
- [ ] Deployed (if applicable)
- [ ] Functionally validated by appropriate reviewer
- [ ] Can be demoed (or has logs/tests for pure infra)

> **"Almost done" is NOT done.**

---

## Part 9: Escalation Protocol

### When to Escalate

| Situation | Escalate To | Timeline |
|-----------|-------------|----------|
| Technical decision needed | Deneb | Same day |
| Trading logic unclear | Olda | Same day |
| Client impact unclear | Dries | Same day |
| Strategic/priority conflict | Pavel | Within 24h |
| Dev blocked >24h | PM (Azara) → appropriate owner | Immediately |

### How to Escalate

1. Move ticket to **Blocked** status
2. Add comment: what's needed, who's needed, deadline
3. Tag person in Discord with `[BLOCKER]` prefix
4. Follow up same day

### Urgency Tags

| Tag | Meaning | Expected Response |
|-----|---------|-------------------|
| `[BLOCKER]` | Work stopped | Immediate |
| `[NEEDS-DECISION]` | Waiting on choice | Same day |
| `[ASYNC]` | Not urgent | Within 24h |

---

## Part 10: Handling Unclear Work (Spikes)

When a ticket is unclear, **DO NOT "start anyway"**.

### Spike Definition

| Attribute | Value |
|-----------|-------|
| **Purpose** | Time-boxed investigation |
| **Duration** | 2-6 hours max |
| **Output Required** | Written findings, proposed approach, updated AC |
| **Result** | Original ticket becomes startable |

### Spike Template

```
## Spike: [Title]

**Question to Answer:**
[What we need to figure out]

**Timebox:** [2-6 hours]

**Context:**
[Why is this unclear? What do we know?]

**Required Output:**
- [ ] Written findings summary
- [ ] Proposed approach
- [ ] Updated acceptance criteria for parent ticket

**Parent Ticket:** [Link]
```

---

## Part 11: Priority Conflict Resolution

| Conflict | Who Wins |
|----------|----------|
| CEO vs Anyone | CEO (business decision) |
| CTO vs PM | CTO on technical, PM on timing |
| Quant vs COO | Each owns their domain |
| Multiple P0s | Escalate to Pavel |

**All priority decisions documented in Jira. No verbal overrides.**

---

## Part 12: PM-Light Effort Estimation

Azara's monthly PM effort (separate from development):

| Activity | Frequency | Duration | Monthly Hours |
|----------|-----------|----------|---------------|
| Business alignment meeting | 1/month | 1h | 1h |
| Backlog refinement | 1/month | 1.5h | 1.5h |
| Sprint planning facilitation | 1/month | 2h | 2h |
| Sprint review | 1/month | 1.5h | 1.5h |
| Retrospective | 1/month | 1h | 1h |
| Jira maintenance & async coordination | Ongoing | ~20 min/day | ~7h |
| Start Gate reviews (ad-hoc) | As needed | ~2h total | 2h |
| **Total** | | | **~16 hours/month** |

---

## Part 13: What We Track (Metrics)

### Weekly Metrics (PM Responsibility)

| Metric | What It Measures | Goal |
|--------|------------------|------|
| **Cycle Time** | Ready → Done | Trend down |
| **Time in Blocked** | Where work gets stuck | Minimize |
| **Time in Clarification** | How long clarity takes | Minimize |
| **Rework Rate** | Tickets moved back after start | < 10% |
| **Start Gate Pass Rate** | Tickets ready at planning | > 80% |

### What We Do NOT Track

- ❌ Hours worked
- ❌ Personal velocity
- ❌ "Busyness" indicators
- ❌ Lines of code

> **Measure flow, not fear.**

---

## Part 14: Working Agreements

### For Developers

1. **Post daily updates** (Jira or Discord) – even if "no change"
2. **Refuse unclear work** – ask for Spike if needed
3. **Escalate same day** – don't absorb ambiguity
4. **One ticket at a time** – finish before pulling next
5. **Ask team before asking CTO** – build collective knowledge

### For Business (Pavel, Dries)

1. **Submit requests through proper channels** – Discord format or Jira
2. **Provide written requirements** – no voice notes as primary source
3. **Approve explicitly** – silence blocks work
4. **Attend Sprint Review** – validate delivered work
5. **Respect sprint boundaries** – changes are expensive

### For PM (Azara)

1. **Triage within 48h** – nothing lingers in Idea
2. **Enforce Start Gate** – no exceptions for "just this once"
3. **Act on blockers same day** – visibility is your job
4. **Protect the sprint** – push back on mid-sprint scope changes
5. **When wearing dev hat** – your tickets follow same rules

### For CTO (Deneb)

1. **Approve tickets explicitly** – silence is not approval
2. **Approve or reject quickly** – don't be the bottleneck
3. **Step back from daily decisions** – trust the process and team
4. **Review Azara's tickets** – conflict of interest coverage
5. **Focus on architecture** – that's your unique value

---

## Part 15: Conflict of Interest Protocol

Since Azara is both PM and Developer:

| Situation | Who Handles |
|-----------|-------------|
| Azara's tickets need Start Gate review | Deneb reviews |
| Azara's work needs approval | Normal approvers (Deneb/Olda/Dries) |
| PM decision affects Azara's workload | Deneb has veto |
| Sprint capacity planning | Azara declares his dev hours, team validates |

**Transparency Rule:** Any potential conflict is flagged in Jira comments.

---

## Part 16: Ticket Templates

### Story Template

```
## Problem Statement
[What problem does this solve? 1-2 sentences]

## Outcome
When this is done, we can: [specific outcome]

## In Scope
- [ ] [Specific deliverable 1]
- [ ] [Specific deliverable 2]
- [ ] [Specific deliverable 3]

## Out of Scope
- [What we explicitly will NOT do]

## Acceptance Criteria
- [ ] [Testable criterion 1]
- [ ] [Testable criterion 2]
- [ ] [Testable criterion 3]

## Dependencies
- [System/person/data needed]

## Example/Mock
[Screenshot, example data, expected output]

---
**Type:** [Core Trading / Trading-Related / Client-Support-UX]
**Owner:** [Single dev]
**Approvers:** [Based on type]
**Priority:** [P0 / P1 / P2]
```

### Bug Template

```
## Bug Description
[What is broken?]

## Steps to Reproduce
1. [Step 1]
2. [Step 2]
3. [Step 3]

## Expected Behavior
[What should happen]

## Actual Behavior
[What actually happens]

## Impact
[Trading / Ops / UX / Compliance]

## Screenshots/Logs
[Attach evidence]

---
**Severity:** [Critical / Major / Minor / Trivial]
**Owner:** [Single dev]
**Priority:** [P0 / P1 / P2]
```

---

## Part 17: Quick Reference Card

### The 10 Rules (Summary)

1. **Jira is truth** – if not in Jira, doesn't exist
2. **Silence ≠ Approval** – explicit approval required
3. **Start Gate or no start** – all 8 items checked
4. **WIP = 1** – one ticket per dev
5. **Scope change = go back** – no silent drift
6. **Escalate same day** – uncertainty isn't absorbed
7. **24h = Blocked** – make stuck work visible
8. **Trading = dual approval** – Deneb + Olda
9. **Devs can refuse** – unclear work doesn't start
10. **CTO ≠ safety net** – team solves, CTO guides

### Approval Quick Reference

| Type | Approvers |
|------|-----------|
| Core Trading | Deneb + Olda |
| Trading-Related | Deneb + Olda |
| Client/UX | Deneb + Dries |
| Infra | Deneb |

### When in Doubt

1. Unclear → Create Spike (2-6h max)
2. Blocked → Move to Blocked, escalate same day
3. Scope changed → Back to Ready for Clarification
4. No response → Ticket is blocked, tag PM

---

## Part 18: Success Criteria

### You Know This Is Working When:

| Signal | Meaning |
|--------|---------|
| No ticket starts without Start Gate | Clarity before execution ✅ |
| Blocked tickets caught within 24h | Early detection works ✅ |
| Rework rate < 10% | Scope is clear upfront ✅ |
| Cycle time trending down | Flow is improving ✅ |
| No "6 weeks → 3 days" surprises | System prevents waste ✅ |
| Devs solving without CTO | Team is growing ✅ |
| Retros happen every sprint | Continuous improvement ✅ |

### Warning Signs It's Failing:

| Signal | Action |
|--------|--------|
| "Deneb will know" becomes common | Retro: reinforce Rule 10 |
| Tickets starting without approval | PM blocks and resets |
| Same problems recurring | Retro: find root cause |
| Standups/retros skipped | PM enforces, escalates if needed |
| Deadlines always slip | Review estimation process |

---

## Part 19: Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Dec 2024 | Hakan (PM) | Initial framework |
| 2.0 | Jan 2026 | Azara (Interim PM) | Merged pragmatic Scrum approach, acknowledged part-time reality, added lessons learned, monthly cadence |

---

## Signatures

By working with this team, you agree to follow these rules:

- [ ] Pavel (CEO)
- [ ] Dries (COO)
- [ ] Deneb (CTO)
- [ ] Olda (Quant)
- [ ] Javier Azara (Interim PM / Dev)
- [ ] Leonardo Rodríguez Martínez (Dev)
- [ ] Jamolpe (Dev)
- [ ] Javier Erro Garcia (Dev)

---

*"A good system makes the right thing easy and the wrong thing hard."*

*This Bible exists because we learned from our mistakes. Follow it.*
