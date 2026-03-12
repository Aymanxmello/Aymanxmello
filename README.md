<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Aymen Zemrani — Mobile Dev Profile</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Space+Mono:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet"/>
<style>
* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  background: #060A10;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding: 2rem 1rem;
}

:root {
  --px: #00FFD1;
  --px2: #FF6B35;
  --px3: #A259FF;
  --px4: #FFE135;
  --dark: #0A0E1A;
  --card: #0F1623;
  --border: #1E2D45;
}

.profile-wrap {
  font-family: 'Space Mono', monospace;
  background: linear-gradient(135deg, #0A0E1A 0%, #0D1520 50%, #0A0E1A 100%);
  border-radius: 16px;
  overflow: hidden;
  position: relative;
  padding: 0 0 2rem;
  max-width: 860px;
  width: 100%;
  border: 1px solid #1E2D45;
}

.scanline {
  position: absolute; top: 0; left: 0; right: 0; bottom: 0;
  background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,255,209,0.015) 2px, rgba(0,255,209,0.015) 4px);
  pointer-events: none; z-index: 0;
}
.pixel-grid {
  position: absolute; top: 0; left: 0; right: 0; bottom: 0;
  background-image: radial-gradient(rgba(0,255,209,0.08) 1px, transparent 1px);
  background-size: 32px 32px;
  pointer-events: none; z-index: 0;
}
.content { position: relative; z-index: 1; }

/* HERO */
.hero {
  padding: 2.5rem 2rem 1.5rem;
  display: flex; align-items: flex-start; gap: 2rem;
  border-bottom: 1px solid #1E2D45;
  flex-wrap: wrap;
}
.avatar-frame {
  flex-shrink: 0;
  width: 120px; height: 120px;
  position: relative;
}
.avatar-border {
  position: absolute; inset: -4px;
  border: 2px solid var(--px);
  animation: borderPulse 2s ease-in-out infinite;
}
.corner { position: absolute; width: 8px; height: 8px; background: var(--px); }
.corner.tl { top: -4px; left: -4px; }
.corner.tr { top: -4px; right: -4px; }
.corner.bl { bottom: -4px; left: -4px; }
.corner.br { bottom: -4px; right: -4px; }
@keyframes borderPulse {
  0%, 100% { box-shadow: 0 0 8px rgba(0,255,209,0.4); }
  50% { box-shadow: 0 0 20px rgba(0,255,209,0.8), 0 0 40px rgba(0,255,209,0.3); }
}
.hero-info { flex: 1; min-width: 240px; }
.badge-row { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 10px; }
.badge {
  font-family: 'Press Start 2P', monospace;
  font-size: 7px;
  padding: 4px 8px;
  border: 1px solid;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}
.badge-cyan { border-color: var(--px); color: var(--px); background: rgba(0,255,209,0.08); }
.badge-orange { border-color: var(--px2); color: var(--px2); background: rgba(255,107,53,0.08); }
.badge-purple { border-color: var(--px3); color: var(--px3); background: rgba(162,89,255,0.08); }
.hero-name {
  font-family: 'Press Start 2P', monospace;
  font-size: 18px;
  color: #fff;
  margin-bottom: 4px;
  text-shadow: 2px 2px 0 var(--px), 0 0 20px rgba(0,255,209,0.5);
  line-height: 1.4;
}
.hero-title {
  font-size: 11px; color: var(--px);
  letter-spacing: 2px; margin-bottom: 12px;
  text-transform: uppercase;
}
.stat-row { display: flex; gap: 1.5rem; flex-wrap: wrap; }
.stat-num {
  font-family: 'Press Start 2P', monospace;
  font-size: 14px; color: var(--px4); display: block;
}
.stat-lbl {
  font-size: 9px; color: #5A7A9A;
  text-transform: uppercase; letter-spacing: 1px; margin-top: 2px;
}

/* SECTIONS */
.section { padding: 1.5rem 2rem; border-bottom: 1px solid #1E2D45; }
.section:last-child { border-bottom: none; }
.sec-header {
  font-family: 'Press Start 2P', monospace;
  font-size: 9px; color: var(--px);
  letter-spacing: 2px; text-transform: uppercase;
  margin-bottom: 1.2rem;
  display: flex; align-items: center; gap: 10px;
}
.sec-header::before { content: '>'; color: var(--px2); }
.sec-header::after {
  content: ''; flex: 1;
  height: 1px;
  background: linear-gradient(90deg, var(--px), transparent);
  opacity: 0.4;
}

/* TERMINAL */
.terminal { background: #060A10; border: 1px solid #1E2D45; border-radius: 4px; overflow: hidden; }
.term-bar {
  background: #1E2D45; padding: 6px 12px;
  display: flex; align-items: center; gap: 6px;
  font-size: 9px; color: #5A7A9A;
}
.term-dot { width: 8px; height: 8px; border-radius: 50%; }
.term-body { padding: 14px; }
.term-line { font-size: 10px; line-height: 1.8; margin-bottom: 2px; }
.t-prompt { color: var(--px3); }
.t-cmd { color: #fff; }
.t-out { color: var(--px); }
.t-comment { color: #3A5A7A; }
.t-warn { color: var(--px4); }
.blink {
  display: inline-block; width: 8px; height: 12px;
  background: var(--px); vertical-align: bottom;
  animation: blink 1s step-end infinite;
}
@keyframes blink { 50% { opacity: 0; } }

/* SKILLS */
.skill-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
.skill-top {
  display: flex; justify-content: space-between; align-items: center;
  margin-bottom: 5px;
}
.skill-name { font-size: 10px; color: #A0B8D0; }
.skill-pct { font-family: 'Press Start 2P', monospace; font-size: 8px; color: var(--px4); }
.skill-bar { height: 6px; background: #1E2D45; position: relative; overflow: hidden; }
.skill-fill { height: 100%; position: relative; }
.skill-fill::after {
  content: ''; position: absolute; right: 0; top: 0;
  width: 3px; height: 100%; background: white; opacity: 0.8;
}

/* TECH TAGS */
.tags { display: flex; flex-wrap: wrap; gap: 8px; }
.tag {
  font-size: 10px; padding: 5px 10px;
  border: 1px solid #1E2D45; color: #7A9AB8;
  background: #0F1623; cursor: pointer;
  transition: all 0.15s;
  display: flex; align-items: center; gap: 5px;
}
.tag:hover { border-color: var(--px); color: var(--px); background: rgba(0,255,209,0.06); }
.tag-dot { width: 6px; height: 6px; flex-shrink: 0; }

/* PROJECTS */
.projects-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; }
@media (max-width: 600px) { .projects-grid { grid-template-columns: 1fr; } }
.proj-card {
  background: #0F1623; border: 1px solid #1E2D45;
  padding: 14px; position: relative; overflow: hidden;
  cursor: pointer; transition: all 0.2s;
}
.proj-card:hover {
  border-color: var(--accent);
  transform: translateY(-2px);
  box-shadow: 0 8px 24px rgba(0,0,0,0.4);
}
.proj-card::before {
  content: ''; position: absolute; top: 0; left: 0; right: 0;
  height: 2px; background: var(--accent);
}
.proj-icon { font-size: 20px; display: block; margin-bottom: 8px; }
.proj-name {
  font-family: 'Press Start 2P', monospace;
  font-size: 7px; color: #fff; margin-bottom: 6px; line-height: 1.6;
}
.proj-desc { font-size: 9px; color: #5A7A9A; margin-bottom: 10px; line-height: 1.6; }
.proj-stats { display: flex; gap: 10px; }
.proj-stat { font-size: 8px; }

/* AVAILABILITY */
.avail-row {
  display: flex; align-items: center; justify-content: space-between;
  flex-wrap: wrap; gap: 1rem;
}
.status-led {
  width: 10px; height: 10px; border-radius: 50%;
  background: #00FF88;
  box-shadow: 0 0 6px #00FF88, 0 0 12px #00FF88;
  animation: ledPulse 2s ease-in-out infinite;
}
@keyframes ledPulse {
  0%, 100% { box-shadow: 0 0 4px #00FF88; }
  50% { box-shadow: 0 0 12px #00FF88, 0 0 24px rgba(0,255,136,0.4); }
}
.avail-text { font-family: 'Press Start 2P', monospace; font-size: 9px; color: #00FF88; }
.avail-detail { font-size: 9px; color: #5A7A9A; }
.hire-btn {
  font-family: 'Press Start 2P', monospace;
  font-size: 8px; padding: 10px 18px;
  background: transparent; border: 2px solid var(--px);
  color: var(--px); cursor: pointer; letter-spacing: 1px;
  transition: all 0.15s;
  text-decoration: none; display: inline-block;
}
.hire-btn:hover {
  background: var(--px); color: #0A0E1A;
  box-shadow: 0 0 20px rgba(0,255,209,0.4);
}

@media (max-width: 500px) {
  .hero { gap: 1rem; }
  .hero-name { font-size: 13px; }
  .skill-grid { grid-template-columns: 1fr; }
}
</style>
</head>
<body>
<div class="profile-wrap">
<div class="scanline"></div>
<div class="pixel-grid"></div>
<div class="content">

<!-- HERO -->
<div class="hero">
  <div class="avatar-frame">
    <div class="avatar-border">
      <div class="corner tl"></div><div class="corner tr"></div>
      <div class="corner bl"></div><div class="corner br"></div>
    </div>
    <svg style="image-rendering:pixelated; width:120px; height:120px;" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
      <rect width="16" height="16" fill="#0F1623"/>
      <rect x="4" y="2" width="8" height="7" fill="#C8956C"/>
      <rect x="3" y="1" width="10" height="3" fill="#1A0A00"/>
      <rect x="3" y="4" width="1" height="2" fill="#1A0A00"/>
      <rect x="12" y="4" width="1" height="2" fill="#1A0A00"/>
      <rect x="5" y="5" width="2" height="2" fill="#00FFD1"/>
      <rect x="9" y="5" width="2" height="2" fill="#00FFD1"/>
      <rect x="6" y="5" width="1" height="1" fill="#0A0E1A"/>
      <rect x="10" y="5" width="1" height="1" fill="#0A0E1A"/>
      <rect x="6" y="7" width="4" height="1" fill="#8B5A42"/>
      <rect x="6" y="9" width="4" height="1" fill="#C8956C"/>
      <rect x="3" y="10" width="10" height="6" fill="#1E2D45"/>
      <rect x="6" y="10" width="4" height="1" fill="#2A3F5A"/>
      <rect x="7" y="11" width="2" height="3" fill="#2A3F5A"/>
      <rect x="11" y="11" width="2" height="3" fill="#0A0E1A"/>
      <rect x="11" y="12" width="2" height="1" fill="#00FFD1"/>
      <rect x="3" y="10" width="3" height="2" fill="#A259FF" opacity="0.6"/>
      <rect x="10" y="10" width="3" height="2" fill="#00FFD1" opacity="0.4"/>
    </svg>
  </div>
  <div class="hero-info">
    <div class="badge-row">
      <span class="badge badge-cyan">Flutter Expert</span>
      <span class="badge badge-orange">UI/UX Pro</span>
      <span class="badge badge-purple">5+ Years</span>
    </div>
    <div class="hero-name">AYMEN<br>ZEMRANI</div>
    <div class="hero-title">Mobile App Architect</div>
    <div class="stat-row">
      <div><span class="stat-num">15+</span><span class="stat-lbl">Apps Built</span></div>
      <div><span class="stat-num">100K+</span><span class="stat-lbl">Downloads</span></div>
      <div><span class="stat-num">4.7★</span><span class="stat-lbl">Avg Rating</span></div>
      <div><span class="stat-num">50K+</span><span class="stat-lbl">Active Users</span></div>
    </div>
  </div>
</div>

<!-- TERMINAL -->
<div class="section">
  <div class="sec-header">System Status</div>
  <div class="terminal">
    <div class="term-bar">
      <div class="term-dot" style="background:#FF5F56"></div>
      <div class="term-dot" style="background:#FFBD2E"></div>
      <div class="term-dot" style="background:#27C93F"></div>
      <span style="margin-left:8px">dev@aymen-zemrani ~ zsh</span>
    </div>
    <div class="term-body">
      <div class="term-line"><span class="t-prompt">~/projects</span> <span class="t-cmd">$ flutter doctor</span></div>
      <div class="term-line"><span class="t-out">✓ Flutter (Channel stable, 3.19.0)</span></div>
      <div class="term-line"><span class="t-out">✓ Android toolchain - Android SDK 34</span></div>
      <div class="term-line"><span class="t-out">✓ Xcode 15.2 - iOS development</span></div>
      <div class="term-line"><span class="t-comment"># Currently building:</span></div>
      <div class="term-line"><span class="t-warn">→ HealthCare+ [75% complete]</span></div>
      <div class="term-line"><span class="t-warn">→ CryptoWallet Pro [90% — beta]</span></div>
      <div class="term-line"><span class="t-prompt">~/projects</span> <span class="t-cmd">$ _</span><span class="blink"></span></div>
    </div>
  </div>
</div>

<!-- SKILLS -->
<div class="section">
  <div class="sec-header">Skill Matrix</div>
  <div class="skill-grid">
    <div>
      <div class="skill-top"><span class="skill-name">Flutter / Dart</span><span class="skill-pct">98%</span></div>
      <div class="skill-bar"><div class="skill-fill" style="width:98%; background: linear-gradient(90deg, #00FFD1, #00B89A);"></div></div>
    </div>
    <div>
      <div class="skill-top"><span class="skill-name">React Native</span><span class="skill-pct">90%</span></div>
      <div class="skill-bar"><div class="skill-fill" style="width:90%; background: linear-gradient(90deg, #61DAFB, #3BA8CC);"></div></div>
    </div>
    <div>
      <div class="skill-top"><span class="skill-name">Swift / SwiftUI</span><span class="skill-pct">85%</span></div>
      <div class="skill-bar"><div class="skill-fill" style="width:85%; background: linear-gradient(90deg, #FA7343, #CC5430);"></div></div>
    </div>
    <div>
      <div class="skill-top"><span class="skill-name">Kotlin / Compose</span><span class="skill-pct">82%</span></div>
      <div class="skill-bar"><div class="skill-fill" style="width:82%; background: linear-gradient(90deg, #A259FF, #7A3FCC);"></div></div>
    </div>
    <div>
      <div class="skill-top"><span class="skill-name">Firebase / BaaS</span><span class="skill-pct">92%</span></div>
      <div class="skill-bar"><div class="skill-fill" style="width:92%; background: linear-gradient(90deg, #FFCA28, #CC9A00);"></div></div>
    </div>
    <div>
      <div class="skill-top"><span class="skill-name">UI / UX Design</span><span class="skill-pct">88%</span></div>
      <div class="skill-bar"><div class="skill-fill" style="width:88%; background: linear-gradient(90deg, #FF6B35, #CC5020);"></div></div>
    </div>
  </div>
</div>

<!-- TECH STACK -->
<div class="section">
  <div class="sec-header">Tech Stack</div>
  <div class="tags">
    <span class="tag"><svg class="tag-dot" viewBox="0 0 6 6"><rect width="6" height="6" fill="#02569B"/></svg>Flutter</span>
    <span class="tag"><svg class="tag-dot" viewBox="0 0 6 6"><rect width="6" height="6" fill="#00B4D8"/></svg>Dart</span>
    <span class="tag"><svg class="tag-dot" viewBox="0 0 6 6"><rect width="6" height="6" fill="#61DAFB"/></svg>React Native</span>
    <span class="tag"><svg class="tag-dot" viewBox="0 0 6 6"><rect width="6" height="6" fill="#FA7343"/></svg>Swift</span>
    <span class="tag"><svg class="tag-dot" viewBox="0 0 6 6"><rect width="6" height="6" fill="#7F52FF"/></svg>Kotlin</span>
    <span class="tag"><svg class="tag-dot" viewBox="0 0 6 6"><rect width="6" height="6" fill="#FFCA28"/></svg>Firebase</span>
    <span class="tag"><svg class="tag-dot" viewBox="0 0 6 6"><rect width="6" height="6" fill="#E10098"/></svg>GraphQL</span>
    <span class="tag"><svg class="tag-dot" viewBox="0 0 6 6"><rect width="6" height="6" fill="#339933"/></svg>Node.js</span>
    <span class="tag"><svg class="tag-dot" viewBox="0 0 6 6"><rect width="6" height="6" fill="#FF0080"/></svg>Figma</span>
    <span class="tag"><svg class="tag-dot" viewBox="0 0 6 6"><rect width="6" height="6" fill="#2088FF"/></svg>CI/CD</span>
    <span class="tag"><svg class="tag-dot" viewBox="0 0 6 6"><rect width="6" height="6" fill="#4CAF50"/></svg>ML Kit</span>
    <span class="tag"><svg class="tag-dot" viewBox="0 0 6 6"><rect width="6" height="6" fill="#FF6B35"/></svg>App Store</span>
  </div>
</div>

<!-- PROJECTS -->
<div class="section">
  <div class="sec-header">Featured Projects</div>
  <div class="projects-grid">
    <div class="proj-card" style="--accent:#00FFD1;">
      <span class="proj-icon">🏃</span>
      <div class="proj-name">FitTrack Pro</div>
      <div class="proj-desc">Fitness tracker with ML-powered insights</div>
      <div class="proj-stats">
        <span class="proj-stat" style="color:#00FFD1">50K↓</span>
        <span class="proj-stat" style="color:#FFE135">4.8★</span>
      </div>
    </div>
    <div class="proj-card" style="--accent:#FF6B35;">
      <span class="proj-icon">🛒</span>
      <div class="proj-name">ShopEase</div>
      <div class="proj-desc">E-commerce with seamless checkout flow</div>
      <div class="proj-stats">
        <span class="proj-stat" style="color:#FF6B35">30K↓</span>
        <span class="proj-stat" style="color:#FFE135">4.6★</span>
      </div>
    </div>
    <div class="proj-card" style="--accent:#A259FF;">
      <span class="proj-icon">🎵</span>
      <div class="proj-name">BeatFlow</div>
      <div class="proj-desc">iOS featured music streaming app</div>
      <div class="proj-stats">
        <span class="proj-stat" style="color:#A259FF">Featured</span>
        <span class="proj-stat" style="color:#FFE135">4.9★</span>
      </div>
    </div>
  </div>
</div>

<!-- PIXEL ART DEV SCENE -->
<div class="section">
  <div class="sec-header">Dev Environment</div>
  <svg width="100%" viewBox="0 0 680 160" xmlns="http://www.w3.org/2000/svg" style="image-rendering:pixelated; display:block;">
    <rect width="680" height="160" fill="#060A10"/>
    <rect x="0" y="120" width="680" height="8" fill="#1E2D45"/>
    <!-- Monitor -->
    <rect x="80" y="30" width="200" height="130" fill="#0F1623" stroke="#2A3F5A" stroke-width="2"/>
    <rect x="85" y="35" width="190" height="110" fill="#0A0E1A"/>
    <rect x="90" y="40" width="180" height="8" fill="#1E2D45"/>
    <rect x="90" y="40" width="60" height="8" fill="#00FFD1" opacity="0.6"/>
    <rect x="90" y="52" width="140" height="4" fill="#1E2D45"/>
    <rect x="90" y="52" width="100" height="4" fill="#A259FF" opacity="0.5"/>
    <rect x="90" y="60" width="160" height="4" fill="#1E2D45"/>
    <rect x="90" y="60" width="120" height="4" fill="#00FFD1" opacity="0.3"/>
    <rect x="90" y="68" width="80" height="4" fill="#FF6B35" opacity="0.6"/>
    <rect x="90" y="76" width="150" height="4" fill="#1E2D45"/>
    <rect x="90" y="76" width="90" height="4" fill="#FFE135" opacity="0.4"/>
    <rect x="90" y="84" width="6" height="8" fill="#00FFD1" opacity="0.9">
      <animate attributeName="opacity" values="0.9;0;0.9" dur="1s" repeatCount="indefinite"/>
    </rect>
    <rect x="168" y="130" width="24" height="10" fill="#1E2D45"/>
    <rect x="150" y="140" width="60" height="6" fill="#2A3F5A"/>
    <!-- Laptop -->
    <rect x="330" y="90" width="180" height="110" fill="#0F1623" stroke="#2A3F5A" stroke-width="2"/>
    <rect x="335" y="95" width="170" height="90" fill="#0A0E1A"/>
    <rect x="340" y="100" width="160" height="6" fill="#A259FF" opacity="0.5"/>
    <rect x="340" y="110" width="120" height="4" fill="#00FFD1" opacity="0.3"/>
    <rect x="340" y="118" width="140" height="4" fill="#FF6B35" opacity="0.4"/>
    <rect x="340" y="126" width="90" height="4" fill="#FFE135" opacity="0.4"/>
    <rect x="330" y="130" width="180" height="10" fill="#1E2D45"/>
    <rect x="330" y="140" width="180" height="20" fill="#0F1623" stroke="#1E2D45" stroke-width="1"/>
    <!-- Phone -->
    <rect x="560" y="60" width="52" height="88" rx="4" fill="#0F1623" stroke="#00FFD1" stroke-width="1.5"/>
    <rect x="564" y="66" width="44" height="68" fill="#0A0E1A"/>
    <rect x="566" y="68" width="40" height="10" fill="#1E2D45"/>
    <rect x="566" y="68" width="25" height="10" fill="#00FFD1" opacity="0.4"/>
    <rect x="566" y="82" width="38" height="6" fill="#1E2D45"/>
    <rect x="566" y="82" width="22" height="6" fill="#A259FF" opacity="0.5"/>
    <rect x="566" y="92" width="36" height="4" fill="#FF6B35" opacity="0.4"/>
    <rect x="566" y="100" width="28" height="4" fill="#FFE135" opacity="0.5"/>
    <rect x="577" y="145" width="18" height="2" rx="1" fill="#2A3F5A"/>
    <!-- Coffee -->
    <rect x="490" y="105" width="30" height="25" fill="#2A3F5A"/>
    <rect x="490" y="100" width="30" height="6" fill="#1E2D45"/>
    <rect x="520" y="110" width="8" height="12" fill="none" stroke="#2A3F5A" stroke-width="2"/>
    <rect x="497" y="92" width="3" height="6" fill="#5A7A9A" opacity="0.5">
      <animate attributeName="opacity" values="0.5;0.1;0.5" dur="1.5s" repeatCount="indefinite"/>
    </rect>
    <rect x="505" y="88" width="3" height="10" fill="#5A7A9A" opacity="0.5">
      <animate attributeName="opacity" values="0.1;0.5;0.1" dur="1.5s" repeatCount="indefinite"/>
    </rect>
    <rect x="513" y="92" width="3" height="6" fill="#5A7A9A" opacity="0.5">
      <animate attributeName="opacity" values="0.5;0.1;0.5" dur="1.5s" repeatCount="indefinite"/>
    </rect>
    <!-- Labels -->
    <text x="180" y="22" text-anchor="middle" font-family="Space Mono, monospace" font-size="8" fill="#3A5A7A">MONITOR</text>
    <text x="420" y="82" text-anchor="middle" font-family="Space Mono, monospace" font-size="8" fill="#3A5A7A">MACBOOK</text>
    <text x="586" y="52" text-anchor="middle" font-family="Space Mono, monospace" font-size="8" fill="#00FFD1" opacity="0.7">iOS DEV</text>
    <rect x="0" y="120" width="680" height="1" fill="#00FFD1" opacity="0.15"/>
  </svg>
</div>

<!-- WORKFLOW -->
<div class="section">
  <div class="sec-header">Dev Workflow</div>
  <div style="display:flex; align-items:center; gap:0; overflow-x:auto; padding-bottom:4px;">
    <div style="text-align:center; min-width:80px;">
      <div style="font-size:20px; margin-bottom:6px;">📝</div>
      <div style="font-family:'Press Start 2P',monospace; font-size:8px; color:#00FFD1;">DESIGN</div>
    </div>
    <div style="flex:1; height:2px; background:linear-gradient(90deg,#00FFD1,#A259FF); min-width:20px; position:relative;">
      <div style="position:absolute;right:-4px;top:-3px;width:0;height:0;border-top:4px solid transparent;border-bottom:4px solid transparent;border-left:8px solid #A259FF;"></div>
    </div>
    <div style="text-align:center; min-width:80px;">
      <div style="font-size:20px; margin-bottom:6px;">💻</div>
      <div style="font-family:'Press Start 2P',monospace; font-size:8px; color:#A259FF;">CODE</div>
    </div>
    <div style="flex:1; height:2px; background:linear-gradient(90deg,#A259FF,#FF6B35); min-width:20px; position:relative;">
      <div style="position:absolute;right:-4px;top:-3px;width:0;height:0;border-top:4px solid transparent;border-bottom:4px solid transparent;border-left:8px solid #FF6B35;"></div>
    </div>
    <div style="text-align:center; min-width:80px;">
      <div style="font-size:20px; margin-bottom:6px;">🧪</div>
      <div style="font-family:'Press Start 2P',monospace; font-size:8px; color:#FF6B35;">TEST</div>
    </div>
    <div style="flex:1; height:2px; background:linear-gradient(90deg,#FF6B35,#FFE135); min-width:20px; position:relative;">
      <div style="position:absolute;right:-4px;top:-3px;width:0;height:0;border-top:4px solid transparent;border-bottom:4px solid transparent;border-left:8px solid #FFE135;"></div>
    </div>
    <div style="text-align:center; min-width:80px;">
      <div style="font-size:20px; margin-bottom:6px;">🚀</div>
      <div style="font-family:'Press Start 2P',monospace; font-size:8px; color:#FFE135;">SHIP</div>
    </div>
    <div style="flex:1; height:2px; background:linear-gradient(90deg,#FFE135,#00FFD1); min-width:20px; position:relative;">
      <div style="position:absolute;right:-4px;top:-3px;width:0;height:0;border-top:4px solid transparent;border-bottom:4px solid transparent;border-left:8px solid #00FFD1;"></div>
    </div>
    <div style="text-align:center; min-width:80px;">
      <div style="font-size:20px; margin-bottom:6px;">📊</div>
      <div style="font-family:'Press Start 2P',monospace; font-size:8px; color:#00FFD1;">MONITOR</div>
    </div>
  </div>
</div>

<!-- AVAILABILITY -->
<div class="section">
  <div class="sec-header">Availability</div>
  <div class="avail-row">
    <div>
      <div style="display:flex; align-items:center; gap:10px; margin-bottom:10px;">
        <div class="status-led"></div>
        <span class="avail-text">Open for Projects</span>
      </div>
      <div style="display:flex; flex-direction:column; gap:4px;">
        <span class="avail-detail">📍 Casablanca, Morocco (GMT+1)</span>
        <span class="avail-detail">💰 $50–100 / hour</span>
        <span class="avail-detail">⚡ Responds in &lt;12 hours</span>
        <span class="avail-detail">📬 LinkedIn · Email · GitHub</span>
      </div>
    </div>
    <a class="hire-btn" href="https://linkedin.com/in/AymenZemrani" target="_blank">HIRE ME ↗</a>
  </div>
</div>

<!-- FOOTER -->
<div style="padding:1rem 2rem 0; text-align:center; border-top:1px solid #1E2D45;">
  <div style="font-family:'Press Start 2P',monospace; font-size:7px; color:#3A5A7A; letter-spacing:2px;">
    © 2026 AYMEN ZEMRANI · MOBILE DEV · ALL RIGHTS RESERVED
  </div>
  <div style="margin-top:8px; font-family:'Press Start 2P',monospace; font-size:6px; color:#1E2D45;">
    BUILT WITH FLUTTER · SWIFT · KOTLIN · ♥
  </div>
</div>

</div>
</div>
</body>
</html>
