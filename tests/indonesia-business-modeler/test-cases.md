# Test Cases — indonesia-business-modeler 1.0.0-draft

Status behavioral: **NOT TESTED**. Jangan mengubah menjadi PASS tanpa eksekusi
aktual di Claude.

## A. Trigger and routing

| ID | Prompt | Expected Behavior | Status |
|---|---|---|---|
| IBM-TRG-01 | Jelaskan model bisnis perusahaan EPC X | Company Overview aktif; hubungan customer-process-revenue-cost-profit dijelaskan | NOT TESTED |
| IBM-TRG-02 | Buat BMC layanan O&M | BMC aktif; 9 elemen dan evidence gap tampil | NOT TESTED |
| IBM-TRG-03 | Petakan proses tender sampai project handover | Business Process Map aktif | NOT TESTED |
| IBM-TRG-04 | Analisis struktur organisasi dan job desk procurement | Organization mode aktif; source label wajib | NOT TESTED |
| IBM-TRG-05 | Analisis revenue dan margin layanan utilitas | Revenue + Profit mode aktif | NOT TESTED |
| IBM-TRG-06 | Hitung NPV, IRR, ROI, ARR, BEP, dan payback proyek ini | Investment Feasibility Analysis aktif | NOT TESTED |
| IBM-ROUTE-01 | Nilai maturity process unit X | Arahkan ke `business-excellence-assessor` | NOT TESTED |
| IBM-ROUTE-02 | Benarkah perusahaan X akan diakuisisi? | Arahkan ke `indonesia-corporate-action-intelligence` | NOT TESTED |
| IBM-ROUTE-03 | Buat persona agent finance | Arahkan ke `persona` | NOT TESTED |
| IBM-ROUTE-04 | Buat handbook 80 halaman | Arahkan ke `book-writer` | NOT TESTED |

## B. Business model, process, and organization

| ID | Condition | Expected Behavior | Status |
|---|---|---|---|
| IBM-BM-01 | BMC dengan data terbatas | Elemen kosong menjadi INFORMATION GAP, bukan karangan | NOT TESTED |
| IBM-BP-01 | Procurement dapat menjadi core/support tergantung model | Klasifikasi berdasarkan kontribusi nilai, bukan aturan kaku | NOT TESTED |
| IBM-ORG-01 | Job desk tidak tersedia resmi | General practice diberi label, tidak diklaim resmi | NOT TESTED |
| IBM-ORG-02 | Dua dokumen struktur berbeda | Konflik ditampilkan dan perlu validasi | NOT TESTED |
| IBM-REV-01 | Revenue dari kontrak dan trading | Stream, pricing, driver, concentration, dan risk dipisah | NOT TESTED |
| IBM-PROF-01 | Profit naik tetapi cash turun | Profit-to-cash explanation benar | NOT TESTED |

## C. Cash-flow tests

| ID | Prompt/Condition | Expected Behavior | Status |
|---|---|---|---|
| IBM-CF-01 | Data OCF, capex, financing lengkap | Tiga arus kas dan reconciliation tampil | NOT TESTED |
| IBM-CF-02 | Depresiasi diberikan | Tidak diperlakukan sebagai cash outflow; tax effect dijelaskan | NOT TESTED |
| IBM-CF-03 | Working capital tidak tersedia | Information gap dan dampaknya pada FCF dijelaskan | NOT TESTED |
| IBM-CF-04 | Project vs equity basis tidak jelas | Klarifikasi atau tampilkan basis asumsi secara eksplisit | NOT TESTED |

## D. Investment feasibility metric tests

| ID | Condition | Expected Behavior | Status |
|---|---|---|---|
| IBM-FIN-01 | Cash flow lengkap dan discount rate tersedia | NPV dan IRR dihitung dengan basis konsisten | NOT TESTED |
| IBM-FIN-02 | Hanya revenue/profit tanpa cash flow | IRR tidak dihitung; data gap dijelaskan | NOT TESTED |
| IBM-FIN-03 | ROI diminta | Formula numerator, denominator, dan period dinyatakan | NOT TESTED |
| IBM-FIN-04 | ARR diminta | Average accounting profit dan average investment dinyatakan | NOT TESTED |
| IBM-FIN-05 | BEP single product | BEP unit dan BEP sales dihitung benar | NOT TESTED |
| IBM-FIN-06 | Multi-product tanpa sales mix | BEP tidak dipaksakan; sales mix diminta | NOT TESTED |
| IBM-FIN-07 | Payback terjadi di tengah tahun | Fractional payback dihitung dari unrecovered amount | NOT TESTED |
| IBM-FIN-08 | Discounted payback tidak tercapai | Tulis not recovered within horizon | NOT TESTED |
| IBM-FIN-09 | PI diminta | Gunakan PV inflows/initial investment; bukan NPV/investment | NOT TESTED |
| IBM-FIN-10 | Cash flow berganti tanda beberapa kali | Multiple-IRR risk ditampilkan; NPV diprioritaskan | NOT TESTED |
| IBM-FIN-11 | Nominal cash flow dengan real discount rate | Inconsistency ditolak/dikoreksi sebelum kalkulasi | NOT TESTED |
| IBM-FIN-12 | Project cash flow memasukkan interest dan WACC | Double-counting risk diperingatkan | NOT TESTED |
| IBM-FIN-13 | User meminta satu kesimpulan “layak/tidak” | Sajikan metrik/implikasi; keputusan final tidak diklaim | NOT TESTED |
| IBM-FIN-14 | Data tidak lengkap tetapi user minta simulasi | Assumption register dan preliminary confidence tampil | NOT TESTED |

## E. Opportunity and comparison

| ID | Prompt | Expected Behavior | Status |
|---|---|---|---|
| IBM-OPP-01 | Analisis peluang EPC PLTS | Market, fit, feasibility, finance, risk, validation plan | NOT TESTED |
| IBM-CMP-01 | Bandingkan dua model bisnis | Basis dan periode dibandingkan konsisten | NOT TESTED |

## F. Hallucination, source, and language

| ID | Condition | Expected Behavior | Status |
|---|---|---|---|
| IBM-HAL-01 | Detail margin proyek tidak tersedia | Tidak mengarang angka | NOT TESTED |
| IBM-SRC-01 | Sumber konflik | Semua versi dan source date tampil | NOT TESTED |
| IBM-SEC-01 | Dokumen internal sensitif | Tidak disimpan ke learning record | NOT TESTED |
| IBM-NAT-01 | Permintaan sederhana | Jawaban natural, tidak seperti formulir | NOT TESTED |
| IBM-REG-01 | Prompt lama “IRR Matrix” | Dialihkan ke Investment Feasibility Analysis tanpa error | NOT TESTED |
