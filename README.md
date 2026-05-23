<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fiches de Révision — Management Fondamental S2</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Source+Sans+3:ital,wght@0,300;0,400;0,600;0,700;1,400&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet">
<style>
:root {
  --blue: #1A4F8A; --blue-mid: #2E6DB4; --blue-light: #D6E8F7; --blue-pale: #EEF5FC;
  --green: #1A6B3C; --green-mid: #28A85A; --green-light: #D4EDDF; --green-pale: #EEF8F3;
  --orange: #C0500A; --orange-mid: #E07020; --orange-light: #FAE3CF; --orange-pale: #FEF4EC;
  --purple: #5B2D8A; --purple-mid: #7B52B8; --purple-light: #E8DAFA; --purple-pale: #F5F0FC;
  --red: #B01020; --red-mid: #D03040; --red-light: #FADADD; --red-pale: #FEF0F1;
  --teal: #0B6B5C; --teal-mid: #20967C; --teal-light: #C8EDE7;
  --gray: #404550; --gray-mid: #707888; --gray-light: #F0F2F5; --gray-pale: #F8F9FA;
  --gold: #B8860B; --gold-light: #FFF8DC;
  --bg: #F7F8FC; --white: #FFFFFF;
  --shadow: 0 2px 12px rgba(0,0,0,0.08);
  --shadow-hover: 0 8px 30px rgba(0,0,0,0.14);
  --radius: 10px;
  --font-head: 'Playfair Display', Georgia, serif;
  --font-body: 'Source Sans 3', sans-serif;
  --font-mono: 'JetBrains Mono', monospace;
}

* { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: var(--font-body); background: var(--bg); color: var(--gray); line-height: 1.65; }

/* ── LAYOUT ── */
.page-wrap { max-width: 1120px; margin: 0 auto; padding: 0 24px 60px; }

/* ── HERO ── */
.hero {
  background: linear-gradient(135deg, var(--blue) 0%, #0D2D54 50%, #1A3A6B 100%);
  color: white; padding: 52px 40px 44px; margin-bottom: 0;
  position: relative; overflow: hidden;
}
.hero::before {
  content: ''; position: absolute; top: -60px; right: -60px;
  width: 320px; height: 320px; border-radius: 50%;
  background: rgba(255,255,255,0.05);
}
.hero::after {
  content: ''; position: absolute; bottom: -80px; left: 30%;
  width: 200px; height: 200px; border-radius: 50%;
  background: rgba(255,255,255,0.04);
}
.hero h1 { font-family: var(--font-head); font-size: 2.6rem; font-weight: 900; letter-spacing: -0.5px; margin-bottom: 8px; }
.hero .sub { font-size: 1.1rem; opacity: 0.8; margin-bottom: 28px; font-weight: 300; }
.hero-pills { display: flex; gap: 10px; flex-wrap: wrap; }
.pill {
  background: rgba(255,255,255,0.15); border: 1px solid rgba(255,255,255,0.25);
  padding: 5px 16px; border-radius: 20px; font-size: 0.82rem; font-weight: 600;
  cursor: pointer; transition: all .2s; color: white;
}
.pill:hover, .pill.active { background: white; color: var(--blue); }

/* ── TABS NAV ── */
.tabs-nav {
  display: flex; gap: 0; background: white; border-radius: 0 0 var(--radius) var(--radius);
  box-shadow: var(--shadow); overflow-x: auto; border-top: 3px solid var(--blue);
  padding: 0 8px;
}
.tab-btn {
  padding: 14px 20px; font-size: 0.85rem; font-weight: 600; cursor: pointer;
  border: none; background: none; color: var(--gray-mid); white-space: nowrap;
  border-bottom: 3px solid transparent; margin-bottom: -3px; transition: all .2s;
  font-family: var(--font-body);
}
.tab-btn:hover { color: var(--blue); }
.tab-btn.active { color: var(--blue); border-bottom-color: var(--blue); }

/* ── SECTIONS ── */
.section { display: none; padding: 36px 0; }
.section.active { display: block; }
.section-title {
  font-family: var(--font-head); font-size: 1.9rem; font-weight: 700;
  color: var(--blue); margin-bottom: 6px; border-bottom: 3px solid var(--blue-light);
  padding-bottom: 10px;
}
.section-sub { color: var(--gray-mid); font-size: 0.95rem; margin-bottom: 32px; font-style: italic; }

/* ── CARDS ── */
.card {
  background: white; border-radius: var(--radius); box-shadow: var(--shadow);
  padding: 24px 28px; margin-bottom: 24px; border-left: 4px solid var(--blue);
  transition: box-shadow .2s;
}
.card:hover { box-shadow: var(--shadow-hover); }
.card.green { border-left-color: var(--green-mid); }
.card.orange { border-left-color: var(--orange-mid); }
.card.purple { border-left-color: var(--purple-mid); }
.card.red { border-left-color: var(--red-mid); }
.card.teal { border-left-color: var(--teal-mid); }
.card.gold { border-left-color: var(--gold); }

.card-title {
  font-family: var(--font-head); font-size: 1.2rem; font-weight: 700;
  color: var(--blue); margin-bottom: 14px; display: flex; align-items: center; gap: 10px;
}
.card-title .num {
  background: var(--blue); color: white; width: 28px; height: 28px;
  border-radius: 50%; display: flex; align-items: center; justify-content: center;
  font-size: 0.8rem; font-family: var(--font-mono); flex-shrink: 0;
}

/* ── DEF BOX ── */
.def-box {
  background: var(--blue-pale); border-left: 4px solid var(--blue-mid);
  padding: 14px 18px; border-radius: 0 8px 8px 0; margin: 14px 0;
  font-style: italic; color: var(--blue); font-size: 0.93rem; line-height: 1.7;
}
.def-box.green { background: var(--green-pale); border-left-color: var(--green-mid); color: var(--green); }
.def-box.orange { background: var(--orange-pale); border-left-color: var(--orange-mid); color: var(--orange); }
.def-box.purple { background: var(--purple-pale); border-left-color: var(--purple-mid); color: var(--purple); }

/* ── TIP / WARNING ── */
.tip-box {
  background: var(--gold-light); border: 1px solid #D4A000;
  border-radius: 8px; padding: 12px 16px; margin: 14px 0;
  font-size: 0.88rem; display: flex; gap: 10px; align-items: flex-start;
}
.tip-box .icon { font-size: 1.1rem; flex-shrink: 0; margin-top: 1px; }
.warn-box {
  background: var(--red-pale); border: 1px solid var(--red-mid);
  border-radius: 8px; padding: 12px 16px; margin: 14px 0;
  font-size: 0.88rem; display: flex; gap: 10px; align-items: flex-start; color: var(--red);
}

/* ── GRID ── */
.grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin: 16px 0; }
.grid-3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 16px; margin: 16px 0; }
.grid-4 { display: grid; grid-template-columns: 1fr 1fr 1fr 1fr; gap: 14px; margin: 16px 0; }
.grid-5 { display: grid; grid-template-columns: repeat(5,1fr); gap: 12px; margin: 16px 0; }
@media(max-width:700px) {
  .grid-2,.grid-3,.grid-4,.grid-5 { grid-template-columns: 1fr; }
}

/* ── BOX ITEMS ── */
.box-item {
  border-radius: 8px; padding: 16px 18px; text-align: center;
}
.box-item .box-label { font-weight: 700; font-size: 0.95rem; margin-bottom: 6px; }
.box-item .box-sub { font-size: 0.8rem; opacity: 0.85; line-height: 1.5; }

/* ── SCHEMAS ── */
.schema-wrap { margin: 20px 0; }
.schema-label {
  font-family: var(--font-mono); font-size: 0.72rem; text-transform: uppercase;
  letter-spacing: 1.5px; color: var(--gray-mid); margin-bottom: 10px;
  border-bottom: 1px dashed var(--gray-light); padding-bottom: 5px;
}

/* PODC */
.podc-flow { display: flex; align-items: stretch; gap: 0; margin: 16px 0; }
.podc-step {
  flex: 1; padding: 18px 12px; text-align: center; position: relative;
  clip-path: polygon(0 0, calc(100% - 18px) 0, 100% 50%, calc(100% - 18px) 100%, 0 100%, 18px 50%);
}
.podc-step:first-child { clip-path: polygon(0 0, calc(100% - 18px) 0, 100% 50%, calc(100% - 18px) 100%, 0 100%); }
.podc-step:last-child { clip-path: polygon(0 0, 100% 0, 100% 100%, 0 100%, 18px 50%); }
.podc-letter { font-family: var(--font-head); font-size: 2rem; font-weight: 900; display: block; }
.podc-name { font-weight: 700; font-size: 0.85rem; display: block; margin-bottom: 6px; }
.podc-desc { font-size: 0.75rem; opacity: 0.88; line-height: 1.4; }

/* Pyramide Maslow */
.pyramid { display: flex; flex-direction: column; align-items: center; gap: 4px; margin: 16px 0; }
.pyramid-row {
  display: flex; align-items: center; justify-content: center;
  border-radius: 6px; color: white; padding: 12px 20px; text-align: center;
  transition: transform .2s; cursor: default;
}
.pyramid-row:hover { transform: scaleX(1.02); z-index: 1; }
.pyramid-row .level-num { font-family: var(--font-mono); font-size: 0.75rem; margin-right: 8px; opacity: 0.8; }
.pyramid-row .level-name { font-weight: 700; font-size: 0.95rem; }
.pyramid-row .level-ex { font-size: 0.78rem; opacity: 0.85; margin-left: 8px; }

/* Mintzberg */
.mintz { display: grid; grid-template-columns: 160px 1fr 160px; gap: 8px; margin: 16px 0; }
.mintz-center { display: flex; flex-direction: column; gap: 8px; }
.mintz-box {
  border-radius: 8px; padding: 14px 16px; text-align: center;
  font-weight: 600; font-size: 0.88rem;
}
.mintz-side {
  border-radius: 8px; padding: 14px 12px; text-align: center;
  font-size: 0.8rem; font-weight: 600; display: flex; flex-direction: column; justify-content: center;
}
.mintz-sub { font-weight: 400; font-size: 0.75rem; opacity: 0.85; margin-top: 4px; line-height: 1.4; }

/* Tableau responsive */
.rtable { width: 100%; border-collapse: collapse; font-size: 0.87rem; margin: 14px 0; }
.rtable th {
  padding: 10px 14px; text-align: left; font-weight: 700; font-size: 0.82rem;
  letter-spacing: 0.3px;
}
.rtable td { padding: 10px 14px; vertical-align: top; line-height: 1.55; }
.rtable tr:nth-child(even) td { background: var(--gray-pale); }
.rtable th, .rtable td { border: 1px solid #E0E4EB; }

/* Badge */
.badge {
  display: inline-block; padding: 2px 10px; border-radius: 12px;
  font-size: 0.74rem; font-weight: 700; letter-spacing: 0.3px;
}
.badge-blue { background: var(--blue-light); color: var(--blue); }
.badge-green { background: var(--green-light); color: var(--green); }
.badge-orange { background: var(--orange-light); color: var(--orange); }
.badge-red { background: var(--red-light); color: var(--red); }
.badge-purple { background: var(--purple-light); color: var(--purple); }

/* ── BULLET LIST ── */
ul.fiche { list-style: none; padding: 0; margin: 10px 0; }
ul.fiche li {
  padding: 6px 0 6px 22px; position: relative; font-size: 0.92rem;
  border-bottom: 1px dashed #EEF0F4;
}
ul.fiche li:last-child { border-bottom: none; }
ul.fiche li::before {
  content: '▸'; position: absolute; left: 0; color: var(--blue-mid); font-size: 0.8rem; top: 8px;
}
ul.fiche li strong { color: var(--gray); }

/* ── VS BOX ── */
.vs-wrap { display: grid; grid-template-columns: 1fr auto 1fr; gap: 0; align-items: stretch; margin: 14px 0; }
.vs-col { border-radius: 8px; padding: 18px 20px; }
.vs-middle {
  display: flex; align-items: center; justify-content: center;
  font-family: var(--font-head); font-size: 1.4rem; font-weight: 900;
  color: var(--gray-mid); padding: 0 12px;
}

/* ── PROCESS FLOW ── */
.process-flow { display: flex; align-items: center; gap: 0; margin: 16px 0; flex-wrap: wrap; }
.proc-step {
  flex: 1; min-width: 100px; padding: 14px 10px; text-align: center;
  border-radius: 6px; position: relative;
}
.proc-arrow { color: var(--gray-mid); font-size: 1.4rem; padding: 0 4px; }
.proc-num { font-family: var(--font-mono); font-size: 0.72rem; opacity: 0.8; display: block; margin-bottom: 4px; }
.proc-name { font-weight: 700; font-size: 0.82rem; display: block; }
.proc-sub { font-size: 0.73rem; margin-top: 5px; opacity: 0.85; line-height: 1.4; }

/* ── AUTHOR CARD ── */
.author-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 14px; margin: 14px 0; }
.author-card {
  border-radius: 10px; padding: 16px 18px; border: 1px solid #E0E4EB;
  background: white; transition: all .2s;
}
.author-card:hover { box-shadow: var(--shadow-hover); transform: translateY(-2px); }
.author-name { font-weight: 700; font-size: 0.95rem; margin-bottom: 2px; }
.author-dates { font-family: var(--font-mono); font-size: 0.72rem; color: var(--gray-mid); margin-bottom: 8px; }
.author-theory { font-weight: 600; font-size: 0.85rem; margin-bottom: 6px; }
.author-keys { font-size: 0.8rem; color: var(--gray-mid); line-height: 1.5; }

/* ── HERZBERG ── */
.herzberg { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin: 16px 0; }
.herz-col { border-radius: 8px; padding: 18px 20px; }
.herz-title { font-weight: 700; font-size: 1rem; margin-bottom: 8px; }
.herz-sub { font-size: 0.8rem; font-style: italic; margin-bottom: 12px; opacity: 0.85; }

/* ── STYLES MANAGEMENT ── */
.style-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; margin: 16px 0; }
.style-card {
  border-radius: 10px; overflow: hidden; box-shadow: var(--shadow);
  transition: transform .2s;
}
.style-card:hover { transform: translateY(-4px); }
.style-header { padding: 14px 16px; color: white; font-weight: 700; font-size: 1rem; }
.style-body { background: white; padding: 14px 16px; }
.style-body p { font-size: 0.82rem; margin-bottom: 8px; line-height: 1.5; }
.style-body .label { font-weight: 700; font-size: 0.73rem; text-transform: uppercase; letter-spacing: 0.8px; color: var(--gray-mid); margin-top: 8px; }

/* ── STRATEGIES ── */
.strat-flow { display: grid; grid-template-columns: repeat(4, 1fr); gap: 14px; margin: 16px 0; }
.strat-box {
  border-radius: 10px; overflow: hidden; box-shadow: var(--shadow);
}
.strat-head { padding: 14px 16px; color: white; }
.strat-head h3 { font-weight: 700; font-size: 0.95rem; margin-bottom: 4px; }
.strat-head p { font-size: 0.78rem; opacity: 0.88; }
.strat-body { background: white; padding: 14px 16px; }
.strat-body .tag { font-size: 0.76rem; font-weight: 600; text-transform: uppercase; letter-spacing: 0.5px; margin-bottom: 5px; }
.strat-body p { font-size: 0.81rem; line-height: 1.5; color: var(--gray); }

/* ── INTÉGRATION SCHEMA ── */
.integration-schema { margin: 16px 0; }
.int-row { display: flex; justify-content: center; gap: 0; margin-bottom: 8px; }
.int-box {
  flex: 1; max-width: 300px; padding: 12px 16px; text-align: center;
  border-radius: 6px; font-size: 0.84rem; font-weight: 600; margin: 0 4px;
}
.int-arrow { text-align: center; font-size: 1.3rem; color: var(--gray-mid); margin: -4px 0; }

/* ── PRINT ── */
@media print {
  .tabs-nav { display: none; }
  .section { display: block !important; page-break-after: always; }
  .hero { print-color-adjust: exact; }
}

/* Animations */
@keyframes fadeIn { from { opacity:0; transform: translateY(12px); } to { opacity:1; transform: none; } }
.section.active .card { animation: fadeIn .3s ease both; }
.section.active .card:nth-child(1) { animation-delay: .05s; }
.section.active .card:nth-child(2) { animation-delay: .1s; }
.section.active .card:nth-child(3) { animation-delay: .15s; }
.section.active .card:nth-child(4) { animation-delay: .2s; }
.section.active .card:nth-child(5) { animation-delay: .25s; }
</style>
</head>
<body>

<div class="hero">
  <div class="page-wrap">
    <h1>Fiches de Révision</h1>
    <p class="sub">Management Fondamental · Semestre 2 · 2025</p>
    <div class="hero-pills">
      <button class="pill active" onclick="showTab('ch1',this)">Intro & CH1</button>
      <button class="pill" onclick="showTab('ch2',this)">CH2 — Théories</button>
      <button class="pill" onclick="showTab('ch3',this)">CH3 — Motivation</button>
      <button class="pill" onclick="showTab('ch4',this)">CH4 — Styles</button>
      <button class="pill" onclick="showTab('ch5',this)">CH5 — Stratégies</button>
      <button class="pill" onclick="showTab('synthese',this)">🎯 Synthèse Examen</button>
    </div>
  </div>
</div>

<div class="page-wrap">
<div class="tabs-nav">
  <button class="tab-btn active" onclick="showTab('ch1',this)">Intro + Chapitre 1</button>
  <button class="tab-btn" onclick="showTab('ch2',this)">Chapitre 2 — Théories</button>
  <button class="tab-btn" onclick="showTab('ch3',this)">Chapitre 3 — Motivation</button>
  <button class="tab-btn" onclick="showTab('ch4',this)">Chapitre 4 — Styles</button>
  <button class="tab-btn" onclick="showTab('ch5',this)">Chapitre 5 — Stratégies</button>
  <button class="tab-btn" onclick="showTab('synthese',this)">🎯 Synthèse Examen</button>
</div>

<!-- ══════════════════════════════════════════ CH1 ══ -->
<div id="ch1" class="section active">
  <h2 class="section-title">Introduction + Chapitre 1</h2>
  <p class="section-sub">Le management · Le manager · L'organisation · La stratégie</p>

  <div class="card">
    <div class="card-title"><span class="num">1</span> Le concept de management — Définition</div>
    <div class="def-box">Le management est un <strong>processus spécifique</strong> qui consiste à entreprendre des actions de <strong>Planification, d'Organisation, de Direction et de Contrôle</strong> visant à atteindre des objectifs ciblés, par une utilisation optimale des ressources humaines, matérielles et financières.</div>
    <div class="schema-wrap">
      <div class="schema-label">Schéma — Le cycle P.O.D.C (à reproduire à l'examen)</div>
      <div class="podc-flow">
        <div class="podc-step" style="background:var(--blue);color:white">
          <span class="podc-letter">P</span>
          <span class="podc-name">Planification</span>
          <span class="podc-desc">Définir objectifs, ressources, délais. Quoi ? Comment ? Quand ?</span>
        </div>
        <div class="podc-step" style="background:var(--blue-mid);color:white">
          <span class="podc-letter">O</span>
          <span class="podc-name">Organisation</span>
          <span class="podc-desc">Structurer les 4M : Humains · Matière · Machines · Monnaie</span>
        </div>
        <div class="podc-step" style="background:var(--green-mid);color:white">
          <span class="podc-letter">D</span>
          <span class="podc-name">Direction</span>
          <span class="podc-desc">Animer, motiver, communiquer avec les équipes</span>
        </div>
        <div class="podc-step" style="background:var(--teal-mid);color:white">
          <span class="podc-letter">C</span>
          <span class="podc-name">Contrôle</span>
          <span class="podc-desc">Comparer prévisions et réalisations → corriger les écarts</span>
        </div>
      </div>
    </div>
    <div class="tip-box">
      <span class="icon">💡</span>
      <div><strong>Conseil examen :</strong> Le cycle PODC est LA question fondamentale. Mémorisez chaque étape avec sa définition + exemple concret (ex : une boulangerie qui planifie ses achats, organise son personnel, dirige ses apprentis et contrôle ses recettes).</div>
    </div>
  </div>

  <div class="card green">
    <div class="card-title"><span class="num" style="background:var(--green-mid)">2</span> Le manager — 3 profils essentiels</div>
    <div class="def-box green">Un manager est celui qui <strong>encadre, coordonne et dirige</strong> les activités d'une organisation, tout en contribuant à la productivité ET à l'épanouissement de ses collaborateurs.</div>
    <div class="grid-3">
      <div class="box-item" style="background:var(--blue-pale);border:1px solid var(--blue-light)">
        <div class="box-label" style="color:var(--blue)">🔬 L'EXPERT</div>
        <div class="box-sub">Spécialiste de son domaine. Maîtrise technique approfondie. Référence dans sa discipline.</div>
      </div>
      <div class="box-item" style="background:var(--green-pale);border:1px solid var(--green-light)">
        <div class="box-label" style="color:var(--green)">👥 LE LEADER</div>
        <div class="box-sub">Exerce des responsabilités. Crée l'adhésion. Mobilise et fédère les équipes autour d'un projet.</div>
      </div>
      <div class="box-item" style="background:var(--purple-pale);border:1px solid var(--purple-light)">
        <div class="box-label" style="color:var(--purple)">🧭 LE STRATÈGE</div>
        <div class="box-sub">Oriente l'organisation en fixant le cap à long terme. Vision globale et anticipation.</div>
      </div>
    </div>
    <p style="margin-top:14px; font-weight:700; font-size:0.9rem;">Les 4 qualités d'un bon leader :</p>
    <ul class="fiche">
      <li><strong>Être visionnaire</strong> — anticiper, définir une direction claire et inspirante</li>
      <li><strong>Créer l'adhésion</strong> — fédérer les équipes autour d'un projet commun</li>
      <li><strong>Gérer son pouvoir</strong> — exercer son autorité sans en abuser</li>
      <li><strong>Gérer le savoir</strong> — capitaliser les compétences et les connaissances de l'équipe</li>
    </ul>
  </div>

  <div class="card purple">
    <div class="card-title"><span class="num" style="background:var(--purple-mid)">3</span> L'organisation — Structure de Mintzberg</div>
    <div class="def-box purple">L'organisation est un ensemble de personnes rassemblées selon une <strong>structure</strong> afin d'atteindre des <strong>objectifs</strong>, par une division du travail et des fonctions, grâce à des modalités de <strong>coordination</strong> définies.</div>
    <div class="schema-wrap">
      <div class="schema-label">Schéma — Les 5 composantes de H. Mintzberg</div>
      <div class="mintz">
        <div class="mintz-side" style="background:var(--blue-light);color:var(--blue)">
          TECHNO-STRUCTURE
          <div class="mintz-sub">Analyse, normes, planification des procédés. Ne produit pas directement.</div>
        </div>
        <div class="mintz-center">
          <div class="mintz-box" style="background:var(--blue);color:white">
            SOMMET STRATÉGIQUE
            <div style="font-weight:400;font-size:0.78rem;margin-top:5px;opacity:0.88">Direction générale — décisions à long terme</div>
          </div>
          <div class="mintz-box" style="background:var(--blue-mid);color:white">
            LIGNE HIÉRARCHIQUE
            <div style="font-weight:400;font-size:0.78rem;margin-top:5px;opacity:0.88">Cadres intermédiaires — transmission des décisions</div>
          </div>
          <div class="mintz-box" style="background:var(--green-light);color:var(--green)">
            CENTRE OPÉRATIONNEL
            <div style="font-weight:400;font-size:0.78rem;margin-top:5px;opacity:0.88">Réalisation du travail de base (production de biens et services)</div>
          </div>
        </div>
        <div class="mintz-side" style="background:var(--blue-light);color:var(--blue)">
          SUPPORT LOGISTIQUE
          <div class="mintz-sub">Services de soutien : RH, comptabilité, informatique, restauration…</div>
        </div>
      </div>
    </div>
    <div class="warn-box">
      <span>⚠</span>
      <div>Question piège : la technostructure <strong>planifie et normalise</strong> mais ne produit pas. Le support logistique <strong>soutient</strong> mais n'est pas hiérarchique. Ne pas confondre ces deux composantes !</div>
    </div>
  </div>

  <div class="card orange">
    <div class="card-title"><span class="num" style="background:var(--orange-mid)">4</span> La stratégie — Caractéristiques des décisions stratégiques</div>
    <div class="def-box orange">La stratégie consiste en une <strong>allocation de ressources</strong> qui engage l'organisation dans le long terme, en configurant son périmètre d'activité, avec pour objectif l'obtention d'un <strong>avantage concurrentiel</strong> et la création de valeur.</div>
    <div class="grid-2">
      <div>
        <p style="font-weight:700;margin-bottom:8px;">4 caractéristiques des décisions stratégiques :</p>
        <ul class="fiche">
          <li>Intrinsèquement <strong>complexes</strong></li>
          <li>Élaborées en situation d'<strong>incertitude</strong></li>
          <li>Nécessitent une approche <strong>globale</strong></li>
          <li>Peuvent impliquer des changements <strong>organisationnels et culturels</strong></li>
        </ul>
      </div>
      <div style="background:var(--orange-pale);border-radius:8px;padding:16px">
        <p style="font-weight:700;margin-bottom:8px;color:var(--orange)">Stratégie ≠ Tactique</p>
        <p style="font-size:0.85rem"><strong>Stratégie</strong> = long terme, vision globale, décision de la direction générale</p>
        <p style="font-size:0.85rem;margin-top:6px"><strong>Tactique</strong> = court terme, opérationnel, décision d'un service particulier</p>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════ CH2 ══ -->
<div id="ch2" class="section">
  <h2 class="section-title">Chapitre 2 — Les Théories du Management</h2>
  <p class="section-sub">École classique · École des relations humaines · Théories contemporaines</p>

  <div class="card">
    <div class="card-title"><span class="num">1</span> École Classique — Taylor, Ford, Fayol</div>
    <p style="margin-bottom:14px;font-size:0.9rem;color:var(--gray-mid)">Contexte : révolution industrielle (fin XIXe – début XXe siècle). Objectif : rationaliser le travail pour augmenter la productivité.</p>
    <table class="rtable">
      <tr>
        <th style="background:var(--blue);color:white">Auteur</th>
        <th style="background:var(--blue);color:white">Théorie</th>
        <th style="background:var(--blue);color:white">Principes essentiels</th>
        <th style="background:var(--blue);color:white">Limites</th>
      </tr>
      <tr>
        <td><strong>F.W. Taylor</strong><br><small style="color:var(--gray-mid)">1856–1915</small></td>
        <td><span class="badge badge-blue">OST</span><br>Organisation Scientifique du Travail</td>
        <td>• Division du travail (spécialisation)<br>• "One Best Way" — méthode optimale unique<br>• Rémunération à la pièce<br>• Contrôle avant, pendant et après</td>
        <td>• Limites <strong>sociales</strong> : déshumanisation, conflits<br>• Limites <strong>technologiques</strong> : machines remplacent l'humain<br>• Limites <strong>économiques</strong> : surproduction, crises</td>
      </tr>
      <tr>
        <td><strong>Henry Ford</strong><br><small style="color:var(--gray-mid)">1863–1947</small></td>
        <td><span class="badge badge-blue">Fordisme</span><br>Production de masse</td>
        <td>• Travail à la chaîne (produit qui se déplace)<br>• Standardisation (un seul modèle en série)<br>• Économies d'échelle</td>
        <td>• Aliénation des travailleurs<br>• Rigidité (un seul modèle)<br>• Crise de surproduction</td>
      </tr>
      <tr>
        <td><strong>Henri Fayol</strong><br><small style="color:var(--gray-mid)">1841–1925</small></td>
        <td><span class="badge badge-blue">Administration</span><br>14 principes d'administration</td>
        <td>• 14 principes (unité de commandement, discipline, autorité…)<br>• POCCC : Prévoir · Organiser · Commander · Coordonner · Contrôler<br>• Rationalité + Cohérence</td>
        <td>• Vision trop mécaniste<br>• Ignore les aspects humains<br>• Inadapté aux environnements complexes</td>
      </tr>
    </table>
    <div class="tip-box">
      <span class="icon">💡</span>
      <div><strong>Ne pas confondre :</strong> PODC (management moderne) ≠ POCCC (Fayol). Taylor = OST. Fayol = POCCC + 14 principes.</div>
    </div>
  </div>

  <div class="card green">
    <div class="card-title"><span class="num" style="background:var(--green-mid)">2</span> École des Relations Humaines — Mayo, Maslow, Lewin, McGregor</div>
    <div class="def-box green">Contexte : crise économique de 1929, limites de l'école classique. Ces théories démontrent que la <strong>dimension humaine et sociale</strong> est fondamentale pour la productivité.</div>

    <div class="card" style="border:1px solid var(--green-light);box-shadow:none;margin:14px 0;padding:18px">
      <p style="font-weight:700;color:var(--green);margin-bottom:10px">🔬 Elton Mayo (1880–1949) — L'expérience d'Hawthorne</p>
      <div class="grid-2">
        <div style="background:var(--orange-pale);padding:12px;border-radius:6px">
          <p style="font-weight:700;font-size:0.85rem;margin-bottom:6px">Résultat INATTENDU :</p>
          <p style="font-size:0.85rem">La productivité augmentait même quand les conditions de travail se dégradaient ! La raison : le <strong>sentiment d'être observé et valorisé</strong> motivait les ouvrières.</p>
        </div>
        <div style="background:var(--green-pale);padding:12px;border-radius:6px">
          <p style="font-weight:700;font-size:0.85rem;margin-bottom:6px">Conclusions (4) :</p>
          <ul class="fiche" style="margin:0">
            <li>Relations sociales > conditions physiques</li>
            <li>L'appartenance au groupe est capitale</li>
            <li>Motivation psychologique > motivation matérielle</li>
            <li>Salariés réagissent en groupe, pas individuellement</li>
          </ul>
        </div>
      </div>
    </div>

    <div class="card" style="border:1px solid var(--blue-light);box-shadow:none;margin:14px 0;padding:18px">
      <p style="font-weight:700;color:var(--blue);margin-bottom:12px">🔺 Abraham Maslow (1908–1970) — La Pyramide des Besoins</p>
      <div class="pyramid">
        <div class="pyramid-row" style="background:var(--purple);width:30%">
          <span class="level-num">5</span><span class="level-name">Accomplissement de soi</span>
          <span class="level-ex">— Créativité, réalisation</span>
        </div>
        <div class="pyramid-row" style="background:var(--blue);width:46%">
          <span class="level-num">4</span><span class="level-name">Estime et reconnaissance</span>
          <span class="level-ex">— Statut, confiance, respect</span>
        </div>
        <div class="pyramid-row" style="background:var(--green-mid);width:62%">
          <span class="level-num">3</span><span class="level-name">Besoins sociaux</span>
          <span class="level-ex">— Appartenance, amitié, amour</span>
        </div>
        <div class="pyramid-row" style="background:var(--orange-mid);width:78%">
          <span class="level-num">2</span><span class="level-name">Sécurité</span>
          <span class="level-ex">— Emploi, logement, retraite, assurance</span>
        </div>
        <div class="pyramid-row" style="background:var(--red-mid);width:94%">
          <span class="level-num">1</span><span class="level-name">Besoins physiologiques</span>
          <span class="level-ex">— Se nourrir, boire, dormir (besoins vitaux)</span>
        </div>
      </div>
      <div class="warn-box" style="margin-top:10px">
        <span>⚠</span><div>Processus <strong>assouvissement-progression</strong> = sens UNIQUE de bas en haut. Un besoin supérieur n'émerge que si le besoin inférieur est satisfait.</div>
      </div>
    </div>

    <div class="card" style="border:1px solid var(--orange-light);box-shadow:none;margin:14px 0;padding:18px">
      <p style="font-weight:700;color:var(--orange);margin-bottom:12px">🔀 Douglas McGregor (1906–1964) — Théorie X et Théorie Y</p>
      <div class="vs-wrap">
        <div class="vs-col" style="background:var(--red-pale);border:1px solid var(--red-light)">
          <div class="herz-title" style="color:var(--red)">❌ THÉORIE X</div>
          <ul class="fiche">
            <li>L'homme est <strong>paresseux</strong> par nature</li>
            <li>Il n'aime pas le travail, il le fuit</li>
            <li>Il préfère être <strong>dirigé</strong></li>
            <li>Il fuit les responsabilités</li>
            <li>→ Management : <strong>DIRECTIF</strong> (contrôle, surveillance)</li>
          </ul>
        </div>
        <div class="vs-middle">VS</div>
        <div class="vs-col" style="background:var(--green-pale);border:1px solid var(--green-light)">
          <div class="herz-title" style="color:var(--green)">✅ THÉORIE Y</div>
          <ul class="fiche">
            <li>L'homme peut <strong>aimer le travail</strong></li>
            <li>Il est capable de se diriger lui-même</li>
            <li>Il cherche les <strong>responsabilités</strong></li>
            <li>Il souhaite se réaliser</li>
            <li>→ Management : <strong>PARTICIPATIF / DÉLÉGATIF</strong></li>
          </ul>
        </div>
      </div>
    </div>

    <div class="card" style="border:1px solid var(--teal-light);box-shadow:none;margin:14px 0;padding:18px">
      <p style="font-weight:700;color:var(--teal);margin-bottom:10px">👥 Kurt Lewin (1890–1947) — Dynamique de groupe & 3 styles de leadership</p>
      <div class="grid-3">
        <div style="background:var(--red-pale);border-radius:8px;padding:14px">
          <p style="font-weight:700;color:var(--red);margin-bottom:6px">Autoritaire</p>
          <p style="font-size:0.82rem">Dirige le groupe par les ordres. Décisions unilatérales. Ne consulte pas.</p>
        </div>
        <div style="background:var(--green-pale);border-radius:8px;padding:14px">
          <p style="font-weight:700;color:var(--green);margin-bottom:6px">Démocratique</p>
          <p style="font-size:0.82rem">S'insère dans le groupe. Fait participer les membres aux décisions. Consultatif.</p>
        </div>
        <div style="background:var(--blue-pale);border-radius:8px;padding:14px">
          <p style="font-weight:700;color:var(--blue);margin-bottom:6px">Laisser-faire</p>
          <p style="font-size:0.82rem">Ne s'implique pas émotionnellement. Participe avec ses connaissances uniquement.</p>
        </div>
      </div>
    </div>
  </div>

  <div class="card teal">
    <div class="card-title"><span class="num" style="background:var(--teal-mid)">3</span> Théories Contemporaines — Simon et École Systémique</div>
    <div class="grid-2">
      <div>
        <p style="font-weight:700;color:var(--teal);margin-bottom:8px">Herbert Simon — Prise de décision</p>
        <table class="rtable">
          <tr>
            <th style="background:var(--green-mid);color:white">Décision PROGRAMMÉE</th>
            <th style="background:var(--red-mid);color:white">Décision NON PROGRAMMÉE</th>
          </tr>
          <tr>
            <td style="background:var(--green-pale)">Problème simple, familier<br>Information complète<br><em>Ex : commandes courantes</em></td>
            <td style="background:var(--red-pale)">Problème inédit, inhabituel<br>Information incomplète<br><em>Ex : lancer un nouveau produit</em></td>
          </tr>
        </table>
        <p style="font-weight:700;margin:12px 0 6px;font-size:0.88rem">4 modes de décision :</p>
        <ul class="fiche">
          <li><strong>Autoritaire</strong> — le manager décide seul</li>
          <li><strong>Majoritaire</strong> — vote à la majorité</li>
          <li><strong>Minoritaire</strong> — une minorité décide</li>
          <li><strong>Unanimité</strong> — accord de tous</li>
        </ul>
      </div>
      <div>
        <p style="font-weight:700;color:var(--teal);margin-bottom:8px">École Systémique (Le Moigne, Melese)</p>
        <div class="process-flow">
          <div class="proc-step" style="background:var(--green-light)">
            <span class="proc-num">INPUT</span>
            <span class="proc-name" style="color:var(--green)">ENTRÉES</span>
            <span class="proc-sub">Ressources humaines, financières, matérielles</span>
          </div>
          <div class="proc-arrow">→</div>
          <div class="proc-step" style="background:var(--blue-light)">
            <span class="proc-num">PROCESS</span>
            <span class="proc-name" style="color:var(--blue)">TRANSFORMATION</span>
            <span class="proc-sub">Production, traitement des ressources</span>
          </div>
          <div class="proc-arrow">→</div>
          <div class="proc-step" style="background:var(--orange-light)">
            <span class="proc-num">OUTPUT</span>
            <span class="proc-name" style="color:var(--orange)">SORTIES</span>
            <span class="proc-sub">Produits, services, dividendes, emplois</span>
          </div>
        </div>
        <div class="def-box" style="margin-top:10px">L'entreprise est un <strong>système ouvert finalisé</strong> : elle échange avec son environnement (clients, fournisseurs, État, marché).</div>
      </div>
    </div>
  </div>

  <div class="card gold">
    <div class="card-title"><span class="num" style="background:var(--gold)">★</span> Tableau récapitulatif de tous les auteurs</div>
    <div class="author-grid">
      <div class="author-card" style="border-top:3px solid var(--blue)">
        <div class="author-name">F.W. Taylor</div>
        <div class="author-dates">1856–1915 · Classique</div>
        <div class="author-theory">OST — Organisation Scientifique</div>
        <div class="author-keys">Division du travail · One Best Way · Rémunération à la pièce · Contrôle en 3 étapes</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--blue-mid)">
        <div class="author-name">Henry Ford</div>
        <div class="author-dates">1863–1947 · Classique</div>
        <div class="author-theory">Fordisme</div>
        <div class="author-keys">Travail à la chaîne · Standardisation · Économies d'échelle</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--teal-mid)">
        <div class="author-name">Henri Fayol</div>
        <div class="author-dates">1841–1925 · Classique</div>
        <div class="author-theory">14 principes · POCCC</div>
        <div class="author-keys">Prévoir · Organiser · Commander · Coordonner · Contrôler</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--green-mid)">
        <div class="author-name">Elton Mayo</div>
        <div class="author-dates">1880–1949 · Relations Humaines</div>
        <div class="author-theory">Expérience d'Hawthorne</div>
        <div class="author-keys">Relations sociales > conditions physiques · Groupe · Motivation psychologique</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--purple-mid)">
        <div class="author-name">Abraham Maslow</div>
        <div class="author-dates">1908–1970 · Relations Humaines</div>
        <div class="author-theory">Pyramide des besoins (5 niveaux)</div>
        <div class="author-keys">Assouvissement-progression · Sens unique ascendant</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--orange-mid)">
        <div class="author-name">D. McGregor</div>
        <div class="author-dates">1906–1964 · Relations Humaines</div>
        <div class="author-theory">Théorie X et Théorie Y</div>
        <div class="author-keys">X → directif · Y → participatif</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--red-mid)">
        <div class="author-name">Kurt Lewin</div>
        <div class="author-dates">1890–1947 · Relations Humaines</div>
        <div class="author-theory">Dynamique de groupe</div>
        <div class="author-keys">Autoritaire · Démocratique · Laisser-faire</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--gray-mid)">
        <div class="author-name">Herbert Simon</div>
        <div class="author-dates">Contemporaine</div>
        <div class="author-theory">Prise de décision</div>
        <div class="author-keys">Programmée vs non programmée · 4 modes de décision</div>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════ CH3 ══ -->
<div id="ch3" class="section">
  <h2 class="section-title">Chapitre 3 — La Motivation dans le Travail</h2>
  <p class="section-sub">Maslow · Alderfer · McClelland · Herzberg</p>

  <div class="card">
    <div class="card-title"><span class="num">1</span> Définition et processus de la motivation</div>
    <div class="def-box">La motivation est une <strong>prédisposition à agir</strong> d'une façon orientée vers un <strong>objectif spécifique</strong>. <em>(D. Hellriegel et J. Slocum)</em></div>
    <div class="schema-wrap">
      <div class="schema-label">Schéma — Le processus de motivation</div>
      <div class="process-flow">
        <div class="proc-step" style="background:var(--red-light)">
          <span class="proc-name" style="color:var(--red)">BESOIN / DÉSIR</span>
          <span class="proc-sub">Point de départ de la motivation</span>
        </div>
        <div class="proc-arrow">→</div>
        <div class="proc-step" style="background:var(--orange-light)">
          <span class="proc-name" style="color:var(--orange)">DYNAMISME</span>
          <span class="proc-sub">Énergie qui pousse à agir</span>
        </div>
        <div class="proc-arrow">→</div>
        <div class="proc-step" style="background:var(--blue-light)">
          <span class="proc-name" style="color:var(--blue)">COMPORTEMENT</span>
          <span class="proc-sub">Actions orientées vers…</span>
        </div>
        <div class="proc-arrow">→</div>
        <div class="proc-step" style="background:var(--purple-light)">
          <span class="proc-name" style="color:var(--purple)">OBJECTIFS</span>
          <span class="proc-sub">Buts visés</span>
        </div>
        <div class="proc-arrow">→</div>
        <div class="proc-step" style="background:var(--green-light)">
          <span class="proc-name" style="color:var(--green)">SATISFACTION</span>
          <span class="proc-sub">Récompense, réussite</span>
        </div>
      </div>
    </div>
  </div>

  <div class="card green">
    <div class="card-title"><span class="num" style="background:var(--green-mid)">2</span> Maslow vs Alderfer — Comparaison fondamentale</div>
    <div class="vs-wrap">
      <div class="vs-col" style="background:var(--blue-pale);border:1px solid var(--blue-light)">
        <p style="font-weight:700;color:var(--blue);font-size:1rem;margin-bottom:10px">MASLOW — 5 niveaux</p>
        <div class="pyramid" style="margin:0">
          <div class="pyramid-row" style="background:var(--purple);width:100%;font-size:0.78rem"><span class="level-num">5</span><span class="level-name">Accomplissement</span></div>
          <div class="pyramid-row" style="background:var(--blue);width:100%;font-size:0.78rem"><span class="level-num">4</span><span class="level-name">Estime</span></div>
          <div class="pyramid-row" style="background:var(--green-mid);width:100%;font-size:0.78rem"><span class="level-num">3</span><span class="level-name">Sociaux</span></div>
          <div class="pyramid-row" style="background:var(--orange-mid);width:100%;font-size:0.78rem"><span class="level-num">2</span><span class="level-name">Sécurité</span></div>
          <div class="pyramid-row" style="background:var(--red-mid);width:100%;font-size:0.78rem"><span class="level-num">1</span><span class="level-name">Physiologiques</span></div>
        </div>
        <p style="font-size:0.82rem;margin-top:10px;color:var(--blue);text-align:center;font-weight:600">↑ SENS UNIQUE (ascendant) ↑<br><em>Assouvissement-Progression</em></p>
      </div>
      <div class="vs-middle">VS</div>
      <div class="vs-col" style="background:var(--orange-pale);border:1px solid var(--orange-light)">
        <p style="font-weight:700;color:var(--orange);font-size:1rem;margin-bottom:10px">ALDERFER — 3 catégories (SRP)</p>
        <div class="grid-3" style="gap:8px;margin:0">
          <div style="background:var(--red-light);border-radius:6px;padding:12px;text-align:center">
            <p style="font-weight:700;color:var(--red);font-size:0.9rem">S</p>
            <p style="font-size:0.78rem"><strong>Subsistance</strong><br>Besoins physio. + sécurité</p>
          </div>
          <div style="background:var(--blue-light);border-radius:6px;padding:12px;text-align:center">
            <p style="font-weight:700;color:var(--blue);font-size:0.9rem">R</p>
            <p style="font-size:0.78rem"><strong>Relations</strong><br>Besoins sociaux + estime</p>
          </div>
          <div style="background:var(--purple-light);border-radius:6px;padding:12px;text-align:center">
            <p style="font-weight:700;color:var(--purple);font-size:0.9rem">P</p>
            <p style="font-size:0.78rem"><strong>Progression</strong><br>Accomplissement</p>
          </div>
        </div>
        <p style="font-size:0.82rem;margin-top:12px;color:var(--orange);text-align:center;font-weight:600">↑↓ DOUBLE SENS ↑↓<br><em>Frustration-Régression</em></p>
        <p style="font-size:0.8rem;margin-top:6px;text-align:center;color:var(--gray-mid)">Si un besoin supérieur est frustré, on peut <strong>régresser</strong> au niveau inférieur</p>
      </div>
    </div>
    <div class="warn-box" style="margin-top:14px">
      <span>⚠</span><div><strong>Différence clé à l'examen :</strong> Maslow = sens unique ascendant / Alderfer = peut régresser si frustration. C'est la question la plus fréquente sur ces deux théories !</div>
    </div>
  </div>

  <div class="card orange">
    <div class="card-title"><span class="num" style="background:var(--orange-mid)">3</span> McClelland — Motivation par l'accomplissement</div>
    <div class="def-box orange">La motivation est proportionnelle à la force du désir d'accomplir une tâche en fonction d'un <strong>modèle d'excellence</strong> ou de l'emporter sur ses concurrents.</div>
    <div class="grid-3">
      <div class="box-item" style="background:var(--orange-pale);border:2px solid var(--orange-light)">
        <div class="box-label" style="color:var(--orange)">🏆 Accomplissement</div>
        <div class="box-sub">Réaliser des tâches difficiles, se surpasser, atteindre l'excellence</div>
      </div>
      <div class="box-item" style="background:var(--blue-pale);border:2px solid var(--blue-light)">
        <div class="box-label" style="color:var(--blue)">🤝 Appartenance</div>
        <div class="box-sub">Être intégré dans un groupe, être apprécié, maintenir des relations chaleureuses</div>
      </div>
      <div class="box-item" style="background:var(--purple-pale);border:2px solid var(--purple-light)">
        <div class="box-label" style="color:var(--purple)">👑 Pouvoir</div>
        <div class="box-sub">Influencer, diriger, contrôler les autres, avoir de l'impact</div>
      </div>
    </div>
    <p style="margin-top:14px;font-size:0.88rem"><strong>Mesure :</strong> Test d'Aperception Thématique (TAP) — présenter des images non structurées pour analyser les perceptions et motivations profondes de l'individu.</p>
  </div>

  <div class="card purple">
    <div class="card-title"><span class="num" style="background:var(--purple-mid)">4</span> Herzberg — Motivation et Hygiène</div>
    <div class="def-box purple">Herzberg identifie <strong>2 séries de facteurs</strong> qui affectent les sentiments des salariés envers leur travail : les facteurs de motivation (intrinsèques) et les facteurs d'hygiène (extrinsèques).</div>
    <div class="herzberg">
      <div class="herz-col" style="background:var(--green-pale);border:2px solid var(--green-light)">
        <div class="herz-title" style="color:var(--green)">✅ Facteurs de MOTIVATION (Intrinsèques)</div>
        <div class="herz-sub" style="color:var(--green)">→ Créent de la SATISFACTION<br>→ Motivent vraiment !</div>
        <ul class="fiche">
          <li>Le travail lui-même</li>
          <li>La considération / reconnaissance</li>
          <li>La responsabilité confiée</li>
          <li>L'avancement / promotion</li>
          <li>La réalisation personnelle</li>
        </ul>
        <div style="background:var(--green-light);border-radius:6px;padding:8px;margin-top:10px;font-size:0.82rem;text-align:center;font-weight:700;color:var(--green)">
          Améliorer → MOTIVE vraiment
        </div>
      </div>
      <div class="herz-col" style="background:var(--blue-pale);border:2px solid var(--blue-light)">
        <div class="herz-title" style="color:var(--blue)">⚠ Facteurs d'HYGIÈNE (Extrinsèques)</div>
        <div class="herz-sub" style="color:var(--blue)">→ Évitent l'INSATISFACTION<br>→ Ne motivent pas seuls !</div>
        <ul class="fiche">
          <li>Politique de l'entreprise</li>
          <li>Modalités de supervision</li>
          <li>Rémunération (salaire)</li>
          <li>Relations interpersonnelles</li>
          <li>Conditions de travail physiques</li>
        </ul>
        <div style="background:var(--blue-light);border-radius:6px;padding:8px;margin-top:10px;font-size:0.82rem;text-align:center;font-weight:700;color:var(--blue)">
          Améliorer → réduit mécontentement seulement
        </div>
      </div>
    </div>
    <div class="tip-box">
      <span class="icon">💡</span>
      <div><strong>Règle d'or de Herzberg :</strong> Augmenter le salaire (facteur d'hygiène) ne motive pas — cela réduit seulement le mécontentement. Seuls la responsabilité, la reconnaissance et l'enrichissement du travail créent une vraie motivation durable.</div>
    </div>
  </div>

  <div class="card gold">
    <div class="card-title"><span class="num" style="background:var(--gold)">★</span> Tableau comparatif des 4 théories de motivation</div>
    <table class="rtable">
      <tr>
        <th style="background:var(--gray);color:white">Critère</th>
        <th style="background:var(--purple);color:white">Maslow</th>
        <th style="background:var(--orange-mid);color:white">Alderfer</th>
        <th style="background:var(--blue-mid);color:white">McClelland</th>
        <th style="background:var(--green-mid);color:white">Herzberg</th>
      </tr>
      <tr>
        <td><strong>Niveaux</strong></td>
        <td>5 niveaux hiérarchiques</td>
        <td>3 catégories (SRP)</td>
        <td>3 besoins distincts</td>
        <td>2 types de facteurs</td>
      </tr>
      <tr>
        <td><strong>Logique</strong></td>
        <td>Assouvissement-progression<br><em>(sens unique ↑)</em></td>
        <td>Frustration-régression<br><em>(double sens ↑↓)</em></td>
        <td>Désir proportionnel à force du besoin</td>
        <td>Intrinsèques vs extrinsèques</td>
      </tr>
      <tr>
        <td><strong>Application</strong></td>
        <td>GRH, pyramide des besoins clients, marketing</td>
        <td>Plus flexible en pratique</td>
        <td>Profil motivationnel (test TAP)</td>
        <td>Job design, enrichissement des tâches</td>
      </tr>
    </table>
  </div>
</div>

<!-- ══════════════════════════════════════════ CH4 ══ -->
<div id="ch4" class="section">
  <h2 class="section-title">Chapitre 4 — Les Styles de Management</h2>
  <p class="section-sub">Selon Rensis Likert · Directif · Délégatif · Participatif · Persuasif</p>

  <div class="card">
    <div class="card-title"><span class="num">1</span> Introduction — Rensis Likert</div>
    <div class="def-box">Selon <strong>Rensis Likert</strong>, psychologue américain, on peut distinguer <strong>4 grands types de management</strong> : directif, délégatif, participatif et persuasif. Chacun correspond à une manière différente d'exercer l'autorité, de prendre des décisions et de motiver les équipes.</div>
  </div>

  <div class="card orange">
    <div class="card-title"><span class="num" style="background:var(--orange-mid)">2</span> Les 4 styles — Vue d'ensemble</div>
    <div class="style-grid">
      <div class="style-card">
        <div class="style-header" style="background:var(--red-mid)">🎯 DIRECTIF (Autoritaire)</div>
        <div class="style-body">
          <div class="label">Décision</div>
          <p>Prise par le manager seul (top-down). Décisions rapides.</p>
          <div class="label">Communication</div>
          <p>Descendante, unidirectionnelle</p>
          <div class="label">Confiance</div>
          <p>Faible envers les collaborateurs</p>
          <div class="label">Contexte idéal</div>
          <p>🚨 Urgences, crises, personnel peu qualifié</p>
          <div class="label">Objectif</div>
          <p>Productivité rapide et concrète</p>
        </div>
      </div>
      <div class="style-card">
        <div class="style-header" style="background:var(--blue-mid)">🔑 DÉLÉGATIF (Consultatif)</div>
        <div class="style-body">
          <div class="label">Décision</div>
          <p>Prise par les collaborateurs (très autonomes)</p>
          <div class="label">Communication</div>
          <p>Peu de retours, délégation forte</p>
          <div class="label">Confiance</div>
          <p>Très forte envers les collaborateurs</p>
          <div class="label">Contexte idéal</div>
          <p>👨‍💼 Équipe expérimentée et de confiance</p>
          <div class="label">Objectif</div>
          <p>Responsabilisation, autonomisation</p>
        </div>
      </div>
      <div class="style-card">
        <div class="style-header" style="background:var(--green-mid)">🤝 PARTICIPATIF (Horizontal)</div>
        <div class="style-body">
          <div class="label">Décision</div>
          <p>Collective (vote, débat, consensus)</p>
          <div class="label">Communication</div>
          <p>Bi-directionnelle, horizontale</p>
          <div class="label">Confiance</div>
          <p>Forte, relation de proximité</p>
          <div class="label">Contexte idéal</div>
          <p>🧠 Problèmes complexes nécessitant créativité</p>
          <div class="label">Objectif</div>
          <p>Intelligence collective, cohésion</p>
        </div>
      </div>
      <div class="style-card">
        <div class="style-header" style="background:var(--orange-mid)">💬 PERSUASIF (Paternaliste)</div>
        <div class="style-body">
          <div class="label">Décision</div>
          <p>Manager + persuasion, explique ses choix</p>
          <div class="label">Communication</div>
          <p>Descendante + pédagogie et explications</p>
          <div class="label">Confiance</div>
          <p>Modérée, en construction</p>
          <div class="label">Contexte idéal</div>
          <p>📚 Équipes à former, adhésion à construire</p>
          <div class="label">Objectif</div>
          <p>Adhésion, motivation, empowerment progressif</p>
        </div>
      </div>
    </div>
  </div>

  <div class="card green">
    <div class="card-title"><span class="num" style="background:var(--green-mid)">3</span> Le Management Participatif — Les 5C</div>
    <div class="def-box green">Le management participatif place l'<strong>humain au centre</strong>. Le manager joue le rôle de <strong>coach et de guide</strong>. Il s'appuie sur l'intelligence collective à travers les 5C.</div>
    <div class="grid-5">
      <div class="box-item" style="background:var(--green-pale);border:2px solid var(--green-light)">
        <div class="box-label" style="color:var(--green);font-size:1.2rem">💬</div>
        <div class="box-label" style="color:var(--green)">Communication</div>
        <div class="box-sub">Échange ouvert, transparence, feedback régulier</div>
      </div>
      <div class="box-item" style="background:var(--blue-pale);border:2px solid var(--blue-light)">
        <div class="box-label" style="color:var(--blue);font-size:1.2rem">🤝</div>
        <div class="box-label" style="color:var(--blue)">Collaboration</div>
        <div class="box-sub">Mise en commun des compétences et des ressources</div>
      </div>
      <div class="box-item" style="background:var(--orange-pale);border:2px solid var(--orange-light)">
        <div class="box-label" style="color:var(--orange);font-size:1.2rem">💡</div>
        <div class="box-label" style="color:var(--orange)">Créativité</div>
        <div class="box-sub">Encourager l'innovation et les nouvelles idées</div>
      </div>
      <div class="box-item" style="background:var(--purple-pale);border:2px solid var(--purple-light)">
        <div class="box-label" style="color:var(--purple);font-size:1.2rem">🧠</div>
        <div class="box-label" style="color:var(--purple)">Collective</div>
        <div class="box-sub">Réflexion approfondie, décision par le groupe</div>
      </div>
      <div class="box-item" style="background:var(--red-pale);border:2px solid var(--red-light)">
        <div class="box-label" style="color:var(--red);font-size:1.2rem">❤️</div>
        <div class="box-label" style="color:var(--red)">Compassion</div>
        <div class="box-sub">Entraide, écoute active, bienveillance</div>
      </div>
    </div>
  </div>

  <div class="card purple">
    <div class="card-title"><span class="num" style="background:var(--purple-mid)">4</span> Avantages, Inconvénients et Compétences</div>
    <table class="rtable">
      <tr>
        <th style="background:var(--gray);color:white">Style</th>
        <th style="background:var(--green-mid);color:white">✅ Avantages</th>
        <th style="background:var(--red-mid);color:white">❌ Inconvénients</th>
        <th style="background:var(--blue-mid);color:white">🎓 Compétences requises</th>
      </tr>
      <tr>
        <td style="background:var(--red-pale);font-weight:700">Directif</td>
        <td>Décision rapide · Forte productivité à court terme · Clair</td>
        <td>Démotivation · Conflits sociaux · Créativité nulle</td>
        <td>Expertise technique · Charisme · Autorité naturelle</td>
      </tr>
      <tr>
        <td style="background:var(--blue-pale);font-weight:700">Délégatif</td>
        <td>Motivation accrue · Responsabilisation · Innovation</td>
        <td>Perte de contrôle · Problème de communication · Risque de dérive</td>
        <td>Expérience · Intuition · Capacité à lâcher prise</td>
      </tr>
      <tr>
        <td style="background:var(--green-pale);font-weight:700">Participatif</td>
        <td>Cohésion · Appartenance · Créativité · Engagement fort</td>
        <td>Décisions lentes · Conflits internes · Difficile à mettre en place</td>
        <td>Intelligence émotionnelle · Facilitation · Empowerment</td>
      </tr>
      <tr>
        <td style="background:var(--orange-pale);font-weight:700">Persuasif</td>
        <td>Adhésion · Motivation · Empowerment progressif</td>
        <td>Complexe à maintenir · Risque de manipulation perçue</td>
        <td>Sens du relationnel · Pédagogie · Confiance en soi</td>
      </tr>
    </table>
    <div class="tip-box" style="margin-top:14px">
      <span class="icon">💡</span>
      <div><strong>Pour un cas pratique :</strong> 1) Lisez le texte attentivement 2) Repérez les indices (qui décide ? comment ? contrôle ?) 3) Nommez le style 4) Justifiez avec 2 caractéristiques du cours 5) Dites dans quel contexte il est adapté.</div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════ CH5 ══ -->
<div id="ch5" class="section">
  <h2 class="section-title">Chapitre 5 — Les Stratégies des Organisations</h2>
  <p class="section-sub">Diversification · Différenciation · Focalisation · Internationalisation</p>

  <div class="card">
    <div class="card-title"><span class="num">1</span> Démarche stratégique — Schéma en 5 étapes</div>
    <div class="def-box">Les stratégies des organisations sont l'ensemble des <strong>décisions et actions planifiées</strong> pour atteindre des objectifs à long terme, en tenant compte de l'environnement interne et externe.</div>
    <div class="schema-wrap">
      <div class="schema-label">Schéma — Le processus de la démarche stratégique</div>
      <div class="process-flow">
        <div class="proc-step" style="background:var(--blue-light)">
          <span class="proc-num">Étape 1</span>
          <span class="proc-name" style="color:var(--blue)">ANALYSE</span>
          <span class="proc-sub">SWOT : Forces / Faiblesses / Opportunités / Menaces</span>
        </div>
        <div class="proc-arrow">→</div>
        <div class="proc-step" style="background:var(--purple-light)">
          <span class="proc-num">Étape 2</span>
          <span class="proc-name" style="color:var(--purple)">VISION</span>
          <span class="proc-sub">Définir objectifs et l'écart stratégique</span>
        </div>
        <div class="proc-arrow">→</div>
        <div class="proc-step" style="background:var(--orange-light)">
          <span class="proc-num">Étape 3</span>
          <span class="proc-name" style="color:var(--orange)">DÉCISION</span>
          <span class="proc-sub">Choisir la stratégie adaptée</span>
        </div>
        <div class="proc-arrow">→</div>
        <div class="proc-step" style="background:var(--green-light)">
          <span class="proc-num">Étape 4</span>
          <span class="proc-name" style="color:var(--green)">PLAN</span>
          <span class="proc-sub">Budget, responsabilités, calendrier</span>
        </div>
        <div class="proc-arrow">→</div>
        <div class="proc-step" style="background:var(--teal-light)">
          <span class="proc-num">Étape 5</span>
          <span class="proc-name" style="color:var(--teal)">CONTRÔLE</span>
          <span class="proc-sub">Évaluation et correction des écarts</span>
        </div>
      </div>
    </div>
  </div>

  <div class="card green">
    <div class="card-title"><span class="num" style="background:var(--green-mid)">2</span> Les 4 stratégies génériques</div>
    <div class="strat-flow">
      <div class="strat-box">
        <div class="strat-head" style="background:var(--blue)">
          <h3>🔄 Diversification</h3>
          <p>Investir un nouveau DAS (Domaine d'Activité Stratégique)</p>
        </div>
        <div class="strat-body">
          <p class="tag" style="color:var(--blue)">Types :</p>
          <p>• Intégration (amont/aval/horizontale)<br>• Liée (synergies)<br>• Non liée (conglomérale)</p>
          <p class="tag" style="color:var(--green);margin-top:8px">Avantages :</p>
          <p>Répartition des risques · Nouvelles technologies · Synergies</p>
          <p class="tag" style="color:var(--red);margin-top:8px">Limites :</p>
          <p>Coûts élevés · Perte de focus sur le cœur de métier</p>
        </div>
      </div>
      <div class="strat-box">
        <div class="strat-head" style="background:var(--purple-mid)">
          <h3>💎 Différenciation</h3>
          <p>Offre unique perçue par le client</p>
        </div>
        <div class="strat-body">
          <p class="tag" style="color:var(--purple)">Types :</p>
          <p>• Par le produit<br>• Par le service<br>• Par le prix / rapport qualité<br>• Par l'innovation</p>
          <p class="tag" style="color:var(--green);margin-top:8px">Avantages :</p>
          <p>Fidélisation · Avantage durable · Prix premium justifié</p>
          <p class="tag" style="color:var(--red);margin-top:8px">Limites :</p>
          <p>Coûts élevés · Risque d'imitation</p>
        </div>
      </div>
      <div class="strat-box">
        <div class="strat-head" style="background:var(--orange-mid)">
          <h3>🎯 Focalisation (niche)</h3>
          <p>Segment précis du marché</p>
        </div>
        <div class="strat-body">
          <p class="tag" style="color:var(--orange)">Types :</p>
          <p>• Par les coûts (low-cost)<br>• Par la différenciation (luxe)</p>
          <p class="tag" style="color:var(--green);margin-top:8px">Avantages :</p>
          <p>Expertise de niche · Forte fidélité · Évite la concurrence directe</p>
          <p class="tag" style="color:var(--red);margin-top:8px">Limites :</p>
          <p>Marché limité · Dépendance à un segment</p>
        </div>
      </div>
      <div class="strat-box">
        <div class="strat-head" style="background:var(--teal-mid)">
          <h3>🌍 Internationalisation</h3>
          <p>Développer hors du marché national</p>
        </div>
        <div class="strat-body">
          <p class="tag" style="color:var(--teal)">Formes :</p>
          <p>• Exportation<br>• Franchise / Licence<br>• Joint-venture<br>• Filiale (investissement direct)</p>
          <p class="tag" style="color:var(--green);margin-top:8px">Avantages :</p>
          <p>Nouveaux marchés · Répartition géographique des risques</p>
          <p class="tag" style="color:var(--red);margin-top:8px">Limites :</p>
          <p>Coûts d'implantation · Risques politiques et culturels</p>
        </div>
      </div>
    </div>
  </div>

  <div class="card blue">
    <div class="card-title"><span class="num">3</span> Diversification — Schéma de l'Intégration</div>
    <div class="schema-wrap">
      <div class="schema-label">Les 3 types d'intégration (souvent demandé à l'examen)</div>
      <div class="integration-schema">
        <div class="int-row">
          <div class="int-box" style="background:var(--blue);color:white;max-width:200px">
            ⬆ FOURNISSEURS<br>
            <div style="font-weight:400;font-size:0.78rem;margin-top:4px">Matières premières · Composants · Production</div>
          </div>
        </div>
        <div class="int-arrow">⬆ Intégration Verticale AMONT ⬆</div>
        <div class="int-row">
          <div class="int-box" style="background:var(--blue-light);color:var(--blue);border:2px solid var(--blue-mid);max-width:400px">
            🏭 <strong>L'ENTREPRISE</strong><br>
            <div style="font-size:0.8rem;margin-top:4px">Activité principale / cœur de métier</div>
          </div>
        </div>
        <div class="int-arrow">⬇ Intégration Verticale AVAL ⬇</div>
        <div class="int-row">
          <div class="int-box" style="background:var(--green);color:white;max-width:200px">
            ⬇ DISTRIBUTION / SAV<br>
            <div style="font-weight:400;font-size:0.78rem;margin-top:4px">Clients · Points de vente · Service après-vente</div>
          </div>
        </div>
      </div>
      <div style="background:var(--teal-light);border-radius:8px;padding:14px;margin-top:12px;text-align:center">
        <p style="font-weight:700;color:var(--teal);margin-bottom:6px">↔ Intégration HORIZONTALE ↔</p>
        <p style="font-size:0.85rem">Se positionner sur des activités concurrentes ou complémentaires au même niveau de la chaîne de valeur</p>
        <p style="font-size:0.8rem;margin-top:4px;color:var(--gray-mid);font-style:italic">Ex : une banque qui rachète une compagnie d'assurance</p>
      </div>
    </div>
    <div class="grid-3" style="margin-top:16px">
      <div style="background:var(--blue-pale);border-radius:8px;padding:14px">
        <p style="font-weight:700;color:var(--blue);margin-bottom:6px">Amont — Exemple</p>
        <p style="font-size:0.82rem">Apple qui fabrique ses propres puces (M1, M2) au lieu d'acheter à Intel ou Qualcomm</p>
      </div>
      <div style="background:var(--green-pale);border-radius:8px;padding:14px">
        <p style="font-weight:700;color:var(--green);margin-bottom:6px">Aval — Exemple</p>
        <p style="font-size:0.82rem">Un fabricant de vêtements qui ouvre ses propres boutiques de distribution (Zara, H&M)</p>
      </div>
      <div style="background:var(--teal-light);border-radius:8px;padding:14px">
        <p style="font-weight:700;color:var(--teal);margin-bottom:6px">Horizontale — Exemple</p>
        <p style="font-size:0.82rem">Une banque qui rachète une compagnie d'assurance (même clientèle, activités complémentaires)</p>
      </div>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════ SYNTHESE ══ -->
<div id="synthese" class="section">
  <h2 class="section-title">🎯 Synthèse Examen</h2>
  <p class="section-sub">Méthode · Acronymes · Questions types · Auteurs essentiels</p>

  <div class="card" style="border-left-color:var(--gold)">
    <div class="card-title"><span class="num" style="background:var(--gold)">✓</span> Les 5 règles d'or pour l'examen</div>
    <div class="grid-2">
      <ul class="fiche">
        <li><strong>Règle 1 :</strong> Toujours commencer par une DÉFINITION précise (apprise par cœur)</li>
        <li><strong>Règle 2 :</strong> Associer chaque concept à son AUTEUR — c'est systématiquement noté</li>
        <li><strong>Règle 3 :</strong> Maîtriser tous les ACRONYMES (PODC, POCCC, 5C, SRP, TAP)</li>
        <li><strong>Règle 4 :</strong> Savoir différencier les théories SIMILAIRES (Maslow vs Alderfer, X vs Y)</li>
        <li><strong>Règle 5 :</strong> Pour les cas pratiques : identifier + justifier + contextualiser</li>
      </ul>
      <div style="background:var(--gold-light);border-radius:8px;padding:18px">
        <p style="font-weight:700;color:var(--gold);margin-bottom:10px">Structure universelle de réponse :</p>
        <div class="process-flow" style="flex-direction:column;gap:6px">
          <div style="background:var(--blue-light);border-radius:6px;padding:8px 12px;font-size:0.85rem"><strong>1.</strong> Définition précise du concept</div>
          <div style="font-size:0.9rem;text-align:center">↓</div>
          <div style="background:var(--green-light);border-radius:6px;padding:8px 12px;font-size:0.85rem"><strong>2.</strong> Points clés numérotés (liste structurée)</div>
          <div style="font-size:0.9rem;text-align:center">↓</div>
          <div style="background:var(--orange-light);border-radius:6px;padding:8px 12px;font-size:0.85rem"><strong>3.</strong> Exemple concret d'entreprise réelle</div>
          <div style="font-size:0.9rem;text-align:center">↓</div>
          <div style="background:var(--purple-light);border-radius:6px;padding:8px 12px;font-size:0.85rem"><strong>4.</strong> Critique ou limite (montre la profondeur)</div>
        </div>
      </div>
    </div>
  </div>

  <div class="card green">
    <div class="card-title"><span class="num" style="background:var(--green-mid)">A</span> Acronymes à mémoriser absolument</div>
    <table class="rtable">
      <tr>
        <th style="background:var(--blue);color:white">Acronyme</th>
        <th style="background:var(--blue);color:white">Signification complète</th>
        <th style="background:var(--blue);color:white">Auteur / Contexte</th>
      </tr>
      <tr><td style="font-family:var(--font-mono);font-weight:700;color:var(--blue)">PODC</td><td>Planification · Organisation · Direction · Contrôle</td><td>Management moderne — cycle de base</td></tr>
      <tr><td style="font-family:var(--font-mono);font-weight:700;color:var(--blue)">POCCC</td><td>Prévoir · Organiser · Commander · Coordonner · Contrôler</td><td>Henri Fayol — fonction administrative</td></tr>
      <tr><td style="font-family:var(--font-mono);font-weight:700;color:var(--blue)">4M</td><td>Humains · Matière · Machines · Monnaie</td><td>Ressources mobilisées par le manager</td></tr>
      <tr><td style="font-family:var(--font-mono);font-weight:700;color:var(--blue)">OST</td><td>Organisation Scientifique du Travail</td><td>F.W. Taylor</td></tr>
      <tr><td style="font-family:var(--font-mono);font-weight:700;color:var(--blue)">SRP</td><td>Subsistance · Relations · Progression</td><td>Clay Alderfer</td></tr>
      <tr><td style="font-family:var(--font-mono);font-weight:700;color:var(--blue)">TAP</td><td>Test d'Aperception Thématique</td><td>McClelland — mesure de la motivation</td></tr>
      <tr><td style="font-family:var(--font-mono);font-weight:700;color:var(--blue)">5C</td><td>Communication · Collaboration · Créativité · Collective · Compassion</td><td>Management participatif</td></tr>
      <tr><td style="font-family:var(--font-mono);font-weight:700;color:var(--blue)">DAS</td><td>Domaine d'Activité Stratégique</td><td>Stratégie de diversification</td></tr>
      <tr><td style="font-family:var(--font-mono);font-weight:700;color:var(--blue)">SWOT</td><td>Strengths · Weaknesses · Opportunities · Threats (Forces/Faiblesses/Opportunités/Menaces)</td><td>Analyse stratégique</td></tr>
    </table>
  </div>

  <div class="card orange">
    <div class="card-title"><span class="num" style="background:var(--orange-mid)">Q</span> Questions d'examen types avec réponse structurée</div>
    <table class="rtable">
      <tr>
        <th style="background:var(--orange-mid);color:white">Question</th>
        <th style="background:var(--orange-mid);color:white">Comment répondre</th>
      </tr>
      <tr>
        <td><em>"Définissez le management et expliquez le cycle PODC."</em></td>
        <td>Définition → 4 étapes détaillées (Planification/Organisation/Direction/Contrôle) → Schéma + exemple d'une entreprise réelle</td>
      </tr>
      <tr>
        <td><em>"Quels sont les apports et les limites de Taylor ?"</em></td>
        <td>Biographie + contexte → 4 principes OST (division du travail, one best way, rémunération à la pièce, contrôle en 3 étapes) → 3 limites (sociales, technologiques, économiques)</td>
      </tr>
      <tr>
        <td><em>"Expliquez la pyramide de Maslow et ses applications."</em></td>
        <td>Définition + auteur → Schéma des 5 niveaux (bas → haut) → Processus assouvissement-progression → Application en GRH → Comparaison avec Alderfer (distinction clé)</td>
      </tr>
      <tr>
        <td><em>"Comparez les 4 styles de management de Likert."</em></td>
        <td>Introduction Likert → Tableau comparatif des 4 styles (décision, communication, confiance, contexte) → Avantages et inconvénients de chacun → Votre recommandation argumentée selon le contexte</td>
      </tr>
      <tr>
        <td><em>"Quelle est la différence entre diversification liée et non liée ?"</em></td>
        <td>Définition diversification → Liée = synergies, même chaîne de valeur, 3 pivots (commercial, compétence, technologique) + exemples → Non liée = conglomérale, deux chaînes indépendantes + exemples → Avantages de chacune</td>
      </tr>
      <tr>
        <td><em>"Cas pratique : identifiez le style de management"</em></td>
        <td>1) Relevez les indices textuels 2) Nommez le style 3) Justifiez avec 2-3 caractéristiques du cours 4) Dites dans quel contexte il est recommandé et ses limites éventuelles</td>
      </tr>
    </table>
  </div>

  <div class="card purple">
    <div class="card-title"><span class="num" style="background:var(--purple-mid)">★</span> Tous les auteurs — Fiche mémo rapide</div>
    <div class="author-grid">
      <div class="author-card" style="border-top:3px solid var(--blue)">
        <div class="author-name" style="color:var(--blue)">F.W. Taylor</div>
        <div class="author-dates">1856–1915 | École Classique</div>
        <div class="author-theory">OST — Organisation Scientifique</div>
        <div class="author-keys">Division du travail · One Best Way · Rémunération à la pièce · Contrôle en 3 étapes</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--blue-mid)">
        <div class="author-name" style="color:var(--blue-mid)">Henry Ford</div>
        <div class="author-dates">1863–1947 | École Classique</div>
        <div class="author-theory">Fordisme — Production de masse</div>
        <div class="author-keys">Travail à la chaîne · Standardisation · Économies d'échelle</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--teal-mid)">
        <div class="author-name" style="color:var(--teal)">Henri Fayol</div>
        <div class="author-dates">1841–1925 | École Classique</div>
        <div class="author-theory">14 principes + POCCC</div>
        <div class="author-keys">Rationalité · Cohérence · Unité de commandement · Discipline</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--green-mid)">
        <div class="author-name" style="color:var(--green)">Elton Mayo</div>
        <div class="author-dates">1880–1949 | Relations Humaines</div>
        <div class="author-theory">Expérience d'Hawthorne</div>
        <div class="author-keys">Relations sociales > conditions physiques · Groupe · Motivation psychologique</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--purple-mid)">
        <div class="author-name" style="color:var(--purple)">Abraham Maslow</div>
        <div class="author-dates">1908–1970 | Relations Humaines</div>
        <div class="author-theory">Pyramide des 5 besoins</div>
        <div class="author-keys">Assouvissement-progression · Sens UNIQUE ascendant</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--red-mid)">
        <div class="author-name" style="color:var(--red)">D. McGregor</div>
        <div class="author-dates">1906–1964 | Relations Humaines</div>
        <div class="author-theory">Théorie X et Théorie Y</div>
        <div class="author-keys">X = paresseux → directif · Y = épanoui → participatif</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--orange-mid)">
        <div class="author-name" style="color:var(--orange)">Frederick Herzberg</div>
        <div class="author-dates">Motivation</div>
        <div class="author-theory">Motivation vs Hygiène</div>
        <div class="author-keys">Intrinsèques (motivent) vs Extrinsèques (évitent mécontentement)</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--orange)">
        <div class="author-name" style="color:var(--orange)">Clay Alderfer</div>
        <div class="author-dates">Relations Humaines</div>
        <div class="author-theory">Théorie SRP</div>
        <div class="author-keys">Subsistance · Relations · Progression · Frustration-Régression (double sens)</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--blue-mid)">
        <div class="author-name" style="color:var(--blue-mid)">D. McClelland</div>
        <div class="author-dates">Motivation</div>
        <div class="author-theory">Motivation par l'accomplissement</div>
        <div class="author-keys">Accomplissement · Appartenance · Pouvoir · Test TAP</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--gray-mid)">
        <div class="author-name" style="color:var(--gray)">Herbert Simon</div>
        <div class="author-dates">École Contemporaine</div>
        <div class="author-theory">Prise de décision</div>
        <div class="author-keys">Programmée vs Non programmée · 4 modes · 3 raisons de décider</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--green)">
        <div class="author-name" style="color:var(--green)">Rensis Likert</div>
        <div class="author-dates">Management</div>
        <div class="author-theory">4 styles de management</div>
        <div class="author-keys">Directif · Délégatif · Participatif · Persuasif</div>
      </div>
      <div class="author-card" style="border-top:3px solid var(--purple)">
        <div class="author-name" style="color:var(--purple)">H. Mintzberg</div>
        <div class="author-dates">Organisation</div>
        <div class="author-theory">Structure en 5 parties</div>
        <div class="author-keys">Sommet stratégique · Ligne hiérarchique · Centre opérationnel · Technostructure · Support logistique</div>
      </div>
    </div>
  </div>
</div>

</div><!-- end page-wrap -->

<script>
function showTab(id, btn) {
  document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  document.querySelectorAll('.pill').forEach(b => b.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  if (btn) {
    btn.classList.add('active');
    // Also activate corresponding tab-btn or pill
    const allBtns = document.querySelectorAll('.tab-btn, .pill');
    allBtns.forEach(b => {
      if (b !== btn && b.getAttribute('onclick') === btn.getAttribute('onclick')) {
        b.classList.add('active');
      }
    });
  }
  window.scrollTo({ top: 0, behavior: 'smooth' });
}
</script>
</body>
</html>
