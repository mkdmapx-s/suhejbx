
<html lang="sq">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<meta name="theme-color" content="#000000"/>
<title>SUHEJBX — Web Development, Video Marketing & Social Media</title>
<meta name="description" content="SUHEJBX - Zhvillim Web, Video Marketing dhe Menaxhim i Rrjeteve Sociale për biznese në Evropë dhe Ballkan."/>
<link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ctext y='.9em' font-size='90'%3E%F0%9F%9A%80%3C/text%3E%3C/svg%3E"/>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=Playfair+Display:wght@500;600;700&family=Poppins:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#000000;
  --white:#ffffff;
  --off:#f2f2f2;
  --blue:#3B82F6;
  --blue-dark:#2563EB;
  --gray:#8a8a8a;
  --gray-light:#c9c9c9;
  --green:#5E9C3E;
  --radius:18px;
}
html{scroll-behavior:smooth;overflow-x:hidden;width:100%}
body{background:var(--bg);color:var(--white);font-family:'Poppins',sans-serif;font-weight:400;overflow-x:hidden;line-height:1.65}
img,svg{max-width:100%;display:block}
a{color:inherit;text-decoration:none}
ul{list-style:none}
section{position:relative}
.container{max-width:1280px;margin:0 auto;padding:0 2rem}

/* NOISE OVERLAY */
.noise{position:fixed;inset:0;z-index:5;pointer-events:none;opacity:.045;mix-blend-mode:overlay;background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E")}

/* ══════════════ NAV ══════════════ */
.nav{position:fixed;top:0;left:0;right:0;z-index:300;display:flex;align-items:center;justify-content:space-between;padding:1.1rem 3rem;background:rgba(0,0,0,.45);backdrop-filter:blur(14px);border-bottom:1px solid rgba(255,255,255,.06);transition:background .3s,border-color .3s}
.nav.scrolled{background:rgba(0,0,0,.85);border-color:rgba(255,255,255,.1)}
.nav-logo{display:flex;align-items:center;gap:.45rem;font-weight:800;font-size:1.25rem;letter-spacing:.08em;color:#fff}
.nav-badge{width:17px;height:17px;flex-shrink:0}
.nav-links{display:flex;align-items:center;gap:2.1rem}
.nav-links a{font-size:.85rem;font-weight:500;color:var(--gray-light);transition:color .25s}
.nav-links a:hover{color:var(--blue)}
.nav-cta{background:var(--blue);color:#fff !important;padding:.6rem 1.4rem;border-radius:999px;font-weight:600;font-size:.82rem;transition:background .25s,transform .25s}
.nav-cta:hover{background:var(--blue-dark);transform:translateY(-2px)}
.nav-toggle{display:none;flex-direction:column;gap:5px;background:none;border:none;cursor:pointer;padding:6px;z-index:310}
.nav-toggle span{width:22px;height:2px;background:#fff;border-radius:2px;transition:transform .25s,opacity .25s}
.nav-toggle.open span:nth-child(1){transform:translateY(7px) rotate(45deg)}
.nav-toggle.open span:nth-child(2){opacity:0}
.nav-toggle.open span:nth-child(3){transform:translateY(-7px) rotate(-45deg)}

/* ══════════════ HERO ══════════════ */
.hero{min-height:100vh;display:flex;align-items:center;padding:7rem 0 3rem;overflow:hidden}
.blob{position:absolute;z-index:1;pointer-events:none;fill:#fff}
.blob-tl{top:-90px;left:-110px;width:380px}
.blob-br{bottom:-110px;right:-130px;width:420px;transform:rotate(180deg)}

.hero-grid{display:grid;grid-template-columns:1.05fr 1fr;gap:2rem;align-items:center;max-width:1280px;margin:0 auto;padding:0 3rem;width:100%;position:relative;z-index:2}
.hero-text{display:flex;flex-direction:column;gap:2.1rem}
.logo-row{display:flex;align-items:flex-start;gap:.9rem;max-width:100%;min-width:0}
.logo{font-weight:800;font-size:clamp(2.1rem,8vw,4.6rem);letter-spacing:.02em;line-height:1;color:#fff;opacity:0;transform:translateY(24px);animation:fadeUp .8s .1s cubic-bezier(.16,1,.3,1) forwards;min-width:0}
.badge{width:clamp(26px,4vw,42px);height:clamp(26px,4vw,42px);margin-top:.35rem;flex-shrink:0;animation:badgePulse 3s ease-in-out infinite,fadeUp .8s .3s cubic-bezier(.16,1,.3,1) forwards;opacity:0}
@keyframes badgePulse{0%,100%{transform:scale(1)}50%{transform:scale(1.12)}}
@keyframes fadeUp{to{opacity:1;transform:translateY(0)}}

.services-list{font-family:'Playfair Display',Georgia,'Times New Roman',serif;font-weight:600;font-size:clamp(1rem,3.6vw,1.7rem);letter-spacing:.01em;color:var(--off);display:flex;flex-direction:column;gap:.3rem}
.services-list p{opacity:0;transform:translateX(-16px);animation:slideIn .7s cubic-bezier(.16,1,.3,1) forwards;max-width:100%}
.services-list p:nth-child(1){animation-delay:.45s}
.services-list p:nth-child(2){animation-delay:.6s}
.services-list p:nth-child(3){animation-delay:.75s}
@keyframes slideIn{to{opacity:1;transform:translateX(0)}}

.tagline{font-family:'DM Serif Display',serif;font-size:clamp(1.05rem,4vw,1.7rem);color:var(--off);max-width:34ch;opacity:0;animation:fadeUp .8s .95s cubic-bezier(.16,1,.3,1) forwards}

.hero-cta{display:flex;gap:1rem;flex-wrap:wrap;margin-top:.3rem;opacity:0;animation:fadeUp .8s 1.1s cubic-bezier(.16,1,.3,1) forwards}
.btn{padding:.85rem 1.9rem;border-radius:999px;font-weight:600;font-size:.9rem;transition:all .25s;border:2px solid transparent;display:inline-flex;align-items:center;gap:.4rem;cursor:pointer}
.btn-primary{background:var(--blue);color:#fff}
.btn-primary:hover{background:var(--blue-dark);transform:translateY(-3px)}
.btn-outline{border-color:rgba(255,255,255,.25);color:#fff}
.btn-outline:hover{border-color:var(--blue);color:var(--blue)}

/* LIZARD STAGE */
.lizard-stage{position:relative;display:flex;justify-content:center;align-items:center;z-index:2;perspective:1400px}
.lizard-stage::before{content:'';position:absolute;width:75%;height:75%;background:radial-gradient(circle,rgba(59,130,246,.30),transparent 70%);filter:blur(50px);z-index:-1}
.lizard-3d{width:100%;max-width:620px;transform-style:preserve-3d;animation:idleTilt 9s ease-in-out infinite;transition:transform .4s ease-out;will-change:transform}
@keyframes idleTilt{0%,100%{transform:rotateY(-8deg) rotateX(3deg)}50%{transform:rotateY(8deg) rotateX(-3deg)}}
.lizard{display:block;width:100%;height:auto;filter:drop-shadow(0 30px 35px rgba(0,0,0,.55))}

#lizard-group{transform-box:fill-box;animation:bob 3.4s ease-in-out infinite}
@keyframes bob{0%,100%{transform:translateY(0)}50%{transform:translateY(-10px)}}

#tail{transform-box:fill-box;transform-origin:0% 50%;animation:tailSway 2.8s ease-in-out infinite}
@keyframes tailSway{0%,100%{transform:rotate(-7deg)}50%{transform:rotate(7deg)}}

.leg{transform-box:fill-box;transform-origin:50% 0%}
.leg-a{animation:legA 1.3s ease-in-out infinite}
.leg-b{animation:legB 1.3s ease-in-out infinite}
@keyframes legA{0%,100%{transform:rotate(-9deg)}50%{transform:rotate(9deg)}}
@keyframes legB{0%,100%{transform:rotate(9deg)}50%{transform:rotate(-9deg)}}

#spikes{transform-box:fill-box;transform-origin:50% 100%;animation:spikeFlex 3.4s ease-in-out infinite;fill:#E8F5D8}
@keyframes spikeFlex{0%,100%{transform:scaleY(1)}50%{transform:scaleY(1.08)}}

#pupil{transform-box:fill-box;transform-origin:50% 50%;animation:blink 4.5s ease-in-out infinite}
@keyframes blink{0%,90%,100%{transform:scaleY(1)}94%{transform:scaleY(.1)}}

#tongue{transform-box:fill-box;transform-origin:100% 50%;opacity:0;animation:tongue 5s ease-in-out infinite}
@keyframes tongue{0%,85%,100%{opacity:0;transform:scaleX(0)}88%,93%{opacity:1;transform:scaleX(1)}}

.scroll-cue{position:absolute;bottom:1.6rem;left:50%;transform:translateX(-50%);z-index:3;display:flex;flex-direction:column;align-items:center;gap:.4rem;color:var(--gray-light);font-size:.7rem;letter-spacing:.2em;text-transform:uppercase;animation:cueBounce 2.4s ease-in-out infinite}
@keyframes cueBounce{0%,100%{transform:translate(-50%,0)}50%{transform:translate(-50%,8px)}}

/* ══════════════ SHARED SECTION STYLES ══════════════ */
.section-tag{font-size:.78rem;letter-spacing:.22em;text-transform:uppercase;color:var(--blue);font-weight:600;margin-bottom:.7rem}
.section-title{font-weight:800;font-size:clamp(2rem,5vw,3.1rem);margin-bottom:1.2rem}
.section-lead{color:var(--gray-light);max-width:60ch;margin-bottom:3rem;font-size:1.02rem}

.reveal{opacity:0;transform:translateY(34px);transition:opacity .8s ease,transform .8s ease}
.reveal.in{opacity:1;transform:none}

/* ══════════════ SERVICES ══════════════ */
.services{padding:6.5rem 0;background:#070707;border-top:1px solid rgba(255,255,255,.05);border-bottom:1px solid rgba(255,255,255,.05)}
.cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:1.6rem}
.card{background:linear-gradient(160deg,rgba(255,255,255,.05),rgba(255,255,255,.012));border:1px solid rgba(255,255,255,.08);border-radius:var(--radius);padding:2.3rem;transition:transform .35s,border-color .35s}
.card:hover{transform:translateY(-8px);border-color:var(--blue)}
.card-icon{width:54px;height:54px;border-radius:14px;background:var(--blue);display:flex;align-items:center;justify-content:center;font-size:1.6rem;margin-bottom:1.5rem}
.card h3{font-size:1.25rem;margin-bottom:.8rem;font-weight:700}
.card p{color:var(--gray-light);font-size:.95rem}

/* ══════════════ ABOUT ══════════════ */
.about{padding:6.5rem 0}
.about-grid{display:grid;grid-template-columns:1.1fr 1fr;gap:3.5rem;align-items:center}
.about p{color:var(--gray-light);margin-bottom:1.1rem;max-width:54ch}
.stats{display:grid;grid-template-columns:repeat(2,1fr);gap:1.8rem 1.4rem}
.stat{border-left:2px solid var(--blue);padding-left:1rem}
.stat-num{font-weight:800;font-size:clamp(1.8rem,4vw,2.6rem);color:#fff;display:block}
.stat-label{font-size:.85rem;color:var(--gray-light)}

/* ══════════════ PROCESS ══════════════ */
.process{padding:6.5rem 0;background:#070707;border-top:1px solid rgba(255,255,255,.05);border-bottom:1px solid rgba(255,255,255,.05)}
.steps{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:1.6rem}
.step{position:relative;padding:2.2rem 1.7rem;border:1px solid rgba(255,255,255,.08);border-radius:var(--radius);overflow:hidden;transition:border-color .3s,transform .3s}
.step:hover{border-color:var(--blue);transform:translateY(-6px)}
.step-num{font-weight:800;font-size:2.8rem;color:rgba(255,255,255,.08);position:absolute;top:.6rem;right:1.2rem;line-height:1}
.step h3{font-size:1.1rem;font-weight:700;margin-bottom:.6rem;position:relative;z-index:1}
.step p{color:var(--gray-light);font-size:.92rem;position:relative;z-index:1}

/* ══════════════ CONTACT ══════════════ */
.contact{padding:6.5rem 0}
.contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:3.5rem}
.form input,.form textarea{width:100%;background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.12);border-radius:12px;padding:.9rem 1.1rem;color:#fff;font-family:inherit;font-size:.92rem;margin-bottom:1rem;transition:border-color .25s}
.form input:focus,.form textarea:focus{outline:none;border-color:var(--blue)}
.form textarea{resize:vertical;min-height:120px}
.contact-info{display:flex;flex-direction:column;justify-content:center}
.contact-info p{color:var(--gray-light);margin-bottom:1.6rem;max-width:46ch}
.contact-info a{display:flex;align-items:center;gap:.7rem;margin-bottom:1rem;color:var(--off);font-weight:500;transition:color .2s}
.contact-info a:hover{color:var(--blue)}
.contact-info .ic{width:38px;height:38px;border-radius:10px;background:rgba(255,255,255,.06);display:flex;align-items:center;justify-content:center;font-size:1.05rem;flex-shrink:0}

/* ══════════════ FOOTER ══════════════ */
footer{padding:3rem 0;border-top:1px solid rgba(255,255,255,.06)}
.footer-grid{display:flex;flex-wrap:wrap;justify-content:space-between;align-items:center;gap:1.4rem}
.footer-logo{display:flex;align-items:center;gap:.45rem;font-weight:800;font-size:1.1rem;letter-spacing:.08em}
.footer-badge{width:15px;height:15px}
footer .nav-links a{color:var(--gray)}
.footer-copy{color:var(--gray);font-size:.8rem}

/* ══════════════ RESPONSIVE ══════════════ */
@media (max-width:980px){
  .hero-grid{grid-template-columns:1fr;text-align:center}
  .hero{padding-top:7rem;min-height:auto}
  .logo-row,.services-list,.hero-cta{align-items:center;justify-content:center}
  .logo-row{justify-content:center}
  .tagline{margin:0 auto}
  .lizard-3d{max-width:440px;margin-top:2.5rem}
  .about-grid,.contact-grid{grid-template-columns:1fr;gap:2.5rem}
}
@media (max-width:860px){
  .nav{padding:1rem 1.4rem}
  .nav-toggle{display:flex}
  .nav-links{position:fixed;top:64px;left:0;right:0;flex-direction:column;align-items:flex-start;background:#000;padding:1.6rem 2rem;gap:1.2rem;border-bottom:1px solid rgba(255,255,255,.08);transform:translateY(-110%);opacity:0;transition:all .3s;pointer-events:none}
  .nav-links.open{transform:translateY(0);opacity:1;pointer-events:auto}
  .nav-cta{display:inline-block;text-align:center;width:100%}
  .footer-grid{flex-direction:column;text-align:center}
}
@media (max-width:560px){
  .container{padding:0 1.1rem}
  .hero{padding-top:6rem;padding-bottom:2rem}
  .hero-grid{padding:0 1.1rem;gap:1.4rem}
  .hero-text{gap:1.5rem}
  .logo-row{gap:.55rem}
  .badge{margin-top:.2rem}
  .blob-tl{width:220px;top:-70px;left:-90px;opacity:.7}
  .blob-br{width:260px}
  .services-list{font-size:clamp(.9rem,4.2vw,1.15rem);gap:.25rem}
  .tagline{font-size:clamp(.95rem,4.2vw,1.15rem);max-width:30ch}
  .hero-cta{gap:.7rem;margin-top:.1rem}
  .btn{padding:.75rem 1.5rem;font-size:.85rem}
  .section-title{font-size:clamp(1.6rem,7vw,2.2rem)}
  .section-lead{margin-bottom:2.2rem;font-size:.95rem}
  .services,.about,.process,.contact{padding:4.2rem 0}
  .card{padding:1.7rem}
  .stats{grid-template-columns:1fr 1fr;gap:1.4rem 1rem}
  .stat-num{font-size:clamp(1.5rem,6vw,2rem)}
}
@media (max-width:400px){
  .container{padding:0 .9rem}
  .hero-grid{padding:0 .9rem}
  .logo{font-size:clamp(1.9rem,11vw,2.6rem)}
  .services-list{font-size:clamp(.82rem,4.5vw,1rem)}
  .tagline{font-size:.92rem}
  .hero-cta{flex-direction:column;width:100%}
  .hero-cta .btn{width:100%;justify-content:center}
  .stats{grid-template-columns:1fr}
}

/* ══════════════ ROCKET STAGE (replaces lizard) ══════════════ */
.rocket-stage{width:100%;height:clamp(440px,56vh,600px);position:relative}
.rocket-stage canvas{width:100%!important;height:100%!important;display:block}
@media (max-width:980px){.rocket-stage{height:clamp(340px,46vh,460px);margin-top:.6rem}}
@media (max-width:560px){.rocket-stage{height:clamp(260px,38vh,340px)}}
@media (max-width:400px){.rocket-stage{height:clamp(230px,34vh,300px)}}
</style>
</head>
<body>
<div class="noise"></div>

<header class="nav" id="siteNav">
  <a href="#top" class="nav-logo">SUHEJBX
    <svg class="nav-badge" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
      <polygon points="50,0 60.1,12.3 75,6.7 77.6,22.4 93.3,25 87.7,39.9 100,50 87.7,60.1 93.3,75 77.6,77.6 75,93.3 60.1,87.7 50,100 39.9,87.7 25,93.3 22.4,77.6 6.7,75 12.3,60.1 0,50 12.3,39.9 6.7,25 22.4,22.4 25,6.7 39.9,12.3" fill="#3B82F6"/>
      <path d="M28 52 L42 66 L74 32" stroke="#fff" stroke-width="9" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
  </a>
  <nav class="nav-links" id="navLinks">
    <a href="#sherbimet">Shërbimet</a>
    <a href="#procesi">Procesi</a>
    <a href="#rreth-nesh">Rreth Nesh</a>
    <a href="#kontakt">Kontakt</a>
    <a href="#kontakt" class="nav-cta">Fillo Projektin</a>
  </nav>
  <button class="nav-toggle" id="navToggle" aria-label="Menu"><span></span><span></span><span></span></button>
</header>

<!-- ══════════════ HERO ══════════════ -->
<section class="hero" id="top">
  <svg class="blob blob-tl" viewBox="0 0 400 300" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="none">
    <path d="M0,0 L400,0 L400,95 C 345,135 318,82 268,138 C 218,196 236,262 158,272 C 80,282 64,202 22,212 C -12,220 0,105 0,0 Z"/>
  </svg>
  <svg class="blob blob-br" viewBox="0 0 400 300" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="none">
    <path d="M0,0 L400,0 L400,95 C 345,135 318,82 268,138 C 218,196 236,262 158,272 C 80,282 64,202 22,212 C -12,220 0,105 0,0 Z"/>
  </svg>

  <div class="hero-grid">
    <div class="hero-text">
      <div class="logo-row">
        <h1 class="logo">SUHEJBX</h1>
        <svg class="badge" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
          <polygon points="50,0 60.1,12.3 75,6.7 77.6,22.4 93.3,25 87.7,39.9 100,50 87.7,60.1 93.3,75 77.6,77.6 75,93.3 60.1,87.7 50,100 39.9,87.7 25,93.3 22.4,77.6 6.7,75 12.3,60.1 0,50 12.3,39.9 6.7,25 22.4,22.4 25,6.7 39.9,12.3" fill="#3B82F6"/>
          <path d="M28 52 L42 66 L74 32" stroke="#fff" stroke-width="9" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </div>

      <div class="services-list">
        <p>Web developer</p>
        <p>Video Marketing</p>
        <p>Manage Social Media</p>
      </div>

      <p class="tagline">We work only for europe, balkan Businesses.</p>

      <div class="hero-cta">
        <a href="#kontakt" class="btn btn-primary">Kontaktona</a>
        <a href="#sherbimet" class="btn btn-outline">Shërbimet Tona</a>
      </div>
    </div>

    <div class="lizard-stage rocket-stage">
      <canvas id="rocketCanvas"></canvas>
    </div>
  </div>

  <div class="scroll-cue">Zbrit ↓</div>
</section>

<!-- ══════════════ SERVICES ══════════════ -->
<section class="services" id="sherbimet">
  <div class="container reveal">
    <p class="section-tag">Çka Ofrojmë</p>
    <h2 class="section-title">Shërbimet Tona</h2>
    <p class="section-lead">Ndihmojmë bizneset evropiane dhe ballkanike të rrisin praninë e tyre online me zgjidhje digjitale moderne, të shpejta dhe efektive.</p>
    <div class="cards">
      <div class="card">
        <div class="card-icon">🌐</div>
        <h3>Zhvillim Web</h3>
        <p>Krijojmë faqe interneti moderne, të shpejta dhe responsive — nga landing pages deri te platforma e-commerce, të optimizuara për konvertim dhe SEO.</p>
      </div>
      <div class="card">
        <div class="card-icon">🎬</div>
        <h3>Video Marketing</h3>
        <p>Prodhojmë dhe montojmë video profesionale për reklama, social media dhe storytelling që e bëjnë brendin tuaj të dallohet dhe rrit shitjet.</p>
      </div>
      <div class="card">
        <div class="card-icon">📱</div>
        <h3>Menaxhim i Rrjeteve Sociale</h3>
        <p>Strategji content-i, dizajn grafik, postime të rregullta dhe rritje organike për Instagram, Facebook, TikTok dhe LinkedIn.</p>
      </div>
    </div>
  </div>
</section>

<!-- ══════════════ ABOUT ══════════════ -->
<section class="about" id="rreth-nesh">
  <div class="container about-grid reveal">
    <div>
      <p class="section-tag">Rreth Nesh</p>
      <h2 class="section-title">Pse SUHEJBX?</h2>
      <p>Jemi një ekip i vogël, por i fokusuar, që punon ekskluzivisht me biznese nga Evropa dhe Ballkani.</p>
      <p>Kombinojmë dizajn modern, teknologji të fundit dhe strategji marketingu për të sjellë rezultate reale — më shumë klientë, më shumë shitje, brand më i fortë.</p>
    </div>
    <div class="stats">
      <div class="stat"><span class="stat-num">30+</span><span class="stat-label">Projekte të Realizuara</span></div>
      <div class="stat"><span class="stat-num">15+</span><span class="stat-label">Klientë të Kënaqur</span></div>
      <div class="stat"><span class="stat-num">6</span><span class="stat-label">Vende të Mbuluara</span></div>
      <div class="stat"><span class="stat-num">100%</span><span class="stat-label">Përkushtim &amp; Cilësi</span></div>
    </div>
  </div>
</section>

<!-- ══════════════ PROCESS ══════════════ -->
<section class="process" id="procesi">
  <div class="container reveal">
    <p class="section-tag">Si Punojmë</p>
    <h2 class="section-title">Procesi Ynë</h2>
    <p class="section-lead">Një proces i thjeshtë, transparent dhe i fokusuar te rezultatet — nga ideja e parë deri te lançimi dhe rritja vazhduese.</p>
    <div class="steps">
      <div class="step">
        <span class="step-num">01</span>
        <h3>Konsultim &amp; Analizë</h3>
        <p>Mësojmë biznesin tuaj, qëllimet dhe audiencën para se të nisim çdo projekt.</p>
      </div>
      <div class="step">
        <span class="step-num">02</span>
        <h3>Strategji &amp; Dizajn</h3>
        <p>Krijojmë konceptin vizual dhe planin e përmbajtjes së përshtatur për brendin tuaj.</p>
      </div>
      <div class="step">
        <span class="step-num">03</span>
        <h3>Zhvillim &amp; Prodhim</h3>
        <p>Ndërtojmë faqen, prodhojmë videot dhe përgatisim përmbajtjen për rrjetet sociale.</p>
      </div>
      <div class="step">
        <span class="step-num">04</span>
        <h3>Lançim &amp; Rritje</h3>
        <p>Publikojmë, monitorojmë performancën dhe optimizojmë vazhdimisht për rezultate më të mira.</p>
      </div>
    </div>
  </div>
</section>

<!-- ══════════════ CONTACT ══════════════ -->
<section class="contact" id="kontakt">
  <div class="container contact-grid reveal">
    <div>
      <p class="section-tag">Kontakt</p>
      <h2 class="section-title">Le të Fillojmë Projektin</h2>
      <form class="form" id="contactForm">
        <input type="text" name="name" placeholder="Emri" required/>
        <input type="email" name="email" placeholder="Email" required/>
        <textarea name="message" placeholder="Më trego pak për biznesin tuaj..." required></textarea>
        <button type="submit" class="btn btn-primary">Dërgo Mesazhin</button>
      </form>
    </div>
    <div class="contact-info">
      <p>Na shkruani disa fjalë për biznesin tuaj — kthehemi shpejt me një plan të përshtatur për ju.</p>
      <a href="mailto:hello@suhejbx.com"><span class="ic">✉️</span> hello@suhejbx.com</a>
      <a href="#"><span class="ic">📷</span> @suhejbx</a>
      <a href="#"><span class="ic">💼</span> SUHEJBX on LinkedIn</a>
    </div>
  </div>
</section>

<!-- ══════════════ FOOTER ══════════════ -->
<footer>
  <div class="container footer-grid">
    <a href="#top" class="footer-logo">SUHEJBX
      <svg class="footer-badge" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
        <polygon points="50,0 60.1,12.3 75,6.7 77.6,22.4 93.3,25 87.7,39.9 100,50 87.7,60.1 93.3,75 77.6,77.6 75,93.3 60.1,87.7 50,100 39.9,87.7 25,93.3 22.4,77.6 6.7,75 12.3,60.1 0,50 12.3,39.9 6.7,25 22.4,22.4 25,6.7 39.9,12.3" fill="#3B82F6"/>
        <path d="M28 52 L42 66 L74 32" stroke="#fff" stroke-width="9" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </a>
    <nav class="nav-links">
      <a href="#sherbimet">Shërbimet</a>
      <a href="#procesi">Procesi</a>
      <a href="#rreth-nesh">Rreth Nesh</a>
      <a href="#kontakt">Kontakt</a>
    </nav>
    <p class="footer-copy">© 2026 SUHEJBX. Të gjitha të drejtat e rezervuara.</p>
  </div>
</footer>

<script>
// nav background on scroll
const siteNav = document.getElementById('siteNav');
window.addEventListener('scroll', () => {
  siteNav.classList.toggle('scrolled', window.scrollY > 40);
});

// mobile menu toggle
const navToggle = document.getElementById('navToggle');
const navLinks = document.getElementById('navLinks');
navToggle.addEventListener('click', () => {
  navToggle.classList.toggle('open');
  navLinks.classList.toggle('open');
});
navLinks.querySelectorAll('a').forEach(a => a.addEventListener('click', () => {
  navToggle.classList.remove('open');
  navLinks.classList.remove('open');
}));

// scroll reveal
const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => { if (entry.isIntersecting) entry.target.classList.add('in'); });
}, { threshold: .15 });
document.querySelectorAll('.reveal').forEach(el => observer.observe(el));


// contact form -> mailto
document.getElementById('contactForm').addEventListener('submit', e => {
  e.preventDefault();
  const data = new FormData(e.target);
  const subject = encodeURIComponent('Projekt i ri nga ' + data.get('name'));
  const body = encodeURIComponent(data.get('message') + '\n\nEmail: ' + data.get('email'));
  window.location.href = `mailto:hello@suhejbx.com?subject=${subject}&body=${body}`;
});
</script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
(function(){
  if(!window.THREE){ return; }
  var canvas = document.getElementById('rocketCanvas');
  if(!canvas) return;
  var stage = canvas.parentElement;
  var mobile = Math.min(window.innerWidth, window.innerHeight) < 760;

  var renderer = new THREE.WebGLRenderer({ canvas: canvas, antialias: true, alpha: true });
  renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
  renderer.setClearColor(0x000000, 0);

  var scene = new THREE.Scene();
  scene.fog = new THREE.FogExp2(0x000000, 0.02);
  var camera = new THREE.PerspectiveCamera(50, 1, 0.1, 120);
  camera.position.set(0, 0, 6);
  var camBaseY = 0;

  // soft round dot
  function discTexture(){
    var c = document.createElement('canvas'); c.width = c.height = 64;
    var x = c.getContext('2d');
    var g = x.createRadialGradient(32,32,0,32,32,32);
    g.addColorStop(0,'rgba(255,255,255,1)');
    g.addColorStop(0.22,'rgba(255,255,255,0.92)');
    g.addColorStop(0.55,'rgba(255,255,255,0.28)');
    g.addColorStop(1,'rgba(255,255,255,0)');
    x.fillStyle = g; x.fillRect(0,0,64,64);
    return new THREE.CanvasTexture(c);
  }
  var sprite = discTexture();

  function glowSprite(hex, opacity){
    var m = new THREE.SpriteMaterial({ map:sprite, color:new THREE.Color(hex), transparent:true,
            depthWrite:false, blending:THREE.AdditiveBlending, opacity:opacity });
    return new THREE.Sprite(m);
  }

  // ---------- build the rocket from points ----------
  var P = [], C = [];
  var white     = new THREE.Color('#eef4ff');
  var lightBlue = new THREE.Color('#a9caff');
  var blue      = new THREE.Color('#3B82F6');
  var deepBlue  = new THREE.Color('#1f5fd6');
  var win       = new THREE.Color('#9af2ff');
  var nozzleCol = new THREE.Color('#7e8ba2');
  function push(x,y,z,col){ P.push(x,y,z); C.push(col.r,col.g,col.b); }
  function mix(a,b,t){ return a.clone().lerp(b,t); }

  var R = 0.46, H = 2.0;
  var i, a, y, t, r, col;

  // body shell
  var bodyN = mobile ? 2600 : 4200;
  for(i=0;i<bodyN;i++){
    a = Math.random()*Math.PI*2; y = Math.random()*H;
    col = mix(white, lightBlue, Math.random()*0.55);
    push(Math.cos(a)*R, y, Math.sin(a)*R, col);
  }
  // panel seam rings (crisper, brighter)
  var seams = [0.30,0.66,1.02,1.40,1.76];
  for(var s=0;s<seams.length;s++){
    var ringN = mobile ? 120 : 200;
    for(i=0;i<ringN;i++){
      a = Math.random()*Math.PI*2;
      push(Math.cos(a)*R*1.004, seams[s] + (Math.random()-0.5)*0.012, Math.sin(a)*R*1.004, white);
    }
  }
  // blue accent band
  var bandN = mobile ? 320 : 520;
  for(i=0;i<bandN;i++){
    a = Math.random()*Math.PI*2; y = 1.04 + Math.random()*0.22;
    push(Math.cos(a)*R*1.006, y, Math.sin(a)*R*1.006, blue);
  }

  // smooth elliptical nose
  var noseN = mobile ? 1000 : 1500;
  for(i=0;i<noseN;i++){
    t = Math.pow(Math.random(),0.6); a = Math.random()*Math.PI*2;
    y = H + 0.95*t; r = R*Math.sqrt(Math.max(0,1 - t*t));
    push(Math.cos(a)*r, y, Math.sin(a)*r, mix(blue, deepBlue, t*0.6));
  }
  // nose tip accent
  for(i=0;i<70;i++){
    a = Math.random()*Math.PI*2; r = Math.random()*0.05;
    push(Math.cos(a)*r, H+0.92+Math.random()*0.05, Math.sin(a)*r, white);
  }

  // four swept fins
  function fin(rot){
    var v0x=R, v0y=0.62, v1x=R, v1y=0.0, v2x=R+0.46, v2y=-0.10, k, u, w, px, py, X, Z;
    var fn = mobile ? 330 : 520;
    for(k=0;k<fn;k++){
      u=Math.random(); w=Math.random();
      if(u+w>1){ u=1-u; w=1-w; }
      px = v0x + (v1x-v0x)*u + (v2x-v0x)*w;
      py = v0y + (v1y-v0y)*u + (v2y-v0y)*w;
      X = px*Math.cos(rot); Z = px*Math.sin(rot);
      push(X, py, Z, mix(blue, deepBlue, 0.3));
    }
  }
  fin(0); fin(Math.PI/2); fin(Math.PI); fin(Math.PI*1.5);

  // porthole window (bright core + ring)
  for(i=0;i<90;i++){
    var ang = Math.random()*Math.PI*2, rad = Math.sqrt(Math.random())*0.12;
    push(Math.cos(ang)*rad, 1.30 + Math.sin(ang)*rad, R + 0.03, win);
  }
  for(i=0;i<170;i++){
    var ang2 = Math.random()*Math.PI*2;
    push(Math.cos(ang2)*0.16, 1.30 + Math.sin(ang2)*0.16, R + 0.025, mix(win, white, 0.4));
  }

  // flared nozzle
  var nozN = mobile ? 300 : 440;
  for(i=0;i<nozN;i++){
    t = Math.random(); a = Math.random()*Math.PI*2;
    r = R*0.66*(1 + t*0.6); y = -0.02 - 0.18*t;
    push(Math.cos(a)*r, y, Math.sin(a)*r, nozzleCol);
  }

  var rgeo = new THREE.BufferGeometry();
  rgeo.setAttribute('position', new THREE.Float32BufferAttribute(P, 3));
  rgeo.setAttribute('color', new THREE.Float32BufferAttribute(C, 3));
  var rmat = new THREE.PointsMaterial({
    size: mobile ? 0.055 : 0.05, map: sprite, vertexColors: true, transparent: true,
    depthWrite: false, blending: THREE.AdditiveBlending, sizeAttenuation: true, opacity: 0
  });
  var rocketPoints = new THREE.Points(rgeo, rmat);

  var rocket = new THREE.Group();
  rocket.add(rocketPoints);

  // engine flare + ignition flash + soft body bloom (move with the rocket)
  var engineFlare = glowSprite('#ffb866', 0.0); engineFlare.position.set(0,-0.16,0); rocket.add(engineFlare);
  var flash = glowSprite('#ffffff', 0.0); flash.position.set(0,-0.16,0); rocket.add(flash);
  var bodyBloom = glowSprite('#5aa0ff', 0.0); bodyBloom.position.set(0,0.95,0); bodyBloom.scale.set(2.4,3.4,1); rocket.add(bodyBloom);
  var winGlow = glowSprite('#9af2ff', 0.0); winGlow.position.set(0,1.30,R+0.05); winGlow.scale.set(0.7,0.7,1); rocketPoints.add(winGlow);

  scene.add(rocket);
  var baseY = -2.1;
  rocket.position.set(0, baseY, 0);

  // ---------- particle pools (world space => leave a trail) ----------
  function Pool(count, size, opacity){
    this.count=count; this.cursor=0;
    this.pos=new Float32Array(count*3); this.col=new Float32Array(count*3);
    this.life=new Float32Array(count); this.max=new Float32Array(count);
    this.vel=new Float32Array(count*3); this.grow=new Float32Array(count);
    for(var i=0;i<count;i++) this.pos[i*3+1]=9999;
    this.geo=new THREE.BufferGeometry();
    this.geo.setAttribute('position', new THREE.BufferAttribute(this.pos,3));
    this.geo.setAttribute('color', new THREE.BufferAttribute(this.col,3));
    this.mat=new THREE.PointsMaterial({ size:size, map:sprite, vertexColors:true, transparent:true,
              depthWrite:false, blending:THREE.AdditiveBlending, sizeAttenuation:true, opacity:opacity });
    this.pts=new THREE.Points(this.geo, this.mat); scene.add(this.pts);
  }
  Pool.prototype.emit=function(n,wx,wy,wz,vmin,vmax,spread,lmin,lmax,grow){
    for(var k=0;k<n;k++){
      var i=this.cursor; this.cursor=(this.cursor+1)%this.count;
      this.max[i]=lmin+Math.random()*(lmax-lmin); this.life[i]=this.max[i];
      this.vel[i*3]=(Math.random()-0.5)*spread;
      this.vel[i*3+1]=-(vmin+Math.random()*(vmax-vmin));
      this.vel[i*3+2]=(Math.random()-0.5)*spread;
      this.grow[i]=grow;
      this.pos[i*3]=wx+(Math.random()-0.5)*0.12;
      this.pos[i*3+1]=wy+(Math.random()-0.5)*0.05;
      this.pos[i*3+2]=wz+(Math.random()-0.5)*0.12;
    }
  };
  Pool.prototype.burst=function(n,wx,wy,wz,speed,lmin,lmax){
    for(var k=0;k<n;k++){
      var i=this.cursor; this.cursor=(this.cursor+1)%this.count;
      this.max[i]=lmin+Math.random()*(lmax-lmin); this.life[i]=this.max[i];
      var th=Math.random()*Math.PI*2, ph=Math.acos(2*Math.random()-1), sp=speed*(0.5+Math.random()*0.7);
      this.vel[i*3]=Math.sin(ph)*Math.cos(th)*sp;
      this.vel[i*3+1]=Math.abs(Math.cos(ph))*-0.3*sp;
      this.vel[i*3+2]=Math.sin(ph)*Math.sin(th)*sp;
      this.grow[i]=0;
      this.pos[i*3]=wx; this.pos[i*3+1]=wy; this.pos[i*3+2]=wz;
    }
  };
  Pool.prototype.update=function(dt, lo, mid, hi){
    for(var i=0;i<this.count;i++){
      if(this.life[i]>0){
        this.life[i]-=dt;
        if(this.grow[i]>0){
          this.vel[i*3]   += (this.vel[i*3]>=0?1:-1)*this.grow[i]*dt;
          this.vel[i*3+2] += (this.vel[i*3+2]>=0?1:-1)*this.grow[i]*dt;
        }
        this.pos[i*3]   += this.vel[i*3]*dt;
        this.pos[i*3+1] += this.vel[i*3+1]*dt;
        this.pos[i*3+2] += this.vel[i*3+2]*dt;
        var f=this.life[i]/this.max[i]; if(f<0)f=0;
        var rr,gg,bb,tt;
        if(f>0.5){ tt=(f-0.5)*2; rr=mid[0]+(hi[0]-mid[0])*tt; gg=mid[1]+(hi[1]-mid[1])*tt; bb=mid[2]+(hi[2]-mid[2])*tt; }
        else { tt=f*2; rr=lo[0]+(mid[0]-lo[0])*tt; gg=lo[1]+(mid[1]-lo[1])*tt; bb=lo[2]+(mid[2]-lo[2])*tt; }
        this.col[i*3]=rr; this.col[i*3+1]=gg; this.col[i*3+2]=bb;
      } else {
        this.col[i*3]=this.col[i*3+1]=this.col[i*3+2]=0;
        this.pos[i*3+1]=9999;
      }
    }
    this.geo.attributes.position.needsUpdate=true;
    this.geo.attributes.color.needsUpdate=true;
  };

  var flame = new Pool(mobile?700:1000, 0.13, 1.0);
  var plume = new Pool(mobile?800:1300, 0.26, 0.85);
  var FLAME_LO=[0.35,0.06,0.0], FLAME_MID=[1.0,0.55,0.16], FLAME_HI=[1.0,0.97,0.80];
  var PLUME_LO=[0.02,0.03,0.05], PLUME_MID=[0.34,0.42,0.56], PLUME_HI=[0.86,0.92,1.0];

  // ---------- sky: two star layers + soft nebula ----------
  function starLayer(count, size, opacity, zmin, zmax, hex){
    var pos=new Float32Array(count*3);
    for(var i=0;i<count;i++){
      pos[i*3]=(Math.random()-0.5)*26;
      pos[i*3+1]=(Math.random()-0.5)*26;
      pos[i*3+2]=zmin-Math.random()*(zmax-zmin);
    }
    var geo=new THREE.BufferGeometry();
    geo.setAttribute('position', new THREE.BufferAttribute(pos,3));
    var mat=new THREE.PointsMaterial({ size:size, map:sprite, color:new THREE.Color(hex), transparent:true,
            opacity:opacity, depthWrite:false, blending:THREE.AdditiveBlending, sizeAttenuation:true });
    var pts=new THREE.Points(geo,mat); scene.add(pts);
    return { pos:pos, geo:geo };
  }
  var starsFar  = starLayer(mobile?350:500, 0.05, 0.55, 9, 22, '#8fb0ff');
  var starsNear = starLayer(mobile?160:260, 0.085, 0.95, 3, 11, '#cfe0ff');

  var nebA = glowSprite('#16336e', 0.13); nebA.position.set(-3,2,-15); nebA.scale.set(20,20,1); scene.add(nebA);
  var nebB = glowSprite('#3a1f5e', 0.10); nebB.position.set(4,-3,-17); nebB.scale.set(22,18,1); scene.add(nebB);

  // ---------- responsive framing ----------
  function resize(){
    var w = stage.clientWidth || canvas.clientWidth || 400;
    var h = stage.clientHeight || canvas.clientHeight || 400;
    renderer.setSize(w, h, false);
    camera.aspect = w / h;
    var fr = camera.fov*Math.PI/180;
    var dH = 1.95/Math.tan(fr/2);
    var dW = 1.30/(camera.aspect*Math.tan(fr/2));
    camera.position.z = Math.max(dH, dW) * 1.45;
    camera.updateProjectionMatrix();
  }
  resize();
  window.addEventListener('resize', resize);
  if(window.ResizeObserver){ new ResizeObserver(resize).observe(stage); }

  // ---------- launch sequence ----------
  var reduce = window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  var state='idle', stateT=0, vy=0, first=true;
  var rocketAlpha=0, starSpeed=0.06, shakeT=0, flashT=0;
  var thrustVis=0.15;
  var clock = new THREE.Clock();

  function update(dt, t){
    stateT += dt;
    var wx = rocket.position.x, wy = rocket.position.y - 0.12, wz = rocket.position.z;
    var thrustTarget = 0.15;

    if(state==='idle'){
      var dur = first ? 2.0 : 1.7;
      rocket.position.x = 0; rocket.position.z = 0;
      var yy = baseY + 0.07*Math.sin(t*2.0);
      var rem = dur - stateT;
      if(rem < 0.28){ var cc = 1 - Math.max(0,rem)/0.28; yy -= 0.16*cc*cc; }   // crouch
      rocket.position.y = yy;
      rocketAlpha += (1 - rocketAlpha) * Math.min(1, dt*5);
      rocketPoints.rotation.y += 0.35*dt;
      starSpeed += (0.06 - starSpeed)*Math.min(1, dt*2);

      if(rem < 0.6){
        var ch = 1 - Math.max(0,rem)/0.6;
        thrustTarget = 0.2 + 0.6*ch;
        flame.emit(Math.floor(3 + ch*16), wx, wy, wz, 1.2+ch*3.2, 2.0+ch*4.0, 0.10+ch*0.08, 0.30, 0.55, 0);
      } else {
        thrustTarget = 0.15;
        flame.emit(3, wx, wy, wz, 1.0, 1.8, 0.08, 0.28, 0.48, 0);
      }
      if(stateT >= dur){ state='launch'; stateT=0; vy=2.0; shakeT=reduce?0:0.34; flashT=0.34;
        flame.burst(reduce?0:60, wx, wy, wz, 5.0, 0.25, 0.5); }

    } else if(state==='launch'){
      thrustTarget = 1.0;
      var accel = reduce ? 3.2 : 6.6;
      vy += accel * dt;
      rocket.position.y += vy * dt;
      rocketPoints.rotation.y += 0.7*dt;
      rocket.position.x = 0.045*Math.sin(t*26) * Math.max(0, 1 - rocket.position.y*0.2);

      if(rocket.position.y > -0.2){
        var over = rocket.position.y + 0.2;
        rocket.position.z -= Math.min(7, over*0.95) * dt * 2.2;
        rocketAlpha += (0 - rocketAlpha) * Math.min(1, dt*1.7);
      }
      flame.emit(reduce?10:24, wx, wy, wz, reduce?3.5:6.0, reduce?5:9, 0.14, 0.30, 0.55, 0);
      plume.emit(reduce?8:18, wx, wy-0.05, wz, 1.6, 3.2, 0.22, 0.7, 1.25, 1.6);
      starSpeed += ((reduce?2.0:6.5) - starSpeed) * Math.min(1, dt*2.5);

      if(rocket.position.y > 7 || rocketAlpha < 0.02){ state='reset'; stateT=0; }

    } else if(state==='reset'){
      thrustTarget = 0.0;
      rocket.position.set(0, baseY, 0); vy=0; rocketAlpha=0;
      starSpeed += (0.06 - starSpeed)*Math.min(1, dt*3);
      if(stateT > 0.35){ state='idle'; stateT=0; first=false; }
    }

    rmat.opacity = rocketAlpha;

    // engine flare + window glow + body bloom
    thrustVis += (thrustTarget - thrustVis) * Math.min(1, dt*8);
    var flick = 0.88 + Math.random()*0.24;
    var es = (0.45 + 1.7*thrustVis) * flick;
    engineFlare.scale.set(es, es*1.15, 1);
    engineFlare.material.opacity = (0.2 + 0.8*thrustVis) * rocketAlpha;
    winGlow.material.opacity = (0.5 + 0.4*Math.sin(t*3.0)) * rocketAlpha * 0.9;
    bodyBloom.material.opacity = 0.10 * rocketAlpha;

    // ignition flash
    if(flashT > 0){
      flashT -= dt;
      var p = Math.max(0, flashT/0.34);
      var fs = 0.5 + (1-p)*3.4;
      flash.scale.set(fs, fs, 1);
      flash.material.opacity = p * 1.0 * rocketAlpha;
    } else { flash.material.opacity = 0; }

    // camera kick
    if(shakeT > 0){
      shakeT -= dt;
      camera.position.x = (Math.random()-0.5)*0.055;
      camera.position.y = camBaseY + (Math.random()-0.5)*0.055;
    } else {
      camera.position.x *= 0.85;
      camera.position.y += (camBaseY - camera.position.y)*0.2;
    }
    camera.lookAt(0, -0.6, 0);

    // particles
    flame.update(dt, FLAME_LO, FLAME_MID, FLAME_HI);
    plume.update(dt, PLUME_LO, PLUME_MID, PLUME_HI);

    // stars (parallax: near layer faster)
    var sp1 = starSpeed, sp2 = starSpeed*1.7;
    for(var i=0;i<starsFar.pos.length;i+=3){
      starsFar.pos[i+1] -= sp1*dt;
      if(starsFar.pos[i+1] < -13){ starsFar.pos[i+1] += 26; starsFar.pos[i] = (Math.random()-0.5)*26; }
    }
    for(var j=0;j<starsNear.pos.length;j+=3){
      starsNear.pos[j+1] -= sp2*dt;
      if(starsNear.pos[j+1] < -13){ starsNear.pos[j+1] += 26; starsNear.pos[j] = (Math.random()-0.5)*26; }
    }
    starsFar.geo.attributes.position.needsUpdate = true;
    starsNear.geo.attributes.position.needsUpdate = true;
  }

  function loop(){
    requestAnimationFrame(loop);
    var dt = Math.min(clock.getDelta(), 0.05);
    update(dt, clock.elapsedTime);
    renderer.render(scene, camera);
  }
  loop();
})();
</script>
</body>
</html>
