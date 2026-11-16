---
name: zynt-news
description: Tell the user what is new about the companies and people on their ZYNT lists. Use when the user asks "any news on my list?", "what changed on my accounts?", "which companies on my list had news this week?", or for news about one of their ZYNT lists.
---

# News on a ZYNT list

1. Call `list_audiences`. If the user named a list, take that one; if they have one list, take it; otherwise ask which.
2. Call `get_list_timeline` with that list and period 7. Nothing there: period 30, then 90.
3. Answer with the newest items first: who it is about, what happened, the date and the link. Say which window answered ("in the last 30 days").

For "who has a reason to hear from me", use `list_signals` instead: signals are the news ZYNT scored for the user's scenarios, and they come after the timeline. Not signed in: see the `zynt-setup` skill.
