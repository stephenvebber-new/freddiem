<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Freddie Mac — Opportunity Briefing</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,600;0,700;1,600&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --navy: #0d1f3c;
    --navy-mid: #162d54;
    --navy-light: #1e3f70;
    --gold: #c8973a;
    --gold-light: #e8b86d;
    --gold-pale: #fdf6e8;
    --cream: #f7f4ef;
    --cream-dark: #ece7de;
    --white: #ffffff;
    --text-dark: #0d1f3c;
    --text-mid: #3a4d6a;
    --text-light: #7a8faa;
    --green: #1a6e42;
    --green-pale: #eaf5f0;
    --amber: #8a5500;
    --amber-pale: #fdf6e8;
    --blue: #1a5aad;
    --blue-pale: #eef4fc;
    --border: rgba(13,31,60,0.1);
    --shadow: 0 1px 3px rgba(13,31,60,0.06), 0 4px 12px rgba(13,31,60,0.04);
  }
  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body { font-family: 'Inter', sans-serif; background: var(--cream); color: var(--text-dark); font-size: 14px; line-height: 1.6; }

  /* HEADER */
  .site-header { background: var(--navy); border-bottom: 3px solid var(--gold); position: sticky; top: 0; z-index: 200; }
  .header-inner { max-width: 1180px; margin: 0 auto; padding: 0 36px; height: 62px; display: flex; align-items: center; justify-content: space-between; }
  .header-left { display: flex; align-items: center; gap: 14px; }
  .conf-badge { background: var(--gold); color: var(--navy); font-size: 9px; font-weight: 700; letter-spacing: 0.14em; text-transform: uppercase; padding: 3px 9px; border-radius: 2px; }
  .header-title { font-family: 'Playfair Display', serif; font-size: 18px; color: white; }
  .header-title em { color: var(--gold); font-style: normal; }
  .header-date { font-size: 11px; color: rgba(255,255,255,0.4); letter-spacing: 0.05em; }

  /* NAV */
  .sticky-nav { background: var(--white); border-bottom: 1px solid var(--border); position: sticky; top: 62px; z-index: 190; box-shadow: 0 2px 8px rgba(13,31,60,0.04); }
  .nav-inner { max-width: 1180px; margin: 0 auto; padding: 0 36px; display: flex; overflow-x: auto; scrollbar-width: none; }
  .nav-inner::-webkit-scrollbar { display: none; }
  .nav-link { font-size: 11px; font-weight: 600; letter-spacing: 0.07em; text-transform: uppercase; color: var(--text-light); text-decoration: none; padding: 15px 18px; border-bottom: 2px solid transparent; white-space: nowrap; transition: color 0.15s, border-color 0.15s; }
  .nav-link:hover, .nav-link.active { color: var(--navy); border-bottom-color: var(--gold); }

  /* MAIN */
  .main { max-width: 1180px; margin: 0 auto; padding: 44px 36px 88px; }

  /* SECTIONS */
  .section { margin-bottom: 64px; }
  .section-header { display: flex; align-items: baseline; gap: 14px; margin-bottom: 26px; padding-bottom: 14px; border-bottom: 1px solid var(--border); }
  .sec-num { font-family: 'Playfair Display', serif; font-size: 12px; color: var(--gold); letter-spacing: 0.1em; min-width: 24px; }
  .sec-title { font-family: 'Playfair Display', serif; font-size: 26px; color: var(--navy); letter-spacing: -0.01em; }

  /* CARD */
  .card { background: var(--white); border: 1px solid var(--border); border-radius: 8px; padding: 26px 30px; box-shadow: var(--shadow); }
  .card-label { font-size: 10px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: var(--text-light); margin-bottom: 10px; }
  .card p { font-size: 13.5px; line-height: 1.78; color: var(--text-mid); }

  /* GRIDS */
  .g2 { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  .g3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; }
  .g4 { display: grid; grid-template-columns: repeat(4, 1fr); gap: 14px; }

  /* EXEC HERO */
  .exec-hero { background: var(--navy); border-radius: 10px; padding: 38px 44px; margin-bottom: 22px; position: relative; overflow: hidden; }
  .exec-hero::after { content: ''; position: absolute; right: -60px; top: -60px; width: 320px; height: 320px; background: radial-gradient(circle, rgba(200,151,58,0.13) 0%, transparent 65%); pointer-events: none; }
  .exec-eyebrow { font-size: 10px; font-weight: 700; letter-spacing: 0.14em; text-transform: uppercase; color: var(--gold); margin-bottom: 10px; }
  .exec-hero h2 { font-family: 'Playfair Display', serif; font-size: 30px; color: var(--white); line-height: 1.25; margin-bottom: 18px; max-width: 680px; }
  .exec-hero p { font-size: 14px; line-height: 1.82; color: rgba(255,255,255,0.68); max-width: 720px; }

  /* STATS */
  .stat-card { background: var(--white); border: 1px solid var(--border); border-radius: 8px; padding: 20px 22px; text-align: center; box-shadow: var(--shadow); }
  .stat-val { font-family: 'Playfair Display', serif; font-size: 28px; color: var(--navy); display: block; margin-bottom: 4px; }
  .stat-lab { font-size: 10px; font-weight: 600; letter-spacing: 0.08em; text-transform: uppercase; color: var(--text-light); }

  /* PILLARS */
  .pillar { background: var(--white); border: 1px solid var(--border); border-radius: 8px; padding: 24px 26px; border-top: 3px solid var(--navy); box-shadow: var(--shadow); }
  .pillar.p-gold { border-top-color: var(--gold); }
  .pillar.p-blue { border-top-color: var(--blue); }
  .pillar.p-green { border-top-color: var(--green); }
  .pillar-icon { font-size: 20px; margin-bottom: 8px; display: block; }
  .pillar-badge { font-size: 9px; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; color: var(--text-light); margin-bottom: 6px; }
  .pillar-name { font-size: 15px; font-weight: 600; color: var(--navy); margin-bottom: 10px; }
  .pillar p { font-size: 13px; line-height: 1.7; color: var(--text-mid); }

  /* GOAL BANNER */
  .goal-banner { background: linear-gradient(120deg, var(--navy-mid) 0%, var(--navy) 100%); border: 1px solid var(--gold); border-radius: 10px; padding: 26px 34px; margin-top: 18px; display: flex; gap: 18px; align-items: flex-start; }
  .goal-icon { font-size: 26px; flex-shrink: 0; }
  .goal-text h3 { font-family: 'Playfair Display', serif; font-size: 18px; color: var(--gold); margin-bottom: 6px; }
  .goal-text p { font-size: 13.5px; line-height: 1.78; color: rgba(255,255,255,0.68); }

  /* TIMELINE */
  .timeline { position: relative; padding-left: 28px; }
  .timeline::before { content: ''; position: absolute; left: 8px; top: 10px; bottom: 10px; width: 2px; background: var(--cream-dark); }
  .tl-item { position: relative; background: var(--white); border: 1px solid var(--border); border-radius: 8px; padding: 18px 22px; margin-bottom: 12px; box-shadow: var(--shadow); }
  .tl-item::before { content: ''; position: absolute; left: -22px; top: 20px; width: 10px; height: 10px; border-radius: 50%; background: var(--text-light); border: 2px solid var(--white); box-shadow: 0 0 0 2px var(--text-light); }
  .tl-item.now::before { background: var(--green); box-shadow: 0 0 0 2px var(--green); width: 12px; height: 12px; top: 18px; left: -23px; }
  .tl-item.future::before { background: var(--gold); box-shadow: 0 0 0 2px var(--gold); }
  .tl-date { font-size: 10px; font-weight: 700; letter-spacing: 0.09em; text-transform: uppercase; color: var(--text-light); margin-bottom: 4px; }
  .tl-title { font-size: 14.5px; font-weight: 600; color: var(--navy); margin-bottom: 6px; }
  .tl-desc { font-size: 13px; line-height: 1.68; color: var(--text-mid); }
  .tag { display: inline-block; font-size: 9px; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; padding: 2px 8px; border-radius: 3px; margin-top: 8px; }
  .tag-green { background: var(--green-pale); color: var(--green); }
  .tag-navy { background: var(--blue-pale); color: var(--blue); }
  .tag-amber { background: var(--amber-pale); color: var(--amber); }
  .tag-gold { background: #fef3e0; color: #7a4500; }

  /* STAKEHOLDERS */
  .sh-card { background: var(--white); border: 1px solid var(--border); border-radius: 8px; padding: 22px 24px; box-shadow: var(--shadow); display: flex; flex-direction: column; }
  .sh-card.priority { border-color: var(--gold); background: linear-gradient(140deg, #fffcf5 0%, var(--white) 55%); }
  .sh-head { display: flex; gap: 13px; align-items: flex-start; margin-bottom: 14px; }
  .avatar { width: 40px; height: 40px; border-radius: 50%; background: var(--navy); display: flex; align-items: center; justify-content: center; font-family: 'Playfair Display', serif; font-size: 15px; color: var(--gold); flex-shrink: 0; }
  .sh-card.priority .avatar { background: var(--gold); color: var(--navy); }
  .sh-name { font-size: 14px; font-weight: 600; color: var(--navy); margin-bottom: 2px; }
  .sh-role { font-size: 11.5px; color: var(--text-light); line-height: 1.4; }
  .sh-notes { list-style: none; flex: 1; }
  .sh-notes li { font-size: 12.5px; line-height: 1.65; color: var(--text-mid); padding-left: 14px; position: relative; margin-bottom: 4px; }
  .sh-notes li::before { content: '·'; position: absolute; left: 4px; color: var(--gold); font-weight: 800; }
  .li-link { display: inline-flex; align-items: center; gap: 5px; font-size: 10.5px; font-weight: 600; color: #0a66c2; text-decoration: none; margin-top: 12px; letter-spacing: 0.04em; }
  .li-link:hover { text-decoration: underline; }
  .li-placeholder { font-size: 10.5px; color: var(--text-light); margin-top: 12px; font-style: italic; display: block; }

  /* ORG NOTE */
  .org-note { background: var(--blue-pale); border: 1px solid rgba(26,90,173,0.15); border-radius: 8px; padding: 18px 22px; margin-top: 14px; font-size: 13px; color: var(--text-mid); line-height: 1.72; }
  .org-note strong { color: var(--navy); }

  /* RISKS */
  .risk-card { background: var(--white); border: 1px solid var(--border); border-radius: 8px; padding: 22px 26px; box-shadow: var(--shadow); }
  .risk-card.r-high { border-left: 4px solid #b02020; }
  .risk-card.r-med  { border-left: 4px solid #d07020; }
  .risk-card.r-low  { border-left: 4px solid #1a8040; }
  .risk-badge { font-size: 9px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; margin-bottom: 6px; }
  .r-high .risk-badge { color: #b02020; }
  .r-med  .risk-badge { color: #d07020; }
  .r-low  .risk-badge { color: #1a8040; }
  .risk-title { font-size: 14px; font-weight: 600; color: var(--navy); margin-bottom: 8px; }
  .risk-desc { font-size: 13px; line-height: 1.68; color: var(--text-mid); }
  .risk-mit { margin-top: 12px; padding-top: 12px; border-top: 1px solid var(--border); font-size: 12px; color: var(--text-mid); line-height: 1.65; }
  .risk-mit strong { color: var(--navy); }

  /* ACTIONS */
  .action-card { background: var(--white); border: 1px solid var(--border); border-radius: 8px; padding: 22px 26px; box-shadow: var(--shadow); }
  .action-track { font-size: 10px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; padding-bottom: 12px; margin-bottom: 14px; border-bottom: 2px solid; }
  .action-track.t-gateway { color: var(--gold); border-color: var(--gold); }
  .action-track.t-mesh    { color: var(--blue); border-color: var(--blue); }
  .action-track.t-strategy{ color: var(--green); border-color: var(--green); }
  .action-track.t-people  { color: #7a3aad; border-color: #7a3aad; }
  .action-item { display: flex; gap: 11px; align-items: flex-start; margin-bottom: 12px; }
  .a-dot { width: 18px; height: 18px; border-radius: 50%; border: 2px solid var(--cream-dark); flex-shrink: 0; margin-top: 1px; cursor: pointer; transition: all 0.2s; }
  .a-dot:hover { border-color: var(--gold); background: var(--gold-pale); }
  .a-dot.done { background: var(--gold); border-color: var(--gold); }
  .a-text { font-size: 13px; line-height: 1.65; color: var(--text-mid); }
  .a-text strong { color: var(--navy); font-weight: 600; }

  /* INFO LIST */
  .info-list { list-style: none; display: flex; flex-direction: column; gap: 9px; }
  .info-list li { font-size: 13px; line-height: 1.68; color: var(--text-mid); padding-left: 18px; position: relative; }
  .info-list li::before { content: '→'; position: absolute; left: 0; color: var(--gold); font-size: 11px; top: 1px; }
  .info-list li strong { color: var(--navy); }

  /* PAIN POINTS */
  .pain-item { background: var(--white); border: 1px solid var(--border); border-radius: 7px; padding: 14px 18px; display: flex; gap: 11px; align-items: flex-start; box-shadow: var(--shadow); }
  .pain-icon { font-size: 17px; flex-shrink: 0; margin-top: 1px; }
  .pain-text { font-size: 13px; line-height: 1.65; color: var(--text-mid); }
  .pain-text strong { display: block; font-size: 12.5px; color: var(--navy); margin-bottom: 3px; font-weight: 600; }

  /* FREDDIE METRICS */
  .fm-box { background: var(--navy); border-radius: 10px; padding: 30px 34px; margin-bottom: 14px; }
  .fm-box h3 { font-family: 'Playfair Display', serif; font-size: 20px; color: var(--white); margin-bottom: 10px; }
  .fm-box p { font-size: 13.5px; line-height: 1.8; color: rgba(255,255,255,0.62); }
  .fm-metrics { display: flex; gap: 12px; margin-top: 18px; flex-wrap: wrap; }
  .fm-metric { background: rgba(255,255,255,0.07); border: 1px solid rgba(255,255,255,0.11); border-radius: 6px; padding: 12px 18px; text-align: center; flex: 1; min-width: 90px; }
  .fm-v { display: block; font-family: 'Playfair Display', serif; font-size: 22px; color: var(--gold); margin-bottom: 3px; }
  .fm-l { font-size: 10px; color: rgba(255,255,255,0.45); letter-spacing: 0.07em; text-transform: uppercase; }

  /* ARCH */
  .arch-img-wrap { background: var(--white); border: 1px solid var(--border); border-radius: 8px; padding: 20px; box-shadow: var(--shadow); text-align: center; }
  .arch-img-wrap img { max-width: 100%; height: auto; border-radius: 4px; }
  .arch-caption { font-size: 11px; color: var(--text-light); text-align: center; margin-top: 10px; letter-spacing: 0.04em; font-style: italic; }

  /* REQUIREMENTS TABLE */
  .req-table { width: 100%; border-collapse: collapse; background: var(--white); border-radius: 8px; overflow: hidden; box-shadow: var(--shadow); font-size: 12.5px; }
  .req-table th { background: var(--navy); color: rgba(255,255,255,0.85); font-size: 10px; font-weight: 700; letter-spacing: 0.1em; text-transform: uppercase; padding: 12px 16px; text-align: left; border-right: 1px solid rgba(255,255,255,0.08); }
  .req-table th:last-child { border-right: none; }
  .req-table td { padding: 11px 16px; vertical-align: top; border-bottom: 1px solid var(--border); border-right: 1px solid var(--border); color: var(--text-mid); line-height: 1.65; }
  .req-table td:last-child { border-right: none; }
  .req-table tr:last-child td { border-bottom: none; }
  .req-table tr:nth-child(even) td { background: rgba(13,31,60,0.018); }
  .req-table .req-cat { font-weight: 600; color: var(--navy); }

  /* FHFA */
  .fhfa-card { background: var(--white); border: 1px solid var(--border); border-radius: 8px; padding: 18px 22px; border-left: 4px solid var(--blue); box-shadow: var(--shadow); }
  .fhfa-num { font-size: 9px; font-weight: 700; letter-spacing: 0.12em; text-transform: uppercase; color: var(--blue); margin-bottom: 5px; }
  .fhfa-title { font-size: 13.5px; font-weight: 600; color: var(--navy); margin-bottom: 8px; }
  .fhfa-desc { font-size: 13px; line-height: 1.7; color: var(--text-mid); }

  /* FOOTER */
  .site-footer { background: var(--navy); padding: 22px 36px; text-align: center; font-size: 11px; color: rgba(255,255,255,0.3); letter-spacing: 0.05em; border-top: 3px solid var(--gold); }

  /* ANIMATIONS */
  @keyframes fadeUp { from { opacity: 0; transform: translateY(14px); } to { opacity: 1; transform: translateY(0); } }
  .section { animation: fadeUp 0.45s ease both; }
  .section:nth-child(1) { animation-delay: 0.05s; }
  .section:nth-child(2) { animation-delay: 0.10s; }
  .section:nth-child(3) { animation-delay: 0.15s; }
  .section:nth-child(4) { animation-delay: 0.20s; }
  .section:nth-child(5) { animation-delay: 0.25s; }
  .section:nth-child(6) { animation-delay: 0.30s; }
  .section:nth-child(7) { animation-delay: 0.35s; }

  /* RESPONSIVE */
  @media (max-width: 960px) { .g4 { grid-template-columns: 1fr 1fr; } .g3 { grid-template-columns: 1fr 1fr; } .main { padding: 30px 24px 64px; } .header-inner, .nav-inner { padding: 0 24px; } }
  @media (max-width: 680px) { .g2, .g3, .g4 { grid-template-columns: 1fr; } .exec-hero { padding: 28px 26px; } .exec-hero h2 { font-size: 24px; } }
</style>
</head>
<body>

<!-- HEADER -->
<header class="site-header">
  <div class="header-inner">
    <div class="header-left">
      <span class="conf-badge">Internal · Confidential</span>
      <span class="header-title">Freddie Mac — <em>Opportunity Brief</em></span>
    </div>
    <span class="header-date">February 2026</span>
  </div>
</header>

<!-- NAV -->
<nav class="sticky-nav">
  <div class="nav-inner">
    <a href="#summary"      class="nav-link">Executive Summary</a>
    <a href="#status"       class="nav-link">Status & Timeline</a>
    <a href="#stakeholders" class="nav-link">Stakeholders</a>
    <a href="#risks"        class="nav-link">Risks & Challenges</a>
    <a href="#next-steps"   class="nav-link">Next Steps</a>
    <a href="#context"      class="nav-link">Account Context</a>
    <a href="#architecture" class="nav-link">Architecture & Reqs</a>
  </div>
</nav>

<main class="main">

<!-- ══ 01: EXECUTIVE SUMMARY ══ -->
<section class="section" id="summary">
  <div class="section-header">
    <span class="sec-num">01</span>
    <h2 class="sec-title">Executive Summary</h2>
  </div>

  <div class="exec-hero">
    <div class="exec-eyebrow">Strategic Sales Opportunity — Solo.io</div>
    <h2>Freddie Mac — Becoming the Platform of Record</h2>
    <p>Freddie Mac is actively migrating off two incumbent vendors — <strong style="color:rgba(255,255,255,0.9)">Tetrate</strong> (service mesh) and <strong style="color:rgba(255,255,255,0.9)">Apigee</strong> (API gateway) — representing a combined ~$3M in annual spend. This is not simply a two-line-item replacement. The mission is to land as Freddie's long-term strategic infrastructure partner across API Gateway, Service Mesh, and AI traffic management — embedded at one of the most systemically critical institutions in the U.S. housing economy.</p>
  </div>

  <div class="g4" style="margin-bottom:22px;">
    <div class="stat-card"><span class="stat-val">$3M+</span><span class="stat-lab">Combined ACV Target</span></div>
    <div class="stat-card"><span class="stat-val">~$1.5M</span><span class="stat-lab">Apigee Spend (Anchor)</span></div>
    <div class="stat-card"><span class="stat-val">~$1.5M</span><span class="stat-lab">Tetrate Spend (Mesh)</span></div>
    <div class="stat-card"><span class="stat-val">Q2 '26</span><span class="stat-lab">Gateway POC Target</span></div>
  </div>

  <div class="g3" style="margin-bottom:18px;">
    <div class="pillar p-gold">
      <span class="pillar-icon">🔌</span>
      <div class="pillar-badge">Anchor · Immediate</div>
      <div class="pillar-name">API Gateway — Gloo</div>
      <p>Freddie wants out of Apigee due to cost and the forced Apigee Hybrid move (data plane on GCP). Full demo delivered. POC scoping is next. Primary use case: B2B API management for Single Family & Multi-Family. <strong>Kong is the primary competitive risk.</strong></p>
    </div>
    <div class="pillar p-blue">
      <span class="pillar-icon">🕸️</span>
      <div class="pillar-badge">Strategic · Mid-Term</div>
      <div class="pillar-name">Service Mesh — Ambient</div>
      <p>Running OSS Istio across 580+ services, 55 clusters — growing to 5K–7K workloads. Tetrate renewal June 2027, migration planning starts late 2026. Core pain: scale, observability, upgrade complexity, no HA failover. Ambient with multi-cluster is the target.</p>
    </div>
    <div class="pillar p-green">
      <span class="pillar-icon">🤖</span>
      <div class="pillar-badge">Expansion · Long-Term</div>
      <div class="pillar-name">AI Infrastructure</div>
      <p>Freddie has an explicit technology mandate to modernize AI/ML for mortgage risk and underwriting. Their gateway requirements already include LLM integrations. Early positioning on AI traffic management is a meaningful differentiator.</p>
    </div>
  </div>

  <div class="goal-banner">
    <span class="goal-icon">🎯</span>
    <div class="goal-text">
      <h3>Strategic Objective — Upcoming On-Site</h3>
      <p>Tie the Gateway and Mesh conversations together and expand the relationship to leadership. The mission: imprint ourselves as a <em style="color:var(--gold-light)">strategic platform partner</em> — not a point solution vendor. Connect with Charles and Anil, help Freddie think holistically about their cloud infrastructure future, and showcase the art of the possible.</p>
    </div>
  </div>
</section>

<!-- ══ 02: STATUS & TIMELINE ══ -->
<section class="section" id="status">
  <div class="section-header">
    <span class="sec-num">02</span>
    <h2 class="sec-title">Current Status & Timeline</h2>
  </div>

  <div class="g2" style="margin-bottom:18px;">
    <div class="card">
      <div class="card-label">🔌 Gateway Track — Current Status</div>
      <p>Actively progressing. Full demo delivered. Freddie is evaluating and POC scoping is underway. Thiru Murugesan (PM) manages the Apigee replacement project — our primary anchor. Kong is an active competitor. Key differentiators: Envoy-native architecture, bring-your-own portal frontend, unified mesh + gateway platform story.</p>
    </div>
    <div class="card">
      <div class="card-label">🕸️ Mesh Track — Current Status</div>
      <p>Earlier stage but strong engagement. Devender Kura's team owns the OSS Istio deployment. Formal evaluation begins end of Q1 2026. Tetrate renewal is June 2027 — migration planning starts late 2026. Freddie knows service bridge is being decommissioned. Pain is real; decision is deliberate.</p>
    </div>
  </div>

  <div class="timeline">
    <div class="tl-item past">
      <div class="tl-date">Early 2025</div>
      <div class="tl-title">First In-Person Meeting with Freddie Mac</div>
      <div class="tl-desc">Louis met with Freddie Mac leadership in person. Discussed Tetrate dissatisfaction and the long-term migration plan. Relationship established and maintained since.</div>
      <span class="tag tag-navy">Completed</span>
    </div>
    <div class="tl-item past">
      <div class="tl-date">October 2025</div>
      <div class="tl-title">Anil Razdan Reaches Out — Inbound Evaluation Signal</div>
      <div class="tl-desc">VP of Cloud Architecture proactively contacts us requesting content comparing Gloo, Apigee, Kong, and Tyk. Strong buying signal. Confirms infrastructure on EKS and OpenShift.</div>
      <span class="tag tag-green">Inbound Signal</span>
    </div>
    <div class="tl-item past">
      <div class="tl-date">Early 2026</div>
      <div class="tl-title">Comprehensive Gateway Demo Delivered</div>
      <div class="tl-desc">Full Gloo Gateway demo completed. Positive engagement. POC scoping is the next milestone on this track.</div>
      <span class="tag tag-navy">Completed</span>
    </div>
    <div class="tl-item now">
      <div class="tl-date">Now — Q1/Q2 2026</div>
      <div class="tl-title">🟢 Upcoming On-Site + POC Scoping</div>
      <div class="tl-desc">Leadership on-site is the immediate priority. Connect with Charles and Anil, expand the platform narrative, define Gateway POC approach and milestones. Begin Mesh architecture discovery in parallel.</div>
      <span class="tag tag-green">Active · Priority</span>
    </div>
    <div class="tl-item future">
      <div class="tl-date">Q2–Q3 2026</div>
      <div class="tl-title">Gateway POC Execution</div>
      <div class="tl-desc">Structured Gateway POC with agreed success criteria. Key focus: portal integration (bring-your-own frontend), B2B API management, Istio ingress integration, multi-region deployment (East1/East2 hot/hot).</div>
      <span class="tag tag-amber">Upcoming</span>
    </div>
    <div class="tl-item future">
      <div class="tl-date">Late 2026</div>
      <div class="tl-title">Mesh Migration Planning Begins</div>
      <div class="tl-desc">Freddie kicks off active migration away from Tetrate. Devender's team leads evaluation. Target: Ambient Mesh architecture validation, multi-cluster HA failover design, cluster-as-cattle capability planning.</div>
      <span class="tag tag-amber">Planned</span>
    </div>
    <div class="tl-item future">
      <div class="tl-date">June 2027</div>
      <div class="tl-title">Tetrate Renewal / Displacement Target</div>
      <div class="tl-desc">Formal Tetrate renewal window. Goal: Ambient Mesh displacement well underway before this date so the renewal is a formality, not a competitive re-evaluation.</div>
      <span class="tag tag-gold">Target Close</span>
    </div>
  </div>
</section>

<!-- ══ 03: STAKEHOLDERS ══ -->
<section class="section" id="stakeholders">
  <div class="section-header">
    <span class="sec-num">03</span>
    <h2 class="sec-title">Key Stakeholders</h2>
  </div>

  <div class="card" style="margin-bottom:18px;">
    <div class="card-label">Team Context</div>
    <p>All primary contacts sit within <strong>Enterprise Operations & Technology</strong> — an overlay organization whose internal customers are Single Family and Multi-Family business units. This team owns platform infrastructure, cloud architecture, and all tooling decisions relevant to this opportunity. Reporting chain: <strong>Charles → Scott → Anil → Devender</strong>.</p>
  </div>

  <div class="g3">
    <div class="sh-card">
      <div class="sh-head">
        <div class="avatar">CS</div>
        <div>
          <div class="sh-name">Charles Shiflett</div>
          <div class="sh-role">VP, Platform & Data Solutions<br>Anil's direct manager</div>
        </div>
      </div>
      <ul class="sh-notes">
        <li>Executive sponsor — key for strategic partnership positioning</li>
        <li>Priority target for the on-site visit</li>
        <li>Engaging here elevates us above a vendor/procurement conversation</li>
        <li>Connect through Anil as the entry point</li>
      </ul>
      <a href="https://www.linkedin.com/search/results/all/?keywords=Charles+Shiflett+Freddie+Mac" target="_blank" class="li-link">
        <svg width="12" height="12" viewBox="0 0 24 24" fill="#0a66c2"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        Search on LinkedIn
      </a>
    </div>

    <div class="sh-card priority">
      <div class="sh-head">
        <div class="avatar">AR</div>
        <div>
          <div class="sh-name">Anil Razdan ⭐</div>
          <div class="sh-role">VP, Cloud Architecture & Engineering<br><strong style="color:#8a5500; font-size:11px;">Most Important Contact</strong></div>
        </div>
      </div>
      <ul class="sh-notes">
        <li>Owns all platform engineering — our primary champion</li>
        <li>Currently behind schedule on platform deliverables</li>
        <li>Proactively reached out Oct 2025 requesting competitive comparison</li>
        <li>Decision authority on both Gateway and Mesh tracks</li>
        <li>Key to connecting us with Charles for executive sponsorship</li>
      </ul>
      <a href="https://www.linkedin.com/search/results/all/?keywords=Anil+Razdan+Freddie+Mac" target="_blank" class="li-link">
        <svg width="12" height="12" viewBox="0 0 24 24" fill="#0a66c2"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        Search on LinkedIn
      </a>
    </div>

    <div class="sh-card">
      <div class="sh-head">
        <div class="avatar">DK</div>
        <div>
          <div class="sh-name">Devender Kura</div>
          <div class="sh-role">Engineering Director<br>Oversees Istio & Mesh Deployment</div>
        </div>
      </div>
      <ul class="sh-notes">
        <li>Day-to-day technical owner of Istio infrastructure</li>
        <li>580+ services, 55 clusters under his team</li>
        <li>Primary evaluation lead for Mesh replacement</li>
        <li>Direct reports: Nishitkumar Tank, Vijay Manteta, Pardeep</li>
      </ul>
      <a href="https://www.linkedin.com/search/results/all/?keywords=Devender+Kura+Freddie+Mac" target="_blank" class="li-link">
        <svg width="12" height="12" viewBox="0 0 24 24" fill="#0a66c2"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        Search on LinkedIn
      </a>
    </div>

    <div class="sh-card">
      <div class="sh-head">
        <div class="avatar">TM</div>
        <div>
          <div class="sh-name">Thiru Murugesan</div>
          <div class="sh-role">Project Manager<br>Apigee Replacement Project</div>
        </div>
      </div>
      <ul class="sh-notes">
        <li>Owns the Apigee migration project — our anchor engagement</li>
        <li>Key operational contact for Gateway POC logistics</li>
        <li>Influence over project milestones and internal approvals</li>
      </ul>
      <a href="https://www.linkedin.com/search/results/all/?keywords=Thiru+Murugesan+Freddie+Mac" target="_blank" class="li-link">
        <svg width="12" height="12" viewBox="0 0 24 24" fill="#0a66c2"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        Search on LinkedIn
      </a>
    </div>

    <div class="sh-card">
      <div class="sh-head">
        <div class="avatar">RC</div>
        <div>
          <div class="sh-name">Ramu Chundu</div>
          <div class="sh-role">Sr. Technical Lead, Engineering</div>
        </div>
      </div>
      <ul class="sh-notes">
        <li>Senior technical lead in Devender's org</li>
        <li>Deep influence on architecture and POC evaluation criteria</li>
        <li>Likely key technical evaluator during POC phase</li>
      </ul>
      <a href="https://www.linkedin.com/search/results/all/?keywords=Ramu+Chundu+Freddie+Mac" target="_blank" class="li-link">
        <svg width="12" height="12" viewBox="0 0 24 24" fill="#0a66c2"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        Search on LinkedIn
      </a>
    </div>

    <div class="sh-card">
      <div class="sh-head">
        <div class="avatar">MI</div>
        <div>
          <div class="sh-name">Michael</div>
          <div class="sh-role">Internal Business Stakeholder<br>Single Family & Multi-Family</div>
        </div>
      </div>
      <ul class="sh-notes">
        <li>Internal customer of the Enterprise Ops & Tech team</li>
        <li>Represents business lines dependent on managed APIs</li>
        <li>Influence on requirements and success criteria definition</li>
      </ul>
      <span class="li-placeholder">LinkedIn — confirm full name to add</span>
    </div>
  </div>

  <div class="org-note">
    <strong>Reporting Structure:</strong> Charles Shiflett (VP) → Scott → Anil Razdan (VP, Cloud Architecture) → Devender Kura (Engineering Director) → Ramu Chundu, Vijay Manteta, Nishitkumar Tank, Pardeep. GPD & PDM functions sit alongside Anil reporting to Scott. Michael (internal customer) is in the Single Family / Multi-Family business units with dotted-line influence on platform requirements.
  </div>
</section>

<!-- ══ 04: RISKS & CHALLENGES ══ -->
<section class="section" id="risks">
  <div class="section-header">
    <span class="sec-num">04</span>
    <h2 class="sec-title">Risks & Challenges</h2>
  </div>
  <div class="g2">
    <div class="risk-card r-high">
      <div class="risk-badge">🔴 High Risk</div>
      <div class="risk-title">Kong — Active Competitor on Gateway</div>
      <div class="risk-desc">Kong is the primary named competitor for the Apigee replacement. Likely already engaged, well-known in enterprise API management, and will run a strong POC. Most acute competitive risk in the near term.</div>
      <div class="risk-mit"><strong>Mitigation:</strong> Lock in POC evaluation criteria early — ensure Gloo's differentiators are baked in: Envoy-native architecture, bring-your-own portal frontend, native Istio integration, and the unified mesh + gateway + AI platform story Kong simply cannot match.</div>
    </div>
    <div class="risk-card r-high">
      <div class="risk-badge">🔴 High Risk</div>
      <div class="risk-title">DIY / Stay on OSS Istio (Mesh Track)</div>
      <div class="risk-desc">Freddie has tolerated significant Istio pain for years without resolving it. They may rationalize continuing to manage OSS Istio independently. A "do nothing" path is real given their stretched team bandwidth and budget scrutiny.</div>
      <div class="risk-mit"><strong>Mitigation:</strong> Validate that HA failover and multi-cluster management are genuinely unsolved. Demonstrate how Ambient + Solo is materially different from what they've tried before. Draw out the "art of the possible" — cluster-as-cattle, automatic failover — that standalone OSS cannot deliver.</div>
    </div>
    <div class="risk-card r-med">
      <div class="risk-badge">🟡 Medium Risk</div>
      <div class="risk-title">Anil Behind Schedule — Champion Bandwidth</div>
      <div class="risk-desc">Anil is currently behind on platform deliverables. A distracted champion slows deal velocity, deprioritizes POC participation, and delays decisions. Given the breadth of his responsibilities, this is a real risk to momentum.</div>
      <div class="risk-mit"><strong>Mitigation:</strong> Make every engagement low-friction. Bring a turnkey POC structure, clear milestones, and minimal burden on their team. The frame: "we'll do the heavy lifting."</div>
    </div>
    <div class="risk-card r-med">
      <div class="risk-badge">🟡 Medium Risk</div>
      <div class="risk-title">FHFA Conservatorship / Procurement Governance</div>
      <div class="risk-desc">Freddie operates under FHFA conservatorship. Major tech decisions in mortgage infrastructure may require FHFA approval or extended governance cycles, significantly stretching procurement timelines beyond typical enterprise deals.</div>
      <div class="risk-mit"><strong>Mitigation:</strong> Understand their procurement and approval cycle early. Engage security and compliance stakeholders alongside technical contacts. Build a realistic multi-quarter runway into the plan from the start.</div>
    </div>
    <div class="risk-card r-med">
      <div class="risk-badge">🟡 Medium Risk</div>
      <div class="risk-title">Mesh Architecture Not Yet Validated</div>
      <div class="risk-desc">Target mesh architecture is unclear. Key open questions: HA failover priority, multi-cluster topology, policy control model. Without shared clarity here, Ambient Mesh demos may miss the mark entirely.</div>
      <div class="risk-mit"><strong>Mitigation:</strong> Dedicate time during on-site for architecture discovery with Devender's team. Draw the target state together before demoing anything. Don't run a demo against undefined requirements.</div>
    </div>
    <div class="risk-card r-low">
      <div class="risk-badge">🟢 Lower Risk</div>
      <div class="risk-title">Cloud Lock-In Sensitivity (Post-Apigee)</div>
      <div class="risk-desc">Freddie's frustration with Apigee is partly driven by being forced to Apigee Hybrid with a GCP-hosted data plane. They may carry heightened sensitivity to any perceived vendor cloud lock-in.</div>
      <div class="risk-mit"><strong>Mitigation:</strong> Lead with Gloo's cloud-native, multi-cloud portability. They own the data plane on EKS/OpenShift. Envoy-based architecture gives them freedom and portability Apigee never offered.</div>
    </div>
  </div>
</section>

<!-- ══ 05: NEXT STEPS ══ -->
<section class="section" id="next-steps">
  <div class="section-header">
    <span class="sec-num">05</span>
    <h2 class="sec-title">Next Steps & Action Items</h2>
  </div>
  <div class="g2">
    <div class="action-card">
      <div class="action-track t-gateway">🔌 Gateway Track</div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Define Gateway POC scope, success criteria & milestones</strong> with Thiru and Devender's team. Agree on what success looks like before a single test is run.</div></div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Confirm Apigee migration timeline</strong> — understand internal urgency, hard deadlines, and who controls the budget and ultimate decision.</div></div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Prepare Kong differentiation narrative</strong> — bring-your-own portal frontend, Envoy-native, Istio-native mesh integration, AI/LLM gateway capabilities Kong cannot replicate.</div></div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Map portal integration path</strong> — confirm Freddie's existing developer portal setup and validate Gloo Portal's bring-your-own frontend model against their requirements.</div></div>
    </div>
    <div class="action-card">
      <div class="action-track t-mesh">🕸️ Mesh Track</div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Architecture discovery session with Devender's team</strong> — draw out target state, validate HA failover as the primary priority, map multi-cluster requirements.</div></div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Show how Ambient + Solo differs from OSS multi-cluster</strong> — why hasn't Freddie achieved HA failover with what they have today? Answer this specifically.</div></div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Quantify sidecar cost savings</strong> — model infrastructure savings from Ambient sidecarless at their scale: 55 clusters, growing to 5K–7K workloads.</div></div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Address kgateway / agentgateway question directly</strong> — Freddie asked about this explicitly. Have a crisp, confident answer ready for the on-site.</div></div>
    </div>
    <div class="action-card">
      <div class="action-track t-strategy">🎯 On-Site Strategy</div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Connect with Charles Shiflett</strong> — frame the platform partnership story, not the product pitch. What does Freddie's infrastructure look like in 2028?</div></div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Deliver a unified Gateway + Mesh + AI narrative</strong> — this is the strategic differentiator no point solution (Kong, Tetrate) can match.</div></div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Introduce AI traffic management angle</strong> — Freddie's FHFA mandate explicitly calls for AI/tech leverage in operations. Their gateway requirements already include LLM integrations. We're ahead of this curve.</div></div>
    </div>
    <div class="action-card">
      <div class="action-track t-people">👥 Stakeholder & Admin</div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Confirm and add LinkedIn profiles</strong> for Charles Shiflett, Vijay Manteta, Nishitkumar Tank, and Pardeep. Update CRM.</div></div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Confirm Michael's full name</strong> — the internal business stakeholder representing Single Family/Multi-Family. Important for understanding business requirements.</div></div>
      <div class="action-item"><div class="a-dot"></div><div class="a-text"><strong>Understand FHFA procurement & approval process</strong> — who signs off, what governance cycle applies, what's the realistic path from POC to contract?</div></div>
    </div>
  </div>
</section>

<!-- ══ 06: ACCOUNT CONTEXT ══ -->
<section class="section" id="context">
  <div class="section-header">
    <span class="sec-num">06</span>
    <h2 class="sec-title">Account Context</h2>
  </div>

  <div class="fm-box">
    <h3>Who is Freddie Mac?</h3>
    <p>Chartered by Congress in 1970, Freddie Mac's mission is to support the stability and affordability of the U.S. housing finance system. Freddie buys mortgage loans from smaller lending banks, bundles them into mortgage-backed securities (MBS), and sells them to institutional investors — shifting liquidity and interest-rate risk while guaranteeing investor payments. Freddie and Fannie Mae are described as "the plumbing" of U.S. housing credit: privately structured companies under federal FHFA conservatorship, with a public mission to prevent housing credit from freezing.</p>
    <div class="fm-metrics">
      <div class="fm-metric"><span class="fm-v">$10.7B</span><span class="fm-l">2025 Net Income</span></div>
      <div class="fm-metric"><span class="fm-v">$23.3B</span><span class="fm-l">Revenue</span></div>
      <div class="fm-metric"><span class="fm-v">$70B</span><span class="fm-l">Net Worth Built</span></div>
      <div class="fm-metric"><span class="fm-v">$465B</span><span class="fm-l">Liquidity Provided</span></div>
      <div class="fm-metric"><span class="fm-v">1.7M</span><span class="fm-l">Families Helped</span></div>
      <div class="fm-metric"><span class="fm-v">54%</span><span class="fm-l">GSE Single-Family Share</span></div>
      <div class="fm-metric"><span class="fm-v">51%</span><span class="fm-l">Multifamily Share</span></div>
    </div>
  </div>

  <div class="g2" style="margin-bottom:14px;">
    <div class="card">
      <div class="card-label">Why Technology is Mission-Critical at Freddie</div>
      <ul class="info-list">
        <li><strong>Risk modeling:</strong> Must analyze default, interest rate, prepayment, and portfolio risk at massive scale</li>
        <li><strong>Underwriting AI:</strong> Automated tool has qualified 250K+ additional borrowers; loans $1,700 less costly on average</li>
        <li><strong>Loan friction detection:</strong> Erratic loan volumes are an early warning signal — real-time monitoring is essential to protecting lender relationships</li>
        <li><strong>QC automation:</strong> Technology to automate quality control review and remedy on delivered loans</li>
        <li><strong>AI/LLM mandate:</strong> Gateway requirements explicitly include LLM integrations — they are already planning for AI infrastructure</li>
      </ul>
    </div>
    <div class="card">
      <div class="card-label">FHFA 2026–2030 Strategic Goals — Our Alignment</div>
      <div style="display:flex; flex-direction:column; gap:10px; margin-top:4px;">
        <div class="fhfa-card">
          <div class="fhfa-num">Strategic Goal 1</div>
          <div class="fhfa-title">Responsibly Oversee Fannie Mae & Freddie Mac</div>
          <div class="fhfa-desc">Risk-based supervisory examinations, safe and sound operations, asset preservation. <em>Our platform supports observability, risk controls, and policy governance.</em></div>
        </div>
        <div class="fhfa-card">
          <div class="fhfa-num">Strategic Goal 3</div>
          <div class="fhfa-title">Efficiently Modernize FHFA Operations</div>
          <div class="fhfa-desc">Leverage data, technology, and AI to reduce inefficiencies and enhance mission agility. <em>Direct alignment with our efficiency, AI gateway, and platform modernization story.</em></div>
        </div>
      </div>
    </div>
  </div>

  <div class="card">
    <div class="card-label">Current Vendor Landscape — Pain Points Driving This Opportunity</div>
    <div class="g2" style="gap:10px; margin-top:6px;">
      <div class="pain-item">
        <span class="pain-icon">⚠️</span>
        <div class="pain-text"><strong>Tetrate — Scale & Observability Failures</strong>5K–7K service/workload scale is breaking the current setup. Service bridge failed for observability. K8s version incompatibilities, configuration not flowing to control/data plane (1-day outage), no repeatable upgrade process between versions.</div>
      </div>
      <div class="pain-item">
        <span class="pain-icon">⚠️</span>
        <div class="pain-text"><strong>Tetrate — No HA Failover / SPOF Concern</strong>Didn't want a central management plane as a single point of failure. Lacking cluster-as-cattle capability and automatic HA failover across clusters. Sidecar infrastructure cost at 55 clusters is significant and growing.</div>
      </div>
      <div class="pain-item">
        <span class="pain-icon">💸</span>
        <div class="pain-text"><strong>Apigee — Cost & Cloud Lock-In</strong>~$1.5M annual spend. Being pushed toward Apigee Hybrid with data plane running in GCP — directly conflicts with Freddie's large push to AWS. Too expensive, wrong architectural direction, and wrong cloud.</div>
      </div>
      <div class="pain-item">
        <span class="pain-icon">🔄</span>
        <div class="pain-text"><strong>Tetrate — Support Quality Deteriorating</strong>Not satisfied with support from Tetrate after 3 years. Aware service bridge is being decommissioned. The relationship is deteriorating — the promises of observability and scale were never delivered.</div>
      </div>
    </div>
  </div>
</section>

<!-- ══ 07: ARCHITECTURE & REQUIREMENTS ══ -->
<section class="section" id="architecture">
  <div class="section-header">
    <span class="sec-num">07</span>
    <h2 class="sec-title">Architecture & Requirements</h2>
  </div>

  <div class="g2" style="margin-bottom:20px; align-items:start;">
    <div>
      <p style="font-size:10px; font-weight:700; letter-spacing:0.12em; text-transform:uppercase; color:var(--text-light); margin-bottom:10px;">Current State Mesh Architecture — What We're Replacing</p>
      <div class="arch-img-wrap">
        <img src="Screenshot_2026-02-16_at_2_34_52_PM.png" alt="Freddie Mac Current State Architecture — Tetrate TSB with multi-cluster Istio" />
        <div class="arch-caption">Current State: Tetrate TSB with multi-cluster Istio ingress, XCP Edge/TSB Operator, Skywalking for tracing. Running across 2+ clusters. Load balancer → Istio Ingress → services per cluster, managed by a central TSB agent with Tracing, Skywalking, UI, and XCP Control components.</div>
      </div>
    </div>
    <div>
      <p style="font-size:10px; font-weight:700; letter-spacing:0.12em; text-transform:uppercase; color:var(--text-light); margin-bottom:10px;">Key Architecture Facts</p>
      <div class="card" style="margin-bottom:10px;">
        <ul class="info-list">
          <li><strong>Platforms:</strong> EKS and OpenShift</li>
          <li><strong>Scale:</strong> 580+ services, 55 clusters, growing to 5K–7K workloads</li>
          <li><strong>Current stack:</strong> Apigee → Istio ingress controller → services</li>
          <li><strong>Cloud direction:</strong> Large push to AWS, multi-region (East1 & East2 hot/hot)</li>
          <li><strong>Legacy:</strong> Previously NGINX-based; all current products are Envoy-based</li>
          <li><strong>Portal:</strong> Existing Freddie Mac Developer Portal — bring-your-own frontend is a stated requirement</li>
        </ul>
      </div>
      <div class="card">
        <ul class="info-list">
          <li><strong>Mesh goal:</strong> Multi-cluster with cluster-as-cattle + automatic HA failover across clusters</li>
          <li><strong>Traffic management:</strong> "Nobody is doing traffic shifting today" — basic capabilities not yet working</li>
          <li><strong>Ambient Mesh interest:</strong> Infrastructure benefits and maturity — explicitly requested</li>
          <li><strong>Open question to address:</strong> What role will kgateway/agentgateway play?</li>
          <li><strong>Avoid:</strong> Central management plane as single point of failure</li>
        </ul>
      </div>
    </div>
  </div>

  <p style="font-size:10px; font-weight:700; letter-spacing:0.12em; text-transform:uppercase; color:var(--text-light); margin-bottom:12px;">Gateway Requirements — API Management Platform Capabilities (Provided by Freddie)</p>

  <div class="arch-img-wrap" style="margin-bottom:16px;">
    <img src="Screenshot_2026-02-16_at_2_34_40_PM.png" alt="Freddie Mac API Management Platform Requirements Matrix" />
    <div class="arch-caption">Freddie Mac's documented API Management Platform requirements across five capability domains — provided directly by their team during evaluation.</div>
  </div>

  <table class="req-table">
    <thead>
      <tr>
        <th style="width:16%">Capability Area</th>
        <th style="width:42%">Key Requirements</th>
        <th style="width:42%">Solo.io / Gloo Coverage & Differentiation</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="req-cat">APIs & Policies</td>
        <td>REST, GraphQL, gRPC, WebSocket, Webhook, Async API, SOAP · Open API Spec · OAuth, JWT, JWS, JWE, API Key · Mediation, Traffic Mgmt, Caching, Extension Policies · Streaming, large payload support · Payload formats: JSON, XML, Protobuf, Avro, Parquet · <strong>AI – LLM Integrations</strong></td>
        <td>Full Envoy-native protocol support. Native JWT/OAuth, extensible WASM filters for custom policies. <strong>AI gateway capabilities built-in</strong> — LLM routing, rate limiting, semantic caching. Already ahead of where Freddie is heading.</td>
      </tr>
      <tr>
        <td class="req-cat">Analytics, Monitoring & Governance</td>
        <td>Built-in API Analytics · APIs to extract analytics data · API Versioning · API Design</td>
        <td>Native observability via OpenTelemetry/OTel. Prometheus/Grafana integration. API lifecycle management through Gloo Portal. Full metrics pipeline compatible with their existing ELK stack.</td>
      </tr>
      <tr>
        <td class="req-cat">Integrations</td>
        <td>Ping (IDP/AuthZ) · ELK for Logging · Bitbucket · Swagger Hub · <strong>Istio</strong> · AWS API Gateway · AWS Lambda · SaaS Providers (Workday, Salesforce) · Cloudflare WAF</td>
        <td><strong>Native Istio integration is a core differentiator</strong> — not bolted on, not an afterthought. AWS-native deployment aligns with their AWS migration. Extensible integration framework for the rest of the stack.</td>
      </tr>
      <tr>
        <td class="req-cat">Developer Portal</td>
        <td>Custom Developer Portal APIs · Productize APIs · Manage & monitor subscriptions · API Monetization · API & Product Catalog · User Role mapping · <strong>Bring-your-own frontend</strong></td>
        <td><strong>Key differentiator vs. Kong.</strong> Gloo Portal supports full bring-your-own frontend — Freddie can hook their existing developer portal without disrupting customers or rebuilding the experience. Kong's portal model is more prescriptive.</td>
      </tr>
      <tr>
        <td class="req-cat">Deployment Architecture</td>
        <td>SaaS on AWS · Hybrid on AWS · Self-hosted on AWS · Kubernetes supported · <strong>Hot/Hot multi-region (East1 & East2)</strong></td>
        <td>Fully Kubernetes-native on EKS/OpenShift. Multi-region hot/hot supported natively. <strong>Self-hosted data plane — no GCP dependency</strong> (unlike Apigee Hybrid). Freddie owns their infrastructure.</td>
      </tr>
    </tbody>
  </table>

</section>

</main>

<footer class="site-footer">
  Internal Use Only &nbsp;·&nbsp; Solo.io Sales &nbsp;·&nbsp; Freddie Mac Opportunity Brief &nbsp;·&nbsp; February 2026 &nbsp;·&nbsp; Confidential
</footer>

<script>
  // Active nav on scroll
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.nav-link');
  const io = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        navLinks.forEach(l => l.classList.remove('active'));
        const a = document.querySelector(`.nav-link[href="#${e.target.id}"]`);
        if (a) a.classList.add('active');
      }
    });
  }, { rootMargin: '-25% 0px -65% 0px' });
  sections.forEach(s => io.observe(s));

  // Checkbox toggle
  document.querySelectorAll('.a-dot').forEach(dot => {
    dot.addEventListener('click', function() {
      this.classList.toggle('done');
      this.style.background = this.classList.contains('done') ? 'var(--gold)' : '';
      this.style.borderColor = this.classList.contains('done') ? 'var(--gold)' : '';
    });
  });
</script>
</body>
</html>

