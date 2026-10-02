---
title: SSO integration
excerpt: >-
  Learn how Pulse’s Single Sign-On (SSO) feature works for enterprise clients.
  This guide explains key benefits, our partnership with WorkOS, and the steps
  for IT administrators to configure user access.
deprecated: false
hidden: false
metadata:
  title: Recurly Engage SSO Integration
  description: >
    Learn how Pulse’s Single Sign-On (SSO) feature works for enterprise clients.
    This guide explains key benefits, our partnership with WorkOS, and the steps
    for IT administrators to configure user access.
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">Single sign-on (SSO) lets users access multiple applications with a single set of login credentials, giving enterprise teams a more efficient and secure way to reach the tools they need. SSO is part of the Pulse Enterprise tier. For more information, reach out to your customer success manager.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on the Enterprise tier</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#set-up-single-sign-on"><span class="rp-toc-num">3</span>Set up single sign-on</a>
  </div>
</div>

# Definition

<div class="rp-definition">Pulse has partnered with WorkOS, an enterprise-focused identity platform, to offer SSO authentication. This partnership lets us support a wide range of identity providers (IdPs), including Okta, Auth0, Google Workspace, Azure AD, and ADP. Your team can log in to Pulse with your company’s existing IdP, so users don’t need separate credentials for our platform, which reduces password fatigue and improves security.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Stronger security</strong>
    <span>Centralized identity management through your IdP strengthens security protocols and makes it easier to enforce company-wide policies, like multi-factor authentication.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Better user experience</strong>
    <span>Users access Pulse with a single click, with no extra passwords to manage and less risk of being locked out of their accounts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Simpler user management</strong>
    <span>IT administrators can provision and de-provision user access directly from their IdP, so access is granted and revoked promptly. This also speeds up onboarding and offboarding.</span>
  </div>
</div>

# Set up single sign-on

Follow these steps to connect your company’s IdP and control who can access Pulse.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Accept the SSO invite and configure your IdP (IT admin)</h4><p>Once SSO is enabled for your domain, your IT admin receives an email invite to the SSO admin portal. The portal walks you through configuring your company’s IdP and includes a built-in connection test, so you can validate sign-in before rollout.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/7519caea2841827a157e29476ba58ccf6700ce45568ca88dc990538c23312916-workos-email-invite.png" align="center" width="75%" border={true} />


After setup, your domain is ready for SSO and the configured IdP appears in the portal.


<Image src="https://files.readme.io/49278dda307470debabd196c8116fec1337b1412f69fe8f68ceb4588e75cd966-workos-idp-list.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Approve users in Pulse (Pulse admin)</h4><p>When SSO is configured, users from your domain can authenticate with your IdP. For security and access control, a Pulse admin in your organization must approve each user before they can use their account. This two-step model ensures only authorized people gain access.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Sign in with your organization (users)</h4><p>On the Pulse login page, users click <span style={{fontWeight: "bold"}}>“Login with your organization”</span> and are redirected to your company’s SSO portal to complete authentication.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/1a6eddffb67af73a2d4689df12a86edcdc20492dfadad2db8904c760c49500f6-unnamed_1.png" align="center" width="75%" border={true} />
