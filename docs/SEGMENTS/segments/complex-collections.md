---
title: Complex collections
excerpt: >-
  How complex collection traits, like subscriptions, differ from standard traits
  — with filtering examples and known behavior to watch for.
deprecated: false
hidden: false
metadata:
  description: >-
    How complex collection traits — such as a user's subscriptions — differ from
    standard traits, with examples and known filtering behavior.
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">Complex collections let you filter segments on repeating records, such as a user's subscriptions. Use them to target users based on subscription-level detail like plan, status, and price.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.</li>
  <li>You should be familiar with building segments. See <a href="/recurly-engage/docs/segments" target="_blank">Overview: segments</a>.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Filters on different sub-attributes within the same collection are evaluated independently, which can produce broader matches than you expect. See <a href="#filtering-behavior">Filtering behavior</a> below.</li>
</ul>

# Definition

<div class="rp-definition">Most traits hold a single value per user, such as a plan code, a lifetime value, or a signup date. A complex collection is different: it's a set of repeating records per user, where each record has its own sub-attributes.</div>

Subscriptions are the collection type available today. A single user can have more than one subscription record, for example one active plan and one expired plan, and each record carries its own plan, status, price, and renewal dates. Complex collections let you filter on those sub-attributes when you build a segment.

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bullseye" aria-hidden="true"></i></div>
    <strong>Richer targeting</strong>
    <span>Filter on subscription-level detail, such as plan, status, and price, rather than a single flattened value per user.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-layer-group" aria-hidden="true"></i></div>
    <strong>Handles multi-subscription users</strong>
    <span>Represent users who hold more than one subscription, at once or over time, instead of exposing only their most recent one.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Composable filters</strong>
    <span>Add multiple sub-attributes to the same collection filter to narrow a segment further.</span>
  </div>
</div>

# Key details

## Build a filter on a complex collection

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Select Subscriptions</h4><p>In the segment builder, select <span style={{fontWeight: "bold"}}>Subscriptions</span> from the trait dropdown.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Choose a sub-attribute</h4><p>Choose the <span style={{fontWeight: "bold"}}>sub-attribute</span> you want to filter on. This is the specific dimension within the collection, such as plan, status, or price.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Set the match type</h4><p>Set your <span style={{fontWeight: "bold"}}>match type</span> and criteria for that sub-attribute.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Add more sub-attributes</h4><p>Add more sub-attributes to the same collection filter to refine it further.</p></div>
  </div>
</div>

## Filtering behavior

Filters on different sub-attributes within a subscription collection are evaluated <span style={{fontWeight: "bold"}}>independently across all of a user's subscription records</span>, not against a single matching record.

This means a user qualifies if _any_ of their subscriptions matches criterion A and _any_ of their subscriptions matches criterion B. Those can be two different subscriptions. The filter doesn't require both conditions to be true on the same record.

### Example

Say you build a segment with two subscription filters:

<ul class="rp-list">
  <li>Plan = Premium</li>
  <li>Status = Expired</li>
</ul>

A user with these two subscription records would match this segment:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Subscription</td><td>Plan</td><td>Status</td></tr>
  <tr><td>A</td><td>Premium</td><td>Active</td></tr>
  <tr><td>B</td><td>Basic</td><td>Expired</td></tr>
</table>

No single subscription of this user's is both Premium _and_ expired, but the user still matches. Subscription A satisfies the Plan filter, and subscription B satisfies the Status filter, independently of each other.

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Why this matters</strong>If your intent is "users whose Premium subscription has expired," this filter setup also captures users like the one above, whose Premium subscription is still active and whose expired subscription was a different, unrelated plan. Build and review segment membership carefully when you combine sub-attributes on a complex collection, since the result can be broader than it first appears.</div>
</div>
