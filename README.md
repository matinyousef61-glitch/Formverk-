# Formverk-
A website their we building website at other
<!DOCTYPE html>
<html lang="sv">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Formverk — hemsidor för företag</title>
<meta name="description" content="Formverk designar och bygger skräddarsydda hemsidor för små och medelstora företag — snabbt, SEO-anpassat och till fast pris.">
<meta property="og:title" content="Formverk — hemsidor för företag">
<meta property="og:description" content="Skräddarsydda hemsidor som ger fler kunder, inte bara fin design.">
<meta property="og:type" content="website">
<link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 200 200'%3E%3Crect width='200' height='200' fill='%23F6F3EC'/%3E%3Cpolygon points='40,15 155,15 155,50 90,50 90,95 150,95 150,130 90,130 90,185 40,185' fill='%231B1A14'/%3E%3Crect x='90' y='95' width='60' height='35' fill='%238A6D2B'/%3E%3C/svg%3E">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,500;9..144,600;9..144,700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg: #F6F3EC;
    --panel: #ECE5D5;
    --ink: #1B1A14;
    --surface-dark: #2E301C;
    --accent: #8A6D2B;
    --accent-dark: #6E5620;
    --accent-soft: #EDE1BE;
    --stone: #D8D0BB;
    --muted: #736C5C;
    --white: #FFFFFF;
    --radius: 2px;
    --maxw: 1120px;
  }

  *{ box-sizing: border-box; }
  html{ scroll-behavior: smooth; }
  body{
    margin:0;
    background: var(--bg);
    color: var(--ink);
    font-family: 'Inter', system-ui, sans-serif;
    font-size: 16px;
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
  }
  h1,h2,h3{
    font-family: 'Fraunces', Georgia, serif;
    font-weight: 500;
    line-height: 1.08;
    margin: 0;
    letter-spacing: -0.01em;
  }
  p{ margin: 0; color: var(--ink); }
  a{ color: inherit; }
  img,svg{ display:block; max-width:100%; }

  a:focus-visible, button:focus-visible, input:focus-visible, textarea:focus-visible{
    outline: 2px solid var(--accent);
    outline-offset: 3px;
  }

  .wrap{
    max-width: var(--maxw);
    margin: 0 auto;
    padding: 0 32px;
  }

  /* ---------- Header ---------- */
  header{
    position: sticky;
    top: 0;
    z-index: 50;
    background: var(--bg);
    border-bottom: 1px solid var(--stone);
  }
  .progress-bar{
    position: fixed;
    top: 0; left: 0;
    height: 3px;
    width: 0%;
    background: var(--accent);
    z-index: 100;
  }
  .nav{
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding: 18px 32px;
    max-width: var(--maxw);
    margin: 0 auto;
    gap: 24px;
  }
  .logo{
    display:flex;
    align-items:center;
    gap: 10px;
    font-family:'Fraunces', serif;
    font-weight:600;
    font-size:1.25rem;
    letter-spacing: -0.01em;
    text-decoration:none;
  }
  .logo-mark{ width: 26px; height: 26px; flex-shrink:0; }

  .navlinks{
    display:flex;
    align-items:center;
    gap: 28px;
    list-style:none;
    margin:0; padding:0;
  }
  .navlinks > li{ position:relative; }
  .navlinks a{
    text-decoration:none;
    font-size: 0.95rem;
    color: var(--ink);
    position:relative;
    padding-bottom: 3px;
  }
  .navlinks a::after{
    content:"";
    position:absolute; left:0; right:0; bottom:0;
    height: 1px; background: var(--accent);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.2s ease;
  }
  .navlinks a:hover::after, .navlinks a.active::after{ transform: scaleX(1); }
  .navlinks a.active{ color: var(--accent); }

  .has-dropdown{ display:flex; align-items:center; gap:5px; color: var(--ink); }
  .has-dropdown .caret{ width:9px; height:9px; cursor:pointer; transition: transform 0.2s ease; }
  .nav-item-dropdown:hover .caret{ transform: rotate(180deg); }

  .dropdown-panel{
    position:absolute;
    top: calc(100% + 18px);
    left: 50%;
    transform: translateX(-50%) translateY(6px);
    background: var(--white);
    border: 1px solid var(--stone);
    border-radius: var(--radius);
    padding: 8px;
    min-width: 230px;
    box-shadow: 0 16px 32px rgba(20,20,16,0.14);
    opacity:0;
    visibility:hidden;
    transition: opacity 0.18s ease, transform 0.18s ease, visibility 0.18s;
    z-index: 60;
  }
  .nav-item-dropdown:hover .dropdown-panel,
  .nav-item-dropdown:focus-within .dropdown-panel{
    opacity:1; visibility:visible; transform: translateX(-50%) translateY(0);
  }
  .dropdown-panel a{
    display:flex; justify-content:space-between; align-items:baseline;
    padding: 10px 12px; border-radius: 2px; font-size:0.88rem;
  }
  .dropdown-panel a:hover{ background: var(--panel); }
  .dropdown-panel a::after{ display:none; }
  .dropdown-panel .dp-price{ color: var(--accent); font-family:'Fraunces', serif; font-size:0.85rem; }

  .nav-contact{
    display:flex; align-items:center; gap:7px;
    font-size:0.86rem; color: var(--muted); text-decoration:none;
    white-space:nowrap;
  }
  .nav-contact svg{ width:15px; height:15px; }
  .nav-contact:hover{ color: var(--ink); }

  .nav-cta{
    background: var(--accent);
    color: var(--white);
    text-decoration:none;
    padding: 10px 20px;
    font-size: 0.9rem;
    font-weight:500;
    border-radius: var(--radius);
    white-space:nowrap;
  }
  .nav-cta:hover{ background: var(--accent-dark); }
  .mobile-cta-wrap{ display:none; }

  .menu-btn{
    display:none;
    background:none; border:none; cursor:pointer;
    flex-direction:column; gap:5px; padding:6px;
    position:relative; z-index:70;
  }
  .menu-btn span{ width:22px; height:2px; background:var(--ink); display:block; transition: transform 0.2s ease, opacity 0.2s ease; }
  header.open .menu-btn span:nth-child(1){ transform: translateY(7px) rotate(45deg); }
  header.open .menu-btn span:nth-child(2){ opacity:0; }
  header.open .menu-btn span:nth-child(3){ transform: translateY(-7px) rotate(-45deg); }

  .nav-backdrop{
    position:fixed; inset:0;
    background: rgba(20,20,16,0.4);
    opacity:0; visibility:hidden;
    transition: opacity 0.25s ease, visibility 0.25s;
    z-index: 55;
  }
  header.open .nav-backdrop{ opacity:1; visibility:visible; }

  .nav-slogan{
    font-family:'Fraunces', serif;
    font-style:italic;
    font-size: 0.82rem;
    color: var(--muted);
    padding-left: 16px;
    margin-left: -8px;
    border-left: 1px solid var(--stone);
    white-space:nowrap;
  }

  @media (max-width: 1000px){
    .nav-contact{ display:none; }
    .nav-slogan{ display:none; }
  }

  /* ---------- Hero ---------- */
  .hero-shell{
    background: var(--surface-dark);
    border-top: none;
    padding: 0;
  }
  .hero{
    padding: 110px 32px 90px;
    max-width: var(--maxw);
    margin: 0 auto;
    display:grid;
    grid-template-columns: 1.4fr 1fr;
    gap: 60px;
    align-items:end;
    opacity: 0;
    transform: translateY(14px);
    animation: hero-in 0.7s ease forwards;
  }
  @keyframes hero-in{ to{ opacity:1; transform:translateY(0);} }

  .hero h1{
    font-size: clamp(2.4rem, 4.8vw, 3.9rem);
    max-width: 14ch;
    color: var(--white);
  }
  .hero h1 em{ font-style: italic; color: var(--accent-soft); }
  .hero .lede{
    margin-top: 28px;
    font-size: 1.15rem;
    color: rgba(255,255,255,0.7);
    max-width: 42ch;
  }
  .hero-actions{
    margin-top: 36px;
    display:flex;
    gap: 18px;
    align-items:center;
    flex-wrap:wrap;
  }
  .btn-primary{
    background: var(--accent);
    color: var(--ink);
    text-decoration:none;
    padding: 14px 26px;
    font-size: 0.95rem;
    font-weight:500;
    border-radius: var(--radius);
    border: 1px solid var(--accent);
  }
  .btn-primary:hover{ background: transparent; color: var(--accent); }
  .btn-ghost{
    text-decoration:none;
    color: var(--white);
    font-size: 0.95rem;
    border-bottom: 1px solid rgba(255,255,255,0.5);
    padding-bottom: 2px;
  }

  .hero-stat{
    border-left: 1px solid rgba(255,255,255,0.25);
    padding-left: 24px;
  }
  .hero-stat .num{
    font-family:'Fraunces', serif;
    font-size: 3rem;
    color: var(--accent-soft);
    line-height:1;
  }
  .hero-stat .cap{
    margin-top: 10px;
    color: rgba(255,255,255,0.6);
    font-size: 0.92rem;
    max-width: 22ch;
  }

  .hero-banner{
    width: 100%;
    height: 320px;
    display: block;
  }

  /* ---------- Section shell ---------- */
  section{ padding: 88px 0; border-top: 1px solid var(--stone); }
  .section-head{
    display:flex;
    justify-content:space-between;
    align-items:flex-end;
    gap: 40px;
    margin-bottom: 52px;
    flex-wrap:wrap;
  }
  .section-head h2{ font-size: clamp(1.7rem, 3vw, 2.3rem); max-width: 16ch; }
  .section-head .note{ color: var(--muted); max-width: 34ch; font-size: 0.98rem; }
  .eyebrow{
    display:block;
    font-family:'Inter', sans-serif;
    font-size: 0.78rem;
    font-weight: 600;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 14px;
  }

  /* ---------- Om ---------- */
  .about-grid{
    display:grid;
    grid-template-columns: 0.9fr 1.3fr 1fr;
    gap: 48px;
    align-items:start;
  }
  .about-photo{
    width: 100%;
    aspect-ratio: 3/4;
    object-fit: cover;
  }
  .about-grid p{ color: var(--muted); font-size: 1.02rem; max-width: 48ch; }
  .about-grid p + p{ margin-top: 18px; }
  .about-marks{
    display:grid;
    grid-template-columns: 1fr 1fr;
    gap: 28px;
  }
  .mark{ border-top: 1px solid var(--stone); padding-top: 14px; }
  .mark .n{ font-family:'Fraunces', serif; font-size: 1.6rem; color: var(--accent); }
  .mark .l{ color: var(--muted); font-size: 0.9rem; margin-top: 4px; }

  /* ---------- Hur det funkar ---------- */
  .process{
    display:grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 0;
    border-top: 1px solid var(--stone);
  }
  .step{
    padding: 28px 24px;
    border-right: 1px solid var(--stone);
  }
  .step:last-child{ border-right:none; }
  .step .idx{
    font-family:'Fraunces', serif;
    color: var(--accent);
    font-size: 1.1rem;
  }
  .step h3{
    font-size: 1.05rem;
    font-weight:600;
    font-family:'Inter', sans-serif;
    margin-top: 14px;
  }
  .step p{ margin-top: 10px; color: var(--muted); font-size: 0.92rem; }

  /* ---------- Tjänster / priser ---------- */
  .plans{
    display:grid;
    grid-template-columns: repeat(3, 1fr);
    border: 1px solid var(--stone);
  }
  .plan{
    padding: 40px 32px;
    border-right: 1px solid var(--stone);
  }
  .plan:last-child{ border-right:none; }
  .plan.is-core{ background: var(--surface-dark); color: var(--white); position:relative; border-top: 2px solid var(--accent); }
  .plan.is-core .badge{
    position:absolute; top:-2px; right:24px;
    transform: translateY(-100%);
    background: var(--accent); color: var(--ink);
    font-size:0.72rem; font-weight:600; letter-spacing:0.06em; text-transform:uppercase;
    padding: 6px 12px;
    border-radius: var(--radius) var(--radius) 0 0;
  }
  .plan.is-core .price, .plan.is-core h3, .plan.is-core .desc{ color: var(--white); }
  .plan.is-core .feat{ color: rgba(255,255,255,0.72); }
  .plan.is-core .feat::before{ color: var(--accent-soft); }
  .plan h3{ font-size:1.15rem; font-family:'Inter'; font-weight:600; }
  .plan .desc{ color: var(--muted); font-size:0.9rem; margin-top:8px; }
  .plan .price{
    font-family:'Fraunces', serif;
    font-size: 2.2rem;
    margin-top: 24px;
  }
  .plan .price span{ font-size: 0.95rem; font-family:'Inter'; color: var(--muted); }
  .plan.is-core .price span{ color: rgba(255,255,255,0.6); }
  .featlist{ list-style:none; padding:0; margin: 26px 0 0; }
  .feat{
    padding: 10px 0;
    border-top: 1px solid var(--stone);
    font-size: 0.92rem;
    color: var(--muted);
    position:relative;
    padding-left: 18px;
  }
  .plan.is-core .feat{ border-top-color: rgba(255,255,255,0.18); }
  .feat::before{
    content:"—";
    position:absolute; left:0; color: var(--accent);
  }
  .plan-cta{
    display:inline-block;
    margin-top: 28px;
    font-size: 0.92rem;
    border-bottom: 1px solid var(--ink);
    text-decoration:none;
    padding-bottom: 2px;
  }
  .plan.is-core .plan-cta{ border-bottom-color: var(--white); }

  .addon{
    display:flex;
    align-items:flex-start;
    gap: 10px;
    margin-top: 26px;
    padding-top: 20px;
    border-top: 1px dashed var(--stone);
    cursor: pointer;
    font-size: 0.86rem;
  }
  .plan.is-core .addon{ border-top-color: rgba(255,255,255,0.18); }
  .addon input{ position:absolute; opacity:0; width:0; height:0; }
  .addon-box{
    flex-shrink:0;
    width: 18px; height: 18px;
    border: 1px solid var(--muted);
    border-radius: 2px;
    margin-top: 1px;
    position:relative;
  }
  .plan.is-core .addon-box{ border-color: rgba(255,255,255,0.5); }
  .addon input:checked + .addon-box{ background: var(--accent); border-color: var(--accent); }
  .addon input:checked + .addon-box::after{
    content:"";
    position:absolute; left:5px; top:1px;
    width:5px; height:9px;
    border: solid var(--white);
    border-width: 0 2px 2px 0;
    transform: rotate(45deg);
  }
  .addon-text{ color: var(--muted); flex:1; }
  .plan.is-core .addon-text{ color: rgba(255,255,255,0.72); }
  .addon-price{ color: var(--accent); font-weight:500; white-space:nowrap; }
  .addon-total{
    margin-top: 10px;
    font-size: 0.86rem;
    color: var(--accent);
    min-height: 1.2em;
    font-weight: 500;
  }

  /* ---------- Portfolio (mosaic) ---------- */
  .mosaic{
    display:grid;
    grid-template-columns: repeat(6, 1fr);
    gap: 20px;
  }
  .case{
    border-radius: var(--radius);
    padding: 26px;
    display:flex;
    flex-direction:column;
    justify-content:flex-end;
    min-height: 220px;
    color: var(--white);
    position:relative;
    overflow:hidden;
    background-size: cover;
    background-position: center;
    border: 1px solid var(--accent);
  }
  .case::before{
    content:"";
    position:absolute; inset:0;
    z-index: 1;
    background: linear-gradient(180deg, rgba(20,20,16,0.05) 30%, rgba(15,15,12,0.75) 100%);
  }
  .case > svg.case-art{
    position:absolute; inset:0;
    width:100%; height:100%;
    z-index: 0;
  }
  .case > *:not(svg.case-art){ position:relative; z-index:2; }
  .case.c1{ grid-column: span 4; min-height: 320px; background: var(--accent); }
  .case.c2{ grid-column: span 2; background: #4A5A44; }
  .case.c3{ grid-column: span 2; background: #7C7361; }
  .case.c4{ grid-column: span 4; background: var(--surface-dark); }
  .case.c1t{ grid-column: span 2; background: var(--stone); color: var(--ink); }
  .case.c1t h3, .case.c1t p{ color: var(--ink); }
  .case.c1t p{ color: #4A473E; }
  .case.c2t{ grid-column: span 2; min-height: 260px; background: var(--accent); }
  .case.c3t{ grid-column: span 2; min-height: 300px; background: var(--surface-dark); }
  .case .tag{ font-size: 0.8rem; opacity:0.75; margin-bottom: 8px; }
  .case h3{ font-family:'Fraunces', serif; font-size: 1.4rem; font-weight:500; color: var(--white); }
  .case p{ color: rgba(255,255,255,0.75); font-size: 0.88rem; margin-top:8px; }
  .placeholder-note{ margin-top: 24px; color: var(--muted); font-size: 0.88rem; }

  /* ---------- Omdömen ---------- */
  .quotes{
    display:grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 40px;
  }
  .quote{ border-top: 2px solid var(--accent); padding-top: 22px; }
  .quote::before{
    content: "\201C";
    display:block;
    font-family:'Fraunces', serif;
    font-size: 3.5rem;
    color: var(--accent);
    line-height: 0.6;
    margin-bottom: 8px;
  }
  .quote p.body{ font-family:'Fraunces', serif; font-size: 1.15rem; line-height:1.5; }
  .quote .who{ margin-top: 18px; color: var(--muted); font-size: 0.88rem; }

  /* ---------- Kontakt ---------- */
  .contact-grid{
    display:grid;
    grid-template-columns: 0.9fr 1.1fr;
    gap: 64px;
  }
  .contact-info p{ color: var(--muted); max-width: 38ch; }
  .contact-info .cline{ margin-top: 26px; }
  .contact-info .cline .l{ font-size: 0.82rem; color: var(--muted); }
  .contact-info .cline .v{ margin-top: 4px; font-size: 1.02rem; }

  form{ display:grid; gap: 20px; }
  .field{ display:grid; gap: 8px; }
  .field label{ font-size: 0.85rem; color: var(--muted); }
  .field input, .field textarea{
    border: none;
    border-bottom: 1px solid var(--stone);
    background: transparent;
    padding: 10px 2px;
    font-family:'Inter', sans-serif;
    font-size: 1rem;
    color: var(--ink);
  }
  .field textarea{ resize: vertical; min-height: 90px; }
  .field input:focus, .field textarea:focus{
    border-bottom-color: var(--accent);
  }
  .submit-btn{
    justify-self:start;
    margin-top: 6px;
    background: var(--accent);
    color: var(--white);
    border:none;
    padding: 14px 30px;
    font-size: 0.95rem;
    font-weight:500;
    border-radius: var(--radius);
    cursor:pointer;
  }
  .submit-btn:hover{ background: var(--accent-dark); }
  .form-msg{ font-size: 0.9rem; color: var(--accent); min-height: 1.2em; }

  /* ---------- Footer ---------- */
  footer{
    border-top: 1px solid var(--stone);
    padding: 64px 0 0;
    background: var(--bg);
  }
  .footer-grid{
    display:grid;
    grid-template-columns: 1.4fr 1fr 1fr 1fr;
    gap: 40px;
    padding-bottom: 48px;
    border-bottom: 1px solid var(--stone);
  }
  .footer-brand .logo{ margin-bottom: 14px; }
  .footer-brand .slogan{ font-family:'Fraunces', serif; font-style:italic; color: var(--accent); font-size:1rem; margin-bottom:12px; }
  .footer-brand p{ color: var(--muted); font-size:0.9rem; max-width: 32ch; }
  .footer-col h4{ font-family:'Inter'; font-size:0.85rem; font-weight:600; text-transform:uppercase; letter-spacing:0.06em; color: var(--muted); margin-bottom:16px; }
  .footer-col ul{ list-style:none; margin:0; padding:0; display:grid; gap:10px; }
  .footer-col a{ text-decoration:none; color: var(--ink); font-size:0.92rem; }
  .footer-col a:hover{ color: var(--accent); }
  .foot-row{
    display:flex;
    justify-content:space-between;
    align-items:center;
    flex-wrap:wrap;
    gap: 16px;
    font-size: 0.85rem;
    color: var(--muted);
    padding: 22px 0;
  }
  .foot-row a{ color: var(--muted); text-decoration:none; }
  .foot-row a:hover{ color: var(--accent); }
  .foot-legal{ display:flex; gap:20px; }
  @media (max-width: 800px){
    .footer-grid{ grid-template-columns: 1fr 1fr; }
  }
  @media (max-width: 500px){
    .footer-grid{ grid-template-columns: 1fr; }
  }

  /* ---------- Scroll reveal ---------- */
  .section-head, .about-grid, .process, .plans, .mosaic, .quotes, .contact-grid, .why-grid{
    opacity: 0;
    transform: translateY(18px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .is-visible{ opacity: 1 !important; transform: none !important; }

  /* ---------- Varför välja oss ---------- */
  .why-grid{
    display:grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 32px;
  }
  .why-item .icon{
    width: 40px; height: 40px;
    margin-bottom: 18px;
  }
  .why-item h3{ font-size: 1.05rem; font-family:'Inter'; font-weight:600; }
  .why-item p{ margin-top: 10px; color: var(--muted); font-size: 0.92rem; }

  /* ---------- Stars ---------- */
  .stars{ color: var(--accent); letter-spacing: 2px; font-size: 0.95rem; margin-bottom: 14px; }

  /* ---------- FAQ ---------- */
  .faq{ max-width: 760px; }
  .faq-item{ border-top: 1px solid var(--stone); }
  .faq-item:last-child{ border-bottom: 1px solid var(--stone); }
  .faq-item summary{
    padding: 22px 4px;
    cursor: pointer;
    font-family:'Fraunces', serif;
    font-size: 1.1rem;
    list-style: none;
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap: 20px;
  }
  .faq-item summary::-webkit-details-marker{ display:none; }
  .faq-item summary::after{
    content: "+";
    font-family:'Inter';
    font-size: 1.4rem;
    color: var(--accent);
    flex-shrink:0;
  }
  .faq-item[open] summary::after{ content: "−"; }
  .faq-item p{ padding: 0 4px 22px; color: var(--muted); max-width: 60ch; }

  /* ---------- Final CTA banner ---------- */
  .cta-banner{
    background: var(--surface-dark);
    color: var(--white);
    text-align:center;
    padding: 100px 32px;
    position:relative;
    overflow:hidden;
  }
  .cta-banner::before{
    content:"";
    position:absolute; top:0; left:50%;
    transform: translateX(-50%);
    width: 1px; height: 60px;
    background: var(--accent);
  }
  .cta-banner .eyebrow{ color: var(--accent-soft); }
  .cta-banner h2{ color: var(--white); font-size: clamp(2rem, 4vw, 3rem); max-width: 20ch; margin: 26px auto 0; }
  .cta-banner h2 em{ font-style:italic; color: var(--accent-soft); }
  .cta-banner p{ color: rgba(255,255,255,0.7); margin-top: 16px; max-width: 46ch; margin-left:auto; margin-right:auto; }
  .cta-banner .cta-actions{ display:flex; gap:24px; align-items:center; justify-content:center; flex-wrap:wrap; margin-top: 34px; }
  .cta-banner .btn-primary{ background: var(--accent); border-color: var(--accent); }
  .cta-banner .btn-primary:hover{ background: transparent; color: var(--white); }
  .cta-banner .btn-ghost{ color: var(--white); border-bottom-color: rgba(255,255,255,0.5); }
  .cta-banner .stars{ margin-top: 30px; justify-content:center; display:flex; gap:8px; align-items:center; }

  /* ---------- Floating CTA ---------- */
  .floating-cta{
    position: fixed;
    bottom: 24px; right: 24px;
    z-index: 40;
    background: var(--accent);
    color: var(--white);
    text-decoration:none;
    padding: 14px 24px;
    border-radius: 999px;
    font-size: 0.9rem;
    font-weight:500;
    box-shadow: 0 10px 24px rgba(20,20,16,0.22);
  }
  .floating-cta:hover{ background: var(--accent-dark); }

  @media (prefers-reduced-motion: reduce){
    html{ scroll-behavior:auto; }
    .hero{ animation:none; opacity:1; transform:none; }
    .section-head, .about-grid, .process, .plans, .mosaic, .quotes, .contact-grid, .why-grid{
      opacity:1; transform:none; transition:none;
    }
  }

  /* ---------- Responsive ---------- */
  @media (max-width: 900px){
    .hero{ grid-template-columns: 1fr; gap: 32px; }
    .hero-stat{ border-left:none; border-top: 1px solid var(--stone); padding-left:0; padding-top:18px; }
    .about-grid{ grid-template-columns: 1fr; }
    .process{ grid-template-columns: repeat(2, 1fr); }
    .step:nth-child(2){ border-right:none; }
    .step:nth-child(3){ border-top: 1px solid var(--stone); }
    .step:nth-child(4){ border-top: 1px solid var(--stone); border-right:none; }
    .plans{ grid-template-columns: 1fr; }
    .plan{ border-right:none; border-bottom: 1px solid var(--stone); }
    .plan:last-child{ border-bottom:none; }
    .quotes{ grid-template-columns: 1fr; gap: 28px; }
    .contact-grid{ grid-template-columns: 1fr; gap: 40px; }
    .case.c1, .case.c2, .case.c3, .case.c4, .case.c1t, .case.c2t, .case.c3t{ grid-column: span 6; }
    .why-grid{ grid-template-columns: 1fr 1fr; }
  }
  @media (max-width: 640px){
    .why-grid{ grid-template-columns: 1fr; }
    .floating-cta{ padding: 12px 18px; font-size: 0.85rem; bottom: 16px; right: 16px; }
    .wrap, .nav, .hero{ padding-left: 20px; padding-right: 20px; }
    .menu-btn{ display:flex; }
    .nav-cta{ display:none; }
    body:has(header.open) .floating-cta{ display:none; }
    .navlinks{
      display:flex; flex-direction:column; align-items:stretch; gap:0;
      position:fixed; left:0; right:0; bottom:0; top:auto;
      width: 100%; height: 50vh;
      background: var(--bg);
      border-radius: 18px 18px 0 0;
      padding: 26px 28px 28px;
      transform: translateY(100%);
      transition: transform 0.3s ease;
      box-shadow: 0 -16px 36px rgba(20,20,16,0.22);
      z-index: 60;
      overflow-y:auto;
    }
    header.open .navlinks{ transform: translateY(0); }
    .navlinks::before{
      content:"";
      position:absolute; top:10px; left:50%;
      transform: translateX(-50%);
      width: 40px; height: 4px;
      border-radius: 2px;
      background: var(--stone);
    }
    .navlinks > li{ width:100%; }
    .navlinks > li:first-child{ margin-top: 12px; }
    .navlinks a{ display:block; padding: 14px 0; border-bottom: 1px solid var(--stone); font-size: 1rem; }
    .has-dropdown{ padding: 14px 0; border-bottom: 1px solid var(--stone); justify-content:space-between; }
    .has-dropdown a{ padding:0; border:none; font-size: 1rem; }
    .dropdown-panel{
      position:static; opacity:1; visibility:visible; transform:none;
      box-shadow:none; border:none; padding:0; min-width:0;
      max-height:0; overflow:hidden;
      background: transparent;
    }
    .nav-item-dropdown.mobile-open .dropdown-panel{ max-height:220px; padding: 4px 0 10px; }
    .dropdown-panel a{ background:transparent; padding: 8px 0; }
    .dropdown-panel a:hover{ background:transparent; color: var(--accent); }
    .mobile-cta-wrap{ display:block; width:100%; margin-top:18px; }
    .mobile-cta-wrap .nav-cta{ display:block; text-align:center; }
    .hero{ padding-top: 60px; }
    section{ padding: 56px 0; }
  }
</style>
</head>
<body>

<header id="site-header">
  <div class="nav-backdrop" id="navBackdrop"></div>
  <div class="progress-bar" id="progressBar"></div>
  <nav class="nav">
    <div style="display:flex; align-items:center;">
      <a href="#" class="logo" aria-label="Formverk startsida">
        <svg class="logo-mark" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
          <polygon points="40,15 155,15 155,50 90,50 90,95 150,95 150,130 90,130 90,185 40,185" fill="var(--ink)"/>
          <rect x="90" y="95" width="60" height="35" fill="var(--accent)"/>
        </svg>
        FormVerk
      </a>
      <span class="nav-slogan">Din idé. Vår design.</span>
    </div>
    <ul class="navlinks" id="navLinks">
      <li><a href="#om" class="navlink">Om</a></li>
      <li><a href="#varfor" class="navlink">Varför oss</a></li>
      <li class="nav-item-dropdown" id="tjansterDropdown">
        <div class="has-dropdown">
          <a href="#tjanster" class="navlink">Tjänster</a>
          <svg class="caret" id="dropdownCaret" viewBox="0 0 10 6" xmlns="http://www.w3.org/2000/svg">
            <path d="M1 1l4 4 4-4" stroke="currentColor" stroke-width="1.4" fill="none"/>
          </svg>
        </div>
        <div class="dropdown-panel">
          <a href="#tjanster"><span>Bas</span><span class="dp-price">2 999 kr</span></a>
          <a href="#tjanster"><span>Standard</span><span class="dp-price">4 999 kr</span></a>
          <a href="#tjanster"><span>Premium</span><span class="dp-price">från 7 499 kr</span></a>
        </div>
      </li>
      <li><a href="#paketexempel" class="navlink">Portfolio</a></li>
      <li><a href="#omdomen" class="navlink">Omdömen</a></li>
      <li><a href="#faq" class="navlink">FAQ</a></li>
      <li><a href="#kontakt" class="navlink">Kontakt</a></li>
      <li class="mobile-cta-wrap"><a class="nav-cta" href="#kontakt">Boka samtal</a></li>
    </ul>
    <a class="nav-contact" href="mailto:hej@formverk.se">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" xmlns="http://www.w3.org/2000/svg"><path d="M3 6h18v12H3z"/><path d="M3 7l9 6 9-6"/></svg>
      hej@formverk.se
    </a>
    <a class="nav-cta" href="#kontakt">Boka samtal</a>
    <button class="menu-btn" id="menuBtn" aria-label="Öppna meny" aria-expanded="false">
      <span></span><span></span><span></span>
    </button>
  </nav>
</header>

<section class="hero-shell">
<section class="hero" style="border-top:none;">
  <div>
    <h1>Jag bygger hemsidor som <em>får</em> företag att synas.</h1>
    <p class="lede">Formverk designar och utvecklar hemsidor för små och medelstora företag — snabba, tydliga och byggda för att faktiskt ge dig fler kunder, inte bara se fina ut.</p>
    <div class="hero-actions">
      <a class="btn-primary" href="#kontakt">Boka ett kostnadsfritt samtal</a>
      <a class="btn-ghost" href="#tjanster">Se priser</a>
    </div>
    <div class="stars" style="margin-top:26px;">★★★★★ <span style="color:rgba(255,255,255,0.65); font-family:'Inter'; letter-spacing:normal;">Nöjd-kund-garanti på varje projekt</span></div>
  </div>
  <div class="hero-stat">
    <div class="num">2–4</div>
    <div class="cap">veckor från första samtal till lanserad hemsida</div>
  </div>
</section>
</section>

<svg class="hero-banner" viewBox="0 0 1600 640" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Illustration av en webbplats under uppbyggnad">
  <rect width="1600" height="640" fill="var(--panel)"/>
  <rect x="160" y="70" width="1280" height="500" rx="8" fill="var(--white)" stroke="var(--stone)" stroke-width="2"/>
  <rect x="160" y="70" width="1280" height="44" rx="8" fill="var(--ink)"/>
  <circle cx="192" cy="92" r="6" fill="var(--accent-soft)"/>
  <circle cx="214" cy="92" r="6" fill="var(--accent-soft)"/>
  <circle cx="236" cy="92" r="6" fill="var(--accent-soft)"/>
  <rect x="210" y="150" width="380" height="30" fill="var(--ink)"/>
  <rect x="210" y="196" width="280" height="14" fill="var(--stone)"/>
  <rect x="210" y="220" width="240" height="14" fill="var(--stone)"/>
  <rect x="210" y="264" width="150" height="40" fill="var(--accent)"/>
  <rect x="700" y="150" width="590" height="200" fill="var(--accent-soft)"/>
  <rect x="210" y="360" width="360" height="150" fill="var(--accent-soft)"/>
  <rect x="600" y="360" width="360" height="150" fill="var(--panel)" stroke="var(--stone)" stroke-width="1.5"/>
  <rect x="990" y="360" width="300" height="150" fill="var(--panel)" stroke="var(--stone)" stroke-width="1.5"/>
</svg>

<section id="kontakt">
  <div class="wrap">
    <div class="section-head">
      <div><span class="eyebrow">Kontakt</span><h2>Hör av dig</h2></div>
      <p class="note">Berätta kort om ert företag så återkommer jag inom en vardag.</p>
    </div>
    <div class="contact-grid">
      <div class="contact-info">
        <p>Oavsett om ni redan vet vad ni behöver eller bara vill bolla en idé — skriv ett par rader så tar vi det därifrån.</p>
        <div class="cline">
          <div class="l">E-post</div>
          <div class="v">hej@formverk.se</div>
        </div>
        <div class="cline">
          <div class="l">Telefon</div>
          <div class="v">070-000 00 00</div>
        </div>
        <div class="cline">
          <div class="l">Baserad i</div>
          <div class="v">Sverige — jobbar med kunder i hela landet</div>
        </div>
      </div>
      <form id="contactForm">
        <div class="field">
          <label for="name">Namn</label>
          <input type="text" id="name" name="name" required>
        </div>
        <div class="field">
          <label for="company">Företag</label>
          <input type="text" id="company" name="company">
        </div>
        <div class="field">
          <label for="email">E-post</label>
          <input type="email" id="email" name="email" required>
        </div>
        <div class="field">
          <label for="message">Meddelande</label>
          <textarea id="message" name="message" required></textarea>
        </div>
        <button class="submit-btn" type="submit">Skicka meddelande</button>
        <p class="form-msg" id="formMsg" role="status"></p>
      </form>
    </div>
  </div>
</section>

<section id="om">
  <div class="wrap">
    <div class="section-head">
      <div><span class="eyebrow">Om oss</span><h2>Om Formverk</h2></div>
    </div>
    <div class="about-grid">
      <svg class="about-photo" viewBox="0 0 500 650" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Formverks logotyp">
        <rect width="500" height="650" fill="var(--accent-soft)"/>
        <g transform="translate(140,205) scale(1.1)">
          <polygon points="40,15 155,15 155,50 90,50 90,95 150,95 150,130 90,130 90,185 40,185" fill="var(--ink)"/>
          <rect x="90" y="95" width="60" height="35" fill="var(--accent)"/>
        </g>
        <text x="250" y="470" text-anchor="middle" font-family="Fraunces, serif" font-size="34" font-weight="600" fill="var(--ink)">FormVerk</text>
      </svg>
      <div>
        <p>Jag heter Matin och driver Formverk. Jag jobbar med företag som vet att en hemsida är en av deras viktigaste säljkanaler — men som inte har tid eller lust att bygga den själva.</p>
        <p>Istället för färdiga mallar bygger jag varje sida från grunden, utifrån vad just ditt företag gör och vilka kunder ni vill nå. Resultatet är en sida som känns som er, laddar snabbt och är enkel att uppdatera själv.</p>
      </div>
      <div class="about-marks">
        <div class="mark"><div class="n">100%</div><div class="l">skräddarsytt, inga mallpaket</div></div>
        <div class="mark"><div class="n">1:1</div><div class="l">direktkontakt med mig genom hela projektet</div></div>
        <div class="mark"><div class="n">SEO</div><div class="l">grundinställt så att Google hittar er</div></div>
        <div class="mark"><div class="n">Support</div><div class="l">efter lansering, inte bara vid leverans</div></div>
      </div>
    </div>
  </div>
</section>

<section id="varfor">
  <div class="wrap">
    <div class="section-head">
      <div><span class="eyebrow">Varför oss</span><h2>Varför Formverk</h2></div>
      <p class="note">Det som skiljer ett skräddarsytt projekt från ett mallpaket.</p>
    </div>
    <div class="why-grid">
      <div class="why-item">
        <svg class="icon" viewBox="0 0 40 40"><circle cx="20" cy="20" r="18" fill="var(--accent-soft)"/><path d="M12 20l5 5 11-11" stroke="var(--accent)" stroke-width="2.5" fill="none" stroke-linecap="round" stroke-linejoin="round"/></svg>
        <h3>Fast pris</h3>
        <p>Du vet kostnaden innan vi börjar — inga överraskningar på fakturan.</p>
      </div>
      <div class="why-item">
        <svg class="icon" viewBox="0 0 40 40"><circle cx="20" cy="20" r="18" fill="var(--accent-soft)"/><path d="M20 10v10l7 4" stroke="var(--accent)" stroke-width="2.5" fill="none" stroke-linecap="round" stroke-linejoin="round"/></svg>
        <h3>Snabb leverans</h3>
        <p>2–4 veckor från första samtal till lanserad sida, inte månader.</p>
      </div>
      <div class="why-item">
        <svg class="icon" viewBox="0 0 40 40"><circle cx="20" cy="20" r="18" fill="var(--accent-soft)"/><circle cx="20" cy="16" r="5" fill="none" stroke="var(--accent)" stroke-width="2.5"/><path d="M10 30c1-6 6-9 10-9s9 3 10 9" stroke="var(--accent)" stroke-width="2.5" fill="none" stroke-linecap="round"/></svg>
        <h3>Personlig kontakt</h3>
        <p>Du pratar alltid med mig direkt — aldrig ett callcenter eller en projektpool.</p>
      </div>
      <div class="why-item">
        <svg class="icon" viewBox="0 0 40 40"><circle cx="20" cy="20" r="18" fill="var(--accent-soft)"/><path d="M20 9l3.5 7.2 7.9 1.1-5.7 5.6 1.3 7.9L20 26.9l-7 3.9 1.3-7.9-5.7-5.6 7.9-1.1z" fill="none" stroke="var(--accent)" stroke-width="2"/></svg>
        <h3>Nöjd-kund-garanti</h3>
        <p>Är du inte nöjd med designen innan vi bygger vidare, justerar vi den tillsammans.</p>
      </div>
    </div>
  </div>
</section>

<section id="hur-det-funkar" style="padding-bottom:0;">
  <div class="wrap">
    <div class="section-head">
      <div><span class="eyebrow">Processen</span><h2>Så går ett projekt till</h2></div>
      <p class="note">Fyra steg, ingen krånglig process.</p>
    </div>
  </div>
  <div class="process">
    <div class="step wrap" style="padding-left:32px;">
      <div class="idx">01</div>
      <h3>Vi pratar om ert företag</h3>
      <p>Ett kostnadsfritt samtal om vad ni gör, vilka kunder ni vill nå och vad sidan behöver klara av.</p>
    </div>
    <div class="step">
      <div class="idx">02</div>
      <h3>Jag skissar och designar</h3>
      <p>Ni får en design att ge feedback på innan något byggs.</p>
    </div>
    <div class="step">
      <div class="idx">03</div>
      <h3>Jag bygger sidan</h3>
      <p>Utveckling, texter och innehåll faller på plats — ni följer arbetet löpande.</p>
    </div>
    <div class="step" style="padding-right:32px;">
      <div class="idx">04</div>
      <h3>Lansering & support</h3>
      <p>Sidan går live, och jag finns kvar för justeringar efteråt.</p>
    </div>
  </div>
</section>

<section id="tjanster">
  <div class="wrap">
    <div class="section-head">
      <div><span class="eyebrow">Priser</span><h2>Tjänster & priser</h2></div>
      <p class="note">Fastpris, inga dolda kostnader. Alla paket går att skräddarsy vid behov.</p>
    </div>
    <div class="plans">
      <div class="plan">
        <h3>Bas</h3>
        <p class="desc">För dig som behöver en tydlig, snygg sida med det viktigaste.</p>
        <div class="price">2 999 kr</div>
        <ul class="featlist">
          <li class="feat">En sida, skräddarsydd design</li>
          <li class="feat">Mobilanpassad & snabbladdande</li>
          <li class="feat">Kontaktformulär</li>
          <li class="feat">Grundläggande SEO</li>
          <li class="feat">Koppling till Google Företagsprofil</li>
        </ul>
        <label class="addon">
          <input type="checkbox" class="addon-check" data-plan="bas" data-cost="759">
          <span class="addon-box"></span>
          <span class="addon-text">Låt Formverk sköta hemsidan åt er</span>
          <span class="addon-price">+759 kr/mån</span>
        </label>
        <p class="addon-total" id="total-bas"></p>
        <a class="plan-cta" href="#kontakt">Kom igång</a>
      </div>
      <div class="plan is-core">
        <div class="badge">Mest populär</div>
        <h3>Standard</h3>
        <p class="desc">Vårt vanligaste val för växande företag.</p>
        <div class="price">4 999 kr</div>
        <ul class="featlist">
          <li class="feat">Upp till 6 sidor</li>
          <li class="feat">Skräddarsydd design & varumärkesanpassning</li>
          <li class="feat">Boknings- eller offertformulär</li>
          <li class="feat">SEO-optimerad struktur</li>
          <li class="feat">Kopplad till Google Analytics</li>
          <li class="feat">30 dagars support efter lansering</li>
        </ul>
        <label class="addon">
          <input type="checkbox" class="addon-check" data-plan="standard" data-cost="759">
          <span class="addon-box"></span>
          <span class="addon-text">Låt Formverk sköta hemsidan åt er</span>
          <span class="addon-price">+759 kr/mån</span>
        </label>
        <p class="addon-total" id="total-standard"></p>
        <a class="plan-cta" href="#kontakt">Kom igång</a>
      </div>
      <div class="plan">
        <h3>Premium</h3>
        <p class="desc">För företag med större behov eller egen webbshop.</p>
        <div class="price">från 7 499 kr</div>
        <ul class="featlist">
          <li class="feat">Obegränsat antal sidor</li>
          <li class="feat">E-handel eller bokningssystem</li>
          <li class="feat">Flerspråkigt innehåll</li>
          <li class="feat">Skräddarsydda animationer & interaktioner</li>
          <li class="feat">Dedikerad kontaktperson</li>
          <li class="feat">Prioriterad support</li>
        </ul>
        <label class="addon">
          <input type="checkbox" class="addon-check" data-plan="premium" data-cost="759">
          <span class="addon-box"></span>
          <span class="addon-text">Låt Formverk sköta hemsidan åt er</span>
          <span class="addon-price">+759 kr/mån</span>
        </label>
        <p class="addon-total" id="total-premium"></p>
        <a class="plan-cta" href="#kontakt">Kom igång</a>
      </div>
    </div>
  </div>
</section>

<section id="paketexempel">
  <div class="wrap">
    <div class="section-head">
      <div><span class="eyebrow">Portfolio</span><h2>Ett exempel per paket</h2></div>
      <p class="note">Så kan resultatet se ut på respektive nivå — byt ut mot era egna case när ni har dem.</p>
    </div>
    <div class="mosaic">
      <a class="case c1t" href="exempel-bas-kvarterskrogen.html" target="_blank" style="text-decoration:none;">
        <svg class="case-art" viewBox="0 0 600 450" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
          <rect width="600" height="450" fill="#DCD3BE"/>
          <circle cx="300" cy="220" r="150" fill="#EFE8D8"/>
          <circle cx="300" cy="220" r="105" fill="none" stroke="#B5482F" stroke-width="4"/>
          <rect x="150" y="330" width="8" height="90" fill="#8A6F4E"/>
          <rect x="440" y="330" width="8" height="90" fill="#8A6F4E"/>
        </svg>
        <div class="tag">Bas — 2 999 kr</div>
        <h3>Kvarterskrogen</h3>
        <p>En sida med meny, öppettider och kontaktuppgifter. Enkelt, snabbt och tydligt.</p>
      </a>
      <a class="case c2t" href="exempel-standard-bjorkangsbygg.html" target="_blank" style="text-decoration:none;">
        <svg class="case-art" viewBox="0 0 600 450" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
          <rect width="600" height="450" fill="#3E5C3A"/>
          <rect x="80" y="240" width="120" height="180" fill="#4A6D45"/>
          <rect x="230" y="180" width="140" height="240" fill="#568060"/>
          <rect x="400" y="120" width="140" height="300" fill="#4A6D45"/>
          <line x1="60" y1="420" x2="560" y2="420" stroke="#2A3E27" stroke-width="6"/>
        </svg>
        <div class="tag">Standard — 4 999 kr</div>
        <h3>Björkängs Bygg</h3>
        <p>Sex sidor med projektgalleri och offertformulär, byggt för att generera fler förfrågningar.</p>
      </a>
      <a class="case c3t" href="exempel-premium-studiolera.html" target="_blank" style="text-decoration:none;">
        <svg class="case-art" viewBox="0 0 600 450" preserveAspectRatio="xMidYMid slice" xmlns="http://www.w3.org/2000/svg">
          <rect width="600" height="450" fill="#20241F"/>
          <path d="M260 130 C230 130 220 170 225 210 C210 250 210 340 260 360 L340 360 C390 340 390 250 375 210 C380 170 370 130 340 130 Z" fill="#9C5A3C"/>
          <ellipse cx="300" cy="130" rx="40" ry="12" fill="#7C4530"/>
        </svg>
        <div class="tag">Premium — från 7 499 kr</div>
        <h3>Studio Lera</h3>
        <p>Fullständig webbshop med produkthantering och flerspråkigt innehåll.</p>
      </a>
    </div>
    <p class="placeholder-note">Detta är platshållartexter/exempel — vi byter till era faktiska kundprojekt efter hand.</p>
  </div>
</section>

<section id="omdomen">
  <div class="wrap">
    <div class="section-head">
      <div><span class="eyebrow">Omdömen</span><h2>Vad kunder säger</h2></div>
    </div>
    <div class="quotes">
      <div class="quote">
        <div class="stars">★★★★★</div>
        <p class="body">"Fick en sida som faktiskt känns som vårt företag, inte en mall. Och den var klar snabbare än jag trodde."</p>
        <div class="who">Anna Lindqvist, Björkängs Bygg</div>
      </div>
      <div class="quote">
        <div class="stars">★★★★★</div>
        <p class="body">"Bra kommunikation genom hela processen. Slapp krångla med tekniken själv."</p>
        <div class="who">Erik Sandström, Kvarterskrogen</div>
      </div>
      <div class="quote">
        <div class="stars">★★★★★</div>
        <p class="body">"Vi har fått fler förfrågningar via sidan än via vår gamla annonsering."</p>
        <div class="who">Maria Öhman, Nordisk Rådgivning</div>
      </div>
    </div>
    <p class="placeholder-note">Platshållarcitat — byt ut mot riktiga omdömen från era kunder.</p>
  </div>
</section>

<section id="faq">
  <div class="wrap">
    <div class="section-head">
      <div><span class="eyebrow">Vanliga frågor</span><h2>Vanliga frågor</h2></div>
    </div>
    <div class="faq">
      <details class="faq-item">
        <summary>Hur lång tid tar ett projekt?</summary>
        <p>De flesta projekt tar 2–4 veckor från första samtal till lansering, beroende på paket och hur snabbt vi får material och feedback från er.</p>
      </details>
      <details class="faq-item">
        <summary>Äger jag hemsidan efteråt?</summary>
        <p>Ja. När sidan är betald och lanserad är den helt er — kod, design och innehåll. Ni är inte låsta till mig för framtida ändringar.</p>
      </details>
      <details class="faq-item">
        <summary>Vad händer om jag inte gillar designen?</summary>
        <p>Ni får se och godkänna designen innan något byggs. Passar den inte justerar vi den tillsammans innan vi går vidare — det ingår i garantin.</p>
      </details>
      <details class="faq-item">
        <summary>Kan jag uppdatera sidan själv efteråt?</summary>
        <p>Ja, ni får en enkel guide för mindre textändringar. Behöver ni större ändringar löpande kan vi också sätta upp ett redigeringsverktyg mot en tilläggskostnad.</p>
      </details>
      <details class="faq-item">
        <summary>Hur betalar jag?</summary>
        <p>Hela summan betalas vid lansering. Ni betalar via Swish, fakturabetalning eller banköverföring — det som passar er bäst.</p>
      </details>
    </div>
  </div>
</section>

<section class="cta-banner" style="border-top:none;">
  <span class="eyebrow">Ta nästa steg</span>
  <h2>Redo att få en hemsida som <em>faktiskt</em> jobbar för er?</h2>
  <p>Boka ett kostnadsfritt samtal — inga förpliktelser, bara ett ärligt förslag på vad ni behöver.</p>
  <div class="cta-actions">
    <a class="btn-primary" href="#kontakt">Boka ett kostnadsfritt samtal</a>
    <a class="btn-ghost" href="mailto:hej@formverk.se">Eller maila oss direkt</a>
  </div>
  <div class="stars">★★★★★ <span style="color:rgba(255,255,255,0.6); font-family:'Inter'; letter-spacing:normal; font-size:0.9rem;">Nöjd-kund-garanti på varje projekt</span></div>
</section>

<footer>
  <div class="wrap">
    <div class="footer-grid">
      <div class="footer-brand">
        <a href="#" class="logo" style="pointer-events:none;">
          <svg class="logo-mark" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
            <polygon points="40,15 155,15 155,50 90,50 90,95 150,95 150,130 90,130 90,185 40,185" fill="var(--ink)"/>
            <rect x="90" y="95" width="60" height="35" fill="var(--accent)"/>
          </svg>
          FormVerk
        </a>
        <p class="slogan">Din idé. Vår design.</p>
        <p>Skräddarsydda hemsidor för företag som vill synas — designade och byggda med fokus på resultat, inte bara utseende.</p>
      </div>
      <div class="footer-col">
        <h4>Sidan</h4>
        <ul>
          <li><a href="#om">Om</a></li>
          <li><a href="#varfor">Varför oss</a></li>
          <li><a href="#paketexempel">Portfolio</a></li>
          <li><a href="#omdomen">Omdömen</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Tjänster</h4>
        <ul>
          <li><a href="#tjanster">Bas — 2 999 kr</a></li>
          <li><a href="#tjanster">Standard — 4 999 kr</a></li>
          <li><a href="#tjanster">Premium — från 7 499 kr</a></li>
          <li><a href="#faq">Vanliga frågor</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Kontakt</h4>
        <ul>
          <li><a href="mailto:hej@formverk.se">hej@formverk.se</a></li>
          <li><a href="tel:0700000000">070-000 00 00</a></li>
          <li><a href="#kontakt">Boka ett samtal</a></li>
        </ul>
      </div>
    </div>
    <div class="foot-row">
      <div>Formverk © 2026. Alla rättigheter förbehållna.</div>
      <div class="foot-legal">
        <a href="#">Integritetspolicy</a>
        <a href="#">Allmänna villkor</a>
      </div>
    </div>
  </div>
</footer>

<a class="floating-cta" href="#kontakt">Boka samtal</a>

<script>
  const menuBtn = document.getElementById('menuBtn');
  const header = document.getElementById('site-header');
  const navBackdrop = document.getElementById('navBackdrop');

  function toggleMenu(force) {
    const isOpen = typeof force === 'boolean' ? force : !header.classList.contains('open');
    header.classList.toggle('open', isOpen);
    menuBtn.setAttribute('aria-expanded', isOpen);
    document.body.style.overflow = isOpen ? 'hidden' : '';
  }
  menuBtn.addEventListener('click', () => toggleMenu());
  navBackdrop.addEventListener('click', () => toggleMenu(false));
  document.querySelectorAll('.navlinks a.navlink, .mobile-cta-wrap a').forEach(link => {
    link.addEventListener('click', () => toggleMenu(false));
  });

  // Dropdown under "Tjänster" — expanderar inline på mobil istället för hover
  const dropdownCaret = document.getElementById('dropdownCaret');
  const tjansterDropdown = document.getElementById('tjansterDropdown');
  dropdownCaret.addEventListener('click', (e) => {
    if (window.innerWidth <= 640) {
      e.preventDefault();
      tjansterDropdown.classList.toggle('mobile-open');
    }
  });

  // Scroll-progressbar högst upp
  const progressBar = document.getElementById('progressBar');
  function updateProgress() {
    const scrollTop = window.scrollY;
    const docHeight = document.documentElement.scrollHeight - window.innerHeight;
    const pct = docHeight > 0 ? (scrollTop / docHeight) * 100 : 0;
    progressBar.style.width = pct + '%';
  }
  window.addEventListener('scroll', updateProgress, { passive: true });
  updateProgress();

  // Markera aktiv sektion i menyn medan man skrollar
  const navLinkEls = document.querySelectorAll('.navlink');
  const linkMap = {};
  navLinkEls.forEach(link => {
    const id = link.getAttribute('href').slice(1);
    (linkMap[id] = linkMap[id] || []).push(link);
  });
  const sectionObserver = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        navLinkEls.forEach(l => l.classList.remove('active'));
        (linkMap[entry.target.id] || []).forEach(l => l.classList.add('active'));
      }
    });
  }, { rootMargin: '-40% 0px -55% 0px' });
  document.querySelectorAll('section[id]').forEach(s => sectionObserver.observe(s));

  // Tilläggstjänst: "vi sköter hemsidan åt er" (+759 kr/mån)
  const basePrices = { bas: 2999, standard: 4999, premium: 7499 };
  document.querySelectorAll('.addon-check').forEach(cb => {
    cb.addEventListener('change', () => {
      const plan = cb.dataset.plan;
      const cost = cb.dataset.cost;
      const totalEl = document.getElementById('total-' + plan);
      if (!totalEl) return;
      if (cb.checked) {
        const base = basePrices[plan].toLocaleString('sv-SE');
        const prefix = plan === 'premium' ? 'Totalt: från ' : 'Totalt: ';
        totalEl.textContent = `${prefix}${base} kr + ${cost} kr/mån`;
      } else {
        totalEl.textContent = '';
      }
    });
  });

  // Fade-in-on-scroll för sektionsblock
  const revealTargets = document.querySelectorAll('.section-head, .about-grid, .process, .plans, .mosaic, .quotes, .contact-grid, .why-grid');
  const io = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('is-visible');
        io.unobserve(entry.target);
      }
    });
  }, { threshold: 0.15 });
  revealTargets.forEach(el => io.observe(el));

  // Formuläret sparar inte till någon server ännu — kopplas till t.ex.
  // Formspree, EmailJS eller ett eget backend-API när sidan ska driftsättas.
  const form = document.getElementById('contactForm');
  const msg = document.getElementById('formMsg');
  form.addEventListener('submit', (e) => {
    e.preventDefault();
    msg.textContent = 'Tack! Meddelandet är redo att skickas — koppla in en e-posttjänst för att ta emot det på riktigt.';
    form.reset();
  });
</script>

</body>
</html>
