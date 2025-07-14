---
title: Testing tips
excerpt: >-
  Testing best practices for validating prompt delivery and user state in
  Recurly Engage.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

The **Testing Tips** page provides recommendations to ensure accurate, reliable testing of prompts using the Test Users segment and to handle reset and propagation considerations.

# Definition

The **Testing Tips** guide outlines steps and considerations for effectively testing prompt configurations, including user whitelisting, reset workflows, and timing allowances.

# Key benefits

* **Reliable validation**: Confirm that prompts render correctly under production-like conditions.
* **Efficient troubleshooting**: Quickly reset and re-test user states to isolate issues.
* **Consistent results**: Mitigate network and caching delays for standardized test outcomes.

# Key details

## Setup test users

You may whitelist specific user IDs to be part of the **Test Users** segment. This allows you to test prompts that are visible only to users in this group. See [Test Users](test-users) for instructions on configuring your Test Users.

## Test cases

When executing test cases, we recommend:

* **Allow SDK initialization**: Wait at least 5 seconds after launching the app before testing. Network latency can delay prompt retrieval.
* **Reset and retest workflow**:
  1. **Reset** the Test User via the web interface.
  2. **Launch** the app, wait a few seconds, then **close** the app—this ensures the SDK fully resets the user state.
  3. **Relaunch** the app, wait a few seconds, then **perform** your test.
* **Propagation delay**: Changes such as pausing or starting prompts may take a few minutes to propagate. Keeping the test app open helps reduce delay and stabilizes test conditions.