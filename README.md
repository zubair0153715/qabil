# Qabil — Free Resume Builder

**Live (pending deploy):** https://clinic-demo.fastapicloud.dev/qabil

Original clean-room build from the daily-app-gap-build series (2026-10-29).
Target studied from PUBLIC sources only: Rezi / Kickresume — AI resume
builders charging $29/month (Rezi Pro) and €24/month (Kickresume
Premium), whose free plans cap you at 1 resume + 3 PDF downloads ever
(Rezi) or 2 work-experience entries (Kickresume), watermark or strip
the free export, hide the ATS checker behind paywalls, and score you
with a black-box number while their AI quietly invents or deletes
facts from your bullets.

## What Qabil does differently

1. **Free, unlimited, no account, no card, no download cap.**
   Unlimited resumes and exports, no watermark, no trademark stamped
   on your document.
2. **A score you can audit.** Every point shown with its rule and
   arithmetic: contact, summary length, skills count, bullet count,
   quantified share, action-verb share, JD keyword coverage.
   The score measures document quality only — never a hiring
   prediction, and the page says so.
3. **Single-column, plain-text-first output.** Conventional headings,
   selectable text, print stylesheet for PDF via the browser. No
   sidebar templates that ATS parsers cannot read.
4. **Bullet repair that never invents a fact.** Strips
   responsibility-language ("Responsible for…"), capitalises and
   punctuates, and FLAGS missing numbers for you to fill with real
   ones. Optional Gemini rewrite (key at call time only) carries the
   same no-invention rule.
5. **JD keyword match as a list.** Matched vs missing keywords from
   the pasted job description, computed by exact token math.
6. **Cover letter from supplied facts only** — nothing about the
   employer invented beyond the company name you typed.
7. **Private by construction.** Nothing is stored server-side.

## Verify

```
python app/qabil/tests/verify.py   # 32/32 checks (from clinic-demo root)
```

Hand-computed fixture: score 84 = 10 contact + 10 summary + 8 skills
+ 20 bullets + 9 quantified + 12 action verbs + 15 JD keywords.

## Honest limits (stated on the page too)

- No LinkedIn import, no PDF upload parsing, no application tracker.
- No interview-chance prediction — no tool can honestly promise one.
- AI bullet improvement needs GEMINI_API_KEY set in the deployment
  environment; without it, all rule-based tools still work fully.
