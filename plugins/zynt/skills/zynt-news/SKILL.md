---
name: zynt-news
description: Tell the user what is new about the companies and people on their ZYNT lists. Use when the user asks "signals for me", "what is new for me?", "any news on my list?", "what changed on my accounts?", "which companies on my list had news this week?", or for news about one of their ZYNT lists.
---

# News on ZYNT lists

1. Call `list_audiences`. If the user named a list, take that one. Otherwise take every list, whatever it holds: targets, leads, companies or people.
2. For each list, call `list_signals` with its `audience_id` and sort `highest-score`. A signal is news that gives the user a reason to talk to a company now. When there are none, the result's `note` says why and what news the lists already have.
3. For each list, call `get_list_timeline` with period 7. Nothing there: period 30, then 90.
4. Answer with the signals of all lists together, highest score first, then the other news, newest first. For a signal: what happened, when, why it matters to the user and who to contact, with its list and `app_url`. For other news: who it is about, what happened, the date it was found, its list and `url`. Say which window answered ("in the last 30 days").
5. No signals yet: say so in one sentence ("ZYNT is still checking which news is a reason to talk to these companies now"), then show the news, as news. Never call news a signal, and do not add that a source was not checked or proves no intent: say what it reports.

No lists: call `list_signals` with sort `highest-score`, and offer to make a list. Not signed in: see the `zynt-setup` skill.
