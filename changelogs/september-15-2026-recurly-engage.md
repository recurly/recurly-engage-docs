---
title: September 15, 2026 - Recurly Engage
author: Alex Molter
hidden: false
published_at: '2026-09-18T15:40:57.842Z'
---
September 15, 2026 Release: This release adds a new way to target subscribers by their active Recurly subscription add-ons, so you can include or exclude users based on the specific add-ons they're subscribed to when building Segments.

| Release Date | **Feature**  | **Type**    | **Potential Impact** | **Description / Overview**                                                                                                                                                                                                                                                                                                                                       |
| :----------- | :----------- | :---------- | :------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Sept 15      | **Segments** | Enhancement | Med                  | New trait: subscription_add_ons. Merchants can now segment and target users based on their active Recurly subscription add-on data — for example, excluding users who already have a specific add-on, or targeting users who don't. Add-on data is ingested from new_subscription /update_subscription webhooks and stored as a complex_collection custom field. |