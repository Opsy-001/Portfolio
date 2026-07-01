# Portfolio
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<!-- ✏️ EDIT: Page title shown in browser tab -->
<title>Abigail Abiodun — Data Analyst Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Plus+Jakarta+Sans:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
  *,*::before,*::after{box-sizing:border-box;margin:0;padding:0}

  /* =============================================
     🎨 COLOUR PALETTE — change hex values here
     INK     = dark background
     CORAL   = primary accent (buttons, highlights)
     AMBER   = secondary accent (awards, tags)
     CREAM   = light section background
     SAND    = card backgrounds on cream sections
     CHARCOAL= body text on light backgrounds
  ============================================= */
  :root{
    --ink:#13111A;
    --ink2:#1E1B28;
    --coral:#F04E37;
    --coral-dim:rgba(240,78,55,.12);
    --amber:#F5A623;
    --amber-dim:rgba(245,166,35,.1);
    --cream:#FAF7F2;
    --sand:#F2EDE6;
    --white:#fff;
    --charcoal:#2D2926;
    --gray:#7A7068;
    --border:#E8E0D6;
    --card-dark:rgba(255,255,255,.04);
    --border-dark:rgba(255,255,255,.09);
  }

  html{scroll-behavior:smooth}
  body{font-family:'Plus Jakarta Sans',sans-serif;background:var(--white);color:var(--charcoal);line-height:1.6}

  /* ── NAV ── */
  nav{position:fixed;top:0;left:0;right:0;z-index:100;background:rgba(19,17,26,.97);backdrop-filter:blur(10px);padding:0 2rem}
  .nav-inner{max-width:1100px;margin:auto;display:flex;align-items:center;justify-content:space-between;height:62px}
  .nav-logo{font-family:'Space Grotesk',sans-serif;font-weight:700;color:var(--white);font-size:1.1rem;letter-spacing:-.01em}
  .nav-logo span{color:var(--coral)}
  .nav-links{display:flex;gap:2rem;list-style:none}
  .nav-links a{color:rgba(255,255,255,.6);text-decoration:none;font-size:.8rem;font-weight:500;letter-spacing:.06em;text-transform:uppercase;transition:color .2s}
  .nav-links a:hover,.nav-links a.active{color:var(--coral)}
  .nav-cta{background:var(--coral);color:var(--white);padding:.42rem 1.2rem;border-radius:6px;font-weight:700;font-size:.8rem;text-decoration:none;letter-spacing:.03em;transition:opacity .2s}
  .nav-cta:hover{opacity:.88}

  /* ── SHARED ── */
  section{padding:96px 2rem}
  .container{max-width:1100px;margin:auto}
  .eyebrow{font-size:.7rem;font-weight:700;letter-spacing:.16em;text-transform:uppercase;color:var(--coral);margin-bottom:.75rem;display:flex;align-items:center;gap:.5rem}
  .eyebrow::before{content:'';display:inline-block;width:24px;height:2px;background:var(--coral)}
  .section-title{font-family:'Space Grotesk',sans-serif;font-size:clamp(1.8rem,3.2vw,2.5rem);font-weight:700;color:var(--ink);line-height:1.1;margin-bottom:.9rem}
  .section-sub{color:var(--gray);font-size:.95rem;max-width:540px;line-height:1.8}

  /* ── HERO ── */
  #hero{padding:136px 2rem 96px;background:var(--ink);overflow:hidden;position:relative}
  #hero::before{content:'';position:absolute;top:0;right:0;width:50%;height:100%;background:radial-gradient(ellipse at 90% 40%,rgba(240,78,55,.08) 0%,transparent 65%);pointer-events:none}
  #hero::after{content:'';position:absolute;bottom:-60px;left:-60px;width:320px;height:320px;border-radius:50%;background:radial-gradient(circle,rgba(245,166,35,.06),transparent 70%);pointer-events:none}
  .hero-inner{max-width:1100px;margin:auto;display:grid;grid-template-columns:1fr 1fr;gap:4.5rem;align-items:center}

  /* ✏️ EDIT HERO TEXT in the HTML section below */
  .hero-tag{display:inline-flex;align-items:center;gap:.5rem;background:rgba(240,78,55,.1);border:1px solid rgba(240,78,55,.25);color:var(--coral);padding:.32rem .9rem;border-radius:20px;font-size:.72rem;font-weight:700;letter-spacing:.07em;text-transform:uppercase;margin-bottom:1.5rem}
  .hero-tag::before{content:'●';font-size:.5rem;animation:pulse 2s infinite}
  @keyframes pulse{0%,100%{opacity:1}50%{opacity:.3}}
  .hero-title{font-family:'Space Grotesk',sans-serif;font-size:clamp(2.1rem,4.5vw,3.3rem);font-weight:700;color:var(--white);line-height:1.08;margin-bottom:1.2rem;letter-spacing:-.02em}
  .hero-title em{font-style:normal;color:var(--coral)}
  .hero-sub{color:rgba(255,255,255,.55);font-size:1rem;line-height:1.8;margin-bottom:1.9rem;max-width:460px}
  .hero-tools{display:flex;flex-wrap:wrap;gap:.5rem;margin-bottom:2.1rem}
  .tool-pill{background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.1);color:rgba(255,255,255,.75);padding:.28rem .8rem;border-radius:20px;font-size:.75rem;font-weight:500}
  .hero-btns{display:flex;gap:1rem;flex-wrap:wrap}
  .btn-primary{background:var(--coral);color:var(--white);padding:.75rem 1.8rem;border-radius:8px;font-weight:700;font-size:.88rem;text-decoration:none;transition:opacity .2s;letter-spacing:.02em}
  .btn-primary:hover{opacity:.88}
  .btn-ghost{border:1.5px solid rgba(255,255,255,.22);color:rgba(255,255,255,.85);padding:.75rem 1.8rem;border-radius:8px;font-weight:600;font-size:.88rem;text-decoration:none;transition:all .25s}
  .btn-ghost:hover{border-color:var(--coral);color:var(--coral)}

  /* Hero chart card */
  .chart-card{background:var(--card-dark);border:1px solid var(--border-dark);border-radius:18px;padding:1.8rem}
  .chart-label{font-size:.68rem;font-weight:600;color:rgba(255,255,255,.38);letter-spacing:.09em;text-transform:uppercase;margin-bottom:1.1rem}
  .bars{display:flex;align-items:flex-end;gap:10px;height:130px;padding-bottom:8px;border-bottom:1px solid rgba(255,255,255,.07)}
  .bar-wrap{display:flex;flex-direction:column;align-items:center;gap:5px;flex:1}
  .bar{width:100%;border-radius:5px 5px 0 0;transition:height 1.2s cubic-bezier(.4,0,.2,1)}
  .bar-val{font-size:.62rem;color:rgba(255,255,255,.4);font-weight:500}
  .bar-name{font-size:.56rem;color:rgba(255,255,255,.3);text-align:center;margin-top:3px;line-height:1.2}
  .stat-row{display:grid;grid-template-columns:repeat(3,1fr);gap:.65rem;margin-top:1.1rem}
  .stat-box{background:rgba(240,78,55,.08);border:1px solid rgba(240,78,55,.12);border-radius:9px;padding:.7rem;text-align:center}
  .stat-val{font-family:'Space Grotesk',sans-serif;font-size:1rem;font-weight:700;color:var(--coral)}
  .stat-lab{font-size:.58rem;color:rgba(255,255,255,.38);margin-top:2px}
  .award-row{display:flex;align-items:center;gap:.75rem;background:var(--amber-dim);border:1px solid rgba(245,166,35,.2);border-radius:10px;padding:.8rem .95rem;margin-top:.95rem}
  .aw-icon{font-size:1.3rem}
  .aw-text{font-size:.73rem;color:rgba(255,255,255,.65);line-height:1.4}
  .aw-text strong{color:var(--amber);display:block;font-size:.76rem}

  /* ── SERVICES ── */
  #services{background:var(--cream)}
  .services-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(235px,1fr));gap:1.4rem;margin-top:3rem}
  .svc-card{background:var(--white);border-radius:16px;padding:1.9rem;border:1px solid var(--border);transition:transform .22s,box-shadow .22s;position:relative;overflow:hidden}
  .svc-card::after{content:'';position:absolute;bottom:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--coral),var(--amber));transform:scaleX(0);transform-origin:left;transition:transform .3s}
  .svc-card:hover{transform:translateY(-5px);box-shadow:0 16px 40px rgba(19,17,26,.1)}
  .svc-card:hover::after{transform:scaleX(1)}
  .svc-icon{font-size:2rem;margin-bottom:1rem;display:block}
  .svc-title{font-family:'Space Grotesk',sans-serif;font-weight:700;font-size:1.02rem;color:var(--ink);margin-bottom:.6rem}
  .svc-desc{font-size:.85rem;color:var(--gray);line-height:1.7}
  .svc-tags{display:flex;flex-wrap:wrap;gap:.4rem;margin-top:1rem}
  .stag{background:var(--coral-dim);color:var(--coral);font-size:.68rem;font-weight:700;padding:.2rem .6rem;border-radius:20px}

  /* ── CASE STUDIES ── */
  #casestudies{background:var(--white)}
  .cs-wrap{background:var(--ink);border-radius:22px;overflow:hidden;margin-top:3rem}
  .cs-grid{display:grid;grid-template-columns:1.15fr 1fr}
  .cs-left{padding:3rem}
  .cs-ey{font-size:.68rem;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--coral);margin-bottom:.7rem}
  .cs-title{font-family:'Space Grotesk',sans-serif;font-size:1.55rem;font-weight:700;color:var(--white);line-height:1.2;margin-bottom:.95rem;letter-spacing:-.01em}
  .cs-desc{color:rgba(255,255,255,.52);font-size:.87rem;line-height:1.75;margin-bottom:1.5rem}
  .cs-metrics{display:grid;grid-template-columns:repeat(2,1fr);gap:.9rem;margin-bottom:1.5rem}
  .metric{background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.07);border-radius:10px;padding:.95rem}
  .metric-val{font-family:'Space Grotesk',sans-serif;font-size:1.4rem;font-weight:700;color:var(--coral)}
  .metric-lab{font-size:.68rem;color:rgba(255,255,255,.38);margin-top:3px;line-height:1.3}
  .cs-tools{display:flex;gap:.45rem;flex-wrap:wrap;margin-bottom:1.4rem}
  .cs-tool{background:rgba(255,255,255,.07);color:rgba(255,255,255,.62);font-size:.7rem;padding:.22rem .65rem;border-radius:20px;font-weight:500}
  .cs-link{display:inline-flex;align-items:center;gap:.4rem;color:var(--coral);font-weight:700;font-size:.85rem;text-decoration:none;transition:gap .2s}
  .cs-link:hover{gap:.7rem}
  .cs-right{background:rgba(255,255,255,.022);border-left:1px solid rgba(255,255,255,.06);padding:2.5rem;display:flex;flex-direction:column;gap:.95rem;justify-content:center}
  .finding{background:rgba(255,255,255,.03);border:1px solid rgba(255,255,255,.06);border-left:3px solid var(--coral);border-radius:10px;padding:.95rem}
  .fnd-label{font-size:.65rem;font-weight:700;color:var(--coral);letter-spacing:.08em;text-transform:uppercase;margin-bottom:.35rem}
  .fnd-text{font-size:.81rem;color:rgba(255,255,255,.6);line-height:1.6}
  .fnd-text strong{color:var(--white)}

  /* ── TESTIMONIALS ── */
  #testimonials{background:var(--cream)}
  .testi-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:1.4rem;margin-top:3rem}
  .testi-card{background:var(--white);border-radius:16px;padding:1.9rem;border:1px solid var(--border)}
  .quote-mark{font-size:3.2rem;font-family:Georgia,serif;color:var(--coral);line-height:.5;margin-bottom:1rem;display:block;opacity:.3}
  .testi-text{font-size:.88rem;color:#4B4543;line-height:1.75;font-style:italic;margin-bottom:1.5rem}
  .testi-author{display:flex;align-items:center;gap:.75rem}
  .t-avatar{width:40px;height:40px;border-radius:50%;background:var(--ink);display:flex;align-items:center;justify-content:center;color:var(--white);font-weight:700;font-size:.85rem;font-family:'Space Grotesk',sans-serif;flex-shrink:0}
  .t-name{font-weight:700;font-size:.86rem;color:var(--ink)}
  .t-role{font-size:.73rem;color:var(--gray)}
  .testi-placeholder{display:flex;flex-direction:column;justify-content:center;align-items:center;text-align:center;min-height:200px;background:var(--cream);border:1.5px dashed rgba(240,78,55,.3)}
  .tp-icon{font-size:1.9rem;margin-bottom:.7rem}
  .tp-title{font-family:'Space Grotesk',sans-serif;font-weight:700;color:var(--ink);font-size:.92rem;margin-bottom:.4rem}
  .tp-sub{font-size:.78rem;color:var(--gray);font-style:italic}
  .tp-btn{display:inline-block;margin-top:1rem;background:var(--ink);color:var(--white);padding:.5rem 1.2rem;border-radius:8px;font-size:.78rem;font-weight:700;text-decoration:none;transition:background .2s}
  .tp-btn:hover{background:var(--coral)}

  /* ── CONTACT ── */
  #contact{background:var(--ink);position:relative;overflow:hidden}
  #contact::before{content:'';position:absolute;bottom:-80px;right:-80px;width:500px;height:500px;background:radial-gradient(circle,rgba(240,78,55,.07),transparent 65%);pointer-events:none}
  .contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:5rem;align-items:start}
  .contact-eyebrow{color:var(--coral)}
  .contact-title{font-family:'Space Grotesk',sans-serif;font-size:clamp(1.8rem,3vw,2.4rem);font-weight:700;color:var(--white);line-height:1.12;margin-bottom:.95rem;letter-spacing:-.02em}
  .contact-sub{color:rgba(255,255,255,.48);font-size:.92rem;line-height:1.8;margin-bottom:2rem}
  .clinks{display:flex;flex-direction:column;gap:.95rem}
  .clink{display:flex;align-items:center;gap:.9rem;color:rgba(255,255,255,.72);text-decoration:none;font-size:.88rem;transition:color .2s}
  .clink:hover{color:var(--coral)}
  .clink-icon{width:38px;height:38px;background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.08);border-radius:9px;display:flex;align-items:center;justify-content:center;font-size:.95rem;flex-shrink:0}
  .form-card{background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.08);border-radius:18px;padding:2rem}
  .fg{margin-bottom:1.2rem}
  .fg label{display:block;font-size:.7rem;font-weight:700;color:rgba(255,255,255,.4);letter-spacing:.07em;text-transform:uppercase;margin-bottom:.5rem}
  .fg input,.fg textarea{width:100%;background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.1);border-radius:9px;padding:.72rem 1rem;color:var(--white);font-family:'Plus Jakarta Sans',sans-serif;font-size:.86rem;outline:none;transition:border-color .2s;resize:none}
  .fg input:focus,.fg textarea:focus{border-color:var(--coral)}
  .fg input::placeholder,.fg textarea::placeholder{color:rgba(255,255,255,.2)}
  .form-btn{width:100%;background:var(--coral);color:var(--white);border:none;border-radius:9px;padding:.85rem;font-family:'Space Grotesk',sans-serif;font-weight:700;font-size:.92rem;cursor:pointer;transition:opacity .2s;letter-spacing:.02em}
  .form-btn:hover{opacity:.88}

  /* ── FOOTER ── */
  footer{background:#0A0810;padding:1.5rem 2rem;text-align:center;border-top:1px solid rgba(255,255,255,.05)}
  footer p{font-size:.75rem;color:rgba(255,255,255,.25)}
  footer span{color:var(--coral)}

  /* ── RESPONSIVE ── */
  @media(max-width:768px){
    .hero-inner,.cs-grid,.contact-grid{grid-template-columns:1fr}
    .hero-chart,.cs-right{display:none}
    .nav-links{display:none}
    section{padding:70px 1.5rem}
  }
</style>
</head>
<body>

<!-- ═══════════════════════════════════════════
     NAV — ✏️ Edit your name and nav links here
═══════════════════════════════════════════ -->
<nav>
  <div class="nav-inner">
    <div class="nav-logo">Abigail<span>.</span></div><!-- ✏️ Your name -->
    <ul class="nav-links">
      <li><a href="#services">Services</a></li>
      <li><a href="#casestudies">Case Studies</a></li>
      <li><a href="#testimonials">Testimonials</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <a href="#contact" class="nav-cta">Hire Me</a>
  </div>
</nav>

<!-- ═══════════════════════════════════════════
     HERO / INTRODUCTION
     ✏️ Edit: tag, title, subtitle, tools, buttons
═══════════════════════════════════════════ -->
<section id="hero">
  <div class="hero-inner container">

    <!-- LEFT: text -->
    <div>
      <div class="hero-tag">Open to Remote &amp; International Roles</div><!-- ✏️ Status tag -->
      <h1 class="hero-title">
        I turn raw data into<br><!-- ✏️ Main headline -->
        <em>decisions that matter.</em>
      </h1>
      <p class="hero-sub">
        <!-- ✏️ One-paragraph intro about yourself -->
        Data Analyst specialising in Power BI, SQL, Excel, and DAX.
        I build interactive dashboards and surface insights that help
        organisations cut costs, operate smarter, and serve people better.
      </p>
      <div class="hero-tools">
        <!-- ✏️ Add or remove tool pills -->
        <span class="tool-pill">Power BI</span>
        <span class="tool-pill">SQL</span>
        <span class="tool-pill">Excel</span>
        <span class="tool-pill">DAX</span>
        <span class="tool-pill">Power Query</span>
        <span class="tool-pill">Data Modeling</span>
      </div>
      <div class="hero-btns">
        <a href="#casestudies" class="btn-primary">View My Work</a><!-- ✏️ CTA 1 -->
        <a href="#contact" class="btn-ghost">Get In Touch</a><!-- ✏️ CTA 2 -->
      </div>
    </div>

    <!-- RIGHT: animated chart card -->
    <div class="hero-chart">
      <div class="chart-card">
        <div class="chart-label">Healthcare Analytics — Cost by Payer ($M)</div><!-- ✏️ Chart title -->
        <div class="bars">
          <!-- ✏️ Bar values and labels (bar heights are set in JS below) -->
          <div class="bar-wrap"><div class="bar-val">49M</div><div class="bar" id="b1" style="height:0;background:linear-gradient(180deg,#F04E37,#b83525)"></div><div class="bar-name">No<br>Insurance</div></div>
          <div class="bar-wrap"><div class="bar-val">25M</div><div class="bar" id="b2" style="height:0;background:rgba(240,78,55,.6)"></div><div class="bar-name">Medicare</div></div>
          <div class="bar-wrap"><div class="bar-val">9M</div><div class="bar" id="b3" style="height:0;background:rgba(240,78,55,.42)"></div><div class="bar-name">Medicaid</div></div>
          <div class="bar-wrap"><div class="bar-val">4M</div><div class="bar" id="b4" style="height:0;background:rgba(240,78,55,.28)"></div><div class="bar-name">Humana</div></div>
          <div class="bar-wrap"><div class="bar-val">3M</div><div class="bar" id="b5" style="height:0;background:rgba(240,78,55,.16)"></div><div class="bar-name">BCBS</div></div>
        </div>
        <div class="stat-row">
          <!-- ✏️ Key stats below the chart -->
          <div class="stat-box"><div class="stat-val">28K+</div><div class="stat-lab">Patient Records</div></div>
          <div class="stat-box"><div class="stat-val">33%</div><div class="stat-lab">Readmission Rate</div></div>
          <div class="stat-box"><div class="stat-val">$101M</div><div class="stat-lab">Total Costs</div></div>
        </div>
        <div class="award-row">
          <div class="aw-icon">🏆</div>
          <!-- ✏️ Award text -->
          <div class="aw-text"><strong>Best Presentation Award</strong>STC Mentorship Cohort 3, May 2026</div>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- ═══════════════════════════════════════════
     SERVICES
     ✏️ Edit each service card: icon, title, desc, tags
═══════════════════════════════════════════ -->
<section id="services">
  <div class="container">
    <div class="eyebrow">What I Do</div>
    <h2 class="section-title">Services</h2>
    <p class="section-sub">From raw data to boardroom-ready insights — here is how I help organisations make smarter, faster decisions.</p>

    <div class="services-grid">

      <!-- ✏️ SERVICE CARD 1 -->
      <div class="svc-card">
        <span class="svc-icon">📊</span>
        <div class="svc-title">Dashboard Development</div>
        <div class="svc-desc">Interactive, multi-page Power BI dashboards built from your raw data — covering KPIs, trends, and drill-down analysis tailored to your specific business questions.</div>
        <div class="svc-tags"><span class="stag">Power BI</span><span class="stag">DAX</span><span class="stag">KPI Design</span></div>
      </div>

      <!-- ✏️ SERVICE CARD 2 -->
      <div class="svc-card">
        <span class="svc-icon">🔍</span>
        <div class="svc-title">Data Analysis &amp; Reporting</div>
        <div class="svc-desc">End-to-end analysis using SQL, Excel, and Power Query — cleaning, transforming, modeling, and surfacing insights that are accurate and decision-ready.</div>
        <div class="svc-tags"><span class="stag">SQL</span><span class="stag">Excel</span><span class="stag">Power Query</span></div>
      </div>

      <!-- ✏️ SERVICE CARD 3 -->
      <div class="svc-card">
        <span class="svc-icon">💡</span>
        <div class="svc-title">Insight Communication</div>
        <div class="svc-desc">Translating complex findings into clear stakeholder-ready presentations and reports — bridging the gap between data and decision-makers at every level.</div>
        <div class="svc-tags"><span class="stag">Storytelling</span><span class="stag">Reporting</span><span class="stag">Presentations</span></div>
      </div>

      <!-- ✏️ SERVICE CARD 4 -->
      <div class="svc-card">
        <span class="svc-icon">🎓</span>
        <div class="svc-title">Data Analytics Training</div>
        <div class="svc-desc">Hands-on coaching in Power BI, Excel, SQL, and DAX for aspiring analysts — covering real-world workflows from data cleaning to dashboard delivery.</div>
        <div class="svc-tags"><span class="stag">Mentoring</span><span class="stag">Curriculum</span><span class="stag">Coaching</span></div>
      </div>

    </div>
  </div>
</section>

<!-- ═══════════════════════════════════════════
     CASE STUDIES
     ✏️ Edit project title, description, metrics, findings, GitHub link
═══════════════════════════════════════════ -->
<section id="casestudies">
  <div class="container">
    <div class="eyebrow">Portfolio</div>
    <h2 class="section-title">Case Studies</h2>
    <p class="section-sub">Real projects, real data, real decisions — here is how I approach analytics problems end-to-end.</p>

    <div class="cs-wrap">
      <div class="cs-grid">

        <!-- LEFT: project details -->
        <div class="cs-left">
          <div class="cs-ey">Healthcare Analytics · Power BI · 2026</div><!-- ✏️ Project type & year -->
          <h3 class="cs-title">Patient Analytics Dashboard — Massachusetts General Hospital</h3><!-- ✏️ Project title -->
          <p class="cs-desc">
            <!-- ✏️ Project description -->
            Analyzed a synthetic healthcare dataset of 28,000+ patient records (2011–2022) to uncover cost drivers, demographic patterns, length-of-stay behaviour, and readmission risk. Built a 4-page interactive Power BI report and delivered actionable recommendations targeting cost optimisation, operational efficiency, and patient outcomes.
          </p>
          <div class="cs-metrics">
            <!-- ✏️ Edit the 4 key metrics -->
            <div class="metric"><div class="metric-val">28,000+</div><div class="metric-lab">Patient encounters analyzed</div></div>
            <div class="metric"><div class="metric-val">$49M</div><div class="metric-lab">Uninsured cost gap identified</div></div>
            <div class="metric"><div class="metric-val">33.04%</div><div class="metric-lab">Inpatient readmission rate tracked</div></div>
            <div class="metric"><div class="metric-val">4 pages</div><div class="metric-lab">Interactive dashboard report</div></div>
          </div>
          <div class="cs-tools">
            <!-- ✏️ Tools used -->
            <span class="cs-tool">Power BI</span><span class="cs-tool">DAX</span><span class="cs-tool">Excel</span><span class="cs-tool">Power Query</span><span class="cs-tool">Data Modeling</span>
          </div>
          <a href="https://github.com/Opsy-001/massachusetts-general-hospital-analysis" target="_blank" class="cs-link">View on GitHub →</a><!-- ✏️ Your GitHub link -->
        </div>

        <!-- RIGHT: key findings -->
        <div class="cs-right">
          <!-- ✏️ Edit each finding label and text -->
          <div class="finding">
            <div class="fnd-label">Cost Insight</div>
            <div class="fnd-text">Uninsured patients generate <strong>$49M in treatment costs</strong> — the highest of any payer category, with near-zero insurance coverage to offset it.</div>
          </div>
          <div class="finding">
            <div class="fnd-label">Readmission Trend</div>
            <div class="fnd-text">Rates fell from <strong>60% (2011) to 12% (2020)</strong> before rising again to 27% in 2022, flagging a post-pandemic risk rebound requiring intervention.</div>
          </div>
          <div class="finding">
            <div class="fnd-label">Demographic Risk</div>
            <div class="fnd-text">Patients aged <strong>61–80 face the highest readmission risk at 37.57%</strong>, indicating older inpatients need targeted follow-up care protocols.</div>
          </div>
          <div class="finding">
            <div class="fnd-label">Procedure Cost Driver</div>
            <div class="fnd-text">Myocardial Infarction averages <strong>$66K per encounter</strong> — the costliest procedure — making cardiac care the primary cost-reduction lever.</div>
          </div>
        </div>

      </div>
    </div>
  </div>
</section>

<!-- ═══════════════════════════════════════════
     TESTIMONIALS
     ✏️ Edit each quote, name, and role.
     Add more .testi-card blocks to add more testimonials.
═══════════════════════════════════════════ -->
<section id="testimonials">
  <div class="container">
    <div class="eyebrow">Social Proof</div>
    <h2 class="section-title">Testimonials</h2>
    <p class="section-sub">What mentors, colleagues, and students say about working with me.</p>

    <div class="testi-grid">

      <!-- ✏️ TESTIMONIAL 1 -->
      <div class="testi-card">
        <span class="quote-mark">"</span>
        <p class="testi-text">Abigail demonstrated outstanding analytical thinking and an impressive ability to communicate complex data findings clearly. Her healthcare dashboard project stood out for its depth, accuracy, and the quality of her recommendations.</p>
        <div class="testi-author">
          <div class="t-avatar">KI</div><!-- ✏️ Initials -->
          <div>
            <div class="t-name">Kaosarat Ibrahim</div><!-- ✏️ Full name -->
            <div class="t-role">Founder, Skills To Career</div><!-- ✏️ Role -->
          </div>
        </div>
      </div>

      <!-- ✏️ TESTIMONIAL 2 -->
      <div class="testi-card">
        <span class="quote-mark">"</span>
        <p class="testi-text">What stood out in Abigail's class was how she broke down complex DAX formulas into steps I could actually follow. She is patient, knowledgeable, and genuinely invested in helping learners succeed.</p>
        <div class="testi-author">
          <div class="t-avatar">ST</div><!-- ✏️ Initials -->
          <div>
            <div class="t-name">Student Testimonial</div><!-- ✏️ Replace with real name when you have one -->
            <div class="t-role">Digital World Tech Academy</div><!-- ✏️ Role -->
          </div>
        </div>
      </div>

      <!-- Placeholder card — remove once you have a 3rd real testimonial -->
      <div class="testi-card testi-placeholder">
        <div class="tp-icon">✨</div>
        <div class="tp-title">Your testimonial here</div>
        <div class="tp-sub">Worked together? I would love to feature your feedback.</div>
        <a href="#contact" class="tp-btn">Leave a Testimonial</a>
      </div>

    </div>
  </div>
</section>

<!-- ═══════════════════════════════════════════
     CONTACT
     ✏️ Edit your email, LinkedIn, GitHub, location
     and the form fields if needed
═══════════════════════════════════════════ -->
<section id="contact">
  <div class="container">
    <div class="contact-grid">

      <!-- LEFT: contact info -->
      <div>
        <div class="eyebrow contact-eyebrow">Let's Work Together</div>
        <h2 class="contact-title">Have a data problem I can solve?</h2><!-- ✏️ Contact headline -->
        <p class="contact-sub">
          <!-- ✏️ Contact intro paragraph -->
          Whether you need a dashboard built, a dataset analyzed, or a data analyst to join your team — I am open to remote and international opportunities.
        </p>
        <div class="clinks">
          <!-- ✏️ Update your email, LinkedIn URL, GitHub URL, location -->
          <a href="mailto:abigaailopeyemi001@gmail.com" class="clink"><div class="clink-icon">📧</div>abigaailopeyemi001@gmail.com</a>
          <a href="https://linkedin.com/in/abigail-abiodun-0205903a7" target="_blank" class="clink"><div class="clink-icon">💼</div>linkedin.com/in/abigail-abiodun</a>
          <a href="https://github.com/Opsy-001" target="_blank" class="clink"><div class="clink-icon">🐙</div>github.com/Opsy-001</a>
          <div class="clink"><div class="clink-icon">📍</div>Lagos, Nigeria · Open to Remote &amp; Relocation</div>
        </div>
      </div>

      <!-- RIGHT: contact form -->
      <div class="form-card">
        <div class="fg"><label>Your Name</label><input type="text" placeholder="e.g. Sarah Johnson"/></div>
        <div class="fg"><label>Email Address</label><input type="email" placeholder="your@email.com"/></div>
        <div class="fg"><label>Subject</label><input type="text" placeholder="e.g. Data Analyst Role at Acme Corp"/></div>
        <div class="fg"><label>Message</label><textarea rows="4" placeholder="Tell me about your project or opportunity..."></textarea></div>
        <button class="form-btn">Send Message →</button>
      </div>

    </div>
  </div>
</section>

<!-- ═══════════════════════════════════════════
     FOOTER — ✏️ Edit your name and year
═══════════════════════════════════════════ -->
<footer>
  <p>© 2026 <span>Abigail Abiodun Opeyemi</span> · Data Analyst · Built with purpose, powered by data.</p>
</footer>

<script>
  // ── Animate bars on page load ──
  // ✏️ Change the h: values to adjust bar heights (in pixels, max ~120)
  window.addEventListener('load', () => {
    const bars = [
      {id:'b1', h:120},
      {id:'b2', h:61},
      {id:'b3', h:22},
      {id:'b4', h:10},
      {id:'b5', h:7}
    ];
    setTimeout(() => {
      bars.forEach((b, i) => {
        setTimeout(() => {
          const el = document.getElementById(b.id);
          if(el) el.style.height = b.h + 'px';
        }, i * 110);
      });
    }, 500);
  });

  // ── Active nav highlight on scroll ──
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.nav-links a');
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(s => { if(window.scrollY >= s.offsetTop - 80) current = s.id; });
    navLinks.forEach(a => {
      a.style.color = a.getAttribute('href') === '#' + current
        ? 'var(--coral)' : 'rgba(255,255,255,.6)';
    });
  });
</script>

</body>
</html>
