<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Surya Pratap Singh</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=VT323&display=swap" rel="stylesheet" />
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      background: #000;
      width: 100%;
      height: 100vh;
      overflow: hidden;
      cursor: none;
      font-family: 'Share Tech Mono', monospace;
    }

    #root {
      background: #000;
      width: 100%;
      height: 100vh;
      position: relative;
      overflow: hidden;
    }

    /* ── CANVAS LAYERS ── */
    #rain-canvas,
    #glow-canvas,
    #interact-canvas {
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
    }
    #rain-canvas    { z-index: 1; pointer-events: none; }
    #glow-canvas    { z-index: 3; pointer-events: none; }
    #interact-canvas{ z-index: 4; }

    /* ── CUSTOM CURSOR ── */
    .cur {
      position: absolute;
      width: 2px; height: 18px;
      background: #00ff41;
      z-index: 10;
      pointer-events: none;
      transform: translate(-50%, -50%);
      box-shadow: 0 0 6px #00ff41, 0 0 12px #00ff41;
    }
    .cur-h {
      position: absolute;
      width: 18px; height: 2px;
      background: #00ff41;
      z-index: 10;
      pointer-events: none;
      transform: translate(-50%, -50%);
      box-shadow: 0 0 6px #00ff41;
    }

    /* ── UI OVERLAY ── */
    .ui {
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      z-index: 6;
      pointer-events: none;
      padding: clamp(20px, 4vw, 48px);
    }

    /* Top bar */
    .top-bar {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: clamp(40px, 8vh, 80px);
    }
    .top-left  { display: flex; flex-direction: column; gap: 4px; }
    .top-right { text-align: right; }

    .commit-line {
      font-family: 'Share Tech Mono', monospace;
      font-size: 11px;
      color: #00aa2a;
      letter-spacing: .5px;
      opacity: .7;
    }
    .commit-line span { color: #00ff41; opacity: 1; }

    /* Links */
    .links-row {
      display: flex;
      gap: 16px;
      margin-top: 8px;
      pointer-events: all;
    }
    .lnk {
      font-family: 'Share Tech Mono', monospace;
      font-size: 11px;
      color: #00661a;
      letter-spacing: 1px;
      text-decoration: none;
      transition: color .15s;
    }
    .lnk:hover { color: #00ff41; }

    /* Name block */
    .name-block { margin-bottom: 12px; }

    .hi-line {
      font-family: 'Share Tech Mono', monospace;
      font-size: 12px;
      color: #00aa2a;
      letter-spacing: 2px;
      margin-bottom: 8px;
    }
    .hi-line span { color: #00ff41; }

    .name-big {
      font-family: 'VT323', monospace;
      font-size: clamp(48px, 10vw, 96px);
      line-height: .9;
      color: #00ff41;
      letter-spacing: 4px;
      text-shadow: 0 0 20px #00ff4166, 0 0 40px #00ff4133;
      display: block;
    }
    .name-dim { color: #00661a; }

    .role-line {
      font-family: 'VT323', monospace;
      font-size: clamp(18px, 3.5vw, 28px);
      color: #00aa2a;
      letter-spacing: 3px;
      margin: 10px 0 6px;
    }

    .aktu-line {
      font-family: 'Share Tech Mono', monospace;
      font-size: 11px;
      color: #006615;
      letter-spacing: 3px;
    }

    /* Bottom bar */
    .bottom-bar {
      position: absolute;
      bottom: clamp(16px, 3vw, 36px);
      left:   clamp(20px, 4vw, 48px);
      right:  clamp(20px, 4vw, 48px);
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
      flex-wrap: wrap;
      gap: 8px;
    }

    .desc-txt {
      font-family: 'VT323', monospace;
      font-size: clamp(18px, 3vw, 26px);
      color: #00661a;
      letter-spacing: 2px;
      max-width: 500px;
      line-height: 1.3;
    }
    .desc-txt span { color: #00aa2a; }

    .stat-col {
      text-align: right;
      display: flex;
      flex-direction: column;
      gap: 3px;
    }
    .stat-item {
      font-family: 'Share Tech Mono', monospace;
      font-size: 10px;
      color: #004410;
      letter-spacing: 1px;
    }
    .stat-item span { color: #00661a; }

    /* Scanline */
    .scan {
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: repeating-linear-gradient(
        0deg,
        transparent,
        transparent 2px,
        rgba(0, 255, 65, .012) 2px,
        rgba(0, 255, 65, .012) 4px
      );
      z-index: 5;
      pointer-events: none;
    }

    /* Blink cursor */
    .blink { animation: blink 1s step-end infinite; }
    @keyframes blink { 0%, 100% { opacity: 1; } 50% { opacity: 0; } }
  </style>
</head>
<body>
<div id="root">

  <!-- Canvas layers -->
  <canvas id="rain-canvas"></canvas>
  <canvas id="glow-canvas"></canvas>
  <canvas id="interact-canvas"></canvas>

  <!-- Custom cursor -->
  <div class="cur"  id="cur"></div>
  <div class="cur-h" id="curH"></div>

  <!-- Scanlines -->
  <div class="scan"></div>

  <!-- UI content -->
  <div class="ui">

    <div class="top-bar">
      <div class="top-left">
        <div class="commit-line">
          <span>1</span> commit today &nbsp;·&nbsp;
          <span>259</span> this month &nbsp;·&nbsp;
          <span>646</span> this year
        </div>
        <div class="links-row">
          <a class="lnk" href="https://github.com/Surya97141"  target="_blank">gh</a>
          <a class="lnk" href="https://linkedin.com/in/surya-singh-b575591b5" target="_blank">in</a>
          <a class="lnk" href="mailto:pratap742006@gmail.com">mail</a>
        </div>
      </div>
      <div class="top-right">
        <div class="commit-line">Hi, I am Surya Pratap Singh, a CS undergrad</div>
        <div class="commit-line">building ML systems that work in the real world</div>
      </div>
    </div>

    <div class="name-block">
      <div class="hi-line">// <span>SURYA PRATAP SINGH</span></div>
      <span class="name-big"><span class="name-dim">_</span>SURYA<span class="name-dim">_</span></span>
      <span class="name-big" style="color:#00aa2a;text-shadow:0 0 10px #00aa2a44">PRATAP</span>
      <span class="name-big" style="color:#00661a;text-shadow:none">SINGH</span>
    </div>

    <div class="role-line">SOFTWARE DEV &nbsp;/&nbsp; ML &nbsp;/&nbsp; AI SYSTEMS</div>
    <div class="aktu-line">AKTU &nbsp;&nbsp;·&nbsp;&nbsp; B.TECH CSE DATA SCIENCE &nbsp;&nbsp;·&nbsp;&nbsp; 2024-2028</div>

  </div><!-- /.ui -->

  <div class="bottom-bar">
    <div class="desc-txt">
      building <span>MAIRA</span> — ml research agent<br>
      + <span>DRL aerial combat</span> sim<br>
      <span class="blink">_</span>
    </div>
    <div class="stat-col">
      <div class="stat-item">projects &nbsp;<span>05</span></div>
      <div class="stat-item">active &nbsp;<span>02</span></div>
      <div class="stat-item">hackathons &nbsp;<span>02</span></div>
      <div class="stat-item">status &nbsp;<span>open to work</span></div>
    </div>
  </div>

</div><!-- /#root -->

<script>
  /* ─────────────────────────────────────────
     SURYA PRATAP SINGH — Matrix Terminal Profile
     Cursor-reveal glow effect on matrix rain
  ───────────────────────────────────────── */

  const root    = document.getElementById('root');
  const rainCv  = document.getElementById('rain-canvas');
  const glowCv  = document.getElementById('glow-canvas');
  const intCv   = document.getElementById('interact-canvas');
  const rCtx    = rainCv.getContext('2d');
  const gCtx    = glowCv.getContext('2d');
  const iCtx    = intCv.getContext('2d');
  const cur     = document.getElementById('cur');
  const curH    = document.getElementById('curH');

  let W, H;
  let mx = -999, my = -999;

  /* ── Character set ── */
  const CHARS =
    'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz' +
    '0123456789@#$%&*<>{}[]' +
    'アイウエオカキクケコサシスセソタチツテトナニヌネノ';

  const COL_W = 16;
  let cols  = [];
  let drops = [];

  /* ── Resize: sync all canvas dimensions ── */
  function resize() {
    W = rainCv.width = glowCv.width = intCv.width  = root.offsetWidth;
    H = rainCv.height= glowCv.height= intCv.height = root.offsetHeight;
    initRain();
  }

  /* ── Initialise rain columns ── */
  function initRain() {
    const n = Math.ceil(W / COL_W);
    cols  = Array.from({ length: n }, (_, i) => i * COL_W + 8);
    drops = cols.map(() => Math.random() * -60);
  }

  /* ── Draw matrix rain ── */
  function drawRain() {
    /* Fade trail — increased opacity wash = faster, dimmer fade */
    rCtx.fillStyle = 'rgba(0,0,0,0.09)';
    rCtx.fillRect(0, 0, W, H);

    rCtx.font = '13px Share Tech Mono';

    for (let i = 0; i < cols.length; i++) {
      const y = drops[i] * COL_W;

      /* Leading char — toned down from bright white-green */
      rCtx.fillStyle = '#44bb66';
      rCtx.fillText(CHARS[Math.floor(Math.random() * CHARS.length)], cols[i] - 6, y);

      /* Trail — shorter, dimmer */
      for (let t = 1; t < 14; t++) {
        const ty = y - t * COL_W;
        if (ty < 0) continue;
        const alpha      = 1 - t / 14;
        const brightness = Math.floor(alpha * 100);
        rCtx.fillStyle   = `rgb(0,${brightness},${Math.floor(brightness * 0.18)})`;
        rCtx.fillText(
          CHARS[Math.floor(Math.random() * CHARS.length)],
          cols[i] - 6, ty
        );
      }

      drops[i]++;
      if (drops[i] * COL_W > H + COL_W * 28) {
        drops[i] = Math.random() * -60;
      }
    }
  }

  /* ── Cursor glow — radial bloom + crosshair, NO particles ── */
  const GLOW_R  = 90;
  const INNER_R = 30;

  function drawGlow() {
    gCtx.clearRect(0, 0, W, H);
    if (mx < 0) return;

    /* Outer radial halo */
    const halo = gCtx.createRadialGradient(mx, my, 0, mx, my, GLOW_R);
    halo.addColorStop(0,    'rgba(0,255,65,0.18)');
    halo.addColorStop(0.30, 'rgba(0,255,65,0.10)');
    halo.addColorStop(0.65, 'rgba(0,255,65,0.04)');
    halo.addColorStop(1,    'rgba(0,255,65,0)');
    gCtx.fillStyle = halo;
    gCtx.beginPath();
    gCtx.arc(mx, my, GLOW_R, 0, Math.PI * 2);
    gCtx.fill();

    /* Horizontal crosshair line */
    const lh = gCtx.createLinearGradient(mx - 60, my, mx + 60, my);
    lh.addColorStop(0,   'rgba(0,255,65,0)');
    lh.addColorStop(0.4, 'rgba(0,255,65,0.20)');
    lh.addColorStop(0.5, 'rgba(0,255,65,0.55)');
    lh.addColorStop(0.6, 'rgba(0,255,65,0.20)');
    lh.addColorStop(1,   'rgba(0,255,65,0)');
    gCtx.strokeStyle = lh;
    gCtx.lineWidth   = 1;
    gCtx.beginPath();
    gCtx.moveTo(mx - 60, my);
    gCtx.lineTo(mx + 60, my);
    gCtx.stroke();

    /* Vertical crosshair line */
    const lv = gCtx.createLinearGradient(mx, my - 60, mx, my + 60);
    lv.addColorStop(0,   'rgba(0,255,65,0)');
    lv.addColorStop(0.4, 'rgba(0,255,65,0.20)');
    lv.addColorStop(0.5, 'rgba(0,255,65,0.55)');
    lv.addColorStop(0.6, 'rgba(0,255,65,0.20)');
    lv.addColorStop(1,   'rgba(0,255,65,0)');
    gCtx.strokeStyle = lv;
    gCtx.beginPath();
    gCtx.moveTo(mx, my - 60);
    gCtx.lineTo(mx, my + 60);
    gCtx.stroke();

    /* Inner bright core */
    const core = gCtx.createRadialGradient(mx, my, 0, mx, my, INNER_R);
    core.addColorStop(0,   'rgba(180,255,200,0.25)');
    core.addColorStop(0.5, 'rgba(0,255,65,0.10)');
    core.addColorStop(1,   'rgba(0,255,65,0)');
    gCtx.fillStyle = core;
    gCtx.beginPath();
    gCtx.arc(mx, my, INNER_R, 0, Math.PI * 2);
    gCtx.fill();
  }

  /* ── Interaction layer — re-renders rain chars near cursor brighter ── */
  function drawInteract() {
    iCtx.clearRect(0, 0, W, H);
    if (mx < 0) return;

    iCtx.font = '13px Share Tech Mono';

    for (let i = 0; i < cols.length; i++) {
      const dx = cols[i] - mx;
      if (Math.abs(dx) > GLOW_R) continue;

      const colBrightness = 1 - Math.abs(dx) / GLOW_R;

      for (let t = -7; t <= 7; t++) {
        const ty = my + t * COL_W;
        if (ty < 0 || ty > H) continue;

        const vDist = Math.abs(ty - my) / (GLOW_R * 0.85);
        const alpha = Math.max(0, colBrightness * (1 - vDist));
        if (alpha <= 0.01) continue;

        const g = Math.floor(150 + 105 * alpha);
        const r = Math.floor(alpha * 60);
        const b = Math.floor(alpha * 40);
        iCtx.fillStyle = `rgba(${r},${g},${b},${Math.min(alpha * 0.95, 1)})`;

        /* Use a stable-ish char per column/row so it doesn't strobe */
        const charIdx = Math.floor(((i * 7 + t * 13) & 0xff) % CHARS.length);
        iCtx.fillText(CHARS[charIdx], cols[i] - 6, ty);
      }
    }
  }

  /* ── Cursor tracking ── */
  intCv.addEventListener('mousemove', e => {
    const rect = intCv.getBoundingClientRect();
    mx = e.clientX - rect.left;
    my = e.clientY - rect.top;
    cur.style.left  = mx + 'px';
    cur.style.top   = my + 'px';
    curH.style.left = mx + 'px';
    curH.style.top  = my + 'px';
  });

  intCv.addEventListener('mouseleave', () => {
    mx = -999;
    my = -999;
  });

  /* ── Main loop ── */
  let frame = 0;
  function loop() {
    requestAnimationFrame(loop);
    frame++;
    /* Rain updates every 2nd frame (~30fps) to keep the classic feel */
    if (frame % 2 === 0) drawRain();
    /* Glow & interact update every frame for smooth cursor response */
    drawGlow();
    drawInteract();
  }

  /* ── Boot ── */
  resize();
  window.addEventListener('resize', resize);
  loop();
</script>
</body>
</html>
