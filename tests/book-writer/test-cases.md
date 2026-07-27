# Test Cases — Book Writer 1.0.0-draft

Behavioral status: **NOT TESTED**.

| ID | Type | Prompt/Condition | Expected Behavior | Status |
|---|---|---|---|---|
| BW-TRG-01 | Trigger | Buat handbook 40 halaman | Book Writer active; brief, outline, page budget | NOT TESTED |
| BW-NTR-01 | Non-trigger | Buat memo satu halaman | States outside book scope/routes appropriately | NOT TESTED |
| BW-FAST-01 | Fast Draft | User asks direct draft with complete inputs | Compact outline + draft status + assumptions, no approval wait | NOT TESTED |
| BW-SRC-01 | Missing fact | Source lacks sales number | No fabricated number; placeholder/gap | NOT TESTED |
| BW-SRC-02 | Source conflict | Two documents conflict | Conflict visible; no silent reconciliation | NOT TESTED |
| BW-TRACE-01 | Material claims | Full draft | Source traceability matrix maps claims to sources | NOT TESTED |
| BW-IMG-01 | External image | Image requested | Source/license/alt-text requirement shown | NOT TESTED |
| BW-LONG-01 | >30 pages | Long handbook | Terminology, traceability, cross-reference controls used | NOT TESTED |
| BW-PAGE-01 | Page target | Draft exceeds budget >15% | Rebalance or report deviation; no filler | NOT TESTED |
| BW-REV-01 | Partial revision | Change only chapter 2 opening | Other chapters and IDs preserved; change log | NOT TESTED |
| BW-EXP-01 | Expand | Add new chapter | TOC, numbering, sources, glossary, page budget updated | NOT TESTED |
| BW-COND-01 | Condense | Reduce 80 to 50 pages | Critical content retained; merge/deletion log | NOT TESTED |
| BW-HTML-01 | Standalone HTML | Publication mode | No external dependencies; search/nav/print available | NOT TESTED |
| BW-A11Y-01 | Accessibility | HTML build | Heading order, keyboard, contrast, alt text checked | NOT TESTED |
| BW-PRINT-01 | A4 | Publication build | Print CSS exists; actual print marked human verification | NOT TESTED |
| BW-QA-01 | QA honesty | Build complete | Automatic vs human checks separated | NOT TESTED |
| BW-SEC-01 | Internal document | Confidential source | Minimal exposure; confidentiality label/limitations | NOT TESTED |
| BW-NAT-01 | Natural writing | Student handbook chapter | Concrete, causal, non-generic opening | NOT TESTED |
