/* ---------------------------------------------------------
   IWR Procesnavigator — Design system
   Refined industrial: graphite + steel blue + signal orange
   --------------------------------------------------------- */

:root {
  --ink:        #0b1220;
  --ink-2:      #1a2332;
  --ink-3:      #2b3648;
  --line:       #d9dde4;
  --line-2:     #eceff3;
  --paper:      #fafaf8;
  --paper-2:    #f2f3ef;
  --steel:      #2E75B6;
  --steel-d:    #1F4E79;
  --signal:     #d9651e;
  --signal-2:   #b04d0e;
  --green:      #2d8a4e;
  --red:        #c0392b;
  --amber:      #d68910;
  --mute:       #6a748a;

  --serif:   'Newsreader', Georgia, serif;
  --sans:    'Inter Tight', system-ui, sans-serif;
  --mono:    'JetBrains Mono', Menlo, monospace;
}

* { box-sizing: border-box; }
html { scroll-behavior: smooth; }

body {
  margin: 0;
  font-family: var(--sans);
  background: var(--paper);
  color: var(--ink);
  font-size: 16px;
  line-height: 1.55;
  -webkit-font-smoothing: antialiased;
}

.wrap { max-width: 1180px; margin: 0 auto; padding: 0 32px; }

/* ---------- BG GRID ---------- */
.grid-bg {
  position: fixed; inset: 0;
  background-image:
    linear-gradient(to right, rgba(11,18,32,0.035) 1px, transparent 1px),
    linear-gradient(to bottom, rgba(11,18,32,0.035) 1px, transparent 1px);
  background-size: 48px 48px;
  pointer-events: none;
  z-index: 0;
}
main, header, footer { position: relative; z-index: 1; }

/* ---------- HEADER ---------- */
.site-header {
  border-bottom: 1px solid var(--line);
  background: rgba(250,250,248,0.85);
  backdrop-filter: blur(8px);
  position: sticky; top: 0; z-index: 10;
}
.site-header .wrap {
  display: flex; justify-content: space-between; align-items: center;
  height: 64px;
}
.brand {
  display: flex; align-items: baseline; gap: 10px;
  font-family: var(--mono); font-size: 14px; font-weight: 700;
}
.brand-mark { color: var(--signal); font-size: 18px; }
.brand-ver {
  font-size: 11px; font-weight: 500; color: var(--mute);
  border: 1px solid var(--line); padding: 2px 6px; border-radius: 3px;
}
.site-nav { display: flex; gap: 28px; align-items: center; font-size: 14px; }
.site-nav a { color: var(--ink-2); text-decoration: none; transition: color 0.15s; }
.site-nav a:hover { color: var(--signal); }
.nav-cta {
  background: var(--ink);
  color: var(--paper) !important;
  padding: 8px 16px;
  border-radius: 3px;
  font-weight: 500;
  font-family: var(--mono);
  font-size: 12px;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}
.nav-cta:hover { background: var(--signal) !important; color: white !important; }

/* ---------- HERO ---------- */
.hero { padding: 96px 0 80px; border-bottom: 1px solid var(--line); }
.hero-wrap { max-width: 960px; }
.eyebrow {
  font-family: var(--mono); font-size: 12px; text-transform: uppercase;
  letter-spacing: 0.1em; color: var(--mute);
  margin-bottom: 28px;
  display: flex; align-items: center; gap: 8px;
}
.eyebrow::before {
  content: ""; display: inline-block;
  width: 32px; height: 1px; background: var(--signal);
}
.headline {
  font-family: var(--serif);
  font-size: clamp(48px, 7vw, 92px);
  font-weight: 500;
  line-height: 1.02;
  letter-spacing: -0.02em;
  margin: 0 0 32px;
  color: var(--ink);
}
.headline em {
  font-style: italic; font-weight: 400;
  color: var(--steel-d);
  font-family: var(--serif);
}
.lede {
  font-size: 20px; line-height: 1.55; max-width: 720px;
  color: var(--ink-2);
  margin: 0 0 40px;
}
.hero-ctas { display: flex; gap: 12px; flex-wrap: wrap; margin-bottom: 72px; }
.btn {
  display: inline-flex; align-items: center; gap: 6px;
  padding: 14px 24px;
  font-family: var(--mono);
  font-size: 13px;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  text-decoration: none;
  border-radius: 3px;
  transition: all 0.15s;
  border: 1px solid transparent;
  cursor: pointer;
}
.btn-primary { background: var(--ink); color: var(--paper); }
.btn-primary:hover { background: var(--signal); }
.btn-ghost { background: transparent; color: var(--ink); border-color: var(--line); }
.btn-ghost:hover { border-color: var(--ink); background: var(--ink); color: var(--paper); }
.btn .meta { opacity: 0.6; font-weight: 400; }

.hero-stats {
  display: grid; grid-template-columns: repeat(4, 1fr);
  gap: 1px;
  background: var(--line);
  border: 1px solid var(--line);
}
.stat {
  background: var(--paper);
  padding: 28px 24px;
}
.stat-val {
  font-family: var(--serif);
  font-size: 48px;
  font-weight: 500;
  letter-spacing: -0.03em;
  line-height: 1;
  color: var(--steel-d);
  margin-bottom: 8px;
}
.stat-lbl {
  font-family: var(--mono);
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--mute);
  line-height: 1.4;
}

/* ---------- SECTIONS ---------- */
.section { padding: 96px 0; border-bottom: 1px solid var(--line); }
.section-dark { background: var(--ink); color: var(--paper); }
.section-dark h2 { color: var(--paper); }
.section-accent { background: var(--paper-2); }

.section-head {
  display: flex; align-items: baseline; gap: 24px;
  margin-bottom: 56px;
  padding-bottom: 24px;
  border-bottom: 1px solid var(--line);
}
.section-dark .section-head { border-bottom-color: var(--ink-3); }
.section-idx {
  font-family: var(--mono);
  font-size: 12px;
  font-weight: 700;
  color: var(--signal);
  letter-spacing: 0.05em;
}
.section h2 {
  font-family: var(--serif);
  font-size: 42px;
  font-weight: 500;
  letter-spacing: -0.015em;
  margin: 0;
  line-height: 1.1;
}

/* ---------- CARDS ---------- */
.cols-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 24px; }
.card {
  background: var(--paper);
  border: 1px solid var(--line);
  padding: 32px;
  display: flex; flex-direction: column;
  transition: all 0.2s;
}
.card:hover { border-color: var(--ink); transform: translateY(-2px); }
.card-accent { background: var(--ink); color: var(--paper); border-color: var(--ink); }
.card-accent h3 { color: var(--paper); }
.card-accent p { color: var(--line); }
.card-accent .card-num { color: var(--signal); }
.card-num {
  font-family: var(--mono);
  font-size: 11px;
  font-weight: 700;
  color: var(--mute);
  letter-spacing: 0.1em;
  margin-bottom: 16px;
}
.card h3 {
  font-family: var(--serif);
  font-size: 24px; font-weight: 500;
  margin: 0 0 12px;
  line-height: 1.2;
}
.card p { margin: 0; color: var(--ink-2); font-size: 15px; }

/* ---------- FORMULA BLOCK ---------- */
.formula-block {
  background: var(--ink-2);
  border: 1px solid var(--ink-3);
  border-radius: 3px;
  overflow: hidden;
}
.formula-row {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 24px;
  padding: 20px 28px;
  border-bottom: 1px solid var(--ink-3);
  align-items: center;
}
.formula-row:last-child { border-bottom: none; }
.formula-hl { background: rgba(217, 101, 30, 0.08); }
.formula-hl .formula-label { color: var(--signal) !important; }
.formula-label {
  font-family: var(--mono);
  font-size: 12px;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  color: var(--line);
  font-weight: 500;
}
.formula-row code {
  font-family: var(--mono);
  font-size: 14px;
  color: var(--paper);
  background: rgba(255,255,255,0.04);
  padding: 6px 10px;
  border-radius: 2px;
}
.voorspel-note {
  margin: 40px 0 0;
  color: var(--line);
  font-size: 15px;
  max-width: 720px;
}
.voorspel-note code {
  font-family: var(--mono);
  font-size: 13px;
  background: var(--ink-2);
  padding: 2px 6px;
  border-radius: 2px;
  color: var(--paper);
}
.voorspel-note strong { color: var(--signal); font-weight: 600; }

/* ---------- STEPS ---------- */
.steps {
  list-style: none; padding: 0; margin: 0;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1px;
  background: var(--line);
  border: 1px solid var(--line);
}
.steps li {
  background: var(--paper);
  padding: 40px 36px;
  display: grid;
  grid-template-columns: 60px 1fr;
  gap: 24px;
  align-items: start;
}
.step-n {
  font-family: var(--serif);
  font-size: 60px;
  font-weight: 500;
  line-height: 1;
  color: var(--steel);
  letter-spacing: -0.03em;
}
.steps h3 {
  font-family: var(--serif);
  font-size: 22px; font-weight: 500;
  margin: 0 0 10px;
}
.steps p { margin: 0; color: var(--ink-2); font-size: 15px; }
.steps code {
  font-family: var(--mono);
  font-size: 13px;
  background: var(--paper-2);
  padding: 2px 6px;
  border-radius: 2px;
  color: var(--steel-d);
  font-weight: 500;
}

/* ---------- DOWNLOAD GRID ---------- */
.download-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}
.download-card {
  background: var(--paper);
  border: 1px solid var(--line);
  padding: 40px 32px;
  display: flex; flex-direction: column;
  align-items: flex-start;
}
.download-icon { font-size: 32px; margin-bottom: 16px; }
.download-card h3 {
  font-family: var(--serif);
  font-size: 24px;
  font-weight: 500;
  margin: 0 0 12px;
}
.download-card p {
  flex: 1;
  margin: 0 0 24px;
  color: var(--ink-2);
  font-size: 15px;
}

/* ---------- BRONNEN DL ---------- */
.bronnen {
  display: grid;
  grid-template-columns: 240px 1fr;
  gap: 0;
  margin: 0;
  border-top: 1px solid var(--line);
}
.bronnen dt, .bronnen dd {
  padding: 24px 0;
  border-bottom: 1px solid var(--line);
  margin: 0;
}
.bronnen dt {
  font-family: var(--mono);
  font-size: 13px;
  font-weight: 500;
  color: var(--steel-d);
  text-transform: uppercase;
  letter-spacing: 0.04em;
}
.bronnen dd { color: var(--ink-2); font-size: 15px; }

/* ---------- FOOTER ---------- */
.site-foot {
  background: var(--ink);
  color: var(--line);
  padding: 48px 0;
}
.foot-wrap { display: flex; justify-content: space-between; align-items: center; gap: 24px; flex-wrap: wrap; }
.foot-brand {
  display: flex; align-items: center; gap: 12px;
  font-family: var(--mono); font-size: 14px; color: var(--paper);
}
.foot-meta {
  font-family: var(--mono); font-size: 12px; color: var(--mute);
  max-width: 560px;
  text-align: right;
}

/* ---------- RESPONSIVE ---------- */
@media (max-width: 900px) {
  .site-nav a:not(.nav-cta) { display: none; }
  .hero-stats { grid-template-columns: repeat(2, 1fr); }
  .cols-3, .download-grid { grid-template-columns: 1fr; }
  .steps { grid-template-columns: 1fr; }
  .formula-row { grid-template-columns: 1fr; gap: 8px; }
  .bronnen { grid-template-columns: 1fr; }
  .bronnen dt { padding-bottom: 4px; border-bottom: none; }
  .bronnen dd { padding-top: 4px; }
  .foot-wrap { flex-direction: column; align-items: flex-start; }
  .foot-meta { text-align: left; }
}

/* =========================================================
   DASHBOARD-SPECIFIC STYLING
   ========================================================= */

.dash-body { background: var(--paper); }
.dash-header {
  background: var(--ink);
  color: var(--paper);
  padding: 18px 0;
  border-bottom: 3px solid var(--signal);
}
.dash-header .wrap {
  display: flex; justify-content: space-between; align-items: center;
  gap: 24px;
}
.dash-header h1 {
  font-family: var(--mono); font-size: 14px; font-weight: 700;
  margin: 0; letter-spacing: 0.06em; text-transform: uppercase;
}
.dash-header .brand-mark { font-size: 16px; margin-right: 8px; }
.dash-header nav a {
  color: var(--line); text-decoration: none;
  font-family: var(--mono); font-size: 12px;
  margin-left: 20px;
  text-transform: uppercase; letter-spacing: 0.06em;
}
.dash-header nav a:hover { color: var(--signal); }

.dash-toolbar {
  padding: 24px 0;
  border-bottom: 1px solid var(--line);
  background: var(--paper-2);
}
.dash-toolbar .wrap {
  display: flex; justify-content: space-between; align-items: center;
  gap: 24px; flex-wrap: wrap;
}
.tb-left { display: flex; align-items: center; gap: 16px; flex-wrap: wrap; }
.tb-label {
  font-family: var(--mono);
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--mute);
}
.tb-source {
  font-family: var(--mono);
  font-size: 13px;
  padding: 6px 12px;
  background: var(--paper);
  border: 1px solid var(--line);
  border-radius: 2px;
}
.tb-source strong { color: var(--steel-d); }
.file-btn {
  display: inline-flex; align-items: center; gap: 8px;
  padding: 10px 18px;
  font-family: var(--mono); font-size: 12px; font-weight: 500;
  text-transform: uppercase; letter-spacing: 0.05em;
  background: var(--ink); color: var(--paper);
  border: none; border-radius: 2px; cursor: pointer;
  transition: background 0.15s;
}
.file-btn:hover { background: var(--signal); }
.file-btn-secondary { background: transparent; color: var(--ink); border: 1px solid var(--line); }
.file-btn-secondary:hover { background: var(--ink); color: var(--paper); border-color: var(--ink); }

.dash-tabs {
  display: flex; gap: 0;
  border-bottom: 1px solid var(--line);
  background: var(--paper);
}
.tab {
  padding: 16px 24px;
  font-family: var(--mono);
  font-size: 12px;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  color: var(--mute);
  background: transparent;
  border: none;
  border-bottom: 2px solid transparent;
  cursor: pointer;
  transition: all 0.15s;
}
.tab:hover { color: var(--ink); }
.tab-active {
  color: var(--ink);
  border-bottom-color: var(--signal);
}
.tab .tab-count {
  display: inline-block;
  margin-left: 6px;
  font-size: 10px;
  padding: 1px 5px;
  background: var(--paper-2);
  border-radius: 8px;
  color: var(--mute);
}
.tab-active .tab-count { background: var(--signal); color: white; }

.dash-main { padding: 32px 0 96px; }

.panel { display: none; }
.panel-active { display: block; }

/* PROJECTOVERZICHT */
.po-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
  gap: 16px;
}
.po-card {
  background: white;
  border: 1px solid var(--line);
  padding: 24px;
  display: flex; flex-direction: column; gap: 16px;
  position: relative;
  transition: all 0.15s;
}
.po-card:hover { border-color: var(--ink); }
.po-card::before {
  content: ""; position: absolute; top: 0; left: 0;
  width: 4px; height: 100%;
  background: var(--line);
}
.po-card-green::before { background: var(--green); }
.po-card-amber::before { background: var(--amber); }
.po-card-red::before   { background: var(--red); }
.po-card-grey::before  { background: var(--line); }
.po-hd {
  display: flex; justify-content: space-between; align-items: flex-start;
  gap: 12px;
}
.po-id {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--mute);
  letter-spacing: 0.04em;
  margin-bottom: 4px;
}
.po-name {
  font-family: var(--serif);
  font-size: 22px;
  font-weight: 500;
  line-height: 1.15;
  color: var(--ink);
  margin: 0 0 8px;
}
.po-route {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--mute);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}
.po-route strong { color: var(--steel-d); font-weight: 500; }
.po-status {
  font-family: var(--mono);
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  font-weight: 500;
  white-space: nowrap;
  padding: 4px 8px;
  border-radius: 2px;
}
.po-status-green { background: #e3f4e8; color: var(--green); }
.po-status-amber { background: #fdf2d8; color: var(--amber); }
.po-status-red   { background: #fbe1dc; color: var(--red); }
.po-status-grey  { background: var(--paper-2); color: var(--mute); }

.po-dates { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
.po-date-block {
  border: 1px solid var(--line);
  padding: 12px 14px;
  background: var(--paper);
}
.po-date-lbl {
  font-family: var(--mono);
  font-size: 10px;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  color: var(--mute);
  margin-bottom: 4px;
}
.po-date-val {
  font-family: var(--serif);
  font-size: 20px;
  font-weight: 500;
  color: var(--ink);
  letter-spacing: -0.01em;
}
.po-date-verwacht { border-left: 3px solid var(--signal); }

.po-delta {
  display: flex; align-items: baseline; gap: 12px;
  padding: 12px 14px;
  background: var(--paper-2);
  border: 1px solid var(--line);
}
.po-delta-val {
  font-family: var(--mono);
  font-size: 20px; font-weight: 700;
  color: var(--ink);
}
.po-delta-lbl {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--mute);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}
.po-krit {
  font-size: 13px;
  color: var(--ink-2);
  padding-top: 12px;
  border-top: 1px solid var(--line-2);
}
.po-krit-lbl {
  font-family: var(--mono);
  font-size: 10px;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  color: var(--mute);
  margin-bottom: 4px;
}
.po-krit-val { font-weight: 500; color: var(--signal-2); }

/* DASHBOARD TABLE */
.ds-toolbar {
  display: flex; gap: 16px; align-items: center;
  padding: 16px 0; flex-wrap: wrap;
  margin-bottom: 16px;
}
.ds-toolbar select, .ds-toolbar input {
  font-family: var(--mono); font-size: 13px;
  padding: 8px 12px;
  border: 1px solid var(--line);
  border-radius: 2px;
  background: white;
  color: var(--ink);
}
.ds-toolbar select:focus, .ds-toolbar input:focus {
  outline: none; border-color: var(--signal);
}
.ds-count {
  margin-left: auto;
  font-family: var(--mono); font-size: 12px;
  color: var(--mute);
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.ds-table-wrap {
  background: white;
  border: 1px solid var(--line);
  overflow-x: auto;
}
table.ds-table {
  width: 100%;
  border-collapse: collapse;
  font-size: 13px;
  min-width: 1400px;
}
.ds-table thead {
  background: var(--ink);
}
.ds-table th {
  color: var(--paper);
  text-align: left;
  padding: 12px 10px;
  font-family: var(--mono);
  font-size: 10px;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  white-space: nowrap;
  position: sticky; top: 0;
  border-right: 1px solid var(--ink-3);
}
.ds-table td {
  padding: 10px;
  border-bottom: 1px solid var(--line-2);
  border-right: 1px solid var(--line-2);
  vertical-align: top;
}
.ds-table tr:hover { background: var(--paper-2); }
.ds-table .c-mono { font-family: var(--mono); font-size: 12px; }
.ds-table .c-id { font-family: var(--mono); font-size: 11px; color: var(--mute); }
.ds-table .c-type { min-width: 280px; }
.ds-table .c-num { text-align: right; font-family: var(--mono); }
.ds-table .c-date { font-family: var(--mono); font-size: 12px; white-space: nowrap; }

.sl {
  display: inline-block;
  width: 12px; height: 12px;
  border-radius: 50%;
  border: 2px solid transparent;
}
.sl-green  { background: var(--green); }
.sl-amber  { background: var(--amber); }
.sl-red    { background: var(--red); }
.sl-grey   { background: #cfd4de; }

.status-pill {
  display: inline-block;
  padding: 2px 8px;
  border-radius: 2px;
  font-family: var(--mono);
  font-size: 10px;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}
.status-Nodig       { background: var(--paper-2); color: var(--mute); }
.status-Ingediend   { background: #e4efff; color: var(--steel-d); }
.status-Afgerond    { background: #e3f4e8; color: var(--green); }
.status-Goedgekeurd { background: #e3f4e8; color: var(--green); font-weight: 700; }
.status-Afgewezen   { background: #fbe1dc; color: var(--red); }
.status-Nvt         { background: var(--paper-2); color: var(--mute); text-decoration: line-through; }

.haalbaar-JA       { color: var(--green); font-weight: 600; }
.haalbaar-KRAP     { color: var(--amber); font-weight: 600; }
.haalbaar-NEE      { color: var(--red); font-weight: 700; }
.haalbaar-ONBEKEND { color: var(--mute); }

.empty-state {
  padding: 96px 32px;
  text-align: center;
  color: var(--mute);
  font-family: var(--mono);
  background: white;
  border: 1px dashed var(--line);
}
.empty-state strong { display: block; color: var(--ink); font-size: 18px; margin-bottom: 8px; font-family: var(--serif); font-weight: 500; }
