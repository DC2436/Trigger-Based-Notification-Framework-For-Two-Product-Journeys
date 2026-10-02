# Trigger-Based-Notification-Framework-For-Two-Product-Journeys
A product notification framework designed for two Pitchsap product journeys: **Personality Test** and **AI Review**.

The work focused on identifying notification gaps, mapping user states to triggers, defining appropriate notification cadences, and designing contextual email communication.

**Core model:**  
Product Event → User State → Trigger → Notification → Follow-up Condition → Stop

---

## Overview

Users interact with a product through different states. A notification that is useful immediately after an event may become unnecessary or repetitive if the user has already acted.

I approached the notification system as part of the overall product journey rather than as a collection of individual emails.

The objective was to determine:

- What should trigger a notification?
- When should it be sent?
- Should it be automated or manually handled?
- How important is the notification?
- Does the user require a single email or a follow-up sequence?
- When should the system stop sending reminders?

---

## Scope

The framework was designed for two product features.

### 1. Personality Test

The notification journey covered:

- User starts the test
- User leaves before completing it
- User remains inactive after a follow-up
- User completes the test
- Personality results are successfully generated
- Results are generated but not viewed
- Results remain unopened after a follow-up
- Results generation fails

### 2. AI Review

The notification journey covered:

- Payment is successful
- AI review generation begins
- AI review is successfully generated
- Review is ready but remains unopened
- Review remains unopened after a follow-up
- Payment fails
- Payment succeeds but AI generation fails
- AI generation takes longer than the expected processing window

---

## Notification Gap Analysis

I created a structured notification matrix for each feature.

Each potential notification was evaluated across:

| Dimension | Purpose |
|---|---|
| User situation / trigger | What happened in the product |
| Email | What communication is required |
| Stage | Immediate, follow-up, last reminder, or exception |
| Automation | Automated or manual |
| Priority | P0 / P1 |
| Existing coverage | Whether the notification already existed |

This allowed me to identify where important user states were not adequately covered by existing notifications.

---

## Notification Cadence

Not every user state requires a single email.

I designed different cadences depending on what happened after the initial trigger.

### Single Notification

Used when the event itself is sufficient.

**Trigger → Immediate notification**

Example:

**Personality Test completed → Completion notification**

### Reminder Sequence

Used when a user starts an action but does not complete it.

**User starts action → User leaves incomplete → Follow-up reminder → Still incomplete → Last reminder → STOP**

The stopping condition is important because an engagement mechanism should not turn into unnecessary notification volume.

### Result Re-engagement

For results that have been generated but not viewed:

**Result generated → User does not view → Follow-up → Still unopened → Final reminder → STOP**

This makes the system responsive to **user behavior**, rather than simply sending the same message repeatedly.

### Exception Notifications

Some notifications are not intended for engagement or reactivation.

They exist to communicate that the expected product flow did not complete normally.

Examples include:

- Payment failure
- AI generation failure
- Generation taking longer than expected

These notifications provide transparency and, where appropriate, a recovery or support path.

---

# Example: AI Review Notification Journey

## B1 — Review Successfully Generated

**Trigger:**  
AI review has been successfully generated.

**Stage:** Immediate

**Objective:**  
Tell the user that their review is ready and direct them back to the product.

**Subject concept:**  
"We just finished looking at your idea."

**CTA:**  
View Your AI Review

---

## B2 — Review Ready but Unopened

**Trigger:**  
The review is ready, but the user has not viewed it.

**Stage:** Follow-up

**Objective:**  
Re-engage the user without simply repeating the original notification.

**Subject concept:**  
"There's something you should see about your idea."

**CTA:**  
View Your AI Review

---

## B3 — Review Still Unopened

**Trigger:**  
The review remains unopened after the follow-up.

**Stage:** Last reminder

**Objective:**  
Provide one final opportunity to return to the review.

**Subject concept:**  
"Your idea is still waiting for you."

**CTA:**  
View Your AI Review

After the final reminder, the sequence stops.

---

## Subject Line Strategy

I intentionally avoided relying only on functional subject lines such as:

> "Your AI Review is ready."

Instead, I explored **contextual curiosity** as a UX-writing strategy.

Examples:

- "We just finished looking at your idea."
- "There's something you should see about your idea."
- "Your idea is still waiting for you."

### Hypothesis

A subject line that creates relevant curiosity may increase the likelihood that a user opens the email and returns to the product.

The approach was designed around three constraints:

1. The subject should create curiosity.
2. It should remain truthful to the user's actual context.
3. It should avoid misleading clickbait.

This could be validated through metrics such as:

- Email open rate
- Click-through rate
- Feature completion rate
- Result-view rate
- Re-engagement rate

---

## Prioritization

Notifications were prioritized based on their importance to the product journey.

### P0

High-importance notifications associated with critical product events or user outcomes.

Examples:

- Payment status
- Successful result generation
- Failed generation
- Important completion events

### P1

Lower-criticality follow-ups or exception states that remain useful to the user but are not as time-sensitive.

The objective was not to maximize the number of emails.

It was to identify **high-value notification moments** while reducing unnecessary communication.

---

## Product Decision Framework

For each notification opportunity, I considered:

**What happened?**  
↓  
**What is the user's current state?**  
↓  
**Does the user need communication?**  
↓  
**What is the appropriate message?**  
↓  
**Should it be immediate or delayed?**  
↓  
**Does the user need a follow-up?**  
↓  
**When should the sequence stop?**

This helped separate genuine product requirements from notifications that could create unnecessary noise.

---

## Product Thinking Demonstrated

This project involved:

- Product requirement thinking
- User journey mapping
- Trigger identification
- Behavioral state analysis
- Notification gap analysis
- Notification prioritization
- Notification cadence design
- Re-engagement strategy
- UX writing
- Exception handling
- Automation vs. manual workflow decisions
- Product documentation

---

## Outcome

The result was a structured notification framework for two Pitchsap product journeys.

Instead of defining notifications as isolated emails, the framework connected:

**Product Event → User State → Trigger → Notification → Follow-up → Stopping Condition**

This provided a structured foundation for future notification implementation, experimentation, and measurement.

---

## Role

**Product Management Intern — Pitchsap**

Relevant areas:

**Product Research · User Journeys · Product Documentation · UX · Notification Strategy · QA**

---

## Note

This case study presents the product thinking and framework at a high level.

Internal Jira tickets, private documentation, implementation details, and confidential company information have not been included.
