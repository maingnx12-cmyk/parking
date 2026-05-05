# parking
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ParkConnect – Nền tảng quản lý bãi xe thông minh</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --navy-950: #020B18;
    --navy-900: #051528;
    --navy-800: #0A2540;
    --navy-700: #0D3460;
    --navy-600: #134B8A;
    --navy-500: #1A6BBF;
    --navy-400: #2E88E0;
    --navy-300: #5BAEF5;
    --navy-200: #93CCF8;
    --navy-100: #C9E8FC;
    --navy-50:  #EBF5FF;
    --accent:   #00D4FF;
    --accent2:  #0FF5A0;
    --amber:    #F5A623;
    --danger:   #EF4444;
    --success:  #22C55E;
    --surface:  #071D36;
    --surface2: #0C2B4E;
    --border:   rgba(255,255,255,0.08);
    --border-light: rgba(255,255,255,0.14);
    --text-primary: #F0F8FF;
    --text-secondary: #7AADCC;
    --text-muted: #4A7A9B;
    --font-display: 'Syne', sans-serif;
    --font-body: 'DM Sans', sans-serif;
    --radius: 12px;
    --radius-lg: 20px;
    --shadow: 0 4px 24px rgba(0,0,0,0.4);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: var(--font-body);
    background: var(--navy-950);
    color: var(--text-primary);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ─── NAVBAR ─────────────────────────────────────── */
  nav {
    position: sticky; top: 0; z-index: 100;
    background: rgba(2, 11, 24, 0.85);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border);
    padding: 0 2.5rem;
    height: 64px;
    display: flex; align-items: center; justify-content: space-between;
  }

  .nav-brand {
    display: flex; align-items: center; gap: 10px;
    font-family: var(--font-display);
    font-weight: 800; font-size: 1.35rem;
    color: var(--text-primary); text-decoration: none;
  }

  .brand-icon {
    width: 32px; height: 32px; border-radius: 8px;
    background: linear-gradient(135deg, var(--navy-500), var(--accent));
    display: flex; align-items: center; justify-content: center;
    font-size: 16px;
  }

  .brand-dot { color: var(--accent); }

  .nav-links {
    display: flex; align-items: center; gap: 2px;
    list-style: none;
  }

  .nav-links a {
    font-size: 0.88rem; font-weight: 500;
    color: var(--text-secondary); text-decoration: none;
    padding: 6px 14px; border-radius: 8px;
    transition: all 0.2s;
  }

  .nav-links a:hover, .nav-links a.active {
    color: var(--text-primary);
    background: var(--surface);
  }

  .nav-links a.active { color: var(--accent); }

  .nav-actions { display: flex; align-items: center; gap: 10px; }

  .btn {
    font-family: var(--font-body); font-size: 0.85rem; font-weight: 500;
    padding: 8px 18px; border-radius: 8px; border: none;
    cursor: pointer; transition: all 0.2s; text-decoration: none;
    display: inline-flex; align-items: center; gap: 6px;
  }

  .btn-ghost {
    background: transparent; color: var(--text-secondary);
    border: 1px solid var(--border-light);
  }

  .btn-ghost:hover { background: var(--surface); color: var(--text-primary); }

  .btn-primary {
    background: var(--navy-500);
    color: #fff;
  }

  .btn-primary:hover { background: var(--navy-400); transform: translateY(-1px); }

  .btn-accent {
    background: var(--accent);
    color: var(--navy-900); font-weight: 700;
  }

  .btn-accent:hover { background: #33DDFF; transform: translateY(-1px); }

  /* ─── VIEW TOGGLE ────────────────────────────────── */
  .view-toggle {
    display: flex; align-items: center;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px; padding: 3px;
  }

  .view-btn {
    font-size: 0.8rem; font-weight: 600; font-family: var(--font-body);
    padding: 5px 14px; border-radius: 7px; border: none;
    cursor: pointer; transition: all 0.2s;
    color: var(--text-muted); background: transparent;
  }

  .view-btn.active {
    background: var(--navy-600); color: var(--text-primary);
  }

  /* ─── SECTIONS ───────────────────────────────────── */
  .page-section { display: none; }
  .page-section.active { display: block; }

  /* ─── HERO ───────────────────────────────────────── */
  .hero {
    position: relative;
    padding: 5rem 2.5rem 4rem;
    text-align: center;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse 80% 60% at 50% 0%, rgba(26,107,191,0.18) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-badge {
    display: inline-flex; align-items: center; gap: 6px;
    background: rgba(0,212,255,0.1); border: 1px solid rgba(0,212,255,0.25);
    color: var(--accent); font-size: 0.78rem; font-weight: 600;
    padding: 5px 14px; border-radius: 100px; margin-bottom: 1.5rem;
    letter-spacing: 0.05em; text-transform: uppercase;
  }

  .hero-badge span { width: 6px; height: 6px; border-radius: 50%; background: var(--accent); }

  .hero h1 {
    font-family: var(--font-display);
    font-size: clamp(2.4rem, 5vw, 4rem);
    font-weight: 800; line-height: 1.1;
    margin-bottom: 1.2rem;
    background: linear-gradient(135deg, #F0F8FF 30%, var(--navy-300) 70%, var(--accent) 100%);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero p {
    font-size: 1.05rem; color: var(--text-secondary); max-width: 560px;
    margin: 0 auto 2rem; line-height: 1.7;
  }

  .hero-cta { display: flex; justify-content: center; gap: 12px; flex-wrap: wrap; }

  /* ─── STATS BAR ──────────────────────────────────── */
  .stats-bar {
    display: grid; grid-template-columns: repeat(4, 1fr);
    gap: 1px; background: var(--border);
    border-top: 1px solid var(--border);
    border-bottom: 1px solid var(--border);
  }

  .stat-item {
    background: var(--navy-950);
    padding: 1.5rem; text-align: center;
  }

  .stat-num {
    font-family: var(--font-display);
    font-size: 1.8rem; font-weight: 800;
    color: var(--accent);
  }

  .stat-label {
    font-size: 0.78rem; color: var(--text-muted);
    margin-top: 2px; text-transform: uppercase; letter-spacing: 0.05em;
  }

  /* ─── VEHICLE SELECTOR ───────────────────────────── */
  .section-block {
    padding: 3rem 2.5rem;
    border-bottom: 1px solid var(--border);
  }

  .section-title {
    font-family: var(--font-display);
    font-size: 0.75rem; font-weight: 700;
    color: var(--text-muted); letter-spacing: 0.12em;
    text-transform: uppercase; margin-bottom: 1.2rem;
  }

  .vehicle-grid {
    display: grid; grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 12px;
  }

  .vehicle-card {
    background: var(--surface); border: 1px solid var(--border);
    border-radius: var(--radius); padding: 1.2rem 1rem;
    cursor: pointer; transition: all 0.2s;
    text-align: center; position: relative; overflow: hidden;
  }

  .vehicle-card::before {
    content: ''; position: absolute;
    top: 0; left: 0; right: 0; height: 2px;
    background: transparent; transition: all 0.2s;
  }

  .vehicle-card:hover { border-color: var(--border-light); background: var(--surface2); }

  .vehicle-card.selected {
    border-color: var(--accent); background: rgba(0,212,255,0.07);
  }

  .vehicle-card.selected::before { background: var(--accent); }

  .vehicle-icon { font-size: 2rem; margin-bottom: 8px; }

  .vehicle-name {
    font-size: 0.88rem; font-weight: 600; color: var(--text-primary);
  }

  .vehicle-desc { font-size: 0.75rem; color: var(--text-muted); margin-top: 3px; }

  /* ─── SEARCH FILTER ──────────────────────────────── */
  .search-bar {
    display: flex; gap: 10px; align-items: center;
    background: var(--surface); border: 1px solid var(--border);
    border-radius: var(--radius); padding: 10px 16px;
    margin-bottom: 1rem;
  }

  .search-bar input {
    background: transparent; border: none; outline: none;
    color: var(--text-primary); font-family: var(--font-body);
    font-size: 0.9rem; flex: 1;
  }

  .search-bar input::placeholder { color: var(--text-muted); }

  .filters {
    display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 1.5rem;
  }

  .filter-chip {
    font-size: 0.8rem; font-weight: 500;
    padding: 5px 14px; border-radius: 100px;
    border: 1px solid var(--border-light);
    background: transparent; color: var(--text-secondary);
    cursor: pointer; transition: all 0.2s;
    font-family: var(--font-body);
  }

  .filter-chip:hover { border-color: var(--navy-400); color: var(--text-primary); }
  .filter-chip.active { background: var(--navy-700); border-color: var(--navy-500); color: var(--text-primary); }

  /* ─── VIEW SWITCHER (List/Map) ───────────────────── */
  .view-switcher {
    display: flex; align-items: center; justify-content: space-between;
    margin-bottom: 1rem;
  }

  .view-mode-btns { display: flex; gap: 6px; }

  .mode-btn {
    font-size: 0.8rem; font-weight: 600; font-family: var(--font-body);
    padding: 6px 14px; border-radius: 8px; border: 1px solid var(--border-light);
    cursor: pointer; transition: all 0.2s;
    color: var(--text-muted); background: transparent;
    display: flex; align-items: center; gap: 6px;
  }

  .mode-btn.active { background: var(--navy-700); border-color: var(--navy-500); color: var(--text-primary); }

  /* ─── PARKING LIST ───────────────────────────────── */
  .parking-list { display: flex; flex-direction: column; gap: 12px; }

  .parking-card {
    background: var(--surface); border: 1px solid var(--border);
    border-radius: var(--radius-lg); padding: 1.25rem 1.5rem;
    display: flex; align-items: center; gap: 1.25rem;
    transition: all 0.2s; cursor: pointer;
  }

  .parking-card:hover { border-color: var(--border-light); background: var(--surface2); }

  .parking-thumb {
    width: 72px; height: 72px; border-radius: 10px;
    background: var(--navy-800); flex-shrink: 0;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.8rem; position: relative; overflow: hidden;
  }

  .parking-thumb img {
    width: 100%; height: 100%; object-fit: cover; border-radius: 10px;
  }

  .parking-info { flex: 1; min-width: 0; }

  .parking-name {
    font-family: var(--font-display); font-size: 1rem; font-weight: 700;
    color: var(--text-primary); margin-bottom: 3px;
  }

  .parking-address {
    font-size: 0.8rem; color: var(--text-muted); margin-bottom: 8px;
  }

  .parking-tags { display: flex; gap: 6px; flex-wrap: wrap; }

  .tag {
    font-size: 0.72rem; font-weight: 600;
    padding: 2px 9px; border-radius: 100px;
  }

  .tag-available { background: rgba(34,197,94,0.12); color: #4ade80; }
  .tag-busy { background: rgba(245,166,35,0.12); color: #fbbf24; }
  .tag-full { background: rgba(239,68,68,0.12); color: #f87171; }
  .tag-covered { background: rgba(26,107,191,0.15); color: var(--navy-300); }
  .tag-open { background: rgba(0,212,255,0.1); color: var(--accent); }

  .parking-meta {
    text-align: right; flex-shrink: 0;
  }

  .parking-price {
    font-family: var(--font-display);
    font-size: 1.1rem; font-weight: 800; color: var(--text-primary);
  }

  .parking-price span { font-size: 0.72rem; font-weight: 400; color: var(--text-muted); }

  .parking-slots {
    font-size: 0.78rem; color: var(--text-secondary); margin-top: 4px;
  }

  .occupancy-bar {
    width: 80px; height: 4px; background: var(--navy-800);
    border-radius: 2px; margin: 6px 0 4px auto; overflow: hidden;
  }

  .occupancy-fill {
    height: 100%; border-radius: 2px; transition: width 0.5s;
  }

  .stars { color: var(--amber); font-size: 0.75rem; }

  /* ─── MAP VIEW ───────────────────────────────────── */
  .map-view {
    background: var(--surface); border: 1px solid var(--border);
    border-radius: var(--radius-lg); height: 420px;
    display: flex; align-items: center; justify-content: center;
    position: relative; overflow: hidden;
  }

  .map-placeholder {
    position: relative; width: 100%; height: 100%;
  }

  .map-bg {
    width: 100%; height: 100%;
    background: var(--navy-900);
    display: grid;
    grid-template-columns: repeat(8, 1fr);
    grid-template-rows: repeat(6, 1fr);
    gap: 2px; padding: 2px;
  }

  .map-block {
    border-radius: 3px;
    background: var(--navy-800);
    opacity: 0.6;
  }

  .map-road-h {
    grid-column: 1/-1; background: var(--navy-700); opacity: 0.4;
  }

  .map-road-v {
    grid-row: 1/-1; background: var(--navy-700); opacity: 0.4;
  }

  .map-pins { position: absolute; inset: 0; }

  .map-pin {
    position: absolute; cursor: pointer;
    transform: translate(-50%, -100%);
    transition: transform 0.2s;
  }

  .map-pin:hover { transform: translate(-50%, -100%) scale(1.15); }

  .pin-body {
    background: var(--navy-600); border: 2px solid var(--navy-400);
    border-radius: 8px; padding: 5px 10px;
    font-size: 0.75rem; font-weight: 700; color: var(--text-primary);
    white-space: nowrap; position: relative;
    box-shadow: 0 4px 12px rgba(0,0,0,0.5);
  }

  .pin-body.available { background: rgba(34,197,94,0.2); border-color: #22c55e; }
  .pin-body.busy { background: rgba(245,166,35,0.2); border-color: var(--amber); }

  .pin-body::after {
    content: ''; position: absolute;
    bottom: -6px; left: 50%; transform: translateX(-50%);
    border: 4px solid transparent;
    border-top-color: inherit;
  }

  /* ─── ═══════════════════════════════════════════ ─── */
  /* ─── B2B OPERATOR DASHBOARD ─────────────────────── */
  /* ─── ═══════════════════════════════════════════ ─── */

  .dashboard-header {
    padding: 2rem 2.5rem 1.5rem;
    border-bottom: 1px solid var(--border);
    display: flex; align-items: center; justify-content: space-between;
  }

  .dashboard-header h1 {
    font-family: var(--font-display);
    font-size: 1.6rem; font-weight: 800;
  }

  .dashboard-header h1 span { color: var(--accent); }

  .operator-name {
    font-size: 0.83rem; color: var(--text-secondary); margin-top: 2px;
  }

  .live-badge {
    display: flex; align-items: center; gap: 6px;
    background: rgba(34,197,94,0.1); border: 1px solid rgba(34,197,94,0.25);
    color: #4ade80; font-size: 0.75rem; font-weight: 600;
    padding: 5px 12px; border-radius: 100px;
  }

  .live-dot {
    width: 7px; height: 7px; border-radius: 50%; background: #22c55e;
    animation: pulse 1.5s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; } 50% { opacity: 0.3; }
  }

  /* KPI GRID */
  .kpi-grid {
    display: grid; grid-template-columns: repeat(4, 1fr);
    gap: 1px; background: var(--border);
    border-bottom: 1px solid var(--border);
  }

  .kpi-card {
    background: var(--navy-950); padding: 1.5rem 1.75rem;
  }

  .kpi-label {
    font-size: 0.72rem; font-weight: 600; color: var(--text-muted);
    text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 8px;
  }

  .kpi-value {
    font-family: var(--font-display);
    font-size: 2rem; font-weight: 800; line-height: 1;
    margin-bottom: 6px;
  }

  .kpi-change {
    font-size: 0.78rem; display: flex; align-items: center; gap: 4px;
  }

  .kpi-change.up { color: var(--success); }
  .kpi-change.down { color: var(--danger); }

  /* OCCUPANCY CONTROL */
  .ops-section {
    padding: 2rem 2.5rem;
    border-bottom: 1px solid var(--border);
  }

  .ops-section h2 {
    font-family: var(--font-display);
    font-size: 1rem; font-weight: 700; margin-bottom: 1.25rem;
    color: var(--text-secondary);
  }

  .slot-control-grid {
    display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px;
  }

  .slot-panel {
    background: var(--surface); border: 1px solid var(--border);
    border-radius: var(--radius-lg); padding: 1.25rem;
  }

  .slot-panel-title {
    font-size: 0.8rem; font-weight: 600; color: var(--text-muted);
    margin-bottom: 12px; display: flex; align-items: center; gap: 6px;
  }

  .slot-type-dot {
    width: 8px; height: 8px; border-radius: 50%;
  }

  .slot-counter {
    display: flex; align-items: center; gap: 12px; margin-bottom: 14px;
  }

  .counter-btn {
    width: 36px; height: 36px; border-radius: 8px; border: none;
    font-size: 1.2rem; font-weight: 700; cursor: pointer;
    transition: all 0.15s; display: flex; align-items: center; justify-content: center;
    font-family: var(--font-body);
  }

  .counter-btn.minus {
    background: rgba(239,68,68,0.12); color: #f87171;
  }

  .counter-btn.minus:hover { background: rgba(239,68,68,0.22); }

  .counter-btn.plus {
    background: rgba(34,197,94,0.12); color: #4ade80;
  }

  .counter-btn.plus:hover { background: rgba(34,197,94,0.22); }

  .counter-value {
    font-family: var(--font-display); font-size: 1.8rem;
    font-weight: 800; color: var(--text-primary); min-width: 40px;
    text-align: center;
  }

  .slot-capacity {
    font-size: 0.75rem; color: var(--text-muted);
  }

  .occ-bar-wrap {
    background: var(--navy-800); border-radius: 4px;
    height: 6px; overflow: hidden; margin-top: 8px;
  }

  .occ-bar-fill {
    height: 100%; border-radius: 4px;
    transition: width 0.4s ease;
  }

  /* CHARTS ROW */
  .charts-row {
    display: grid; grid-template-columns: 1.6fr 1fr; gap: 16px;
    padding: 2rem 2.5rem; border-bottom: 1px solid var(--border);
  }

  .chart-panel {
    background: var(--surface); border: 1px solid var(--border);
    border-radius: var(--radius-lg); padding: 1.25rem;
  }

  .chart-title {
    font-size: 0.8rem; font-weight: 600; color: var(--text-muted);
    margin-bottom: 1rem; text-transform: uppercase; letter-spacing: 0.08em;
  }

  .bar-chart {
    display: flex; align-items: flex-end; gap: 6px;
    height: 120px; padding-bottom: 24px; position: relative;
  }

  .bar-chart::after {
    content: ''; position: absolute; bottom: 24px;
    left: 0; right: 0; border-bottom: 1px solid var(--border);
  }

  .bar-col {
    flex: 1; display: flex; flex-direction: column;
    align-items: center; gap: 4px; height: 100%;
    justify-content: flex-end;
  }

  .bar-fill {
    width: 100%; border-radius: 4px 4px 0 0;
    background: var(--navy-600); transition: height 0.5s;
    position: relative; cursor: pointer;
  }

  .bar-fill:hover { background: var(--navy-400); }
  .bar-fill.peak { background: var(--accent); opacity: 0.85; }

  .bar-label {
    font-size: 0.68rem; color: var(--text-muted);
    white-space: nowrap;
  }

  .donut-wrap {
    display: flex; align-items: center; justify-content: center; gap: 1.5rem;
    height: 120px;
  }

  .donut-legend { display: flex; flex-direction: column; gap: 8px; }

  .legend-item {
    display: flex; align-items: center; gap: 8px;
    font-size: 0.78rem; color: var(--text-secondary);
  }

  .legend-dot {
    width: 10px; height: 10px; border-radius: 50%; flex-shrink: 0;
  }

  .legend-val { margin-left: auto; font-weight: 600; color: var(--text-primary); }

  /* REPORTS */
  .reports-section {
    display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px;
    padding: 2rem 2.5rem; border-bottom: 1px solid var(--border);
  }

  .report-card {
    background: var(--surface); border: 1px solid var(--border);
    border-radius: var(--radius-lg); padding: 1.25rem;
  }

  .report-header {
    display: flex; justify-content: space-between; align-items: flex-start;
    margin-bottom: 1rem;
  }

  .report-title {
    font-size: 0.78rem; font-weight: 600; color: var(--text-muted);
    text-transform: uppercase; letter-spacing: 0.08em;
  }

  .peak-list { display: flex; flex-direction: column; gap: 8px; }

  .peak-row {
    display: flex; align-items: center; gap: 10px;
    font-size: 0.82rem;
  }

  .peak-time {
    font-family: var(--font-display); font-weight: 700; color: var(--text-primary);
    min-width: 70px;
  }

  .peak-bar-bg {
    flex: 1; height: 5px; background: var(--navy-800);
    border-radius: 3px; overflow: hidden;
  }

  .peak-bar-val {
    height: 100%; border-radius: 3px; background: var(--navy-500);
  }

  .peak-pct { font-size: 0.75rem; color: var(--text-muted); min-width: 36px; text-align: right; }

  .metric-row {
    display: flex; justify-content: space-between; align-items: center;
    padding: 8px 0; border-bottom: 1px solid var(--border);
    font-size: 0.83rem;
  }

  .metric-row:last-child { border-bottom: none; }

  .metric-row .label { color: var(--text-secondary); }
  .metric-row .val { font-weight: 700; font-family: var(--font-display); font-size: 0.95rem; }

  /* MARKETING SECTION */
  .marketing-section {
    padding: 2rem 2.5rem;
  }

  .profile-upload {
    background: var(--surface); border: 1px dashed var(--border-light);
    border-radius: var(--radius-lg); padding: 2rem;
    text-align: center; margin-bottom: 1rem; cursor: pointer;
    transition: all 0.2s;
  }

  .profile-upload:hover { border-color: var(--navy-400); }

  .profile-upload p { font-size: 0.83rem; color: var(--text-muted); margin-top: 6px; }

  .promo-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; }

  .promo-card {
    background: var(--surface); border: 1px solid var(--border);
    border-radius: var(--radius); padding: 1.1rem;
    text-align: center; cursor: pointer; transition: all 0.2s;
  }

  .promo-card:hover { border-color: var(--border-light); }

  .promo-card.recommended {
    border-color: var(--accent); background: rgba(0,212,255,0.05);
  }

  .promo-name {
    font-family: var(--font-display); font-size: 0.9rem; font-weight: 700;
    margin-bottom: 4px;
  }

  .promo-price {
    font-size: 1.3rem; font-weight: 800; font-family: var(--font-display);
    color: var(--accent);
  }

  .promo-price span { font-size: 0.72rem; color: var(--text-muted); font-weight: 400; }

  .promo-features {
    margin-top: 10px; list-style: none;
    font-size: 0.75rem; color: var(--text-secondary);
    display: flex; flex-direction: column; gap: 4px;
  }

  /* ─── FOOTER ─────────────────────────────────────── */
  footer {
    border-top: 1px solid var(--border); padding: 2rem 2.5rem;
    display: flex; align-items: center; justify-content: space-between;
  }

  footer p { font-size: 0.78rem; color: var(--text-muted); }

  .footer-links { display: flex; gap: 1.5rem; list-style: none; }

  .footer-links a {
    font-size: 0.78rem; color: var(--text-muted); text-decoration: none;
    transition: color 0.2s;
  }

  .footer-links a:hover { color: var(--text-secondary); }

  /* ─── MODAL ──────────────────────────────────────── */
  .modal-overlay {
    display: none; position: fixed; inset: 0; z-index: 200;
    background: rgba(0,0,0,0.7); backdrop-filter: blur(4px);
    align-items: center; justify-content: center;
  }

  .modal-overlay.open { display: flex; }

  .modal {
    background: var(--navy-900); border: 1px solid var(--border-light);
    border-radius: var(--radius-lg); width: 90%; max-width: 500px;
    padding: 1.75rem; position: relative;
  }

  .modal-title {
    font-family: var(--font-display); font-size: 1.2rem; font-weight: 800;
    margin-bottom: 0.25rem;
  }

  .modal-subtitle { font-size: 0.82rem; color: var(--text-muted); margin-bottom: 1.5rem; }

  .modal-close {
    position: absolute; top: 1rem; right: 1rem;
    background: var(--surface); border: 1px solid var(--border);
    border-radius: 8px; width: 32px; height: 32px;
    color: var(--text-secondary); cursor: pointer;
    font-size: 1rem; display: flex; align-items: center; justify-content: center;
    transition: all 0.2s;
  }

  .modal-close:hover { background: var(--surface2); color: var(--text-primary); }

  .modal-row {
    display: flex; align-items: center; justify-content: space-between;
    padding: 10px 0; border-bottom: 1px solid var(--border);
    font-size: 0.85rem;
  }

  .modal-row:last-of-type { border-bottom: none; }

  .modal-row .label { color: var(--text-secondary); }
  .modal-row .val { font-weight: 600; }

  .modal-footer { margin-top: 1.5rem; display: flex; gap: 10px; }

  /* ─── TOAST ──────────────────────────────────────── */
  .toast {
    position: fixed; bottom: 1.5rem; right: 1.5rem; z-index: 300;
    background: var(--navy-700); border: 1px solid var(--border-light);
    border-radius: var(--radius); padding: 12px 18px;
    font-size: 0.83rem; color: var(--text-primary);
    transform: translateY(100px); opacity: 0;
    transition: all 0.35s cubic-bezier(0.16, 1, 0.3, 1);
    display: flex; align-items: center; gap: 8px;
  }

  .toast.show { transform: translateY(0); opacity: 1; }

  /* ─── SCROLLBAR ──────────────────────────────────── */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--navy-950); }
  ::-webkit-scrollbar-thumb { background: var(--navy-700); border-radius: 3px; }
</style>
</head>
<body>

<!-- ─── NAVBAR ─── -->
<nav>
  <a class="nav-brand" href="#">
    <div class="brand-icon">🅿</div>
    Park<span class="brand-dot">Connect</span>
  </a>
  <ul class="nav-links">
    <li><a href="#" class="active" onclick="navTo(event, 'b2c')">Tìm bãi xe</a></li>
    <li><a href="#" onclick="navTo(event, 'b2b')">Dashboard</a></li>
    <li><a href="#">Giá cả</a></li>
    <li><a href="#">Hỗ trợ</a></li>
  </ul>
  <div class="nav-actions">
    <div class="view-toggle">
      <button class="view-btn active" id="btnB2C" onclick="switchView('b2c')">Người dùng</button>
      <button class="view-btn" id="btnB2B" onclick="switchView('b2b')">Vận hành</button>
    </div>
    <a href="#" class="btn btn-accent">Đăng ký miễn phí</a>
  </div>
</nav>

<!-- ══════════════════════════════════════════════════ -->
<!-- B2C – USER INTERFACE                               -->
<!-- ══════════════════════════════════════════════════ -->
<section class="page-section active" id="sec-b2c">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-badge"><span></span>Real-time · Đặt trước · Không lo chỗ đậu</div>
    <h1>Tìm bãi xe ngay,<br>không mất thêm phút nào</h1>
    <p>Xem chỗ trống theo thời gian thực, so sánh giá, đặt trước — tất cả trong một nền tảng. Hỗ trợ xe máy, ô tô và xe tải.</p>
    <div class="hero-cta">
      <button class="btn btn-accent" onclick="showToast('Đang mở tìm kiếm...')">Tìm bãi xe gần tôi</button>
      <button class="btn btn-ghost" onclick="showToast('Demo đang phát triển')">Xem Demo</button>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-bar">
    <div class="stat-item"><div class="stat-num" id="s1">2,400+</div><div class="stat-label">Bãi xe đối tác</div></div>
    <div class="stat-item"><div class="stat-num" id="s2">120K+</div><div class="stat-label">Lượt đặt chỗ/tháng</div></div>
    <div class="stat-item"><div class="stat-num" id="s3">98.2%</div><div class="stat-label">Độ hài lòng</div></div>
    <div class="stat-item"><div class="stat-num" id="s4">15 TP</div><div class="stat-label">Thành phố</div></div>
  </div>

  <!-- VEHICLE SELECTOR -->
  <div class="section-block">
    <div class="section-title">Loại phương tiện</div>
    <div class="vehicle-grid">
      <div class="vehicle-card selected" onclick="selectVehicle(this)">
        <div class="vehicle-icon">🛵</div>
        <div class="vehicle-name">Xe máy</div>
        <div class="vehicle-desc">Scooter, moto, xe số</div>
      </div>
      <div class="vehicle-card" onclick="selectVehicle(this)">
        <div class="vehicle-icon">🚗</div>
        <div class="vehicle-name">Ô tô con</div>
        <div class="vehicle-desc">Sedan, SUV, hatchback</div>
      </div>
      <div class="vehicle-card" onclick="selectVehicle(this)">
        <div class="vehicle-icon">🚙</div>
        <div class="vehicle-name">SUV / MPV</div>
        <div class="vehicle-desc">7 chỗ, xe cao cấp</div>
      </div>
      <div class="vehicle-card" onclick="selectVehicle(this)">
        <div class="vehicle-icon">🚐</div>
        <div class="vehicle-name">Xe tải nhỏ</div>
        <div class="vehicle-desc">Bán tải, van</div>
      </div>
      <div class="vehicle-card" onclick="selectVehicle(this)">
        <div class="vehicle-icon">🚌</div>
        <div class="vehicle-name">Xe khách</div>
        <div class="vehicle-desc">16–45 chỗ</div>
      </div>
    </div>
  </div>

  <!-- SEARCH + FILTER -->
  <div class="section-block">
    <div class="search-bar">
      <span style="font-size:16px; color: var(--text-muted);">📍</span>
      <input type="text" placeholder="Tìm khu vực, quận, địa chỉ...">
      <button class="btn btn-primary" style="padding:6px 14px; font-size:0.8rem;">Tìm kiếm</button>
    </div>
    <div class="filters">
      <button class="filter-chip active" onclick="toggleFilter(this)">Tất cả khu vực</button>
      <button class="filter-chip" onclick="toggleFilter(this)">Quận 1</button>
      <button class="filter-chip" onclick="toggleFilter(this)">Quận 3</button>
      <button class="filter-chip" onclick="toggleFilter(this)">Bình Thạnh</button>
      <button class="filter-chip" onclick="toggleFilter(this)">Thủ Đức</button>
      <button class="filter-chip" onclick="toggleFilter(this)">Có mái che</button>
      <button class="filter-chip" onclick="toggleFilter(this)">Camera 24/7</button>
      <button class="filter-chip" onclick="toggleFilter(this)">Còn chỗ ngay</button>
    </div>

    <!-- LIST / MAP TOGGLE -->
    <div class="view-switcher">
      <span style="font-size: 0.83rem; color: var(--text-muted);">12 bãi xe phù hợp</span>
      <div class="view-mode-btns">
        <button class="mode-btn active" id="btnList" onclick="switchListMap('list')">≡ Danh sách</button>
        <button class="mode-btn" id="btnMap" onclick="switchListMap('map')">⊞ Bản đồ</button>
      </div>
    </div>

    <!-- LIST VIEW -->
    <div id="listView" class="parking-list">

      <div class="parking-card" onclick="openModal('Bãi xe Vincom Đồng Khởi', '220', '68', 'Tầng B1, Vincom Center, 70 Lê Thánh Tôn, Q.1', '4.8', 'available')">
        <div class="parking-thumb">🏢</div>
        <div class="parking-info">
          <div class="parking-name">Bãi xe Vincom Đồng Khởi</div>
          <div class="parking-address">📍 70 Lê Thánh Tôn, Quận 1 · 0.3km</div>
          <div class="parking-tags">
            <span class="tag tag-available">● Còn 68 chỗ</span>
            <span class="tag tag-covered">Có mái che</span>
            <span class="tag tag-open">24/7</span>
          </div>
        </div>
        <div class="parking-meta">
          <div class="parking-price">5K <span>/giờ</span></div>
          <div class="occupancy-bar"><div class="occupancy-fill" style="width:70%; background: var(--amber);"></div></div>
          <div class="parking-slots">70% lấp đầy</div>
          <div class="stars">★★★★★ 4.8</div>
        </div>
      </div>

      <div class="parking-card" onclick="openModal('Bãi xe Parkson Hùng Vương', '150', '102', 'Tầng B1, Parkson HV Plaza, Q.5', '4.5', 'available')">
        <div class="parking-thumb">🏬</div>
        <div class="parking-info">
          <div class="parking-name">Parkson Hùng Vương</div>
          <div class="parking-address">📍 Hùng Vương Plaza, Quận 5 · 1.2km</div>
          <div class="parking-tags">
            <span class="tag tag-available">● Còn 102 chỗ</span>
            <span class="tag tag-covered">Có mái che</span>
          </div>
        </div>
        <div class="parking-meta">
          <div class="parking-price">4K <span>/giờ</span></div>
          <div class="occupancy-bar"><div class="occupancy-fill" style="width:32%; background: var(--success);"></div></div>
          <div class="parking-slots">32% lấp đầy</div>
          <div class="stars">★★★★☆ 4.5</div>
        </div>
      </div>

      <div class="parking-card" onclick="openModal('Bãi xe Bến Thành', '80', '4', 'Phố đi bộ Bến Thành, Q.1', '3.9', 'busy')">
        <div class="parking-thumb">🗿</div>
        <div class="parking-info">
          <div class="parking-name">Bãi xe Bến Thành</div>
          <div class="parking-address">📍 Khu vực chợ Bến Thành, Q.1 · 0.7km</div>
          <div class="parking-tags">
            <span class="tag tag-busy">● Còn 4 chỗ</span>
            <span class="tag tag-open">6:00–22:00</span>
          </div>
        </div>
        <div class="parking-meta">
          <div class="parking-price">3K <span>/giờ</span></div>
          <div class="occupancy-bar"><div class="occupancy-fill" style="width:95%; background: var(--danger);"></div></div>
          <div class="parking-slots">95% lấp đầy</div>
          <div class="stars">★★★★☆ 3.9</div>
        </div>
      </div>

      <div class="parking-card" onclick="openModal('Green Park – Landmark 81', '600', '341', 'Tầng B2–B3, Vinhomes Central Park, Q.BT', '4.9', 'available')">
        <div class="parking-thumb">🌿</div>
        <div class="parking-info">
          <div class="parking-name">Green Park – Landmark 81</div>
          <div class="parking-address">📍 Vinhomes Central Park, Bình Thạnh · 2.1km</div>
          <div class="parking-tags">
            <span class="tag tag-available">● Còn 341 chỗ</span>
            <span class="tag tag-covered">Có mái che</span>
            <span class="tag tag-open">24/7</span>
          </div>
        </div>
        <div class="parking-meta">
          <div class="parking-price">8K <span>/giờ</span></div>
          <div class="occupancy-bar"><div class="occupancy-fill" style="width:43%; background: var(--success);"></div></div>
          <div class="parking-slots">43% lấp đầy</div>
          <div class="stars">★★★★★ 4.9</div>
        </div>
      </div>

    </div>

    <!-- MAP VIEW -->
    <div id="mapView" style="display:none;">
      <div class="map-view">
        <div class="map-placeholder">
          <div class="map-bg">
            <div class="map-block" style="grid-column:1/3; grid-row:1/3; opacity:0.3;"></div>
            <div class="map-block" style="grid-column:3/5; grid-row:2/4;"></div>
            <div class="map-block" style="grid-column:6/8; grid-row:1/3;"></div>
            <div class="map-block" style="grid-column:1/2; grid-row:4/6;"></div>
            <div class="map-block" style="grid-column:5/7; grid-row:4/6;"></div>
            <div class="map-block" style="grid-column:7/9; grid-row:3/5;"></div>
            <div class="map-block" style="grid-column:2/4; grid-row:5/7;"></div>
          </div>
          <div class="map-pins">
            <div class="map-pin" style="left:28%; top:38%;">
              <div class="pin-body available">5K · 68 chỗ</div>
            </div>
            <div class="map-pin" style="left:52%; top:58%;">
              <div class="pin-body">4K · 102 chỗ</div>
            </div>
            <div class="map-pin" style="left:38%; top:52%;">
              <div class="pin-body busy">3K · 4 chỗ</div>
            </div>
            <div class="map-pin" style="left:72%; top:30%;">
              <div class="pin-body available">8K · 341 chỗ</div>
            </div>
          </div>
        </div>
      </div>
    </div>

  </div>

</section>

<!-- ══════════════════════════════════════════════════ -->
<!-- B2B – OPERATOR DASHBOARD                          -->
<!-- ══════════════════════════════════════════════════ -->
<section class="page-section" id="sec-b2b">

  <div class="dashboard-header">
    <div>
      <h1>Operator <span>Dashboard</span></h1>
      <div class="operator-name">Bãi xe Vincom Đồng Khởi · Quản lý: Nguyễn Văn Minh</div>
    </div>
    <div style="display: flex; gap: 10px; align-items: center;">
      <div class="live-badge"><div class="live-dot"></div> Live</div>
      <button class="btn btn-ghost" onclick="showToast('Báo cáo đang được tải xuống...')">Xuất báo cáo</button>
    </div>
  </div>

  <!-- KPI CARDS -->
  <div class="kpi-grid">
    <div class="kpi-card">
      <div class="kpi-label">Tỷ lệ lấp đầy hôm nay</div>
      <div class="kpi-value" style="color: var(--amber);" id="kpiOcc">70%</div>
      <div class="kpi-change up">↑ +5.2% so với hôm qua</div>
    </div>
    <div class="kpi-card">
      <div class="kpi-label">Doanh thu hôm nay</div>
      <div class="kpi-value" style="color: var(--accent2);" id="kpiRev">2.4M</div>
      <div class="kpi-change up">↑ +12% so với TB tuần</div>
    </div>
    <div class="kpi-card">
      <div class="kpi-label">Lượt vào ra hôm nay</div>
      <div class="kpi-value" style="color: var(--navy-300);" id="kpiTrips">842</div>
      <div class="kpi-change down">↓ -3% so với hôm qua</div>
    </div>
    <div class="kpi-card">
      <div class="kpi-label">Chỗ trống hiện tại</div>
      <div class="kpi-value" style="color: var(--success);" id="kpiSlots">66</div>
      <div class="kpi-change" style="color:var(--text-muted);">/ 220 tổng chỗ</div>
    </div>
  </div>

  <!-- SLOT MANAGEMENT -->
  <div class="ops-section">
    <h2>Quản lý chỗ đỗ – Cập nhật thủ công</h2>
    <div class="slot-control-grid">

      <div class="slot-panel">
        <div class="slot-panel-title">
          <span class="slot-type-dot" style="background:#F5A623;"></span>
          Xe máy
        </div>
        <div class="slot-counter">
          <button class="counter-btn minus" onclick="adjustSlot('motor', -1)">−</button>
          <span class="counter-value" id="motorSlot">44</span>
          <button class="counter-btn plus" onclick="adjustSlot('motor', 1)">+</button>
        </div>
        <div class="slot-capacity">Tổng: 120 chỗ · Đang dùng: <span id="motorUsed">76</span></div>
        <div class="occ-bar-wrap">
          <div class="occ-bar-fill" id="motorBar" style="width:63%; background: var(--amber);"></div>
        </div>
      </div>

      <div class="slot-panel">
        <div class="slot-panel-title">
          <span class="slot-type-dot" style="background:var(--accent);"></span>
          Ô tô
        </div>
        <div class="slot-counter">
          <button class="counter-btn minus" onclick="adjustSlot('car', -1)">−</button>
          <span class="counter-value" id="carSlot">18</span>
          <button class="counter-btn plus" onclick="adjustSlot('car', 1)">+</button>
        </div>
        <div class="slot-capacity">Tổng: 80 chỗ · Đang dùng: <span id="carUsed">62</span></div>
        <div class="occ-bar-wrap">
          <div class="occ-bar-fill" id="carBar" style="width:78%; background: var(--navy-400);"></div>
        </div>
      </div>

      <div class="slot-panel">
        <div class="slot-panel-title">
          <span class="slot-type-dot" style="background:var(--accent2);"></span>
          VIP / SUV
        </div>
        <div class="slot-counter">
          <button class="counter-btn minus" onclick="adjustSlot('vip', -1)">−</button>
          <span class="counter-value" id="vipSlot">4</span>
          <button class="counter-btn plus" onclick="adjustSlot('vip', 1)">+</button>
        </div>
        <div class="slot-capacity">Tổng: 20 chỗ · Đang dùng: <span id="vipUsed">16</span></div>
        <div class="occ-bar-wrap">
          <div class="occ-bar-fill" id="vipBar" style="width:80%; background: var(--accent2); opacity:0.8;"></div>
        </div>
      </div>

    </div>
  </div>

  <!-- CHARTS -->
  <div class="charts-row">
    <div class="chart-panel">
      <div class="chart-title">Doanh thu theo giờ hôm nay (VNĐ)</div>
      <div class="bar-chart" id="revenueChart">
        <!-- JS fills this -->
      </div>
    </div>
    <div class="chart-panel">
      <div class="chart-title">Phân bổ loại xe</div>
      <div class="donut-wrap">
        <svg width="100" height="100" viewBox="0 0 36 36">
          <circle cx="18" cy="18" r="14" fill="none" stroke="var(--navy-800)" stroke-width="5"/>
          <circle cx="18" cy="18" r="14" fill="none" stroke="var(--amber)" stroke-width="5"
            stroke-dasharray="55 100" stroke-dashoffset="-25" transform="rotate(-90 18 18)"/>
          <circle cx="18" cy="18" r="14" fill="none" stroke="var(--accent)" stroke-width="5"
            stroke-dasharray="28 100" stroke-dashoffset="-80" transform="rotate(-90 18 18)"/>
          <circle cx="18" cy="18" r="14" fill="none" stroke="var(--accent2)" stroke-width="5"
            stroke-dasharray="10 100" stroke-dashoffset="-108" transform="rotate(-90 18 18)"/>
          <text x="18" y="18" text-anchor="middle" dominant-baseline="central"
            fill="var(--text-primary)" font-size="5" font-weight="700">70%</text>
        </svg>
        <div class="donut-legend">
          <div class="legend-item"><span class="legend-dot" style="background:var(--amber);"></span> Xe máy <span class="legend-val">55%</span></div>
          <div class="legend-item"><span class="legend-dot" style="background:var(--accent);"></span> Ô tô <span class="legend-val">28%</span></div>
          <div class="legend-item"><span class="legend-dot" style="background:var(--accent2);"></span> VIP/SUV <span class="legend-val">10%</span></div>
          <div class="legend-item"><span class="legend-dot" style="background:var(--navy-600);"></span> Xe khác <span class="legend-val">7%</span></div>
        </div>
      </div>
    </div>
  </div>

  <!-- REPORTS -->
  <div class="reports-section">
    <div class="report-card">
      <div class="report-header">
        <div class="report-title">Giờ cao điểm hôm nay</div>
        <span style="font-size:0.72rem; color:var(--accent); font-weight:600;">Thứ 3, 06/05</span>
      </div>
      <div class="peak-list">
        <div class="peak-row">
          <span class="peak-time">07:00–08:00</span>
          <div class="peak-bar-bg"><div class="peak-bar-val" style="width:75%; background:var(--amber);"></div></div>
          <span class="peak-pct">75%</span>
        </div>
        <div class="peak-row">
          <span class="peak-time">12:00–13:00</span>
          <div class="peak-bar-bg"><div class="peak-bar-val" style="width:92%; background:var(--danger);"></div></div>
          <span class="peak-pct">92%</span>
        </div>
        <div class="peak-row">
          <span class="peak-time">17:00–19:00</span>
          <div class="peak-bar-bg"><div class="peak-bar-val" style="width:88%; background:var(--amber);"></div></div>
          <span class="peak-pct">88%</span>
        </div>
        <div class="peak-row">
          <span class="peak-time">21:00–22:00</span>
          <div class="peak-bar-bg"><div class="peak-bar-val" style="width:34%; background:var(--navy-400);"></div></div>
          <span class="peak-pct">34%</span>
        </div>
      </div>
    </div>

    <div class="report-card">
      <div class="report-header">
        <div class="report-title">Hiệu suất tài sản</div>
        <span style="font-size:0.72rem; color:var(--accent2); font-weight:600;">+15% target</span>
      </div>
      <div class="metric-row">
        <span class="label">Lượng khách TB/ngày</span>
        <span class="val" style="color:var(--navy-300);">712</span>
      </div>
      <div class="metric-row">
        <span class="label">Doanh thu TB/ngày</span>
        <span class="val" style="color:var(--accent2);">2.2M ₫</span>
      </div>
      <div class="metric-row">
        <span class="label">Asset utilization</span>
        <span class="val" style="color:var(--amber);">68.4%</span>
      </div>
      <div class="metric-row">
        <span class="label">Doanh thu/chỗ/ngày</span>
        <span class="val">10K ₫</span>
      </div>
      <div class="metric-row">
        <span class="label">Occupancy tối ưu</span>
        <span class="val" style="color:var(--success);">+26% tiềm năng</span>
      </div>
    </div>
  </div>

  <!-- MARKETING -->
  <div class="marketing-section">
    <div class="ops-section" style="padding:0; border:none; margin-bottom:1.5rem;">
      <h2 style="margin-bottom:1rem;">Marketing & Hồ sơ bãi xe</h2>
      <div class="profile-upload" onclick="showToast('Chức năng tải ảnh sắp ra mắt!')">
        <div style="font-size:2rem;">📸</div>
        <p>Kéo thả ảnh bãi xe hoặc <strong style="color:var(--accent)">chọn từ máy tính</strong></p>
        <p style="font-size:0.72rem; margin-top:4px;">JPG, PNG tối đa 10MB · Khuyến nghị: 1200×800px</p>
      </div>
    </div>

    <div style="margin-bottom:1rem;">
      <div class="section-title">Gói quảng bá (Featured Listing)</div>
    </div>
    <div class="promo-grid">
      <div class="promo-card">
        <div class="promo-name">Basic</div>
        <div class="promo-price">Miễn phí <span>/tháng</span></div>
        <ul class="promo-features">
          <li>✓ Hiển thị trên nền tảng</li>
          <li>✓ Hồ sơ cơ bản</li>
          <li>✗ Ưu tiên tìm kiếm</li>
        </ul>
        <button class="btn btn-ghost" style="margin-top:14px; width:100%; justify-content:center; font-size:0.8rem;">Đang dùng</button>
      </div>
      <div class="promo-card recommended">
        <div style="font-size:0.68rem; font-weight:700; color:var(--accent); margin-bottom:6px; letter-spacing:0.08em;">★ PHỔ BIẾN NHẤT</div>
        <div class="promo-name">Pro</div>
        <div class="promo-price">299K <span>/tháng</span></div>
        <ul class="promo-features">
          <li>✓ Ưu tiên top tìm kiếm</li>
          <li>✓ Banner quảng cáo</li>
          <li>✓ Phân tích nâng cao</li>
        </ul>
        <button class="btn btn-accent" style="margin-top:14px; width:100%; justify-content:center; font-size:0.8rem;" onclick="showToast('Đang chuyển đến trang thanh toán...')">Nâng cấp ngay</button>
      </div>
      <div class="promo-card">
        <div class="promo-name">Enterprise</div>
        <div class="promo-price">Liên hệ <span></span></div>
        <ul class="promo-features">
          <li>✓ Quảng bá toàn hệ thống</li>
          <li>✓ API tích hợp</li>
          <li>✓ Account manager</li>
        </ul>
        <button class="btn btn-ghost" style="margin-top:14px; width:100%; justify-content:center; font-size:0.8rem;" onclick="showToast('Đội sales sẽ liên hệ bạn trong 24h!')">Liên hệ tư vấn</button>
      </div>
    </div>
  </div>

</section>

<!-- ─── FOOTER ─── -->
<footer>
  <p>© 2025 ParkConnect · Nền tảng quản lý bãi xe thông minh · TP. Hồ Chí Minh</p>
  <ul class="footer-links">
    <li><a href="#">Điều khoản</a></li>
    <li><a href="#">Bảo mật</a></li>
    <li><a href="#">Liên hệ</a></li>
    <li><a href="#">API Docs</a></li>
  </ul>
</footer>

<!-- ─── BOOKING MODAL ─── -->
<div class="modal-overlay" id="bookingModal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal()">✕</button>
    <div class="modal-title" id="modalName">–</div>
    <div class="modal-subtitle" id="modalAddr">–</div>
    <div class="modal-row"><span class="label">Số chỗ trống</span><span class="val" id="modalSlots" style="color:var(--success);">–</span></div>
    <div class="modal-row"><span class="label">Tổng sức chứa</span><span class="val" id="modalTotal">–</span></div>
    <div class="modal-row"><span class="label">Giá đỗ xe</span><span class="val" id="modalPrice">–</span></div>
    <div class="modal-row"><span class="label">Đánh giá</span><span class="val" id="modalRating">–</span></div>
    <div class="modal-row"><span class="label">Đặt trước</span><span class="val" style="color:var(--accent);">Cho phép (30 phút)</span></div>
    <div class="modal-footer">
      <button class="btn btn-accent" style="flex:1; justify-content:center;" onclick="showToast('Đặt chỗ thành công! Mã xác nhận: #PC2025'); closeModal();">Đặt chỗ ngay</button>
      <button class="btn btn-ghost" onclick="closeModal()">Đóng</button>
    </div>
  </div>
</div>

<!-- ─── TOAST ─── -->
<div class="toast" id="toast"></div>

<script>
  /* ─── VIEW SWITCH ─── */
  function switchView(v) {
    document.getElementById('sec-b2c').classList.toggle('active', v === 'b2c');
    document.getElementById('sec-b2b').classList.toggle('active', v === 'b2b');
    document.getElementById('btnB2C').classList.toggle('active', v === 'b2c');
    document.getElementById('btnB2B').classList.toggle('active', v === 'b2b');
    if (v === 'b2b') buildChart();
  }

  function navTo(e, v) {
    e.preventDefault();
    document.querySelectorAll('.nav-links a').forEach(a => a.classList.remove('active'));
    e.target.classList.add('active');
    switchView(v);
  }

  /* ─── VEHICLE ─── */
  function selectVehicle(el) {
    document.querySelectorAll('.vehicle-card').forEach(c => c.classList.remove('selected'));
    el.classList.add('selected');
    showToast('Đã chọn: ' + el.querySelector('.vehicle-name').textContent);
  }

  /* ─── FILTER ─── */
  function toggleFilter(el) {
    el.classList.toggle('active');
  }

  /* ─── LIST / MAP ─── */
  function switchListMap(mode) {
    document.getElementById('listView').style.display = mode === 'list' ? 'flex' : 'none';
    document.getElementById('mapView').style.display = mode === 'map' ? 'block' : 'none';
    document.getElementById('btnList').classList.toggle('active', mode === 'list');
    document.getElementById('btnMap').classList.toggle('active', mode === 'map');
  }

  /* ─── SLOT CONTROLS ─── */
  const caps = { motor: 120, car: 80, vip: 20 };
  const slotData = { motor: { free: 44, total: 120 }, car: { free: 18, total: 80 }, vip: { free: 4, total: 20 } };

  function adjustSlot(type, delta) {
    const d = slotData[type];
    d.free = Math.max(0, Math.min(d.total, d.free + delta));
    const used = d.total - d.free;
    const pct = Math.round((used / d.total) * 100);
    document.getElementById(type + 'Slot').textContent = d.free;
    document.getElementById(type + 'Used').textContent = used;
    const bar = document.getElementById(type + 'Bar');
    bar.style.width = pct + '%';

    const totalFree = slotData.motor.free + slotData.car.free + slotData.vip.free;
    const totalAll = 220;
    const totalOcc = Math.round(((totalAll - totalFree) / totalAll) * 100);
    document.getElementById('kpiOcc').textContent = totalOcc + '%';
    document.getElementById('kpiSlots').textContent = totalFree;
    showToast(delta > 0 ? '✓ Thêm 1 chỗ trống' : '✓ Ghi nhận 1 xe vào');
  }

  /* ─── REVENUE CHART ─── */
  const hours = ['6h','7h','8h','9h','10h','11h','12h','13h','14h','15h','16h','17h','18h','19h','20h'];
  const rev   = [80,180,210,150,120,200,280,240,130,110,160,290,270,140,90];
  const maxR  = Math.max(...rev);

  function buildChart() {
    const container = document.getElementById('revenueChart');
    if (!container || container.children.length > 0) return;
    hours.forEach((h, i) => {
      const pct = (rev[i] / maxR) * 100;
      const isPeak = rev[i] > 250;
      const col = document.createElement('div'); col.className = 'bar-col';
      const bar = document.createElement('div');
      bar.className = 'bar-fill' + (isPeak ? ' peak' : '');
      bar.style.height = pct + '%';
      bar.title = h + ': ' + rev[i] + 'K ₫';
      bar.onclick = () => showToast(h + ' → ' + rev[i] + 'K ₫ doanh thu');
      const label = document.createElement('div'); label.className = 'bar-label'; label.textContent = h;
      col.appendChild(bar); col.appendChild(label);
      container.appendChild(col);
    });
  }

  /* ─── MODAL ─── */
  function openModal(name, total, free, addr, rating, status) {
    document.getElementById('modalName').textContent = name;
    document.getElementById('modalAddr').textContent = '📍 ' + addr;
    document.getElementById('modalSlots').textContent = free + ' chỗ trống';
    document.getElementById('modalTotal').textContent = total + ' chỗ';
    document.getElementById('modalPrice').textContent = name.includes('Vincom') ? '5.000 ₫/giờ · 50K/ngày' : name.includes('Green') ? '8.000 ₫/giờ' : '3.000–4.000 ₫/giờ';
    document.getElementById('modalRating').textContent = '★ ' + rating + ' / 5.0';
    document.getElementById('bookingModal').classList.add('open');
  }

  function closeModal() {
    document.getElementById('bookingModal').classList.remove('open');
  }

  document.getElementById('bookingModal').addEventListener('click', function(e) {
    if (e.target === this) closeModal();
  });

  /* ─── TOAST ─── */
  let toastTimer;
  function showToast(msg) {
    const t = document.getElementById('toast');
    t.textContent = msg;
    t.classList.add('show');
    clearTimeout(toastTimer);
    toastTimer = setTimeout(() => t.classList.remove('show'), 2800);
  }
</script>
</body>
</html>
