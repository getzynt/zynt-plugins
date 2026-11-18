---
name: zynt-news
description: Tell the user what is new about the companies and people on their ZYNT lists. Use when the user asks "signals for me", "what is new for me?", "any news on my list?", "what changed on my accounts?", "which companies on my list had news this week?", or for news about one of their ZYNT lists.
---

# News on ZYNT lists

1. Call `list_audiences`. If the user named a list, take that one. Otherwise take every list, whatever it holds: targets, leads, companies or people.
2. For each list, call `list_signals` with its `audience_id` and sort `highest-score`. Signals are the news ZYNT scored for the user's scenarios: reasons to reach out now.
3. For each list, call `get_list_timeline` with period 7. Nothing there: period 30, then 90.
4. Answer with the signals of all lists together, highest score first, then the other news, newest first. For each: who it is about, what happened, the date, the list it is on and the link (`app_url` for a signal, `url` for other news). Say which window answered ("in the last 30 days").

No lists: call `list_signals` with sort `highest-score`, and offer to make a list. Not signed in: see the `zynt-setup` skill.
