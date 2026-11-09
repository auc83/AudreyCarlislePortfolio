<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#0f0f13">
  <meta name="description" content="Audrey Carlisle's game design portfolio, featuring projects in systems design, interactive storytelling, and player experience.">
  <title>Audrey Carlisle | Game Designer Portfolio</title>
  <style>
    :root {
      color-scheme: dark;
      --page: #0f0f13;
      --surface: #1a1a24;
      --surface-raised: #20202c;
      --border: #30303d;
      --text: #f4f2fb;
      --muted: #b7b5c5;
      --accent: #a995ff;
      --accent-strong: #8068dc;
      --content-width: 1160px;
      --header-height: 76px;
    }

    *,
    *::before,
    *::after {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
      scroll-padding-top: 1.5rem;
    }

    body {
      min-width: 320px;
      margin: 0;
      background: var(--page);
      color: var(--text);
      font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
      font-size: 1rem;
      line-height: 1.7;
    }

    h1,
    h2,
    h3 {
      margin: 0 0 0.75rem;
      color: var(--text);
      line-height: 1.2;
    }

    p {
      margin: 0 0 1rem;
      color: var(--muted);
    }

    a {
      color: var(--accent);
      text-decoration: none;
      transition: color 160ms ease, background-color 160ms ease, border-color 160ms ease;
    }

    a:hover {
      color: #c4b8ff;
    }

    a:focus-visible,
    button:focus-visible,
    input:focus-visible,
    textarea:focus-visible {
      outline: 3px solid var(--accent);
      outline-offset: 3px;
    }

    /* A flexible sticky header keeps navigation visible without covering content. */
    .site-header {
      position: sticky;
      top: 0;
      z-index: 5;
      border-bottom: 1px solid var(--border);
      background: rgb(15 15 19 / 96%);
      backdrop-filter: blur(12px);
    }

    .site-nav {
      display: flex;
      width: min(100% - 3rem, var(--content-width));
      min-height: var(--header-height);
      margin: 0 auto;
      align-items: center;
      justify-content: space-between;
      gap: 1rem 2rem;
      padding: 0.75rem 0;
    }

    .nav-logo {
      flex: 0 0 auto;
      color: var(--text);
      font-size: 1.2rem;
      font-weight: 750;
      letter-spacing: 0.02em;
      white-space: nowrap;
    }

    .nav-links {
      display: flex;
      flex-wrap: wrap;
      justify-content: flex-end;
      gap: 0.35rem 1.35rem;
      margin: 0;
      padding: 0;
      list-style: none;
    }

    .nav-links a {
      display: inline-block;
      padding: 0.3rem 0;
      color: var(--muted);
      font-size: 0.95rem;
      font-weight: 600;
      white-space: nowrap;
    }

    .nav-links a:hover,
    .nav-links a:focus-visible {
      color: var(--accent);
    }

    main section {
      width: min(100% - 3rem, var(--content-width));
      margin: 0 auto;
      padding: 5.5rem 0;
      scroll-margin-top: 1rem;
    }

    .section-title {
      margin-bottom: 2.5rem;
      text-align: center;
      font-size: clamp(1.8rem, 3vw, 2.35rem);
      letter-spacing: -0.025em;
    }

    .section-title::after {
      display: block;
      width: 3.5rem;
      height: 4px;
      margin: 0.8rem auto 0;
      border-radius: 999px;
      background: var(--accent-strong);
      content: "";
    }

    /* Hero */
    #hero {
      display: grid;
      width: 100%;
      min-height: min(760px, 82svh);
      place-items: center;
      padding: 5rem 1.5rem;
      background:
        linear-gradient(110deg, rgb(15 15 19 / 88%), rgb(15 15 19 / 58%)),
        url("https://images.unsplash.com/photo-1550745165-9bc0b252726f?auto=format&fit=crop&w=1600&q=80") center / cover no-repeat;
      text-align: center;
    }

    .hero-content {
      width: min(100%, 760px);
    }

    .hero-content h1 {
      margin-bottom: 1rem;
      font-size: clamp(2.6rem, 8vw, 5rem);
      letter-spacing: 0.035em;
      line-height: 1.05;
      text-transform: uppercase;
    }

    .hero-content p {
      margin-bottom: 2rem;
      color: #d0c5ff;
      font-size: clamp(1.1rem, 2.5vw, 1.45rem);
    }

    .button {
      display: inline-flex;
      min-height: 48px;
      align-items: center;
      justify-content: center;
      border: 1px solid transparent;
      border-radius: 6px;
      background: var(--accent-strong);
      color: #fff;
      cursor: pointer;
      font: inherit;
      font-weight: 700;
      padding: 0.75rem 1.35rem;
    }

    .button:hover {
      background: #6d55c4;
      color: #fff;
    }

    /* Responsive card grids */
    .grid-2,
    .grid-3 {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(min(100%, 290px), 1fr));
      gap: 1.25rem;
    }

    .grid-3 {
      grid-template-columns: repeat(auto-fit, minmax(min(100%, 260px), 1fr));
    }

    .block-card {
      min-width: 0;
      padding: clamp(1.25rem, 3vw, 2rem);
      border: 1px solid var(--border);
      border-radius: 12px;
      background: var(--surface);
      transition: transform 180ms ease, border-color 180ms ease, background-color 180ms ease;
    }

    .block-card:hover {
      transform: translateY(-3px);
      border-color: var(--accent-strong);
      background: var(--surface-raised);
    }

    .block-card h3 {
      font-size: 1.15rem;
    }

    .block-card p:last-child {
      margin-bottom: 0;
    }

    .project-card {
      display: flex;
      min-height: 260px;
      flex-direction: column;
      align-items: flex-start;
      justify-content: space-between;
      gap: 1.5rem;
    }

    .project-tag {
      display: inline-block;
      margin-bottom: 1rem;
      border: 1px solid rgb(169 149 255 / 28%);
      border-radius: 999px;
      background: rgb(169 149 255 / 10%);
      color: #c4b8ff;
      font-size: 0.78rem;
      font-weight: 700;
      letter-spacing: 0.03em;
      padding: 0.25rem 0.7rem;
    }

    .project-link {
      font-weight: 700;
    }

    /* Contact */
    .contact-card {
      width: min(100%, 680px);
      margin: 0 auto;
    }

    .form-group {
      margin-bottom: 1.25rem;
    }

    .form-group label {
      display: block;
      margin-bottom: 0.45rem;
      color: var(--text);
      font-weight: 600;
    }

    .form-group input,
    .form-group textarea {
      display: block;
      width: 100%;
      min-height: 48px;
      border: 1px solid var(--border);
      border-radius: 6px;
      background: #121219;
      color: var(--text);
      font: inherit;
      padding: 0.75rem 0.85rem;
    }

    .form-group textarea {
      min-height: 150px;
      resize: vertical;
    }

    .form-group input::placeholder,
    .form-group textarea::placeholder {
      color: #858393;
    }

    .contact-card .button {
      width: 100%;
      border: 0;
    }

    footer {
      border-top: 1px solid var(--border);
      background: #09090c;
      padding: 1.75rem 1.5rem;
      text-align: center;
    }

    footer p {
      margin: 0;
      font-size: 0.9rem;
    }

    @media (max-width: 760px) {
      .site-nav {
        width: min(100% - 2rem, var(--content-width));
        flex-direction: column;
        justify-content: center;
        gap: 0.25rem;
        padding: 0.65rem 0;
      }

      .nav-links {
        justify-content: center;
        column-gap: clamp(0.7rem, 3vw, 1.25rem);
      }

      .nav-links a {
        font-size: 0.88rem;
      }

      main section {
        width: min(100% - 2rem, var(--content-width));
        padding: 4rem 0;
      }

      #hero {
        min-height: 70svh;
      }
    }

    @media (max-width: 420px) {
      .nav-logo {
        font-size: 1.1rem;
      }

      .nav-links {
        column-gap: 0.8rem;
        row-gap: 0.1rem;
      }

      .nav-links a {
        font-size: 0.82rem;
      }

      main section {
        padding: 3.25rem 0;
      }

      .project-card {
        min-height: 0;
      }
    }

    @media (prefers-reduced-motion: reduce) {
      html {
        scroll-behavior: auto;
      }

      *,
      *::before,
      *::after {
        transition-duration: 0.01ms !important;
      }

      .block-card:hover {
        transform: none;
      }
    }
  </style>
</head>
<body>
  <header class="site-header">
    <nav class="site-nav" aria-label="Main navigation">
      <a class="nav-logo" href="#hero">Audrey Carlisle</a>
      <ul class="nav-links">
        <li><a href="#hero">Home</a></li>
        <li><a href="#about">About &amp; Field</a></li>
        <li><a href="#hobbies">Interests</a></li>
        <li><a href="#portfolio">Portfolio</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <section id="hero" aria-labelledby="hero-title">
    <div class="hero-content">
      <h1 id="hero-title">Audrey Carlisle</h1>
      <p>Game Designer &amp; Interactive Worldbuilder</p>
      <a href="#portfolio" class="button">View My Work</a>
    </div>
  </section>

  <main>
    <section id="about" aria-labelledby="about-title">
      <h2 class="section-title" id="about-title">Field of Study</h2>
      <div class="grid-2">
        <article class="block-card">
          <h3>B.S. in Digital Narrative &amp; Game Design</h3>
          <p>University of Pittsburgh</p>
          <p>Focusing on environmental storytelling, mechanics balance, systems design, and player psychology. Specialized in creating immersive level layouts and modular game logic using Unreal Engine.</p>
        </article>
        <article class="block-card">
          <h3>Core Competencies</h3>
          <p>Systems Design &amp; Rules Balancing • Level Design &amp; Scripting • Technical Documentation • Rapid Prototyping • Player Experience (UX) Research</p>
        </article>
      </div>
    </section>

    <section id="hobbies" aria-labelledby="hobbies-title">
      <h2 class="section-title" id="hobbies-title">Relevant Hobbies &amp; Interests</h2>
      <div class="grid-3">
        <article class="block-card">
          <h3>Tabletop RPG Campaign Director</h3>
          <p>Designing custom mechanics, modules, and narrative arcs for tabletop sessions. Enhances real-time pacing, emergent storytelling, and systems balance.</p>
        </article>
        <article class="block-card">
          <h3>Retro Arcade Hardware Restoration</h3>
          <p>Rebuilding vintage cabinet controls and boards. Deepens appreciation for arcade design history and tactile physical-to-digital input responsiveness.</p>
        </article>
        <article class="block-card">
          <h3>3D Environment Sculpting</h3>
          <p>Creating low-poly assets and modular environment sets during game jams to rapidly bring world ideas from sketch to prototype.</p>
        </article>
      </div>
    </section>

    <section id="portfolio" aria-labelledby="portfolio-title">
      <h2 class="section-title" id="portfolio-title">Project Portfolio</h2>
      <div class="grid-3">
        <article class="block-card project-card">
          <div>
            <span class="project-tag">Game Design Document</span>
            <h3>Project Proposal</h3>
            <p>Comprehensive design document proposing <em>Echoes of Aether</em>, a system-driven cooperative puzzle game.</p>
          </div>
          <a class="project-link" href="#" target="_blank" rel="noopener noreferrer">View Proposal (PDF) &rarr;</a>
        </article>

        <article class="block-card project-card">
          <div>
            <span class="project-tag">VR Documentation</span>
            <h3>VR Safety &amp; Play Guidelines</h3>
            <p>Standard operating protocols and ergonomic risk mitigation strategies for room-scale VR game testing.</p>
          </div>
          <a class="project-link" href="#" target="_blank" rel="noopener noreferrer">View Safety Doc (PDF) &rarr;</a>
        </article>

        <article class="block-card project-card">
          <div>
            <span class="project-tag">Data Visualization</span>
            <h3>Mechanics Breakdown Infographic</h3>
            <p>Visual map analyzing player retention loops, difficulty scaling, and risk/reward dynamics in roguelikes.</p>
          </div>
          <a class="project-link" href="#" target="_blank" rel="noopener noreferrer">View Infographic (PNG) &rarr;</a>
        </article>

        <article class="block-card project-card">
          <div>
            <span class="project-tag">Playable Demo</span>
            <h3>Main Project: Celestial Run</h3>
            <p>A playable 3D platformer prototype demonstrating momentum-based movement and dynamic lighting traps.</p>
          </div>
          <a class="project-link" href="#" target="_blank" rel="noopener noreferrer">Play Build / Watch Demo &rarr;</a>
        </article>

        <article class="block-card project-card">
          <div>
            <span class="project-tag">UX Research</span>
            <h3>Usability Study &amp; Report</h3>
            <p>Playtesting analytics, heatmap observations, and UX improvement recommendations based on 15 user sessions.</p>
          </div>
          <a class="project-link" href="#" target="_blank" rel="noopener noreferrer">View Usability Study (PDF) &rarr;</a>
        </article>

        <article class="block-card project-card">
          <div>
            <span class="project-tag">Presentation</span>
            <h3>Project Pitch &amp; Oral Presentation</h3>
            <p>Slide deck and video recording of the final project pitch delivered to industry faculty reviewers.</p>
          </div>
          <a class="project-link" href="#" target="_blank" rel="noopener noreferrer">Watch Presentation (Video) &rarr;</a>
        </article>
      </div>
    </section>

    <section id="contact" aria-labelledby="contact-title">
      <h2 class="section-title" id="contact-title">Contact Me</h2>
      <div class="block-card contact-card">
        <form action="#" method="POST">
          <div class="form-group">
            <label for="name">Name</label>
            <input type="text" id="name" name="name" placeholder="Your Name" autocomplete="name" required>
          </div>
          <div class="form-group">
            <label for="email">Email</label>
            <input type="email" id="email" name="email" placeholder="Your Email Address" autocomplete="email" required>
          </div>
          <div class="form-group">
            <label for="message">Message</label>
            <textarea id="message" name="message" rows="5" placeholder="Your message or collaboration request..." required></textarea>
          </div>
          <button type="submit" class="button">Send Message</button>
        </form>
      </div>
    </section>
  </main>

  <footer>
    <p>&copy; 2026 Audrey Carlisle | Game Designer Portfolio | University of Pittsburgh</p>
  </footer>
</body>
</html>
