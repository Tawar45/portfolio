<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Developer Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --bg: #0a0a0f;
    --bg2: #111118;
    --bg3: #1a1a24;
    --accent1: #7c6bff;
    --accent2: #00e5c0;
    --accent3: #ff6b6b;
    --text: #f0eff8;
    --muted: #888899;
    --border: rgba(255,255,255,0.07);
  }
  html { scroll-behavior: smooth; }
  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 1.2rem 4rem;
    background: rgba(10,10,15,0.85);
    backdrop-filter: blur(16px);
    border-bottom: 1px solid var(--border);
  }
  .logo { font-family: 'Syne', sans-serif; font-weight: 800; font-size: 1.4rem; letter-spacing: -0.5px; }
  .logo span { color: var(--accent1); }
  nav ul { list-style: none; display: flex; gap: 2.5rem; }
  nav ul li a { color: var(--muted); text-decoration: none; font-size: 0.875rem; font-weight: 500; letter-spacing: 0.3px; transition: color 0.2s; }
  nav ul li a:hover { color: var(--text); }
  .nav-cta {
    background: var(--accent1); color: #fff; padding: 0.5rem 1.25rem;
    border-radius: 50px; font-size: 0.85rem; font-weight: 500; text-decoration: none;
    transition: opacity 0.2s;
  }
  .nav-cta:hover { opacity: 0.85; }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex; flex-direction: column; justify-content: center; align-items: flex-start;
    padding: 8rem 4rem 4rem;
    position: relative; overflow: hidden;
  }
  .hero-bg {
    position: absolute; top: -120px; right: -80px;
    width: 700px; height: 700px; border-radius: 50%;
    background: radial-gradient(circle, rgba(124,107,255,0.15) 0%, transparent 70%);
    pointer-events: none;
  }
  .hero-bg2 {
    position: absolute; bottom: -100px; left: 20%;
    width: 500px; height: 500px; border-radius: 50%;
    background: radial-gradient(circle, rgba(0,229,192,0.08) 0%, transparent 70%);
    pointer-events: none;
  }
  .badge {
    display: inline-flex; align-items: center; gap: 6px;
    background: rgba(124,107,255,0.12); border: 1px solid rgba(124,107,255,0.3);
    color: var(--accent1); font-size: 0.78rem; font-weight: 500; letter-spacing: 0.5px;
    padding: 0.35rem 0.9rem; border-radius: 50px; margin-bottom: 1.5rem;
    text-transform: uppercase;
  }
  .badge-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--accent2); animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.4} }
  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.8rem, 6vw, 5rem);
    font-weight: 800; line-height: 1.05; letter-spacing: -2px;
    margin-bottom: 1.2rem; max-width: 750px;
  }
  h1 .grad {
    background: linear-gradient(135deg, var(--accent1), var(--accent2));
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .hero-sub {
    color: var(--muted); font-size: 1.1rem; line-height: 1.7;
    max-width: 560px; margin-bottom: 2.5rem; font-weight: 300;
  }
  .hero-actions { display: flex; gap: 1rem; flex-wrap: wrap; }
  .btn-primary {
    background: var(--accent1); color: #fff;
    padding: 0.85rem 2rem; border-radius: 50px; font-weight: 500; font-size: 0.95rem;
    text-decoration: none; border: none; cursor: pointer; transition: transform 0.2s, box-shadow 0.2s;
    box-shadow: 0 4px 20px rgba(124,107,255,0.35);
  }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 28px rgba(124,107,255,0.45); }
  .btn-outline {
    background: transparent; color: var(--text);
    padding: 0.85rem 2rem; border-radius: 50px; font-weight: 500; font-size: 0.95rem;
    text-decoration: none; border: 1px solid var(--border);
    cursor: pointer; transition: border-color 0.2s, background 0.2s;
  }
  .btn-outline:hover { border-color: rgba(255,255,255,0.2); background: rgba(255,255,255,0.04); }
  .hero-stats {
    display: flex; gap: 3rem; margin-top: 4rem;
    border-top: 1px solid var(--border); padding-top: 2.5rem;
  }
  .stat-num {
    font-family: 'Syne', sans-serif; font-size: 2rem; font-weight: 800; color: var(--text);
    display: block;
  }
  .stat-label { color: var(--muted); font-size: 0.82rem; margin-top: 2px; }

  /* SECTION */
  section { padding: 6rem 4rem; }
  .section-tag {
    font-size: 0.75rem; text-transform: uppercase; letter-spacing: 2px;
    color: var(--accent1); font-weight: 600; margin-bottom: 0.75rem;
  }
  .section-title {
    font-family: 'Syne', sans-serif; font-size: clamp(1.8rem, 3vw, 2.6rem);
    font-weight: 800; letter-spacing: -1px; margin-bottom: 3.5rem;
  }

  /* TECH STACK */
  .tech-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
    gap: 1rem;
  }
  .tech-card {
    background: var(--bg2); border: 1px solid var(--border);
    border-radius: 16px; padding: 1.5rem 1.25rem;
    text-align: center; cursor: default;
    transition: transform 0.25s, border-color 0.25s, background 0.25s;
    position: relative; overflow: hidden;
  }
  .tech-card:hover {
    transform: translateY(-4px);
    border-color: rgba(255,255,255,0.15);
    background: var(--bg3);
  }
  .tech-card::before {
    content: ''; position: absolute; inset: 0;
    background: radial-gradient(circle at 50% 0%, var(--card-glow, rgba(124,107,255,0.1)) 0%, transparent 60%);
    opacity: 0; transition: opacity 0.3s;
  }
  .tech-card:hover::before { opacity: 1; }
  .tech-icon { font-size: 2rem; margin-bottom: 0.6rem; display: block; }
  .tech-name { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 0.95rem; margin-bottom: 0.25rem; }
  .tech-type { font-size: 0.72rem; color: var(--muted); }

  /* PROJECTS */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
    gap: 1.5rem;
  }
  .project-card {
    background: var(--bg2); border: 1px solid var(--border);
    border-radius: 20px; overflow: hidden;
    transition: transform 0.25s, border-color 0.25s;
  }
  .project-card:hover { transform: translateY(-5px); border-color: rgba(255,255,255,0.15); }
  .project-thumb {
    height: 200px; display: flex; align-items: center; justify-content: center;
    font-size: 3.5rem; position: relative; overflow: hidden;
  }
  .project-body { padding: 1.5rem; }
  .project-tags { display: flex; gap: 0.5rem; flex-wrap: wrap; margin-bottom: 0.75rem; }
  .project-tag {
    font-size: 0.7rem; font-weight: 600; letter-spacing: 0.5px; text-transform: uppercase;
    padding: 0.2rem 0.65rem; border-radius: 50px;
  }
  .project-title { font-family: 'Syne', sans-serif; font-size: 1.15rem; font-weight: 700; margin-bottom: 0.5rem; }
  .project-desc { color: var(--muted); font-size: 0.875rem; line-height: 1.6; margin-bottom: 1.25rem; }
  .project-links { display: flex; gap: 0.75rem; }
  .project-link {
    font-size: 0.8rem; font-weight: 500; text-decoration: none;
    padding: 0.4rem 1rem; border-radius: 50px; border: 1px solid var(--border);
    color: var(--muted); transition: color 0.2s, border-color 0.2s;
  }
  .project-link:hover { color: var(--text); border-color: rgba(255,255,255,0.2); }
  .project-link.primary { background: rgba(124,107,255,0.15); border-color: rgba(124,107,255,0.35); color: var(--accent1); }

  /* ABOUT */
  .about-wrap {
    display: grid; grid-template-columns: 1fr 1.4fr; gap: 5rem; align-items: center;
  }
  .about-visual {
    aspect-ratio: 1; border-radius: 24px;
    background: var(--bg3); border: 1px solid var(--border);
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    position: relative; overflow: hidden;
  }
  .avatar-circle {
    width: 100px; height: 100px; border-radius: 50%;
    background: linear-gradient(135deg, var(--accent1), var(--accent2));
    display: flex; align-items: center; justify-content: center;
    font-family: 'Syne', sans-serif; font-size: 2.2rem; font-weight: 800;
    color: #fff; margin-bottom: 1rem;
    box-shadow: 0 0 40px rgba(124,107,255,0.4);
  }
  .avatar-name { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 1.1rem; }
  .avatar-role { color: var(--muted); font-size: 0.85rem; margin-top: 0.25rem; }
  .avatar-badges {
    display: flex; gap: 0.5rem; margin-top: 1.5rem; flex-wrap: wrap; justify-content: center;
    padding: 0 1.5rem;
  }
  .skill-pill {
    font-size: 0.72rem; font-weight: 600; padding: 0.3rem 0.7rem; border-radius: 50px;
    background: rgba(124,107,255,0.12); border: 1px solid rgba(124,107,255,0.25); color: var(--accent1);
  }
  .about-text p {
    color: var(--muted); font-size: 1rem; line-height: 1.75; margin-bottom: 1.5rem; font-weight: 300;
  }
  .about-text p strong { color: var(--text); font-weight: 500; }

  /* CONTACT */
  .contact-wrap {
    display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: start;
  }
  .contact-info h3 { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 1.1rem; margin-bottom: 1rem; }
  .contact-item {
    display: flex; align-items: center; gap: 0.75rem;
    margin-bottom: 1.25rem; color: var(--muted); font-size: 0.9rem;
  }
  .contact-icon {
    width: 38px; height: 38px; border-radius: 10px;
    background: rgba(255,255,255,0.04); border: 1px solid var(--border);
    display: flex; align-items: center; justify-content: center; font-size: 1rem; flex-shrink: 0;
  }
  .form-group { margin-bottom: 1.25rem; }
  .form-group label { display: block; font-size: 0.8rem; color: var(--muted); margin-bottom: 0.4rem; font-weight: 500; }
  .form-control {
    width: 100%; background: var(--bg2); border: 1px solid var(--border);
    border-radius: 10px; padding: 0.75rem 1rem; color: var(--text);
    font-family: 'DM Sans', sans-serif; font-size: 0.9rem;
    outline: none; transition: border-color 0.2s;
  }
  .form-control:focus { border-color: rgba(124,107,255,0.5); }
  textarea.form-control { resize: vertical; min-height: 120px; }

  /* FOOTER */
  footer {
    border-top: 1px solid var(--border);
    padding: 2rem 4rem;
    display: flex; justify-content: space-between; align-items: center;
    color: var(--muted); font-size: 0.82rem;
  }
  .footer-links { display: flex; gap: 1.5rem; }
  .footer-links a { color: var(--muted); text-decoration: none; transition: color 0.2s; }
  .footer-links a:hover { color: var(--text); }

  @media (max-width: 768px) {
    nav { padding: 1rem 1.5rem; }
    nav ul { display: none; }
    .hero, section { padding: 5rem 1.5rem 3rem; }
    .about-wrap, .contact-wrap { grid-template-columns: 1fr; gap: 2.5rem; }
    .hero-stats { gap: 1.5rem; flex-wrap: wrap; }
    footer { flex-direction: column; gap: 1rem; padding: 1.5rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo">dev<span>.</span>folio</div>
  <ul>
    <li><a href="#stack">Stack</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#about">About</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg"></div>
  <div class="hero-bg2"></div>
  <div class="badge"><span class="badge-dot"></span> Available for freelance & full-time</div>
  <h1>Expert <span class="grad">Shopify Developer</span> & E-Commerce Specialist</h1>
  <p class="hero-sub">
    I build high-converting, visually stunning Shopify stores — custom themes, Liquid templating, app integrations, and performance-tuned storefronts that sell.
  </p>
  <div class="hero-actions">
    <a href="#projects" class="btn-primary">View My Work</a>
    <a href="#contact" class="btn-outline">Get In Touch</a>
  </div>
  <div class="hero-stats">
    <div>
      <span class="stat-num">5+</span>
      <span class="stat-label">Years Experience</span>
    </div>
    <div>
      <span class="stat-num">25+</span>
      <span class="stat-label">Shopify Stores</span>
    </div>
    <div>
      <span class="stat-num">30+</span>
      <span class="stat-label">Happy Clients</span>
    </div>
    <div>
      <span class="stat-num">100%</span>
      <span class="stat-label">Client Satisfaction</span>
    </div>
  </div>
</section>

<!-- TECH STACK -->
<section id="stack">
  <p class="section-tag">Technologies</p>
  <h2 class="section-title">My Shopify Tech Stack</h2>
  <div class="tech-grid">
    <div class="tech-card" style="--card-glow: rgba(150,191,83,0.15);">
      <span class="tech-icon">🛍️</span>
      <div class="tech-name">Shopify</div>
      <div class="tech-type">Platform</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(0,229,192,0.12);">
      <span class="tech-icon">💧</span>
      <div class="tech-name">Liquid</div>
      <div class="tech-type">Templating</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(124,107,255,0.12);">
      <span class="tech-icon">🎨</span>
      <div class="tech-name">Dawn / Custom</div>
      <div class="tech-type">Theme Dev</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(97,218,251,0.12);">
      <span class="tech-icon">⚛️</span>
      <div class="tech-name">Hydrogen</div>
      <div class="tech-type">Headless React</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(255,153,0,0.1);">
      <span class="tech-icon">🔌</span>
      <div class="tech-name">Shopify APIs</div>
      <div class="tech-type">Admin & Storefront</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(255,107,107,0.1);">
      <span class="tech-icon">💳</span>
      <div class="tech-name">Checkout Ext.</div>
      <div class="tech-type">Custom Checkout</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(33,117,186,0.12);">
      <span class="tech-icon">📦</span>
      <div class="tech-name">Metafields</div>
      <div class="tech-type">Custom Data</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(120,82,161,0.12);">
      <span class="tech-icon">🚀</span>
      <div class="tech-name">Performance</div>
      <div class="tech-type">CRO & Speed</div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <p class="section-tag">Portfolio</p>
  <h2 class="section-title">Featured Shopify Projects</h2>
  <div class="projects-grid">

    <!-- Thrive Meals -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1a3c2e, #2f9c6e);">🥗</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Food & Meal Kits</span>
        </div>
        <div class="project-title">Thrive Meals</div>
        <div class="project-desc">Custom Shopify store for a meal delivery brand in Australia — subscription plans, dynamic menu sections, and a seamless mobile-first checkout experience.</div>
        <div class="project-links">
          <a href="https://thrivemeals.com.au/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Residence Supply -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #2a1f0a, #8a6520);">🕯️</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Home Décor</span>
        </div>
        <div class="project-title">Residence Supply</div>
        <div class="project-desc">Luxury home fragrance and décor store — custom theme with immersive product pages, editorial storytelling sections, and refined typography to match the brand aesthetic.</div>
        <div class="project-links">
          <a href="https://residencesupply.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Reitmans -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1e0a2a, #7b2d8b);">👗</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Fashion Retail</span>
        </div>
        <div class="project-title">Reitmans</div>
        <div class="project-desc">Large-scale Canadian fashion retailer on Shopify — size-inclusive filtering, loyalty integration, multi-collection navigation, and performance-optimized product listing pages.</div>
        <div class="project-links">
          <a href="https://www.reitmans.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Penningtons -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #3a0a1a, #c0245c);">✨</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Plus Size Fashion</span>
        </div>
        <div class="project-title">Penningtons</div>
        <div class="project-desc">Plus-size women's fashion brand — advanced size filtering, curated lookbook sections, fit guide integration, and a streamlined checkout optimized for conversion.</div>
        <div class="project-links">
          <a href="https://www.penningtons.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- RW&Co -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #0a1a2e, #1565c0);">👔</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Contemporary Fashion</span>
        </div>
        <div class="project-title">RW&Co</div>
        <div class="project-desc">Contemporary Canadian fashion retailer — editorial homepage layouts, gender-split navigation, outfit builder features, and seamless collection browsing with advanced filters.</div>
        <div class="project-links">
          <a href="https://www.rw-co.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Bhumi Agro -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1a2e0a, #4a8c1c);">🌾</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Agro / B2B</span>
        </div>
        <div class="project-title">Bhumi Agro Industries</div>
        <div class="project-desc">Agricultural products store built on Shopify — bulk ordering functionality, B2B pricing tiers, custom product specification layouts, and inquiry form integration.</div>
        <div class="project-links">
          <a href="https://bhumiagroindustries.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- RightShift -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #0a1429, #1e3a7c);">💻</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Tech / Services</span>
        </div>
        <div class="project-title">RightShift</div>
        <div class="project-desc">Tech services brand store — clean, professional Shopify setup with service-based product pages, custom sections for showcasing expertise, and lead-capture integrations.</div>
        <div class="project-links">
          <a href="https://rightshift.in/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Atvel -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1a1a0a, #8a7c1c);">🧳</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Travel / Lifestyle</span>
        </div>
        <div class="project-title">Atvel</div>
        <div class="project-desc">Travel accessories Shopify store — custom lifestyle imagery sections, product bundling, geo-targeted banners, and an optimized mobile shopping experience for on-the-go buyers.</div>
        <div class="project-links">
          <a href="https://atvel.in/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- NYX Cosmetics -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1a0a14, #8b1a5c);">💄</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Beauty / Cosmetics</span>
        </div>
        <div class="project-title">NYX Cosmetics</div>
        <div class="project-desc">High-traffic beauty brand store — shade-matching product options, UGC integration, loyalty program hooks, shade finder quiz, and dynamic promotional banner system.</div>
        <div class="project-links">
          <a href="https://www.nyxcosmetics.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- With Clarity -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #0a1a2e, #1a5c8c);">💎</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Jewelry / Luxury</span>
        </div>
        <div class="project-title">With Clarity</div>
        <div class="project-desc">Premium lab diamond jewelry store — custom ring builder tool, 360° product views, metal & stone filter combinations, and a luxury-grade checkout experience optimized for high AOV.</div>
        <div class="project-links">
          <a href="https://www.withclarity.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Mendock -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #0a1e1a, #1a7c6a);">🔧</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Tools / Hardware</span>
        </div>
        <div class="project-title">Mendock</div>
        <div class="project-desc">Industrial tools and hardware Shopify store — technical specification tables, category-heavy navigation, bulk add-to-cart, and trade account application flow.</div>
        <div class="project-links">
          <a href="https://www.mendock.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Members Only -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1a1014, #5c1a3c);">🧥</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Streetwear</span>
        </div>
        <div class="project-title">Members Only</div>
        <div class="project-desc">Iconic American streetwear brand — heritage-inspired design sections, capsule collection drops, limited-quantity badges, and a VIP member early-access integration.</div>
        <div class="project-links">
          <a href="https://membersonly.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Zana Herbals -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1a2a0a, #5c8c1a);">🌿</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Wellness / Herbal</span>
        </div>
        <div class="project-title">Zana Herbals</div>
        <div class="project-desc">Herbal wellness brand store — ingredient transparency pages, subscription bundles, trust-building review integrations, and an educational blog seamlessly tied to products.</div>
        <div class="project-links">
          <a href="https://zanaherbals.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Momz Joy -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #2a0a1a, #8c1a5c);">👶</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Mom & Baby</span>
        </div>
        <div class="project-title">Momz Joy</div>
        <div class="project-desc">Maternity and baby products store — age/stage-based product filtering, gift bundle builder, baby registry feature, and warm, nurturing UI tailored for new parents.</div>
        <div class="project-links">
          <a href="https://momzjoy.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Space Milk -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #0a0a1e, #1a1a6c);">🌌</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Beverage / D2C</span>
        </div>
        <div class="project-title">Space Milk</div>
        <div class="project-desc">Futuristic beverage D2C brand — bold cosmic visual theme, animated hero sections, subscription-first checkout flow, and referral program integration.</div>
        <div class="project-links">
          <a href="https://spacemilk.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Cupji -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1e0a0a, #8c2a1a);">☕</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Coffee / Lifestyle</span>
        </div>
        <div class="project-title">Cupji</div>
        <div class="project-desc">Specialty coffee and drinkware Shopify store — custom flavor/roast filter system, subscription coffee plans, gifting section, and a cozy editorial homepage layout.</div>
        <div class="project-links">
          <a href="https://cupji.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Lea Clothing Co -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1a0e0a, #7c3c1a);">👚</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Fashion / Apparel</span>
        </div>
        <div class="project-title">Lea Clothing Co</div>
        <div class="project-desc">Independent women's clothing brand — editorial lookbook pages, size guide integration, Instagram feed sync, and a streamlined one-page checkout for mobile shoppers.</div>
        <div class="project-links">
          <a href="https://www.leaclothingco.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Genaura -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1a0a1e, #6c1a8c);">✨</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Beauty / Skincare</span>
        </div>
        <div class="project-title">Genaura</div>
        <div class="project-desc">Premium Indian skincare brand — skin type quiz, ingredient highlight sections, before/after gallery, and a subscription-first product strategy with auto-renew flows.</div>
        <div class="project-links">
          <a href="https://www.genaura.in/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- NextGen Nutra -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #0a1a0a, #1a6c1a);">💪</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Nutrition / Sports</span>
        </div>
        <div class="project-title">NextGen Nutra</div>
        <div class="project-desc">Sports nutrition brand — flavor variant swatches, stack builder bundles, goal-based product filtering (bulk/cut/endurance), and a performance-optimized storefront for high traffic.</div>
        <div class="project-links">
          <a href="https://nextgennutra.in/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Gibson Athletic -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1a1a0a, #6c5c1a);">🏋️</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Athletic / Fitness</span>
        </div>
        <div class="project-title">Gibson Athletic</div>
        <div class="project-desc">Professional wrestling and gymnastics equipment brand — heavy-duty product specs layout, institutional buyer (school/gym) account tier, bulk quote request, and custom mat builder tool.</div>
        <div class="project-links">
          <a href="https://gibsonathletic.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Zephh -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #0a1e2a, #1a6c8c);">🌬️</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Lifestyle / Wellness</span>
        </div>
        <div class="project-title">Zephh</div>
        <div class="project-desc">Wellness lifestyle brand — minimalist Shopify theme with custom section blocks, scent/mood-based product navigation, and subscription wellness box setup.</div>
        <div class="project-links">
          <a href="https://www.zephh.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Alice Collins -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1e1414, #6c3c3c);">💍</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Jewelry / Accessories</span>
        </div>
        <div class="project-title">Alice Collins</div>
        <div class="project-desc">Elegant jewelry e-commerce — refined Shopify theme with high-end editorial photography support, gift wrapping add-on, engraving customization, and a luxury unboxing-focused product page.</div>
        <div class="project-links">
          <a href="https://alicecollins.com/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

    <!-- Style Union -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1a0a2a, #5c1a8c);">🧣</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Fashion / India</span>
        </div>
        <div class="project-title">Style Union</div>
        <div class="project-desc">Indian fashion brand on Shopify — ethnic wear categories, COD payment integration, regional size chart customization, and festive collection campaign landing pages.</div>
        <div class="project-links">
          <a href="https://styleunion.in/" target="_blank" class="project-link primary">Live Site</a>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <p class="section-tag">About Me</p>
  <h2 class="section-title">The Developer Behind The Stores</h2>
  <div class="about-wrap">
    <div class="about-visual">
      <div class="avatar-circle">JD</div>
      <div class="avatar-name">John Dev</div>
      <div class="avatar-role">Shopify Developer & E-Commerce Expert</div>
      <div class="avatar-badges">
        <span class="skill-pill">Shopify</span>
        <span class="skill-pill">Liquid</span>
        <span class="skill-pill">Hydrogen</span>
        <span class="skill-pill">Checkout Ext.</span>
        <span class="skill-pill">Metafields</span>
        <span class="skill-pill">Shopify APIs</span>
        <span class="skill-pill">CRO</span>
        <span class="skill-pill">Theme Dev</span>
      </div>
    </div>
    <div class="about-text">
      <p>I'm a <strong>dedicated Shopify developer with 5+ years of experience</strong> building high-converting e-commerce stores across fashion, beauty, wellness, food, athletics, and luxury niches. I've shipped 25+ Shopify projects ranging from independent DTC brands to large-scale multi-national retailers.</p>
      <p>My expertise spans <strong>custom Liquid theme development</strong>, Shopify Hydrogen (headless), checkout extensions, metafield architectures, and deep API integrations — everything needed to turn a Shopify store into a revenue-generating machine.</p>
      <p>Whether you need a <strong>fully custom theme from scratch</strong>, a Dawn customization, a subscription setup, a complex product configurator, or a CRO audit — I bring the same level of care and craftsmanship to every project.</p>
      <a href="#contact" class="btn-primary" style="display:inline-block; margin-top:0.5rem;">Let's Work Together</a>
    </div>
  </div>
</section>


<!-- FOOTER -->
<footer>
  <div>© 2025 Rohit Tawar · </div>
  <div class="footer-links">
    <a href="#">GitHub</a>
    <a href="#">LinkedIn</a>
    <a href="#">Twitter</a>
    <a href="#">Resume</a>
  </div>
</footer>

</body>
</html>
