<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Dr. Ouseph C.J. — Physicist · Data Scientist · Adelaide, Australia</title>
<meta name="description" content="Ph.D. Physicist transitioning into data science. 15+ Q1 publications, >10TB processed, statistical rigour applied to industry problems. Based in Adelaide, AU." />

<!-- Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=IBM+Plex+Mono:wght@400;500;600&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;1,9..40,300&display=swap" rel="stylesheet" />

<style>
/* ─── TOKENS ─────────────────────────────────────────────── */
:root {
  --bg:         #020b18;
  --bg1:        #051226;
  --bg2:        #081c38;
  --surface:    #0d2545;
  --surface2:   #112e55;
  --border:     rgba(56,189,248,0.12);
  --border2:    rgba(56,189,248,0.25);

  --cyan:       #38bdf8;
  --cyan-dim:   #1e7aa0;
  --amber:      #f59e0b;
  --amber-dim:  #92600a;
  --green:      #10b981;
  --purple:     #818cf8;

  --text-1:     #e2eeff;
  --text-2:     #94aac8;
  --text-3:     #4d6a8a;

  --font-display: 'Syne', sans-serif;
  --font-mono:    'IBM Plex Mono', monospace;
  --font-body:    'DM Sans', sans-serif;

  --r:  8px;
  --r2: 16px;
  --r3: 24px;
}

/* ─── RESET ──────────────────────────────────────────────── */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body {
  background: var(--bg);
  color: var(--text-1);
  font-family: var(--font-body);
  font-size: 16px;
  line-height: 1.65;
  overflow-x: hidden;
}
a { color: var(--cyan); text-decoration: none; }
a:hover { color: var(--text-1); }
img { max-width: 100%; display: block; }

/* ─── CANVAS BACKGROUND ──────────────────────────────────── */
#canvas-bg {
  position: fixed; inset: 0; z-index: 0;
  pointer-events: none;
  opacity: 0.35;
}

/* ─── LAYOUT ─────────────────────────────────────────────── */
.container {
  position: relative; z-index: 1;
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 24px;
}

section { padding: 80px 0; }

/* ─── NAV ────────────────────────────────────────────────── */
nav {
  position: sticky; top: 0; z-index: 100;
  background: rgba(2,11,24,0.82);
  backdrop-filter: blur(16px);
  border-bottom: 1px solid var(--border);
  padding: 14px 0;
}
.nav-inner {
  display: flex; align-items: center; justify-content: space-between;
  max-width: 1100px; margin: 0 auto; padding: 0 24px;
}
.nav-brand {
  font-family: var(--font-mono);
  font-size: 14px; font-weight: 600;
  color: var(--cyan);
  letter-spacing: 0.04em;
}
.nav-links {
  display: flex; gap: 28px; list-style: none;
}
.nav-links a {
  font-size: 13px; font-weight: 500;
  color: var(--text-2);
  letter-spacing: 0.03em;
  transition: color 0.2s;
}
.nav-links a:hover { color: var(--cyan); }
.nav-cta {
  background: var(--cyan);
  color: var(--bg) !important;
  padding: 7px 18px;
  border-radius: var(--r);
  font-weight: 600 !important;
  font-size: 13px !important;
}
.nav-cta:hover { background: var(--text-1) !important; }

/* ─── HERO ───────────────────────────────────────────────── */
#hero {
  min-height: 100vh;
  display: flex; align-items: center;
  padding: 120px 0 80px;
  position: relative;
}
.hero-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 64px;
  align-items: center;
}
.hero-eyebrow {
  display: inline-flex; align-items: center; gap: 8px;
  font-family: var(--font-mono);
  font-size: 12px; font-weight: 500;
  color: var(--cyan);
  letter-spacing: 0.12em; text-transform: uppercase;
  background: rgba(56,189,248,0.08);
  border: 1px solid rgba(56,189,248,0.2);
  border-radius: 100px;
  padding: 6px 14px;
  margin-bottom: 24px;
}
.hero-eyebrow::before {
  content: '';
  width: 6px; height: 6px;
  border-radius: 50%;
  background: var(--cyan);
  animation: pulse 2s infinite;
}
@keyframes pulse {
  0%,100% { opacity:1; transform:scale(1); }
  50%      { opacity:0.4; transform:scale(0.7); }
}
.hero-title {
  font-family: var(--font-display);
  font-size: clamp(38px, 5vw, 60px);
  font-weight: 800;
  line-height: 1.08;
  letter-spacing: -0.02em;
  color: var(--text-1);
  margin-bottom: 12px;
}
.hero-title span { color: var(--cyan); }
.hero-sub {
  font-family: var(--font-mono);
  font-size: 14px;
  color: var(--amber);
  letter-spacing: 0.04em;
  margin-bottom: 20px;
}
.hero-body {
  font-size: 17px;
  color: var(--text-2);
  line-height: 1.7;
  margin-bottom: 36px;
  max-width: 520px;
}
.hero-body strong { color: var(--text-1); font-weight: 500; }
.hero-actions {
  display: flex; gap: 12px; flex-wrap: wrap;
}
.btn-primary {
  display: inline-flex; align-items: center; gap: 8px;
  background: var(--cyan);
  color: var(--bg);
  padding: 13px 26px;
  border-radius: var(--r);
  font-weight: 700;
  font-size: 15px;
  letter-spacing: 0.01em;
  transition: all 0.2s;
  cursor: pointer;
}
.btn-primary:hover {
  background: var(--text-1);
  color: var(--bg);
  transform: translateY(-2px);
  box-shadow: 0 8px 32px rgba(56,189,248,0.3);
}
.btn-secondary {
  display: inline-flex; align-items: center; gap: 8px;
  background: transparent;
  color: var(--text-1);
  padding: 13px 26px;
  border-radius: var(--r);
  font-weight: 600;
  font-size: 15px;
  border: 1px solid var(--border2);
  transition: all 0.2s;
  cursor: pointer;
}
.btn-secondary:hover {
  background: var(--surface);
  border-color: var(--cyan);
  color: var(--cyan);
  transform: translateY(-2px);
}

/* ─── HERO CARD ──────────────────────────────────────────── */
.hero-card {
  background: linear-gradient(135deg, var(--bg2) 0%, var(--surface) 100%);
  border: 1px solid var(--border2);
  border-radius: var(--r3);
  padding: 36px;
  position: relative;
  overflow: hidden;
}
.hero-card::before {
  content: '';
  position: absolute; top: 0; left: 0; right: 0; height: 2px;
  background: linear-gradient(90deg, transparent, var(--cyan), transparent);
}
.card-header {
  display: flex; align-items: center; gap: 16px; margin-bottom: 28px;
}
.avatar {
  width: 60px; height: 60px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--cyan) 0%, var(--purple) 100%);
  display: flex; align-items: center; justify-content: center;
  font-family: var(--font-display);
  font-size: 22px; font-weight: 800;
  color: var(--bg);
  flex-shrink: 0;
}
.card-name { font-family: var(--font-display); font-size: 18px; font-weight: 700; }
.card-role { font-size: 13px; color: var(--text-2); margin-top: 2px; }
.stat-grid {
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 12px; margin-bottom: 24px;
}
.stat-item {
  background: rgba(0,0,0,0.25);
  border: 1px solid var(--border);
  border-radius: var(--r);
  padding: 14px;
}
.stat-val {
  font-family: var(--font-mono);
  font-size: 22px; font-weight: 600;
  color: var(--cyan);
  line-height: 1;
}
.stat-label {
  font-size: 11px;
  color: var(--text-3);
  text-transform: uppercase;
  letter-spacing: 0.08em;
  margin-top: 4px;
}
.status-row {
  display: flex; gap: 8px; flex-wrap: wrap;
}
.pill {
  display: inline-flex; align-items: center; gap: 5px;
  font-size: 11px; font-weight: 500;
  border-radius: 100px;
  padding: 4px 10px;
  letter-spacing: 0.03em;
}
.pill-green  { background: rgba(16,185,129,0.12); color: var(--green);  border: 1px solid rgba(16,185,129,0.2); }
.pill-blue   { background: rgba(56,189,248,0.10); color: var(--cyan);   border: 1px solid rgba(56,189,248,0.2); }
.pill-amber  { background: rgba(245,158,11,0.10); color: var(--amber);  border: 1px solid rgba(245,158,11,0.2); }
.pill-purple { background: rgba(129,140,248,0.10);color: var(--purple); border: 1px solid rgba(129,140,248,0.2);}
.pill::before { content:'●'; font-size:7px; }

/* ─── SECTION LABELS ─────────────────────────────────────── */
.section-label {
  font-family: var(--font-mono);
  font-size: 11px; font-weight: 600;
  color: var(--cyan);
  letter-spacing: 0.14em; text-transform: uppercase;
  margin-bottom: 10px;
  display: flex; align-items: center; gap: 10px;
}
.section-label::after {
  content: '';
  flex: 1; max-width: 40px;
  height: 1px;
  background: var(--cyan-dim);
}
.section-title {
  font-family: var(--font-display);
  font-size: clamp(28px, 3.5vw, 42px);
  font-weight: 800;
  letter-spacing: -0.02em;
  color: var(--text-1);
  line-height: 1.1;
  margin-bottom: 16px;
}
.section-desc {
  font-size: 17px;
  color: var(--text-2);
  max-width: 560px;
  line-height: 1.7;
  margin-bottom: 48px;
}

/* ─── DIVIDER ────────────────────────────────────────────── */
.hr {
  border: none;
  border-top: 1px solid var(--border);
  margin: 0;
}

/* ─── SKILLS SECTION ─────────────────────────────────────── */
#skills { background: var(--bg1); }

.skills-tabs {
  display: flex; gap: 4px; margin-bottom: 36px;
  background: var(--bg2);
  border: 1px solid var(--border);
  border-radius: var(--r2);
  padding: 4px;
  width: fit-content;
}
.tab-btn {
  font-family: var(--font-mono);
  font-size: 12px; font-weight: 500;
  color: var(--text-2);
  background: transparent;
  border: none;
  border-radius: var(--r);
  padding: 8px 18px;
  cursor: pointer;
  letter-spacing: 0.04em;
  transition: all 0.2s;
}
.tab-btn.active {
  background: var(--surface2);
  color: var(--cyan);
}
.tab-panel { display: none; }
.tab-panel.active { display: block; }

.skills-cluster {
  display: flex; flex-wrap: wrap; gap: 8px;
  margin-bottom: 20px;
}
.skill-chip {
  font-family: var(--font-mono);
  font-size: 12px;
  color: var(--text-2);
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--r);
  padding: 6px 13px;
  transition: all 0.15s;
}
.skill-chip:hover {
  border-color: var(--cyan);
  color: var(--cyan);
  background: rgba(56,189,248,0.05);
}
.skill-chip.expert { border-color: rgba(56,189,248,0.3); color: var(--cyan); }
.skill-chip.advanced { border-color: rgba(16,185,129,0.3); color: var(--green); }
.skill-chip.proficient { border-color: rgba(245,158,11,0.25); color: var(--amber); }

.cluster-label {
  font-size: 11px; font-weight: 500;
  color: var(--text-3);
  text-transform: uppercase;
  letter-spacing: 0.1em;
  margin-bottom: 10px;
}

.stats-row {
  display: grid;
  grid-template-columns: repeat(4,1fr);
  gap: 1px;
  background: var(--border);
  border: 1px solid var(--border);
  border-radius: var(--r2);
  overflow: hidden;
  margin-top: 48px;
}
.stats-cell {
  background: var(--bg2);
  padding: 28px 24px;
  text-align: center;
}
.stats-cell-val {
  font-family: var(--font-display);
  font-size: 36px; font-weight: 800;
  color: var(--cyan);
  line-height: 1;
}
.stats-cell-label {
  font-size: 12px; color: var(--text-3);
  text-transform: uppercase; letter-spacing: 0.08em;
  margin-top: 6px;
}

/* ─── PROJECTS ───────────────────────────────────────────── */
.projects-grid {
  display: grid;
  grid-template-columns: repeat(2,1fr);
  gap: 20px;
}
.project-card {
  background: var(--bg2);
  border: 1px solid var(--border);
  border-radius: var(--r2);
  padding: 28px;
  position: relative;
  overflow: hidden;
  transition: all 0.25s;
}
.project-card::after {
  content: '';
  position: absolute; inset: 0;
  background: linear-gradient(135deg, rgba(56,189,248,0.04) 0%, transparent 60%);
  opacity: 0;
  transition: opacity 0.25s;
}
.project-card:hover {
  border-color: var(--border2);
  transform: translateY(-3px);
  box-shadow: 0 12px 40px rgba(0,0,0,0.4);
}
.project-card:hover::after { opacity: 1; }
.project-icon {
  font-size: 28px; margin-bottom: 16px;
  display: block;
}
.project-title {
  font-family: var(--font-display);
  font-size: 19px; font-weight: 700;
  color: var(--text-1); margin-bottom: 8px;
}
.project-desc {
  font-size: 14px; color: var(--text-2);
  line-height: 1.6; margin-bottom: 20px;
}
.project-tags {
  display: flex; flex-wrap: wrap; gap: 6px; margin-bottom: 20px;
}
.tag {
  font-family: var(--font-mono);
  font-size: 10px; font-weight: 500;
  color: var(--text-3);
  background: rgba(255,255,255,0.04);
  border: 1px solid var(--border);
  border-radius: 4px;
  padding: 3px 8px;
  text-transform: uppercase; letter-spacing: 0.06em;
}
.project-link {
  font-family: var(--font-mono);
  font-size: 12px; font-weight: 600;
  color: var(--cyan);
  display: inline-flex; align-items: center; gap: 6px;
  transition: gap 0.2s;
}
.project-link:hover { gap: 10px; }

/* ─── PUBLICATIONS ───────────────────────────────────────── */
#research { background: var(--bg1); }

.pub-list { display: flex; flex-direction: column; gap: 2px; }
.pub-item {
  display: grid;
  grid-template-columns: 52px 1fr auto;
  gap: 20px;
  align-items: start;
  padding: 20px;
  border-radius: var(--r);
  transition: background 0.2s;
  border-left: 2px solid transparent;
}
.pub-item:hover {
  background: var(--bg2);
  border-left-color: var(--cyan);
}
.pub-year {
  font-family: var(--font-mono);
  font-size: 12px; font-weight: 600;
  color: var(--cyan);
  padding-top: 2px;
  letter-spacing: 0.04em;
}
.pub-title {
  font-size: 15px; font-weight: 500;
  color: var(--text-1); line-height: 1.5;
  margin-bottom: 4px;
}
.pub-journal {
  font-family: var(--font-mono);
  font-size: 11px; color: var(--text-3);
  font-style: italic;
}
.pub-badge {
  font-family: var(--font-mono);
  font-size: 10px; font-weight: 600;
  background: rgba(56,189,248,0.1);
  color: var(--cyan);
  border: 1px solid rgba(56,189,248,0.2);
  border-radius: 4px;
  padding: 3px 8px;
  white-space: nowrap;
  align-self: start;
}
.pub-badge.submitted {
  background: rgba(245,158,11,0.1);
  color: var(--amber);
  border-color: rgba(245,158,11,0.2);
}

/* ─── EXPERIENCE ─────────────────────────────────────────── */
.timeline { position: relative; padding-left: 28px; }
.timeline::before {
  content: '';
  position: absolute; left: 6px; top: 0; bottom: 0; width: 1px;
  background: linear-gradient(to bottom, var(--cyan), transparent);
}
.tl-item {
  position: relative;
  padding-bottom: 40px;
}
.tl-item::before {
  content: '';
  position: absolute; left: -25px; top: 4px;
  width: 10px; height: 10px; border-radius: 50%;
  background: var(--bg);
  border: 2px solid var(--cyan);
}
.tl-period {
  font-family: var(--font-mono);
  font-size: 11px; font-weight: 500;
  color: var(--cyan); letter-spacing: 0.06em;
  text-transform: uppercase;
  margin-bottom: 6px;
}
.tl-role {
  font-family: var(--font-display);
  font-size: 17px; font-weight: 700;
  color: var(--text-1); margin-bottom: 2px;
}
.tl-org {
  font-size: 14px; color: var(--text-2);
  margin-bottom: 14px;
}
.tl-bullets { list-style: none; }
.tl-bullets li {
  font-size: 14px; color: var(--text-2);
  padding: 3px 0 3px 16px;
  position: relative; line-height: 1.6;
}
.tl-bullets li::before {
  content: '▸';
  position: absolute; left: 0;
  color: var(--cyan-dim);
  font-size: 10px; top: 6px;
}

/* ─── TALKS ──────────────────────────────────────────────── */
.talks-grid {
  display: grid; grid-template-columns: repeat(2,1fr); gap: 12px;
}
.talk-card {
  background: var(--bg2);
  border: 1px solid var(--border);
  border-radius: var(--r);
  padding: 18px 20px;
  display: flex; gap: 16px; align-items: start;
  transition: border-color 0.2s;
}
.talk-card:hover { border-color: var(--border2); }
.talk-date {
  font-family: var(--font-mono);
  font-size: 11px; color: var(--amber);
  white-space: nowrap; padding-top: 2px;
}
.talk-title { font-size: 13px; font-weight: 500; color: var(--text-1); margin-bottom: 3px; }
.talk-venue { font-size: 12px; color: var(--text-3); }

/* ─── ACHIEVEMENTS ───────────────────────────────────────── */
#achievements { background: var(--bg1); }
.ach-grid { display: grid; grid-template-columns: repeat(3,1fr); gap: 16px; }
.ach-card {
  background: var(--bg2);
  border: 1px solid var(--border);
  border-radius: var(--r2);
  padding: 24px;
  transition: all 0.2s;
}
.ach-card:hover {
  border-color: var(--border2);
  transform: translateY(-2px);
}
.ach-icon { font-size: 24px; margin-bottom: 12px; }
.ach-title { font-size: 14px; font-weight: 600; color: var(--text-1); margin-bottom: 4px; }
.ach-detail { font-size: 13px; color: var(--text-2); line-height: 1.5; }

/* ─── CONTACT ────────────────────────────────────────────── */
#contact {
  background: radial-gradient(ellipse at 50% 0%, rgba(56,189,248,0.07) 0%, transparent 70%);
  border-top: 1px solid var(--border);
}
.contact-inner {
  text-align: center; max-width: 680px; margin: 0 auto;
}
.contact-title {
  font-family: var(--font-display);
  font-size: clamp(30px, 4vw, 50px);
  font-weight: 800; letter-spacing: -0.02em;
  color: var(--text-1); margin-bottom: 16px;
}
.contact-sub {
  font-size: 17px; color: var(--text-2);
  margin-bottom: 40px; line-height: 1.6;
}
.contact-links {
  display: flex; flex-wrap: wrap; justify-content: center; gap: 12px;
  margin-bottom: 48px;
}
.contact-link {
  display: inline-flex; align-items: center; gap: 10px;
  font-weight: 600; font-size: 14px;
  padding: 12px 22px;
  border-radius: var(--r);
  border: 1px solid var(--border2);
  color: var(--text-1);
  background: var(--surface);
  transition: all 0.2s;
}
.contact-link:hover {
  background: var(--surface2);
  border-color: var(--cyan);
  color: var(--cyan);
  transform: translateY(-2px);
}
.contact-link svg { width: 16px; height: 16px; fill: currentColor; flex-shrink: 0; }
.looking-for {
  background: var(--bg2);
  border: 1px solid var(--border);
  border-radius: var(--r2);
  padding: 28px 32px;
  text-align: left;
}
.lf-title {
  font-family: var(--font-mono);
  font-size: 11px; color: var(--cyan);
  text-transform: uppercase; letter-spacing: 0.1em;
  margin-bottom: 16px;
}
.lf-grid { display: grid; grid-template-columns: repeat(2,1fr); gap: 10px; }
.lf-item {
  display: flex; gap: 10px; align-items: start;
  font-size: 14px; color: var(--text-2); line-height: 1.5;
}
.lf-item::before {
  content: '▸';
  color: var(--cyan);
  font-size: 10px; margin-top: 4px; flex-shrink: 0;
}

/* ─── FOOTER ─────────────────────────────────────────────── */
footer {
  border-top: 1px solid var(--border);
  padding: 24px;
  text-align: center;
  font-family: var(--font-mono);
  font-size: 12px;
  color: var(--text-3);
}

/* ─── ANIMATIONS ─────────────────────────────────────────── */
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.reveal.visible {
  opacity: 1;
  transform: none;
}
.reveal-delay-1 { transition-delay: 0.1s; }
.reveal-delay-2 { transition-delay: 0.2s; }
.reveal-delay-3 { transition-delay: 0.3s; }

/* ─── RESPONSIVE ─────────────────────────────────────────── */
@media (max-width: 900px) {
  .hero-grid { grid-template-columns: 1fr; gap: 40px; }
  .projects-grid { grid-template-columns: 1fr; }
  .stats-row { grid-template-columns: repeat(2,1fr); }
  .talks-grid { grid-template-columns: 1fr; }
  .ach-grid { grid-template-columns: repeat(2,1fr); }
  .lf-grid { grid-template-columns: 1fr; }
}
@media (max-width: 600px) {
  .nav-links { display: none; }
  .stats-row { grid-template-columns: 1fr 1fr; }
  .ach-grid { grid-template-columns: 1fr; }
  .pub-item { grid-template-columns: 40px 1fr; }
  .pub-badge { display: none; }
  section { padding: 56px 0; }
}
</style>
</head>
<body>

<!-- Particle canvas background -->
<canvas id="canvas-bg"></canvas>

<!-- ── NAV ──────────────────────────────────────────────── -->
<nav aria-label="Main navigation">
  <div class="nav-inner">
    <span class="nav-brand">// ouseph444</span>
    <ul class="nav-links">
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#research">Research</a></li>
      <li><a href="#experience">Experience</a></li>
      <li><a href="#contact" class="nav-cta">Hire Me</a></li>
    </ul>
  </div>
</nav>

<!-- ── HERO ─────────────────────────────────────────────── -->
<section id="hero">
  <div class="container">
    <div class="hero-grid">

      <div class="hero-left">
        <div class="hero-eyebrow">Available for hire · Adelaide, AU</div>
        <h1 class="hero-title">
          Dr. Ouseph<br><span>C.J.</span>
        </h1>
        <p class="hero-sub">Ph.D. Physics → Data Science &amp; Quantitative Analytics</p>
        <p class="hero-body">
          I spent six years solving hard problems with data — designing HPC pipelines for <strong>multi-terabyte collider datasets</strong>, publishing <strong>15+ Q1 papers</strong>, and building tools that turn abstract models into decisions. Now I bring that same rigour to industry.
        </p>
        <div class="hero-actions">
          <a href="mailto:ouseph444@gmail.com" class="btn-primary">
            <svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>
            Get in touch
          </a>
          <a href="https://ouseph444.github.io/Personal_Webpage.github.io/" target="_blank" class="btn-secondary">
            View Portfolio →
          </a>
        </div>
      </div>

      <div class="hero-right">
        <div class="hero-card">
          <div class="card-header">
            <div class="avatar">CJ</div>
            <div>
              <div class="card-name">Dr. Ouseph C.J.</div>
              <div class="card-role">Senior Research Scientist · Data Scientist</div>
            </div>
          </div>
          <div class="stat-grid">
            <div class="stat-item">
              <div class="stat-val">15+</div>
              <div class="stat-label">Q1 Publications</div>
            </div>
            <div class="stat-item">
              <div class="stat-val">&gt;10TB</div>
              <div class="stat-label">Data Processed</div>
            </div>
            <div class="stat-item">
              <div class="stat-val">20+</div>
              <div class="stat-label">Int'l Talks</div>
            </div>
            <div class="stat-item">
              <div class="stat-val">5+</div>
              <div class="stat-label">Countries</div>
            </div>
          </div>
          <div class="status-row">
            <span class="pill pill-green">Open to work</span>
            <span class="pill pill-blue">Perm. Resident AU</span>
            <span class="pill pill-amber">Adelaide SA</span>
            <span class="pill pill-purple">Ph.D. Physics</span>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<hr class="hr" />

<!-- ── SKILLS ────────────────────────────────────────────── -->
<section id="skills">
  <div class="container">
    <div class="reveal">
      <div class="section-label">Technical Stack</div>
      <h2 class="section-title">Skills &amp; Competencies</h2>
      <p class="section-desc">Physics-grade statistical rigour applied to real-world data engineering, machine learning, and visualisation challenges.</p>
    </div>

    <div class="skills-tabs reveal reveal-delay-1">
      <button class="tab-btn active" onclick="switchTab(event,'programming')">Languages</button>
      <button class="tab-btn" onclick="switchTab(event,'ml')">ML &amp; Stats</button>
      <button class="tab-btn" onclick="switchTab(event,'infra')">Infra &amp; Viz</button>
    </div>

    <div id="tab-programming" class="tab-panel active reveal reveal-delay-2">
      <div class="cluster-label">Expert</div>
      <div class="skills-cluster">
        <span class="skill-chip expert">Python</span>
        <span class="skill-chip expert">Mathematica</span>
        <span class="skill-chip expert">Bash / Shell</span>
        <span class="skill-chip expert">LaTeX</span>
      </div>
      <div class="cluster-label">Proficient</div>
      <div class="skills-cluster">
        <span class="skill-chip advanced">R</span>
        <span class="skill-chip advanced">SQL</span>
        <span class="skill-chip advanced">JavaScript</span>
        <span class="skill-chip advanced">HTML5 / CSS3</span>
      </div>
    </div>

    <div id="tab-ml" class="tab-panel reveal reveal-delay-2">
      <div class="cluster-label">Statistical Methods</div>
      <div class="skills-cluster">
        <span class="skill-chip expert">Bayesian Inference</span>
        <span class="skill-chip expert">Monte Carlo Simulation</span>
        <span class="skill-chip expert">Hypothesis Testing</span>
        <span class="skill-chip expert">Likelihood Analysis</span>
        <span class="skill-chip expert">Time Series Analysis</span>
        <span class="skill-chip expert">Uncertainty Quantification</span>
        <span class="skill-chip advanced">A/B Testing</span>
      </div>
      <div class="cluster-label">ML Libraries</div>
      <div class="skills-cluster">
        <span class="skill-chip expert">NumPy · SciPy · Pandas</span>
        <span class="skill-chip advanced">Scikit-learn</span>
        <span class="skill-chip advanced">TensorFlow</span>
        <span class="skill-chip proficient">XGBoost</span>
        <span class="skill-chip advanced">Feature Engineering</span>
        <span class="skill-chip advanced">ETL Pipelines</span>
      </div>
    </div>

    <div id="tab-infra" class="tab-panel reveal reveal-delay-2">
      <div class="cluster-label">Visualisation &amp; BI</div>
      <div class="skills-cluster">
        <span class="skill-chip expert">Matplotlib · Seaborn</span>
        <span class="skill-chip advanced">Plotly Dash</span>
        <span class="skill-chip proficient">Power BI</span>
        <span class="skill-chip advanced">ROOT (CERN)</span>
      </div>
      <div class="cluster-label">Infrastructure</div>
      <div class="skills-cluster">
        <span class="skill-chip expert">Linux (5+ yrs)</span>
        <span class="skill-chip advanced">HPC Clusters · SLURM</span>
        <span class="skill-chip advanced">Parallel Computing</span>
        <span class="skill-chip proficient">Git / GitHub</span>
      </div>
      <div class="cluster-label">Scientific Computing</div>
      <div class="skills-cluster">
        <span class="skill-chip expert">MadGraph · Pythia</span>
        <span class="skill-chip advanced">Delphes · FeynRules · FeynCalc</span>
      </div>
    </div>

    <div class="stats-row reveal reveal-delay-3">
      <div class="stats-cell">
        <div class="stats-cell-val">15+</div>
        <div class="stats-cell-label">Q1 Papers</div>
      </div>
      <div class="stats-cell">
        <div class="stats-cell-val">&gt;10TB</div>
        <div class="stats-cell-label">Processed</div>
      </div>
      <div class="stats-cell">
        <div class="stats-cell-val">12</div>
        <div class="stats-cell-label">HPC Projects</div>
      </div>
      <div class="stats-cell">
        <div class="stats-cell-val">3</div>
        <div class="stats-cell-label">Mentored → Q1</div>
      </div>
    </div>
  </div>
</section>

<hr class="hr" />

<!-- ── PROJECTS ───────────────────────────────────────────── -->
<section id="projects">
  <div class="container">
    <div class="reveal">
      <div class="section-label">Portfolio</div>
      <h2 class="section-title">Featured Projects</h2>
      <p class="section-desc">From production PWAs to multi-terabyte physics pipelines — software that ships and research that publishes.</p>
    </div>

    <div class="projects-grid">

      <div class="project-card reveal reveal-delay-1">
        <span class="project-icon">🏥</span>
        <div class="project-title">Roster Hub — Shift &amp; Team Manager</div>
        <p class="project-desc">Production-grade Progressive Web App for healthcare workforce scheduling. Real-time Firebase sync, offline support, multi-timezone awareness, gamified UX — deployed across 8+ countries.</p>
        <div class="project-tags">
          <span class="tag">HTML5</span><span class="tag">Firebase</span><span class="tag">Tailwind</span><span class="tag">PWA</span><span class="tag">ES2022</span>
        </div>
        <a href="https://github.com/ouseph444/Shift-Manager" target="_blank" class="project-link">View on GitHub →</a>
      </div>

      <div class="project-card reveal reveal-delay-2">
        <span class="project-icon">🌌</span>
        <div class="project-title">Inflation Explorer</div>
        <p class="project-desc">Interactive research dashboard for inflationary cosmology. Real-time parameter sweeps with Planck 2018 and BICEP/Keck observational constraints overlaid — both a research tool and teaching aid.</p>
        <div class="project-tags">
          <span class="tag">Python</span><span class="tag">SciPy</span><span class="tag">Plotly Dash</span><span class="tag">NumPy</span>
        </div>
        <a href="https://github.com/ouseph444/Inflation-Explorer" target="_blank" class="project-link">View on GitHub →</a>
      </div>

      <div class="project-card reveal reveal-delay-1">
        <span class="project-icon">⚛️</span>
        <div class="project-title">LHC Data Analysis Pipeline</div>
        <p class="project-desc">End-to-end HPC pipeline for rare-signal extraction from multi-terabyte LHC simulations. Theory → event generation → detector simulation → ML classification → published exclusion limits.</p>
        <div class="project-tags">
          <span class="tag">Python</span><span class="tag">ROOT</span><span class="tag">MadGraph</span><span class="tag">Scikit-learn</span><span class="tag">TensorFlow</span>
        </div>
        <a href="https://github.com/ouseph444/LHE-file" target="_blank" class="project-link">View on GitHub →</a>
      </div>

      <div class="project-card reveal reveal-delay-2">
        <span class="project-icon">🌐</span>
        <div class="project-title">Personal Academic Webpage</div>
        <p class="project-desc">Fully responsive single-page portfolio — biography, research, publications with DOI + arXiv links, contact form. Zero-cost GitHub Pages CI/CD with Intersection Observer scroll animations.</p>
        <div class="project-tags">
          <span class="tag">HTML5</span><span class="tag">CSS3</span><span class="tag">Vanilla JS</span><span class="tag">GitHub Pages</span>
        </div>
        <a href="https://ouseph444.github.io/Personal_Webpage.github.io/" target="_blank" class="project-link">View Live Site →</a>
      </div>

    </div>
  </div>
</section>

<hr class="hr" />

<!-- ── RESEARCH ───────────────────────────────────────────── -->
<section id="research">
  <div class="container">
    <div class="reveal">
      <div class="section-label">Publications &amp; Talks</div>
      <h2 class="section-title">Research &amp; Scholarship</h2>
      <p class="section-desc">15+ peer-reviewed publications in JHEP, PRD, EPJC, JPG. Spanning collider phenomenology, dark matter, cosmology, and neutrino physics.</p>
    </div>

    <div class="pub-list reveal">
      <div class="pub-item">
        <div class="pub-year">2025</div>
        <div>
          <div class="pub-title">Probing Double-Peaked Gamma-Ray Spectra from Primordial Black Holes</div>
          <div class="pub-journal">arXiv preprint · arXiv:2507.16244</div>
        </div>
        <a href="https://arxiv.org/abs/2507.16244" target="_blank" class="pub-badge submitted">Submitted</a>
      </div>
      <div class="pub-item">
        <div class="pub-year">2025</div>
        <div>
          <div class="pub-title">Searching for Dark Photon Tridents Through PBH Signatures</div>
          <div class="pub-journal">arXiv preprint · arXiv:2503.04175</div>
        </div>
        <a href="https://arxiv.org/abs/2503.04175" target="_blank" class="pub-badge submitted">Submitted</a>
      </div>
      <div class="pub-item">
        <div class="pub-year">2025</div>
        <div>
          <div class="pub-title">New Physics Search at the CEPC: a General Perspective</div>
          <div class="pub-journal">Chinese Physics C · arXiv:2505.24810</div>
        </div>
        <a href="https://arxiv.org/abs/2505.24810" target="_blank" class="pub-badge">Published</a>
      </div>
      <div class="pub-item">
        <div class="pub-year">2024</div>
        <div>
          <div class="pub-title">Probing dark photons from a light scalar at Belle II</div>
          <div class="pub-journal">Journal of High Energy Physics (JHEP)</div>
        </div>
        <a href="https://doi.org/10.1007/JHEP05(2024)094" target="_blank" class="pub-badge">JHEP</a>
      </div>
      <div class="pub-item">
        <div class="pub-year">2024</div>
        <div>
          <div class="pub-title">Exploring interference effects between two ALP operators at the LHC</div>
          <div class="pub-journal">Journal of High Energy Physics (JHEP)</div>
        </div>
        <a href="https://doi.org/10.1007/JHEP09(2024)101" target="_blank" class="pub-badge">JHEP</a>
      </div>
      <div class="pub-item">
        <div class="pub-year">2024</div>
        <div>
          <div class="pub-title">NANOGrav and PTA signals from modified Higgs inflation</div>
          <div class="pub-journal">European Physical Journal C (EPJC)</div>
        </div>
        <a href="https://doi.org/10.1140/epjc/s10052-024-13268-6" target="_blank" class="pub-badge">EPJC</a>
      </div>
      <div class="pub-item">
        <div class="pub-year">2023</div>
        <div>
          <div class="pub-title">Axionlike particle search at Higgs factories</div>
          <div class="pub-journal">Physical Review D</div>
        </div>
        <a href="https://doi.org/10.1103/PhysRevD.108.035003" target="_blank" class="pub-badge">PRD</a>
      </div>
      <div class="pub-item">
        <div class="pub-year">2022</div>
        <div>
          <div class="pub-title">Sensitivities on dark photon from forward physics experiments</div>
          <div class="pub-journal">Journal of High Energy Physics (JHEP)</div>
        </div>
        <a href="https://doi.org/10.1007/JHEP10(2022)196" target="_blank" class="pub-badge">JHEP</a>
      </div>
    </div>

    <div style="margin-top:20px; display:flex; gap:12px; flex-wrap:wrap;" class="reveal">
      <a href="https://inspirehep.net/authors/1842258" target="_blank" class="btn-secondary" style="font-size:13px;padding:10px 20px;">Full list on InspireHEP →</a>
      <a href="https://scholar.google.com/citations?user=GgLr0BsAAAAJ" target="_blank" class="btn-secondary" style="font-size:13px;padding:10px 20px;">Citation metrics →</a>
    </div>

    <div style="margin-top:64px;" class="reveal">
      <div class="section-label">Invited Talks</div>
      <h3 style="font-family:var(--font-display);font-size:22px;font-weight:700;margin-bottom:24px;">Selected International Presentations</h3>
      <div class="talks-grid">
        <div class="talk-card">
          <div class="talk-date">Apr 2025</div>
          <div>
            <div class="talk-title">Dark Photon Tridents Through PBH Signatures</div>
            <div class="talk-venue">NTHU, Taiwan</div>
          </div>
        </div>
        <div class="talk-card">
          <div class="talk-date">Mar 2025</div>
          <div>
            <div class="talk-title">Dark Photon Tridents Through PBH Signatures</div>
            <div class="talk-venue">University of Adelaide, Australia</div>
          </div>
        </div>
        <div class="talk-card">
          <div class="talk-date">Mar 2024</div>
          <div>
            <div class="talk-title">New Physics at the Forward Physics Facility</div>
            <div class="talk-venue">University of Notre Dame, USA</div>
          </div>
        </div>
        <div class="talk-card">
          <div class="talk-date">Jun 2024</div>
          <div>
            <div class="talk-title">New Physics at the Forward Physics Facility</div>
            <div class="talk-venue">Academia Sinica, Taiwan</div>
          </div>
        </div>
        <div class="talk-card">
          <div class="talk-date">Jan 2022</div>
          <div>
            <div class="talk-title">Nonstandard Neutrino and Z′ at FASERν</div>
            <div class="talk-venue">CERN, Geneva, Switzerland</div>
          </div>
        </div>
        <div class="talk-card">
          <div class="talk-date">Oct 2022</div>
          <div>
            <div class="talk-title">BSM Physics at FASERν</div>
            <div class="talk-venue">NuINT 2022 · Seoul National University</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<hr class="hr" />

<!-- ── EXPERIENCE ─────────────────────────────────────────── -->
<section id="experience">
  <div class="container">
    <div class="reveal">
      <div class="section-label">Career</div>
      <h2 class="section-title">Experience</h2>
      <p class="section-desc">Research-driven career spanning India, Taiwan, South Korea, and Australia — applying advanced statistical methods to large-scale data at every step.</p>
    </div>

    <div class="timeline reveal reveal-delay-1">

      <div class="tl-item">
        <div class="tl-period">Sep 2024 – Aug 2025</div>
        <div class="tl-role">Senior Research Scientist</div>
        <div class="tl-org">Seoul National University of Science &amp; Technology, South Korea</div>
        <ul class="tl-bullets">
          <li>Designed Python pipelines (NumPy · SciPy · Pandas) for &gt;10TB dataset processing on Linux/HPC</li>
          <li>Applied Bayesian inference, time series analysis, hypothesis testing, and likelihood estimation to complex physics datasets</li>
          <li>Led international collaborations across 5+ countries; secured competitive research grants</li>
          <li>Supervised early-career researchers on computational techniques and analysis methodology</li>
        </ul>
      </div>

      <div class="tl-item">
        <div class="tl-period">Mar 2025 – May 2025</div>
        <div class="tl-role">Senior Visiting Research Scientist</div>
        <div class="tl-org">University of Adelaide, Australia</div>
        <ul class="tl-bullets">
          <li>Computational statistics, data simulation, and numerical modelling using Python and Mathematica</li>
          <li>Collaborated with multidisciplinary teams on quantitative problem-solving</li>
        </ul>
      </div>

      <div class="tl-item">
        <div class="tl-period">Sep 2019 – Jul 2024</div>
        <div class="tl-role">Doctoral Researcher &amp; Teaching Assistant</div>
        <div class="tl-org">National Tsing Hua University (NTHU), Taiwan · Ph.D. Physics</div>
        <ul class="tl-bullets">
          <li>HPC pipelines for multi-terabyte collider and cosmological datasets → 15+ Q1 publications</li>
          <li>Applied hypothesis testing, Monte Carlo simulation, and Bayesian methods at scale</li>
          <li>TA: Advanced Mathematical Science (2022–23) and Electrodynamics (2020–21)</li>
          <li>Mentored 3 students (2 M.Sc. + 1 exchange) → all co-authored Q1 papers within 12 months</li>
        </ul>
      </div>

    </div>
  </div>
</section>

<hr class="hr" />

<!-- ── ACHIEVEMENTS ───────────────────────────────────────── -->
<section id="achievements">
  <div class="container">
    <div class="reveal">
      <div class="section-label">Honours</div>
      <h2 class="section-title">Achievements &amp; Awards</h2>
    </div>
    <div class="ach-grid reveal reveal-delay-1">
      <div class="ach-card">
        <div class="ach-icon">🎓</div>
        <div class="ach-title">NTHU International Ph.D. Scholarship</div>
        <div class="ach-detail">5-year full scholarship (tuition + stipend). Highly competitive international award. 2019–2024.</div>
      </div>
      <div class="ach-card">
        <div class="ach-icon">🌏</div>
        <div class="ach-title">TEEP International Grant</div>
        <div class="ach-detail">Taiwan Experience Education Program international education scholarship, 2019.</div>
      </div>
      <div class="ach-card">
        <div class="ach-icon">✈️</div>
        <div class="ach-title">Competitive Travel Grants</div>
        <div class="ach-detail">Multiple grants for international conferences across Asia, Europe, and the Americas. 2019–2024.</div>
      </div>
      <div class="ach-card">
        <div class="ach-icon">🥇</div>
        <div class="ach-title">Top 6% — All-India JAM Physics</div>
        <div class="ach-detail">Rank 694 / 10,989 candidates nationwide in the Joint Admission Test for M.Sc. Physics, 2016.</div>
      </div>
      <div class="ach-card">
        <div class="ach-icon">📜</div>
        <div class="ach-title">PTE Academic Certification</div>
        <div class="ach-detail">Professional English proficiency certification, 2023.</div>
      </div>
      <div class="ach-card">
        <div class="ach-icon">🎤</div>
        <div class="ach-title">20+ International Talks</div>
        <div class="ach-detail">Invited presentations at CERN, Notre Dame, Academia Sinica, Seoul National University, and more.</div>
      </div>
    </div>
  </div>
</section>

<hr class="hr" />

<!-- ── CONTACT ────────────────────────────────────────────── -->
<section id="contact">
  <div class="container">
    <div class="contact-inner reveal">
      <div class="section-label" style="justify-content:center;">Let's connect</div>
      <h2 class="contact-title">Open to Work</h2>
      <p class="contact-sub">If your team wrestles with large, messy, high-stakes data and needs someone who treats statistical rigour as non-negotiable — let's talk.</p>

      <div class="contact-links">
        <a href="mailto:ouseph444@gmail.com" class="contact-link">
          <svg viewBox="0 0 24 24"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6" style="fill:none;stroke:currentColor;stroke-width:2"/></svg>
          ouseph444@gmail.com
        </a>
        <a href="https://linkedin.com/in/c-j-ouseph-p-hd-3099251a9/" target="_blank" class="contact-link">
          <svg viewBox="0 0 24 24"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect x="2" y="9" width="4" height="12"/><circle cx="4" cy="4" r="2"/></svg>
          LinkedIn
        </a>
        <a href="https://github.com/ouseph444" target="_blank" class="contact-link">
          <svg viewBox="0 0 24 24"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"/></svg>
          GitHub
        </a>
        <a href="https://scholar.google.com/citations?user=GgLr0BsAAAAJ" target="_blank" class="contact-link">
          <svg viewBox="0 0 24 24"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg>
          Google Scholar
        </a>
        <a href="https://inspirehep.net/authors/1842258" target="_blank" class="contact-link">
          <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M12 8v4l3 3"/></svg>
          InspireHEP
        </a>
      </div>

      <div class="looking-for">
        <div class="lf-title">Roles I'm seeking</div>
        <div class="lf-grid">
          <div class="lf-item">Data Scientist / Senior Data Scientist — statistical depth + ML pipelines</div>
          <div class="lf-item">Quantitative Analyst / Research Scientist — finance, climate, biotech, government</div>
          <div class="lf-item">Machine Learning Engineer — applied ML with strong statistical foundations</div>
          <div class="lf-item">Data &amp; Research Consultant — uncertainty quantification, complex systems</div>
        </div>
        <div style="margin-top:18px; display:flex; flex-wrap:wrap; gap:8px;">
          <span class="pill pill-blue">📍 Adelaide SA · Remote OK</span>
          <span class="pill pill-green">✅ Available immediately</span>
          <span class="pill pill-amber">🛂 Australian PR — no sponsorship needed</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ── FOOTER ─────────────────────────────────────────────── -->
<footer>
  <span>Dr. Ouseph C.J. · Adelaide, SA, Australia · Last updated June 2026</span>
  &nbsp;·&nbsp;
  <span>"From the fundamental laws of the universe to the patterns in your data."</span>
</footer>


<!-- ── SCRIPTS ────────────────────────────────────────────── -->
<script>
/* Particle canvas */
(function () {
  const canvas = document.getElementById('canvas-bg');
  const ctx = canvas.getContext('2d');
  let W, H, particles = [];

  function resize() {
    W = canvas.width  = window.innerWidth;
    H = canvas.height = window.innerHeight;
  }
  resize();
  window.addEventListener('resize', resize);

  const N = 55;
  for (let i = 0; i < N; i++) {
    particles.push({
      x: Math.random() * W,
      y: Math.random() * H,
      vx: (Math.random() - 0.5) * 0.3,
      vy: (Math.random() - 0.5) * 0.3,
      r: Math.random() * 1.8 + 0.4,
      alpha: Math.random() * 0.6 + 0.15
    });
  }

  function draw() {
    ctx.clearRect(0, 0, W, H);

    /* Connection lines */
    for (let i = 0; i < N; i++) {
      for (let j = i + 1; j < N; j++) {
        const dx = particles[i].x - particles[j].x;
        const dy = particles[i].y - particles[j].y;
        const dist = Math.sqrt(dx * dx + dy * dy);
        if (dist < 140) {
          ctx.beginPath();
          ctx.strokeStyle = `rgba(56,189,248,${0.12 * (1 - dist / 140)})`;
          ctx.lineWidth = 0.5;
          ctx.moveTo(particles[i].x, particles[i].y);
          ctx.lineTo(particles[j].x, particles[j].y);
          ctx.stroke();
        }
      }
    }

    /* Dots */
    particles.forEach(p => {
      ctx.beginPath();
      ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
      ctx.fillStyle = `rgba(56,189,248,${p.alpha})`;
      ctx.fill();

      p.x += p.vx;
      p.y += p.vy;
      if (p.x < 0 || p.x > W) p.vx *= -1;
      if (p.y < 0 || p.y > H) p.vy *= -1;
    });

    requestAnimationFrame(draw);
  }
  draw();
})();

/* Tab switching */
function switchTab(evt, id) {
  document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
  document.querySelectorAll('.tab-panel').forEach(p => p.classList.remove('active'));
  evt.currentTarget.classList.add('active');
  document.getElementById('tab-' + id).classList.add('active');
}

/* Scroll reveal */
(function () {
  const obs = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); obs.unobserve(e.target); } });
  }, { threshold: 0.12 });
  document.querySelectorAll('.reveal').forEach(el => obs.observe(el));
})();
</script>

</body>
</html>
