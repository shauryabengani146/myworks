<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shaurya Bengani — Works</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@300;400;500&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --ink: #0e0d0b;
  --paper: #f5f0e8;
  --cream: #ede7d6;
  --accent: #c8451a;
  --gold: #b8912a;
  --muted: #8a7f6e;
  --border: #d4ccba;
  --card-bg: #faf7f2;
}

html { scroll-behavior: smooth; }

body {
  font-family: 'DM Mono', monospace;
  background: var(--paper);
  color: var(--ink);
  min-height: 100vh;
  cursor: none;
  overflow-x: hidden;
}

/* ── CUSTOM CURSOR ── */
#cursor {
  position: fixed;
  width: 12px;
  height: 12px;
  background: var(--accent);
  border-radius: 50%;
  pointer-events: none;
  z-index: 9999;
  transform: translate(-50%, -50%);
  transition: transform 0.08s, width 0.2s, height 0.2s, background 0.2s;
  mix-blend-mode: multiply;
}
#cursorRing {
  position: fixed;
  width: 36px;
  height: 36px;
  border: 1.5px solid var(--accent);
  border-radius: 50%;
  pointer-events: none;
  z-index: 9998;
  transform: translate(-50%, -50%);
  transition: transform 0.18s ease-out, width 0.25s, height 0.25s, opacity 0.2s;
  opacity: 0.5;
}
body:has(a:hover) #cursor, body:has(.card:hover) #cursor {
  width: 20px; height: 20px;
}
body:has(a:hover) #cursorRing, body:has(.card:hover) #cursorRing {
  width: 60px; height: 60px; opacity: 0.2;
}

/* ── NOISE TEXTURE ── */
body::after {
  content: '';
  position: fixed;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
  pointer-events: none;
  z-index: 1000;
  opacity: 0.6;
}

/* ── HEADER ── */
header {
  border-bottom: 1px solid var(--border);
  padding: 0 48px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 64px;
  position: sticky;
  top: 0;
  background: rgba(245,240,232,0.92);
  backdrop-filter: blur(12px);
  z-index: 100;
}

.header-name {
  font-family: 'DM Mono', monospace;
  font-size: 0.72rem;
  font-weight: 500;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: var(--ink);
  text-decoration: none;
}

.header-tag {
  font-size: 0.68rem;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--muted);
}

/* ── HERO ── */
.hero {
  padding: 90px 48px 70px;
  max-width: 1100px;
  margin: 0 auto;
  position: relative;
}

.hero-eyebrow {
  font-size: 0.72rem;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: var(--accent);
  font-weight: 500;
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 22px;
  animation: fadeDown 0.7s ease both;
}

.hero-eyebrow::after {
  content: '';
  width: 40px;
  height: 1px;
  background: var(--accent);
}

h1 {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(4.5rem, 12vw, 9rem);
  line-height: 0.92;
  letter-spacing: 1px;
  color: var(--ink);
  animation: fadeDown 0.7s 0.1s ease both;
}

h1 em {
  font-family: 'DM Serif Display', serif;
  font-style: italic;
  color: var(--accent);
  letter-spacing: -1px;
}

.hero-sub {
  margin-top: 28px;
  font-size: 0.85rem;
  color: var(--muted);
  line-height: 1.8;
  max-width: 420px;
  animation: fadeDown 0.7s 0.2s ease both;
}

.hero-divider {
  margin: 60px 0 0;
  height: 1px;
  background: linear-gradient(90deg, var(--border) 0%, transparent 100%);
  animation: fadeDown 0.7s 0.3s ease both;
}

/* ── WORKS SECTION ── */
.works-section {
  padding: 0 48px 100px;
  max-width: 1100px;
  margin: 0 auto;
}

.section-label {
  padding: 28px 0 40px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.section-label span {
  font-size: 0.68rem;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: var(--muted);
}

.section-label .count {
  font-family: 'DM Serif Display', serif;
  font-style: italic;
  font-size: 0.8rem;
  color: var(--accent);
}

/* ── CARDS GRID ── */
.cards-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: 16px;
}

/* Featured card – spans 8 cols */
.card-featured { grid-column: span 8; }
/* Side card – spans 4 cols */
.card-side { grid-column: span 4; }
/* Full row */
.card-half { grid-column: span 4; }

.card {
  position: relative;
  background: var(--card-bg);
  border: 1px solid var(--border);
  border-radius: 4px;
  overflow: hidden;
  text-decoration: none;
  color: inherit;
  display: flex;
  flex-direction: column;
  transition: transform 0.3s cubic-bezier(0.34,1.2,0.64,1), box-shadow 0.3s, border-color 0.3s;
  animation: cardReveal 0.6s ease both;
  cursor: none;
}

.card:nth-child(1) { animation-delay: 0.3s; }
.card:nth-child(2) { animation-delay: 0.4s; }
.card:nth-child(3) { animation-delay: 0.5s; }
.card:nth-child(4) { animation-delay: 0.6s; }
.card:nth-child(5) { animation-delay: 0.7s; }

.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 20px 48px rgba(14,13,11,0.12);
  border-color: var(--accent);
}

.card-visual {
  height: 200px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
  flex-shrink: 0;
}

.card-featured .card-visual { height: 280px; }

/* Individual card themes */
.card[data-theme="personal"] .card-visual {
  background: linear-gradient(135deg, #1a1512 0%, #2d2218 50%, #1a1512 100%);
}
.card[data-theme="rcb"] .card-visual {
  background: linear-gradient(135deg, #1a0505 0%, #3d0b0b 50%, #1a0505 100%);
}
.card[data-theme="game1"] .card-visual {
  background: linear-gradient(135deg, #0a0f1a 0%, #112240 50%, #0a0f1a 100%);
}
.card[data-theme="game2"] .card-visual {
  background: linear-gradient(135deg, #090d1a 0%, #1a1040 50%, #090d1a 100%);
}
.card[data-theme="story"] .card-visual {
  background: linear-gradient(135deg, #120d08 0%, #2a1f12 50%, #120d08 100%);
}

/* Visual icons / art */
.card-art {
  font-size: 3.5rem;
  filter: drop-shadow(0 0 20px rgba(255,255,255,0.2));
  transition: transform 0.4s cubic-bezier(0.34,1.4,0.64,1), filter 0.4s;
  z-index: 1;
  position: relative;
}
.card-featured .card-art { font-size: 5rem; }
.card:hover .card-art { transform: scale(1.12) rotate(-3deg); filter: drop-shadow(0 0 30px rgba(255,255,255,0.35)); }

/* Decorative lines behind art */
.card-visual::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: repeating-linear-gradient(
    -45deg,
    transparent,
    transparent 24px,
    rgba(255,255,255,0.02) 24px,
    rgba(255,255,255,0.02) 25px
  );
}

.card-visual::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 60px;
  background: linear-gradient(to top, var(--card-bg), transparent);
}

/* Accent strip */
.card-strip {
  position: absolute;
  top: 0;
  left: 0;
  width: 3px;
  height: 100%;
  background: var(--accent);
  transform: scaleY(0);
  transform-origin: top;
  transition: transform 0.3s ease;
}
.card:hover .card-strip { transform: scaleY(1); }

.card-body {
  padding: 22px 24px 24px;
  display: flex;
  flex-direction: column;
  gap: 8px;
  flex: 1;
}

.card-tag {
  font-size: 0.62rem;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: var(--accent);
  font-weight: 500;
}

.card-title {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1.7rem;
  letter-spacing: 1px;
  line-height: 1;
  color: var(--ink);
  transition: color 0.2s;
}
.card-featured .card-title { font-size: 2.2rem; }
.card:hover .card-title { color: var(--accent); }

.card-desc {
  font-size: 0.75rem;
  color: var(--muted);
  line-height: 1.7;
  margin-top: 4px;
}

.card-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: auto;
  padding-top: 14px;
  border-top: 1px solid var(--border);
}

.card-cta {
  font-size: 0.68rem;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--ink);
  font-weight: 500;
  display: flex;
  align-items: center;
  gap: 8px;
  transition: color 0.2s, gap 0.2s;
}
.card:hover .card-cta { color: var(--accent); gap: 14px; }

.card-cta-arrow {
  width: 20px;
  height: 1px;
  background: currentColor;
  position: relative;
  transition: width 0.2s;
}
.card-cta-arrow::after {
  content: '';
  position: absolute;
  right: 0;
  top: -3px;
  width: 6px;
  height: 6px;
  border-right: 1.5px solid currentColor;
  border-top: 1.5px solid currentColor;
  transform: rotate(45deg);
}
.card:hover .card-cta-arrow { width: 28px; }

.card-num {
  font-family: 'DM Serif Display', serif;
  font-style: italic;
  font-size: 1.1rem;
  color: var(--border);
  transition: color 0.2s;
}
.card:hover .card-num { color: var(--accent); opacity: 0.5; }

/* ── BOTTOM ROW – 3 equal cards ── */
.cards-row {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
  margin-top: 16px;
}

/* ── FOOTER ── */
footer {
  border-top: 1px solid var(--border);
  padding: 28px 48px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 1100px;
  margin: 0 auto;
}

.footer-left {
  font-size: 0.7rem;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--muted);
}

.footer-right {
  font-family: 'DM Serif Display', serif;
  font-style: italic;
  font-size: 0.88rem;
  color: var(--accent);
}

/* ── MARQUEE ── */
.marquee-wrap {
  background: var(--ink);
  overflow: hidden;
  padding: 14px 0;
  margin-bottom: 0;
}

.marquee-track {
  display: flex;
  gap: 0;
  animation: marquee 18s linear infinite;
  white-space: nowrap;
}

.marquee-item {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 0.95rem;
  letter-spacing: 4px;
  color: var(--cream);
  padding: 0 32px;
  opacity: 0.5;
  display: flex;
  align-items: center;
  gap: 32px;
  flex-shrink: 0;
}

.marquee-item span { color: var(--accent); opacity: 1; }

/* ── ANIMATIONS ── */
@keyframes fadeDown {
  from { opacity: 0; transform: translateY(-16px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes cardReveal {
  from { opacity: 0; transform: translateY(24px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes marquee {
  from { transform: translateX(0); }
  to { transform: translateX(-50%); }
}

/* ── RESPONSIVE ── */
@media (max-width: 768px) {
  header, .hero, .works-section { padding-left: 20px; padding-right: 20px; }
  .hero { padding-top: 50px; padding-bottom: 40px; }
  h1 { font-size: clamp(3rem, 14vw, 5rem); }
  .cards-grid { grid-template-columns: 1fr; }
  .card-featured, .card-side, .card-half { grid-column: span 1; }
  .cards-row { grid-template-columns: 1fr; }
  footer { flex-direction: column; gap: 10px; text-align: center; }
}
</style>
</head>
<body>

<div id="cursor"></div>
<div id="cursorRing"></div>

<!-- HEADER -->
<header>
  <a href="#" class="header-name">Shaurya Bengani</a>
  <div class="header-tag">Portfolio — Selected Works</div>
</header>

<!-- HERO -->
<div class="hero">
  <div class="hero-eyebrow">Digital Craft</div>
  <h1>THINGS<br>I'VE <em>Built</em></h1>
  <p class="hero-sub">
    A collection of experiments, games, and projects — each one a different way of thinking through problems with code.
  </p>
  <div class="hero-divider"></div>
</div>

<!-- MARQUEE -->
<div class="marquee-wrap">
  <div class="marquee-track">
    <div class="marquee-item">SHAURYA BENGANI <span>✦</span> DEVELOPER <span>✦</span> DESIGNER <span>✦</span> BUILDER <span>✦</span></div>
    <div class="marquee-item">SHAURYA BENGANI <span>✦</span> DEVELOPER <span>✦</span> DESIGNER <span>✦</span> BUILDER <span>✦</span></div>
    <div class="marquee-item">SHAURYA BENGANI <span>✦</span> DEVELOPER <span>✦</span> DESIGNER <span>✦</span> BUILDER <span>✦</span></div>
    <div class="marquee-item">SHAURYA BENGANI <span>✦</span> DEVELOPER <span>✦</span> DESIGNER <span>✦</span> BUILDER <span>✦</span></div>
  </div>
</div>

<!-- WORKS -->
<section class="works-section">
  <div class="section-label">
    <span>Selected Works</span>
    <span class="count">Five projects</span>
  </div>

  <!-- TOP ROW: Featured + Side -->
  <div class="cards-grid">

    <a class="card card-featured" href="https://shauryabengani146.github.io/shaurya.github.io/" target="_blank" rel="noopener" data-theme="personal">
      <div class="card-strip"></div>
      <div class="card-visual">
        <div class="card-art">🌐</div>
      </div>
      <div class="card-body">
        <div class="card-tag">Personal</div>
        <div class="card-title">Shaurya.io</div>
        <p class="card-desc">The main hub — a personal website that ties everything together. Identity, work, and everything in between.</p>
        <div class="card-footer">
          <div class="card-cta">Visit site <div class="card-cta-arrow"></div></div>
          <div class="card-num">01</div>
        </div>
      </div>
    </a>

    <a class="card card-side" href="https://shauryabengani146.github.io/rcb.github.io/" target="_blank" rel="noopener" data-theme="rcb">
      <div class="card-strip"></div>
      <div class="card-visual">
        <div class="card-art">🏏</div>
      </div>
      <div class="card-body">
        <div class="card-tag">Fan Project</div>
        <div class="card-title">RCB.io</div>
        <p class="card-desc">A tribute to Royal Challengers Bangalore — built for the faithful.</p>
        <div class="card-footer">
          <div class="card-cta">Explore <div class="card-cta-arrow"></div></div>
          <div class="card-num">02</div>
        </div>
      </div>
    </a>

  </div>

  <!-- BOTTOM ROW: 3 equal cards -->
  <div class="cards-row">

    <a class="card" href="https://shauryabengani146.github.io/supertictactoe/" target="_blank" rel="noopener" data-theme="game1">
      <div class="card-strip"></div>
      <div class="card-visual">
        <div class="card-art">⚔️</div>
      </div>
      <div class="card-body">
        <div class="card-tag">Game</div>
        <div class="card-title">Super Tic Tac Toe</div>
        <p class="card-desc">Tic Tac Toe, but every cell is another game. Nine boards, one winner. Strategy goes deep.</p>
        <div class="card-footer">
          <div class="card-cta">Play now <div class="card-cta-arrow"></div></div>
          <div class="card-num">03</div>
        </div>
      </div>
    </a>

    <a class="card" href="https://shauryabengani146.github.io/4Dchess/" target="_blank" rel="noopener" data-theme="game2">
      <div class="card-strip"></div>
      <div class="card-visual">
        <div class="card-art">♟️</div>
      </div>
      <div class="card-body">
        <div class="card-tag">Game</div>
        <div class="card-title">4D Chess</div>
        <p class="card-desc">Chess across four dimensions. Not a metaphor. Moves through space and time — genuinely.</p>
        <div class="card-footer">
          <div class="card-cta">Play now <div class="card-cta-arrow"></div></div>
          <div class="card-num">04</div>
        </div>
      </div>
    </a>

    <a class="card" href="https://shauryabengani146.github.io/theexamstory/" target="_blank" rel="noopener" data-theme="story">
      <div class="card-strip"></div>
      <div class="card-visual">
        <div class="card-art">📖</div>
      </div>
      <div class="card-body">
        <div class="card-tag">Story</div>
        <div class="card-title">The Exam Story</div>
        <p class="card-desc">An interactive story about exams, anxiety, and that very specific kind of dread. Relatable.</p>
        <div class="card-footer">
          <div class="card-cta">Read story <div class="card-cta-arrow"></div></div>
          <div class="card-num">05</div>
        </div>
      </div>
    </a>

  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-left">© 2026 Shaurya Bengani — All works</div>
  <div class="footer-right">Made with intent.</div>
</footer>

<script>
// Cursor tracking
const cursor = document.getElementById('cursor');
const ring = document.getElementById('cursorRing');
let mx = 0, my = 0, rx = 0, ry = 0;

document.addEventListener('mousemove', e => {
  mx = e.clientX; my = e.clientY;
  cursor.style.left = mx + 'px';
  cursor.style.top = my + 'px';
});

function animateRing() {
  rx += (mx - rx) * 0.12;
  ry += (my - ry) * 0.12;
  ring.style.left = rx + 'px';
  ring.style.top = ry + 'px';
  requestAnimationFrame(animateRing);
}
animateRing();
</script>
</body>
</html>
