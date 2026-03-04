
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Luna&co — A Modern Art & Design Studio</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --cream: #FDF6EC;
      --warm-white: #FFFBF4;
      --terracotta: #C8613A;
      --peach: #F0A07A;
      --blush: #F2C9B0;
      --sage: #8BAF8D;
      --deep: #2E1F14;
      --muted: #7A5C48;
      --gold: #D4973A;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'DM Sans', sans-serif;
      background-color: var(--cream);
      color: var(--deep);
      overflow-x: hidden;
    }

    /* ---- NAV ---- */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 1.2rem 3rem;
      background: rgba(253,246,236,0.88);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(200,97,58,0.1);
    }
    .nav-logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.5rem; font-weight: 900;
      color: var(--terracotta);
      letter-spacing: -0.02em;
    }
    .nav-logo span { font-style: italic; }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a {
      text-decoration: none; font-size: 0.85rem; font-weight: 500;
      color: var(--muted); letter-spacing: 0.05em; text-transform: uppercase;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--terracotta); }
    .nav-cta {
      background: var(--terracotta); color: #fff;
      border: none; padding: 0.6rem 1.4rem; border-radius: 100px;
      font-family: 'DM Sans', sans-serif; font-size: 0.85rem; font-weight: 500;
      cursor: pointer; transition: background 0.2s, transform 0.15s;
    }
    .nav-cta:hover { background: var(--deep); transform: translateY(-1px); }

    /* ---- HERO ---- */
    #hero {
      min-height: 100vh;
      display: grid; grid-template-columns: 1fr 1fr;
      padding: 7rem 3rem 4rem;
      gap: 2rem; align-items: center;
      position: relative; overflow: hidden;
    }
    .hero-blob {
      position: absolute; border-radius: 50%; filter: blur(80px); opacity: 0.35; pointer-events: none;
    }
    .blob1 { width: 500px; height: 500px; background: var(--peach); top: -100px; right: -100px; animation: float 7s ease-in-out infinite; }
    .blob2 { width: 350px; height: 350px; background: var(--blush); bottom: 0; left: 5%; animation: float 9s ease-in-out infinite reverse; }
    .blob3 { width: 250px; height: 250px; background: var(--sage); opacity: 0.2; top: 40%; right: 45%; animation: float 11s ease-in-out infinite; }

    @keyframes float {
      0%, 100% { transform: translateY(0) scale(1); }
      50% { transform: translateY(-30px) scale(1.04); }
    }

    .hero-text { position: relative; z-index: 2; }
    .hero-eyebrow {
      display: inline-flex; align-items: center; gap: 0.5rem;
      background: var(--blush); color: var(--terracotta);
      font-size: 0.75rem; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase;
      padding: 0.4rem 1rem; border-radius: 100px; margin-bottom: 1.5rem;
      animation: fadeUp 0.8s ease both;
    }
    .hero-eyebrow::before { content: '✦'; font-size: 0.6rem; }

    h1.hero-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3.2rem, 6vw, 5.5rem);
      font-weight: 900; line-height: 1.05;
      color: var(--deep);
      animation: fadeUp 0.8s 0.15s ease both;
    }
    h1.hero-title em { font-style: italic; color: var(--terracotta); }

    .hero-subtitle {
      margin-top: 1.5rem; font-size: 1.1rem; line-height: 1.7;
      color: var(--muted); max-width: 460px;
      animation: fadeUp 0.8s 0.3s ease both;
    }
    .hero-actions {
      display: flex; gap: 1rem; margin-top: 2.5rem; flex-wrap: wrap;
      animation: fadeUp 0.8s 0.45s ease both;
    }
    .btn-primary {
      background: var(--terracotta); color: #fff;
      padding: 0.9rem 2rem; border-radius: 100px; font-weight: 500;
      border: none; cursor: pointer; font-size: 0.95rem; font-family: 'DM Sans', sans-serif;
      transition: all 0.2s; box-shadow: 0 4px 20px rgba(200,97,58,0.35);
    }
    .btn-primary:hover { background: var(--deep); transform: translateY(-2px); box-shadow: 0 8px 30px rgba(46,31,20,0.25); }
    .btn-secondary {
      background: transparent; color: var(--deep);
      padding: 0.9rem 2rem; border-radius: 100px; font-weight: 500;
      border: 2px solid var(--deep); cursor: pointer; font-size: 0.95rem; font-family: 'DM Sans', sans-serif;
      transition: all 0.2s;
    }
    .btn-secondary:hover { background: var(--deep); color: var(--cream); }

    .hero-visual {
      position: relative; z-index: 2;
      display: flex; justify-content: center; align-items: center;
      animation: fadeUp 0.8s 0.2s ease both;
    }
    .hero-canvas {
      width: min(420px, 90%); aspect-ratio: 3/4;
      background: linear-gradient(135deg, var(--blush) 0%, var(--peach) 50%, var(--terracotta) 100%);
      border-radius: 2rem 6rem 2rem 6rem;
      display: flex; align-items: center; justify-content: center;
      position: relative; overflow: hidden;
      box-shadow: 0 30px 80px rgba(200,97,58,0.2), 0 0 0 12px rgba(240,160,122,0.15);
    }
    .canvas-text {
      font-family: 'Playfair Display', serif;
      font-size: 5rem; color: rgba(255,255,255,0.4); user-select: none;
      animation: spinSlow 30s linear infinite;
    }
    @keyframes spinSlow { to { transform: rotate(360deg); } }
    .canvas-badge {
      position: absolute; bottom: 2rem; right: 2rem;
      background: #fff; border-radius: 1rem; padding: 0.8rem 1.2rem;
      font-size: 0.75rem; font-weight: 500; color: var(--deep);
      box-shadow: 0 8px 30px rgba(0,0,0,0.1);
    }
    .canvas-badge strong { display: block; font-family: 'Playfair Display', serif; font-size: 1.1rem; color: var(--terracotta); }
    .canvas-dot {
      position: absolute; top: 1.5rem; left: 1.5rem;
      width: 60px; height: 60px; border-radius: 50%;
      background: rgba(255,255,255,0.3); backdrop-filter: blur(4px);
      display: flex; align-items: center; justify-content: center;
      font-size: 1.5rem;
    }

    /* ---- MARQUEE ---- */
    .marquee-wrap {
      background: var(--terracotta); padding: 1rem 0; overflow: hidden;
      border-top: 2px solid var(--deep); border-bottom: 2px solid var(--deep);
    }
    .marquee-track {
      display: flex; gap: 3rem; white-space: nowrap;
      animation: marquee 20s linear infinite;
    }
    @keyframes marquee { from { transform: translateX(0); } to { transform: translateX(-50%); } }
    .marquee-item {
      font-family: 'Playfair Display', serif; font-style: italic;
      font-size: 1.1rem; color: #fff; flex-shrink: 0;
      display: flex; align-items: center; gap: 1.5rem;
    }
    .marquee-item span { color: var(--blush); font-size: 0.6rem; }

    /* ---- SECTION SHARED ---- */
    section { padding: 6rem 3rem; }
    .section-eyebrow {
      display: inline-flex; align-items: center; gap: 0.5rem;
      font-size: 0.75rem; font-weight: 500; letter-spacing: 0.12em; text-transform: uppercase;
      color: var(--terracotta); margin-bottom: 1rem;
    }
    .section-eyebrow::before { content: '◆'; font-size: 0.5rem; }
    h2.section-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 4vw, 3.2rem); font-weight: 900; line-height: 1.15; color: var(--deep);
    }
    h2.section-title em { font-style: italic; color: var(--terracotta); }

    /* ---- ABOUT ---- */
    #about {
      background: var(--warm-white);
      display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center;
    }
    .about-visual {
      display: grid; grid-template-columns: 1fr 1fr; gap: 1rem;
    }
    .about-card {
      border-radius: 1.5rem; overflow: hidden;
      aspect-ratio: 1; display: flex; align-items: center; justify-content: center;
      font-size: 2.5rem; font-weight: 900;
      font-family: 'Playfair Display', serif;
      transition: transform 0.3s;
    }
    .about-card:hover { transform: scale(1.03) rotate(1deg); }
    .about-card:nth-child(1) { background: linear-gradient(135deg, var(--peach), var(--terracotta)); color: #fff; grid-row: span 2; border-radius: 2rem; font-size: 3.5rem; }
    .about-card:nth-child(2) { background: var(--blush); color: var(--terracotta); font-size: 2rem; }
    .about-card:nth-child(3) { background: var(--sage); color: #fff; font-size: 2rem; }
    .about-text p { font-size: 1.05rem; line-height: 1.8; color: var(--muted); margin-top: 1.2rem; }
    .about-stats { display: flex; gap: 2rem; margin-top: 2.5rem; flex-wrap: wrap; }
    .stat { text-align: center; }
    .stat-num {
      font-family: 'Playfair Display', serif; font-size: 2.5rem; font-weight: 900;
      color: var(--terracotta); line-height: 1;
    }
    .stat-label { font-size: 0.8rem; color: var(--muted); margin-top: 0.25rem; letter-spacing: 0.05em; text-transform: uppercase; }

    /* ---- SERVICES ---- */
    #services { background: var(--cream); }
    .services-header { max-width: 600px; margin-bottom: 3.5rem; }
    .services-grid {
      display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 1.5rem;
    }
    .service-card {
      background: var(--warm-white); border-radius: 1.5rem;
      padding: 2rem; border: 1.5px solid transparent;
      transition: all 0.3s; cursor: default;
      position: relative; overflow: hidden;
    }
    .service-card::before {
      content: ''; position: absolute; inset: 0; opacity: 0;
      background: linear-gradient(135deg, rgba(200,97,58,0.05), rgba(240,160,122,0.08));
      transition: opacity 0.3s;
    }
    .service-card:hover { border-color: var(--peach); transform: translateY(-4px); box-shadow: 0 16px 40px rgba(200,97,58,0.1); }
    .service-card:hover::before { opacity: 1; }
    .service-icon {
      width: 52px; height: 52px; border-radius: 1rem;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.4rem; margin-bottom: 1.2rem;
      background: var(--blush);
    }
    .service-card h3 {
      font-family: 'Playfair Display', serif; font-size: 1.25rem;
      font-weight: 700; color: var(--deep); margin-bottom: 0.6rem;
    }
    .service-card p { font-size: 0.9rem; line-height: 1.7; color: var(--muted); }
    .service-tag {
      display: inline-block; margin-top: 1.2rem;
      background: var(--blush); color: var(--terracotta);
      font-size: 0.7rem; font-weight: 500; letter-spacing: 0.08em; text-transform: uppercase;
      padding: 0.3rem 0.8rem; border-radius: 100px;
    }

    /* ---- PROCESS ---- */
    #process {
      background: var(--deep); color: var(--cream);
      text-align: center;
    }
    #process .section-eyebrow { color: var(--peach); }
    #process h2.section-title { color: var(--cream); }
    #process h2.section-title em { color: var(--peach); }
    .process-steps {
      display: flex; gap: 0; margin-top: 3.5rem;
      flex-wrap: wrap; justify-content: center;
    }
    .process-step {
      flex: 1; min-width: 200px; padding: 2rem 1.5rem;
      position: relative;
    }
    .process-step:not(:last-child)::after {
      content: '→'; position: absolute; right: -0.5rem; top: 2.5rem;
      font-size: 1.5rem; color: var(--terracotta);
    }
    .step-num {
      font-family: 'Playfair Display', serif; font-size: 3.5rem; font-weight: 900;
      color: var(--terracotta); opacity: 0.4; line-height: 1; margin-bottom: 0.5rem;
    }
    .step-title { font-family: 'Playfair Display', serif; font-size: 1.1rem; font-weight: 700; color: var(--cream); margin-bottom: 0.5rem; }
    .step-desc { font-size: 0.85rem; line-height: 1.6; color: rgba(253,246,236,0.6); }

    /* ---- CONTACT ---- */
    #contact { background: var(--warm-white); }
    .contact-wrapper {
      display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: start;
    }
    .contact-info p { font-size: 1.05rem; line-height: 1.8; color: var(--muted); margin-top: 1.2rem; }
    .contact-details { margin-top: 2rem; display: flex; flex-direction: column; gap: 1rem; }
    .contact-detail {
      display: flex; align-items: center; gap: 1rem;
      font-size: 0.9rem; color: var(--muted);
    }
    .contact-detail-icon {
      width: 40px; height: 40px; border-radius: 50%;
      background: var(--blush); display: flex; align-items: center; justify-content: center;
      font-size: 1rem; flex-shrink: 0;
    }

    .contact-form { display: flex; flex-direction: column; gap: 1.2rem; }
    .form-group { display: flex; flex-direction: column; gap: 0.4rem; }
    .form-group label { font-size: 0.8rem; font-weight: 500; letter-spacing: 0.05em; text-transform: uppercase; color: var(--muted); }
    .form-group input, .form-group textarea, .form-group select {
      background: var(--cream); border: 1.5px solid rgba(200,97,58,0.2);
      border-radius: 0.8rem; padding: 0.85rem 1rem;
      font-family: 'DM Sans', sans-serif; font-size: 0.95rem; color: var(--deep);
      outline: none; transition: border-color 0.2s;
    }
    .form-group input:focus, .form-group textarea:focus, .form-group select:focus { border-color: var(--terracotta); }
    .form-group textarea { resize: vertical; min-height: 120px; }
    .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
    .submit-btn {
      background: var(--terracotta); color: #fff;
      padding: 1rem 2rem; border-radius: 100px; border: none;
      font-family: 'DM Sans', sans-serif; font-weight: 500; font-size: 0.95rem;
      cursor: pointer; transition: all 0.2s;
      box-shadow: 0 4px 20px rgba(200,97,58,0.3);
      align-self: flex-start;
    }
    .submit-btn:hover { background: var(--deep); transform: translateY(-2px); }

    /* ---- FOOTER ---- */
    footer {
      background: var(--deep); color: rgba(253,246,236,0.7);
      padding: 3rem; display: flex; justify-content: space-between; align-items: center;
      flex-wrap: wrap; gap: 1rem;
    }
    .footer-logo {
      font-family: 'Playfair Display', serif; font-size: 1.4rem; font-weight: 900;
      color: var(--peach);
    }
    .footer-links { display: flex; gap: 1.5rem; list-style: none; }
    .footer-links a { color: rgba(253,246,236,0.5); text-decoration: none; font-size: 0.85rem; transition: color 0.2s; }
    .footer-links a:hover { color: var(--peach); }
    .footer-copy { font-size: 0.8rem; color: rgba(253,246,236,0.4); }

    /* ---- ANIMATIONS ---- */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .reveal { opacity: 0; transform: translateY(30px); transition: opacity 0.7s ease, transform 0.7s ease; }
    .reveal.visible { opacity: 1; transform: translateY(0); }

    /* ---- RESPONSIVE ---- */
    @media (max-width: 768px) {
      nav { padding: 1rem 1.5rem; }
      .nav-links { display: none; }
      #hero { grid-template-columns: 1fr; padding: 6rem 1.5rem 3rem; }
      .hero-visual { order: -1; }
      section { padding: 4rem 1.5rem; }
      #about, .contact-wrapper { grid-template-columns: 1fr; gap: 3rem; }
      .form-row { grid-template-columns: 1fr; }
      footer { flex-direction: column; text-align: center; padding: 2rem 1.5rem; }
      .process-step:not(:last-child)::after { display: none; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <div class="nav-logo">Luna<span>&co</span></div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#services">Services</a></li>
      <li><a href="#process">Process</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <button class="nav-cta" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})">Let's Work Together</button>
  </nav>

  <!-- HERO -->
  <section id="hero">
    <div class="hero-blob blob1"></div>
    <div class="hero-blob blob2"></div>
    <div class="hero-blob blob3"></div>
    <div class="hero-text">
      <div class="hero-eyebrow">Modern Art & Design Studio</div>
      <h1 class="hero-title">Where Art<br/>Meets <em>Everyday</em><br/>Beauty</h1>
      <p class="hero-subtitle">Luna&co brings warmth, creativity, and intention to every design. From custom artwork to branded experiences — we make the world a more beautiful place.</p>
      <div class="hero-actions">
        <button class="btn-primary" onclick="document.getElementById('services').scrollIntoView({behavior:'smooth'})">Explore Our Work</button>
        <button class="btn-secondary" onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})">Get in Touch</button>
      </div>
    </div>
    <div class="hero-visual">
      <div class="hero-canvas">
        <div class="canvas-text">L&</div>
        <div class="canvas-dot">🎨</div>
        <div class="canvas-badge">
          <strong>Luna&co</strong>
          Est. by Angel, Lyriq & Ella
        </div>
      </div>
    </div>
  </section>

  <!-- MARQUEE -->
  <div class="marquee-wrap">
    <div class="marquee-track">
      <div class="marquee-item">Custom Artwork <span>✦</span></div>
      <div class="marquee-item">Mug & Product Design <span>✦</span></div>
      <div class="marquee-item">Brand Identity <span>✦</span></div>
      <div class="marquee-item">Print on Demand <span>✦</span></div>
      <div class="marquee-item">Art Licensing <span>✦</span></div>
      <div class="marquee-item">Design Workshops <span>✦</span></div>
      <div class="marquee-item">Event Art Rentals <span>✦</span></div>
      <div class="marquee-item">Custom Artwork <span>✦</span></div>
      <div class="marquee-item">Mug & Product Design <span>✦</span></div>
      <div class="marquee-item">Brand Identity <span>✦</span></div>
      <div class="marquee-item">Print on Demand <span>✦</span></div>
      <div class="marquee-item">Art Licensing <span>✦</span></div>
      <div class="marquee-item">Design Workshops <span>✦</span></div>
      <div class="marquee-item">Event Art Rentals <span>✦</span></div>
    </div>
  </div>

  <!-- ABOUT -->
  <section id="about" class="reveal">
    <div class="about-visual">
      <div class="about-card">L&</div>
      <div class="about-card">🌿</div>
      <div class="about-card">✦</div>
    </div>
    <div class="about-text">
      <div class="section-eyebrow">Our Story</div>
      <h2 class="section-title">Art that <em>lives</em><br/>in the real world</h2>
      <p>Luna&co is a modern art and design studio founded by Angel, Lyriq, and Ella — three creatives with a shared belief that beautiful design should be accessible, meaningful, and everywhere.</p>
      <p>From designing mugs for your favourite local café to licensing artwork for hospitality spaces, we bring a warm, intentional aesthetic to every project we touch.</p>
      <div class="about-stats">
        <div class="stat">
          <div class="stat-num">3</div>
          <div class="stat-label">Founders</div>
        </div>
        <div class="stat">
          <div class="stat-num">∞</div>
          <div class="stat-label">Creative Ideas</div>
        </div>
        <div class="stat">
          <div class="stat-num">1</div>
          <div class="stat-label">Bold Vision</div>
        </div>
      </div>
    </div>
  </section>

  <!-- SERVICES -->
  <section id="services">
    <div class="services-header reveal">
      <div class="section-eyebrow">What We Offer</div>
      <h2 class="section-title">Products & <em>Services</em><br/>for every space</h2>
    </div>
    <div class="services-grid">
      <div class="service-card reveal">
        <div class="service-icon">☕</div>
        <h3>Product & Mug Design</h3>
        <p>Custom artwork on everyday objects — mugs, totes, stationery. We partner with cafés and businesses to bring your brand to life.</p>
        <span class="service-tag">Collab-friendly</span>
      </div>
      <div class="service-card reveal">
        <div class="service-icon">🖼️</div>
        <h3>Art for Spaces</h3>
        <p>We create and sell original artworks for restaurants, cafes, libraries, and hospitality spaces that want personality on their walls.</p>
        <span class="service-tag">Commercial</span>
      </div>
      <div class="service-card reveal">
        <div class="service-icon">📜</div>
        <h3>Art Licensing</h3>
        <p>License Luna&co designs for products, packaging, and merchandise. Earn royalties — so can we. It's a win-win creative partnership.</p>
        <span class="service-tag">Passive Income</span>
      </div>
      <div class="service-card reveal">
        <div class="service-icon">🎓</div>
        <h3>Online Courses & Tutorials</h3>
        <p>Learn the craft. Our online courses and tutorials teach design fundamentals, illustration techniques, and creative entrepreneurship.</p>
        <span class="service-tag">Education</span>
      </div>
      <div class="service-card reveal">
        <div class="service-icon">🎉</div>
        <h3>Event Art Rentals</h3>
        <p>Rent our curated artwork for events, pop-ups, exhibitions, and corporate spaces. Transform any venue into a gallery experience.</p>
        <span class="service-tag">Events</span>
      </div>
      <div class="service-card reveal">
        <div class="service-icon">📦</div>
        <h3>Print on Demand</h3>
        <p>Shop our prints, posters, and products — shipped directly to you. New drops regularly. Follow us to never miss a release.</p>
        <span class="service-tag">Shop Now</span>
      </div>
    </div>
  </section>

  <!-- PROCESS -->
  <section id="process">
    <div class="section-eyebrow">How We Work</div>
    <h2 class="section-title">Our <em>creative</em> process</h2>
    <div class="process-steps">
      <div class="process-step">
        <div class="step-num">01</div>
        <div class="step-title">Vision & Discovery</div>
        <div class="step-desc">We start by understanding your brand, space, or vision — your values, your audience, your aesthetic.</div>
      </div>
      <div class="process-step">
        <div class="step-num">02</div>
        <div class="step-title">Concept & Create</div>
        <div class="step-desc">Our studio explores ideas and develops designs that are warm, intentional, and uniquely yours.</div>
      </div>
      <div class="process-step">
        <div class="step-num">03</div>
        <div class="step-title">Refine Together</div>
        <div class="step-desc">We collaborate closely, iterating until every detail feels right and the work truly resonates.</div>
      </div>
      <div class="process-step">
        <div class="step-num">04</div>
        <div class="step-title">Launch & Deliver</div>
        <div class="step-desc">Files, prints, or products — delivered beautifully, on time, ready to go live in the world.</div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <div class="contact-wrapper">
      <div class="contact-info reveal">
        <div class="section-eyebrow">Get In Touch</div>
        <h2 class="section-title">Let's make<br/>something <em>beautiful</em></h2>
        <p>Whether you're a café owner, an event planner, or someone who just wants art on their walls — we'd love to hear from you. Every great project starts with a conversation.</p>
        <div class="contact-details">
          <div class="contact-detail">
            <div class="contact-detail-icon">📧</div>
            <span>hello@lunaco.studio</span>
          </div>
          <div class="contact-detail">
            <div class="contact-detail-icon">📍</div>
            <span>Available worldwide · Studio-based</span>
          </div>
          <div class="contact-detail">
            <div class="contact-detail-icon">📅</div>
            <span>Book a discovery call via Calendly</span>
          </div>
        </div>
      </div>
      <div class="contact-form reveal">
        <div class="form-row">
          <div class="form-group">
            <label>First Name</label>
            <input type="text" placeholder="Angel" />
          </div>
          <div class="form-group">
            <label>Last Name</label>
            <input type="text" placeholder="Smith" />
          </div>
        </div>
        <div class="form-group">
          <label>Email</label>
          <input type="email" placeholder="hello@yourcompany.com" />
        </div>
        <div class="form-group">
          <label>I'm interested in...</label>
          <select>
            <option value="">Select a service</option>
            <option>Product & Mug Design</option>
            <option>Art for Spaces</option>
            <option>Art Licensing</option>
            <option>Online Courses</option>
            <option>Event Art Rentals</option>
            <option>Print on Demand</option>
            <option>Something else</option>
          </select>
        </div>
        <div class="form-group">
          <label>Tell us about your project</label>
          <textarea placeholder="Share as much or as little as you'd like. We're all ears ✦"></textarea>
        </div>
        <button class="submit-btn">Send Message ✦</button>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="footer-logo">Luna<em style="font-style:italic">&co</em></div>
    <ul class="footer-links">
      <li><a href="#about">About</a></li>
      <li><a href="#services">Services</a></li>
      <li><a href="#process">Process</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <div class="footer-copy">© 2025 Luna&co. Made with love by Angel, Lyriq & Ella.</div>
  </footer>

  <script>
    // Scroll reveal
    const reveals = document.querySelectorAll('.reveal');
    const observer = new IntersectionObserver(entries => {
      entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); } });
    }, { threshold: 0.1 });
    reveals.forEach(el => observer.observe(el));
  </script>
</body>
</html>
