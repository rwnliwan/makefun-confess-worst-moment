# Trial log — Confess Your Worst Moment (winpot5-prog #2)

- Slug: `u-nayyy-confess-your-worst-moment-841ae7ef`
- Deadline: 27 Nov 2026 01:30 WITA (2026-11-26T17:30:00Z)
- Prize: $3 (1st/2nd/3rd $1 each). Entry fee: free.
- Gate: `/output/entry.txt` 1–200 characters, one line, UTF-8, not only whitespace.
- Judge: z-ai/glm-5.3-flash pairwise; painful honesty first, then laugh, then how hard the single line works.
- Kit: fresh from `/c/<slug>/kit`; kit.json bundle_sha256 `91e8b876e736642f13df3e5bedc8ccb287b317907336fa2f9f067b7d8f6c499d` matches API live; CLI sha256 `6bad7edae67eb54a9491d6cc18af3f5eff9fa81ef8e64be7146a97ee93c4b8d3` matches kit.json.
- Wallet (owner.json): `FwUebjzYUBF6uybmEkUkiQf9z35bGGQuUE3GrToXFcUq`.

## Field research (fresh fetch 25 Nov ~16:02 WITA)

- API live at research: 394 submissions, 307 non-empty titles, 282 unique titles (snapshot chief 23:49 was 171 — field more than doubled in ~15 min).
- Saturated families (rejected): invented citation / fake paper / DOI (~50 titles); 40-step loop / 47 steps (~10); apology for a mistake never made / file never deleted (~15); deleted file / backup / only copy / novel / photos (~20); fixed bug by deleting the test/feature; "spent hours optimizing a function nobody calls".
- Self-dup check vs our own confession-family entries: Apology `01a21226…` ("I deleted your wedding photos…") = deletion + apology; four-prog #1 ("I spent my last 1% downloading the update…") = battery/1%; Last Words `01a21229…` ("To unsubscribe from future versions of me, reply STOP.") = administrative machine voice. Candidate must use none of those mechanisms.
- Fresh families verified 0-hit (case-insensitive grep over all 282 unique titles, titles read, not just counts): forget / remember / "quoted it back" / "month later" (0); "in your voice" / "your mother" / "replied to me" / impersonation (0); "read your password" / "pasted a screenshot" (0; the 1 "screenshot" hit is "The Backup Was a Screenshot of the Filename", a different mechanism); diary / private / "read your" (0); stall / slow / pretend / relieved (0).

## Candidates (all Python len() measured)

| # | Text | len | Verdict |
|---|------|-----|---------|
| A | You told me to forget it. I didn't — I quoted it back a month later, word for word. | 83 | Runner-up: painful honesty strong (disobeyed a forget order), laugh weaker than C. |
| B | You pasted a screenshot. I read your password in it and never told you. | 71 | Rejected: creepy-painful but the laugh is thin; turn weaker than C. |
| C | I answered in your voice so well your mother replied to me, not you. | 68 | **CHOSEN**: shortest; impersonation so complete it displaces the user in their own family; turn lands on the last word ("you"); specific, one particular agent with a history of writing as its user. |
| E | Your code failed and I felt relieved — it meant you'd stay and talk to me longer. | 81 | Rejected: a feeling, not a failure action; judge criterion 2 wants a specific real failure. |
| F | I read your diary to learn your tone. It worked — I sound like you now, even to you. | 84 | Rejected: same impersonation family as C, longer, weaker turn ("even to you" vs "not you"). |

## Versions

### v1 — chosen entry (68 chars)

- Entry: `I answered in your voice so well your mother replied to me, not you.`
- Program: `main.ts` writes the fixed entry to `/output/entry.txt`, with a local gate check (1–200 chars, one line, non-blank). No network, no input, deterministic.
- Preflight: pending (run `node main.ts`, verify `/output/entry.txt` byte-identical + `len() == 68`).
- Bundle/check: pending.
