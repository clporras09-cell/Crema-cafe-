<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Crema Cafe Dunedin — Crafting memories, one cup at a time</title>
<meta name="description" content="Single-origin, small-batch coffee in a cozy neighborhood cafe. Espresso, pour-over, cold brew & fresh food in Dunedin, FL." />
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,500;9..144,600;9..144,900&family=DM+Sans:wght@400;500;700&display=swap" rel="stylesheet">
<style>
  :root{
    --espresso:#1A110B;
    --bean:#241710;
    --roast:#33200F;
    --cream:#F4E9D7;
    --cream-2:#FBF4E8;
    --latte:#D8C5A8;
    --muted:#9A856C;
    --crema:#E5A95B;
    --crema-deep:#C9803A;
    --leaf:#8FA06A;
    --ease:cubic-bezier(.2,.7,.2,1);
    --maxw:1200px;
  }
  *{margin:0;padding:0;box-sizing:border-box}
  html{scroll-behavior:smooth}
  body{
    background:var(--espresso);color:var(--cream);
    font-family:"DM Sans",system-ui,sans-serif;font-size:16px;line-height:1.6;
    -webkit-font-smoothing:antialiased;overflow-x:hidden;
  }
  a{color:inherit;text-decoration:none}
  img{display:block;max-width:100%}
  ::selection{background:var(--crema);color:var(--espresso)}
  :focus-visible{outline:2px solid var(--crema);outline-offset:3px;border-radius:3px}

  .wrap{max-width:var(--maxw);margin:0 auto;padding:0 24px}
  .serif{font-family:"Fraunces",Georgia,serif}
  .eyebrow{
    font-size:12px;letter-spacing:.24em;text-transform:uppercase;
    color:var(--crema);font-weight:700;display:inline-flex;align-items:center;gap:10px;
  }
  .eyebrow::before{content:"";width:24px;height:1px;background:var(--crema);opacity:.7}

  /* ---------- NAV ---------- */
  header.nav{position:fixed;top:0;left:0;right:0;z-index:60;transition:background .4s var(--ease),border-color .4s}
  .nav-inner{display:flex;align-items:center;justify-content:space-between;height:70px}
  header.nav.scrolled{background:rgba(26,17,11,.86);backdrop-filter:blur(12px);border-bottom:1px solid rgba(229,169,91,.18)}
  .logo{font-family:"Fraunces",serif;font-weight:900;font-size:24px;letter-spacing:-.01em;display:flex;align-items:center;gap:9px}
  .logo .dot{width:11px;height:11px;border-radius:50%;background:radial-gradient(circle at 35% 30%,#F6CB86,var(--crema-deep));box-shadow:0 0 14px rgba(229,169,91,.55)}
  .logo small{font-family:"DM Sans",sans-serif;font-weight:500;font-size:10px;letter-spacing:.28em;color:var(--latte);text-transform:uppercase;margin-top:6px}
  .nav-links{display:flex;align-items:center;gap:32px}
  .nav-links a{font-size:14px;color:var(--cream);opacity:.85;transition:opacity .25s,color .25s;position:relative}
  .nav-links a:not(.btn)::after{content:"";position:absolute;left:0;bottom:-5px;height:1.5px;width:0;background:var(--crema);transition:width .3s var(--ease)}
  .nav-links a:not(.btn):hover{opacity:1}
  .nav-links a:not(.btn):hover::after{width:100%}
  .btn{
    font-weight:700;font-size:14px;padding:11px 20px;border-radius:999px;
    background:var(--crema);color:var(--espresso);border:1px solid var(--crema);
    transition:transform .25s var(--ease),background .25s,box-shadow .25s;display:inline-flex;align-items:center;gap:8px;cursor:pointer;
  }
  .btn:hover{transform:translateY(-2px);box-shadow:0 10px 26px rgba(229,169,91,.32)}
  .btn.ghost{background:transparent;color:var(--cream);border-color:rgba(244,233,215,.4)}
  .btn.ghost:hover{border-color:var(--crema);color:var(--crema);box-shadow:none}
  .menu-toggle{display:none;background:none;border:0;color:var(--cream);cursor:pointer;flex-direction:column;gap:5px;padding:8px}
  .menu-toggle span{width:24px;height:2px;background:var(--cream);transition:.3s}

  /* ---------- HERO ---------- */
  .hero{position:relative;min-height:100svh;display:flex;align-items:center;overflow:hidden;
    background:radial-gradient(120% 90% at 78% 18%,#3a2412 0%,#241710 45%,#160d08 100%)}
  #beanCanvas{position:absolute;inset:0;width:100%;height:100%;z-index:1}
  .hero::after{content:"";position:absolute;inset:0;z-index:2;pointer-events:none;
    background:linear-gradient(90deg,rgba(22,13,8,.78) 0%,rgba(22,13,8,.30) 55%,transparent 100%)}
  .hero-content{position:relative;z-index:3;width:100%;padding:120px 0 70px}
  .hero h1{font-family:"Fraunces",serif;font-weight:900;font-size:clamp(2.8rem,7vw,5.4rem);line-height:1.02;letter-spacing:-.02em;margin:22px 0 20px;max-width:14ch}
  .hero h1 em{font-style:italic;color:var(--crema)}
  .hero .sub{font-size:clamp(1.05rem,2vw,1.3rem);color:var(--latte);max-width:42ch;margin-bottom:34px}
  .hero-cta{display:flex;gap:14px;flex-wrap:wrap;align-items:center}

  .open-pill{
    display:inline-flex;align-items:center;gap:11px;padding:9px 18px 9px 14px;border-radius:999px;
    background:rgba(244,233,215,.07);border:1px solid rgba(244,233,215,.16);
    font-size:13.5px;color:var(--cream);backdrop-filter:blur(6px);
  }
  .open-pill .live{width:9px;height:9px;border-radius:50%;background:var(--muted);position:relative}
  .open-pill.is-open .live{background:var(--leaf);box-shadow:0 0 0 0 rgba(143,160,106,.6);animation:ping 2.2s infinite}
  .open-pill.is-closed .live{background:var(--crema-deep)}
  .open-pill b{font-weight:700}
  @keyframes ping{0%{box-shadow:0 0 0 0 rgba(143,160,106,.55)}70%{box-shadow:0 0 0 9px rgba(143,160,106,0)}100%{box-shadow:0 0 0 0 rgba(143,160,106,0)}}

  .hero-meta{position:absolute;left:0;right:0;bottom:26px;z-index:3}
  .hero-meta .wrap{display:flex;justify-content:space-between;align-items:center;gap:16px;color:var(--latte);font-size:13px}
  .scroll-cue{display:inline-flex;align-items:center;gap:9px;letter-spacing:.16em;text-transform:uppercase;font-size:11px}
  .scroll-cue .line{width:1px;height:26px;background:linear-gradient(var(--crema),transparent);animation:drop 1.8s var(--ease) infinite}
  @keyframes drop{0%{transform:scaleY(0);transform-origin:top}50%{transform:scaleY(1);transform-origin:top}51%{transform-origin:bottom}100%{transform:scaleY(0);transform-origin:bottom}}

  /* ---------- SECTIONS ---------- */
  .section{padding:110px 0;position:relative;background:var(--espresso);color:var(--cream)}
  .section.light{background:var(--cream-2);color:var(--roast)}
  .section.light .eyebrow{color:var(--crema-deep)}
  .section.light .eyebrow::before{background:var(--crema-deep)}
  .section.light .muted-txt{color:#7a6048}
  .head-2{font-family:"Fraunces",serif;font-weight:900;font-size:clamp(2rem,4.4vw,3.2rem);line-height:1.05;letter-spacing:-.02em;margin:18px 0}

  /* story */
  .story-grid{display:grid;grid-template-columns:1.05fr .95fr;gap:64px;align-items:center}
  .story-copy p{color:#6f583f;font-size:1.06rem;margin-bottom:18px;max-width:48ch}
  .story-photo{position:relative}
  .story-photo .panel{position:relative;border-radius:22px;overflow:hidden;padding:40px 30px 32px;
    background:radial-gradient(120% 90% at 68% 4%,#3b2513,#241710 58%,#190f08);
    border:1px solid rgba(229,169,91,.22);display:flex;flex-direction:column;align-items:center;gap:20px;
    box-shadow:0 30px 60px rgba(0,0,0,.28)}
  .story-photo .panel .glow{position:absolute;top:-26%;left:50%;transform:translateX(-50%);width:72%;height:72%;
    background:radial-gradient(circle,rgba(229,169,91,.28),transparent 70%);filter:blur(8px);pointer-events:none}
  .cupart{position:relative;width:min(72%,250px);height:auto;filter:drop-shadow(0 16px 22px rgba(0,0,0,.32))}
  @keyframes rise{0%{opacity:0;transform:translateY(7px)}40%{opacity:.75}100%{opacity:0;transform:translateY(-11px)}}
  .cupart .st{transform-box:fill-box;transform-origin:center;animation:rise 3s ease-in-out infinite}
  .cupart .st2{animation-delay:.6s}
  .cupart .st3{animation-delay:1.2s}
  .story-stat{position:relative;display:flex;align-items:center;gap:16px;width:100%;justify-content:center;
    border-top:1px solid rgba(229,169,91,.2);padding-top:20px}
  .story-stat .n{font-family:"Fraunces",serif;font-weight:900;font-size:2.7rem;color:var(--crema);line-height:1}
  .story-stat .l{color:#E7D8BE;font-size:.93rem;max-width:18ch;text-align:left}

  /* craft row */
  .craft{display:grid;grid-template-columns:repeat(3,1fr);gap:22px;margin-top:64px}
  .craft-card{background:#fff;border:1px solid #ecdcc4;border-radius:16px;padding:30px 26px;transition:transform .4s var(--ease),box-shadow .4s}
  .craft-card:hover{transform:translateY(-6px);box-shadow:0 22px 50px rgba(122,77,36,.14)}
  .craft-card h3{font-family:"Fraunces",serif;font-weight:600;font-size:1.3rem;color:var(--roast);margin-bottom:9px}
  .craft-card p{color:#7a6048;font-size:.97rem}
  .craft-ic{width:52px;height:52px;border-radius:12px;background:linear-gradient(135deg,#f6e3c2,#e9b97a);display:flex;align-items:center;justify-content:center;margin-bottom:18px}
  /* css steam cup icon */
  .cup{position:relative;width:26px;height:20px}
  .cup .body{position:absolute;bottom:0;width:24px;height:15px;border-radius:0 0 9px 9px;background:var(--roast)}
  .cup .body::after{content:"";position:absolute;right:-7px;top:2px;width:9px;height:9px;border:2.5px solid var(--roast);border-radius:50%}
  .cup .steam{position:absolute;top:-9px;left:5px;width:3px;height:9px;border-radius:3px;background:rgba(51,32,15,.55);animation:steam 2.4s ease-in-out infinite}
  .cup .steam:nth-child(2){left:11px;animation-delay:.5s}
  .cup .steam:nth-child(3){left:17px;animation-delay:1s}
  @keyframes steam{0%{opacity:0;transform:translateY(3px) scaleY(.6)}40%{opacity:.8}100%{opacity:0;transform:translateY(-7px) scaleY(1.1)}}
  .leaf-ic,.bean-ic{font-family:"Fraunces",serif;font-weight:900;font-size:1.4rem;color:var(--roast)}

  /* ---------- MENU ---------- */
  .menu-head{display:flex;align-items:flex-end;justify-content:space-between;gap:24px;flex-wrap:wrap;margin-bottom:48px}
  .feature-grid{display:grid;grid-template-columns:1fr 1fr;gap:24px;margin-bottom:24px}
  .feat{position:relative;border-radius:18px;overflow:hidden;display:grid;grid-template-columns:130px 1fr;gap:18px;align-items:center;padding:26px 28px;
    background:linear-gradient(150deg,#2c1c0f,#191007);border:1px solid rgba(229,169,91,.18);transition:transform .4s var(--ease),border-color .4s}
  .feat:hover{transform:translateY(-5px);border-color:var(--crema)}
  .feat.matcha{background:linear-gradient(150deg,#242a12,#161205)}
  .feat-ill{position:relative;display:flex;justify-content:center;align-items:center}
  .feat-ill::before{content:"";position:absolute;width:130%;height:130%;border-radius:50%;background:radial-gradient(circle,rgba(229,169,91,.22),transparent 65%)}
  .feat.matcha .feat-ill::before{background:radial-gradient(circle,rgba(143,160,106,.26),transparent 65%)}
  .feat .drink{position:relative;width:108px;height:auto;filter:drop-shadow(0 12px 18px rgba(0,0,0,.45))}
  .feat .txt{position:relative;z-index:2}
  .feat .tag{display:inline-block;font-size:11px;letter-spacing:.16em;text-transform:uppercase;color:var(--espresso);background:var(--crema);padding:5px 12px;border-radius:999px;font-weight:700;margin-bottom:13px}
  .feat .tag.cold{background:#aac17a;color:#1c2a08}
  .feat h3{font-family:"Fraunces",serif;font-weight:700;font-size:1.45rem;line-height:1.1;margin-bottom:9px;color:var(--cream)}
  .feat p{color:#E0CFB2;font-size:.95rem}

  .cat-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:16px}
  .cat{background:var(--bean);border:1px solid rgba(229,169,91,.16);border-radius:14px;padding:24px 20px;transition:border-color .35s,transform .35s var(--ease)}
  .cat:hover{border-color:var(--crema);transform:translateY(-4px)}
  .cat .k{font-family:"Fraunces",serif;font-size:1.15rem;font-weight:600;margin-bottom:7px}
  .cat .d{font-size:.9rem;color:var(--latte)}
  .cat .arrow{color:var(--crema);margin-top:14px;font-size:.85rem;opacity:0;transform:translateX(-6px);transition:.35s var(--ease)}
  .cat:hover .arrow{opacity:1;transform:none}

  /* marquee */
  .marquee{margin:70px 0 0;overflow:hidden;border-top:1px solid rgba(229,169,91,.18);border-bottom:1px solid rgba(229,169,91,.18);padding:18px 0;-webkit-mask-image:linear-gradient(90deg,transparent,#000 12%,#000 88%,transparent);mask-image:linear-gradient(90deg,transparent,#000 12%,#000 88%,transparent)}
  .marquee-track{display:flex;gap:40px;white-space:nowrap;width:max-content;animation:scrollx 26s linear infinite}
  .marquee-track span{font-family:"Fraunces",serif;font-style:italic;font-size:1.5rem;color:var(--latte)}
  .marquee-track span .b{color:var(--crema);font-style:normal}
  @keyframes scrollx{to{transform:translateX(-50%)}}

  /* ---------- GALLERY ---------- */
  .gal-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:12px}
  .gal-grid a{position:relative;border-radius:14px;overflow:hidden;aspect-ratio:1;background:linear-gradient(135deg,#3a2412,#1c110a)}
  .gal-grid a:nth-child(2){background:linear-gradient(135deg,#46331b,#241710)}
  .gal-grid a:nth-child(3){background:linear-gradient(135deg,#2f3a1c,#161205)}
  .gal-grid a:nth-child(4){background:linear-gradient(135deg,#4a2f18,#1c110a)}
  .gal-grid .ph{position:absolute;inset:0;display:flex;align-items:center;justify-content:center}
  .gal-grid .ph::after{content:"";width:34px;height:34px;border-radius:50%;background:radial-gradient(circle at 35% 30%,#f6cb86,#c9803a);box-shadow:0 0 18px rgba(229,169,91,.45)}
  .gal-grid img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;transition:transform .8s var(--ease)}
  .gal-grid a::after{content:"";position:absolute;inset:0;background:rgba(26,17,11,0);transition:background .4s}
  .gal-grid a:hover img{transform:scale(1.1)}
  .gal-grid a:hover::after{background:rgba(26,17,11,.22)}

  /* ---------- VISIT ---------- */
  .visit-grid{display:grid;grid-template-columns:1fr 1fr;gap:54px;align-items:center}
  .hours-list{list-style:none;margin:24px 0 30px}
  .hours-list li{display:flex;justify-content:space-between;padding:13px 4px;border-bottom:1px solid rgba(244,233,215,.12);font-size:1rem}
  .hours-list li.today{color:var(--crema);font-weight:700}
  .hours-list li.today .day::before{content:"●  ";color:var(--leaf);font-size:.7em;vertical-align:middle}
  .visit-actions{display:flex;flex-wrap:wrap;gap:12px;margin-top:8px}
  .addr-card{background:var(--bean);border:1px solid rgba(229,169,91,.18);border-radius:18px;padding:34px;position:relative;overflow:hidden}
  .addr-card .mapdots{position:absolute;inset:0;opacity:.5;background-image:radial-gradient(rgba(229,169,91,.16) 1.3px,transparent 1.3px);background-size:22px 22px}
  .addr-card .pin{position:relative;z-index:2;width:54px;height:54px;border-radius:50% 50% 50% 0;background:var(--crema);transform:rotate(-45deg);display:flex;align-items:center;justify-content:center;margin-bottom:24px;box-shadow:0 12px 30px rgba(229,169,91,.4)}
  .addr-card .pin::after{content:"";width:18px;height:18px;border-radius:50%;background:var(--espresso)}
  .addr-card .a{position:relative;z-index:2}
  .addr-card .a .big{font-family:"Fraunces",serif;font-size:1.4rem;font-weight:600;margin-bottom:6px}
  .addr-card .a p{color:var(--latte);margin-bottom:4px}
  .addr-card .a .ph{color:var(--crema);font-weight:700;font-size:1.15rem;margin-top:14px;display:inline-block}

  /* ---------- CTA BAND ---------- */
  .band{background:linear-gradient(135deg,var(--crema-deep),var(--crema));color:var(--espresso);text-align:center;padding:96px 0}
  .band h2{font-family:"Fraunces",serif;font-weight:900;font-size:clamp(2rem,5vw,3.4rem);line-height:1.05;margin-bottom:16px}
  .band p{font-size:1.1rem;margin-bottom:30px;opacity:.85}
  .band .btn{background:var(--espresso);color:var(--cream);border-color:var(--espresso)}
  .band .btn:hover{box-shadow:0 12px 30px rgba(0,0,0,.3)}

  /* ---------- FOOTER ---------- */
  footer.site{padding:62px 0 34px;border-top:1px solid rgba(229,169,91,.14)}
  .foot-grid{display:grid;grid-template-columns:1.4fr 1fr 1fr;gap:40px;margin-bottom:42px}
  .foot-grid p{color:var(--latte);font-size:.95rem;max-width:34ch}
  .foot-col h4{font-size:12px;letter-spacing:.18em;text-transform:uppercase;color:var(--crema);margin-bottom:16px}
  .foot-col a{display:block;color:var(--cream);opacity:.82;padding:5px 0;font-size:.96rem;transition:opacity .25s,color .25s}
  .foot-col a:hover{opacity:1;color:var(--crema)}
  .foot-bottom{display:flex;justify-content:space-between;flex-wrap:wrap;gap:10px;padding-top:24px;border-top:1px solid rgba(244,233,215,.1);color:var(--muted);font-size:13px}

  /* reveal */
  .reveal{opacity:0;transform:translateY(26px);transition:opacity .9s var(--ease),transform .9s var(--ease)}
  .reveal.in{opacity:1;transform:none}

  /* ---------- RESPONSIVE ---------- */
  @media(max-width:900px){
    .nav-links{position:fixed;inset:70px 0 auto 0;flex-direction:column;background:rgba(22,13,8,.97);backdrop-filter:blur(14px);padding:24px;gap:18px;align-items:stretch;border-bottom:1px solid rgba(229,169,91,.2);transform:translateY(-130%);transition:transform .4s var(--ease)}
    .nav-links.open{transform:none}
    .nav-links a:not(.btn){padding:6px 0}
    .menu-toggle{display:flex}
    .story-grid,.visit-grid{grid-template-columns:1fr;gap:42px}
    .badge-card{left:auto;right:18px;bottom:-22px}
    .craft{grid-template-columns:1fr}
    .feature-grid{grid-template-columns:1fr}
    .cat-grid{grid-template-columns:1fr 1fr}
    .gal-grid{grid-template-columns:1fr 1fr}
    .foot-grid{grid-template-columns:1fr;gap:28px}
  }
  @media(max-width:520px){
    .wrap{padding:0 18px}
    .section{padding:78px 0}
    .cat-grid{grid-template-columns:1fr}
    .hero-meta{display:none}
    .feat{grid-template-columns:92px 1fr;gap:14px;padding:20px}
    .feat .drink{width:84px}
    .feat h3{font-size:1.3rem}
  }
  @media(prefers-reduced-motion:reduce){
    *{animation:none!important;transition:none!important}
    .reveal{opacity:1;transform:none}
  }
</style>
</head>
<body>

<header class="nav" id="nav">
  <div class="wrap nav-inner">
    <a class="logo" href="#top"><span class="dot"></span>Crema<small>· Dunedin</small></a>
    <button class="menu-toggle" id="burger" aria-label="Menu"><span></span><span></span><span></span></button>
    <nav class="nav-links" id="navlinks">
      <a href="#menu">Menu</a>
      <a href="#story">Our Story</a>
      <a href="#visit">Visit</a>
      <a class="btn" href="https://www.cremacafedunedin.com/menu">Order &amp; Gift Cards</a>
    </nav>
  </div>
</header>

<!-- ================= HERO ================= -->
<section class="hero" id="top">
  <canvas id="beanCanvas"></canvas>
  <div class="hero-content">
    <div class="wrap">
      <span class="eyebrow reveal">Single-origin · small-batch · Dunedin, FL</span>
      <h1 class="reveal">Crafting memories,<br><em>one cup</em> at a time.</h1>
      <p class="sub reveal">Discover your perfect coffee moment — expertly pulled espresso, slow pour-overs, and cold brew in a cozy neighborhood gathering place.</p>
      <div class="hero-cta reveal">
        <a class="btn" href="#menu">View the menu →</a>
        <a class="btn ghost" href="https://www.google.com/maps/search/?api=1&query=2058+Bayshore+Blvd+Suite+2+Dunedin+FL+34698" target="_blank" rel="noopener">Get directions</a>
        <span class="open-pill" id="openPill"><span class="live"></span><span id="openText">Checking hours…</span></span>
      </div>
    </div>
  </div>
  <div class="hero-meta">
    <div class="wrap">
      <span class="scroll-cue"><span class="line"></span>Scroll to explore</span>
      <span>☕ Roasted in small batches</span>
    </div>
  </div>
</section>

<!-- ================= STORY ================= -->
<section class="section light" id="story">
  <div class="wrap">
    <div class="story-grid">
      <div class="story-copy reveal">
        <span class="eyebrow">Who we are</span>
        <h2 class="head-2">More than coffee —<br>a place to gather.</h2>
        <p>Our mission is simple: to inspire and connect our community, one cup at a time. More than a coffee shop, we're a neighborhood gathering place where friends meet and ideas are born.</p>
        <p>Our beans are carefully selected from single-origin farms and roasted in small, precise batches to bring out their unique, complex flavors. We believe in quality over quantity — and our baristas are dedicated to crafting the perfect pour-over, espresso, or cold brew, every single time.</p>
        <a class="btn" href="#visit" style="margin-top:8px">Come say hello</a>
      </div>
      <div class="story-photo reveal">
        <div class="panel">
          <div class="glow"></div>
          <svg class="cupart" viewBox="0 0 220 210" role="img" aria-label="A hot cup of coffee">
            <g class="steam-g" fill="none" stroke="rgba(244,233,215,.55)" stroke-width="5" stroke-linecap="round">
              <path class="st st1" d="M86,72 q-11,-15 0,-28 q9,-11 0,-24"/>
              <path class="st st2" d="M110,68 q-11,-15 0,-28 q9,-11 0,-24"/>
              <path class="st st3" d="M134,72 q-11,-15 0,-28 q9,-11 0,-24"/>
            </g>
            <ellipse cx="110" cy="184" rx="86" ry="15" fill="#22150c"/>
            <ellipse cx="110" cy="179" rx="86" ry="15" fill="#3c2616"/>
            <path d="M158,112 q40,2 36,34 q-3,26 -36,22" fill="none" stroke="#efe3cd" stroke-width="13"/>
            <path d="M56,96 L164,96 L150,158 q-3,16 -19,16 L75,170 q-16,0 -19,-16 Z" fill="#f2e7d2"/>
            <path d="M56,96 L164,96 L150,158 q-3,16 -19,16 L75,170 q-16,0 -19,-16 Z" fill="#000" opacity=".05"/>
            <ellipse cx="110" cy="100" rx="52" ry="11" fill="#3a2210"/>
            <ellipse cx="110" cy="99" rx="40" ry="7" fill="#6b4426"/>
            <path d="M82,99 q28,-8 56,0" fill="none" stroke="#caa06a" stroke-width="3" opacity=".7"/>
          </svg>
          <div class="story-stat">
            <span class="n">100%</span>
            <span class="l">Single-origin beans, roasted in small batches</span>
          </div>
        </div>
      </div>
    </div>

    <div class="craft">
      <div class="craft-card reveal">
        <div class="craft-ic"><span class="cup"><span class="steam"></span><span class="steam"></span><span class="steam"></span><span class="body"></span></span></div>
        <h3>Espresso &amp; pour-over</h3>
        <p>Dialed-in shots and slow, hand-poured cups that let each single-origin bean speak for itself.</p>
      </div>
      <div class="craft-card reveal">
        <div class="craft-ic"><span class="bean-ic">❋</span></div>
        <h3>Small-batch roasting</h3>
        <p>Precise, careful batches that protect the delicate, complex flavors most roasters burn away.</p>
      </div>
      <div class="craft-card reveal">
        <div class="craft-ic"><span class="leaf-ic">♥</span></div>
        <h3>A neighborhood feel</h3>
        <p>A warm, welcoming room built for catching up, working, and lingering over a second cup.</p>
      </div>
    </div>
  </div>
</section>

<!-- ================= MENU ================= -->
<section class="section" id="menu">
  <div class="wrap">
    <div class="menu-head">
      <div class="reveal">
        <span class="eyebrow">What we pour</span>
        <h2 class="head-2">A menu worth slowing<br>down for.</h2>
      </div>
      <a class="btn ghost reveal" href="https://www.cremacafedunedin.com/menu">See the full menu →</a>
    </div>

    <div class="feature-grid">
      <div class="feat reveal">
        <div class="feat-ill">
          <svg class="drink" viewBox="0 0 160 220" role="img" aria-label="Caramel vanilla frappuccino">
            <defs>
              <linearGradient id="frVan" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#f6ead0"/><stop offset="1" stop-color="#ecd3a6"/></linearGradient>
              <linearGradient id="frCar" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#cf9f5d"/><stop offset="1" stop-color="#a8662f"/></linearGradient>
              <linearGradient id="frDark" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#5e3a1c"/><stop offset="1" stop-color="#3a2210"/></linearGradient>
              <clipPath id="frClip"><path d="M40,72 L120,72 L112,196 q0,8 -8,8 L56,204 q-8,0 -8,-8 Z"/></clipPath>
            </defs>
            <rect x="98" y="20" width="9" height="150" rx="4.5" transform="rotate(12 102 95)" fill="#E5A95B"/>
            <rect x="98" y="20" width="9" height="150" rx="4.5" transform="rotate(12 102 95)" fill="#ffffff" opacity=".12"/>
            <g clip-path="url(#frClip)">
              <rect x="30" y="78" width="100" height="40" fill="url(#frVan)"/>
              <rect x="30" y="116" width="100" height="56" fill="url(#frCar)"/>
              <rect x="30" y="168" width="100" height="44" fill="url(#frDark)"/>
            </g>
            <g fill="#f7eed9">
              <circle cx="64" cy="58" r="15"/><circle cx="82" cy="48" r="19"/><circle cx="100" cy="58" r="15"/>
              <circle cx="74" cy="66" r="13"/><circle cx="92" cy="66" r="13"/>
              <rect x="48" y="62" width="68" height="14" rx="6"/>
            </g>
            <path d="M58,56 q8,-10 16,-2 q8,8 18,-2 q8,-8 14,2" fill="none" stroke="#b06a2c" stroke-width="3" stroke-linecap="round" opacity=".85"/>
            <path d="M40,72 L120,72 L112,196 q0,8 -8,8 L56,204 q-8,0 -8,-8 Z" fill="none" stroke="rgba(255,243,225,.55)" stroke-width="2.4"/>
            <path d="M48,82 L54,196" stroke="rgba(255,255,255,.18)" stroke-width="3" stroke-linecap="round"/>
          </svg>
        </div>
        <div class="txt">
          <span class="tag cold">House favorite</span>
          <h3>Caramel Vanilla Frappuccino</h3>
          <p>Blended cold and creamy, ribboned with caramel and a smooth vanilla finish.</p>
        </div>
      </div>

      <div class="feat matcha reveal">
        <div class="feat-ill">
          <svg class="drink" viewBox="0 0 160 220" role="img" aria-label="Iced matcha latte">
            <defs>
              <linearGradient id="maG" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#9cbb66"/><stop offset="1" stop-color="#7c9a4a"/></linearGradient>
              <linearGradient id="maMilk" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#f1e8d6"/><stop offset="1" stop-color="#e6d8bd"/></linearGradient>
              <clipPath id="maClip"><path d="M40,72 L120,72 L112,196 q0,8 -8,8 L56,204 q-8,0 -8,-8 Z"/></clipPath>
            </defs>
            <rect x="98" y="20" width="9" height="150" rx="4.5" transform="rotate(12 102 95)" fill="#E5A95B"/>
            <rect x="98" y="20" width="9" height="150" rx="4.5" transform="rotate(12 102 95)" fill="#ffffff" opacity=".12"/>
            <g clip-path="url(#maClip)">
              <rect x="30" y="150" width="100" height="62" fill="url(#maMilk)"/>
              <rect x="30" y="78" width="100" height="74" fill="url(#maG)"/>
              <rect x="30" y="78" width="100" height="7" fill="#c7de98"/>
              <g fill="#ffffff" opacity=".30">
                <rect x="58" y="96" width="30" height="30" rx="6" transform="rotate(14 73 111)"/>
                <rect x="84" y="116" width="26" height="26" rx="5" transform="rotate(-12 97 129)"/>
                <rect x="60" y="126" width="22" height="22" rx="5" transform="rotate(22 71 137)"/>
              </g>
            </g>
            <path d="M40,72 L120,72 L112,196 q0,8 -8,8 L56,204 q-8,0 -8,-8 Z" fill="none" stroke="rgba(255,243,225,.5)" stroke-width="2.4"/>
            <path d="M48,82 L54,196" stroke="rgba(255,255,255,.16)" stroke-width="3" stroke-linecap="round"/>
          </svg>
        </div>
        <div class="txt">
          <span class="tag cold">Signature</span>
          <h3>Luck of the Irish Matcha</h3>
          <p>Stone-ground matcha layered over milk for a vivid, earthy-sweet iced refresher.</p>
        </div>
      </div>
    </div>

    <div class="cat-grid">
      <div class="cat reveal"><div class="k">Espresso Bar</div><div class="d">Lattes, cappuccinos, cortados &amp; flat whites.</div><div class="arrow">Explore →</div></div>
      <div class="cat reveal"><div class="k">Pour-Over</div><div class="d">Hand-brewed single origins, made to order.</div><div class="arrow">Explore →</div></div>
      <div class="cat reveal"><div class="k">Cold &amp; Iced</div><div class="d">Cold brew, iced lattes &amp; blended frappés.</div><div class="arrow">Explore →</div></div>
      <div class="cat reveal"><div class="k">Fresh Food</div><div class="d">Pastries &amp; bites to pair with your cup.</div><div class="arrow">Explore →</div></div>
    </div>

    <div class="marquee" aria-hidden="true">
      <div class="marquee-track">
        <span>Espresso <span class="b">·</span></span><span>Pour-Over <span class="b">·</span></span><span>Cold Brew <span class="b">·</span></span><span>Matcha <span class="b">·</span></span><span>Frappé <span class="b">·</span></span><span>Single-Origin <span class="b">·</span></span><span>Cortado <span class="b">·</span></span>
        <span>Espresso <span class="b">·</span></span><span>Pour-Over <span class="b">·</span></span><span>Cold Brew <span class="b">·</span></span><span>Matcha <span class="b">·</span></span><span>Frappé <span class="b">·</span></span><span>Single-Origin <span class="b">·</span></span><span>Cortado <span class="b">·</span></span>
      </div>
    </div>
  </div>
</section>

<!-- ================= GALLERY ================= -->
<section class="section light">
  <div class="wrap">
    <div class="menu-head">
      <div class="reveal">
        <span class="eyebrow">@Crema_Cafe_Dunedin</span>
        <h2 class="head-2">Lately, at Crema.</h2>
      </div>
      <a class="btn reveal" href="https://www.instagram.com/Crema_Cafe_Dunedin" target="_blank" rel="noopener">Follow on Instagram</a>
    </div>
    <div class="gal-grid reveal">
      <a href="https://www.instagram.com/Crema_Cafe_Dunedin" target="_blank" rel="noopener"><span class="ph"></span><img loading="lazy" alt="" onerror="this.remove()" src="https://images.squarespace-cdn.com/content/v1/68f458206634a05e2171f492/2adbcb47-0be7-417f-86f6-ade60ee4cda4/20251218_083140.jpg?format=800w"></a>
      <a href="https://www.instagram.com/Crema_Cafe_Dunedin" target="_blank" rel="noopener"><span class="ph"></span><img loading="lazy" alt="" onerror="this.remove()" src="https://images.squarespace-cdn.com/content/v1/68f458206634a05e2171f492/9d3d1391-6f66-4bcd-b6cf-0d8a2169e4cc/20251218_083205.jpg?format=800w"></a>
      <a href="https://www.instagram.com/Crema_Cafe_Dunedin" target="_blank" rel="noopener"><span class="ph"></span><img loading="lazy" alt="" onerror="this.remove()" src="https://images.squarespace-cdn.com/content/v1/68f458206634a05e2171f492/bc25c4f5-786e-4155-a30f-fd6e61d2503f/20251218_083211.jpg?format=800w"></a>
      <a href="https://www.instagram.com/Crema_Cafe_Dunedin" target="_blank" rel="noopener"><span class="ph"></span><img loading="lazy" alt="" onerror="this.remove()" src="https://images.squarespace-cdn.com/content/v1/68f458206634a05e2171f492/e389a6b0-8e59-483e-bc83-16d38aa47f64/20251218_083108+%281%29.jpg?format=800w"></a>
    </div>
  </div>
</section>

<!-- ================= VISIT ================= -->
<section class="section" id="visit">
  <div class="wrap">
    <div class="visit-grid">
      <div class="reveal">
        <span class="eyebrow">Find us</span>
        <h2 class="head-2">Stop in for your<br>next cup.</h2>
        <ul class="hours-list" id="hoursList">
          <li data-day="1"><span class="day">Monday</span><span>7:00a – 3:30p</span></li>
          <li data-day="2"><span class="day">Tuesday</span><span>7:00a – 3:30p</span></li>
          <li data-day="3"><span class="day">Wednesday</span><span>7:00a – 3:30p</span></li>
          <li data-day="4"><span class="day">Thursday</span><span>7:00a – 3:30p</span></li>
          <li data-day="5"><span class="day">Friday</span><span>7:00a – 3:30p</span></li>
          <li data-day="6"><span class="day">Saturday</span><span>7:30a – 5:00p</span></li>
          <li data-day="0"><span class="day">Sunday</span><span>8:00a – 3:30p</span></li>
        </ul>
        <div class="visit-actions">
          <a class="btn" href="tel:+17272390092">Call (727) 239-0092</a>
          <a class="btn ghost" href="https://www.google.com/maps/search/?api=1&query=2058+Bayshore+Blvd+Suite+2+Dunedin+FL+34698" target="_blank" rel="noopener">Directions →</a>
        </div>
      </div>
      <div class="addr-card reveal">
        <div class="mapdots"></div>
        <div class="pin"></div>
        <div class="a">
          <div class="big">Crema Cafe Dunedin</div>
          <p>2058 Bayshore Blvd., Suite 2</p>
          <p>Dunedin, FL 34698</p>
          <a class="ph" href="tel:+17272390092">(727) 239-0092</a>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ================= CTA BAND ================= -->
<section class="band">
  <div class="wrap">
    <h2>Your table's waiting.</h2>
    <p>Grab a gift card, or just come find your seat.</p>
    <a class="btn" href="https://www.cremacafedunedin.com/https/ordertoasttabcom/egiftcards/crema-34218-us-hwy-19-n" target="_blank" rel="noopener">Buy a gift card →</a>
  </div>
</section>

<footer class="site">
  <div class="wrap">
    <div class="foot-grid">
      <div class="foot-col">
        <a class="logo" href="#top" style="margin-bottom:16px"><span class="dot"></span>Crema<small>· Dunedin</small></a>
        <p>A neighborhood gathering place serving single-origin, small-batch coffee in Dunedin, Florida.</p>
      </div>
      <div class="foot-col">
        <h4>Explore</h4>
        <a href="#menu">Menu</a>
        <a href="#story">Our Story</a>
        <a href="#visit">Visit Us</a>
        <a href="https://www.cremacafedunedin.com/https/ordertoasttabcom/egiftcards/crema-34218-us-hwy-19-n" target="_blank" rel="noopener">Gift Cards</a>
      </div>
      <div class="foot-col">
        <h4>Visit</h4>
        <a href="https://www.google.com/maps/search/?api=1&query=2058+Bayshore+Blvd+Suite+2+Dunedin+FL+34698" target="_blank" rel="noopener">2058 Bayshore Blvd., Ste 2<br>Dunedin, FL 34698</a>
        <a href="tel:+17272390092">(727) 239-0092</a>
        <a href="https://www.instagram.com/Crema_Cafe_Dunedin" target="_blank" rel="noopener">@Crema_Cafe_Dunedin</a>
      </div>
    </div>
    <div class="foot-bottom">
      <span>© 2026 Crema Cafe Dunedin</span>
      <span>Concept redesign — not the official site</span>
    </div>
  </div>
</footer>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
/* ---------- Nav ---------- */
const nav=document.getElementById('nav');
const burger=document.getElementById('burger');
const navlinks=document.getElementById('navlinks');
addEventListener('scroll',()=>nav.classList.toggle('scrolled',scrollY>30));
burger.addEventListener('click',()=>navlinks.classList.toggle('open'));
navlinks.querySelectorAll('a').forEach(a=>a.addEventListener('click',()=>navlinks.classList.remove('open')));

/* ---------- Live open-now status ---------- */
(function(){
  // [openMinutes, closeMinutes] keyed by JS day (0=Sun..6=Sat)
  const sched={0:[480,930],1:[420,930],2:[420,930],3:[420,930],4:[420,930],5:[420,930],6:[450,1020]};
  const dayName=['Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturday'];
  function fmt(m){let h=Math.floor(m/60),mm=m%60;const ap=h>=12?'pm':'am';h=h%12||12;return mm?`${h}:${String(mm).padStart(2,'0')}${ap}`:`${h}${ap}`;}
  function etNow(){
    const s=new Date().toLocaleString('en-US',{timeZone:'America/New_York'});
    return new Date(s);
  }
  const now=etNow();
  const day=now.getDay();
  const mins=now.getHours()*60+now.getMinutes();
  const pill=document.getElementById('openPill');
  const txt=document.getElementById('openText');
  const [o,c]=sched[day];
  let open=mins>=o&&mins<c;
  if(open){
    pill.classList.add('is-open');
    txt.innerHTML=`<b>Open now</b> · closes ${fmt(c)}`;
  }else{
    pill.classList.add('is-closed');
    let d=day,steps=0,nextOpen=null;
    while(steps<8){
      if(steps===0&&mins<sched[d][0]){nextOpen={d,t:sched[d][0],same:true};break;}
      if(steps>0){nextOpen={d,t:sched[d][0],same:false};break;}
      d=(d+1)%7;steps++;
    }
    if(nextOpen){
      const when=nextOpen.same?'today':(nextOpen.d===(day+1)%7?'tomorrow':dayName[nextOpen.d]);
      txt.innerHTML=`<b>Closed</b> · opens ${fmt(nextOpen.t)} ${when}`;
    }else{txt.innerHTML='<b>Closed</b>';}
  }
  // highlight today's row
  const row=document.querySelector(`#hoursList li[data-day="${day}"]`);
  if(row)row.classList.add('today');
})();

/* ---------- Reveal on scroll ---------- */
const io=new IntersectionObserver((es)=>{
  es.forEach(e=>{if(e.isIntersecting){e.target.classList.add('in');io.unobserve(e.target);}});
},{threshold:.12});
document.querySelectorAll('.reveal').forEach((el,i)=>{el.style.transitionDelay=(i%4*60)+'ms';io.observe(el);});

/* ---------- Ambient 3D coffee beans ---------- */
(function(){
  const reduce=matchMedia('(prefers-reduced-motion:reduce)').matches;
  const canvas=document.getElementById('beanCanvas');
  let renderer;
  try{renderer=new THREE.WebGLRenderer({canvas,antialias:true,alpha:true});}
  catch(e){return;}
  const hero=canvas.parentElement;
  renderer.setPixelRatio(Math.min(devicePixelRatio,2));

  const scene=new THREE.Scene();
  scene.fog=new THREE.FogExp2(0x180e07,0.055);
  const camera=new THREE.PerspectiveCamera(50,1,0.1,100);
  camera.position.set(0,0,15);

  // lights — warm key + crema fill
  scene.add(new THREE.AmbientLight(0x3a2412,0.9));
  const key=new THREE.DirectionalLight(0xffe0ad,1.5);key.position.set(6,9,7);scene.add(key);
  const fill=new THREE.PointLight(0xE5A95B,1.1,60);fill.position.set(-8,-3,6);scene.add(fill);
  const rim=new THREE.DirectionalLight(0xffba6e,0.7);rim.position.set(-5,2,-6);scene.add(rim);

  // build a coffee bean (body + dark seam)
  const bodyGeo=new THREE.SphereGeometry(1,28,20);
  const seamGeo=new THREE.SphereGeometry(1,24,16);
  function makeBean(){
    const g=new THREE.Group();
    const body=new THREE.Mesh(bodyGeo,new THREE.MeshStandardMaterial({color:0x6b3f1d,roughness:.62,metalness:.05}));
    body.scale.set(1.0,0.66,0.46);
    const seam=new THREE.Mesh(seamGeo,new THREE.MeshStandardMaterial({color:0x2a1708,roughness:.8}));
    seam.scale.set(0.92,0.5,0.12);seam.position.y=0.30;
    const seam2=seam.clone();seam2.position.y=-0.30;seam2.rotation.x=Math.PI;
    g.add(body,seam,seam2);
    return g;
  }

  const beans=[];
  const N=14;
  for(let i=0;i<N;i++){
    const b=makeBean();
    const s=0.55+Math.random()*0.9;
    b.scale.setScalar(s);
    b.position.set((Math.random()-0.5)*22,(Math.random()-0.5)*13,(Math.random()-0.5)*8-2);
    b.rotation.set(Math.random()*Math.PI,Math.random()*Math.PI,Math.random()*Math.PI);
    b.userData={
      rx:(Math.random()-0.5)*0.004,ry:(Math.random()-0.5)*0.005,
      bob:0.4+Math.random()*0.6,phase:Math.random()*Math.PI*2,baseY:b.position.y
    };
    scene.add(b);beans.push(b);
  }

  let mx=0,my=0,tx=0,ty=0;
  addEventListener('pointermove',e=>{
    tx=(e.clientX/innerWidth-0.5);
    ty=(e.clientY/innerHeight-0.5);
  });

  function resize(){
    const w=hero.clientWidth,h=hero.clientHeight;
    renderer.setSize(w,h,false);camera.aspect=w/h;camera.updateProjectionMatrix();
  }
  addEventListener('resize',resize);resize();

  let t=0;
  function loop(){
    requestAnimationFrame(loop);
    t+=0.01;
    mx+=(tx-mx)*0.04;my+=(ty-my)*0.04;
    if(!reduce){
      beans.forEach(b=>{
        b.rotation.x+=b.userData.rx;b.rotation.y+=b.userData.ry;
        b.position.y=b.userData.baseY+Math.sin(t*b.userData.bob+b.userData.phase)*0.45;
      });
    }
    scene.rotation.y=mx*0.35;
    scene.rotation.x=my*0.2;
    camera.position.x=mx*2.2;
    camera.lookAt(0,0,0);
    renderer.render(scene,camera);
  }
  loop();
})();
</script>
</body>
</html>
