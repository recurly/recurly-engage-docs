---
title: Cookie consent
excerpt: >-
  Explains why cookies can block the Engage tag under default consent settings
  and how to configure consent categorization and opt-out syncing correctly.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">If you're managing cookie consent, the Engage (Redfast) tag can get blocked before a visitor ever consents — and that can quietly stop critical functions like cancel-save from firing. Here's why it happens and how to configure consent categorization and opt-out syncing so Engage keeps working for every visitor.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#recommended-setup"><span class="rp-toc-num">2</span>Recommended setup</a>
    <a class="rp-toc-pill" href="#data-collection-practices"><span class="rp-toc-num">3</span>Data collection practices</a>
  </div>
</div>

# Definition

<div class="rp-definition">By default, the Engage tag loads with your site's default consent configuration. If that configuration categorizes the tag under Performance or Targeting, cookie managers block it until the visitor consents to that category. Because Engage deploys as a single script rather than per-prompt, this classification applies at the tag level, not to individual prompts.</div>

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong>If the Engage tag is categorized under Performance or Targeting, it won't load for any visitor who hasn't consented to that category — including visitors who need to reach critical functions like cancel-save or the on-hold state.</div>
</div>

# Recommended setup

Set the Engage tag's cookie category to Strictly Necessary. This ensures critical functions fire reliably for every visitor, regardless of consent status.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Categorize the Engage tag as Strictly Necessary</h4><p>Set this at the tag level in your cookie manager. Since Engage deploys as a single script, the category applies to the tag as a whole rather than to individual prompts.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Sync opt-out status into Engage</h4><p>Engage can read the cookie consent directly using live user trait ingest, recording that value as a user trait.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Build a segment for opted-out users</h4><p>Use the synced trait to create a separate segment for visitors who've opted out of targeting.</p></div>
  </div>
</div>

For this segment, you have two options:

<ul class="rp-list">
  <li>Exclude the segment fully from the experience</li>
  <li>Show a "blackbox" version — opted-out users still receive the experience, but you won't see the performance data for that flow</li>
</ul>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong>Either option keeps opted-out users on core functions like the paywall and the on-hold state — they just won't receive personalized experiences.</div>
</div>

# Data collection practices

By default, Recurly Engage collects only session timestamps. No personally identifiable information (PII) is collected unless you explicitly configure it, and IP addresses are never stored. Location targeting uses a one-way hash against a locally hosted GeoIP database. Cookies aren't used in platform operations unless you explicitly enable first-party cookies for your use case.

<div class="rp-nav-grid">

<Cards>
  <Card title="Data Privacy & Security" href="https://docs.recurly.com/recurly-engage/docs/data-privacy" target="_blank">
    Covers what is and isn't collected, cookie usage, IP address handling, and compliance (SOC 2 Type II, GDPR, CCPA).
  </Card>
  <Card title="Usage Tracking" href="https://docs.recurly.com/recurly-engage/docs/usage-tracking-1" target="_blank">
    Details the behavioral signals Engage captures, including visits, session duration, and custom events.
  </Card>
</Cards>
</div>

<br />

<br />
