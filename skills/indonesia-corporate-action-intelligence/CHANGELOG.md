# Changelog — Indonesia Corporate Action Intelligence

## [1.0.0-draft] — 2026-07-27

### Major revision

- Menambahkan **CNBC International/CNBC.com** sebagai Tier 2B international
  source, berdampingan dengan CNBC Indonesia sebagai Tier 2A local source.
- Memperketat Mode K menjadi hard filter empat sektor: Energi, Oil & Gas,
  Petrokimia, dan Pupuk.
- Menambahkan bilingual search strategy per sektor.
- Menambahkan mandatory global-to-Indonesia/Rekind transmission path untuk
  berita internasional.
- Memperdalam analisis menjadi event, sector/value-chain, business relevance,
  horizon, risk/opportunity signal, dan next indicator to monitor.
- Menambahkan selection gate, source balance rules, deep item structure,
  global-to-local table, and opportunity/risk matrix.
- Memperluas tests untuk CNBC, hard-sector boundary, international relevance,
  no-filler behavior, HTML, and routing.

### Status

Draft. Static validation dilakukan pada package 0.6.0-draft; behavioral search
and report tests belum dijalankan di Claude.

## [0.2.0-draft] — 2026-07-24

- Added Mode K and CNBC Indonesia priority.

## [0.1.0-draft] — 2026-07-22

- Initial prototype.
