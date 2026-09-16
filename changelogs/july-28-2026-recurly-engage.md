---
title: July 28, 2026 - Recurly Engage
author: Alex Molter
hidden: false
published_at: '2026-07-31T18:23:20.431Z'
---
The July 28 release focused on reliability enhancements: Liquid template parsing is now always on (fixing staging/production drift), a table-sorting bug that could scramble result order is resolved, and a timezone-handling fix ensures paths and experiments start and stop at the correct time near timezone boundaries.

| Release Date | **Feature**                    | **Type**    | **Potential Impact** | **Description / Overview**                                                                                                                                                                                                         |
| :----------- | :----------------------------- | :---------- | :------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Jul 28       | **Engage Prompts**             | Enhancement | Low                  | Liquid template parsing is now always enabled for every app. Previously this required an opt-in flag, and prompts using Liquid that worked in one environment could unexpectedly fail in another if the flag wasn't enabled there. |
| Jul 28       | **Engage Console**             | Bug Fix     | Low                  | Fixed a bug where clearing a sort filter on Prompts, Guides, Segments, or Audits tables could result in incorrect result ordering. Tables now correctly return to unsorted order when a sort is cleared.                           |
| Jul 28       | **Engage Paths & Experiments** | Bug Fix     | Low                  | Fixed a bug where paths and experiments could start or stop at the wrong time near a timezone boundary due to a timezone-handling issue. Scheduling now behaves correctly regardless of timezone.                                  |