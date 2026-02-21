# boringstack
the anti-hype starter pack
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BoringStack — Ship Fast. Profit Faster.</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --ink: #0f0e0c;
    --paper: #f5f0e8;
    --cream: #ede8db;
    --accent: #d4541a;
    --accent2: #2563a8;
    --muted: #8a8070;
    --border: #cfc8b8;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--paper);
    color: var(--ink);
    font-family: 'Outfit', sans-serif;
    font-weight: 400;
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* ── NOISE TEXTURE OVERLAY ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.035'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 1000;
    opacity: 0.6;
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.25rem 3rem;
    border-bottom: 1px solid var(--border);
    background: rgba(245,240,232,0.9);
    backdrop-filter: blur(8px);
  }

  .nav-logo {
    font-family: 'Bebas Neue', cursive;
    font-size: 1.6rem;
    letter-spacing: 0.05em;
    color: var(--ink);
    text-decoration: none;
  }

  .nav-logo span { color: var(--accent); }

  .nav-links {
    display: flex;
    gap: 2rem;
    list-style: none;
    align-items: center;
  }

  .nav-links a {
    font-size: 0.85rem;
    font-weight: 500;
    text-decoration: none;
    color: var(--muted);
    letter-spacing: 0.05em;
    text-transform: uppercase;
    transition: color 0.2s;
  }

  .nav-links a:hover { color: var(--ink); }

  .btn-nav {
    background: var(--ink);
    color: var(--paper) !important;
    padding: 0.55rem 1.4rem;
    border-radius: 2px;
    font-weight: 600 !important;
    font-size: 0.82rem !important;
    transition: background 0.2s !important;
  }

  .btn-nav:hover { background: var(--accent) !important; color: white !important; }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding-top: 5rem;
    position: relative;
    overflow: hidden;
  }

  .hero-left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 6rem 3rem 6rem 3rem;
    border-right: 1px solid var(--border);
    position: relative;
  }

  .hero-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 0.78rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 1.5rem;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.2s;
  }

  .hero-title {
    font-family: 'Bebas Neue', cursive;
    font-size: clamp(4.5rem, 8vw, 7rem);
    line-height: 0.92;
    letter-spacing: 0.02em;
    color: var(--ink);
    margin-bottom: 2rem;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.35s;
  }

  .hero-title em {
    font-style: italic;
    font-family: 'DM Serif Display', serif;
    color: var(--accent);
  }

  .hero-subtitle {
    font-size: 1.1rem;
    color: var(--muted);
    max-width: 440px;
    line-height: 1.7;
    margin-bottom: 3rem;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.5s;
  }

  .hero-cta {
    display: flex;
    gap: 1rem;
    align-items: center;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.65s;
  }

  .btn-primary {
    background: var(--accent);
    color: white;
    padding: 0.9rem 2.2rem;
    font-size: 0.95rem;
    font-weight: 600;
    border: none;
    border-radius: 2px;
    cursor: pointer;
    text-decoration: none;
    display: inline-block;
    transition: transform 0.15s, box-shadow 0.15s;
    letter-spacing: 0.02em;
  }

  .btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 24px rgba(212,84,26,0.35);
  }

  .btn-secondary {
    font-size: 0.9rem;
    color: var(--ink);
    text-decoration: none;
    font-weight: 500;
    border-bottom: 1.5px solid var(--border);
    padding-bottom: 2px;
    transition: border-color 0.2s, color 0.2s;
  }

  .btn-secondary:hover { border-color: var(--ink); }

  .hero-right {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 6rem 3rem;
    background: var(--cream);
    position: relative;
  }

  .stack-diagram {
    display: flex;
    flex-direction: column;
    gap: 1px;
    border: 1px solid var(--border);
    overflow: hidden;
  }

  .stack-row {
    display: flex;
    align-items: center;
    gap: 1.5rem;
    padding: 1.4rem 1.8rem;
    background: var(--paper);
    border-bottom: 1px solid var(--border);
    cursor: default;
    transition: background 0.2s;
    opacity: 0;
  }

  .stack-row:last-child { border-bottom: none; }
  .stack-row:hover { background: white; }

  .stack-row.anim-1 { animation: slideIn 0.5s ease forwards 0.7s; }
  .stack-row.anim-2 { animation: slideIn 0.5s ease forwards 0.85s; }
  .stack-row.anim-3 { animation: slideIn 0.5s ease forwards 1s; }
  .stack-row.anim-4 { animation: slideIn 0.5s ease forwards 1.15s; }
  .stack-row.anim-5 { animation: slideIn 0.5s ease forwards 1.3s; }

  .stack-icon {
    width: 44px;
    height: 44px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.3rem;
    flex-shrink: 0;
  }

  .stack-info { flex: 1; }

  .stack-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--muted);
    margin-bottom: 0.15rem;
  }

  .stack-name {
    font-size: 1rem;
    font-weight: 600;
    color: var(--ink);
  }

  .stack-badge {
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    padding: 0.25rem 0.7rem;
    border-radius: 99px;
    background: var(--cream);
    border: 1px solid var(--border);
    color: var(--muted);
    white-space: nowrap;
  }

  /* ── TICKER ── */
  .ticker {
    background: var(--ink);
    color: var(--paper);
    padding: 0.9rem 0;
    overflow: hidden;
    white-space: nowrap;
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }

  .ticker-inner {
    display: inline-flex;
    animation: ticker 25s linear infinite;
  }

  .ticker-item {
    display: inline-flex;
    align-items: center;
    gap: 1rem;
    padding: 0 2rem;
    font-family: 'DM Mono', monospace;
    font-size: 0.78rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  .ticker-dot {
    width: 5px;
    height: 5px;
    border-radius: 50%;
    background: var(--accent);
    flex-shrink: 0;
  }

  @keyframes ticker {
    from { transform: translateX(0); }
    to { transform: translateX(-50%); }
  }

  /* ── HOW IT WORKS ── */
  .section {
    padding: 7rem 3rem;
    max-width: 1200px;
    margin: 0 auto;
  }

  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    color: var(--accent);
    margin-bottom: 1rem;
  }

  .section-title {
    font-family: 'DM Serif Display', serif;
    font-size: clamp(2.2rem, 4vw, 3.2rem);
    line-height: 1.15;
    color: var(--ink);
    margin-bottom: 1.5rem;
    max-width: 560px;
  }

  .section-subtitle {
    font-size: 1.05rem;
    color: var(--muted);
    max-width: 520px;
    margin-bottom: 4rem;
    line-height: 1.7;
  }

  .steps {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
    border: 1px solid var(--border);
    overflow: hidden;
  }

  .step {
    padding: 2.5rem;
    background: var(--paper);
    border-right: 1px solid var(--border);
    transition: background 0.2s;
    position: relative;
  }

  .step:last-child { border-right: none; }
  .step:hover { background: var(--cream); }

  .step-number {
    font-family: 'Bebas Neue', cursive;
    font-size: 4rem;
    color: var(--border);
    line-height: 1;
    margin-bottom: 1.5rem;
    display: block;
  }

  .step h3 {
    font-size: 1.1rem;
    font-weight: 600;
    margin-bottom: 0.75rem;
    color: var(--ink);
  }

  .step p {
    font-size: 0.92rem;
    color: var(--muted);
    line-height: 1.65;
  }

  .step-tool {
    margin-top: 1.5rem;
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    color: var(--accent2);
    background: rgba(37,99,168,0.08);
    padding: 0.35rem 0.8rem;
    border-radius: 3px;
    letter-spacing: 0.05em;
  }

  /* ── FEATURES ── */
  .features-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
    border: 1px solid var(--border);
    overflow: hidden;
  }

  .feature {
    padding: 2.5rem;
    background: var(--paper);
    border-bottom: 1px solid var(--border);
    border-right: 1px solid var(--border);
    transition: background 0.2s;
  }

  .feature:nth-child(2n) { border-right: none; }
  .feature:nth-last-child(-n+2) { border-bottom: none; }
  .feature:hover { background: white; }

  .feature-icon {
    font-size: 1.8rem;
    margin-bottom: 1rem;
    display: block;
  }

  .feature h3 {
    font-size: 1rem;
    font-weight: 600;
    margin-bottom: 0.6rem;
    color: var(--ink);
  }

  .feature p {
    font-size: 0.88rem;
    color: var(--muted);
    line-height: 1.65;
  }

  /* ── PRICING ── */
  .pricing-section {
    background: var(--cream);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
    padding: 7rem 3rem;
  }

  .pricing-inner {
    max-width: 1000px;
    margin: 0 auto;
  }

  .pricing-cards {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 2px;
    margin-top: 4rem;
    border: 1px solid var(--border);
    overflow: hidden;
  }

  .pricing-card {
    background: var(--paper);
    padding: 2.5rem;
    border-right: 1px solid var(--border);
    position: relative;
    transition: background 0.2s;
  }

  .pricing-card:last-child { border-right: none; }
  .pricing-card:hover { background: white; }
  .pricing-card.featured {
    background: var(--ink);
    color: var(--paper);
  }

  .pricing-card.featured:hover { background: #1a1915; }

  .plan-name {
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    color: var(--muted);
    margin-bottom: 1.5rem;
  }

  .pricing-card.featured .plan-name { color: rgba(245,240,232,0.5); }

  .price {
    font-family: 'Bebas Neue', cursive;
    font-size: 3.5rem;
    line-height: 1;
    color: var(--ink);
    margin-bottom: 0.4rem;
  }

  .pricing-card.featured .price { color: var(--paper); }

  .price-period {
    font-size: 0.82rem;
    color: var(--muted);
    margin-bottom: 2rem;
  }

  .pricing-card.featured .price-period { color: rgba(245,240,232,0.5); }

  .pricing-features {
    list-style: none;
    margin-bottom: 2rem;
  }

  .pricing-features li {
    font-size: 0.88rem;
    color: var(--muted);
    padding: 0.5rem 0;
    border-bottom: 1px solid var(--border);
    display: flex;
    align-items: center;
    gap: 0.6rem;
  }

  .pricing-card.featured .pricing-features li {
    color: rgba(245,240,232,0.7);
    border-color: rgba(245,240,232,0.1);
  }

  .pricing-features li::before {
    content: '✓';
    color: var(--accent);
    font-weight: 700;
    font-size: 0.75rem;
    flex-shrink: 0;
  }

  .btn-plan {
    display: block;
    width: 100%;
    padding: 0.85rem;
    text-align: center;
    font-size: 0.88rem;
    font-weight: 600;
    border: 1.5px solid var(--border);
    background: transparent;
    color: var(--ink);
    border-radius: 2px;
    cursor: pointer;
    transition: all 0.2s;
    text-decoration: none;
    letter-spacing: 0.03em;
  }

  .btn-plan:hover { background: var(--ink); color: var(--paper); border-color: var(--ink); }

  .pricing-card.featured .btn-plan {
    background: var(--accent);
    border-color: var(--accent);
    color: white;
  }

  .pricing-card.featured .btn-plan:hover {
    background: #bf4a15;
    border-color: #bf4a15;
  }

  .popular-badge {
    position: absolute;
    top: -1px; right: 2rem;
    background: var(--accent);
    color: white;
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    padding: 0.3rem 0.8rem;
    border-radius: 0 0 4px 4px;
  }

  /* ── FAQ ── */
  .faq-list {
    border: 1px solid var(--border);
    overflow: hidden;
    max-width: 720px;
  }

  .faq-item {
    border-bottom: 1px solid var(--border);
  }

  .faq-item:last-child { border-bottom: none; }

  .faq-question {
    width: 100%;
    text-align: left;
    padding: 1.4rem 1.8rem;
    background: none;
    border: none;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-family: 'Outfit', sans-serif;
    font-size: 0.95rem;
    font-weight: 600;
    color: var(--ink);
    transition: background 0.15s;
  }

  .faq-question:hover { background: var(--cream); }

  .faq-icon {
    font-size: 1.3rem;
    transition: transform 0.25s;
    color: var(--muted);
    flex-shrink: 0;
    font-weight: 300;
  }

  .faq-item.open .faq-icon { transform: rotate(45deg); color: var(--accent); }

  .faq-answer {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.3s ease, padding 0.3s ease;
    font-size: 0.9rem;
    color: var(--muted);
    line-height: 1.7;
    padding: 0 1.8rem;
  }

  .faq-item.open .faq-answer {
    max-height: 200px;
    padding: 0 1.8rem 1.4rem;
  }

  /* ── CTA ── */
  .cta-section {
    background: var(--ink);
    padding: 7rem 3rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }

  .cta-section::before {
    content: 'SHIP';
    position: absolute;
    font-family: 'Bebas Neue', cursive;
    font-size: 28rem;
    color: rgba(255,255,255,0.025);
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    pointer-events: none;
    letter-spacing: -0.02em;
    white-space: nowrap;
  }

  .cta-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    color: var(--accent);
    margin-bottom: 1.5rem;
  }

  .cta-title {
    font-family: 'Bebas Neue', cursive;
    font-size: clamp(3rem, 6vw, 5.5rem);
    color: var(--paper);
    line-height: 0.95;
    letter-spacing: 0.02em;
    margin-bottom: 1.5rem;
  }

  .cta-title em {
    font-style: italic;
    font-family: 'DM Serif Display', serif;
    color: var(--accent);
  }

  .cta-sub {
    font-size: 1rem;
    color: rgba(245,240,232,0.5);
    margin-bottom: 3rem;
    max-width: 420px;
    margin-left: auto;
    margin-right: auto;
    line-height: 1.7;
  }

  .cta-form {
    display: flex;
    gap: 0.75rem;
    justify-content: center;
    max-width: 440px;
    margin: 0 auto;
  }

  .cta-input {
    flex: 1;
    padding: 0.85rem 1.2rem;
    background: rgba(255,255,255,0.08);
    border: 1px solid rgba(255,255,255,0.15);
    border-radius: 2px;
    color: var(--paper);
    font-family: 'Outfit', sans-serif;
    font-size: 0.9rem;
    outline: none;
    transition: border-color 0.2s;
  }

  .cta-input::placeholder { color: rgba(245,240,232,0.3); }
  .cta-input:focus { border-color: var(--accent); }

  /* ── FOOTER ── */
  footer {
    background: var(--ink);
    border-top: 1px solid rgba(255,255,255,0.07);
    padding: 2.5rem 3rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .footer-logo {
    font-family: 'Bebas Neue', cursive;
    font-size: 1.3rem;
    color: rgba(245,240,232,0.4);
    text-decoration: none;
    letter-spacing: 0.05em;
  }

  .footer-logo span { color: var(--accent); }

  .footer-copy {
    font-size: 0.78rem;
    color: rgba(245,240,232,0.3);
    font-family: 'DM Mono', monospace;
  }

  .footer-links {
    display: flex;
    gap: 1.5rem;
    list-style: none;
  }

  .footer-links a {
    font-size: 0.78rem;
    color: rgba(245,240,232,0.3);
    text-decoration: none;
    transition: color 0.2s;
    font-family: 'DM Mono', monospace;
  }

  .footer-links a:hover { color: var(--paper); }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes slideIn {
    from { opacity: 0; transform: translateX(20px); }
    to { opacity: 1; transform: translateX(0); }
  }

  .reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }

  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    .hero { grid-template-columns: 1fr; }
    .hero-left { border-right: none; border-bottom: 1px solid var(--border); }
    .steps { grid-template-columns: 1fr; }
    .step { border-right: none; border-bottom: 1px solid var(--border); }
    .features-grid { grid-template-columns: 1fr; }
    .feature { border-right: none !important; }
    .pricing-cards { grid-template-columns: 1fr; }
    .pricing-card { border-right: none; border-bottom: 1px solid var(--border); }
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    .section { padding: 5rem 1.5rem; }
    .cta-form { flex-direction: column; }
    footer { flex-direction: column; gap: 1rem; text-align: center; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">Boring<span>Stack</span></a>
  <ul class="nav-links">
    <li><a href="#how">How it Works</a></li>
    <li><a href="#features">Features</a></li>
    <li><a href="#pricing">Pricing</a></li>
    <li><a href="#faq">FAQ</a></li>
    <li><a href="#start" class="btn-nav">Get Started</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-left">
    <span class="hero-eyebrow">🔩 The Anti-Hype Starter Kit</span>
    <h1 class="hero-title">Build Fast.<br><em>Profit</em><br>Faster.</h1>
    <p class="hero-subtitle">
      Stop obsessing over tech. Use Carrd, Airtable, Stripe — the "boring" stack that ships real products in days, not months.
    </p>
    <div class="hero-cta">
      <a href="#start" class="btn-primary">Start Building Free →</a>
      <a href="#how" class="btn-secondary">See how it works</a>
    </div>
  </div>
  <div class="hero-right">
    <p style="font-family:'DM Mono',monospace;font-size:0.72rem;text-transform:uppercase;letter-spacing:0.12em;color:var(--muted);margin-bottom:1rem;">Your Entire Stack</p>
    <div class="stack-diagram">
      <div class="stack-row anim-1">
        <div class="stack-icon" style="background:#fff3e0;">🌐</div>
        <div class="stack-info">
          <div class="stack-label">Frontend</div>
          <div class="stack-name">Carrd / Ghost</div>
        </div>
        <span class="stack-badge">No-code</span>
      </div>
      <div class="stack-row anim-2">
        <div class="stack-icon" style="background:#e8f5e9;">🗄️</div>
        <div class="stack-info">
          <div class="stack-label">Database</div>
          <div class="stack-name">Airtable</div>
        </div>
        <span class="stack-badge">Spreadsheet</span>
      </div>
      <div class="stack-row anim-3">
        <div class="stack-icon" style="background:#e3f2fd;">⚡</div>
        <div class="stack-info">
          <div class="stack-label">Web App Layer</div>
          <div class="stack-name">Softr</div>
        </div>
        <span class="stack-badge">In hours</span>
      </div>
      <div class="stack-row anim-4">
        <div class="stack-icon" style="background:#fce4ec;">💳</div>
        <div class="stack-info">
          <div class="stack-label">Payments</div>
          <div class="stack-name">Stripe / LemonSqueezy</div>
        </div>
        <span class="stack-badge">Tax-ready</span>
      </div>
      <div class="stack-row anim-5">
        <div class="stack-icon" style="background:#f3e5f5;">🤖</div>
        <div class="stack-info">
          <div class="stack-label">Automation</div>
          <div class="stack-name">Zapier / Make</div>
        </div>
        <span class="stack-badge">Zero code</span>
      </div>
    </div>
    <p style="margin-top:1.2rem;font-size:0.78rem;color:var(--muted);font-family:'DM Mono',monospace;">
      Total monthly cost: ~$50–$80 · Launch time: 1–3 days
    </p>
  </div>
</section>

<!-- TICKER -->
<div class="ticker">
  <div class="ticker-inner">
    <span class="ticker-item"><span class="ticker-dot"></span>Ship in days, not months</span>
    <span class="ticker-item"><span class="ticker-dot"></span>Zero DevOps required</span>
    <span class="ticker-item"><span class="ticker-dot"></span>Automatic tax compliance via LemonSqueezy</span>
    <span class="ticker-item"><span class="ticker-dot"></span>Airtable = your database & CMS</span>
    <span class="ticker-item"><span class="ticker-dot"></span>Softr turns spreadsheets into web apps</span>
    <span class="ticker-item"><span class="ticker-dot"></span>Ghost powers newsletters & directories</span>
    <span class="ticker-item"><span class="ticker-dot"></span>Boring is profitable</span>
    <span class="ticker-item"><span class="ticker-dot"></span>Ship in days, not months</span>
    <span class="ticker-item"><span class="ticker-dot"></span>Zero DevOps required</span>
    <span class="ticker-item"><span class="ticker-dot"></span>Automatic tax compliance via LemonSqueezy</span>
    <span class="ticker-item"><span class="ticker-dot"></span>Airtable = your database & CMS</span>
    <span class="ticker-item"><span class="ticker-dot"></span>Softr turns spreadsheets into web apps</span>
    <span class="ticker-item"><span class="ticker-dot"></span>Ghost powers newsletters & directories</span>
    <span class="ticker-item"><span class="ticker-dot"></span>Boring is profitable</span>
  </div>
</div>

<!-- HOW IT WORKS -->
<section id="how" class="section">
  <div class="reveal">
    <div class="section-label">How it Works</div>
    <h2 class="section-title">Three steps from idea to revenue.</h2>
    <p class="section-subtitle">No engineers. No architecture debates. No "just one more feature." Pick a tool, connect them, charge money.</p>
  </div>
  <div class="steps reveal">
    <div class="step">
      <span class="step-number">01</span>
      <h3>Build your front door</h3>
      <p>Use Carrd for a beautiful one-page site, or Ghost if you're running a directory or newsletter. Both are live in under an hour — and actually look good.</p>
      <span class="step-tool">🌐 Carrd · Ghost</span>
    </div>
    <div class="step">
      <span class="step-number">02</span>
      <h3>Wire up your back-end</h3>
      <p>Drop your data into Airtable — it's just a spreadsheet. Connect Softr to it and you have a real web app: user portals, dashboards, directories. No SQL needed.</p>
      <span class="step-tool">🗄️ Airtable · Softr</span>
    </div>
    <div class="step">
      <span class="step-number">03</span>
      <h3>Get paid (the boring way)</h3>
      <p>Stripe or LemonSqueezy handles everything — subscriptions, one-time payments, sales tax in 180 countries. You click a button. Money arrives.</p>
      <span class="step-tool">💳 Stripe · LemonSqueezy</span>
    </div>
  </div>
</section>

<!-- FEATURES -->
<section id="features" style="background:var(--cream);border-top:1px solid var(--border);border-bottom:1px solid var(--border);">
  <div class="section">
    <div class="reveal">
      <div class="section-label">Why Boring Wins</div>
      <h2 class="section-title">Everything you need. Nothing you don't.</h2>
      <p class="section-subtitle">The best stack is the one you actually ship with.</p>
    </div>
    <div class="features-grid reveal">
      <div class="feature">
        <span class="feature-icon">⚡</span>
        <h3>Ship in Hours, Not Sprints</h3>
        <p>Forget two-week dev cycles. Carrd + Airtable + Softr gets a working product live before lunch. No backlog, no standups.</p>
      </div>
      <div class="feature">
        <span class="feature-icon">💸</span>
        <h3>Tax Compliance on Autopilot</h3>
        <p>LemonSqueezy acts as Merchant of Record — they handle VAT, GST, sales tax globally. You collect the money, they handle the paperwork.</p>
      </div>
      <div class="feature">
        <span class="feature-icon">🔌</span>
        <h3>Everything Connects</h3>
        <p>Stripe webhooks → Airtable → Softr. Payment confirmed? New row appears. Softr renders it. Zapier automates the email. Magic, boring magic.</p>
      </div>
      <div class="feature">
        <span class="feature-icon">📈</span>
        <h3>Scales to Real Revenue</h3>
        <p>This stack runs six-figure businesses. Softr handles thousands of users. Airtable handles millions of records. Stripe processes billions. You're covered.</p>
      </div>
      <div class="feature">
        <span class="feature-icon">🛡️</span>
        <h3>Zero Infrastructure Ops</h3>
        <p>No servers. No containers. No "is the deploy broken?" at 2am. These are SaaS tools — uptime is someone else's problem, as it should be.</p>
      </div>
      <div class="feature">
        <span class="feature-icon">🧪</span>
        <h3>Validate Before You Invest</h3>
        <p>Spend $0 before your first customer. Free tiers across Carrd, Airtable, and Softr let you test the market before you spend a cent on infrastructure.</p>
      </div>
    </div>
  </div>
</section>

<!-- PRICING -->
<section id="pricing" class="pricing-section">
  <div class="pricing-inner">
    <div class="reveal">
      <div class="section-label">Simple Pricing</div>
      <h2 class="section-title">Start free. Pay when you're profitable.</h2>
      <p class="section-subtitle">Our templates and playbooks — the stack costs you nothing extra beyond what you pay the tools directly.</p>
    </div>
    <div class="pricing-cards reveal">
      <div class="pricing-card">
        <div class="plan-name">Starter</div>
        <div class="price">$0</div>
        <div class="price-period">forever free</div>
        <ul class="pricing-features">
          <li>Core stack guide (PDF)</li>
          <li>1 niche template</li>
          <li>Community access</li>
          <li>Basic Zapier flows</li>
        </ul>
        <a href="#" class="btn-plan">Get Started Free</a>
      </div>
      <div class="pricing-card featured">
        <div class="popular-badge">Most Popular</div>
        <div class="plan-name">Builder</div>
        <div class="price">$49</div>
        <div class="price-period">one-time payment</div>
        <ul class="pricing-features">
          <li>5 done-for-you templates</li>
          <li>Full Airtable → Softr setup</li>
          <li>Stripe + LemonSqueezy config</li>
          <li>Video walkthroughs</li>
          <li>6-month email support</li>
        </ul>
        <a href="#" class="btn-plan">Buy Builder Pack</a>
      </div>
      <div class="pricing-card">
        <div class="plan-name">Studio</div>
        <div class="price">$149</div>
        <div class="price-period">one-time payment</div>
        <ul class="pricing-features">
          <li>Everything in Builder</li>
          <li>12 niche-specific templates</li>
          <li>Custom domain + SEO guide</li>
          <li>1:1 onboarding call (30 min)</li>
          <li>Lifetime updates</li>
        </ul>
        <a href="#" class="btn-plan">Get Studio</a>
      </div>
    </div>
    <p class="reveal" style="text-align:center;margin-top:1.5rem;font-size:0.8rem;color:var(--muted);font-family:'DM Mono',monospace;">
      Payments via Stripe — secure, instant, refundable within 14 days.
    </p>
  </div>
</section>

<!-- FAQ -->
<section id="faq" class="section">
  <div class="reveal">
    <div class="section-label">FAQ</div>
    <h2 class="section-title">The questions everyone asks.</h2>
  </div>
  <div class="faq-list reveal">
    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        Do I need to know how to code?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">Not at all. Carrd, Softr, and Ghost are drag-and-drop or WYSIWYG. Airtable is a spreadsheet. Stripe has a dashboard for everything. If you can use Google Sheets, you can run this stack.</div>
    </div>
    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        How much does the full stack cost per month?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">Roughly $50–$90/month depending on the tiers you choose. Carrd Pro (~$19/yr), Airtable Plus ($20/mo), Softr Starter ($49/mo), and LemonSqueezy is free until you sell. Many businesses run the whole thing under $80/mo.</div>
    </div>
    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        What kind of products can I build?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">Directories, SaaS dashboards, marketplaces, membership sites, newsletters, job boards, resource libraries, booking tools — anything that's primarily data + payments. This stack is not ideal for real-time apps or heavy computation.</div>
    </div>
    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        Why LemonSqueezy over Stripe for payments?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">LemonSqueezy is a Merchant of Record — they collect the money, handle all global sales taxes, and remit them on your behalf. Stripe is more powerful but puts tax compliance on you. For solo founders selling globally, LemonSqueezy wins on simplicity.</div>
    </div>
    <div class="faq-item">
      <button class="faq-question" onclick="toggleFaq(this)">
        Can this scale beyond a side project?
        <span class="faq-icon">+</span>
      </button>
      <div class="faq-answer">Yes. Many businesses using this exact stack hit $10k–$50k MRR before ever touching custom code. At that point, you have revenue to invest in a proper engineer if you want. Most never need to.</div>
    </div>
  </div>
</section>

<!-- CTA -->
<section id="start" class="cta-section">
  <div class="reveal">
    <div class="cta-eyebrow">Ready to ship?</div>
    <h2 class="cta-title">Stop Planning.<br><em>Start Building.</em></h2>
    <p class="cta-sub">Join 3,000+ founders who swapped "perfect" for "profitable." Get the free starter guide in your inbox.</p>
    <div class="cta-form">
      <input type="email" class="cta-input" placeholder="your@email.com">
      <a href="#" class="btn-primary">Get Free Guide →</a>
    </div>
    <p style="margin-top:1rem;font-size:0.75rem;color:rgba(245,240,232,0.3);font-family:'DM Mono',monospace;">No spam. Unsubscribe anytime. Powered by Ghost.</p>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <a href="#" class="footer-logo">Boring<span>Stack</span></a>
  <span class="footer-copy">© 2025 BoringStack — Built with the boring stack, obviously.</span>
  <ul class="footer-links">
    <li><a href="#">Privacy</a></li>
    <li><a href="#">Terms</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</footer>

<script>
  // Intersection observer for reveal animations
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        // Stagger children if it's a grid
        const children = e.target.querySelectorAll('.step, .feature, .pricing-card, .faq-item');
        children.forEach((child, i) => {
          child.style.transitionDelay = `${i * 0.08}s`;
        });
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

  // FAQ toggle
  function toggleFaq(btn) {
    const item = btn.closest('.faq-item');
    const isOpen = item.classList.contains('open');
    document.querySelectorAll('.faq-item.open').forEach(i => i.classList.remove('open'));
    if (!isOpen) item.classList.add('open');
  }
</script>
</body>
</html>
