# Claude Skill Rekind — Package 0.7.0-draft

Package ini berisi **enam skill** yang saling melengkapi, memiliki fungsi yang berbeda, dan menggunakan routing berbasis primary intent agar tidak saling mengambil tugas di luar domainnya.

| Skill | Fungsi utama | Bukan untuk |
|---|---|---|
| `persona` | Merancang, merevisi, mengaudit, dan menguji persona agent | Menjalankan analisis domain atau technical setup |
| `book-writer` | Menyusun dan memublikasikan buku/handbook HTML | Laporan pendek, troubleshooting teknis, atau analisis domain |
| `indonesia-business-modeler` | Model bisnis, proses, organisasi, revenue, cost, profit, cash flow, peluang bisnis, dan investment feasibility | Maturity scoring, corporate-action verification, atau technical setup |
| `indonesia-corporate-action-intelligence` | Corporate-action verification dan four-sector Rekind intelligence brief | Business model/financial feasibility, technical setup, atau investment advice |
| `business-excellence-assessor` | Evidence-based maturity assessment dan improvement roadmap | NPV/IRR/ROI/ARR/BEP/payback, business-model analysis, atau technical troubleshooting |
| `ai-advice` | Technical setup, installation, configuration, deployment, integration, troubleshooting, validation, dan technical platform recommendation | Business analysis, maturity assessment, corporate intelligence, persona development, atau book publication |

## Routing Principle

Routing skill menggunakan **primary user intent**, bukan sekadar keyword.

Contoh:

- “Cara setup Hostinger VPS” → `ai-advice`
- “OpenRouter error saat menjalankan Business Modeler” → `ai-advice`
- “Analisis model bisnis perusahaan yang menggunakan OpenRouter” → `indonesia-business-modeler`
- “Nilai maturity organisasi ini” → `business-excellence-assessor`
- “Berikan update berita sektor Rekind hari ini” → `indonesia-corporate-action-intelligence`
- “Buat handbook dari hasil analisis ini” → `book-writer`

Detail routing tersedia di:

`docs/skill-routing-matrix.md`

## Perubahan utama 0.7.0-draft

### AI Advice

Menambahkan skill baru `ai-advice` sebagai general technical setup advisor.

Capability utama:

- technical setup;
- software installation;
- configuration;
- deployment;
- infrastructure setup;
- technical integration;
- troubleshooting;
- validation;
- technical platform recommendation.

AI Advice menggunakan empat working mode:

1. Advisor Mode
2. Setup Mode
3. Troubleshooting Mode
4. Validation Mode

Skill dirancang modular dengan struktur:

```text
skills/ai-advice/
├── SKILL.md
├── README.md
├── references/
│   ├── api-integration.md
│   ├── database.md
│   ├── deployment.md
│   ├── discord.md
│   ├── etap.md
│   ├── github.md
│   ├── hostinger.md
│   ├── linux-ubuntu.md
│   ├── openrouter.md
│   └── security.md
└── templates/
    ├── comparison-template.md
    ├── setup-checklist.md
    ├── troubleshooting-template.md
    └── validation-checklist.md
```

Routing AI Advice diperbaiki menjadi **intent-based routing**.

Skill tidak boleh aktif hanya karena prompt mengandung kata seperti:

- API;
- GitHub;
- server;
- database;
- OpenRouter;
- Linux;
- error.

Primary intent user harus berkaitan dengan setup, configuration, deployment, troubleshooting, validation, integration, atau technical recommendation.

### Indonesia Business Modeler

Folder skill distandardisasi menjadi:

`skills/indonesia-business-modeler/`

Investment analysis diperluas dari IRR Matrix menjadi **Investment Feasibility Analysis**, mencakup:

- NPV;
- IRR;
- ROI;
- ARR;
- BEP Unit dan BEP Sales;
- Payback Period;
- Discounted Payback Period;
- Profitability Index;
- scenario dan sensitivity analysis.

Formula Profitability Index diperbaiki.

Aturan basis analisis ditambahkan untuk:

- cash flow;
- working capital;
- tax;
- nominal versus real;
- project versus equity;
- multiple-IRR risk.

Skill juga mencakup analisis peluang bisnis secara evidence-based.

### Indonesia Corporate Action Intelligence

- CNBC Indonesia dipertahankan sebagai media Indonesia prioritas.
- **CNBC International/CNBC.com** digunakan sebagai international Tier 2 source.
- Mode Rekind Sector Intelligence menggunakan hard filter:
  **Energi, Oil & Gas, Petrokimia, dan Pupuk**.
- Berita internasional harus memiliki global-to-Indonesia/Rekind transmission path.
- Analisis diperluas ke:
  - project/tender;
  - value chain;
  - supply-demand;
  - feedstock;
  - EPC/O&M/utilities implications;
  - horizon;
  - risk/opportunity;
  - next signal.

Routing skill dipisahkan secara eksplisit dari `ai-advice`, sehingga masalah teknis terkait API, deployment, atau connectivity diarahkan ke AI Advice, sedangkan news intelligence tetap menjadi domain Corporate Action Intelligence.

### Business Excellence Assessor

Menambahkan rubric enam dimensi:

- Approach;
- Deployment;
- Measurement;
- Learning;
- Integration;
- Results.

Recommendation traceability dan prioritization juga ditambahkan.

Business Excellence Assessor tetap dibatasi untuk maturity assessment dan tidak mengambil tugas financial feasibility atau technical troubleshooting.

### Persona

Menambahkan:

- Fast Build mode;
- definition of complete persona;
- routing antar-skill;
- batas kewenangan terhadap domain skill.

Persona tidak menggantikan domain skill.

### Book Writer

Menambahkan:

- source traceability matrix;
- publication QA report;
- deliverables per mode;
- kontrol konsistensi untuk buku panjang.

Book Writer menangani publication architecture, bukan menggantikan domain analysis atau technical setup.

## Struktur Repository

```text
persona-development/
├── skills/
│   ├── ai-advice/
│   ├── book-writer/
│   ├── business-excellence-assessor/
│   ├── indonesia-business-modeler/
│   ├── indonesia-corporate-action-intelligence/
│   └── persona/
│
├── tests/
│   └── test cases dan test results
│
├── docs/
│   ├── installation.md
│   ├── skill-routing-matrix.md
│   ├── Hermes_AI_Agent_Architecture.md
│   ├── audit documents
│   ├── release notes
│   └── validation report
│
├── feedback/
│   └── correction and learning logs
│
├── learning/
│   └── approved lessons and unresolved questions
│
├── CHANGELOG.md
├── README.md
└── VERSION
```

## Validation Strategy

Static validation digunakan untuk memastikan:

- struktur folder;
- path;
- frontmatter;
- skill name consistency;
- Markdown structure;
- required files;
- reference paths;
- template paths;
- dependency integrity.

Static validation **tidak membuktikan behavioral response sudah benar**.

Behavioral testing tetap diperlukan untuk memastikan:

- skill dapat terdeteksi;
- skill routing sesuai primary intent;
- explicit skill invocation bekerja;
- implicit routing bekerja;
- output mengikuti instruction skill;
- troubleshooting mengikuti diagnostic-first behavior;
- validation dilakukan sebelum menyatakan setup selesai;
- multi-user menghasilkan routing yang konsisten.

## Recommended Behavioral Tests

Setiap skill harus diuji melalui:

1. direct invocation;
2. automatic routing;
3. boundary/conflict prompt;
4. negative routing;
5. language behavior;
6. multi-user consistency;
7. expected output structure;
8. failure handling.

Khusus `ai-advice`, minimum test mencakup:

- Advisor Mode;
- Setup Mode;
- Troubleshooting Mode;
- Validation Mode;
- security behavior;
- beginner instruction;
- unknown platform handling;
- cross-skill routing;
- multi-user routing consistency.

## Status

Package berstatus **0.7.0-draft**.

Current status:

- skill structure: implemented;
- AI Advice: added;
- routing matrix: updated;
- Business Modeler folder naming: standardized;
- static validation: required after every structural change;
- behavioral testing: still required before release candidate;
- multi-user routing consistency: requires validation through Hermes/Discord.

Package belum boleh disebut **production-ready** sebelum seluruh acceptance test selesai dan hasilnya didokumentasikan.

## Dokumen penting

- `docs/skill-routing-matrix.md`
- `docs/Hermes_AI_Agent_Architecture.md`
- `docs/release-notes-v0.6.0.md`
- `docs/full-skill-audit-v0.6.0.md`
- `docs/validation-report.json`
- `CHANGELOG.md`

Catatan: release notes, audit, validation report, dan versioning perlu diperbarui untuk mencerminkan perubahan `0.7.0-draft`, khususnya penambahan `ai-advice` dan revisi routing.

## Source of Truth

GitHub repository digunakan sebagai **source of truth** untuk versi skill terbaru.

Workflow pengembangan:

```text
Claude
→ generate / review / brainstorming

VS Code
→ final editing

GitHub
→ version control dan source of truth

Hermes
→ runtime untuk menjalankan skill

Discord
→ multi-user interface
```

Perubahan pada Claude Project tidak otomatis memperbarui GitHub atau Hermes. Setiap versi final harus disimpan ke GitHub dan kemudian disinkronkan ke runtime Hermes.