---
title: Adblocker mitigation
excerpt: >-
  Configuration guide for Ad Blocker Mitigation, enabling Recurly Engage to
  function when users have ad blockers enabled.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-page">
  <div class="rp-overview">Public reports (<a href="https://backlinko.com/ad-blockers-users" target="_blank">Backlinko</a>, <a href="https://www.statista.com/topics/3201/ad-blocking/#topicOverview" target="_blank">Statista</a>) indicate that up to 50% of web users employ ad blockers. Ad blockers may block third-party JavaScript tags, including the Recurly Engage tag, which disables your engagement prompts.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on the Enterprise plan or with the Ad Blocker Mitigation add-on</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.</li>
  <li>You must be on the Enterprise plan or have purchased the Ad Blocker Mitigation add-on.</li>
</ul>

# Definition

<div class="rp-definition">Ad Blocker Mitigation routes the Recurly Engage tag and API traffic through a customer-owned subdomain (for example, <code>track.yourcompany.com</code>) so that browser extensions no longer block prompt delivery. The change requires only a Domain Name System (DNS) update and reconfiguration of your tag manager.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-users" aria-hidden="true"></i></div>
    <strong>Maximized reach</strong>
    <span>Make sure prompts reach users even when ad blockers are enabled.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-globe" aria-hidden="true"></i></div>
    <strong>DNS-only setup</strong>
    <span>No code changes. Configure a canonical name (CNAME) record and update your script tag.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrows-rotate" aria-hidden="true"></i></div>
    <strong>Automatic updates</strong>
    <span>Recurly Engage continues to host and update software development kit (SDK) assets on the new subdomain.</span>
  </div>
</div>

# Key details

To enable Ad Blocker Mitigation, complete the following steps.

## Update DNS

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Agree on a subdomain</h4><p>Agree upon a subdomain (for example, <code>track.yourcompany.com</code>).</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Get the CNAME target</h4><p>Your Recurly Engage Customer Success Manager provides the CNAME target (for example, <code>yourapp.recurlyengage.com</code>).</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add a CNAME entry</h4><p>Your IT team adds a CNAME entry in your DNS.</p></div>
  </div>
</div>

<br />

<br />
