---
title: Complex Collections
deprecated: false
hidden: false
metadata:
  description: >-
    How complex collection traits — such as a user's subscriptions — differ from
    standard traits, with examples and known filtering behavior.
  robots: index
---
# Overview

### Prerequisites

- Company or App Administrator permissions in Recurly Engage.
- Familiarity with building segments — see [Overview: Segments](/recurly-engage/docs/segments).

### Limitations

- Filters on different sub-attributes within the same collection evaluate independently — see [Filtering behavior](#filtering-behavior) below. This can produce broader matches than expected.
- \[TODO: Confirm with team] Subscriptions is the only complex collection trait currently supported — confirm before publishing whether others exist or are planned.

# Definition

Most traits hold a single value per user — a plan code, a lifetime value, a signup date. A **complex collection** is different: it's a set of repeating records per user, where each record has its own sub-attributes.

Subscriptions are the collection type available today. A single user can have more than one subscription record — for example, one active plan and one expired plan — and each record carries its own plan, status, price, and renewal dates. Complex collections let you filter on those sub-attributes when building a segment.

# Key benefits

- **Richer targeting**: Filter on subscription-level detail — plan, status, price — rather than a single flattened value per user.
- **Handles multi-subscription users**: Correctly represents users who hold more than one subscription at once or over time, instead of only exposing their most recent one.
- **Composable filters**: Add multiple sub-attributes to the same collection filter to narrow a segment further.

# Key details

## Building a filter on a complex collection

1. In the segment builder, select **Subscriptions** from the trait dropdown.
2. Choose a **sub-attribute** — the specific dimension within the collection you want to filter on (for example, plan, status, or price).
3. Set your **match type** and criteria for that sub-attribute.
4. Add additional sub-attributes to the same collection filter to refine it further.

## Filtering behavior

Filters on different sub-attributes within a subscription collection are evaluated **independently across all of a user's subscription records** — not against a single matching record.

This means a user qualifies if _any_ of their subscriptions matches criterion A and _any_ of their subscriptions matches criterion B. Those can be two different subscriptions; the filter doesn't require both conditions to be true on the same record.

### Example

Say you build a segment with two subscription filters:

- Plan = Premium
- Status = Expired

A user with these two subscription records would match this segment:

| Subscription | Plan    | Status  |
| ------------ | ------- | ------- |
| A            | Premium | Active  |
| B            | Basic   | Expired |

Even though no single subscription of this user's is both Premium _and_ expired, the user matches — subscription A satisfies the Plan filter, and subscription B satisfies the Status filter, independently of each other.

**Why this matters**: if your intent is "users whose Premium subscription has expired," this filter setup will also capture users like the one above, whose Premium subscription is still active and whose expired subscription was actually a different, unrelated plan. Build and review segment membership carefully when combining sub-attributes on a complex collection, since the result can be broader than it first appears.
