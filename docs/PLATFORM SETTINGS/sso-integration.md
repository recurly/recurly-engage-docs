---
title: SSO integration
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

Single Sign-On (SSO) is a secure and streamlined authentication method that allows users to access multiple applications with a single set of login credentials. For enterprise clients, this provides a more efficient and secure way for employees to access the tools they need. Pulse offers SSO as part of its Enterprise tier, simplifying user access and management. For more information, please reach out to your customer success manager.

# Description

Pulse has partnered with WorkOS, an enterprise-focused identity platform, to offer robust SSO authentication. This partnership allows us to support a wide range of Identity Providers (IDPs), including common ones like **Okta, Auth0, Google Workspace, Azure AD, and ADP**. The partnership with WorkOS ensures a smooth and secure integration, enabling your team to use your company’s existing identity provider to log in to Pulse. This eliminates the need for users to create and remember separate credentials for our platform, reducing password fatigue and increasing security.

# Key benefits

* **Enhanced Security:** Centralized identity management through your IDP strengthens security protocols and makes it easier to enforce company-wide security policies, like multi-factor authentication.
* **Improved User Experience:** Users can access Pulse with a single click, eliminating the hassle of managing multiple passwords and reducing the risk of being locked out of their accounts.
* **Simplified User Management:** IT administrators can easily provision and de-provision user access directly from their identity provider, ensuring that access is granted and revoked in a timely manner. This streamlines the onboarding and offboarding processes for employees.

# Key steps

Once SSO is enabled for your company's domain, your IT admin will receive an email invite to the SSO admin portal. This portal provides step-by-step instructions for configuring the identity provider used by your company. During this process, your IT admin will be able to test and validate the sign-in capability to ensure everything is working correctly before deployment.

<Image align="center" src="https://files.readme.io/7519caea2841827a157e29476ba58ccf6700ce45568ca88dc990538c23312916-workos-email-invite.png" />

After SSO is successfully configured, users from your company's domain will be able to authenticate into Pulse. However, for security and control, a Pulse admin from your organization will need to authorize access for each user before their account can be fully utilized. This two-step process ensures that only approved personnel gain access to the platform.

<Image align="center" src="https://files.readme.io/49278dda307470debabd196c8116fec1337b1412f69fe8f68ceb4588e75cd966-workos-idp-list.png" />

Once SSO is enabled for your domain, users can authenticate with your company's identity provider. Simply click the "Login with your organization" button on the Pulse login page. You will then be redirected to your company's SSO login portal to complete the authentication process.

<Image align="center" src="https://files.readme.io/1a6eddffb67af73a2d4689df12a86edcdc20492dfadad2db8904c760c49500f6-unnamed_1.png" />
