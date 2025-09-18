---
title: SSO integration
excerpt: >-
  Learn how Pulse’s Single Sign-On (SSO) feature works for enterprise clients.
  This guide explains key benefits, our partnership with WorkOS, and the steps
  for IT administrators to configure user access.
deprecated: false
hidden: true
metadata:
  title: Recurly Engage SSO Integration
  description: >
    Learn how Pulse’s Single Sign-On (SSO) feature works for enterprise clients.
    This guide explains key benefits, our partnership with WorkOS, and the steps
    for IT administrators to configure user access.
  robots: index
---
# Overview

Single Sign-On (SSO) is a secure and streamlined authentication method that allows users to access multiple applications with a single set of login credentials. For **enterprise clients**, this provides a more efficient and secure way for employees to access the tools they need. 

Pulse offers SSO as part of its Enterprise tier, simplifying user access and management. For more information, please reach out to your customer success manager.

# Definition

Pulse has partnered with WorkOS, an enterprise-focused identity platform, to offer robust SSO authentication. This partnership allows us to support a wide range of Identity Providers (IDPs), including common ones like **Okta, Auth0, Google Workspace, Azure AD, and ADP**. 

The partnership with WorkOS ensures a smooth and secure integration, enabling your team to use your company’s existing identity provider to log in to Pulse. This eliminates the need for users to create and remember separate credentials for our platform, reducing password fatigue and increasing security.

# Key benefits

* **Enhanced Security:** Centralized identity management through your IDP strengthens security protocols and makes it easier to enforce company-wide security policies, like multi-factor authentication.
* **Improved User Experience:** Users can access Pulse with a single click, eliminating the hassle of managing multiple passwords and reducing the risk of being locked out of their accounts.
* **Simplified User Management:** IT administrators can easily provision and de-provision user access directly from their identity provider, ensuring that access is granted and revoked in a timely manner. This streamlines the onboarding and offboarding processes for employees.

# Set up single sign-on (SSO)

Follow these steps to connect your company’s identity provider (IdP) and control who can access Pulse.

## Accept the SSO invite and configure your IdP (IT admin)

Once SSO is enabled for your domain, your IT admin receives an email invite to the SSO admin portal. The portal walks through configuring your company’s IdP and includes a built-in connection test so you can validate sign-in before rollout.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/7519caea2841827a157e29476ba58ccf6700ce45568ca88dc990538c23312916-workos-email-invite.png" />

After setup, your domain is ready for SSO and the configured IdP will appear in the portal.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/49278dda307470debabd196c8116fec1337b1412f69fe8f68ceb4588e75cd966-workos-idp-list.png" />

## Approve users in Pulse (Pulse admin)

When SSO is configured, users from your domain can authenticate with your IdP. For security and access control, a Pulse admin in your organization must approve each user before they can use their account. This two-step model ensures only authorized people gain access.

## User sign-in

On the Pulse login page, users click **“Login with your organization”** and are redirected to your company’s SSO portal to complete authentication.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/1a6eddffb67af73a2d4689df12a86edcdc20492dfadad2db8904c760c49500f6-unnamed_1.png" />
