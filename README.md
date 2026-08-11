# design.org
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Vaish — Climate Resilience & Cultural Conservation</title>
  <meta name="description" content="Consultant and researcher working at the intersection of urban resilience, climate justice, and heritage cultural conservation.">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;1,300;1,400&family=Inter:wght@300;400;500&family=Space+Mono&display=swap" rel="stylesheet">

  <style>
    /* ─── TOKENS ─────────────────────────────────────── */
    :root {
      --green:       #1C3B2E;
      --green-mid:   #2D5C44;
      --green-light: #E9EFE7;
      --umber:       #8B6F47;
      --umber-light: #F0E9DF;
      --bg:          #F7F6F2;
      --ink:         #141412;
      --ink-mid:     #4A4940;
      --ink-light:   #8C8B84;
      --white:       #FFFFFF;
      --thread-w:    2px;
      --thread-x:    44px;
      --max:         1080px;
      --pad-x:       clamp(1.5rem, 5vw, 5rem);
    }

    /* ─── RESET ──────────────────────────────────────── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body {
      background: var(--bg);
      color: var(--ink);
      font-family: 'Inter', sans-serif;
      font-weight: 300;
      font-size: 16px;
      line-height: 1.7;
      -webkit-font-smoothing: antialiased;
    }
    a { color: inherit; text-decoration: none; }
    img { display: block; max-width: 100%; }

    /* ─── THREAD LINE ─────────────────────────────────── */
    body::before {
      content: '';
      position: fixed;
      top: 0; left: var(--thread-x);
      width: var(--thread-w);
      height: 100vh;
      background: linear-gradient(to bottom, transparent 0%, var(--green) 8%, var(--green) 92%, transparent 100%);
      opacity: 0.18;
      pointer-events: none;
      z-index: 0;
    }

    /* ─── NAV ─────────────────────────────────────────── */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1.25rem var(--pad-x);
      background: rgba(247,246,242,0.92);
      backdrop-filter: blur(8px);
      -webkit-backdrop-filter: blur(8px);
    }

    .nav-name {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.15rem;
      font-weight: 500;
      letter-spacing: 0.02em;
      color: var(--green);
      padding-left: calc(var(--thread-x) + 1rem);
    }

    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

    .nav-links a {
      font-family: 'Space Mono', monospace;
      font-size: 0.68rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--ink-mid);
      transition: color 0.2s;
    }

    .nav-links a:hover { color: var(--green); }

    /* ─── SECTIONS ────────────────────────────────────── */
    section {
      position: relative;
      padding: 6rem var(--pad-x);
      max-width: var(--max);
      margin: 0 auto;
    }

    .eyebrow {
      font-family: 'Space Mono', monospace;
      font-size: 0.65rem;
      letter-spacing: 0.14em;
      text-transform: uppercase;
      color: var(--umber);
      margin-bottom: 1.25rem;
    }

    /* ─── HERO ────────────────────────────────────────── */
    #hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding-top: 7rem;
      padding-left: calc(var(--thread-x) + 2rem + var(--pad-x));
    }

    .hero-thesis {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2.4rem, 5.5vw, 4.2rem);
      font-weight: 300;
      line-height: 1.15;
      letter-spacing: -0.01em;
      color: var(--ink);
      max-width: 820px;
      margin-bottom: 2rem;
    }

    .hero-thesis em {
      font-style: italic;
      color: var(--green);
    }

    .hero-meta {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem 2rem;
      margin-bottom: 2.5rem;
    }

    .hero-meta span {
      font-family: 'Space Mono', monospace;
      font-size: 0.7rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: var(--ink-light);
    }

    .hero-cta {
      display: inline-flex;
      align-items: center;
      gap: 0.6rem;
      background: var(--green);
      color: var(--white);
      padding: 0.85rem 1.75rem;
      font-family: 'Inter', sans-serif;
      font-size: 0.82rem;
      font-weight: 500;
      letter-spacing: 0.04em;
      border-radius: 2px;
      transition: background 0.2s;
      width: fit-content;
    }

    .hero-cta:hover { background: var(--green-mid); }

    .scroll-hint {
      position: absolute;
      bottom: 2.5rem;
      left: calc(var(--thread-x) + 2rem + var(--pad-x));
      font-family: 'Space Mono', monospace;
      font-size: 0.62rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--ink-light);
      display: flex;
      align-items: center;
      gap: 0.75rem;
    }

    .scroll-hint::before {
      content: '';
      display: block;
      width: 1px;
      height: 40px;
      background: var(--green);
      opacity: 0.4;
      animation: scrollpulse 2s ease-in-out infinite;
    }

    @keyframes scrollpulse {
      0%, 100% { opacity: 0.2; }
      50% { opacity: 0.7; }
    }

    /* ─── DIVIDER ─────────────────────────────────────── */
    .divider {
      width: 100%;
      height: 1px;
      background: linear-gradient(to right, var(--green-light), transparent);
      margin: 0 auto;
      max-width: var(--max);
      padding: 0 var(--pad-x);
    }

    /* ─── ABOUT ───────────────────────────────────────── */
    #about {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: start;
    }

    .about-left p {
      font-size: 1.05rem;
      line-height: 1.8;
      color: var(--ink-mid);
      margin-bottom: 1.25rem;
    }

    .about-left p strong {
      color: var(--ink);
      font-weight: 500;
    }

    .about-right {
      padding-top: 2.25rem;
    }

    .fact-group {
      margin-bottom: 2rem;
    }

    .fact-label {
      font-family: 'Space Mono', monospace;
      font-size: 0.62rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--umber);
      margin-bottom: 0.4rem;
    }

    .fact-value {
      font-size: 0.92rem;
      color: var(--ink-mid);
      line-height: 1.6;
    }

    /* ─── CONSULTING ──────────────────────────────────── */
    #consulting { background: transparent; }

    .consulting-intro {
      max-width: 620px;
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.45rem;
      font-weight: 300;
      line-height: 1.5;
      color: var(--ink);
      margin-bottom: 3.5rem;
      font-style: italic;
    }

    .offer-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1.5px;
      background: var(--green-light);
      border: 1.5px solid var(--green-light);
      border-radius: 4px;
      overflow: hidden;
    }

    .offer-card {
      background: var(--bg);
      padding: 2.25rem 1.75rem;
      transition: background 0.25s;
    }

    .offer-card:hover { background: var(--white); }

    .offer-num {
      font-family: 'Cormorant Garamond', serif;
      font-size: 2.8rem;
      font-weight: 300;
      color: var(--green-light);
      line-height: 1;
      margin-bottom: 1rem;
      user-select: none;
    }

    .offer-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.3rem;
      font-weight: 500;
      color: var(--green);
      margin-bottom: 0.75rem;
      line-height: 1.3;
    }

    .offer-desc {
      font-size: 0.88rem;
      color: var(--ink-mid);
      line-height: 1.75;
      margin-bottom: 1.25rem;
    }

    .offer-deliverable {
      font-family: 'Space Mono', monospace;
      font-size: 0.62rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: var(--umber);
    }

    .offer-deliverable span {
      display: block;
      margin-top: 0.2rem;
      color: var(--ink-mid);
      font-family: 'Inter', sans-serif;
      font-size: 0.82rem;
      font-style: italic;
      letter-spacing: 0;
      text-transform: none;
    }

    /* ─── EXPERIENCE ──────────────────────────────────── */
    #experience { }

    .timeline {
      display: flex;
      flex-direction: column;
      gap: 0;
    }

    .timeline-item {
      display: grid;
      grid-template-columns: 160px 1fr;
      gap: 2rem;
      padding: 2rem 0;
      border-bottom: 1px solid var(--green-light);
      position: relative;
    }

    .timeline-item:last-child { border-bottom: none; }

    .timeline-period {
      font-family: 'Space Mono', monospace;
      font-size: 0.68rem;
      letter-spacing: 0.06em;
      color: var(--ink-light);
      padding-top: 0.2rem;
      line-height: 1.6;
    }

    .timeline-role {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.15rem;
      font-weight: 500;
      color: var(--ink);
      margin-bottom: 0.2rem;
    }

    .timeline-org {
      font-size: 0.85rem;
      color: var(--umber);
      margin-bottom: 0.6rem;
      font-weight: 400;
    }

    .timeline-detail {
      font-size: 0.88rem;
      color: var(--ink-mid);
      line-height: 1.75;
    }

    /* ─── WRITING ─────────────────────────────────────── */
    #writing {
      background: transparent;
    }

    .writing-intro {
      max-width: 580px;
      font-size: 0.95rem;
      color: var(--ink-mid);
      margin-bottom: 2.5rem;
      line-height: 1.8;
    }

    .writing-cta {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      border: 1px solid var(--green);
      color: var(--green);
      padding: 0.75rem 1.5rem;
      font-size: 0.82rem;
      font-weight: 500;
      border-radius: 2px;
      transition: all 0.2s;
    }

    .writing-cta:hover {
      background: var(--green);
      color: var(--white);
    }

    .topic-pills {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin-bottom: 2rem;
    }

    .pill {
      display: inline-block;
      padding: 0.35rem 0.9rem;
      background: var(--green-light);
      color: var(--green);
      font-size: 0.78rem;
      border-radius: 20px;
      font-weight: 400;
    }

    /* ─── CONTACT ─────────────────────────────────────── */
    #contact {
      background: var(--green);
      max-width: 100%;
      padding: 6rem var(--pad-x);
    }

    #contact > * {
      max-width: var(--max);
      margin-left: auto;
      margin-right: auto;
    }

    .contact-inner {
      max-width: var(--max);
      margin: 0 auto;
    }

    .contact-heading {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2rem, 4vw, 3.2rem);
      font-weight: 300;
      color: var(--white);
      line-height: 1.2;
      margin-bottom: 1.25rem;
      max-width: 640px;
    }

    .contact-sub {
      font-size: 0.92rem;
      color: rgba(255,255,255,0.65);
      margin-bottom: 2.5rem;
      max-width: 480px;
    }

    .contact-form {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1rem;
      max-width: 680px;
    }

    .contact-form .full { grid-column: 1 / -1; }

    .contact-form input,
    .contact-form textarea,
    .contact-form select {
      width: 100%;
      background: rgba(255,255,255,0.08);
      border: 1px solid rgba(255,255,255,0.2);
      border-radius: 2px;
      padding: 0.85rem 1rem;
      font-family: 'Inter', sans-serif;
      font-size: 0.88rem;
      color: var(--white);
      outline: none;
      transition: border-color 0.2s;
      -webkit-appearance: none;
    }

    .contact-form input::placeholder,
    .contact-form textarea::placeholder {
      color: rgba(255,255,255,0.35);
    }

    .contact-form input:focus,
    .contact-form textarea:focus {
      border-color: rgba(255,255,255,0.55);
    }

    .contact-form select {
      color: rgba(255,255,255,0.55);
      cursor: pointer;
    }

    .contact-form select option {
      background: var(--green);
      color: var(--white);
    }

    .contact-form textarea { resize: vertical; min-height: 120px; }

    .contact-submit {
      background: var(--white);
      color: var(--green);
      border: none;
      padding: 0.9rem 2rem;
      font-family: 'Inter', sans-serif;
      font-size: 0.88rem;
      font-weight: 500;
      border-radius: 2px;
      cursor: pointer;
      transition: opacity 0.2s;
      letter-spacing: 0.03em;
    }

    .contact-submit:hover { opacity: 0.88; }

    /* ─── FOOTER ──────────────────────────────────────── */
    footer {
      background: #111C17;
      padding: 2rem var(--pad-x);
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .footer-name {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1rem;
      color: rgba(255,255,255,0.5);
    }

    .footer-links {
      display: flex;
      gap: 1.5rem;
      list-style: none;
    }

    .footer-links a {
      font-family: 'Space Mono', monospace;
      font-size: 0.62rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: rgba(255,255,255,0.35);
      transition: color 0.2s;
    }

    .footer-links a:hover { color: rgba(255,255,255,0.7); }

    /* ─── RESPONSIVE ──────────────────────────────────── */
    @media (max-width: 820px) {
      :root { --thread-x: 20px; }

      nav { padding: 1rem 1.5rem; }
      .nav-name { padding-left: calc(var(--thread-x) + 0.75rem); }
      .nav-links { gap: 1.25rem; }

      #hero { padding-left: calc(var(--thread-x) + 1rem + 1.5rem); }
      .scroll-hint { left: calc(var(--thread-x) + 1rem + 1.5rem); }

      #about { grid-template-columns: 1fr; gap: 2rem; }
      .offer-grid { grid-template-columns: 1fr; }
      .timeline-item { grid-template-columns: 1fr; gap: 0.25rem; }
      .contact-form { grid-template-columns: 1fr; }
    }

    @media (max-width: 520px) {
      .nav-links { display: none; }
      .hero-thesis { font-size: 2rem; }
    }

    /* ─── SECTION TITLE ───────────────────────────────── */
    .section-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 2.2rem;
      font-weight: 300;
      color: var(--ink);
      margin-bottom: 2.5rem;
      line-height: 1.2;
    }
  </style>
</head>

<body>

  <!-- NAV -->
  <nav>
    <span class="nav-name">Vaish</span>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#consulting">Consulting</a></li>
      <li><a href="#experience">Experience</a></li>
      <li><a href="#writing">Writing</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section id="hero">
    <p class="eyebrow">Urban Resilience · Climate Justice · Cultural Conservation</p>
    <h1 class="hero-thesis">
      The systems failing our cities<br>
      are the same systems erasing<br>
      <em>centuries of living knowledge.</em>
    </h1>
    <div class="hero-meta">
      <span>Vaish</span>
      <span>Brooklyn, NY</span>
      <span>Available for consulting</span>
    </div>
    <a href="#contact" class="hero-cta">
      Work with me
      <svg width="14" height="14" viewBox="0 0 14 14" fill="none"><path d="M2 7h10M7 2l5 5-5 5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>
    </a>
    <div class="scroll-hint">Scroll</div>
  </section>

  <div class="divider"></div>

  <!-- ABOUT -->
  <section id="about">
    <div class="about-left">
      <p class="eyebrow">About</p>
      <p>I work at the intersection of <strong>urban resilience, climate justice, and cultural conservation</strong> — connecting the physical, ecological, and human dimensions of how communities survive and adapt.</p>
      <p>My background spans urban design, environmental conservation, UN intergovernmental processes, and youth education. What runs through all of it is the same question: <strong>who gets to shape the conditions they live in?</strong></p>
      <p>Today I work with organizations designing resilience strategies, programs, and engagements that hold both the urgency of the climate crisis and the depth of the communities navigating it — including the artisan communities whose knowledge systems are among the most sophisticated climate adaptations ever developed.</p>
    </div>
    <div class="about-right">
      <div class="fact-group">
        <p class="fact-label">Education</p>
        <p class="fact-value">MA Environmental Conservation Education<br><em>New York University, 2024</em></p>
        <p class="fact-value" style="margin-top:0.5rem;">Bachelor of Urban Design<br><em>CEPT University, 2021</em></p>
      </div>
      <div class="fact-group">
        <p class="fact-label">International engagement</p>
        <p class="fact-value">UN Youth Delegate — ECOSOC, HLPF, CSW, FfD4, BBNJ, UNGA 80th</p>
      </div>
      <div class="fact-group">
        <p class="fact-label">Climate networks</p>
        <p class="fact-value">UNFCCC YOUNGO — Finance & Markets, Human Rights, Climate Security</p>
      </div>
      <div class="fact-group">
        <p class="fact-label">Based in</p>
        <p class="fact-value">Brooklyn, New York</p>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- CONSULTING -->
  <section id="consulting">
    <p class="eyebrow">Consulting</p>
    <p class="consulting-intro">I help organizations build resilience strategies that work with communities — not just for them.</p>

    <div class="offer-grid">
      <div class="offer-card">
        <div class="offer-num">I</div>
        <h3 class="offer-title">Resilience Strategy</h3>
        <p class="offer-desc">Urban resilience planning and heritage cultural conservation for city agencies, municipalities, and planning firms navigating the intersection of climate adaptation and community identity.</p>
        <p class="offer-deliverable">Deliverable
          <span>Strategy frameworks, research reports, policy recommendations</span>
        </p>
      </div>
      <div class="offer-card">
        <div class="offer-num">II</div>
        <h3 class="offer-title">Program Design</h3>
        <p class="offer-desc">Climate justice program design and sustainability curriculum development for nonprofits, foundations, schools, and UN agencies. Grounded in participatory methods and community-led learning.</p>
        <p class="offer-deliverable">Deliverable
          <span>Programs, curricula, facilitation guides, evaluation frameworks</span>
        </p>
      </div>
      <div class="offer-card">
        <div class="offer-num">III</div>
        <h3 class="offer-title">Community Engagement</h3>
        <p class="offer-desc">Facilitation, stakeholder engagement, and participatory design for clients who need someone to work directly with communities — translating between policy rooms and lived experience.</p>
        <p class="offer-deliverable">Deliverable
          <span>Engagement processes, stakeholder reports, workshop outputs</span>
        </p>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- EXPERIENCE -->
  <section id="experience">
    <p class="eyebrow">Experience</p>
    <h2 class="section-title">Where this work comes from</h2>

    <div class="timeline">
      <div class="timeline-item">
        <div class="timeline-period">2023 — Present</div>
        <div>
          <p class="timeline-role">Youth Engagement Specialist</p>
          <p class="timeline-org">Global Kids, New York</p>
          <p class="timeline-detail">Designing and leading climate resiliency programs for NYC public school students — integrating media literacy, climate justice frameworks, and SDG facilitation into youth-led learning.</p>
        </div>
      </div>
      <div class="timeline-item">
        <div class="timeline-period">2022 — 2023</div>
        <div>
          <p class="timeline-role">Program Support Officer</p>
          <p class="timeline-org">UN Major Group for Children and Youth (MGCY)</p>
          <p class="timeline-detail">Coordinated operations across 80+ global youth networks and managed the ECOSOC Youth Forum — working at the intersection of youth participation, intergovernmental processes, and sustainable development policy.</p>
        </div>
      </div>
      <div class="timeline-item">
        <div class="timeline-period">2021 — 2022</div>
        <div>
          <p class="timeline-role">Teaching Assistant — Urban Design</p>
          <p class="timeline-org">CEPT University</p>
          <p class="timeline-detail">Supported graduate urban design students through research, studio critique, and program development in the department where I completed my undergraduate degree.</p>
        </div>
      </div>
      <div class="timeline-item">
        <div class="timeline-period">Ongoing</div>
        <div>
          <p class="timeline-role">UN Youth Delegate</p>
          <p class="timeline-org">ECOSOC · HLPF · CSW · FfD4 · BBNJ · UNGA 80th</p>
          <p class="timeline-detail">Participating in intergovernmental processes as a youth delegate — advocating for climate justice, cultural rights, and intergenerational equity in international policy frameworks.</p>
        </div>
      </div>
    </div>
  </section>

  <div class="divider"></div>

  <!-- WRITING -->
  <section id="writing">
    <p class="eyebrow">Writing & Research</p>
    <h2 class="section-title">Ideas in progress</h2>
    <p class="writing-intro">I write about the structural failures behind cultural erasure — how economic systems, urban policy, and climate displacement are destroying the conditions artisan communities need to survive, and what it would take to change that.</p>
    <div class="topic-pills">
      <span class="pill">Endangered heritage arts</span>
      <span class="pill">Climate displacement</span>
      <span class="pill">Circular economies</span>
      <span class="pill">Urban informality</span>
      <span class="pill">Artisan livelihoods</span>
      <span class="pill">Cultural conservation</span>
    </div>
    <a href="#" class="writing-cta" target="_blank" rel="noopener">
      Read on Substack
      <svg width="13" height="13" viewBox="0 0 13 13" fill="none"><path d="M1.5 11.5l10-10M3.5 1.5h8v8" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/></svg>
    </a>
  </section>

  <!-- CONTACT -->
  <div id="contact" style="background:var(--green); padding: 6rem var(--pad-x);">
    <div class="contact-inner">
      <h2 class="contact-heading">Let's work together on what matters.</h2>
      <p class="contact-sub">Whether you're designing a resilience strategy, building a climate program, or navigating a complex community engagement — reach out.</p>

      <form class="contact-form" action="mailto:your@email.com" method="GET" enctype="text/plain">
        <input type="text" name="name" placeholder="Your name" required>
        <input type="email" name="email" placeholder="Your email" required>
        <select name="type" class="full">
          <option value="" disabled selected>What are you working on?</option>
          <option>Resilience Strategy</option>
          <option>Program Design</option>
          <option>Community Engagement</option>
          <option>Research Collaboration</option>
          <option>Something else</option>
        </select>
        <textarea name="message" class="full" placeholder="Tell me about your project..." required></textarea>
        <div class="full">
          <button type="submit" class="contact-submit">Send message →</button>
        </div>
      </form>
    </div>
  </div>

  <!-- FOOTER -->
  <footer>
    <span class="footer-name">Vaish — Brooklyn, NY</span>
    <ul class="footer-links">
      <li><a href="https://linkedin.com" target="_blank">LinkedIn</a></li>
      <li><a href="#" target="_blank">Substack</a></li>
      <li><a href="mailto:your@email.com">Email</a></li>
    </ul>
  </footer>

</body>
</html>
