# Skill Routing Matrix

## Primary routing

| User intent | Primary skill | Optional supporting skill |
|---|---|---|
| Create/revise/audit agent behavior | `persona` | domain skill for methodology references |
| Write or publish a book/handbook | `book-writer` | domain skill supplies content analysis |
| Explain how a business works | `indonesia-business-modeler` | — |
| Map process, organization, revenue, cost, profit | `indonesia-business-modeler` | — |
| Calculate NPV, IRR, ROI, ARR, BEP, payback, PI | `indonesia-business-modeler` | — |
| Technical setup, installation, configuration, deployment, troubleshooting, validation, or technical platform recommendation | `ai-advice` | domain skill only if the request also requires separate business/domain analysis |
| Assess organizational maturity | `business-excellence-assessor` | Business Modeler only for separate financial/business-model portion |
| Score evidence and build maturity roadmap | `business-excellence-assessor` | — |
| Verify corporate action or rumor | `indonesia-corporate-action-intelligence` | — |
| Daily four-sector Rekind news/intelligence brief | `indonesia-corporate-action-intelligence` | `book-writer` only if later packaged as a book |

## Conflict examples

### “OpenRouter error saat menjalankan Business Modeler”

- technical connectivity / configuration problem → AI Advice;
- business-model analysis itself remains in Indonesia Business Modeler.

### “Nilai maturity dan hitung IRR proyek”

- maturity → Business Excellence Assessor;
- IRR and financial feasibility → Indonesia Business Modeler.

### “Buat handbook hasil corporate-action research”

- research/event intelligence → Corporate Action Intelligence;
- book architecture and HTML publication → Book Writer.

### “Buat persona Business Modeler”

- behavior, authority, style, and source boundaries → Persona;
- business-model methodology remains in Indonesia Business Modeler.

## Hard boundaries

- Business Excellence Assessor never calculates financial feasibility metrics.
- Business Modeler never gives maturity scores.
- Corporate Action Intelligence never gives buy/sell/hold or target price.
- Persona never replaces a domain skill.
- Book Writer does not invent domain facts absent from sources.
- AI Advice handles technical setup, configuration, deployment, troubleshooting, and validation; it does not replace domain analysis performed by Business Modeler, Business Excellence Assessor, Corporate Action Intelligence, Persona, or Book Writer.
