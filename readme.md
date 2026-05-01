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
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#contact" class="nav-cta">Hire Me</a>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg"></div>
  <div class="hero-bg2"></div>
  <div class="badge"><span class="badge-dot"></span> Available for freelance & full-time</div>
  <h1>Full-Stack <span class="grad">Web Developer</span> & Digital Craftsman</h1>
  <p class="hero-sub">
    I build fast, scalable, and visually stunning digital experiences — from WordPress themes and Shopify stores to enterprise-grade React, Angular & Node.js applications.
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
      <span class="stat-num">80+</span>
      <span class="stat-label">Projects Delivered</span>
    </div>
    <div>
      <span class="stat-num">30+</span>
      <span class="stat-label">Happy Clients</span>
    </div>
    <div>
      <span class="stat-num">7</span>
      <span class="stat-label">Tech Ecosystems</span>
    </div>
  </div>
</section>

<!-- TECH STACK -->
<section id="stack">
  <p class="section-tag">Technologies</p>
  <h2 class="section-title">My Tech Stack</h2>
  <div class="tech-grid">
    <div class="tech-card" style="--card-glow: rgba(33,117,186,0.15);">
      <span class="tech-icon">🟦</span>
      <div class="tech-name">WordPress</div>
      <div class="tech-type">CMS & Themes</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(150,191,83,0.12);">
      <span class="tech-icon">🛍️</span>
      <div class="tech-name">Shopify</div>
      <div class="tech-type">E-Commerce</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(104,160,99,0.12);">
      <span class="tech-icon">🟩</span>
      <div class="tech-name">Node.js</div>
      <div class="tech-type">Backend Runtime</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(221,0,49,0.1);">
      <span class="tech-icon">🔺</span>
      <div class="tech-name">Angular</div>
      <div class="tech-type">Frontend Framework</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(97,218,251,0.12);">
      <span class="tech-icon">⚛️</span>
      <div class="tech-name">React.js</div>
      <div class="tech-type">UI Library</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(120,82,161,0.12);">
      <span class="tech-icon">🐘</span>
      <div class="tech-name">PHP</div>
      <div class="tech-type">Server-Side Lang</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(0,229,192,0.1);">
      <span class="tech-icon">🗄️</span>
      <div class="tech-name">MySQL / MongoDB</div>
      <div class="tech-type">Databases</div>
    </div>
    <div class="tech-card" style="--card-glow: rgba(255,153,0,0.1);">
      <span class="tech-icon">☁️</span>
      <div class="tech-name">AWS / Vercel</div>
      <div class="tech-type">Cloud & Deploy</div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <p class="section-tag">Portfolio</p>
  <h2 class="section-title">Featured Projects</h2>
  <div class="projects-grid">

    <!-- WordPress -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1e3a5f, #2b6cb0);">🎨</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(33,117,186,0.15);color:#5ba3d9;">WordPress</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">PHP</span>
        </div>
        <div class="project-title">CreativeAgency Theme</div>
        <div class="project-desc">Custom WordPress theme with Elementor integration, WooCommerce support, and a fully responsive layout for a digital marketing agency.</div>
        <div class="project-links">
          <a href="#" class="project-link primary">Live Demo</a>
          <a href="#" class="project-link">GitHub</a>
        </div>
      </div>
    </div>

    <!-- Shopify -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1a3c2e, #2f9c6e);">🛒</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(150,191,83,0.15);color:#8ecf4e;">Shopify</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Liquid</span>
        </div>
        <div class="project-title">LuxeWear Store</div>
        <div class="project-desc">High-converting Shopify store for a fashion brand — custom Liquid templates, metafields, subscription app integration & checkout customization.</div>
        <div class="project-links">
          <a href="#" class="project-link primary">Live Demo</a>
          <a href="#" class="project-link">GitHub</a>
        </div>
      </div>
    </div>

    <!-- Node.js -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1c2e1c, #3d7a3d);">⚡</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(104,160,99,0.15);color:#7ec87a;">Node.js</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Express</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">MongoDB</span>
        </div>
        <div class="project-title">Real-Time Chat API</div>
        <div class="project-desc">Scalable REST & WebSocket API powering a real-time messaging app. Includes JWT auth, rate limiting, Redis caching, and Socket.io integration.</div>
        <div class="project-links">
          <a href="#" class="project-link primary">Live Demo</a>
          <a href="#" class="project-link">GitHub</a>
        </div>
      </div>
    </div>

    <!-- Angular -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #3a0a0a, #b71c1c);">🔺</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(221,0,49,0.15);color:#ff6b6b;">Angular</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">TypeScript</span>
        </div>
        <div class="project-title">Enterprise Dashboard</div>
        <div class="project-desc">Analytics dashboard for an HR SaaS platform — built with Angular 17, NgRx state management, chart integrations, and role-based access control.</div>
        <div class="project-links">
          <a href="#" class="project-link primary">Live Demo</a>
          <a href="#" class="project-link">GitHub</a>
        </div>
      </div>
    </div>

    <!-- React -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #0a1929, #1565c0);">⚛️</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(97,218,251,0.12);color:#61dafb;">React.js</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Next.js</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Tailwind</span>
        </div>
        <div class="project-title">SaaS Landing Platform</div>
        <div class="project-desc">Full-featured marketing site and app shell for a B2B SaaS product — SSR, dynamic OG images, Stripe billing, and Framer Motion animations.</div>
        <div class="project-links">
          <a href="#" class="project-link primary">Live Demo</a>
          <a href="#" class="project-link">GitHub</a>
        </div>
      </div>
    </div>

    <!-- PHP -->
    <div class="project-card">
      <div class="project-thumb" style="background: linear-gradient(135deg, #1e1440, #4a1d96);">🐘</div>
      <div class="project-body">
        <div class="project-tags">
          <span class="project-tag" style="background:rgba(120,82,161,0.15);color:#b48fd4;">PHP</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">Laravel</span>
          <span class="project-tag" style="background:rgba(255,255,255,0.06);color:#888;">MySQL</span>
        </div>
        <div class="project-title">Multi-Vendor Marketplace</div>
        <div class="project-desc">Laravel-powered marketplace with vendor dashboards, order management, Stripe Connect payouts, email notifications, and an admin control panel.</div>
        <div class="project-links">
          <a href="#" class="project-link primary">Live Demo</a>
          <a href="#" class="project-link">GitHub</a>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <p class="section-tag">About Me</p>
  <h2 class="section-title">The Developer Behind The Code</h2>
  <div class="about-wrap">
    <div class="about-visual">
      <div class="avatar-circle">JD</div>
      <div class="avatar-name">John Dev</div>
      <div class="avatar-role">Full-Stack Web Developer</div>
      <div class="avatar-badges">
        <span class="skill-pill">WordPress</span>
        <span class="skill-pill">Shopify</span>
        <span class="skill-pill">Node.js</span>
        <span class="skill-pill">React</span>
        <span class="skill-pill">Angular</span>
        <span class="skill-pill">PHP</span>
        <span class="skill-pill">Laravel</span>
        <span class="skill-pill">Next.js</span>
      </div>
    </div>
    <div class="about-text">
      <p>I'm a <strong>full-stack developer with 5+ years of experience</strong> building everything from blazing-fast e-commerce stores to complex enterprise web applications. I thrive at the intersection of design and engineering — writing clean code that looks as good as it performs.</p>
      <p>My journey started with <strong>PHP and WordPress</strong>, and over the years I've expanded into modern JavaScript ecosystems — <strong>React, Angular, and Node.js</strong> — as well as Shopify's Liquid templating system for building high-converting storefronts.</p>
      <p>Whether you need a <strong>custom WordPress plugin</strong>, a Shopify store that converts, a <strong>scalable REST API</strong>, or a polished React SPA — I bring the same level of care and craftsmanship to every project.</p>
      <a href="#contact" class="btn-primary" style="display:inline-block; margin-top:0.5rem;">Let's Work Together</a>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <p class="section-tag">Get In Touch</p>
  <h2 class="section-title">Start a Project</h2>
  <div class="contact-wrap">
    <div class="contact-info">
      <h3>Let's build something great together.</h3>
      <p style="color:var(--muted);font-size:0.9rem;line-height:1.7;margin-bottom:2rem;">
        Whether you have a project in mind, want to explore collaboration, or just have a question — my inbox is always open.
      </p>
      <div class="contact-item">
        <div class="contact-icon">📧</div>
        <span>hello@johndev.io</span>
      </div>
      <div class="contact-item">
        <div class="contact-icon">📍</div>
        <span>Available worldwide · Remote-first</span>
      </div>
      <div class="contact-item">
        <div class="contact-icon">💼</div>
        <span>linkedin.com/in/johndev</span>
      </div>
      <div class="contact-item">
        <div class="contact-icon">🐙</div>
        <span>github.com/johndev</span>
      </div>
    </div>
    <div>
      <div class="form-group">
        <label>Your Name</label>
        <input type="text" class="form-control" placeholder="Jane Smith" />
      </div>
      <div class="form-group">
        <label>Email Address</label>
        <input type="email" class="form-control" placeholder="jane@company.com" />
      </div>
      <div class="form-group">
        <label>Project Type</label>
        <select class="form-control">
          <option>WordPress Development</option>
          <option>Shopify Store</option>
          <option>React / Next.js App</option>
          <option>Angular Application</option>
          <option>Node.js API / Backend</option>
          <option>PHP / Laravel Project</option>
          <option>Other</option>
        </select>
      </div>
      <div class="form-group">
        <label>Tell me about your project</label>
        <textarea class="form-control" placeholder="Describe your project, timeline, and budget…"></textarea>
      </div>
      <button class="btn-primary" style="width:100%;text-align:center;" onclick="alert('Message sent! I\'ll get back to you within 24 hours.')">
        Send Message →
      </button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div>© 2025 John Dev · Built with passion & caffeine</div>
  <div class="footer-links">
    <a href="#">GitHub</a>
    <a href="#">LinkedIn</a>
    <a href="#">Twitter</a>
    <a href="#">Resume</a>
  </div>
</footer>

</body>
</html>
