# eco-verde-website
this is my first git repository
<br>
author-june stacy
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>EcoVerde — Sustainable Products for a Better Planet</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --green: #2d6a4f;
    --green-light: #52b788;
    --green-pale: #d8f3dc;
    --earth: #b7924a;
    --earth-light: #f4e2c1;
    --cream: #faf7f2;
    --dark: #1a2e1f;
    --text: #2c3e2d;
    --muted: #6b7c6d;
    --white: #ffffff;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body { font-family: 'DM Sans', sans-serif; background: var(--cream); color: var(--text); overflow-x: hidden; }

  /* ── CURSOR ── */
  .cursor { width: 16px; height: 16px; border-radius: 50%; background: var(--green-light); position: fixed; top: 0; left: 0; pointer-events: none; z-index: 9999; transform: translate(-50%,-50%); transition: transform .15s ease, width .2s, height .2s, background .2s; mix-blend-mode: multiply; }
  .cursor.expand { width: 44px; height: 44px; background: var(--green-pale); }

  /* ── NAV ── */
  nav { position: fixed; top: 0; left: 0; right: 0; z-index: 1000; padding: 18px 5%; display: flex; justify-content: space-between; align-items: center; transition: background .4s, box-shadow .4s; }
  nav.scrolled { background: rgba(250,247,242,.95); backdrop-filter: blur(12px); box-shadow: 0 2px 24px rgba(45,106,79,.08); }
  .nav-logo { font-family: 'Playfair Display', serif; font-size: 1.6rem; font-weight: 900; color: var(--green); letter-spacing: -1px; }
  .nav-logo span { color: var(--earth); }
  .nav-links { display: flex; gap: 2.2rem; list-style: none; }
  .nav-links a { text-decoration: none; color: var(--text); font-size: .92rem; font-weight: 500; letter-spacing: .02em; transition: color .2s; }
  .nav-links a:hover { color: var(--green); }
  .nav-cta { background: var(--green); color: white; border: none; padding: 10px 26px; border-radius: 50px; font-family: 'DM Sans', sans-serif; font-size: .9rem; font-weight: 600; cursor: pointer; transition: background .2s, transform .2s; }
  .nav-cta:hover { background: var(--dark); transform: translateY(-1px); }

  /* ── HERO ── */
  #hero { min-height: 100vh; display: flex; align-items: center; position: relative; overflow: hidden; background: radial-gradient(ellipse at 70% 50%, #c7f5d8 0%, var(--cream) 65%); }
  .hero-bg-leaves { position: absolute; inset: 0; pointer-events: none; }
  .leaf { position: absolute; opacity: .18; animation: floatLeaf linear infinite; }
  @keyframes floatLeaf { 0% { transform: translateY(110vh) rotate(0deg); } 100% { transform: translateY(-20vh) rotate(360deg); } }
  .hero-content { position: relative; z-index: 2; padding: 0 5%; max-width: 700px; }
  .hero-badge { display: inline-flex; align-items: center; gap: 8px; background: var(--green-pale); color: var(--green); font-size: .8rem; font-weight: 600; letter-spacing: .08em; text-transform: uppercase; padding: 7px 18px; border-radius: 50px; margin-bottom: 2rem; animation: fadeUp .8s .2s both; }
  .hero-badge::before { content: ''; width: 8px; height: 8px; border-radius: 50%; background: var(--green-light); animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100%{transform:scale(1);opacity:1} 50%{transform:scale(1.5);opacity:.6} }
  .hero-title { font-family: 'Playfair Display', serif; font-size: clamp(3rem, 6vw, 5.2rem); font-weight: 900; line-height: 1.05; color: var(--dark); margin-bottom: 1.4rem; animation: fadeUp .8s .35s both; }
  .hero-title em { font-style: italic; color: var(--green); }
  .hero-sub { font-size: 1.15rem; font-weight: 300; color: var(--muted); line-height: 1.75; max-width: 480px; margin-bottom: 2.4rem; animation: fadeUp .8s .5s both; }
  .hero-btns { display: flex; gap: 16px; flex-wrap: wrap; animation: fadeUp .8s .65s both; }
  .btn-primary { background: var(--green); color: white; padding: 15px 36px; border-radius: 50px; font-weight: 600; font-size: 1rem; text-decoration: none; transition: background .2s, transform .2s, box-shadow .2s; display: inline-block; }
  .btn-primary:hover { background: var(--dark); transform: translateY(-3px); box-shadow: 0 12px 32px rgba(45,106,79,.25); }
  .btn-secondary { background: transparent; color: var(--green); padding: 15px 36px; border-radius: 50px; font-weight: 600; font-size: 1rem; text-decoration: none; border: 2px solid var(--green); transition: all .2s; display: inline-block; }
  .btn-secondary:hover { background: var(--green); color: white; transform: translateY(-3px); }
  .hero-visual { position: absolute; right: 4%; top: 50%; transform: translateY(-50%); width: 480px; animation: heroFloat 6s ease-in-out infinite; }
  @keyframes heroFloat { 0%,100%{transform:translateY(-50%) translateX(0);} 50%{transform:translateY(calc(-50% - 20px)) translateX(-8px);} }
  .hero-globe { width: 100%; filter: drop-shadow(0 30px 60px rgba(45,106,79,.2)); }
  .hero-stats { display: flex; gap: 3rem; margin-top: 3.5rem; animation: fadeUp .8s .8s both; }
  .stat-item { display: flex; flex-direction: column; }
  .stat-num { font-family: 'Playfair Display', serif; font-size: 2.2rem; font-weight: 900; color: var(--green); line-height: 1; }
  .stat-label { font-size: .82rem; color: var(--muted); font-weight: 400; margin-top: 4px; }

  @keyframes fadeUp { from{opacity:0;transform:translateY(30px)} to{opacity:1;transform:translateY(0)} }

  /* ── MARQUEE ── */
  .marquee-band { background: var(--green); padding: 14px 0; overflow: hidden; }
  .marquee-track { display: flex; gap: 0; width: max-content; animation: marquee 28s linear infinite; }
  .marquee-item { white-space: nowrap; font-size: .88rem; font-weight: 600; color: white; letter-spacing: .08em; padding: 0 2.5rem; opacity: .9; }
  .marquee-item span { color: var(--green-pale); margin: 0 1rem; }
  @keyframes marquee { from{transform:translateX(0)} to{transform:translateX(-50%)} }

  /* ── SECTIONS ── */
  section { padding: 100px 5%; }
  .section-label { font-size: .78rem; font-weight: 700; letter-spacing: .14em; text-transform: uppercase; color: var(--green); margin-bottom: .8rem; }
  .section-title { font-family: 'Playfair Display', serif; font-size: clamp(2rem, 4vw, 3.2rem); font-weight: 900; color: var(--dark); line-height: 1.15; margin-bottom: 1rem; }
  .section-sub { font-size: 1.05rem; color: var(--muted); line-height: 1.8; max-width: 560px; }

  /* ── COUNTRIES ── */
  #countries { background: var(--white); }
  .countries-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 6rem; align-items: center; }
  .country-flags { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1rem; }
  .country-card { background: var(--cream); border-radius: 20px; padding: 1.4rem; text-align: center; transition: transform .3s, box-shadow .3s; cursor: default; position: relative; overflow: hidden; }
  .country-card::before { content: ''; position: absolute; inset: 0; background: var(--green); transform: scaleY(0); transform-origin: bottom; transition: transform .3s; border-radius: 20px; }
  .country-card:hover { transform: translateY(-6px); box-shadow: 0 20px 40px rgba(45,106,79,.15); }
  .country-card:hover::before { transform: scaleY(1); }
  .country-card:hover .country-name, .country-card:hover .country-pct { color: white; }
  .flag { font-size: 2.2rem; display: block; margin-bottom: .5rem; position: relative; z-index: 1; }
  .country-name { font-size: .8rem; font-weight: 600; color: var(--text); display: block; position: relative; z-index: 1; transition: color .3s; }
  .country-pct { font-size: .75rem; color: var(--muted); position: relative; z-index: 1; transition: color .3s; }
  .country-card.featured { background: var(--green); }
  .country-card.featured .country-name { color: white; }
  .country-card.featured .flag { filter: drop-shadow(0 4px 8px rgba(0,0,0,.2)); }
  .country-card.featured .country-pct { color: var(--green-pale); }
  .country-card.featured::before { display: none; }

  /* ── PRODUCTS ── */
  #shop { background: var(--cream); }
  .shop-header { display: flex; justify-content: space-between; align-items: flex-end; margin-bottom: 3.5rem; }
  .filter-tabs { display: flex; gap: .6rem; }
  .tab { padding: 9px 22px; border-radius: 50px; font-size: .87rem; font-weight: 500; cursor: pointer; border: 1.5px solid var(--green-pale); background: transparent; color: var(--muted); transition: all .2s; }
  .tab.active, .tab:hover { background: var(--green); color: white; border-color: var(--green); }
  .products-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 2rem; }
  .product-card { background: white; border-radius: 24px; overflow: hidden; transition: transform .35s cubic-bezier(.25,.46,.45,.94), box-shadow .35s; cursor: pointer; }
  .product-card:hover { transform: translateY(-10px); box-shadow: 0 30px 60px rgba(45,106,79,.12); }
  .product-img { height: 220px; display: flex; align-items: center; justify-content: center; font-size: 5rem; position: relative; overflow: hidden; }
  .product-img::after { content: ''; position: absolute; inset: 0; background: linear-gradient(0deg, rgba(45,106,79,.05) 0%, transparent 60%); }
  .img-bg-1 { background: #e8f5e9; }
  .img-bg-2 { background: #fff3e0; }
  .img-bg-3 { background: #e3f2fd; }
  .img-bg-4 { background: #fce4ec; }
  .img-bg-5 { background: #f3e5f5; }
  .img-bg-6 { background: #e0f7fa; }
  .product-emoji { animation: bobProduct 4s ease-in-out infinite; display: block; }
  @keyframes bobProduct { 0%,100%{transform:translateY(0) scale(1)} 50%{transform:translateY(-12px) scale(1.08)} }
  .product-body { padding: 1.4rem 1.5rem; }
  .product-tag { font-size: .73rem; font-weight: 700; letter-spacing: .1em; text-transform: uppercase; color: var(--green); background: var(--green-pale); padding: 4px 12px; border-radius: 50px; display: inline-block; margin-bottom: .8rem; }
  .product-name { font-family: 'Playfair Display', serif; font-size: 1.2rem; font-weight: 700; color: var(--dark); margin-bottom: .5rem; }
  .product-desc { font-size: .86rem; color: var(--muted); line-height: 1.65; margin-bottom: 1.2rem; }
  .product-footer { display: flex; justify-content: space-between; align-items: center; }
  .product-price { font-family: 'Playfair Display', serif; font-size: 1.4rem; font-weight: 900; color: var(--green); }
  .product-price small { font-size: .8rem; font-family: 'DM Sans'; font-weight: 400; color: var(--muted); }
  .add-btn { background: var(--green); color: white; border: none; width: 40px; height: 40px; border-radius: 50%; font-size: 1.3rem; cursor: pointer; display: flex; align-items: center; justify-content: center; transition: background .2s, transform .2s; }
  .add-btn:hover { background: var(--dark); transform: rotate(90deg) scale(1.1); }
  .badge-new { position: absolute; top: 14px; right: 14px; background: var(--earth); color: white; font-size: .72rem; font-weight: 700; padding: 4px 12px; border-radius: 50px; letter-spacing: .06em; z-index: 2; }
  .badge-hot { position: absolute; top: 14px; right: 14px; background: #e53935; color: white; font-size: .72rem; font-weight: 700; padding: 4px 12px; border-radius: 50px; letter-spacing: .06em; z-index: 2; }

  /* ── WHY US ── */
  #why { background: var(--dark); padding: 100px 5%; }
  #why .section-label { color: var(--green-light); }
  #why .section-title { color: white; }
  #why .section-sub { color: rgba(255,255,255,.55); }
  .why-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 2rem; margin-top: 4rem; }
  .why-card { background: rgba(255,255,255,.04); border: 1px solid rgba(255,255,255,.08); border-radius: 24px; padding: 2rem; transition: background .3s, transform .3s; }
  .why-card:hover { background: rgba(82,183,136,.1); border-color: rgba(82,183,136,.3); transform: translateY(-6px); }
  .why-icon { width: 56px; height: 56px; border-radius: 16px; background: rgba(82,183,136,.15); display: flex; align-items: center; justify-content: center; font-size: 1.6rem; margin-bottom: 1.2rem; }
  .why-title { font-size: 1.05rem; font-weight: 600; color: white; margin-bottom: .6rem; }
  .why-desc { font-size: .88rem; color: rgba(255,255,255,.5); line-height: 1.7; }

  /* ── IMPACT ── */
  #impact { background: var(--green-pale); }
  .impact-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 2rem; margin-top: 3rem; }
  .impact-card { text-align: center; padding: 2rem 1rem; }
  .impact-num { font-family: 'Playfair Display', serif; font-size: 3.5rem; font-weight: 900; color: var(--green); display: block; line-height: 1; }
  .impact-label { font-size: .9rem; color: var(--muted); margin-top: .5rem; font-weight: 500; }
  .impact-icon { font-size: 2rem; display: block; }

  /* ── TESTIMONIALS ── */
  #testimonials { background: white; }
  .testimonials-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 2rem; margin-top: 3rem; }
  .testi-card { background: var(--cream); border-radius: 24px; padding: 2rem; position: relative; transition: transform .3s; }
  .testi-card:hover { transform: translateY(-6px); }
  .stars { color: var(--earth); font-size: 1rem; margin-bottom: 1rem; letter-spacing: .1em; }
  .testi-text { font-size: .95rem; color: var(--text); line-height: 1.8; font-style: italic; margin-bottom: 1.4rem; }
  .testi-author { display: flex; align-items: center; gap: .8rem; }
  .testi-avatar { width: 44px; height: 44px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 1.3rem; background: var(--green-pale); }
  .testi-name { font-weight: 600; font-size: .9rem; color: var(--dark); }
  .testi-country { font-size: .78rem; color: var(--muted); }
  .quote-mark { position: absolute; top: 1.5rem; right: 1.8rem; font-family: 'Playfair Display', serif; font-size: 5rem; color: var(--green-pale); line-height: 1; font-weight: 900; }

  /* ── NEWSLETTER ── */
  #newsletter { background: var(--green); text-align: center; padding: 80px 5%; }
  #newsletter .section-label { color: var(--green-pale); }
  #newsletter .section-title { color: white; }
  #newsletter .section-sub { color: rgba(255,255,255,.7); margin: 0 auto 2.5rem; }
  .nl-form { display: flex; gap: 12px; max-width: 480px; margin: 0 auto; }
  .nl-input { flex: 1; padding: 15px 22px; border-radius: 50px; border: none; font-family: 'DM Sans'; font-size: .95rem; outline: none; }
  .nl-btn { background: var(--dark); color: white; border: none; padding: 15px 28px; border-radius: 50px; font-family: 'DM Sans'; font-weight: 600; cursor: pointer; transition: background .2s, transform .2s; white-space: nowrap; }
  .nl-btn:hover { background: var(--earth); transform: translateY(-2px); }

  /* ── FOOTER ── */
  footer { background: var(--dark); color: rgba(255,255,255,.65); padding: 60px 5% 30px; }
  .footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr 1fr; gap: 3rem; margin-bottom: 3rem; }
  .footer-brand { font-family: 'Playfair Display', serif; font-size: 1.8rem; font-weight: 900; color: white; margin-bottom: .8rem; }
  .footer-brand span { color: var(--green-light); }
  .footer-tagline { font-size: .9rem; line-height: 1.7; margin-bottom: 1.5rem; }
  .social-links { display: flex; gap: .8rem; }
  .social-link { width: 38px; height: 38px; border-radius: 50%; background: rgba(255,255,255,.08); display: flex; align-items: center; justify-content: center; font-size: 1rem; text-decoration: none; transition: background .2s; }
  .social-link:hover { background: var(--green); }
  .footer-col h4 { color: white; font-size: .9rem; font-weight: 600; margin-bottom: 1.2rem; letter-spacing: .04em; }
  .footer-col ul { list-style: none; }
  .footer-col ul li { margin-bottom: .6rem; }
  .footer-col ul a { text-decoration: none; color: rgba(255,255,255,.5); font-size: .88rem; transition: color .2s; }
  .footer-col ul a:hover { color: var(--green-light); }
  .footer-bottom { border-top: 1px solid rgba(255,255,255,.08); padding-top: 1.5rem; display: flex; justify-content: space-between; align-items: center; font-size: .83rem; flex-wrap: wrap; gap: 1rem; }

  /* ── CART TOAST ── */
  .cart-toast { position: fixed; bottom: 2rem; right: 2rem; background: var(--dark); color: white; padding: 1rem 1.5rem; border-radius: 16px; font-size: .9rem; transform: translateY(120px); transition: transform .4s cubic-bezier(.25,.46,.45,.94); z-index: 9999; display: flex; align-items: center; gap: .8rem; box-shadow: 0 16px 40px rgba(0,0,0,.3); }
  .cart-toast.show { transform: translateY(0); }
  .cart-count { background: var(--green-light); color: white; font-weight: 700; font-size: .78rem; padding: 2px 8px; border-radius: 50px; }

  /* ── ANIMATIONS on scroll ── */
  .reveal { opacity: 0; transform: translateY(40px); transition: opacity .7s ease, transform .7s ease; }
  .reveal.visible { opacity: 1; transform: translateY(0); }
  .reveal-delay-1 { transition-delay: .1s; }
  .reveal-delay-2 { transition-delay: .2s; }
  .reveal-delay-3 { transition-delay: .3s; }
  .reveal-delay-4 { transition-delay: .4s; }

  /* ── STICKY CART ── */
  .sticky-cart { position: fixed; bottom: 2rem; left: 2rem; background: var(--green); color: white; border: none; border-radius: 50px; padding: 12px 22px; font-family: 'DM Sans'; font-size: .9rem; font-weight: 600; cursor: pointer; display: flex; align-items: center; gap: 10px; transition: background .2s, transform .2s; z-index: 990; box-shadow: 0 8px 24px rgba(45,106,79,.3); }
  .sticky-cart:hover { background: var(--dark); transform: scale(1.04); }
  .cart-badge { background: var(--earth); border-radius: 50%; width: 22px; height: 22px; display: flex; align-items: center; justify-content: center; font-size: .72rem; font-weight: 700; }

  @media(max-width: 900px) {
    .hero-visual { display: none; }
    .countries-grid { grid-template-columns: 1fr; }
    .footer-grid { grid-template-columns: 1fr 1fr; }
    nav .nav-links { display: none; }
  }
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>

<!-- NAV -->
<nav id="navbar">
  <div class="nav-logo">Eco<span>Verde</span></div>
  <ul class="nav-links">
    <li><a href="#shop">Shop</a></li>
    <li><a href="#why">Why Us</a></li>
    <li><a href="#impact">Impact</a></li>
    <li><a href="#countries">Global</a></li>
    <li><a href="#testimonials">Reviews</a></li>
  </ul>
  <button class="nav-cta" onclick="document.getElementById('shop').scrollIntoView({behavior:'smooth'})">Shop Now 🌿</button>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg-leaves" id="leavesContainer"></div>
  <div class="hero-content">
    <div class="hero-badge">🌍 Trusted in 40+ Countries</div>
    <h1 class="hero-title">Live <em>Green,</em><br>Live Better.</h1>
    <p class="hero-sub">Premium eco-friendly products crafted for conscious consumers worldwide. From Switzerland to Singapore, we deliver sustainability to your door.</p>
    <div class="hero-btns">
      <a href="#shop" class="btn-primary">Explore Products →</a>
      <a href="#impact" class="btn-secondary">Our Impact</a>
    </div>
    <div class="hero-stats">
      <div class="stat-item">
        <span class="stat-num" id="counter1">0</span>
        <span class="stat-label">Happy Customers</span>
      </div>
      <div class="stat-item">
        <span class="stat-num" id="counter2">0</span>
        <span class="stat-label">Tons CO₂ Saved</span>
      </div>
      <div class="stat-item">
        <span class="stat-num" id="counter3">0</span>
        <span class="stat-label">Products</span>
      </div>
    </div>
  </div>

  <!-- SVG Globe Illustration -->
  <div class="hero-visual">
    <svg class="hero-globe" viewBox="0 0 460 460" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <radialGradient id="gGlobe" cx="40%" cy="35%">
          <stop offset="0%" stop-color="#d8f3dc"/>
          <stop offset="100%" stop-color="#95d5b2"/>
        </radialGradient>
        <radialGradient id="gSea" cx="50%" cy="50%">
          <stop offset="0%" stop-color="#a8d8ea"/>
          <stop offset="100%" stop-color="#6ec6e6"/>
        </radialGradient>
        <clipPath id="circClip">
          <circle cx="230" cy="230" r="185"/>
        </clipPath>
      </defs>
      <circle cx="230" cy="230" r="210" fill="none" stroke="#c7f5d8" stroke-width="2" opacity=".5"/>
      <circle cx="230" cy="230" r="196" fill="none" stroke="#c7f5d8" stroke-width="1" opacity=".3"/>
      <circle cx="230" cy="230" r="185" fill="url(#gSea)"/>
      <g clip-path="url(#circClip)">
        <ellipse cx="240" cy="160" rx="38" ry="50" fill="url(#gGlobe)" opacity=".9"/>
        <ellipse cx="248" cy="235" rx="30" ry="55" fill="#52b788" opacity=".8"/>
        <ellipse cx="140" cy="175" rx="32" ry="60" fill="url(#gGlobe)" opacity=".85" transform="rotate(-10,140,175)"/>
        <ellipse cx="145" cy="270" rx="25" ry="45" fill="#52b788" opacity=".75" transform="rotate(5,145,270)"/>
        <ellipse cx="320" cy="165" rx="55" ry="45" fill="url(#gGlobe)" opacity=".9"/>
        <ellipse cx="345" cy="280" rx="28" ry="22" fill="url(#gGlobe)" opacity=".85"/>
        <line x1="45" y1="230" x2="415" y2="230" stroke="white" stroke-width="0.5" opacity=".3"/>
        <ellipse cx="230" cy="230" rx="185" ry="55" fill="none" stroke="white" stroke-width="0.5" opacity=".25"/>
        <ellipse cx="230" cy="230" rx="185" ry="115" fill="none" stroke="white" stroke-width="0.5" opacity=".2"/>
        <line x1="230" y1="45" x2="230" y2="415" stroke="white" stroke-width="0.5" opacity=".25"/>
      </g>
      <g>
        <circle cx="240" cy="155" r="7" fill="#e63946" opacity=".9"/>
        <circle cx="240" cy="155" r="12" fill="#e63946" opacity=".25"/>
        <circle cx="135" cy="175" r="6" fill="#e63946" opacity=".8"/>
        <circle cx="320" cy="160" r="6" fill="#e63946" opacity=".8"/>
        <circle cx="345" cy="280" r="5" fill="#e63946" opacity=".75"/>
        <circle cx="245" cy="240" r="5" fill="#e63946" opacity=".75"/>
      </g>
      <g transform="translate(60,70)" opacity=".7">
        <ellipse cx="0" cy="0" rx="18" ry="10" fill="#52b788" transform="rotate(-30)"/>
        <line x1="0" y1="0" x2="0" y2="-8" stroke="#2d6a4f" stroke-width="1"/>
      </g>
      <g transform="translate(380,100)" opacity=".6">
        <ellipse cx="0" cy="0" rx="14" ry="8" fill="#52b788" transform="rotate(25)"/>
        <line x1="0" y1="0" x2="0" y2="-6" stroke="#2d6a4f" stroke-width="1"/>
      </g>
      <g transform="translate(390,350)" opacity=".55">
        <ellipse cx="0" cy="0" rx="16" ry="9" fill="#95d5b2" transform="rotate(-15)"/>
      </g>
      <g transform="translate(240,152)">
        <rect x="-14" y="-32" width="28" height="20" rx="4" fill="white" stroke="#ccc" stroke-width="0.5"/>
        <rect x="-14" y="-32" width="28" height="20" rx="4" fill="#d52b1e"/>
        <rect x="-5" y="-30" width="10" height="16" fill="white"/>
        <rect x="-11" y="-26" width="22" height="6" fill="white"/>
        <polygon points="0,-34 -4,-44 4,-44" fill="#d52b1e"/>
      </g>
    </svg>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-band">
  <div class="marquee-track" id="marquee">
    <span class="marquee-item">🌱 Zero Plastic <span>✦</span></span>
    <span class="marquee-item">♻️ 100% Recycled Materials <span>✦</span></span>
    <span class="marquee-item">🌍 Carbon Neutral Shipping <span>✦</span></span>
    <span class="marquee-item">🇨🇭 Loved in Switzerland <span>✦</span></span>
    <span class="marquee-item">🌿 Certified Organic <span>✦</span></span>
    <span class="marquee-item">💧 Ocean-Friendly Formulas <span>✦</span></span>
    <span class="marquee-item">🌱 Zero Plastic <span>✦</span></span>
    <span class="marquee-item">♻️ 100% Recycled Materials <span>✦</span></span>
    <span class="marquee-item">🌍 Carbon Neutral Shipping <span>✦</span></span>
    <span class="marquee-item">🇨🇭 Loved in Switzerland <span>✦</span></span>
    <span class="marquee-item">🌿 Certified Organic <span>✦</span></span>
    <span class="marquee-item">💧 Ocean-Friendly Formulas <span>✦</span></span>
  </div>
</div>

<!-- COUNTRIES -->
<section id="countries">
  <div class="countries-grid">
    <div>
      <p class="section-label reveal">🌍 Global Reach</p>
      <h2 class="section-title reveal reveal-delay-1">Shipped to<br><em style="color:var(--green);font-style:italic;">40+ Countries</em></h2>
      <p class="section-sub reveal reveal-delay-2">From the eco-conscious streets of Zurich to Tokyo's sustainable living movement — EcoVerde reaches conscious consumers everywhere. Switzerland leads our global community.</p>
      <br>
      <div class="reveal reveal-delay-3" style="display:flex;gap:1rem;flex-wrap:wrap;margin-top:.5rem">
        <div style="background:var(--green-pale);padding:10px 18px;border-radius:50px;font-size:.85rem;font-weight:600;color:var(--green)">🏆 #1 in Switzerland</div>
        <div style="background:var(--earth-light);padding:10px 18px;border-radius:50px;font-size:.85rem;font-weight:600;color:var(--earth)">⚡ Same-day EU Dispatch</div>
      </div>
    </div>
    <div class="country-flags reveal reveal-delay-2">
      <div class="country-card featured">
        <span class="flag">🇨🇭</span>
        <span class="country-name">Switzerland</span>
        <span class="country-pct">★ #1 Market</span>
      </div>
      <div class="country-card">
        <span class="flag">🇩🇪</span>
        <span class="country-name">Germany</span>
        <span class="country-pct">18% orders</span>
      </div>
      <div class="country-card">
        <span class="flag">🇫🇷</span>
        <span class="country-name">France</span>
        <span class="country-pct">12% orders</span>
      </div>
      <div class="country-card">
        <span class="flag">🇬🇧</span>
        <span class="country-name">UK</span>
        <span class="country-pct">11% orders</span>
      </div>
      <div class="country-card">
        <span class="flag">🇯🇵</span>
        <span class="country-name">Japan</span>
        <span class="country-pct">9% orders</span>
      </div>
      <div class="country-card">
        <span class="flag">🇺🇸</span>
        <span class="country-name">USA</span>
        <span class="country-pct">8% orders</span>
      </div>
      <div class="country-card">
        <span class="flag">🇦🇺</span>
        <span class="country-name">Australia</span>
        <span class="country-pct">7% orders</span>
      </div>
      <div class="country-card">
        <span class="flag">🇨🇦</span>
        <span class="country-name">Canada</span>
        <span class="country-pct">6% orders</span>
      </div>
      <div class="country-card">
        <span class="flag">🌏</span>
        <span class="country-name">+33 More</span>
        <span class="country-pct">Worldwide</span>
      </div>
    </div>
  </div>
</section>

<!-- SHOP -->
<section id="shop">
  <div class="shop-header">
    <div>
      <p class="section-label">🛒 Our Collection</p>
      <h2 class="section-title">Shop Eco Products</h2>
    </div>
    <div class="filter-tabs">
      <button class="tab active" onclick="filterProducts('all',this)">All</button>
      <button class="tab" onclick="filterProducts('home',this)">Home</button>
      <button class="tab" onclick="filterProducts('personal',this)">Personal Care</button>
      <button class="tab" onclick="filterProducts('food',this)">Food & Kitchen</button>
    </div>
  </div>
  <div class="products-grid" id="productsGrid"></div>
  <div style="text-align:center;margin-top:3rem">
    <a href="#" class="btn-primary" onclick="return false" style="display:inline-block">Load More Products ↓</a>
  </div>
</section>

<!-- WHY -->
<section id="why">
  <div style="max-width:560px">
    <p class="section-label">💚 Why EcoVerde</p>
    <h2 class="section-title">More Than a Product,<br>It's a <em style="color:var(--green-light);font-style:italic;">Movement</em></h2>
  </div>
  <div class="why-grid" style="margin-top:3.5rem">
    <div class="why-card reveal">
      <div class="why-icon">🌱</div>
      <h3 class="why-title">100% Organic Materials</h3>
      <p class="why-desc">Every product is certified organic, biodegradable, and free from harmful chemicals. Verified by independent Swiss labs.</p>
    </div>
    <div class="why-card reveal reveal-delay-1">
      <div class="why-icon">🚢</div>
      <h3 class="why-title">Carbon-Neutral Shipping</h3>
      <p class="why-desc">We offset 110% of our shipping emissions through verified forest restoration projects worldwide.</p>
    </div>
    <div class="why-card reveal reveal-delay-2">
      <div class="why-icon">♻️</div>
      <h3 class="why-title">Zero Waste Packaging</h3>
      <p class="why-desc">All packaging is made from recycled ocean plastics or seed paper you can plant after unboxing.</p>
    </div>
    <div class="why-card reveal reveal-delay-3">
      <div class="why-icon">🤝</div>
      <h3 class="why-title">Fair Trade Certified</h3>
      <p class="why-desc">We partner with 60+ artisan cooperatives across 12 countries, ensuring fair wages and safe conditions.</p>
    </div>
  </div>
</section>

<!-- IMPACT -->
<section id="impact">
  <div style="text-align:center;max-width:600px;margin:0 auto">
    <p class="section-label reveal">📊 Our Planet Impact</p>
    <h2 class="section-title reveal reveal-delay-1">Numbers That<br>Actually <em style="color:var(--green);font-style:italic;">Matter</em></h2>
  </div>
  <div class="impact-grid" style="margin-top:3rem">
    <div class="impact-card reveal">
      <span class="impact-icon">🌳</span>
      <span class="impact-num">84K+</span>
      <span class="impact-label">Trees Planted</span>
    </div>
    <div class="impact-card reveal reveal-delay-1">
      <span class="impact-icon">🌊</span>
      <span class="impact-num">12T</span>
      <span class="impact-label">Plastic Removed from Ocean</span>
    </div>
    <div class="impact-card reveal reveal-delay-2">
      <span class="impact-icon">☁️</span>
      <span class="impact-num">950T</span>
      <span class="impact-label">CO₂ Offset (tonnes)</span>
    </div>
    <div class="impact-card reveal reveal-delay-3">
      <span class="impact-icon">👩‍🌾</span>
      <span class="impact-num">1,200</span>
      <span class="impact-label">Artisans Supported</span>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section id="testimonials">
  <div style="text-align:center;max-width:600px;margin:0 auto 3rem">
    <p class="section-label reveal">💬 Customer Stories</p>
    <h2 class="section-title reveal reveal-delay-1">Loved Around the <em style="color:var(--green);font-style:italic;">World</em></h2>
  </div>
  <div class="testimonials-grid">
    <div class="testi-card reveal">
      <div class="quote-mark">"</div>
      <div class="stars">★★★★★</div>
      <p class="testi-text">EcoVerde completely transformed how I shop. The bamboo kit arrived in the most beautiful seed-paper packaging I've ever seen. Truly Swiss quality.</p>
      <div class="testi-author">
        <div class="testi-avatar">🧖‍♀️</div>
        <div>
          <div class="testi-name">Mia Hoffmann</div>
          <div class="testi-country">🇨🇭 Zurich, Switzerland</div>
        </div>
      </div>
    </div>
    <div class="testi-card reveal reveal-delay-1">
      <div class="quote-mark">"</div>
      <div class="stars">★★★★★</div>
      <p class="testi-text">I've tried many eco brands but nothing compares. The reusable beeswax wraps saved me from so much single-use plastic. Fast shipping to Tokyo too!</p>
      <div class="testi-author">
        <div class="testi-avatar">👨‍💻</div>
        <div>
          <div class="testi-name">Kenji Tanaka</div>
          <div class="testi-country">🇯🇵 Tokyo, Japan</div>
        </div>
      </div>
    </div>
    <div class="testi-card reveal reveal-delay-2">
      <div class="quote-mark">"</div>
      <div class="stars">★★★★★</div>
      <p class="testi-text">The natural cleaning set is incredible. My home smells amazing and I know my kids are safe. And knowing every purchase plants a tree — chef's kiss!</p>
      <div class="testi-author">
        <div class="testi-avatar">👩‍🦰</div>
        <div>
          <div class="testi-name">Sophie Laurent</div>
          <div class="testi-country">🇫🇷 Paris, France</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- NEWSLETTER -->
<section id="newsletter">
  <p class="section-label">📧 Stay Green</p>
  <h2 class="section-title">Join 50,000+ Eco Warriors</h2>
  <p class="section-sub">Get sustainable living tips, exclusive offers, and impact reports straight to your inbox.</p>
  <div class="nl-form">
    <input class="nl-input" type="email" placeholder="your@email.com" id="nlEmail"/>
    <button class="nl-btn" onclick="subscribeNL()">Subscribe 🌿</button>
  </div>
  <p style="font-size:.8rem;color:rgba(255,255,255,.45);margin-top:1rem">No spam, ever. Unsubscribe anytime. 🌱</p>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-grid">
    <div>
      <div class="footer-brand">Eco<span>Verde</span></div>
      <p class="footer-tagline">Premium eco-friendly products for a planet that deserves better. Certified sustainable. Globally loved.</p>
      <div class="social-links">
        <a class="social-link" href="#" title="Instagram">📸</a>
        <a class="social-link" href="#" title="Twitter">🐦</a>
        <a class="social-link" href="#" title="Facebook">👍</a>
        <a class="social-link" href="#" title="YouTube">▶️</a>
        <a class="social-link" href="#" title="Pinterest">📌</a>
      </div>
    </div>
    <div class="footer-col">
      <h4>Shop</h4>
      <ul>
        <li><a href="#">Home Care</a></li>
        <li><a href="#">Personal Care</a></li>
        <li><a href="#">Food & Kitchen</a></li>
        <li><a href="#">Gifts & Bundles</a></li>
        <li><a href="#">New Arrivals</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Company</h4>
      <ul>
        <li><a href="#">Our Story</a></li>
        <li><a href="#">B Corp Status</a></li>
        <li><a href="#">Impact Report</a></li>
        <li><a href="#">Blog</a></li>
        <li><a href="#">Press</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Support</h4>
      <ul>
        <li><a href="#">Shipping Info</a></li>
        <li><a href="#">Returns Policy</a></li>
        <li><a href="#">Track Order</a></li>
        <li><a href="#">FAQ</a></li>
        <li><a href="#">Contact Us</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2025 EcoVerde. All rights reserved. 🌿</span>
    <span>Privacy Policy · Terms · Cookie Settings</span>
    <span>🇨🇭 Made with love for the planet</span>
  </div>
</footer>

<!-- STICKY CART -->
<button class="sticky-cart" id="stickyCart" onclick="viewCart()">
  🛒 Cart <span class="cart-badge" id="cartBadge">0</span>
</button>

<!-- TOAST -->
<div class="cart-toast" id="cartToast">
  <span>🛒</span>
  <span id="toastMsg">Added to cart!</span>
  <span class="cart-count" id="toastCount">1</span>
</div>

<script>
  // ── CURSOR ──
  const cursor = document.getElementById('cursor');
  document.addEventListener('mousemove', e => {
    cursor.style.left = e.clientX + 'px';
    cursor.style.top = e.clientY + 'px';
  });
  document.querySelectorAll('a,button,.product-card,.country-card').forEach(el => {
    el.addEventListener('mouseenter', () => cursor.classList.add('expand'));
    el.addEventListener('mouseleave', () => cursor.classList.remove('expand'));
  });

  // ── NAV SCROLL ──
  window.addEventListener('scroll', () => {
    document.getElementById('navbar').classList.toggle('scrolled', window.scrollY > 60);
  });

  // ── FLOATING LEAVES ──
  const leavesContainer = document.getElementById('leavesContainer');
  const leafColors = ['#52b788','#2d6a4f','#95d5b2','#b7e4c7','#74c69d'];
  for (let i = 0; i < 18; i++) {
    const leaf = document.createElement('div');
    leaf.className = 'leaf';
    const size = 12 + Math.random() * 30;
    leaf.innerHTML = `<svg width="${size}" height="${size * 1.6}" viewBox="0 0 20 32">
      <ellipse cx="10" cy="16" rx="9" ry="14" fill="${leafColors[Math.floor(Math.random()*leafColors.length)]}" transform="rotate(${Math.random()*30-15},10,16)"/>
      <line x1="10" y1="4" x2="10" y2="28" stroke="#1b4332" stroke-width="1"/>
    </svg>`;
    leaf.style.cssText = `left:${Math.random()*100}%;animation-duration:${6+Math.random()*12}s;animation-delay:${-Math.random()*15}s`;
    leavesContainer.appendChild(leaf);
  }

  // ── COUNTER ANIMATION ──
  function animateCounter(el, target, suffix='', duration=2000) {
    let start = 0, step = target / (duration / 16);
    const timer = setInterval(() => {
      start = Math.min(start + step, target);
      el.textContent = Math.floor(start).toLocaleString() + suffix;
      if (start >= target) clearInterval(timer);
    }, 16);
  }
  let countersStarted = false;
  const heroObserver = new IntersectionObserver(([entry]) => {
    if (entry.isIntersecting && !countersStarted) {
      countersStarted = true;
      animateCounter(document.getElementById('counter1'), 52000, '+');
      animateCounter(document.getElementById('counter2'), 950, 'T');
      animateCounter(document.getElementById('counter3'), 120, '+');
    }
  });
  heroObserver.observe(document.getElementById('hero'));

  // ── PRODUCTS DATA ──
  const products = [
    { name:'Bamboo Essentials Kit', desc:'Complete personal care kit made from sustainably harvested bamboo. Includes toothbrush, comb & nail brush.', price:24.90, tag:'Home', emoji:'🪥', bg:'img-bg-1', badge:'new', cat:'home' },
    { name:'Beeswax Food Wraps', desc:'Replace single-use cling film with these reusable, organic beeswax-coated cotton wraps. Set of 3 sizes.', price:18.50, tag:'Kitchen', emoji:'🍯', bg:'img-bg-2', badge:'hot', cat:'food' },
    { name:'Ocean Soap Bars (3-pack)', desc:'Cold-pressed artisan soaps made from ocean-collected algae and organic essential oils. Zero-plastic wrapped.', price:22.00, tag:'Personal Care', emoji:'🧼', bg:'img-bg-3', badge:null, cat:'personal' },
    { name:'Reusable Produce Bags', desc:'Lightweight organic cotton mesh bags for shopping. Set of 8 various sizes. Machine washable.', price:14.90, tag:'Kitchen', emoji:'🥦', bg:'img-bg-4', badge:null, cat:'food' },
    { name:'Natural Cleaning Kit', desc:'Plant-based multi-surface cleaner concentrate. Makes 10 bottles. Biodegradable, child & pet safe.', price:32.00, tag:'Home', emoji:'🫧', bg:'img-bg-5', badge:'new', cat:'home' },
    { name:'Seed Paper Notebook', desc:'Write your story, then plant the pages. Embedded with wildflower seeds. 100% recycled post-consumer paper.', price:16.00, tag:'Lifestyle', emoji:'📔', bg:'img-bg-6', badge:null, cat:'home' },
  ];

  let cart = 0;

  function renderProducts(filter='all') {
    const grid = document.getElementById('productsGrid');
    const filtered = filter === 'all' ? products : products.filter(p => p.cat === filter);
    grid.innerHTML = filtered.map((p, i) => `
      <div class="product-card reveal" style="transition-delay:${i*0.08}s">
        <div class="product-img ${p.bg}" style="position:relative">
          ${p.badge === 'new' ? '<span class="badge-new">NEW</span>' : p.badge === 'hot' ? '<span class="badge-hot">🔥 BESTSELLER</span>' : ''}
          <span class="product-emoji">${p.emoji}</span>
        </div>
        <div class="product-body">
          <span class="product-tag">${p.tag}</span>
          <div class="product-name">${p.name}</div>
          <p class="product-desc">${p.desc}</p>
          <div class="product-footer">
            <div class="product-price">CHF ${p.price.toFixed(2)} <small>/ unit</small></div>
            <button class="add-btn" onclick="addToCart('${p.name.replace(/'/g,'')}')" title="Add to cart">+</button>
          </div>
        </div>
      </div>
    `).join('');
    observeReveal();
  }

  function filterProducts(cat, btn) {
    document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
    btn.classList.add('active');
    renderProducts(cat);
  }

  function addToCart(name) {
    cart++;
    document.getElementById('cartBadge').textContent = cart;
    const toast = document.getElementById('cartToast');
    document.getElementById('toastMsg').textContent = name + ' added!';
    document.getElementById('toastCount').textContent = cart;
    toast.classList.add('show');
    setTimeout(() => toast.classList.remove('show'), 2800);
  }

  function viewCart() {
    if (cart === 0) { alert('Your cart is empty! Add some eco products 🌿'); return; }
    alert(`🛒 You have ${cart} item(s) in your cart.\n\nCheckout coming soon — we're building a planet-friendly checkout experience! 🌍`);
  }

  function subscribeNL() {
    const email = document.getElementById('nlEmail').value;
    if (!email || !email.includes('@')) { alert('Please enter a valid email 📧'); return; }
    alert(`🌿 Welcome to the EcoVerde community!\n\nWe've sent a confirmation to ${email}.\nTogether we make the planet greener! 🌍`);
    document.getElementById('nlEmail').value = '';
  }

  // ── SCROLL REVEAL ──
  function observeReveal() {
    const revealObserver = new IntersectionObserver((entries) => {
      entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); revealObserver.unobserve(e.target); } });
    }, { threshold: 0.12 });
    document.querySelectorAll('.reveal:not(.visible)').forEach(el => revealObserver.observe(el));
  }


  renderProducts();
  observeReveal();
</script>
</body>
</html>
