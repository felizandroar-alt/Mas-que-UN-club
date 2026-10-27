<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#07152e">
  <meta name="description" content="Barça History: descubra a história do FC Barcelona, as suas lendas, títulos e momentos que marcaram o futebol.">
  <title>Barça History — Mais do que um clube</title>
  <style>
    :root {
      --navy: #07152e;
      --navy-2: #0d2143;
      --blue: #0756b8;
      --blue-light: #3d91ff;
      --garnet: #a50044;
      --gold: #f1c66d;
      --white: #f7f9fc;
      --muted: #aebbd0;
      --panel: rgba(255,255,255,.06);
      --line: rgba(255,255,255,.12);
      --radius: 20px;
      --shadow: 0 18px 60px rgba(0,0,0,.28);
    }
    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; scroll-padding-top: 90px; }
    body {
      margin: 0; background: var(--navy); color: var(--white);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      line-height: 1.65;
    }
    a { color: inherit; }
    button, input { font: inherit; }
    button { cursor: pointer; }
    img { max-width: 100%; display: block; }
    .container { width: min(1160px, calc(100% - 36px)); margin: 0 auto; }
    .eyebrow { color: var(--gold); text-transform: uppercase; letter-spacing: .16em; font-size: .76rem; font-weight: 800; }
    .section { padding: 84px 0; }
    .section-head { max-width: 720px; margin-bottom: 32px; }
    .section-head h2 { margin: 8px 0 12px; font-size: clamp(2rem, 4vw, 3.2rem); line-height: 1.08; letter-spacing: -.04em; }
    .section-head p { color: var(--muted); margin: 0; }
    .topbar {
      position: sticky; top: 0; z-index: 100; backdrop-filter: blur(18px);
      background: rgba(5,15,34,.88); border-bottom: 1px solid var(--line);
    }
    .nav { min-height: 76px; display: flex; align-items: center; justify-content: space-between; gap: 20px; }
    .brand { display: flex; align-items: center; gap: 11px; text-decoration: none; font-weight: 900; letter-spacing: -.04em; }
    .brand-mark {
      width: 43px; height: 43px; border-radius: 13px; display: grid; place-items: center;
      color: white; font-size: 1.2rem; font-weight: 950;
      background: linear-gradient(135deg, var(--blue), var(--garnet)); box-shadow: 0 8px 24px #a500443b;
    }
    .brand small { display: block; color: var(--muted); font-size: .64rem; letter-spacing: .12em; font-weight: 700; }
    .nav-links { display: flex; align-items: center; gap: 22px; }
    .nav-links a { color: #d8e2f2; text-decoration: none; font-size: .9rem; font-weight: 650; }
    .nav-links a:hover { color: var(--gold); }
    .menu-toggle { display: none; color: white; background: transparent; border: 1px solid var(--line); border-radius: 10px; padding: 8px 12px; }
    .hero {
      position: relative; overflow: hidden; min-height: 650px; display: flex; align-items: center;
      background:
        linear-gradient(90deg, rgba(5,15,34,.97) 0%, rgba(5,15,34,.83) 48%, rgba(5,15,34,.28) 100%),
        linear-gradient(0deg, var(--navy) 0%, transparent 30%),
        url("https://images.unsplash.com/photo-1522778119026-d647f0596c20?auto=format&fit=crop&w=2000&q=85") center/cover;
    }
    .hero::after { content: ""; position: absolute; width: 520px; height: 520px; border-radius: 50%; right: -150px; top: -180px; background: radial-gradient(circle, #0756b833, transparent 68%); pointer-events: none; }
    .hero-content { position: relative; z-index: 1; max-width: 760px; padding: 90px 0 110px; }
    .hero h1 { font-size: clamp(3.2rem, 8.5vw, 7rem); line-height: .92; letter-spacing: -.075em; margin: 16px 0 22px; }
    .hero h1 span { color: transparent; -webkit-text-stroke: 1.5px rgba(255,255,255,.8); }
    .hero p { max-width: 600px; font-size: clamp(1rem, 2vw, 1.18rem); color: #d1daea; }
    .hero-actions { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 28px; }
    .btn { border: 0; border-radius: 12px; padding: 13px 18px; font-weight: 850; text-decoration: none; display: inline-flex; align-items: center; justify-content: center; gap: 9px; transition: transform .2s, filter .2s; }
    .btn:hover { transform: translateY(-2px); filter: brightness(1.08); }
    .btn-primary { color: white; background: linear-gradient(110deg, var(--garnet), #d00052); box-shadow: 0 10px 26px #a5004438; }
    .btn-secondary { color: white; border: 1px solid #ffffff45; background: #ffffff0b; }
    .hero-note { display: flex; align-items: center; gap: 10px; margin-top: 36px; color: #c5d0e0; font-size: .83rem; }
    .dot { width: 8px; height: 8px; background: #54d6a0; border-radius: 50%; box-shadow: 0 0 0 5px #54d6a01b; }
    .stats { position: relative; z-index: 2; margin-top: -42px; }
    .stats-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; }
    .stat { padding: 22px; border-radius: 17px; border: 1px solid var(--line); background: linear-gradient(145deg, #10264b, #0a1933); box-shadow: var(--shadow); }
    .stat strong { display: block; font-size: clamp(1.9rem, 4vw, 2.8rem); line-height: 1.1; letter-spacing: -.06em; }
    .stat span { color: var(--muted); font-size: .82rem; }
    .notice { margin-top: 14px; color: #aebbd0; font-size: .78rem; }
    .split { display: grid; grid-template-columns: 1.02fr .98fr; gap: 42px; align-items: center; }
    .image-panel { position: relative; min-height: 400px; border-radius: var(--radius); overflow: hidden; background: #10264b; box-shadow: var(--shadow); }
    .image-panel img { width: 100%; height: 100%; min-height: 400px; object-fit: cover; }
    .image-caption { position: absolute; bottom: 16px; left: 16px; right: 16px; padding: 14px 16px; border: 1px solid #ffffff35; background: #07152edb; backdrop-filter: blur(10px); border-radius: 13px; font-size: .85rem; }
    .copy h2 { font-size: clamp(2rem, 4vw, 3rem); line-height: 1.08; letter-spacing: -.05em; margin: 10px 0 18px; }
    .copy p { color: var(--muted); }
    .pill-row { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 22px; }
    .pill { border: 1px solid var(--line); background: var(--panel); border-radius: 999px; padding: 7px 11px; font-size: .78rem; color: #dce6f6; }
    .dark-section { background: linear-gradient(180deg, #091a36, #07152e); border-top: 1px solid #ffffff08; border-bottom: 1px solid #ffffff08; }
    .timeline-tools { display: flex; flex-wrap: wrap; gap: 10px; margin-bottom: 30px; }
    .filter-btn { color: #dce6f6; background: #ffffff08; border: 1px solid var(--line); border-radius: 999px; padding: 9px 14px; font-size: .85rem; }
    .filter-btn.active, .filter-btn:hover { background: var(--garnet); border-color: var(--garnet); color: white; }
    .timeline { position: relative; display: grid; gap: 16px; }
    .timeline::before { content: ""; position: absolute; left: 20px; top: 18px; bottom: 18px; width: 2px; background: linear-gradient(var(--blue-light), var(--garnet), var(--gold)); opacity: .75; }
    .era { position: relative; padding: 23px 24px 23px 62px; border: 1px solid var(--line); border-radius: 17px; background: var(--panel); transition: border-color .2s, transform .2s; }
    .era:hover { border-color: #3d91ff88; transform: translateX(3px); }
    .era::before { content: ""; position: absolute; left: 12px; top: 28px; width: 18px; height: 18px; border: 4px solid var(--navy); border-radius: 50%; background: var(--gold); box-shadow: 0 0 0 2px var(--blue-light); }
    .era[hidden] { display: none; }
    .era-top { display: flex; flex-wrap: wrap; align-items: center; justify-content: space-between; gap: 10px; }
    .era time { color: var(--gold); font-weight: 900; font-size: .86rem; letter-spacing: .06em; }
    .era h3 { margin: 5px 0 8px; font-size: 1.3rem; }
    .era p { margin: 0; color: var(--muted); }
    .era-tag { font-size: .72rem; padding: 5px 9px; border-radius: 999px; background: #0756b82b; color: #9fc9ff; border: 1px solid #3d91ff35; }
    .legend-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
    .legend-card { border: 1px solid var(--line); background: var(--panel); border-radius: 18px; overflow: hidden; transition: transform .2s, border-color .2s; }
    .legend-card:hover { transform: translateY(-4px); border-color: #ffffff35; }
    .legend-card img { width: 100%; height: 220px; object-fit: cover; background: #10264b; }
    .legend-body { padding: 19px; }
    .legend-body .years { color: var(--gold); font-size: .77rem; font-weight: 850; letter-spacing: .08em; }
    .legend-body h3 { margin: 6px 0; font-size: 1.2rem; }
    .legend-body p { margin: 0; color: var(--muted); font-size: .9rem; }
    .trophy-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 14px; }
    .trophy { position: relative; padding: 23px; min-height: 180px; border: 1px solid var(--line); border-radius: 18px; background: linear-gradient(140deg, #11274b, #0a1933); overflow: hidden; }
    .trophy::after { content: "✦"; position: absolute; right: 14px; top: 6px; font-size: 5rem; color: #ffffff09; }
    .trophy .number { color: var(--gold); font-size: 2.6rem; font-weight: 950; line-height: 1; letter-spacing: -.07em; }
    .trophy h3 { margin: 12px 0 4px; font-size: 1rem; }
    .trophy p { color: var(--muted); margin: 0; font-size: .83rem; }
    .current-grid { display: grid; grid-template-columns: 1.15fr .85fr; gap: 18px; }
    .current-feature, .current-list { border: 1px solid var(--line); border-radius: var(--radius); overflow: hidden; background: var(--panel); }
    .current-feature img { width: 100%; height: 300px; object-fit: cover; }
    .current-feature-body { padding: 24px; }
    .current-feature h3 { font-size: 1.5rem; margin: 8px 0; }
    .current-feature p, .current-item p { color: var(--muted); }
    .current-list { padding: 22px; }
    .current-item { padding: 15px 0; border-bottom: 1px solid var(--line); }
    .current-item:last-child { border-bottom: 0; }
    .current-item strong { display: block; }
    .current-item p { font-size: .87rem; margin: 5px 0 0; }
    .source-list { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; }
    .source-link { display: flex; flex-direction: column; gap: 8px; padding: 18px; border: 1px solid var(--line); border-radius: 15px; background: var(--panel); text-decoration: none; }
    .source-link:hover { border-color: var(--blue-light); }
    .source-link strong { font-size: .95rem; }
    .source-link span { color: var(--muted); font-size: .82rem; }
    .source-link em { color: var(--gold); font-size: .8rem; font-style: normal; }
    .disclaimer { color: #aebbd0; font-size: .82rem; border-left: 3px solid var(--gold); padding-left: 14px; margin-top: 22px; }
    footer { border-top: 1px solid var(--line); padding: 30px 0; color: var(--muted); font-size: .82rem; }
    .footer-inner { display: flex; flex-wrap: wrap; align-items: center; justify-content: space-between; gap: 15px; }
    .back-top { text-decoration: none; color: white; border: 1px solid var(--line); border-radius: 999px; padding: 8px 12px; }
    @media (max-width: 850px) {
      .nav-links { display: none; position: absolute; top: 75px; left: 0; right: 0; padding: 18px; background: #07152ef7; border-bottom: 1px solid var(--line); flex-direction: column; align-items: stretch; gap: 0; }
      .nav-links.open { display: flex; }
      .nav-links a { padding: 12px 10px; }
      .menu-toggle { display: block; }
      .hero { min-height: 590px; background-position: 58% center; }
      .stats-grid { grid-template-columns: repeat(2, 1fr); }
      .split, .current-grid { grid-template-columns: 1fr; }
      .legend-grid { grid-template-columns: repeat(2, 1fr); }
      .trophy-grid { grid-template-columns: repeat(2, 1fr); }
      .source-list { grid-template-columns: 1fr; }
    }
    @media (max-width: 520px) {
      .container { width: min(100% - 26px, 1160px); }
      .section { padding: 62px 0; }
      .hero { min-height: 570px; }
      .hero-content { padding: 75px 0 95px; }
      .hero h1 { font-size: clamp(3rem, 17vw, 5rem); }
      .stats-grid { gap: 8px; }
      .stat { padding: 16px; }
      .legend-grid, .trophy-grid { grid-template-columns: 1fr; }
      .legend-card img { height: 230px; }
      .image-panel, .image-panel img { min-height: 300px; }
      .era { padding: 20px 15px 20px 52px; }
      .timeline::before { left: 16px; }
      .era::before { left: 8px; }
      .hero-actions .btn { width: 100%; }
    }
    @media (prefers-reduced-motion: reduce) {
      html { scroll-behavior: auto; }
      *, *::before, *::after { transition-duration: .01ms !important; animation-duration: .01ms !important; }
    }

    /* BARÇA MUSEUM EXPERIENCE — nova camada visual */
    :root {
      --navy: #030611;
      --navy-2: #07132c;
      --blue: #0756d8;
      --blue-light: #64a8ff;
      --garnet: #b0003a;
      --gold: #e6bd75;
      --white: #f8f7fb;
      --muted: #b1b7c9;
      --panel: rgba(7, 15, 36, .72);
      --line: rgba(125, 161, 255, .19);
      --shadow: 0 22px 70px rgba(0,0,0,.45);
    }
    body {
      background: radial-gradient(ellipse at 12% 15%, rgba(0,70,190,.17), transparent 34%),
                  radial-gradient(ellipse at 90% 26%, rgba(174,0,57,.13), transparent 32%), #03050d;
    }
    .topbar {
      background: rgba(3,5,14,.82);
      border-bottom: 1px solid rgba(80,130,255,.22);
      box-shadow: 0 8px 34px rgba(0,0,0,.22);
    }
    .brand-mark {
      border-radius: 50%; border: 1px solid rgba(255,255,255,.28);
      background: linear-gradient(145deg,#0754c9 0 48%,#a50044 52% 100%);
      box-shadow: 0 0 28px rgba(0,82,220,.27), 0 0 28px rgba(165,0,68,.18);
    }
    .hero {
      min-height: 720px;
      background:
        radial-gradient(ellipse at 83% 25%, rgba(0,83,255,.24), transparent 25%),
        radial-gradient(ellipse at 93% 63%, rgba(191,0,58,.27), transparent 29%),
        linear-gradient(90deg, rgba(2,4,13,.98) 0%, rgba(3,7,21,.88) 42%, rgba(3,5,15,.36) 100%),
        linear-gradient(0deg, #03050d 0%, transparent 40%),
        url("https://images.unsplash.com/photo-1522778119026-d647f0596c20?auto=format&fit=crop&w=2000&q=85") center/cover;
    }
    .hero::before {
      content:""; position:absolute; z-index:0; top:-15%; right:7%; width:2px; height:125%;
      background:linear-gradient(transparent,rgba(52,125,255,.0),rgba(54,126,255,.78),rgba(52,125,255,0));
      box-shadow:0 0 28px 7px rgba(0,83,255,.16), 0 0 85px 20px rgba(0,83,255,.08);
      transform:rotate(18deg); pointer-events:none;
    }
    .hero::after {
      width:620px;height:620px;right:-180px;top:-80px;border-radius:50%;
      background:radial-gradient(circle,rgba(0,85,255,.2),rgba(0,50,150,.06) 35%,transparent 69%);
      box-shadow:-300px 390px 100px -100px rgba(176,0,58,.12);
    }
    .hero-content { max-width: 820px; }
    .hero .eyebrow { color:#e7c27f; text-shadow:0 0 18px rgba(231,194,127,.16); }
    .hero h1 { text-shadow:0 5px 45px rgba(0,0,0,.48); }
    .hero h1 span { -webkit-text-stroke-color:rgba(230,189,117,.86); }
    .btn-primary { background:linear-gradient(110deg,#92002f,#c60048); box-shadow:0 0 26px rgba(190,0,58,.22); }
    .btn-secondary { border-color:rgba(99,154,255,.4); background:rgba(4,14,37,.42); backdrop-filter:blur(12px); }
    .stats { margin-top:-48px; }
    .stat, .trophy {
      background:linear-gradient(145deg,rgba(8,27,66,.91),rgba(6,8,22,.94));
      border-color:rgba(89,139,255,.2); box-shadow:0 16px 48px rgba(0,0,0,.23);
    }
    .stat:nth-child(even) { border-bottom-color:rgba(190,0,58,.45); }
    .section { position:relative; }
    .section:nth-of-type(even)::before {
      content:""; position:absolute; top:0; left:0; right:0; height:1px;
      background:linear-gradient(90deg,transparent,rgba(0,91,255,.28),rgba(184,0,58,.3),transparent);
    }
    .section-head h2 { text-shadow:0 0 30px rgba(0,72,200,.12); }
    .image-panel, .legend-card, .current-feature, .current-list, .source-link {
      background:rgba(5,10,25,.82); border-color:rgba(111,146,230,.2);
      box-shadow:0 18px 55px rgba(0,0,0,.22);
    }
    .image-panel::after {
      content:"";position:absolute;inset:0;pointer-events:none;
      background:linear-gradient(135deg,rgba(0,73,210,.13),transparent 42%,rgba(164,0,53,.16));
    }
    .legend-card { transition:transform .3s,border-color .3s,box-shadow .3s; }
    .legend-card:hover { transform:translateY(-6px);border-color:rgba(230,189,117,.5);box-shadow:0 20px 55px rgba(0,30,100,.22),0 0 25px rgba(0,74,220,.08); }
    .legend-card img { filter:saturate(.86) contrast(1.06); }
    .trophy { position:relative; }
    .trophy::before { content:"";position:absolute;left:0;top:0;bottom:0;width:2px;background:linear-gradient(transparent,#0756d8,#b0003a,transparent);opacity:.8; }
    .current-feature, .current-list { backdrop-filter:blur(14px); }
    .source-link:hover { border-color:rgba(230,189,117,.48); transform:translateY(-2px); }
    .source-link { transition:transform .22s,border-color .22s; }
    ::selection { background:rgba(176,0,58,.72);color:#fff; }
    @media (max-width:850px) {
      .hero { min-height:650px; background-position:58% center; }
      .nav-links { background:rgba(3,5,14,.97); border-bottom-color:rgba(0,85,255,.25); backdrop-filter:blur(18px); }
    }
    @media (max-width:520px) {
      .hero { min-height:610px; }
      .hero-content { padding-top:78px; }
      .stats { margin-top:-28px; }
    }

  </style>
</head>
<body>
  <header class="topbar">
    <div class="container nav">
      <a class="brand" href="#inicio" aria-label="Barça History, início">
        <span class="brand-mark">BH</span>
        <span>BARÇA HISTORY<small>1899 · MÉS QUE UN CLUB</small></span>
      </a>
      <button class="menu-toggle" id="menuToggle" aria-expanded="false" aria-controls="navLinks">☰ Menu</button>
      <nav class="nav-links" id="navLinks" aria-label="Navegação principal">
        <a href="#historia">História</a>
        <a href="#cronologia">Cronologia</a>
        <a href="#lendas">Lendas</a>
        <a href="#titulos">Títulos</a>
        <a href="#actualidade">Actualidade</a>
        <a href="#fontes">Fontes</a>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero" id="inicio">
      <div class="container">
        <div class="hero-content">
          <div class="eyebrow">Desde 29 de Novembro de 1899</div>
          <h1>MAIS DO<br>QUE <span>UM CLUBE.</span></h1>
          <p>Uma viagem pela história do FC Barcelona: as origens, as lendas, as noites europeias e a nova geração que continua a escrever o futuro blaugrana.</p>
          <div class="hero-actions">
            <a class="btn btn-primary" href="#cronologia">Explorar a história <span aria-hidden="true">↗</span></a>
            <a class="btn btn-secondary" href="#titulos">Ver palmarés</a>
          </div>
          <div class="hero-note"><span class="dot"></span> História e dados consultados em fontes oficiais do clube</div>
        </div>
      </div>
    </section>

    <section class="stats" aria-label="Títulos principais">
      <div class="container">
        <div class="stats-grid">
          <article class="stat"><strong>29</strong><span>Ligas espanholas masculinas</span></article>
          <article class="stat"><strong>5</strong><span>Ligas dos Campeões masculinas</span></article>
          <article class="stat"><strong>32</strong><span>Taças do Rei masculinas</span></article>
          <article class="stat"><strong>16</strong><span>Supertaças de Espanha masculinas</span></article>
        </div>
        <p class="notice">Contagem publicada pelo FC Barcelona, incluindo a época 2025/26. Títulos da equipa masculina principal; não inclui futebol feminino nem modalidades.</p>
      </div>
    </section>

    <section class="section" id="historia">
      <div class="container split">
        <div class="image-panel">
          <img src="https://images.unsplash.com/photo-1522778119026-d647f0596c20?auto=format&fit=crop&w=1200&q=85" alt="Estádio de futebol cheio de adeptos" loading="lazy">
          <div class="image-caption">Barcelona, Catalunha — uma identidade que ultrapassa as quatro linhas.</div>
        </div>
        <div class="copy">
          <div class="eyebrow">A identidade blaugrana</div>
          <h2>Uma história feita de futebol, cultura e pertença.</h2>
          <p>O FC Barcelona foi fundado em 29 de Novembro de 1899 por um grupo liderado por Joan Gamper. Ao longo das décadas, tornou-se uma instituição central na vida desportiva e cultural da Catalunha.</p>
          <p>O lema <em>“Més que un club”</em> — “Mais do que um clube” — exprime uma ligação que vai além dos resultados. A história do Barça inclui grandes conquistas, períodos difíceis, renovação e uma identidade de jogo associada à técnica, à posse de bola e à formação de jovens talentos.</p>
          <div class="pill-row">
            <span class="pill">Fundado em 1899</span><span class="pill">Joan Gamper</span><span class="pill">La Masia</span><span class="pill">Blaugrana</span>
          </div>
        </div>
      </div>
    </section>

    <section class="section dark-section" id="cronologia">
      <div class="container">
        <div class="section-head">
          <div class="eyebrow">Do primeiro jogo às novas conquistas</div>
          <h2>Cronologia histórica</h2>
          <p>Selecciona uma época para percorrer os momentos que moldaram o clube. Os filtros funcionam também em telemóveis.</p>
        </div>
        <div class="timeline-tools" role="group" aria-label="Filtrar cronologia">
          <button class="filter-btn active" data-filter="all" aria-pressed="true">Todas as épocas</button>
          <button class="filter-btn" data-filter="origens" aria-pressed="false">Origens</button>
          <button class="filter-btn" data-filter="consolidacao" aria-pressed="false">Consolidação</button>
          <button class="filter-btn" data-filter="europa" aria-pressed="false">Europa</button>
          <button class="filter-btn" data-filter="moderna" aria-pressed="false">Era moderna</button>
        </div>
        <div class="timeline" id="timeline">
          <article class="era" data-era="origens">
            <div class="era-top"><time>1899–1910</time><span class="era-tag">Fundação</span></div>
            <h3>Joan Gamper cria o FC Barcelona</h3>
            <p>O clube nasce em 29 de Novembro de 1899. Nos primeiros anos, constrói a sua comunidade, adopta as cores blaugrana e começa a conquistar competições regionais.</p>
          </article>
          <article class="era" data-era="origens">
            <div class="era-top"><time>1910–1929</time><span class="era-tag">Crescimento</span></div>
            <h3>Uma instituição em expansão</h3>
            <p>O número de adeptos cresce e o clube ganha uma dimensão social mais forte. Em 1922, inaugura o estádio de Les Corts; em 1929, vence a primeira edição do campeonato espanhol.</p>
          </article>
          <article class="era" data-era="consolidacao">
            <div class="era-top"><time>1930–1950</time><span class="era-tag">Resistência</span></div>
            <h3>Futebol em tempos difíceis</h3>
            <p>A Guerra Civil Espanhola e a repressão do pós-guerra afectam profundamente o clube. A equipa continua a competir e conquista títulos num período marcado por dificuldades sociais e políticas.</p>
          </article>
          <article class="era" data-era="consolidacao">
            <div class="era-top"><time>1950–1961</time><span class="era-tag">Nova casa</span></div>
            <h3>A era de Kubala e a abertura do Camp Nou</h3>
            <p>Com Ladislao Kubala como uma das grandes figuras, o Barça aumenta a sua base de adeptos. O Camp Nou é inaugurado em 24 de Setembro de 1957 e torna-se símbolo do crescimento do clube.</p>
          </article>
          <article class="era" data-era="consolidacao">
            <div class="era-top"><time>1973–1978</time><span class="era-tag">Cruyff jogador</span></div>
            <h3>Johan Cruyff muda uma geração</h3>
            <p>A chegada de Cruyff em 1973/74 marca uma época. O Barcelona conquista a Liga em 1973/74, com uma equipa que se torna parte importante da memória blaugrana.</p>
          </article>
          <article class="era" data-era="europa">
            <div class="era-top"><time>1988–1996</time><span class="era-tag">Dream Team</span></div>
            <h3>A primeira Taça dos Campeões Europeus</h3>
            <p>Como treinador, Cruyff constrói o chamado Dream Team. Em 20 de Maio de 1992, o Barcelona vence a Sampdoria em Wembley e conquista pela primeira vez a Taça dos Campeões Europeus.</p>
          </article>
          <article class="era" data-era="europa">
            <div class="era-top"><time>2003–2008</time><span class="era-tag">Regresso ao topo</span></div>
            <h3>Ronaldinho e a conquista de Paris</h3>
            <p>Com Ronaldinho como figura central, o Barça vence a Liga dos Campeões de 2005/06, derrotando o Arsenal na final de Paris. A equipa volta a afirmar-se no panorama europeu.</p>
          </article>
          <article class="era" data-era="europa">
            <div class="era-top"><time>2008–2012</time><span class="era-tag">Era Guardiola</span></div>
            <h3>Futebol de posse e seis troféus em 2009</h3>
            <p>Com Pep Guardiola, Messi, Xavi e Iniesta, o Barcelona conquista a Liga dos Campeões em 2009 e 2011. Em 2009, torna-se o primeiro clube a vencer seis grandes troféus no mesmo ano civil.</p>
          </article>
          <article class="era" data-era="europa">
            <div class="era-top"><time>2014–2015</time><span class="era-tag">Tridente ofensivo</span></div>
            <h3>A quinta Liga dos Campeões</h3>
            <p>Orientado por Luis Enrique, o Barcelona de Messi, Suárez e Neymar vence a Liga dos Campeões de 2014/15 e completa um triplete: Liga, Taça do Rei e competição europeia.</p>
          </article>
          <article class="era" data-era="moderna">
            <div class="era-top"><time>2017–2023</time><span class="era-tag">Mudança de ciclo</span></div>
            <h3>Renovação e novos protagonistas</h3>
            <p>O clube atravessa mudanças desportivas e financeiras, despede-se de Lionel Messi em 2021 e inicia uma renovação. Sob Xavi Hernández, conquista a Liga e a Supertaça espanhola em 2022/23.</p>
          </article>
          <article class="era" data-era="moderna">
            <div class="era-top"><time>2024–2026</time><span class="era-tag">Nova geração</span></div>
            <h3>Hansi Flick e títulos consecutivos da Liga</h3>
            <p>Com Hansi Flick, o Barça conquista a Liga, a Taça do Rei e a Supertaça em 2024/25. Em 2025/26, vence novamente a Liga e a Supertaça, alcançando o 29.º campeonato espanhol e o 16.º título da Supertaça.</p>
          </article>
        </div>
      </div>
    </section>

    <section class="section" id="lendas">
      <div class="container">
        <div class="section-head">
          <div class="eyebrow">Nomes que marcaram gerações</div>
          <h2>Lendas do Barça</h2>
          <p>Jogadores e treinadores que ajudaram a definir a identidade e os momentos mais memoráveis do clube.</p>
        </div>
        <div class="legend-grid">
          <article class="legend-card">
            <img src="https://images.unsplash.com/photo-1508098682722-e99c43a406b2?auto=format&fit=crop&w=900&q=80" alt="Campo de futebol" loading="lazy">
            <div class="legend-body"><div class="years">FUNDADOR · 1899</div><h3>Joan Gamper</h3><p>Fundador e figura decisiva nos primeiros anos do Barcelona, ajudou a estabelecer as bases da instituição.</p></div>
          </article>
          <article class="legend-card">
            <img src="https://images.unsplash.com/photo-1522778119026-d647f0596c20?auto=format&fit=crop&w=900&q=80" alt="Estádio de futebol" loading="lazy">
            <div class="legend-body"><div class="years">JOGADOR E TREINADOR</div><h3>Johan Cruyff</h3><p>Influenciou o futebol do clube dentro e fora do campo; como treinador, liderou o Dream Team campeão europeu em 1992.</p></div>
          </article>
          <article class="legend-card">
            <img src="https://images.unsplash.com/photo-1522778119026-d647f0596c20?auto=format&fit=crop&w=900&q=80" alt="Estádio de futebol iluminado" loading="lazy">
            <div class="legend-body"><div class="years">2004–2021</div><h3>Lionel Messi</h3><p>Máximo goleador histórico da equipa principal masculina e protagonista de uma das épocas mais vitoriosas do clube.</p></div>
          </article>
          <article class="legend-card">
            <img src="https://images.unsplash.com/photo-1508098682722-e99c43a406b2?auto=format&fit=crop&w=900&q=80" alt="Bola de futebol no relvado" loading="lazy">
            <div class="legend-body"><div class="years">ERA GUARDIOLA</div><h3>Xavi Hernández</h3><p>Maestro do meio-campo, conhecido pela leitura de jogo, precisão de passe e papel central no futebol de posse.</p></div>
          </article>
          <article class="legend-card">
            <img src="https://images.unsplash.com/photo-1522778119026-d647f0596c20?auto=format&fit=crop&w=900&q=80" alt="Estádio de futebol" loading="lazy">
            <div class="legend-body"><div class="years">ERA GUARDIOLA</div><h3>Andrés Iniesta</h3><p>Referência técnica e criativa, decisivo em grandes jogos e símbolo da geração que dominou o futebol europeu.</p></div>
          </article>
          <article class="legend-card">
            <img src="https://images.unsplash.com/photo-1508098682722-e99c43a406b2?auto=format&fit=crop&w=900&q=80" alt="Bola num campo de futebol" loading="lazy">
            <div class="legend-body"><div class="years">NOVA GERAÇÃO</div><h3>Lamine Yamal</h3><p>Um dos rostos da nova geração blaugrana, representa a aposta na formação e no talento jovem da equipa.</p></div>
          </article>
        </div>
        <p class="notice">As fotografias nesta versão são imagens ilustrativas de futebol e estádio, não retratos oficiais dos jogadores. Substitui-as por imagens próprias ou autorizadas antes de uma publicação comercial.</p>
      </div>
    </section>

    <section class="section dark-section" id="titulos">
      <div class="container">
        <div class="section-head">
          <div class="eyebrow">Palmarés masculino</div>
          <h2>Uma sala de troféus histórica</h2>
          <p>Os principais títulos da equipa principal masculina, de acordo com o palmarés oficial do clube consultado em Outubro de 2026.</p>
        </div>
        <div class="trophy-grid">
          <article class="trophy"><div class="number">29</div><h3>Campeonato espanhol</h3><p>Último título: 2025/26.</p></article>
          <article class="trophy"><div class="number">5</div><h3>Liga dos Campeões / Taça dos Campeões</h3><p>1992, 2006, 2009, 2011 e 2015.</p></article>
          <article class="trophy"><div class="number">32</div><h3>Taça do Rei</h3><p>Último título: 2024/25.</p></article>
          <article class="trophy"><div class="number">16</div><h3>Supertaça de Espanha</h3><p>Inclui as conquistas de 2024/25 e 2025/26.</p></article>
          <article class="trophy"><div class="number">5</div><h3>Supertaça Europeia</h3><p>Conquistas em 1992, 1997, 2009, 2011 e 2015.</p></article>
          <article class="trophy"><div class="number">3</div><h3>Mundial de Clubes da FIFA</h3><p>Conquistas em 2009, 2011 e 2015.</p></article>
        </div>
        <p class="disclaimer">Nota de rigor: o número de títulos pode variar conforme a competição e os critérios de contagem. Esta página destaca as competições principais listadas pelo FC Barcelona; consulta a fonte oficial para a lista completa e actualizações.</p>
      </div>
    </section>

    <section class="section" id="actualidade">
      <div class="container">
        <div class="section-head">
          <div class="eyebrow">2025/26 · 2026/27</div>
          <h2>O Barça no presente</h2>
          <p>O capítulo actual combina títulos recentes, formação de jovens jogadores e a continuidade de um projecto desportivo.</p>
        </div>
        <div class="current-grid">
          <article class="current-feature">
            <img src="https://images.unsplash.com/photo-1522778119026-d647f0596c20?auto=format&fit=crop&w=1200&q=85" alt="Estádio de futebol com adeptos" loading="lazy">
            <div class="current-feature-body">
              <div class="eyebrow">Época 2025/26</div>
              <h3>Campeões da Liga pela 29.ª vez</h3>
              <p>O Barcelona confirmou o título da Liga espanhola de 2025/26 em Maio de 2026, defendendo o campeonato conquistado na época anterior. O clube também registou a conquista da Supertaça espanhola na mesma época.</p>
              <a class="btn btn-secondary" href="https://www.fcbarcelona.com/en/football/first-team/news/4501708/the-29th-league-title-in-fc-barcelona-history" target="_blank" rel="noopener noreferrer">Ler notícia oficial ↗</a>
            </div>
          </article>
          <aside class="current-list">
            <div class="eyebrow">Factos recentes</div>
            <div class="current-item"><strong>Hansi Flick</strong><p>O clube anunciou a extensão do contrato do treinador até 30 de Junho de 2028, com opção por mais uma época.</p></div>
            <div class="current-item"><strong>Formação e juventude</strong><p>A aposta em jovens talentos continua a ser uma das marcas do projecto desportivo blaugrana.</p></div>
            <div class="current-item"><strong>Rivalidade histórica</strong><p>O El Clásico frente ao Real Madrid continua a ser um dos jogos mais acompanhados do futebol mundial.</p></div>
            <div class="current-item"><strong>Actualizações futuras</strong><p>Os resultados, o plantel e as notícias mudam ao longo da época. Consulta o portal oficial para dados em tempo real.</p></div>
            <a class="btn btn-primary" href="https://www.fcbarcelona.com/en/football/first-team" target="_blank" rel="noopener noreferrer">Equipa principal ↗</a>
          </aside>
        </div>
      </div>
    </section>

    <section class="section dark-section" id="fontes">
      <div class="container">
        <div class="section-head">
          <div class="eyebrow">Consulta e verifica</div>
          <h2>Fontes oficiais</h2>
          <p>Usa estas páginas para confirmar o palmarés, aprofundar a cronologia e acompanhar as notícias do clube.</p>
        </div>
        <div class="source-list">
          <a class="source-link" href="https://www.fcbarcelona.com/en/club/history/decade-by-decade" target="_blank" rel="noopener noreferrer"><strong>História década a década</strong><span>A cronologia oficial do FC Barcelona desde a fundação.</span><em>fcbarcelona.com ↗</em></a>
          <a class="source-link" href="https://www.fcbarcelona.com/en/football/primer-equipo/palmares" target="_blank" rel="noopener noreferrer"><strong>Palmarés oficial</strong><span>Lista de títulos e épocas das principais competições.</span><em>fcbarcelona.com ↗</em></a>
          <a class="source-link" href="https://www.fcbarcelona.com/en/football/first-team" target="_blank" rel="noopener noreferrer"><strong>Equipa principal e notícias</strong><span>Informação recente sobre a equipa masculina principal.</span><em>fcbarcelona.com ↗</em></a>
        </div>
        <p class="disclaimer">Barça History é um projecto informativo independente, sem afiliação oficial ao FC Barcelona. O nome e a identidade do clube pertencem aos respectivos titulares. As fotografias externas dependem da disponibilidade dos respectivos serviços; para um projecto público ou comercial, confirma as licenças de utilização.</p>
      </div>
    </section>
  </main>

  <footer>
    <div class="container footer-inner">
      <div><strong>BARÇA HISTORY</strong> · Um arquivo para quem vive o futebol.</div>
      <div>Conteúdo histórico consultado em Outubro de 2026 · <a href="#inicio">Voltar ao topo ↑</a></div>
    </div>
  </footer>

  <script>
    // Menu móvel
    const menuToggle = document.getElementById('menuToggle');
    const navLinks = document.getElementById('navLinks');

    menuToggle.addEventListener('click', () => {
      const isOpen = navLinks.classList.toggle('open');
      menuToggle.setAttribute('aria-expanded', String(isOpen));
      menuToggle.textContent = isOpen ? '✕ Fechar' : '☰ Menu';
    });

    navLinks.querySelectorAll('a').forEach(link => {
      link.addEventListener('click', () => {
        navLinks.classList.remove('open');
        menuToggle.setAttribute('aria-expanded', 'false');
        menuToggle.textContent = '☰ Menu';
      });
    });

    // Filtros interactivos da cronologia
    const filterButtons = document.querySelectorAll('.filter-btn');
    const eras = document.querySelectorAll('.era');

    filterButtons.forEach(button => {
      button.addEventListener('click', () => {
        const filter = button.dataset.filter;
        filterButtons.forEach(item => {
          const active = item === button;
          item.classList.toggle('active', active);
          item.setAttribute('aria-pressed', String(active));
        });
        eras.forEach(era => {
          era.hidden = filter !== 'all' && era.dataset.era !== filter;
        });
      });
    });

    // Actualiza automaticamente o ano do rodapé sem alterar o conteúdo histórico.
    // A data histórica de consulta indicada na página é intencionalmente fixa.
    document.title = 'Barça History — Mais do que um clube';
  </script>
</body>
</html>
