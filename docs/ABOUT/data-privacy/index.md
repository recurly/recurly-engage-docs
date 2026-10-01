---
title: Data privacy and security
excerpt: >-
  Overview of Recurly Engage’s data privacy and security practices, ensuring
  compliance and user trust.
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
  <div class="rp-overview">Recurly Engage processes only the data you designate, with strict controls around retention and access. The result is a secure, privacy-first engagement platform.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">This page outlines how Recurly Engage handles end-user information, including what it collects, how it stores that information, and how it protects it.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-shield" aria-hidden="true"></i></div>
    <strong>Privacy-by-design</strong>
    <span>Minimal default data collection with configurable tracking to meet your privacy requirements.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-scale-balanced" aria-hidden="true"></i></div>
    <strong>Regulatory compliance</strong>
    <span>Built-in support for Health Insurance Portability and Accountability Act (HIPAA), System and Organization Controls (SOC) 2 Type II, General Data Protection Regulation (GDPR), and California Consumer Privacy Act (CCPA) controls to safeguard user data.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-clock-rotate-left" aria-hidden="true"></i></div>
    <strong>Flexible retention</strong>
    <span>A default 90-day lookback window, with optional extended retention or suppression lists.</span>
  </div>
</div>

# Key details

By default, Recurly Engage does not collect or process end-user information besides session timestamps. IP addresses are never stored. Tracking is limited to the attributes and events you explicitly enable. Data is retained for a default 90-day lookback window, configurable to your needs.

## IP address

Recurly Engage never stores end-user IP addresses. Location targeting uses a one-way hashed integration with a locally hosted copy of MaxMind's GeoIP database. IP data remains internal and is not shared externally.

## Cookies

Recurly Engage does not use cookies in its platform operations unless you explicitly enable first-party cookies for your use case.

## Email address

Recurly Engage does not use email addresses by default. **Email addresses may only be imported at your option** as a custom trait (see <a href="/recurly-engage/docs/user-traits" target="_blank">User traits</a>). Third-party connectors (for example, SendGrid) may require encrypted email for campaign triggers.

## End user privacy

We never share your end-user data with third parties, and we never aggregate external data against your user profiles. We rely on platform-recommended identifiers (for example, Identifier for Vendor (IDFV) on iOS and Instance ID on Android). We never use hardware or network identifiers (MAC, IP) for identification.

## SOC 2 Type II

Recurly Engage is SOC 2 Type II compliant, audited by a trusted American Institute of Certified Public Accountants (AICPA) firm. Controls cover security policies, change management, access controls, backup, disaster recovery, and incident response. Growth and Enterprise customers can request the SOC 2 report through their Customer Success Manager.

## GDPR and CCPA compliance

See the Recurly Engage <a href="https://www.redfast.com/privacy" target="_blank">Privacy Policy</a> for details on GDPR and CCPA adherence, data subject requests, and privacy rights.

## Suppression list

You can provide a list of user IDs to suppress. Recurly Engage immediately stops processing any data associated with those users.

## Data retention

On an ongoing basis, Recurly Engage retains end-user usage data for no longer than 90 days past the latest activity from that end user, unless extended lookback has been enabled. For customers who request the extended lookback feature, data is retained for one year. For end users who have been added to the suppression list, Recurly Engage retains no history of their usage.

## API access

Secure any direct integration with third-party systems that you configure within Recurly Engage with a developer-specific API key assigned to Recurly Engage. Recurly Engage uses publicly or privately supplied documentation for these APIs to establish communications between the systems. An alternative to API access for 1-Click actions is redirecting the user to an existing screen within your app to perform the desired action. However, this will adversely impact your conversion rate.

## Apple App Store

In December 2020, Apple introduced new requirements for app developers to outline their apps' data collection and usage policies. The following list specifies the data Recurly Engage collects by default:

* **Identifiers**: Recurly Engage does not create a user identifier. A User ID created by your system is passed to the Recurly Engage software development kit (SDK). Your system may be using Apple's IDFV identifier and passing that to the SDK. Consult your engineer for specific details.
* **Usage data**: Session-related information, and optionally any additional user events that you choose to track using Recurly Engage.
