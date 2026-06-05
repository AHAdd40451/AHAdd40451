<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Abdul Ahad — Full Stack Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;700;800&family=DM+Mono:wght@400;500&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }

  :root {
    --bg: #0a0a0f;
    --surface: #111118;
    --border: rgba(255,255,255,0.07);
    --border-hover: rgba(255,255,255,0.15);
    --accent: #7c6dfa;
    --accent2: #4fcfa0;
    --accent3: #f4845f;
    --text: #f0f0f5;
    --muted: #8585a0;
    --dim: #3a3a50;
  }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      radial-gradient(circle at 20% 20%, rgba(124,109,250,0.06) 0%, transparent 50%),
      radial-gradient(circle at 80% 80%, rgba(79,207,160,0.05) 0%, transparent 50%),
      radial-gradient(circle at 60% 10%, rgba(244,132,95,0.04) 0%, transparent 40%);
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 60px 32px 80px;
    position: relative;
    z-index: 1;
  }

  .header { margin-bottom: 56px; }

  .eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.18em;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .eyebrow::after {
    content: '';
    flex: 1;
    max-width: 48px;
    height: 1px;
    background: var(--accent);
    opacity: 0.5;
  }

  h1 {
    font-family: 'Syne', sans-serif;
    font-size: clamp(44px, 8vw, 72px);
    font-weight: 800;
    line-height: 1.0;
    letter-spacing: -0.03em;
    margin-bottom: 8px;
  }
  h1 .name-line {
    display: block;
    background: linear-gradient(135deg, #ffffff 0%, #c0bff5 60%, #7c6dfa 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .title-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(124,109,250,0.1);
    border: 1px solid rgba(124,109,250,0.25);
    border-radius: 100px;
    padding: 6px 16px 6px 10px;
    font-size: 13px;
    color: #b8b0fa;
    margin-top: 20px;
    font-family: 'DM Mono', monospace;
  }
  .dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    background: var(--accent2);
    box-shadow: 0 0 8px var(--accent2);
    animation: pulse 2s ease-in-out infinite;
  }
  @keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.6;transform:scale(0.8)} }

  .tagline {
    margin-top: 24px;
    font-size: 17px;
    color: var(--muted);
    line-height: 1.65;
    max-width: 540px;
    font-weight: 300;
  }
  .tagline strong { color: #c8c6e8; font-weight: 500; }

  .stack-section { margin-bottom: 52px; }
  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--dim);
    margin-bottom: 16px;
  }
  .stack-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  .tag {
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    padding: 5px 12px;
    border-radius: 6px;
    border: 1px solid var(--border);
    background: var(--surface);
    color: var(--muted);
    transition: border-color 0.2s, color 0.2s, background 0.2s;
    cursor: default;
    white-space: nowrap;
  }
  .tag:hover { border-color: var(--border-hover); color: var(--text); background: rgba(255,255,255,0.04); }
  .tag.accent { border-color: rgba(124,109,250,0.3); color: #a89cfa; background: rgba(124,109,250,0.06); }
  .tag.green  { border-color: rgba(79,207,160,0.3);  color: #6fd9b8; background: rgba(79,207,160,0.06); }
  .tag.orange { border-color: rgba(244,132,95,0.3);  color: #f4a07c; background: rgba(244,132,95,0.06); }

  .divider { border: none; border-top: 1px solid var(--border); margin: 0 0 52px; }

  .projects-header {
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    margin-bottom: 24px;
  }
  .projects-header h2 {
    font-family: 'Syne', sans-serif;
    font-size: 22px;
    font-weight: 700;
    color: var(--text);
    letter-spacing: -0.02em;
  }
  .projects-count {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--dim);
  }

  .project-list {
    display: flex;
    flex-direction: column;
    gap: 1px;
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    background: var(--border);
  }

  .project-item {
    background: var(--surface);
    padding: 20px 24px;
    display: grid;
    grid-template-columns: 1fr auto;
    gap: 12px;
    align-items: start;
    transition: background 0.2s;
    cursor: default;
    text-decoration: none;
    color: inherit;
  }
  .project-item:hover { background: rgba(255,255,255,0.03); }

  .project-name {
    font-family: 'Syne', sans-serif;
    font-size: 15px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 4px;
    letter-spacing: -0.01em;
  }
  .project-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.5;
    font-weight: 300;
  }
  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-top: 10px;
  }
  .ptag {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    padding: 2px 8px;
    border-radius: 4px;
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border);
    color: var(--dim);
    letter-spacing: 0.05em;
  }
  .project-link {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--accent);
    opacity: 0.7;
    text-decoration: none;
    margin-top: 2px;
    white-space: nowrap;
  }
  .project-link:hover { opacity: 1; }

  .currently {
    margin-top: 48px;
    padding: 28px;
    border: 1px solid var(--border);
    border-radius: 12px;
    background: var(--surface);
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
  }

  .current-item { display: flex; flex-direction: column; gap: 6px; }
  .current-label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--dim);
  }
  .current-value {
    font-size: 14px;
    color: var(--text);
    font-weight: 400;
    line-height: 1.5;
  }
  .current-value a { color: var(--accent2); text-decoration: none; }
  .current-value a:hover { text-decoration: underline; }
  .badge-ai {
    display: inline-block;
    background: rgba(79,207,160,0.1);
    border: 1px solid rgba(79,207,160,0.25);
    color: #6fd9b8;
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    padding: 2px 8px;
    border-radius: 4px;
    margin-left: 6px;
    vertical-align: middle;
    letter-spacing: 0.08em;
  }

  .footer-row {
    margin-top: 40px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 16px;
  }
  .contact-link {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: var(--muted);
    text-decoration: none;
    border: 1px solid var(--border);
    padding: 8px 16px;
    border-radius: 8px;
    transition: border-color 0.2s, color 0.2s;
  }
  .contact-link:hover { border-color: var(--border-hover); color: var(--text); }
  .gh-link {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-family: 'DM Mono', monospace;
    font-size: 12px;
    color: var(--accent);
    text-decoration: none;
    border: 1px solid rgba(124,109,250,0.3);
    padding: 8px 16px;
    border-radius: 8px;
    background: rgba(124,109,250,0.06);
    transition: background 0.2s, border-color 0.2s;
  }
  .gh-link:hover { background: rgba(124,109,250,0.12); border-color: rgba(124,109,250,0.5); }

  @media (max-width: 560px) {
    .container { padding: 40px 20px 60px; }
    .currently { grid-template-columns: 1fr; gap: 18px; }
    .footer-row { flex-direction: column; align-items: flex-start; }
  }
</style>
</head>
<body>
<div class="container">

  <header class="header">
    <div class="eyebrow">Full Stack Developer</div>
    <h1><span class="name-line">Abdul Ahad</span></h1>
    <div class="title-badge">
      <span class="dot"></span>
      5 yrs exp · Pakistan
    </div>
    <p class="tagline">
      I build <strong>products that ship</strong> — marketplaces, Web3 platforms, multi-tenant SaaS, real-time dashboards. From pixel-perfect UIs to distributed backends. Currently exploring <strong>AI multi-agent systems</strong> with OpenClaw.
    </p>
  </header>

  <section class="stack-section">
    <div class="section-label">Frontend</div>
    <div class="stack-grid" style="margin-bottom: 24px;">
      <span class="tag accent">TypeScript</span>
      <span class="tag accent">React</span>
      <span class="tag accent">Next.js</span>
      <span class="tag accent">Vue</span>
      <span class="tag">JavaScript</span>
      <span class="tag">Tailwind CSS</span>
    </div>

    <div class="section-label">Backend &amp; APIs</div>
    <div class="stack-grid" style="margin-bottom: 24px;">
      <span class="tag green">Node.js</span>
      <span class="tag green">NestJS</span>
      <span class="tag green">Express</span>
      <span class="tag">WebSockets</span>
      <span class="tag">gRPC</span>
      <span class="tag">GraphQL</span>
      <span class="tag">REST</span>
      <span class="tag">Prisma</span>
    </div>

    <div class="section-label">Data &amp; Infra</div>
    <div class="stack-grid">
      <span class="tag orange">PostgreSQL</span>
      <span class="tag orange">MongoDB</span>
      <span class="tag orange">Redis</span>
      <span class="tag orange">Firebase</span>
      <span class="tag">Docker</span>
      <span class="tag">AWS</span>
      <span class="tag">Kubernetes</span>
      <span class="tag">Vercel</span>
      <span class="tag">GitHub Actions</span>
    </div>
  </section>

  <hr class="divider">

  <section>
    <div class="projects-header">
      <h2>Selected Work</h2>
      <span class="projects-count">7 projects</span>
    </div>

    <div class="project-list">

      <a class="project-item" href="https://www.sysselmarket.com/" target="_blank">
        <div>
          <div class="project-name">Syssel — Norway Service Marketplace</div>
          <div class="project-desc">Full ecosystem: cross-platform mobile app, provider & customer dashboards, admin panel. Stripe Connect, Apple Pay, Google Pay, Google Business Profile, multilingual. Built solo over one year.</div>
          <div class="project-tags">
            <span class="ptag">React Native</span><span class="ptag">Node.js</span><span class="ptag">Stripe Connect</span><span class="ptag">AWS Amplify</span><span class="ptag">iOS</span><span class="ptag">Android</span>
          </div>
        </div>
        <span class="project-link">↗ live</span>
      </a>

      <a class="project-item" href="https://www.app.taskbound.io/" target="_blank">
        <div>
          <div class="project-name">Taskbound — Web3 Bounty Platform</div>
          <div class="project-desc">Earn crypto by completing task-based campaigns. EVM wallet connections, reward distribution, referral logic, leaderboards, and campaign creation system.</div>
          <div class="project-tags">
            <span class="ptag">MERN</span><span class="ptag">Web3</span><span class="ptag">EVM Wallets</span><span class="ptag">MVC</span>
          </div>
        </div>
        <span class="project-link">↗ live</span>
      </a>

      <a class="project-item" href="https://www.hashoneglobal.com/software/web-application-development" target="_blank">
        <div>
          <div class="project-name">HashOne Global — Corporate Website</div>
          <div class="project-desc">20+ page corporate site built pixel-perfect from Figma. Sanity CMS integration, reusable component library, SEO and performance optimized.</div>
          <div class="project-tags">
            <span class="ptag">React</span><span class="ptag">Sanity CMS</span><span class="ptag">Figma</span><span class="ptag">SEO</span>
          </div>
        </div>
        <span class="project-link">↗ live</span>
      </a>

      <a class="project-item" href="https://fannet-seven.vercel.app/leads" target="_blank">
        <div>
          <div class="project-name">Fannet — Lead Tracking Dashboard</div>
          <div class="project-desc">Real-time yearly, quarterly and weekly goal tracking for software agencies, pulling live data from GoHighLevel API.</div>
          <div class="project-tags">
            <span class="ptag">React</span><span class="ptag">GoHighLevel API</span><span class="ptag">Vercel</span>
          </div>
        </div>
        <span class="project-link">↗ live</span>
      </a>

      <a class="project-item" href="https://simplycavapoos.com/" target="_blank">
        <div>
          <div class="project-name">Simply Southern Pups — Full Rebuild</div>
          <div class="project-desc">Complete redesign and rebuild of a dog sales site. Breeder dashboard, puppy listing management, SEO-friendly React front end, mobile-first.</div>
          <div class="project-tags">
            <span class="ptag">React</span><span class="ptag">Dashboard</span><span class="ptag">SEO</span>
          </div>
        </div>
        <span class="project-link">↗ live</span>
      </a>

      <a class="project-item" href="https://next-full-stack-ecommerce-psi.vercel.app/" target="_blank">
        <div>
          <div class="project-name">Suqhur — Buy &amp; Sell Marketplace</div>
          <div class="project-desc">Full-stack marketplace with Next.js SSR for SEO, secure auth, product listings and user dashboards.</div>
          <div class="project-tags">
            <span class="ptag">Next.js</span><span class="ptag">SSR</span><span class="ptag">PostgreSQL</span>
          </div>
        </div>
        <span class="project-link">↗ live</span>
      </a>

      <div class="project-item">
        <div>
          <div class="project-name">247 Seating — Restaurant Reservation Platform</div>
          <div class="project-desc">Full-stack reservation and table management system. Real-time table occupancy, booking flows, and seating schedule management for restaurant staff.</div>
          <div class="project-tags">
            <span class="ptag">Node.js</span><span class="ptag">Real-time</span><span class="ptag">Dashboard</span>
          </div>
        </div>
        <span class="project-link" style="opacity:0.3;">private</span>
      </div>

    </div>
  </section>

  <section class="currently">
    <div class="current-item">
      <div class="current-label">Currently building</div>
      <div class="current-value">AI multi-agent systems with OpenClaw <span class="badge-ai">new</span></div>
    </div>
    <div class="current-item">
      <div class="current-label">Also into</div>
      <div class="current-value">DevOps infrastructure, Kubernetes, private client work</div>
    </div>
    <div class="current-item">
      <div class="current-label">Ask me about</div>
      <div class="current-value">JavaScript, TypeScript, React, Node.js</div>
    </div>
    <div class="current-item">
      <div class="current-label">GitHub</div>
      <div class="current-value"><a href="https://github.com/AHAdd40451" target="_blank">AHAdd40451</a> — consistently shipping</div>
    </div>
  </section>

  <div class="footer-row">
    <a class="contact-link" href="mailto:ahadkhan40451@gmail.com">ahadkhan40451@gmail.com</a>
    <a class="gh-link" href="https://github.com/AHAdd40451" target="_blank">github.com/AHAdd40451 ↗</a>
  </div>

</div>
</body>
</html>
