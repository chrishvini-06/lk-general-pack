# Sri Lanka general statutory pack (draft 0.1.2)

Jurisdiction LK, currency LKR, scope general. Status: **draft for review.** Author: Chrishvini Rogers (ACCA student). Not yet reviewed by a qualified accountant.

## What it covers
VAT, the Social Security Contribution Levy (SSCL) and withholding tax on service fees. Rates, thresholds and dates are in `rules.yaml`, each with its source. Twenty-one worked examples are in `examples/`. Guidance for business owners' assistants is in `guidance/GUIDANCE.md`. Rules the schema cannot express are in `capability-requests.md`.

## What it does not cover
Income tax, payroll taxes, customs, e-invoicing, VAT on financial services, withholding on rent, interest and dividends, SSCL on imports, registered distributors, and partial input-tax recovery.

## Open items for the author before release 
1. **Read the original documents** for every source marked "read via secondary summary" below. Nothing in this draft replaces that step.
2. **Map the return boxes** to the real IRD return layouts. The box numbers here are plain groupings for the pack, not IRD form field numbers.
3. **Decide on due dates** (see CR-2). VAT carries the payment date, not the return date.
   

## Source status

| Rule | Source | How it was read |
|---|---|---|
| VAT rates, thresholds, due dates | IRD VAT page (updated 19 Nov 2025) | Read directly |
| SSCL rate, percentages, due dates | IRD SSCL page (updated 27 Jan 2026) | Read directly |
| SSCL threshold cut to LKR 36M a year (LKR 9M a quarter) from 1 Jul 2026 | SSCL (Amendment) Act No. 10 of 2026; IRD Notice PN/SSCL/2026-04/1 | Secondary summary (Lanka Tax Club). The IRD page above still shows the older threshold |
| SSCL exemption for financial services at 20.5% VAT | SSCL (Amendment) Act No. 24 of 2025; IRD notice SEC/PN/SSCL/2026-01 | Secondary summary |
| VAT Amendment Act No. 14 of 2026 (threshold unchanged, 20.5% on financial services from 1 Jul 2026) | IRD notice SEC/PN/VAT/2026-03 | Secondary summaries (KPMG and others); the Act is listed on the IRD VAT page |
| Withholding rates (5% and 14%), scope, due date | Inland Revenue (Amendment) Act No. 11 of 2026; IRD Circular SEC/2026/E/04 | Secondary summaries (Lanka Tax Club, Bloomberg Tax). The exact 2026 scope for the 5% rate was not read |

## Layout choices inferred, not confirmed
- The toolkit's sample pack (Examplia) and writing-guidance file could not be opened in this session. The layout of the expected values for receipts and payments (`expected.taxes`) and the account keys used in postings follow `format.md` and `worked-examples.md` but were not compared with a sample.
- `day_of_following_month` is used for due dates.
- The SSCL codes use `treatment: standard` with the levy's liable percentage as a `fraction`.

## Examples
Each of the ten tax codes has at least three examples. Rounding edge cases, VAT-inclusive entries and the change from 15% to 18% (31 Dec 2023 and 1 Jan 2024) are covered. The pack has no compound taxes, so there is no compound example. All figures were worked out by hand and match the separate recomputation.
