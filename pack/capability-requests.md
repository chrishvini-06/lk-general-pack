# Capability requests: Sri Lanka general pack

Each entry is a rule this pack could not express with capabilities C1 to C16 (schema 0.1). None has been approximated in `rules.yaml`.

## CR-1: VAT on financial services, charged on the value addition
- **Rule:** Financial services are taxed on the value addition attributable to financial services, calculated by the attributable method, not on the invoice line. The rate is 20.5% from 1 Jul 2026 (read via secondary summaries; the author should confirm the rate and any earlier rates against the Act and IRD notice). Financial services taxed at 20.5% are outside SSCL.
- **Legal source:** VAT Act No. 14 of 2002, Chapter IIIA (section 25B onwards) and the Gazette under section 25C; VAT (Amendment) Act No. 14 of 2026; SSCL (Amendment) Act No. 24 of 2025; IRD Notice SEC/PN/VAT/2026-03 dated 3 Jul 2026.
- **Who it affects:** Banks, finance companies, insurers and other specified institutions.
- **Worked example:** To be supplied by the author from the attributable-method schedule.
- **Workaround meanwhile:** None. Financial institutions should not use this pack for VAT.

## CR-2: Filing and payment dates
- **Rule:** VAT is paid by the 20th of the month after the month concerned, and the return is due on the last day of the month after the taxable period (monthly or quarterly, depending on the taxpayer). SSCL is paid monthly by the 20th of the following month (with the third month of the quarter paid by the 20th after quarter end) and the quarterly return is due on the 20th of the month after quarter end. Schema 0.1 holds one due date per tax, cannot express "last day of the following month", and cannot offer a monthly or quarterly choice per business.
- **Legal source:** Inland Revenue Department VAT page ("VAT Payments", "Furnishing VAT Returns", page last updated 19 Nov 2025); Inland Revenue Department SSCL page ("Payment of SSCL on Self-Assessment Basis", page last updated 27 Jan 2026).
- **Who it affects:** Every VAT and SSCL registrant.
- **Worked example:** A business with a monthly VAT period ending 31 March 2027 pays by 20 April 2027 and files by 30 April 2027.
- **Workaround meanwhile:** `rules.yaml` states the payment date (20th) as the due date for VAT. Clients must rely on the IRD for the return date.

## CR-3: Minimum monthly amount per payee for withholding on service fees
- **Rule:** The 5% deduction on service fees to a resident individual applies only where the fees paid to that person exceed a monthly aggregate threshold (LKR 100,000 per month in the circular read), and only for the categories of independent service provider the law lists (the list was widened from 3 Jun 2026).
- **Legal source:** Inland Revenue Act No. 24 of 2017 as amended by Inland Revenue (Amendment) Act No. 11 of 2026; IRD Circular SEC/2026/E/04 dated 8 Jun 2026.
- **Who it affects:** Any business paying freelancers and professionals.
- **Worked example:** Fees paid to one individual in a month: 80,000 (no deduction) and 120,000 (deduction on the full 120,000).
- **Workaround meanwhile:** The platform computes the tax only when the user chooses the code. The guidance asks the assistant to test the monthly total and category before the code is chosen. The threshold figure is not in the pack data.

## CR-4: Withholding on the amount before VAT where the settlement includes VAT
- **Rule:** Withholding is worked out on the payment before VAT. Schema 0.1 computes it on the full amount settled.
- **Legal source:** IRD Circular SEC/2026/E/04 dated 8 Jun 2026 (as summarised by Lanka Tax Club; original to be checked).
- **Who it affects:** Payments for services where the supplier's invoice includes VAT. This is uncommon for resident individuals under the VAT threshold but common for non-resident providers once they charge VAT.
- **Worked example:** Invoice 118,000 including 18,000 VAT paid to a resident individual: deduction should be on 100,000.
- **Workaround meanwhile:** None in the data. The guidance tells the assistant to flag the case to the owner.

## CR-5: SSCL bad debts and recoveries
- **Rule:** Bad debts incurred in a quarter are removed from that quarter's SSCL turnover, and bad debts recovered are added back.
- **Legal source:** Social Security Contribution Levy Act No. 25 of 2022, as amended; Inland Revenue Department SSCL page ("Turnover").
- **Who it affects:** Any SSCL registrant with unpaid invoices.
- **Worked example:** To be supplied by the author.
- **Workaround meanwhile:** None. SSCL on a bad debt is not reversed by the pack.

## CR-6: Two-measure registration thresholds
- **Rule:** VAT registration is required when turnover exceeds LKR 15 million in a quarter or LKR 60 million in twelve months. SSCL is similar (LKR 9 million per quarter or LKR 36 million over four quarters from 1 Jul 2026), and the test also applies when turnover is "likely to exceed" the limit. Schema 0.1 holds one threshold per tax.
- **Legal source:** Inland Revenue Department VAT page (Registration Threshold); IRD Notice PN/SSCL/2026-04/1.
- **Who it affects:** Information shown to businesses approaching registration.
- **Workaround meanwhile:** `rules.yaml` carries the annual figure for both VAT (LKR 60 million) and SSCL (LKR 36 million). The quarterly measures (LKR 15 million for VAT, LKR 9 million for SSCL) are not recorded.

## CR-7: SSCL on imports and for registered distributors
- **Rule:** SSCL on imported articles is charged at the point of import, and a registered distributor's sales are liable on a smaller share of turnover than other wholesale or retail sales.
- **Legal source:** Inland Revenue Department SSCL page (Rate, items 1 and 4(a)).
- **Who it affects:** Importers and registered distributors.
- **Workaround meanwhile:** Not covered in this release. These businesses should not rely on the SSCL part of this pack. (Registered distributors could be added with another question and code once the author confirms the rule; imports need a customs-based document type.)
