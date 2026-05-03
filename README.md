
<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  .root {
    font-family: 'Syne', sans-serif;
    background: #0d0f14;
    min-height: 600px;
    padding: 2rem 1.5rem;
    position: relative;
    overflow: hidden;
    border-radius: 16px;
  }

  .grid-bg {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(rgba(57, 255, 120, 0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(57, 255, 120, 0.04) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
  }

  .scanlines {
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.15) 2px,
      rgba(0,0,0,0.15) 4px
    );
    pointer-events: none;
    opacity: 0.4;
  }

  .glow-orb {
    position: absolute;
    width: 300px;
    height: 300px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(57,255,120,0.08) 0%, transparent 70%);
    top: -80px;
    right: -60px;
    pointer-events: none;
  }

  .header {
    position: relative;
    display: flex;
    align-items: center;
    gap: 1.25rem;
    margin-bottom: 2rem;
  }

  .avatar-ring {
    width: 72px;
    height: 72px;
    border-radius: 50%;
    background: linear-gradient(135deg, #39ff78, #00c8ff);
    padding: 2px;
    flex-shrink: 0;
    animation: spin-ring 8s linear infinite;
  }

  @keyframes spin-ring {
    from { filter: hue-rotate(0deg); }
    to { filter: hue-rotate(360deg); }
  }

  .avatar-inner {
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background: #0d0f14;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'JetBrains Mono', monospace;
    font-size: 22px;
    font-weight: 700;
    color: #39ff78;
  }

  .header-text h1 {
    font-size: 26px;
    font-weight: 800;
    color: #ffffff;
    letter-spacing: -0.5px;
    line-height: 1;
  }

  .handle {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: #39ff78;
    margin-top: 4px;
  }

  .status-dot {
    display: inline-block;
    width: 7px;
    height: 7px;
    border-radius: 50%;
    background: #39ff78;
    margin-right: 6px;
    animation: pulse 2s ease-in-out infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.3; }
  }

  .section {
    position: relative;
    margin-bottom: 1.5rem;
  }

  .section-label {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #39ff78;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 0.75rem;
    opacity: 0.7;
  }

  .about-card {
    background: rgba(255,255,255,0.03);
    border: 0.5px solid rgba(57,255,120,0.15);
    border-radius: 12px;
    padding: 1rem 1.25rem;
  }

  .about-row {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 6px 0;
    font-size: 14px;
    color: #c8d0e0;
    border-bottom: 0.5px solid rgba(255,255,255,0.05);
  }

  .about-row:last-child { border-bottom: none; }

  .about-icon {
    font-size: 14px;
    width: 20px;
    text-align: center;
    flex-shrink: 0;
  }

  .lang-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 8px;
  }

  .lang-chip {
    background: rgba(255,255,255,0.04);
    border: 0.5px solid rgba(255,255,255,0.1);
    border-radius: 8px;
    padding: 8px 6px;
    text-align: center;
    transition: border-color 0.2s, background 0.2s;
    cursor: default;
  }

  .lang-chip:hover {
    border-color: rgba(57,255,120,0.4);
    background: rgba(57,255,120,0.06);
  }

  .lang-chip .lang-icon { font-size: 18px; display: block; margin-bottom: 4px; }
  .lang-chip .lang-name {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #8892a4;
  }

  .focus-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
  }

  .focus-card {
    background: rgba(255,255,255,0.03);
    border: 0.5px solid rgba(255,255,255,0.08);
    border-radius: 10px;
    padding: 10px 12px;
    display: flex;
    align-items: center;
    gap: 10px;
    transition: border-color 0.2s;
    cursor: default;
  }

  .focus-card:hover { border-color: rgba(57,255,120,0.3); }

  .focus-icon {
    font-size: 20px;
    flex-shrink: 0;
  }

  .focus-title {
    font-size: 13px;
    font-weight: 700;
    color: #e0e6f0;
  }

  .focus-sub {
    font-size: 11px;
    color: #5a6478;
    margin-top: 2px;
    font-family: 'JetBrains Mono', monospace;
  }

  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 8px;
  }

  .stat-box {
    background: rgba(255,255,255,0.03);
    border: 0.5px solid rgba(57,255,120,0.12);
    border-radius: 10px;
    padding: 12px;
    text-align: center;
  }

  .stat-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 22px;
    font-weight: 700;
    color: #39ff78;
    display: block;
  }

  .stat-label {
    font-size: 11px;
    color: #4a5568;
    margin-top: 3px;
    font-family: 'JetBrains Mono', monospace;
  }

  .streak-bar-wrap {
    background: rgba(255,255,255,0.03);
    border: 0.5px solid rgba(57,255,120,0.12);
    border-radius: 12px;
    padding: 1rem 1.25rem;
  }

  .streak-bar-label {
    display: flex;
    justify-content: space-between;
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: #4a5568;
    margin-bottom: 8px;
  }

  .streak-bar-track {
    height: 6px;
    background: rgba(255,255,255,0.05);
    border-radius: 3px;
    overflow: hidden;
    margin-bottom: 6px;
  }

  .streak-bar-fill {
    height: 100%;
    border-radius: 3px;
    background: linear-gradient(90deg, #39ff78, #00c8ff);
    width: 0;
    transition: width 1.2s ease;
  }

  .contribution-dots {
    display: grid;
    grid-template-columns: repeat(26, 1fr);
    gap: 3px;
    margin-top: 6px;
  }

  .dot {
    aspect-ratio: 1;
    border-radius: 2px;
    background: rgba(57,255,120,0.08);
    transition: background 0.2s;
  }

  .dot.l1 { background: rgba(57,255,120,0.2); }
  .dot.l2 { background: rgba(57,255,120,0.45); }
  .dot.l3 { background: rgba(57,255,120,0.75); }
  .dot.l4 { background: rgba(57,255,120,1); }

  .footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-top: 1.25rem;
    padding-top: 1rem;
    border-top: 0.5px solid rgba(255,255,255,0.05);
  }

  .footer-tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #2a3040;
    letter-spacing: 1px;
  }

  .open-source-badge {
    font-family: 'JetBrains Mono', monospace;
    font-size: 10px;
    color: #39ff78;
    border: 0.5px solid rgba(57,255,120,0.3);
    border-radius: 20px;
    padding: 3px 10px;
    letter-spacing: 1px;
  }
</style>

<div class="root">
  <div class="grid-bg"></div>
  <div class="scanlines"></div>
  <div class="glow-orb"></div>

  <div class="header">
    <div class="avatar-ring">
      <div class="avatar-inner">L</div>
    </div>
    <div class="header-text">
      <h1>Lu2ky</h1>
      <div class="handle"><span class="status-dot"></span>@Lu2ky · github.com</div>
    </div>
  </div>

  <div class="section">
    <div class="section-label">// about.json</div>
    <div class="about-card">
      <div class="about-row">
        <span class="about-icon">⚡</span>
        <span>Learning <strong style="color:#fff;">Full-Stack Development</strong></span>
      </div>
      <div class="about-row">
        <span class="about-icon">🔥</span>
        <span>Passionate about <strong style="color:#fff;">Open-Source</strong></span>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-label">// languages[]</div>
    <div class="lang-grid">
      <div class="lang-chip">
        <span class="lang-icon">☕</span>
        <div class="lang-name">Java</div>
      </div>
      <div class="lang-chip">
        <span class="lang-icon">🔷</span>
        <div class="lang-name">TypeScript</div>
      </div>
      <div class="lang-chip">
        <span class="lang-icon">🟨</span>
        <div class="lang-name">JavaScript</div>
      </div>
      <div class="lang-chip">
        <span class="lang-icon">🐹</span>
        <div class="lang-name">Golang</div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-label">// focus_areas[]</div>
    <div class="focus-grid">
      <div class="focus-card">
        <span class="focus-icon">🌐</span>
        <div>
          <div class="focus-title">Full-Stack</div>
          <div class="focus-sub">frontend + backend</div>
        </div>
      </div>
      <div class="focus-card">
        <span class="focus-icon">📦</span>
        <div>
          <div class="focus-title">Open Source</div>
          <div class="focus-sub">build in public</div>
        </div>
      </div>
    </div>
  </div>

  <div class="section">
    <div class="section-label">// streak_stats</div>
    <div class="streak-bar-wrap">
      <div class="streak-bar-label">
        <span>contributions this year</span>
        <span id="pct-label">0%</span>
      </div>
      <div class="streak-bar-track">
        <div class="streak-bar-fill" id="bar"></div>
      </div>
      <div class="contribution-dots" id="dots"></div>
    </div>
  </div>

  <div class="section">
    <div class="section-label">// github_stats{}</div>
    <div class="stats-row">
      <div class="stat-box">
        <span class="stat-num" id="c1">0</span>
        <div class="stat-label">commits</div>
      </div>
      <div class="stat-box">
        <span class="stat-num" id="c2">0</span>
        <div class="stat-label">repos</div>
      </div>
      <div class="stat-box">
        <span class="stat-num" id="c3">0</span>
        <div class="stat-label">streak</div>
      </div>
    </div>
  </div>

  <div class="footer">
    <span class="footer-tag">// EOF</span>
    <span class="open-source-badge">OPEN SOURCE</span>
  </div>
</div>

<script>
  const levels = [0, 0, 1, 0, 2, 1, 0, 3, 2, 1, 4, 3, 2, 1, 0, 3, 4, 2, 1, 0, 2, 3, 1, 4, 0, 1,
                  2, 0, 1, 3, 2, 4, 1, 0, 2, 3, 0, 4, 1, 2, 3, 0, 1, 2, 4, 3, 2, 1, 0, 3, 4, 2];

  const container = document.getElementById('dots');
  levels.forEach(l => {
    const d = document.createElement('div');
    d.className = 'dot' + (l > 0 ? ' l' + l : '');
    container.appendChild(d);
  });

  setTimeout(() => {
    document.getElementById('bar').style.width = '72%';
    document.getElementById('pct-label').textContent = '72%';
  }, 300);

  function countUp(el, target, duration) {
    let start = 0;
    const step = target / (duration / 16);
    const t = setInterval(() => {
      start = Math.min(start + step, target);
      el.textContent = Math.round(start);
      if (start >= target) clearInterval(t);
    }, 16);
  }

  setTimeout(() => {
    countUp(document.getElementById('c1'), 342, 1200);
    countUp(document.getElementById('c2'), 18, 900);
    countUp(document.getElementById('c3'), 27, 1000);
  }, 400);
</script>
