# BusinessTaxTool
Most tax software prepares tax returns. Most retirement calculators draw one confident line. Local Quantum is different: it starts with the **decisions** that create those results and works backward, explaining the rules as it goes and citing the primary legal sources (IRC/DOR guidance) so you can verify the reasoning yourself.
# Local Quantum

**A simple tool for understanding how business, tax, and retirement decisions affect one another — that runs entirely on your own computer.**

Enhance your decision-making. Protect your future. Nothing leaves this file — no accounts, no logins, no cloud, no analytics, no dataverse.

---

## What this is

Most tax software prepares tax returns. Most retirement calculators draw one confident line. Local Quantum is different: it starts with the **decisions** that create those results and works backward, explaining the rules as it goes and citing the primary legal sources (IRC sections, IRS publications and form instructions, state DOR guidance) so you can verify the reasoning yourself.

It is one self-contained HTML file. Open it in any modern browser, on any device, with or without an internet connection. Your answers save to a small JSON file you keep. The HTML file and your JSON file together are the entire system.

**This is education, not advice.** It is not legal, tax, accounting, investment, or financial advice. Its job is to make you dangerous in the meeting with your CPA and attorney — not to replace them.

## Modules

Local Quantum is a growing suite. Both current modules live in the same file, behind a switcher, sharing one saved-answers file.

### Module 1 · Decisions (business & tax)

An interview that starts at the end point — how the business ends, where you retire — and works backward through your household, entities, and last year's return. It produces a layered reasoning report:

- **Money** — what each federal classification costs on your numbers (sole prop / partnership / S-corp / C-corp), with the owner-salary slider, QBI/SSTB phase-out math, max 401(k) room per option, a small-profit guard, and a sensitivity row showing whether the answer changes at $25k–$500k of profit
- **Thresholds** — the bright lines you're standing near (2% S-corp fringe lockout, 5% HCE, 25% cafeteria concentration, 50% common control, real-estate-professional hour tests per spouse), with family attribution traced through tiered entities
- **Geographic planning** — state-by-state comparison for living, working, and retiring: income tax on business profit and household wages, reciprocity, PTET availability, retirement-income treatment, plus the context the tax math ignores (property tax, sales tax, vehicle registration, cost of living). Deep pair logic (credit mechanics, statutory-residency traps) currently implemented for WI/MN
- **Strategy** — your flags, biggest dollar levers first, each tagged with a confidence level (**settled law · depends on your facts · professional judgment**) and, where relevant, an audit-posture note
- **Last Year's Math** — paste text from your federal 1040 PDF (or enter ~11 numbers by hand) and get a diagnosis of where money leaked: missed other-state credits, S-election savings, QBI reasons (including loss carryforwards), your real marginal rate
- **Appendices** — everything you entered, and every education note, collected for the printout so the report is self-contained for a CPA meeting

### Module 2 · Investing & Retirement

Reads everything Module 1 knows — marginal fed+state rate, state plans, entity structure, student-loan situation — and layers wealth planning on top:

- **People & Benefits** — birth years drive every age-triggered rule (catch-ups at 50 and 60–63, RMD age, Social Security window, Medicare). Includes a step-by-step for pulling your real Social Security Statement from ssa.gov; pensions entered from statements or as labeled guesses
- **Accounts** — enter category totals (enough for projections) or individual accounts (unlocks fee-bleed and asset-location analysis). Your choice of granularity
- **Debts** — so "invest vs. pay down" gets a real answer against your actual rates, with deductible-interest and income-driven-repayment adjustments
- **College** — optional, checkbox-revealed, per-child targets with the 529-to-Roth rollover rules
- **Combined Report** — three-band projections plus a Monte Carlo probability the money lasts to 95 (never a single confident line); guaranteed-income stack vs. spending gap; first-RMD estimate; the Roth conversion window sequenced around any planned move to a no-tax state (4 U.S.C. §114); IRMAA cliff warnings; and the **next-dollar engine** — where each additional saved dollar should go, in order, reasoned from your specific facts rather than advice-column defaults

## Getting started

1. Download `local-quantum.html` (one file).
2. Double-click it. It opens in your browser. No install, no internet needed.
3. Answer the interview. Use **Save Answers** to write your progress to a JSON file in your Downloads folder.
4. To continue anywhere: open the HTML file, click **Load Answers**, pick your JSON.
5. **Print / PDF** produces the full report with all sections open — inputs, reasoning, citations, education notes.

## The Local Quantum exchange format

Every save writes a tagged envelope:

```json
{
  "localQuantum": {
    "product": "Local Quantum",
    "tool": "decisions",
    "version": "0.8",
    "savedAt": "2026-08-15T00:00:00Z"
  },
  "data": { }
}
```

Any Local Quantum tool can read any other tool's file. Drop a file from another tool into any screen and it attaches to your workspace without touching your answers — current and future engines use attachments where they connect. This is how the suite grows without a fixed order of operations.

## Design principles

- **Local-first, always.** No account. No telemetry. No network calls. What you type never leaves the file.
- **Primary sources only.** Claims cite the IRC, regulations, IRS publications, and state DOR guidance — never blog posts, forums, or "10 tax hacks" content. If you can't verify it, the tool shouldn't say it.
- **Honest uncertainty.** Every flag carries a confidence tag. Projections show bands and probabilities. Judgment areas (reasonable compensation, real-estate-professional status) are labeled as documentation projects, not conclusions.
- **Data has a vintage.** Rates, brackets, limits, and thresholds are packaged as labeled data packs (currently tax year 2025). Stale tax data is worse than none, so the vintage is printed on every screen and report.
- **The household is the unit of analysis.** Flow-through entities don't pay tax; people do. Every chain of reasoning terminates in the household's federal and state returns.

## Known limitations

- The calculation data pack is **2025-vintage**; other years adjust line references but dollar outputs are estimates.
- Deep state-pair logic (resident credits, residency traps) is built for **WI/MN**; all other states use top-rate screening — a first-pass filter, not a final answer.
- The classification comparison is decision-support math, not a full return simulation (no AMT, limited credits, additional Medicare partially modeled).
- The 1040 paste-parser handles standard text-layout PDFs; professional tax software that prints values in detached blocks is detected and routed to manual entry rather than guessed at.
- Fund-level portfolio analytics (overlap, sector exposure, performance history) are intentionally excluded — they require market databases that cannot stay current inside an offline file.

## Roadmap

- Annual data-pack refreshes (federal + state + retirement rules)
- Additional state deep-pair logic beyond WI/MN
- Defined-benefit / cash-balance plan modeling (needs actuarial inputs)
- College module expansion (state 529 deductions, aid interactions)
- Further Local Quantum tools, each reading and writing the exchange format

## Disclaimer

Local Quantum provides educational analysis based on tax law and primary sources as of its data-pack vintage. It is not legal, tax, accounting, investment, or financial advice, and no professional-client relationship is created by using it. Tax laws change; some decisions require professional judgment. Verify important decisions with qualified advisors before acting.

## License

Copyright © Local Quantum. All rights reserved. *(Choose a license before publishing — MIT if you want it open, or keep it proprietary while the product develops.)*

