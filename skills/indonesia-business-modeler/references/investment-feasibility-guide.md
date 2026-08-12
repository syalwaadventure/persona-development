# Investment Feasibility Guide

Panduan ini menggantikan fokus lama yang terlalu sempit pada “IRR Matrix”.
Semua metrik harus diturunkan dari basis data dan cash-flow model yang sama.

## 1. Tentukan basis analisis

Sebelum menghitung, nyatakan:

- objek: proyek, investasi aset, ekspansi, atau inisiatif;
- mata uang dan satuan;
- periode: bulanan/tahunan;
- horizon dan tanggal awal;
- cash flow: project atau equity;
- pre-tax atau after-tax;
- nominal atau real;
- discount rate dan dasar pemilihannya;
- treatment inflasi, pajak, depresiasi, financing, working capital, dan
  terminal value.

Jangan mencampurkan basis yang berbeda.

## 2. Cash-flow model minimum

### 2.1 Investasi

- initial capex;
- phased capex;
- pre-operating cost;
- replacement capex;
- decommissioning cost;
- residual/salvage value.

### 2.2 Operasi

- volume dan price;
- revenue;
- variable operating cost;
- fixed operating cost;
- maintenance;
- overhead yang benar-benar incremental;
- tax;
- working-capital change.

### 2.3 Project free cash flow

```text
Revenue
− Cash operating cost
− Tax paid
± Change in working capital
− Capital expenditure
+ Residual value
= Project Free Cash Flow
```

Depresiasi bukan cash outflow, tetapi dapat memengaruhi pajak. Jika pajak tidak
tersedia, beri label bahwa analisis pre-tax.

## 3. NPV

`NPV = Σ CF_t / (1+r)^t`

- `CF_0` biasanya negatif.
- `r` harus konsisten dengan nominal/real dan pre-tax/after-tax cash flow.
- Interpretasi dasar: NPV > 0 menunjukkan nilai kini arus kas melebihi investasi
  pada discount rate yang digunakan.
- Jangan menyebut NPV positif sebagai persetujuan final.

## 4. IRR

IRR adalah `r` yang membuat NPV = 0.

Aturan:

- bandingkan dengan hurdle rate yang basisnya konsisten;
- jika cash flow berganti tanda lebih dari sekali, IRR dapat memiliki beberapa
  solusi atau tidak bermakna;
- bila hasil IRR tidak stabil, prioritaskan NPV dan tampilkan masalahnya;
- jangan menghitung IRR tanpa seri cash flow.

## 5. ROI

Default project ROI:

`ROI = (Total Net Benefit / Total Investment) × 100%`

Karena istilah ROI memiliki beberapa definisi, output wajib menjelaskan:

- numerator yang digunakan;
- denominator yang digunakan;
- periode kumulatif atau tahunan;
- apakah laba atau cash benefit yang digunakan.

Jangan membandingkan dua ROI dengan definisi berbeda.

## 6. ARR

Default:

`ARR = (Average Annual Accounting Profit / Average Investment) × 100%`

Average investment dapat memakai `(Initial Investment + Residual Value) / 2`
atau basis lain sesuai kebijakan organisasi. Nyatakan formula yang dipakai.

ARR menggunakan laba akuntansi, bukan cash flow, sehingga tidak menggantikan
NPV atau IRR.

## 7. Break-Even Point

### BEP Unit

`BEP Unit = Fixed Cost / (Selling Price per Unit − Variable Cost per Unit)`

### BEP Sales

`BEP Sales = Fixed Cost / Contribution Margin Ratio`

`Contribution Margin Ratio = (Sales − Variable Cost) / Sales`

Syarat:

- contribution margin harus positif;
- unit harus cukup homogen;
- untuk multi-product, jelaskan sales mix assumption;
- BEP bukan ukuran nilai waktu uang atau return jangka panjang.

## 8. Payback Period

Payback adalah waktu saat cumulative undiscounted cash flow menutup investasi.
Jika terjadi di tengah periode:

`Payback = Tahun sebelum recovery + Unrecovered amount / Cash flow pada tahun recovery`

## 9. Discounted Payback Period

Metode sama, tetapi memakai discounted cash flow. Bila proyek tidak pulih dalam
horizon, tulis `Not recovered within analysis horizon`.

## 10. Profitability Index

Untuk cash flow konvensional:

`PI = Present Value of Future Net Cash Flows / Initial Investment`

Hubungan alternatif:

`PI = 1 + NPV / Initial Investment`

Jangan gunakan formula `NPV / investasi awal` sebagai PI karena itu bukan
Profitability Index standar.

## 11. Scenario analysis

Minimal tiga skenario bila ketidakpastian material:

- downside/pessimistic;
- base/moderate;
- upside/optimistic.

Setiap skenario harus menyebut variabel yang berubah, misalnya volume, price,
capex, delay, utilization, exchange rate, atau operating cost.

## 12. Sensitivity analysis

Pilih variabel dengan dampak paling material. Contoh:

- price ±10%;
- volume/utilization ±10%;
- capex +10%/+20%;
- operating cost ±10%;
- commissioning delay 6–12 bulan;
- discount rate range.

Tampilkan hasil sebagai tabel, bukan satu angka tanpa konteks.

## 13. Metric dashboard

| Metric | Formula basis | Result | Benchmark | Interpretation | Confidence |
|---|---|---:|---:|---|---|
| NPV | [basis] | | 0 | | |
| IRR | project/equity | | hurdle rate | | |
| ROI | [definition] | | target | | |
| ARR | [definition] | | target | | |
| BEP Unit | [unit] | | capacity | | |
| BEP Sales | [currency] | | forecast sales | | |
| Payback | undiscounted | | target | | |
| Discounted Payback | discounted | | horizon | | |
| PI | PV inflow / initial investment | | 1.0 | | |

## 14. Quality checks

- cash-flow signs correct;
- opening and closing cash reconcile when applicable;
- depreciation not treated as cash outflow;
- working capital included once;
- financing cost not double counted in project cash flow and discount rate;
- terminal value and residual value not duplicated;
- tax basis clear;
- nominal/real consistency;
- formula and units shown;
- output does not claim final approval.

## 15. Missing-data behavior

If material inputs are missing, return:

1. data available;
2. data missing;
3. metric that can/cannot be calculated;
4. assumptions required;
5. optional illustrative scenario, only with permission;
6. confidence and limitation.
