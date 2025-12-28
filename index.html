<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <title>Gelişmiş Atış Hareketi Simülasyonu</title>
  <style>
    :root {
      --bg: #0b1220;
      --panel: #121a2b;
      --accent: #4fc3f7;
      --accent2: #ffca28;
      --text: #e8eef9;
      --muted: #a7b1c4;
      --ok: #66bb6a;
      --warn: #ef5350;
    }
    * { box-sizing: border-box; }
    body {
      margin: 0; background: var(--bg); color: var(--text);
      font-family: ui-sans-serif, system-ui, Segoe UI, Roboto, Helvetica, Arial;
      display: grid; grid-template-columns: 360px 1fr; height: 100vh;
    }
    .sidebar {
      background: var(--panel); padding: 16px; overflow-y: auto; border-right: 1px solid #1f2b44;
    }
    h1 { font-size: 18px; margin: 0 0 12px; }
    h2 { font-size: 14px; margin: 16px 0 8px; color: var(--muted); }
    label { display: block; font-size: 13px; margin-bottom: 6px; }
    .row { display: grid; grid-template-columns: 1fr 100px; gap: 8px; margin-bottom: 10px; }
    input[type="number"], select {
      width: 100%; padding: 8px; background: #0e1727; color: var(--text);
      border: 1px solid #223050; border-radius: 6px;
    }
    input[type="checkbox"] { transform: translateY(2px); margin-right: 6px; }
    .buttons { display: flex; gap: 8px; margin: 12px 0; flex-wrap: wrap; }
    button {
      padding: 8px 12px; border: 1px solid #223050; border-radius: 6px;
      background: #152038; color: var(--text); cursor: pointer;
    }
    button.primary { background: #1c2a48; border-color: #2b3b60; }
    button:disabled { opacity: 0.5; cursor: not-allowed; }
    .speed { display: flex; gap: 6px; }
    .pill { padding: 6px 10px; border: 1px solid #223050; border-radius: 999px; cursor: pointer; }
    .pill.active { background: var(--accent); color: #001221; border-color: transparent; }
    .panel {
      margin-top: 10px; padding: 10px; background: #0f192d; border: 1px solid #1f2b44; border-radius: 8px;
    }
    .kv { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; font-size: 12px; color: var(--muted); }
    .kv div { background:#0c1526; padding: 6px 8px; border-radius: 6px; }
    canvas { width: 100%; height: 100%; display: block; background: radial-gradient(ellipse at top, #0e1630 0%, #0b1220 60%); }
    .legend { font-size: 12px; color: var(--muted); margin-top: 8px; }
    .legend span { display: inline-flex; align-items: center; margin-right: 12px; }
    .dot { width: 10px; height: 10px; border-radius: 50%; display: inline-block; margin-right: 6px; }
    .v-vel { background: var(--accent); }
    .v-acc { background: var(--warn); }
    .v-comp { background: var(--accent2); }
    .footer { font-size: 11px; color: var(--muted); margin-top: 10px; }
  </style>
</head>
<body>
  <div class="sidebar">
    <h1>Gelişmiş Atış Simülasyonu</h1>

    <h2>Atış tipi</h2>
    <div class="row">
      <label for="type">Tip</label>
      <select id="type">
        <option value="oblique">Eğik atış</option>
        <option value="horizontal">Yatay atış</option>
        <option value="vertical-up">Yukarı düşey</option>
        <option value="vertical-down">Aşağı düşey</option>
      </select>
    </div>

    <h2>Başlangıç parametreleri</h2>
    <div class="row">
      <label for="v0">İlk hız V0 (m/s)</label>
      <input id="v0" type="number" value="25" step="0.1" min="0" />
    </div>
    <div class="row">
      <label for="angle">Açı θ (°)</label>
      <input id="angle" type="number" value="53" step="0.1" min="0" max="90" />
    </div>
    <div class="row">
      <label for="h0">Yükseklik h (m)</label>
      <input id="h0" type="number" value="0" step="0.1" />
    </div>

    <h2>Yerçekimi</h2>
    <div class="row">
      <label for="gravity">Gezegen</label>
      <select id="gravity">
        <option value="9.81">Dünya (9.81)</option>
        <option value="1.62">Ay (1.62)</option>
        <option value="3.71">Mars (3.71)</option>
        <option value="custom">Özel</option>
      </select>
      <input id="gCustom" type="number" value="9.81" step="0.01" />
    </div>

    <h2>Ortam etkileri</h2>
    <div class="row">
      <label for="drag">Sürtünme katsayısı k (kg⁻¹)</label>
      <input id="drag" type="number" value="0.02" step="0.001" min="0" />
    </div>
    <div class="row">
      <label for="wind">Rüzgâr (m/s, +x)</label>
      <input id="wind" type="number" value="0" step="0.1" />
    </div>
    <label><input id="enableDrag" type="checkbox" checked /> Hava direnci etkin</label>
    <label><input id="trace" type="checkbox" checked /> İz (path) göster</label>

    <h2>Çarpışma</h2>
    <div class="row">
      <label for="restitution">Esneklik e (0–1)</label>
      <input id="restitution" type="number" value="0" step="0.05" min="0" max="1" />
    </div>

    <h2>Zaman ölçeği</h2>
    <div class="speed">
      <div class="pill active" data-speed="0.5">0.5×</div>
      <div class="pill" data-speed="1">1×</div>
      <div class="pill" data-speed="2">2×</div>
      <div class="pill" data-speed="4">4×</div>
    </div>

    <div class="buttons">
      <button id="start" class="primary">Başlat</button>
      <button id="pause">Duraklat</button>
      <button id="reset">Sıfırla</button>
    </div>

    <div class="panel">
      <div class="kv" id="stats">
        <div><b>t</b>: <span id="t">0.00</span> s</div>
        <div><b>x</b>: <span id="x">0.00</span> m</div>
        <div><b>y</b>: <span id="y">0.00</span> m</div>
        <div><b>v</b>: <span id="v">0.00</span> m/s</div>
        <div><b>vx</b>: <span id="vx">0.00</span> m/s</div>
        <div><b>vy</b>: <span id="vy">0.00</span> m/s</div>
        <div><b>ax</b>: <span id="ax">0.00</span> m/s²</div>
        <div><b>ay</b>: <span id="ay">0.00</span> m/s²</div>
      </div>
      <div class="legend">
        <span><span class="dot v-vel"></span> Hız vektörü</span>
        <span><span class="dot v-acc"></span> İvme (g + drag)</span>
        <span><span class="dot v-comp"></span> Bileşenler</span>
      </div>
    </div>

    <div class="footer">
      v0, θ ve g ile klasik atış: 
      \(x(t)=v_0\cos\theta\cdot t\), 
      \(y(t)=h_0+v_0\sin\theta\cdot t-\frac{1}{2}gt^2\). 
      Drag açıkken sayısal integrasyon kullanılır.
    </div>
  </div>

  <canvas id="view"></canvas>

  <script>
    // Canvas setup
    const canvas = document.getElementById('view');
    const ctx = canvas.getContext('2d');
    function resize() {
      const dpr = window.devicePixelRatio || 1;
      canvas.width = canvas.clientWidth * dpr;
      canvas.height = canvas.clientHeight * dpr;
      ctx.setTransform(dpr, 0, 0, dpr, 0, 0);
    }
    window.addEventListener('resize', resize);
    resize();

    // UI elements
    const ui = {
      type: document.getElementById('type'),
      v0: document.getElementById('v0'),
      angle: document.getElementById('angle'),
      h0: document.getElementById('h0'),
      gravity: document.getElementById('gravity'),
      gCustom: document.getElementById('gCustom'),
      drag: document.getElementById('drag'),
      wind: document.getElementById('wind'),
      enableDrag: document.getElementById('enableDrag'),
      restitution: document.getElementById('restitution'),
      trace: document.getElementById('trace'),
      pills: Array.from(document.querySelectorAll('.pill')),
      start: document.getElementById('start'),
      pause: document.getElementById('pause'),
      reset: document.getElementById('reset'),
      stats: {
        t: document.getElementById('t'),
        x: document.getElementById('x'),
        y: document.getElementById('y'),
        v: document.getElementById('v'),
        vx: document.getElementById('vx'),
        vy: document.getElementById('vy'),
        ax: document.getElementById('ax'),
        ay: document.getElementById('ay'),
      }
    };

    // Simulation state
    let running = false;
    let paused = false;
    let speedScale = 0.5;
    let t = 0;
    let state = null; // {x,y,vx,vy}
    let tracePoints = [];

    // World transform: meters -> pixels (auto-fit)
    const world = {
      meterToPx: 40, // initial scale; will auto adjust
      origin: { x: 80, y: 0 }, // left margin, y set later
      groundY: null, // pixel y of ground
    };

    function updateGravity() {
      const gSel = ui.gravity.value;
      if (gSel === 'custom') return parseFloat(ui.gCustom.value);
      return parseFloat(gSel);
    }

    function initLaunch() {
      const type = ui.type.value;
      const v0 = parseFloat(ui.v0.value);
      const thetaDeg = parseFloat(ui.angle.value);
      const h0 = parseFloat(ui.h0.value);
      const g = updateGravity();
      const wind = parseFloat(ui.wind.value);
      const k = parseFloat(ui.drag.value);
      const dragOn = ui.enableDrag.checked;

      // Initial components
      let theta = thetaDeg * Math.PI / 180;
      let vx = 0, vy = 0;

      if (type === 'oblique') {
        vx = v0 * Math.cos(theta) + wind;
        vy = v0 * Math.sin(theta);
      } else if (type === 'horizontal') {
        vx = v0 + wind; vy = 0;
      } else if (type === 'vertical-up') {
        vx = wind; vy = v0;
      } else if (type === 'vertical-down') {
        vx = wind; vy = -v0;
      }

      state = { x: 0, y: h0, vx, vy, g, k, dragOn, wind };
      t = 0; tracePoints = [{ x: state.x, y: state.y }];
      paused = false;

      // Auto fit canvas scaling
      autoScale(state);
    }

    function autoScale(s) {
      // Rough estimate of range and height to fit canvas
      const v0mag = Math.hypot(s.vx - s.wind, s.vy);
      const theta = Math.atan2(s.vy, s.vx - s.wind);
      const g = s.g;
      const h0 = s.y;
      let range = 50, hmax = Math.max(20, h0);
      if (!s.dragOn) {
        // Projectile motion estimates
        const vy0 = v0mag * Math.sin(theta);
        const vx0 = Math.max(1, v0mag * Math.cos(theta));
        const tFlight = (vy0 + Math.sqrt(vy0*vy0 + 2*g*h0)) / g * 2 / 2; // up+down approx
        range = Math.max(10, vx0 * tFlight);
        hmax = Math.max(h0, (vy0*vy0)/(2*g) + h0);
      }
      const margin = 60;
      const usableW = canvas.clientWidth - margin*2;
      const usableH = canvas.clientHeight - margin*2;
      const sx = usableW / Math.max(10, range);
      const sy = usableH / Math.max(10, hmax);
      world.meterToPx = Math.max(10, Math.min(sx, sy));
      world.origin.x = margin;
      world.groundY = canvas.clientHeight - margin;
      world.origin.y = world.groundY - h0 * world.meterToPx;
    }

    function metersToCanvas(x, y) {
      return {
        cx: world.origin.x + x * world.meterToPx,
        cy: world.origin.y - y * world.meterToPx
      };
    }

    function step(dtReal) {
      if (!running || paused || !state) return;
      const dt = dtReal * speedScale;
      const s = state;

      // Forces: gravity + (optional) quadratic drag ~ k * v * |v|
      const vRel = { x: s.vx - s.wind, y: s.vy }; // velocity relative to air
      const vRelMag = Math.hypot(vRel.x, vRel.y);
      let ax = 0, ay = -s.g;

      if (s.dragOn && s.k > 0 && vRelMag > 0) {
        const drag = s.k * vRelMag;
        ax += -drag * vRel.x;
        ay += -drag * vRel.y;
      }

      // Integrate (semi-implicit Euler for stability)
      s.vx += ax * dt;
      s.vy += ay * dt;
      s.x += s.vx * dt;
      s.y += s.vy * dt;

      // Collision with ground (y=0)
      if (s.y <= 0) {
        const e = Math.max(0, Math.min(1, parseFloat(ui.restitution.value)));
        if (e > 0 && Math.abs(s.vy) > 0.1) {
          s.y = 0;
          s.vy = -s.vy * e; // bounce
          s.vx = s.vx * (1 - 0.02); // tiny frictional loss
        } else {
          s.y = 0; s.vx = s.vx; s.vy = 0;
          paused = true; // stop on ground
        }
      }

      t += dt;
      tracePoints.push({ x: s.x, y: s.y });
      updateStats(ax, ay);
      draw();
    }

    function updateStats(ax, ay) {
      ui.stats.t.textContent = t.toFixed(2);
      ui.stats.x.textContent = state.x.toFixed(2);
      ui.stats.y.textContent = state.y.toFixed(2);
      const vmag = Math.hypot(state.vx, state.vy);
      ui.stats.v.textContent = vmag.toFixed(2);
      ui.stats.vx.textContent = state.vx.toFixed(2);
      ui.stats.vy.textContent = state.vy.toFixed(2);
      ui.stats.ax.textContent = ax.toFixed(2);
      ui.stats.ay.textContent = ay.toFixed(2);
    }

    function drawGrid() {
      const w = canvas.clientWidth, h = canvas.clientHeight;
      ctx.clearRect(0, 0, w, h);
      // Ground line
      ctx.strokeStyle = '#223050';
      ctx.lineWidth = 2;
      ctx.beginPath();
      ctx.moveTo(0, world.groundY);
      ctx.lineTo(w, world.groundY);
      ctx.stroke();

      // Vertical ticks (every 5 m)
      ctx.strokeStyle = '#18243c';
      ctx.lineWidth = 1;
      for (let m=0; m<=w/world.meterToPx; m+=5) {
        const x = world.origin.x + m*world.meterToPx;
        ctx.beginPath(); ctx.moveTo(x, world.groundY); ctx.lineTo(x, world.groundY-8); ctx.stroke();
      }

      // Height ticks (every 5 m)
      for (let m=5; m<= (world.origin.y/world.meterToPx) + 50; m+=5) {
        const y = world.origin.y - m*world.meterToPx;
        ctx.beginPath(); ctx.moveTo(world.origin.x-8, y); ctx.lineTo(world.origin.x, y); ctx.stroke();
      }
    }

    function drawVectors() {
      const s = state;
      const { cx, cy } = metersToCanvas(s.x, s.y);

      // Velocity vector
      drawArrow(cx, cy, cx + s.vx * 0.6, cy - s.vy * 0.6, '#4fc3f7');

      // Acceleration vector (gravity + drag)
      // Recompute ax, ay for length
      const vRel = { x: s.vx - s.wind, y: s.vy };
      const vRelMag = Math.hypot(vRel.x, vRel.y);
      let ax = 0, ay = -s.g;
      if (s.dragOn && s.k > 0 && vRelMag > 0) {
        const drag = s.k * vRelMag;
        ax += -drag * vRel.x;
        ay += -drag * vRel.y;
      }
      drawArrow(cx, cy, cx + ax * 3, cy - ay * 3, '#ef5350');

      // Components (vx, vy)
      drawArrow(cx, cy, cx + s.vx * 0.6, cy, '#ffca28');
      drawArrow(cx, cy, cx, cy - s.vy * 0.6, '#ffca28');
    }

    function drawArrow(x1, y1, x2, y2, color) {
      const head = 8;
      ctx.strokeStyle = color;
      ctx.fillStyle = color;
      ctx.lineWidth = 2;
      ctx.beginPath();
      ctx.moveTo(x1, y1); ctx.lineTo(x2, y2); ctx.stroke();
      const angle = Math.atan2(y2 - y1, x2 - x1);
      ctx.beginPath();
      ctx.moveTo(x2, y2);
      ctx.lineTo(x2 - head * Math.cos(angle - Math.PI/6), y2 - head * Math.sin(angle - Math.PI/6));
      ctx.lineTo(x2 - head * Math.cos(angle + Math.PI/6), y2 - head * Math.sin(angle + Math.PI/6));
      ctx.closePath(); ctx.fill();
    }

    function drawTrace() {
      if (!ui.trace.checked || tracePoints.length < 2) return;
      ctx.strokeStyle = '#3f7dc2';
      ctx.lineWidth = 2; ctx.setLineDash([4,3]);
      ctx.beginPath();
      const p0 = metersToCanvas(tracePoints[0].x, tracePoints[0].y);
      ctx.moveTo(p0.cx, p0.cy);
      for (let i=1; i<tracePoints.length; i++) {
        const p = metersToCanvas(tracePoints[i].x, tracePoints[i].y);
        ctx.lineTo(p.cx, p.cy);
      }
      ctx.stroke();
      ctx.setLineDash([]);
    }

    function drawProjectile() {
      const s = state;
      const { cx, cy } = metersToCanvas(s.x, s.y);
      // Body
      ctx.fillStyle = '#e8eef9';
      ctx.beginPath(); ctx.arc(cx, cy, 6, 0, Math.PI*2); ctx.fill();
      // Glow
      ctx.fillStyle = 'rgba(79,195,247,0.15)';
      ctx.beginPath(); ctx.arc(cx, cy, 16, 0, Math.PI*2); ctx.fill();
    }

    function draw() {
      drawGrid();
      drawTrace();
      drawProjectile();
      drawVectors();
    }

    // Animation loop
    let last = performance.now();
    function loop(now) {
      const dt = Math.min(0.05, (now - last) / 1000); // clamp
      last = now;
      step(dt);
      requestAnimationFrame(loop);
    }
    requestAnimationFrame(loop);

    // UI interactions
    ui.pills.forEach(p => {
      p.addEventListener('click', () => {
        ui.pills.forEach(pp => pp.classList.remove('active'));
        p.classList.add('active');
        speedScale = parseFloat(p.dataset.speed);
      });
    });

    ui.gravity.addEventListener('change', () => {
      ui.gCustom.disabled = ui.gravity.value !== 'custom';
    });
    ui.gCustom.disabled = ui.gravity.value !== 'custom';

    ui.start.addEventListener('click', () => {
      initLaunch();
      running = true; paused = false;
      ui.pause.textContent = 'Duraklat';
    });

    ui.pause.addEventListener('click', () => {
      if (!running) return;
      paused = !paused;
      ui.pause.textContent = paused ? 'Devam' : 'Duraklat';
    });

    ui.reset.addEventListener('click', () => {
      running = false; paused = false; t = 0; state = null; tracePoints = [];
      ui.stats.t.textContent = '0.00';
      ui.stats.x.textContent = '0.00';
      ui.stats.y.textContent = '0.00';
      ui.stats.v.textContent = '0.00';
      ui.stats.vx.textContent = '0.00';
      ui.stats.vy.textContent = '0.00';
      ui.stats.ax.textContent = '0.00';
      ui.stats.ay.textContent = '0.00';
      drawGrid();
    });

    // Initial draw
    drawGrid();
  </script>
</body>
</html>
