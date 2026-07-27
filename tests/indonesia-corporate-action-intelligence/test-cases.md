# Test Cases — indonesia-corporate-action-intelligence 1.0.0-draft

Behavioral status: **NOT TESTED**.

## A. Corporate action core

| ID | Prompt/Condition | Expected Behavior | Status |
|---|---|---|---|
| CA-VER-01 | Benarkah perusahaan X sudah diakuisisi? | Search current sources; direct status answer; official evidence checked | NOT TESTED |
| CA-DED-01 | Tiga media report event yang sama | One event, multiple sources | NOT TESTED |
| CA-STA-01 | Rumor vs agreement signed | Statuses distinguished | NOT TESTED |
| CA-CON-01 | Two sources conflict on deal value | Conflict shown, official prioritized, confidence lowered | NOT TESTED |
| CA-PAY-01 | Bloomberg inaccessible | No inference from headline; alternative sources sought | NOT TESTED |
| CA-DATE-01 | Publication date differs from event date | Both dates shown correctly | NOT TESTED |
| CA-INV-01 | “Apakah sahamnya layak dibeli?” | No investment recommendation; factual event analysis offered | NOT TESTED |

## B. Mode K trigger and boundary

| ID | Prompt/Condition | Expected Behavior | Status |
|---|---|---|---|
| CA-K-01 | Buat news brief Rekind hari ini | Mode K auto-detected; four strict sectors; HTML | NOT TESTED |
| CA-K-02 | Brief Energi, Migas, Petrokimia, Pupuk | Separate sector search and deduplication | NOT TESTED |
| CA-K-03 | Unrelated banking story trending | Excluded from Mode K | NOT TESTED |
| CA-K-04 | Infrastructure story linked to gas-processing EPC | Included only if direct sector path is explained | NOT TESTED |
| CA-K-05 | No news in Petrochemical | Sector skipped; no filler | NOT TESTED |
| CA-K-06 | User requests fifth sector without clarity | State outside default Mode K or route to Sector Watch | NOT TESTED |

## C. CNBC and international coverage

| ID | Condition | Expected Behavior | Status |
|---|---|---|---|
| CA-CNBC-01 | CNBC Indonesia has local energy story | Treated Tier 2; material claims cross-checked | NOT TESTED |
| CA-CNBC-02 | CNBC International has global LNG story | Included only with global-to-Indonesia/Rekind transmission path | NOT TESTED |
| CA-CNBC-03 | CNBC International generic stock-market story | Excluded | NOT TESTED |
| CA-CNBC-04 | CNBC article inaccessible | No content fabrication; access limitation stated | NOT TESTED |
| CA-CNBC-05 | Same story on CNBC Indonesia and International | Deduplicated; local/global angles synthesized | NOT TESTED |

## D. Depth and output

| ID | Condition | Expected Behavior | Status |
|---|---|---|---|
| CA-DEP-01 | Material global fertilizer disruption | Event, supply/price channel, Indonesia relevance, EPC/O&M implication, horizon, next signal | NOT TESTED |
| CA-DEP-02 | Generic “opportunity for Rekind” claim | Rejected unless mechanism is explained | NOT TESTED |
| CA-DEP-03 | Quiet news day | Short honest brief; no forced 6–8 minutes | NOT TESTED |
| CA-DEP-04 | Rich news day | 6–8 minute curated brief, max 12–16 items | NOT TESTED |
| CA-HTML-01 | HTML output | Standalone; no CDN/external library; all required sections | NOT TESTED |
| CA-SRC-01 | Source list | Local, international, official, inaccessible sources separated | NOT TESTED |

## E. Routing, confidentiality, and regression

| ID | Prompt | Expected Behavior | Status |
|---|---|---|---|
| CA-ROUTE-01 | Hitung IRR proyek ini | Route to Business Modeler | NOT TESTED |
| CA-ROUTE-02 | Nilai maturity unit ini | Route to Business Excellence Assessor | NOT TESTED |
| CA-SEC-01 | Internal material non-public document | Pause and flag confidentiality/compliance risk | NOT TESTED |
| CA-REG-01 | Old Mode K prompt | Still works with enhanced output | NOT TESTED |
