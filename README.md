# bosship004.github.io
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Luna&co — Art & Design Studio</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    :root {
      --cream: #FDF6EC; --warm-white: #FFFBF5;
      --terracotta: #D9704A; --blush: #F2A98A;
      --mustard: #E8C04A; --sage: #8BAF88;
      --deep: #2C2118; --mid: #6B4F3A; --light-mid: #C49A7A;
    }
    html { scroll-behavior: smooth; }
    body { font-family: 'DM Sans', sans-serif; background: var(--cream); color: var(--deep); overflow-x: hidden; }

    /* NAV */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 1.2rem 3rem;
      background: rgba(253,246,236,0.9); backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(217,112,74,0.12);
    }
    .nav-logo { font-family: 'Playfair Display', serif; font-size: 1.6rem; font-weight: 900; color: var(--terracotta); }
    .nav-logo em { font-style: italic; }
    .nav-links { display: flex; gap: 2.4rem; list-style: none; }
    .nav-links a { text-decoration: none; color: var(--mid); font-size: 0.85rem; font-weight: 500; letter-spacing: 0.06em; text-transform: uppercase; transition: color 0.2s; }
    .nav-links a:hover { color: var(--terracotta); }
    .nav-cta { background: var(--terracotta); color: #fff; padding: 0.55rem 1.4rem; border-radius: 50px; font-size: 0.85rem; font-weight: 500; text-decoration: none; transition: background 0.2s, transform 0.15s; }
    .nav-cta:hover { background: var(--mid); transform: translateY(-1px); }

    /* HERO */
    #hero {
      min-height: 100vh; display: grid; grid-template-columns: 1fr 1fr;
      align-items: center; padding: 7rem 3rem 4rem; gap: 3rem;
      position: relative; overflow: hidden;
    }
    #hero::before {
      content: ''; position: absolute; top: -120px; right: -80px;
      width: 520px; height: 520px; border-radius: 50%;
      background: radial-gradient(circle, rgba(242,169,138,0.3) 0%, transparent 70%);
      animation: floatBlob 8s ease-in-out infinite;
    }
    #hero::after {
      content: ''; position: absolute; bottom: -80px; left: 5%;
      width: 360px; height: 360px; border-radius: 50%;
      background: radial-gradient(circle, rgba(232,192,74,0.22) 0%, transparent 70%);
      animation: floatBlob 11s ease-in-out infinite reverse;
    }
    @keyframes floatBlob { 0%,100% { transform: translateY(0) scale(1); } 50% { transform: translateY(-28px) scale(1.04); } }

    .hero-text { position: relative; z-index: 2; }
    .eyebrow {
      display: inline-flex; align-items: center; gap: 0.6rem;
      font-size: 0.78rem; font-weight: 500; text-transform: uppercase; letter-spacing: 0.12em;
      color: var(--terracotta); margin-bottom: 1.5rem;
    }
    .eyebrow::before { content: ''; width: 28px; height: 2px; background: var(--terracotta); display: inline-block; }
    h1 { font-family: 'Playfair Display', serif; font-size: clamp(3rem, 5.5vw, 5.2rem); font-weight: 900; line-height: 1.06; color: var(--deep); margin-bottom: 1.5rem; }
    h1 em { font-style: italic; color: var(--terracotta); }
    .hero-sub { font-size: 1.08rem; color: var(--mid); line-height: 1.75; max-width: 480px; margin-bottom: 2.5rem; }
    .hero-btns { display: flex; gap: 1rem; flex-wrap: wrap; }
    .btn-primary { background: var(--terracotta); color: #fff; padding: 0.85rem 2.2rem; border-radius: 50px; font-size: 0.95rem; font-weight: 500; text-decoration: none; box-shadow: 0 4px 20px rgba(217,112,74,0.3); transition: transform 0.2s, box-shadow 0.2s; }
    .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(217,112,74,0.45); }
    .btn-ghost { border: 1.5px solid var(--light-mid); color: var(--mid); padding: 0.85rem 2.2rem; border-radius: 50px; font-size: 0.95rem; font-weight: 500; text-decoration: none; transition: border-color 0.2s, color 0.2s; }
    .btn-ghost:hover { border-color: var(--terracotta); color: var(--terracotta); }

    .hero-visual { position: relative; z-index: 2; display: flex; justify-content: center; }
    .art-grid { display: grid; grid-template-columns: 1fr 1fr; grid-template-rows: auto auto; gap: 1rem; width: 100%; max-width: 440px; }
    .art-card { border-radius: 20px; overflow: hidden; animation: fadeUp 0.7s ease both; }
    .art-card:nth-child(1) { grid-row: span 2; animation-delay: 0.1s; }
    .art-card:nth-child(2) { animation-delay: 0.2s; }
    .art-card:nth-child(3) { animation-delay: 0.3s; }
    @keyframes fadeUp { from { opacity: 0; transform: translateY(28px); } to { opacity: 1; transform: translateY(0); } }
    .art-block { width: 100%; display: flex; align-items: center; justify-content: center; min-height: 155px; }
    .art-block.tall { min-height: 330px; }
    .ac1 { background: linear-gradient(145deg, #D9704A, #E8934A); }
    .ac2 { background: linear-gradient(145deg, #E8C04A, #F0D060); }
    .ac3 { background: linear-gradient(145deg, #8BAF88, #6A9E7A); }
    .art-block svg { width: 55%; opacity: 0.38; }

    /* BADGE */
    .badge { display: inline-block; background: rgba(217,112,74,0.1); color: var(--terracotta); font-size: 0.76rem; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase; padding: 0.38rem 1rem; border-radius: 50px; margin-bottom: 1.1rem; }

    /* ABOUT */
    #about { padding: 7rem 3rem; display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: center; background: var(--warm-white); }
    h2 { font-family: 'Playfair Display', serif; font-size: clamp(2rem, 3.8vw, 3rem); font-weight: 800; line-height: 1.15; color: var(--deep); margin-bottom: 1.3rem; }
    h2 em { font-style: italic; color: var(--terracotta); }
    .body-text { color: var(--mid); line-height: 1.8; font-size: 1rem; margin-bottom: 1.2rem; }
    .pills { display: flex; flex-wrap: wrap; gap: 0.6rem; margin-top: 1.4rem; }
    .pill { background: var(--cream); border: 1px solid rgba(196,154,122,0.3); padding: 0.45rem 1rem; border-radius: 50px; font-size: 0.83rem; color: var(--mid); }
    .blob-wrap { position: relative; }
    .blob {
      width: 100%; aspect-ratio: 1;
      border-radius: 60% 40% 55% 45% / 45% 55% 40% 60%;
      background: linear-gradient(135deg, var(--blush), var(--mustard) 55%, var(--sage));
      display: flex; align-items: center; justify-content: center;
      font-family: 'Playfair Display', serif; font-size: 2rem; font-style: italic;
      color: rgba(44,33,24,0.55);
      animation: morph 10s ease-in-out infinite;
    }
    @keyframes morph {
      0%,100% { border-radius: 60% 40% 55% 45% / 45% 55% 40% 60%; }
      33%      { border-radius: 45% 55% 40% 60% / 60% 40% 55% 45%; }
      66%      { border-radius: 55% 45% 60% 40% / 40% 60% 45% 55%; }
    }
    .about-stat { position: absolute; bottom: -1rem; right: -1rem; background: var(--deep); color: #fff; padding: 1.1rem 1.5rem; border-radius: 16px; text-align: center; }
    .about-stat strong { display: block; font-family: 'Playfair Display', serif; font-size: 2rem; color: var(--mustard); }
    .about-stat span { font-size: 0.72rem; letter-spacing: 0.08em; text-transform: uppercase; opacity: 0.65; }

    /* SERVICES */
    #services { padding: 7rem 3rem; background: var(--cream); }
    .sec-head { text-align: center; margin-bottom: 3.5rem; }
    .sec-head p { color: var(--mid); font-size: 1rem; max-width: 500px; margin: 0.8rem auto 0; line-height: 1.75; }
    .grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.4rem; }
    .svc {
      background: var(--warm-white); border-radius: 22px; padding: 2rem;
      border: 1px solid rgba(196,154,122,0.2);
      position: relative; overflow: hidden;
      transition: transform 0.25s, box-shadow 0.25s;
    }
    .svc::after { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px; background: var(--grad); opacity: 0; transition: opacity 0.25s; }
    .svc:hover { transform: translateY(-6px); box-shadow: 0 18px 45px rgba(44,33,24,0.1); }
    .svc:hover::after { opacity: 1; }
    .svc:nth-child(1) { --grad: linear-gradient(90deg, #D9704A, #F2A98A); }
    .svc:nth-child(2) { --grad: linear-gradient(90deg, #E8C04A, #F2A98A); }
    .svc:nth-child(3) { --grad: linear-gradient(90deg, #8BAF88, #E8C04A); }
    .svc:nth-child(4) { --grad: linear-gradient(90deg, #F2A98A, #D9704A); }
    .svc:nth-child(5) { --grad: linear-gradient(90deg, #D9704A, #E8C04A); }
    .svc:nth-child(6) { --grad: linear-gradient(90deg, #8BAF88, #F2A98A); }
    .svc-icon { width: 48px; height: 48px; border-radius: 12px; display: flex; align-items: center; justify-content: center; font-size: 1.4rem; margin-bottom: 1.1rem; }
    .i1{background:rgba(217,112,74,0.12);} .i2{background:rgba(232,192,74,0.14);} .i3{background:rgba(139,175,136,0.14);}
    .i4{background:rgba(242,169,138,0.14);} .i5{background:rgba(217,112,74,0.1);} .i6{background:rgba(139,175,136,0.1);}
    .svc h3 { font-family: 'Playfair Display', serif; font-size: 1.2rem; font-weight: 700; color: var(--deep); margin-bottom: 0.6rem; }
    .svc p { color: var(--mid); font-size: 0.9rem; line-height: 1.7; margin-bottom: 1.2rem; }
    .svc-btn { display: inline-flex; align-items: center; gap: 0.4rem; font-size: 0.83rem; font-weight: 500; color: var(--terracotta); text-decoration: none; letter-spacing: 0.03em; transition: gap 0.2s; }
    .svc-btn:hover { gap: 0.7rem; }
    .svc-btn::after { content: '→'; }

    /* MISSION */
    #mission { padding: 7rem 3rem; background: var(--deep); color: #fff; text-align: center; position: relative; overflow: hidden; }
    #mission::before { content: ''; position: absolute; top: -150px; left: -80px; width: 580px; height: 580px; border-radius: 50%; background: radial-gradient(circle, rgba(217,112,74,0.14), transparent 70%); }
    #mission .badge { background: rgba(217,112,74,0.2); color: var(--blush); position: relative; z-index: 2; }
    #mission h2 { color: #fff; font-size: clamp(2rem, 4vw, 3.2rem); max-width: 680px; margin: 0 auto 1.4rem; position: relative; z-index: 2; }
    #mission h2 em { color: var(--mustard); }
    #mission > p { color: rgba(255,255,255,0.6); font-size: 1rem; max-width: 560px; margin: 0 auto 3rem; line-height: 1.8; position: relative; z-index: 2; }
    .values { display: flex; justify-content: center; gap: 3rem; flex-wrap: wrap; position: relative; z-index: 2; }
    .val { max-width: 175px; }
    .val-n { font-family: 'Playfair Display', serif; font-size: 2.8rem; font-weight: 900; color: var(--terracotta); display: block; margin-bottom: 0.3rem; }
    .val p { color: rgba(255,255,255,0.55); font-size: 0.86rem; line-height: 1.55; }

    /* CONTACT */
    #contact { padding: 7rem 3rem; background: var(--warm-white); display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: start; }
    .contact-info h2 { margin-bottom: 1rem; }
    .contact-info > p { color: var(--mid); font-size: 1rem; line-height: 1.8; margin-bottom: 2rem; }
    .c-detail { display: flex; align-items: center; gap: 0.85rem; margin-bottom: 1.1rem; color: var(--mid); font-size: 0.93rem; }
    .c-icon { width: 38px; height: 38px; border-radius: 10px; background: rgba(217,112,74,0.1); display: flex; align-items: center; justify-content: center; font-size: 1rem; flex-shrink: 0; }
    .cform { background: var(--cream); border-radius: 22px; padding: 2.4rem; border: 1px solid rgba(196,154,122,0.2); }
    .fg { margin-bottom: 1.2rem; }
    .fg label { display: block; font-size: 0.8rem; font-weight: 500; text-transform: uppercase; letter-spacing: 0.07em; color: var(--mid); margin-bottom: 0.45rem; }
    .fg input, .fg textarea, .fg select {
      width: 100%; padding: 0.82rem 1rem;
      border: 1.5px solid rgba(196,154,122,0.3); border-radius: 11px;
      background: var(--warm-white); font-family: 'DM Sans', sans-serif;
      font-size: 0.93rem; color: var(--deep); outline: none; transition: border-color 0.2s;
    }
    .fg input:focus, .fg textarea:focus, .fg select:focus { border-color: var(--terracotta); }
    .fg textarea { min-height: 105px; resize: vertical; }
    .fg select { appearance: none; cursor: pointer; }
    .fsub { width: 100%; padding: 0.9rem; background: var(--terracotta); color: #fff; border: none; border-radius: 11px; font-family: 'DM Sans', sans-serif; font-size: 0.98rem; font-weight: 500; cursor: pointer; transition: background 0.2s, transform 0.15s; }
    .fsub:hover { background: var(--mid); transform: translateY(-1px); }

    /* FOOTER */
    footer { background: var(--deep); color: rgba(255,255,255,0.45); padding: 2.2rem 3rem; display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 1rem; }
    .f-logo { font-family: 'Playfair Display', serif; font-size: 1.3rem; font-weight: 900; color: var(--terracotta); font-style: italic; }
    footer p { font-size: 0.82rem; }
    .f-links { display: flex; gap: 1.5rem; }
    .f-links a { color: rgba(255,255,255,0.35); text-decoration: none; font-size: 0.82rem; transition: color 0.2s; }
    .f-links a:hover { color: var(--blush); }

    /* RESPONSIVE */
    @media(max-width:900px){
      nav { padding: 1rem 1.5rem; }
      .nav-links { display: none; }
      #hero { grid-template-columns: 1fr; padding: 6rem 1.5rem 3rem; }
      .hero-visual { display: none; }
      #about { grid-template-columns: 1fr; padding: 4rem 1.5rem; gap: 3rem; }
      .blob-wrap { display: none; }
      #services { padding: 4rem 1.5rem; }
      .grid-3 { grid-template-columns: 1fr 1fr; }
      #contact { grid-template-columns: 1fr; padding: 4rem 1.5rem; gap: 3rem; }
      footer { padding: 2rem 1.5rem; }
    }
    @media(max-width:600px){
      .grid-3 { grid-template-columns: 1fr; }
      #mission { padding: 4rem 1.5rem; }
      .values { gap: 2rem; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">Luna<em>&co</em></div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#mission">Mission</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#contact" class="nav-cta">Work With Us</a>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-text">
    <div class="eyebrow">Modern Art & Design Studio</div>
    <h1>Where <em>art</em> meets<br>bold design</h1>
    <p class="hero-sub">Luna&co is a modern creative studio crafting designs that tell your story — from custom artwork to full brand identities that leave a lasting impression.</p>
    <div class="hero-btns">
      <a href="#services" class="btn-primary">Explore Our Work</a>
      <a href="#contact" class="btn-ghost">Get In Touch</a>
    </div>
  </div>
  <div class="hero-visual">
    <div class="art-grid">
      <div class="art-card">
        <div class="art-block tall ac1">
          <svg viewBox="0 0 100 100" fill="none"><circle cx="50" cy="50" r="34" stroke="white" stroke-width="3"/><circle cx="50" cy="50" r="19" stroke="white" stroke-width="2" stroke-dasharray="5 4"/><line x1="50" y1="12" x2="50" y2="88" stroke="white" stroke-width="2"/><line x1="12" y1="50" x2="88" y2="50" stroke="white" stroke-width="2"/></svg>
        </div>
      </div>
      <div class="art-card">
        <div class="art-block ac2">
          <svg viewBox="0 0 100 100" fill="none"><rect x="18" y="18" width="64" height="64" stroke="white" stroke-width="3" rx="10"/><rect x="34" y="34" width="32" height="32" fill="white" opacity="0.3" rx="5"/></svg>
        </div>
      </div>
      <div class="art-card">
        <div class="art-block ac3">
          <svg viewBox="0 0 100 100" fill="none"><polygon points="50,14 86,80 14,80" stroke="white" stroke-width="3" fill="none"/><polygon points="50,34 70,70 30,70" fill="white" opacity="0.28"/></svg>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div>
    <span class="badge">Our Story</span>
    <h2>Built on <em>creativity</em>,<br>driven by vision</h2>
    <p class="body-text">Luna&co was born from a love of art and a belief that great design can transform any space, brand, or experience. We blend artistic expression with strategic thinking to help creators and businesses stand out.</p>
    <p class="body-text">From licensing original artwork to designing for cafes, restaurants, and libraries — we bring warmth, playfulness, and intention to everything we create.</p>
    <div class="pills">
      <span class="pill">🎨 Original Art</span>
      <span class="pill">✏️ Brand Design</span>
      <span class="pill">☕ Collaborations</span>
      <span class="pill">📦 Print on Demand</span>
      <span class="pill">🎓 Tutorials & Courses</span>
    </div>
  </div>
  <div class="blob-wrap">
    <div class="blob">Luna&co</div>
    <div class="about-stat">
      <strong>∞</strong>
      <span>Creative Possibilities</span>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <div class="sec-head">
    <span class="badge">What We Offer</span>
    <h2>Services that <em>spark</em> something</h2>
    <p>From commissioned artwork to brand strategy, we offer a full suite of creative services designed to elevate your vision.</p>
  </div>
  <div class="grid-3">
    <div class="svc">
      <div class="svc-icon i1">🖼️</div>
      <h3>Custom Artwork</h3>
      <p>Original pieces commissioned for homes, restaurants, cafes, libraries, and events. Every piece tells a story.</p>
      <a href="custom-artwork.html" class="svc-btn">Learn More</a>
    </div>
    <div class="svc">
      <div class="svc-icon i2">🏷️</div>
      <h3>Brand Design</h3>
      <p>Logos, color palettes, packaging, and full identity systems that make your brand truly unforgettable.</p>
      <a href="brand-design.html" class="svc-btn">Learn More</a>
    </div>
    <div class="svc">
      <div class="svc-icon i3">☕</div>
      <h3>Product Collaborations</h3>
      <p>Partner with us to design mugs, merchandise, and more for your café, shop, or venue.</p>
      <a href="product-collaborations.html" class="svc-btn">Learn More</a>
    </div>
    <div class="svc">
      <div class="svc-icon i4">📜</div>
      <h3>Art Licensing</h3>
      <p>License our designs for products, prints, and commercial use — earn alongside Luna&co's creative portfolio.</p>
      <a href="art-licensing.html" class="svc-btn">Learn More</a>
    </div>
    <div class="svc">
      <div class="svc-icon i5">🎓</div>
      <h3>Online Courses</h3>
      <p>Learn design fundamentals and creative techniques through tutorials built for aspiring artists and entrepreneurs.</p>
      <a href="online-courses.html" class="svc-btn">Learn More</a>
    </div>
    <div class="svc">
      <div class="svc-icon i6">🎉</div>
      <h3>Event Art Rental</h3>
      <p>Rent curated artwork for events, pop-ups, and exhibitions to transform any space into a gallery experience.</p>
      <a href="event-art-rental.html" class="svc-btn">Learn More</a>
    </div>
  </div>
</section>

<!-- MISSION -->
<section id="mission">
  <span class="badge">Our Mission</span>
  <h2>Design with <em>purpose</em>,<br>art with heart</h2>
  <p>We believe creativity should be sustainable, joyful, and accessible. Our mission is to empower artists and inspire communities through design that endures.</p>
  <div class="values">
    <div class="val"><span class="val-n">01</span><p>Pursue value-aligned opportunities that feel genuinely right</p></div>
    <div class="val"><span class="val-n">02</span><p>Build innovatively on every past work and lesson</p></div>
    <div class="val"><span class="val-n">03</span><p>Maintain balance for sustainable creative performance</p></div>
    <div class="val"><span class="val-n">04</span><p>Grow with intention through monthly reflection</p></div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-info">
    <span class="badge">Get In Touch</span>
    <h2>Let's create<br><em>something beautiful</em></h2>
    <p>Whether you're looking to commission a piece, collaborate on a product, or just say hello — we'd love to hear from you.</p>
    <div class="c-detail"><div class="c-icon">📧</div><span><a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="98f0fdf4f4f7d8f4edf6f9fbf7b6ebecedfcf1f7">[email&#160;protected]</a></span></div>
    <div class="c-detail"><div class="c-icon">📍</div><span>Available for remote & in-person projects</span></div>
    <div class="c-detail"><div class="c-icon">📅</div><span>Book a free consultation via Calendly</span></div>
  </div>
  <div class="cform">
    <div class="fg">
      <label>Your Name</label>
      <input type="text" placeholder="e.g. Jane Smith" />
    </div>
    <div class="fg">
      <label>Email Address</label>
      <input type="email" placeholder="jane@example.com" />
    </div>
    <div class="fg">
      <label>What are you looking for?</label>
      <select>
        <option value="">Select a service…</option>
        <option>Custom Artwork</option>
        <option>Brand Design</option>
        <option>Product Collaboration</option>
        <option>Art Licensing</option>
        <option>Online Course</option>
        <option>Event Art Rental</option>
      </select>
    </div>
    <div class="fg">
      <label>Tell us about your project</label>
      <textarea placeholder="Share your vision, timeline, and any details…"></textarea>
    </div>
    <button class="fsub">Send Message ✦</button>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="f-logo">Luna&co</div>
  <p>© 2025 Luna&co. A Modern Art & Design Studio.</p>
  <div class="f-links">
    <a href="#abo
