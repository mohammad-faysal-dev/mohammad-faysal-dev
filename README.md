<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Mohammad Faysal — Developer & AI Engineer</title>
  <meta name="description" content="Full-Stack Developer & AI Engineer. MERN Stack Specialist."/>
  <link rel="preconnect" href="https://fonts.googleapis.com"/>
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;1,9..40,300&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --lime:    #c6f135;
      --lime-dk: #a8d41a;
      --ink:     #0f0f0f;
      --ink-2:   #1a1a1a;
      --ink-3:   #2a2a2a;
      --white:   #f5f5f0;
      --muted:   #888;
      --card-bg: #161616;
      --r:       18px;
    }
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--ink);
      color: var(--white);
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* ── NOISE OVERLAY ── */
    body::before {
      content: '';
      position: fixed; inset: 0; z-index: 0; pointer-events: none;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
      background-size: 200px;
      opacity: 0.5;
    }

    /* ── LAYOUT ── */
    .wrapper {
      position: relative; z-index: 1;
      max-width: 1080px;
      margin: 0 auto;
      padding: 48px 24px 80px;
    }

    /* ── NAV ── */
    nav {
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 0 48px;
    }
    .nav-logo {
      font-family: 'Syne', sans-serif;
      font-weight: 800; font-size: 1.1rem;
      letter-spacing: -0.02em;
    }
    .nav-logo span { color: var(--lime); }
    .nav-status {
      display: flex; align-items: center; gap: 8px;
      font-size: 0.8rem; color: var(--muted);
    }
    .nav-status-dot {
      width: 8px; height: 8px; border-radius: 50%;
      background: var(--lime);
      box-shadow: 0 0 10px var(--lime);
      animation: blink 2s ease-in-out infinite;
    }
    @keyframes blink { 0%,100%{opacity:1;} 50%{opacity:0.3;} }

    /* ── BENTO GRID ── */
    .bento {
      display: grid;
      grid-template-columns: repeat(12, 1fr);
      grid-auto-rows: 90px;
      gap: 14px;
    }

    .cell {
      background: var(--card-bg);
      border-radius: var(--r);
      border: 1px solid #242424;
      overflow: hidden;
      transition: border-color 0.3s, transform 0.3s;
    }
    .cell:hover { border-color: #3a3a3a; transform: translateY(-2px); }

    /* spans */
    .c-hero    { grid-column: span 8; grid-row: span 4; }
    .c-status  { grid-column: span 4; grid-row: span 2; }
    .c-gif     { grid-column: span 4; grid-row: span 2; }
    .c-fe      { grid-column: span 4; grid-row: span 3; }
    .c-be      { grid-column: span 4; grid-row: span 3; }
    .c-ai      { grid-column: span 4; grid-row: span 3; }
    .c-tools   { grid-column: span 6; grid-row: span 2; }
    .c-streak  { grid-column: span 6; grid-row: span 2; }
    .c-quote   { grid-column: span 12; grid-row: span 2; }

    /* ── HERO CELL ── */
    .c-hero {
      padding: 48px 52px;
      display: flex; flex-direction: column; justify-content: center;
      background: linear-gradient(135deg, #161616 0%, #1e1e1e 100%);
      position: relative; overflow: hidden;
    }
    .c-hero::before {
      content: '';
      position: absolute; top: -60px; right: -60px;
      width: 300px; height: 300px; border-radius: 50%;
      background: radial-gradient(circle, rgba(198,241,53,0.08) 0%, transparent 70%);
      pointer-events: none;
    }
    .hero-eyebrow {
      display: inline-flex; align-items: center; gap: 8px;
      font-size: 0.75rem; font-weight: 500; letter-spacing: 0.15em;
      text-transform: uppercase; color: var(--lime);
      margin-bottom: 20px;
    }
    .hero-eyebrow::before {
      content: ''; width: 24px; height: 2px; background: var(--lime); border-radius: 2px;
    }
    .hero-name {
      font-family: 'Syne', sans-serif;
      font-size: 3.8rem; font-weight: 800;
      line-height: 1.0; letter-spacing: -0.03em;
      color: var(--white);
      margin-bottom: 10px;
    }
    .hero-name .line2 { color: var(--lime); }
    .hero-role {
      font-size: 1rem; color: var(--muted);
      font-weight: 300; margin-bottom: 32px; line-height: 1.6;
    }
    .hero-role em { color: var(--white); font-style: normal; font-weight: 500; }
    .hero-links { display: flex; gap: 10px; flex-wrap: wrap; }
    .btn {
      display: inline-flex; align-items: center; gap: 7px;
      text-decoration: none;
      font-size: 0.82rem; font-weight: 500;
      padding: 10px 20px; border-radius: 50px;
      transition: all 0.25s;
    }
    .btn-lime {
      background: var(--lime); color: var(--ink);
    }
    .btn-lime:hover { background: var(--lime-dk); transform: translateY(-1px); box-shadow: 0 6px 20px rgba(198,241,53,0.35); }
    .btn-ghost {
      background: transparent; color: var(--white);
      border: 1px solid #333;
    }
    .btn-ghost:hover { border-color: var(--lime); color: var(--lime); transform: translateY(-1px); }

    /* ── STATUS CELL ── */
    .c-status {
      padding: 28px;
      display: flex; flex-direction: column; justify-content: space-between;
    }
    .status-label {
      font-size: 0.7rem; letter-spacing: 0.12em; text-transform: uppercase;
      color: var(--muted); margin-bottom: 12px;
    }
    .status-value {
      font-family: 'Syne', sans-serif;
      font-size: 1.15rem; font-weight: 700; color: var(--white);
    }
    .status-chips { display: flex; flex-wrap: wrap; gap: 6px; margin-top: auto; }
    .chip {
      font-size: 0.72rem; font-weight: 500;
      padding: 5px 12px; border-radius: 50px;
      background: #222; border: 1px solid #333; color: #ccc;
    }
    .chip.lime { background: rgba(198,241,53,0.1); border-color: rgba(198,241,53,0.3); color: var(--lime); }

    /* ── GIF CELL ── */
    .c-gif { padding: 0; }
    .c-gif img { width: 100%; height: 100%; object-fit: cover; display: block; filter: saturate(0.8) contrast(1.1); }

    /* ── TECH CELLS ── */
    .tech-cell {
      padding: 26px; display: flex; flex-direction: column;
    }
    .tech-cell-title {
      display: flex; align-items: center; gap: 8px;
      font-family: 'Syne', sans-serif;
      font-size: 0.9rem; font-weight: 700;
      color: var(--white); margin-bottom: 18px;
    }
    .tech-cell-emoji { font-size: 1.1rem; }
    .icon-row { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 16px; }
    .icon-wrap {
      width: 38px; height: 38px; border-radius: 10px;
      background: #202020; border: 1px solid #2e2e2e;
      display: flex; align-items: center; justify-content: center;
      overflow: hidden; transition: border-color 0.2s, transform 0.2s;
    }
    .icon-wrap:hover { border-color: var(--lime); transform: scale(1.1); }
    .icon-wrap img { width: 26px; height: 26px; }
    .tag-row { display: flex; flex-wrap: wrap; gap: 6px; margin-top: auto; }
    .tag {
      font-size: 0.68rem; font-weight: 500;
      padding: 4px 10px; border-radius: 50px;
      background: #1e1e1e; border: 1px solid #2e2e2e; color: var(--muted);
      font-family: 'DM Mono', monospace;
      transition: color 0.2s, border-color 0.2s;
    }
    .tag:hover { color: var(--lime); border-color: rgba(198,241,53,0.4); }

    /* ── TOOLS CELL ── */
    .c-tools-inner {
      padding: 26px 28px;
      height: 100%; display: flex; flex-direction: column; justify-content: space-between;
    }
    .tools-top { display: flex; align-items: center; gap: 10px; }
    .tools-label {
      font-family: 'Syne', sans-serif;
      font-size: 0.85rem; font-weight: 700;
    }
    .tools-icons { display: flex; flex-wrap: wrap; gap: 7px; margin-top: 14px; }

    /* ── STREAK CELL ── */
    .c-streak { padding: 0; position: relative; }
    .c-streak img { width: 100%; height: 100%; object-fit: cover; display: block; border-radius: var(--r); }
    .streak-overlay {
      position: absolute; inset: 0; padding: 20px 24px;
      display: flex; flex-direction: column; justify-content: flex-end;
      background: linear-gradient(to top, rgba(0,0,0,0.7) 0%, transparent 60%);
      border-radius: var(--r);
    }
    .streak-title {
      font-family: 'Syne', sans-serif;
      font-size: 0.85rem; font-weight: 700; color: var(--lime);
      text-transform: uppercase; letter-spacing: 0.1em;
    }

    /* ── QUOTE CELL ── */
    .c-quote {
      background: var(--lime);
      border-color: var(--lime);
      padding: 36px 52px;
      display: flex; align-items: center; justify-content: space-between;
      gap: 24px;
    }
    .c-quote:hover { transform: none; border-color: var(--lime); }
    .quote-text {
      font-family: 'Syne', sans-serif;
      font-size: 1.35rem; font-weight: 700;
      color: var(--ink); line-height: 1.4;
      max-width: 680px;
    }
    .quote-text::before { content: '"'; font-size: 3rem; line-height: 0; vertical-align: -0.5em; margin-right: 4px; opacity: 0.4; }
    .quote-attr {
      flex-shrink: 0; text-align: right;
      font-size: 0.8rem; color: rgba(15,15,15,0.6);
      font-weight: 500;
    }
    .quote-attr strong { display: block; font-size: 1rem; color: var(--ink); font-family: 'Syne', sans-serif; }

    /* ── FOOTER ── */
    footer {
      position: relative; z-index: 1;
      text-align: center; padding: 40px 24px 24px;
      font-size: 0.78rem; color: #444;
    }
    footer a { color: var(--lime); text-decoration: none; }

    /* ── SCROLL ANIMATION ── */
    [data-reveal] {
      opacity: 0; transform: translateY(24px);
      transition: opacity 0.65s ease, transform 0.65s ease;
    }
    [data-reveal].in { opacity: 1; transform: none; }

    /* ── RESPONSIVE ── */
    @media (max-width: 860px) {
      .c-hero    { grid-column: span 12; grid-row: span 3; }
      .c-status  { grid-column: span 6;  grid-row: span 2; }
      .c-gif     { grid-column: span 6;  grid-row: span 2; }
      .c-fe, .c-be, .c-ai { grid-column: span 12; grid-row: span 2; }
      .c-tools   { grid-column: span 12; }
      .c-streak  { grid-column: span 12; }
      .c-quote   { flex-direction: column; }
      .hero-name { font-size: 2.8rem; }
    }
    @media (max-width: 560px) {
      .c-hero { padding: 32px 28px; }
      .hero-name { font-size: 2.2rem; }
      .c-status, .c-gif { grid-column: span 12; }
    }
  </style>
</head>
<body>
<div class="wrapper">

  <!-- NAV -->
  <nav data-reveal>
    <div class="nav-logo">MF<span>.</span></div>
    <div class="nav-status">
      <div class="nav-status-dot"></div>
      Available for work
    </div>
  </nav>

  <!-- BENTO GRID -->
  <div class="bento">

    <!-- HERO -->
    <div class="cell c-hero" data-reveal>
      <div class="hero-eyebrow">Full-Stack Developer & AI Engineer</div>
      <h1 class="hero-name">Mohammad<br><span class="line2">Faysal.</span></h1>
      <p class="hero-role">
        Transforms complex problems into <em>elegant, AI-powered</em> solutions.<br>
        MERN Stack · LangChain.js · Vector Databases
      </p>
      <div class="hero-links">
        <a href="https://mohammad-faysal-dev.netlify.app/" target="_blank" class="btn btn-lime">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M18 13v6a2 2 0 01-2 2H5a2 2 0 01-2-2V8a2 2 0 012-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
          View Portfolio
        </a>
        <a href="https://www.linkedin.com/in/mohammad-foysal-dev/" target="_blank" class="btn btn-ghost">LinkedIn</a>
        <a href="mailto:contact.mohammad.faysal@gmail.com" class="btn btn-ghost">Email</a>
      </div>
    </div>

    <!-- STATUS -->
    <div class="cell c-status" data-reveal>
      <div class="tech-cell" style="height:100%;justify-content:space-between;">
        <div>
          <div class="status-label">Current Focus</div>
          <div class="status-value">AI Web Apps</div>
          <p style="font-size:0.78rem;color:var(--muted);margin-top:8px;line-height:1.6;">
            Building AI-integrated applications using LangChain.js &amp; advanced LLM orchestration.
          </p>
        </div>
        <div class="status-chips">
          <span class="chip lime">● Open to work</span>
          <span class="chip">BUTEX Graduate</span>
        </div>
      </div>
    </div>

    <!-- GIF -->
    <div class="cell c-gif" data-reveal>
      <img src="https://cdn.dribbble.com/users/1162077/screenshots/3848914/programmer.gif" alt="Coder" />
    </div>

    <!-- FRONTEND -->
    <div class="cell c-fe" data-reveal>
      <div class="tech-cell" style="height:100%;">
        <div class="tech-cell-title">
          <span class="tech-cell-emoji">🎨</span> Frontend
        </div>
        <div class="icon-row">
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=html"    alt="HTML"/></div>
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=css"     alt="CSS"/></div>
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=js"      alt="JS"/></div>
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=ts"      alt="TS"/></div>
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=react"   alt="React"/></div>
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=nextjs"  alt="Next"/></div>
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=tailwind" alt="Tailwind"/></div>
        </div>
        <div class="tag-row">
          <span class="tag">DaisyUI</span>
          <span class="tag">Framer Motion</span>
          <span class="tag">Redux</span>
          <span class="tag">Shadcn</span>
        </div>
      </div>
    </div>

    <!-- BACKEND -->
    <div class="cell c-be" data-reveal>
      <div class="tech-cell" style="height:100%;">
        <div class="tech-cell-title">
          <span class="tech-cell-emoji">⚙️</span> Backend
        </div>
        <div class="icon-row">
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=nodejs"     alt="Node"/></div>
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=express"    alt="Express"/></div>
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=mongodb"    alt="MongoDB"/></div>
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=postgresql" alt="PostgreSQL"/></div>
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=firebase"   alt="Firebase"/></div>
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=prisma"     alt="Prisma"/></div>
        </div>
        <div class="tag-row">
          <span class="tag">JWT</span>
          <span class="tag">Socket.io</span>
          <span class="tag">Redis</span>
          <span class="tag">REST &amp; GraphQL</span>
        </div>
      </div>
    </div>

    <!-- AI -->
    <div class="cell c-ai" data-reveal>
      <div class="tech-cell" style="height:100%;">
        <div class="tech-cell-title">
          <span class="tech-cell-emoji">🤖</span> AI Engineering
        </div>
        <div class="icon-row">
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=py"         alt="Python"/></div>
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=tensorflow" alt="TF"/></div>
          <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=pytorch"    alt="PyTorch"/></div>
        </div>
        <div class="tag-row">
          <span class="tag">OpenAI</span>
          <span class="tag">Gemini</span>
          <span class="tag">LangChain</span>
          <span class="tag">Hugging Face</span>
          <span class="tag">RAG</span>
          <span class="tag">Vector DB</span>
        </div>
      </div>
    </div>

    <!-- TOOLS -->
    <div class="cell c-tools" data-reveal>
      <div class="c-tools-inner">
        <div>
          <div class="tools-top">
            <span style="font-size:1.1rem;">🔧</span>
            <span class="tools-label">Tools &amp; DevOps</span>
          </div>
          <div class="tools-icons">
            <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=git"        alt="Git"/></div>
            <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=docker"     alt="Docker"/></div>
            <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=kubernetes" alt="K8s"/></div>
            <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=aws"        alt="AWS"/></div>
            <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=vercel"     alt="Vercel"/></div>
            <div class="icon-wrap"><img src="https://skillicons.dev/icons?i=postman"    alt="Postman"/></div>
          </div>
        </div>
        <div class="tag-row">
          <span class="tag">Nginx</span>
          <span class="tag">Linux</span>
          <span class="tag">Jenkins</span>
          <span class="tag">CI/CD</span>
        </div>
      </div>
    </div>

    <!-- STREAK -->
    <div class="cell c-streak" data-reveal style="position:relative; overflow:hidden;">
      <img
        src="https://github-readme-streak-stats.herokuapp.com/?user=mohammad-faysal-dev&theme=dark&hide_border=true&background=161616&ring=c6f135&fire=c6f135&currStreakLabel=c6f135"
        alt="GitHub Streak"
        style="width:100%;height:100%;object-fit:cover;display:block;"
        onerror="this.parentElement.style.background='#161616'; this.style.display='none';"
      />
      <div class="streak-overlay">
        <div class="streak-title">📊 GitHub Streak</div>
      </div>
    </div>

    <!-- QUOTE -->
    <div class="cell c-quote" data-reveal>
      <p class="quote-text">Write clean, maintainable code that solves real problems</p>
      <div class="quote-attr">
        <strong>Mohammad Faysal</strong>
        Technical Philosophy
      </div>
    </div>

  </div><!-- /bento -->

</div><!-- /wrapper -->

<footer>
  Designed &amp; Built by <a href="mailto:contact.mohammad.faysal@gmail.com">Mohammad Faysal</a> · 2025
</footer>

<script>
  // scroll reveal
  const els = document.querySelectorAll('[data-reveal]');
  const io = new IntersectionObserver(entries => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('in'), i * 60);
        io.unobserve(e.target);
      }
    });
  }, { threshold: 0.08 });
  els.forEach(el => io.observe(el));
</script>
</body>
</html>
