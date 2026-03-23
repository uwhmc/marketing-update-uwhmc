<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>UWHMC — Board Marketing Update</title>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --blue:   #0044B5;
    --red:    #D12626;
    --yellow: #FFBA00;
    --dk:     #21296B;
    --dkblue: #21296B;
    --green:  #009464;
    --ltblue: #A7D2FF;
    --ltyel:  #FFF3CD;
    --ltgray: #F4F6F9;
    --border: #E4E6EA;
    --gray:   #6B7280;
    --white:  #FFFFFF;
    --card-r: 6px;
  }

  body {
    font-family: Arial, sans-serif;
    background: #1A2744;
    margin: 0;
    padding: 48px 24px 64px;
  }

  .page {
    width: 720px;
    margin: 0 auto;
    background: var(--white);
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 24px 80px rgba(0,0,0,0.5);
  }

  /* ── DARK HEADER ─────────────────────────────────────── */
  .header {
    background: var(--dk);
    padding: 44px 48px 40px;
    position: relative;
    overflow: hidden;
  }

  .header-bg {
    position: absolute;
    inset: 0;
    pointer-events: none;
  }

  .header-top {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    position: relative;
    z-index: 2;
  }

  .header-org {
    font-size: 10px;
    font-weight: bold;
    letter-spacing: 2.5px;
    text-transform: uppercase;
    color: rgba(255,255,255,0.4);
    margin-bottom: 16px;
  }

  .header-title {
    font-size: 36px;
    font-weight: 900;
    text-transform: uppercase;
    color: var(--white);
    line-height: 1.0;
    letter-spacing: -0.5px;
  }

  .header-title em {
    color: var(--yellow);
    font-style: normal;
  }

  .header-badge {
    background: rgba(255,255,255,0.07);
    border: 1px solid rgba(255,255,255,0.12);
    border-radius: 4px;
    padding: 10px 16px;
    text-align: right;
    flex-shrink: 0;
  }

  .header-badge-label {
    font-size: 9px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: rgba(255,255,255,0.4);
    margin-bottom: 4px;
  }

  .header-badge-val {
    font-size: 13px;
    font-weight: bold;
    color: var(--white);
  }

  /* Yellow accent line */
  .accent-bar {
    height: 3px;
    background: linear-gradient(to right, var(--yellow), var(--red), transparent);
    position: relative;
    z-index: 2;
    margin-top: 28px;
  }

  /* ── BODY ──────────────────────────────────────────── */
  .body {
    padding: 32px 48px 40px;
    background: var(--ltgray);
    display: flex;
    flex-direction: column;
    gap: 24px;
  }

  /* ── ROW LAYOUT ────────────────────────────────────── */
  .row {
    display: grid;
    gap: 16px;
  }
  .row-2 { grid-template-columns: 1fr 1fr; }
  .row-3 { grid-template-columns: 1fr 1fr 1fr; }
  .row-1 { grid-template-columns: 1fr; }

  /* ── BASE CARD ─────────────────────────────────────── */
  .card {
    background: var(--white);
    border-radius: var(--card-r);
    border: 1px solid var(--border);
    overflow: hidden;
  }

  .card-inner {
    padding: 20px 22px;
  }

  .card-label {
    font-size: 8.5px;
    font-weight: bold;
    letter-spacing: 2.5px;
    text-transform: uppercase;
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 7px;
  }

  .card-label-dot {
    width: 6px;
    height: 6px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  .card-title {
    font-size: 17px;
    font-weight: 900;
    text-transform: uppercase;
    letter-spacing: -0.2px;
    line-height: 1.15;
    margin-bottom: 10px;
  }

  .card-body {
    font-size: 12.5px;
    color: var(--gray);
    line-height: 1.7;
  }

  /* ── STAT CARD ─────────────────────────────────────── */
  .stat-card {
    background: var(--white);
    border-radius: var(--card-r);
    border: 1px solid var(--border);
    padding: 20px 22px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    gap: 8px;
  }

  .stat-label {
    font-size: 9px;
    font-weight: bold;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--gray);
  }

  .stat-number {
    font-size: 40px;
    font-weight: 900;
    line-height: 1;
    letter-spacing: -1px;
  }

  .stat-change {
    font-size: 11px;
    font-weight: bold;
    display: inline-flex;
    align-items: center;
    gap: 4px;
    padding: 3px 8px;
    border-radius: 20px;
  }

  .up   { color: #166534; background: #DCFCE7; }
  .meta { font-size: 10.5px; color: var(--gray); margin-top: 2px; line-height: 1.5; }

  /* ── HERO STAT CARD ────────────────────────────────── */
  .hero-stat {
    background: var(--dk);
    border-radius: var(--card-r);
    padding: 24px 26px;
    border: none;
    position: relative;
    overflow: hidden;
  }

  .hero-stat-bg {
    position: absolute;
    inset: 0;
    pointer-events: none;
  }

  .hero-stat-label {
    font-size: 9px;
    font-weight: bold;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: rgba(255,255,255,0.45);
    margin-bottom: 10px;
    position: relative;
    z-index: 2;
  }

  .hero-stat-num {
    font-size: 52px;
    font-weight: 900;
    color: var(--yellow);
    line-height: 1;
    letter-spacing: -2px;
    position: relative;
    z-index: 2;
  }

  .hero-stat-change {
    font-size: 12px;
    font-weight: bold;
    color: #4ADE80;
    margin-top: 8px;
    position: relative;
    z-index: 2;
  }

  .hero-stat-desc {
    font-size: 11px;
    color: rgba(255,255,255,0.5);
    margin-top: 6px;
    line-height: 1.5;
    position: relative;
    z-index: 2;
  }

  /* ── INSIGHT CARD ──────────────────────────────────── */
  .insight-card {
    background: var(--dkblue);
    border-radius: var(--card-r);
    padding: 22px 24px;
    border: none;
  }

  .insight-label {
    font-size: 9px;
    letter-spacing: 2px;
    font-weight: bold;
    text-transform: uppercase;
    color: var(--ltblue);
    margin-bottom: 12px;
    opacity: 0.7;
  }

  .insight-text {
    font-size: 15px;
    font-weight: bold;
    color: var(--white);
    line-height: 1.5;
  }

  .insight-text em {
    color: var(--yellow);
    font-style: normal;
  }

  /* ── SECTION HEADER ────────────────────────────────── */
  .section-header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 0;
  }

  .section-header-line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .section-header-label {
    font-size: 8.5px;
    font-weight: bold;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--gray);
    white-space: nowrap;
  }

  /* ── WAREHOUSE CARD ────────────────────────────────── */
  .warehouse-header {
    background: var(--red);
    padding: 18px 22px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .warehouse-header-title {
    font-size: 15px;
    font-weight: 900;
    text-transform: uppercase;
    color: var(--white);
    letter-spacing: 0.2px;
  }

  .warehouse-tag {
    background: rgba(255,255,255,0.18);
    border-radius: 3px;
    padding: 3px 10px;
    font-size: 9px;
    font-weight: bold;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--white);
  }

  .warehouse-body {
    padding: 20px 22px;
    background: var(--white);
  }

  .warehouse-desc {
    font-size: 12.5px;
    color: var(--gray);
    line-height: 1.65;
    margin-bottom: 16px;
  }

  .items-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 8px;
  }

  .item-chip {
    background: var(--ltgray);
    border-radius: 4px;
    padding: 10px 12px;
    border-left: 3px solid var(--blue);
    display: flex;
    align-items: flex-start;
    gap: 10px;
  }

  .item-chip.red-b  { border-left-color: var(--red); }
  .item-chip.yel-b  { border-left-color: var(--yellow); }
  .item-chip.grn-b  { border-left-color: var(--green); }

  .item-chip-text { flex: 1; }

  .item-chip-title {
    font-size: 10px;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 0.8px;
    color: var(--dkblue);
    margin-bottom: 3px;
  }

  .item-chip-bullets {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .item-chip-bullets li {
    font-size: 10.5px;
    color: var(--gray);
    line-height: 1.5;
    display: flex;
    gap: 5px;
    align-items: flex-start;
  }

  .item-chip-bullets li::before {
    content: "·";
    color: var(--gray);
    flex-shrink: 0;
    font-weight: bold;
  }

  .network-note {
    margin-top: 14px;
    background: var(--ltyel);
    border-left: 3px solid var(--yellow);
    border-radius: 0 4px 4px 0;
    padding: 10px 14px;
    font-size: 11.5px;
    color: var(--dkblue);
    font-weight: bold;
  }

  /* ── ACTION CARDS ──────────────────────────────────── */
  .action-card {
    background: var(--white);
    border-radius: var(--card-r);
    border: 1px solid var(--border);
    padding: 18px 20px;
    display: flex;
    gap: 16px;
    align-items: flex-start;
  }

  .action-num {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 13px;
    font-weight: 900;
    flex-shrink: 0;
    color: var(--white);
  }

  .action-content strong {
    display: block;
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    color: var(--dkblue);
    margin-bottom: 4px;
    font-weight: 900;
  }

  .action-content span {
    font-size: 12px;
    color: var(--gray);
    line-height: 1.6;
  }

  /* ── STRATEGY BULLETS ──────────────────────────────── */
  .strategy-bullets {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: 9px;
  }

  .strategy-bullets li {
    display: flex;
    gap: 10px;
    align-items: flex-start;
    font-size: 12.5px;
    color: var(--gray);
    line-height: 1.55;
  }

  .strategy-bullets li .dash {
    color: var(--blue);
    font-weight: 900;
    flex-shrink: 0;
    margin-top: 0;
    font-size: 14px;
  }

  /* ── INSTAGRAM ROW ─────────────────────────────────── */
  .ig-row {
    display: flex;
    gap: 12px;
    align-items: center;
    margin-top: 14px;
    padding-top: 14px;
    border-top: 1px solid var(--border);
    flex-wrap: wrap;
  }

  .ig-label {
    font-size: 9px;
    font-weight: bold;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--gray);
    flex-shrink: 0;
  }

  .ig-stat {
    font-size: 12px;
    color: var(--dkblue);
    font-weight: 600;
  }

  .ig-stat strong { color: var(--blue); }

  /* ── FOOTER ────────────────────────────────────────── */
  .footer {
    background: var(--dk);
    padding: 18px 48px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .footer-org {
    font-size: 10px;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 2px;
    color: rgba(255,255,255,0.5);
  }

  .footer-pillars {
    display: flex;
    gap: 6px;
  }

  .footer-pill {
    font-size: 8px;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 0.8px;
    padding: 3px 8px;
    border-radius: 2px;
    color: var(--white);
  }

  @media print {
    body { background: white; padding: 0; }
    .page { box-shadow: none; border-radius: 0; width: 100%; }
  }
</style>
</head>
<body>
<div class="page">

  <!-- ══ DARK HEADER ════════════════════════════════════ -->
  <div class="header">
    <svg class="header-bg" viewBox="0 0 720 180" fill="none" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMaxYMid meet">
      <path d="M500 180 Q600 80 720 0"  stroke="white" stroke-width="60" opacity="0.025" stroke-linecap="round"/>
      <path d="M540 180 Q630 85 720 20" stroke="white" stroke-width="36" opacity="0.02"  stroke-linecap="round"/>
      <path d="M580 180 Q660 90 720 40" stroke="white" stroke-width="18" opacity="0.018" stroke-linecap="round"/>
      <path d="M660 0 Q700 40 720 90"   stroke="#FFBA00" stroke-width="4" opacity="0.3" stroke-linecap="round"/>
      <path d="M680 0 Q712 30 720 65"   stroke="#FFBA00" stroke-width="2" opacity="0.2" stroke-linecap="round"/>
    </svg>

    <div class="header-top">
      <div>
        <div class="header-org">United Way of Harvey &amp; Marion Counties</div>
        <div class="header-title">Marketing<br><em>Update.</em></div>
      </div>
      <div class="header-badge">
        <div class="header-badge-label">Board Briefing</div>
        <div class="header-badge-val">March 2026</div>
      </div>
    </div>
    <div class="accent-bar"></div>
  </div>

  <!-- ══ BODY ══════════════════════════════════════════ -->
  <div class="body">

    <!-- ── SECTION: SOCIAL GROWTH ── -->
    <div class="section-header">
      <div class="section-header-label">Social Media Performance — Last 28 Days</div>
      <div class="section-header-line"></div>
    </div>

    <!-- Hero stat + 3 supporting stats -->
    <div class="row row-2" style="grid-template-columns: 1.1fr 0.9fr; gap:16px;">

      <!-- Left: 2 hero stats stacked -->
      <div style="display:flex; flex-direction:column; gap:16px;">

        <div class="hero-stat">
          <svg class="hero-stat-bg" viewBox="0 0 340 130" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M220 130 Q290 50 340 0" stroke="white" stroke-width="50" opacity="0.04" stroke-linecap="round"/>
            <path d="M260 130 Q320 55 340 20" stroke="white" stroke-width="28" opacity="0.03" stroke-linecap="round"/>
          </svg>
          <div class="hero-stat-label">Unique Viewers</div>
          <div class="hero-stat-num">6,773</div>
          <div class="hero-stat-change">↑ 146.3%</div>
          <div class="hero-stat-desc">People who saw our content this month</div>
        </div>

        <div class="hero-stat" style="background: #0A3080;">
          <svg class="hero-stat-bg" viewBox="0 0 340 130" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M220 130 Q290 50 340 0" stroke="white" stroke-width="50" opacity="0.07" stroke-linecap="round"/>
          </svg>
          <div class="hero-stat-label" style="color:rgba(255,255,255,0.55);">Total Views</div>
          <div class="hero-stat-num" style="color:var(--white); font-size:44px;">17.4K</div>
          <div class="hero-stat-change">↑ 53.5%</div>
          <div class="hero-stat-desc">Impressions across all content</div>
        </div>

      </div>

      <!-- Right: insight + 2 supporting stats -->
      <div style="display:flex; flex-direction:column; gap:16px;">

        <div class="insight-card">
          <div class="insight-label">Key Insight</div>
          <div class="insight-text"><em>77%</em> of our views are coming from people who don't follow us yet.</div>
        </div>

        <div class="row row-2" style="gap:12px;">
          <div class="stat-card">
            <div class="stat-label">Non-Follower Views</div>
            <div class="stat-number" style="color:var(--blue); font-size:32px;">77%</div>
            <div><span class="stat-change up">↑ 46.3%</span></div>
            <div class="meta">Content being shared &amp; discovered</div>
          </div>
          <div class="stat-card">
            <div class="stat-label">Net New Followers</div>
            <div class="stat-number" style="color:var(--green); font-size:32px;">+15</div>
            <div><span class="stat-change up">↑ 400%</span></div>
            <div class="meta">Page visits up 7.5%</div>
          </div>
        </div>

        <!-- Instagram row -->
        <div class="card">
          <div class="card-inner" style="padding: 14px 18px;">
            <div class="stat-label" style="margin-bottom:10px;">Instagram — Week of Mar 8–14</div>
            <div class="ig-row" style="margin-top:0; padding-top:0; border-top:none; gap:16px;">
              <div class="ig-stat">Post views <strong>↑ 60.7%</strong> WoW</div>
              <div class="ig-stat">Story views <strong>↑ 30.8%</strong> WoW</div>
            </div>
          </div>
        </div>

      </div>
    </div>

    <!-- ── SECTION: STRATEGY ── -->
    <div class="section-header">
      <div class="section-header-label">Marketing Strategy</div>
      <div class="section-header-line"></div>
    </div>

    <div class="row row-2">
      <div class="card">
        <div class="card-inner">
          <div class="card-label" style="color:var(--blue);">
            <div class="card-label-dot" style="background:var(--blue);"></div>
            Where We Are
          </div>
          <div class="card-title" style="color:var(--dkblue); font-size:14px;">The Gap Is the Opportunity</div>
          <ul class="strategy-bullets" style="margin-top:12px;">
            <li><span class="dash">—</span><span>Newton's top Facebook page: <strong>9,748</strong> followers. Ours: <strong>1,133</strong></span></li>
            <li><span class="dash">—</span><span>Harvey County Now + Newton Kansan: <strong>15,000+</strong> combined readers — free channel</span></li>
            <li><span class="dash">—</span><span>Nextdoor Newton: <strong>18,500</strong> residents — UWHMC has zero presence today</span></li>
          </ul>
        </div>
      </div>
      <div class="card">
        <div class="card-inner">
          <div class="card-label" style="color:var(--green);">
            <div class="card-label-dot" style="background:var(--green);"></div>
            Where We're Going
          </div>
          <div class="card-title" style="color:var(--dkblue); font-size:14px;">Community Infrastructure, Not a Charity</div>
          <ul class="strategy-bullets" style="margin-top:12px;">
            <li><span class="dash">—</span><span>Consistent social presence — 3x per week, on a system</span></li>
            <li><span class="dash">—</span><span>Earned media — press release every 6–8 weeks</span></li>
            <li><span class="dash">—</span><span>Email newsletter — building list from zero toward 300</span></li>
            <li><span class="dash">—</span><span>Per-capita giving: $9.17 today vs. $18–22 at peers</span></li>
          </ul>
        </div>
      </div>
    </div>

    <!-- ── SECTION: WAREHOUSE ── -->
    <div class="section-header">
      <div class="section-header-label">Warehouse Build-Out</div>
      <div class="section-header-line"></div>
    </div>

    <div class="card" style="padding:0; overflow:hidden;">
      <div class="warehouse-header">
        <div class="warehouse-header-title">We Are Building a Warehouse For Everyone</div>
        <div class="warehouse-tag">Not Yet Public</div>
      </div>
      <div class="warehouse-body">
        <div class="warehouse-desc">A community resource warehouse open to every Harvey County resident — furniture, appliances, and household goods for families getting back on their feet. Currently in build-out. We need this board to source what fills it.</div>
        <div class="items-grid">
          <div class="item-chip">
            <svg width="22" height="22" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg" style="flex-shrink:0; margin-top:1px;">
              <path d="M5 20v-5a2 2 0 012-2h22a2 2 0 012 2v5" stroke="#0044B5" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
              <path d="M3 20a2 2 0 012-2h1a2 2 0 012 2v4H3v-4z" stroke="#0044B5" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
              <path d="M33 20a2 2 0 00-2-2h-1a2 2 0 00-2 2v4h5v-4z" stroke="#0044B5" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
              <path d="M8 24h20v2a1 1 0 01-1 1H9a1 1 0 01-1-1v-2z" stroke="#0044B5" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
              <line x1="7" y1="27" x2="7" y2="30" stroke="#0044B5" stroke-width="2.2" stroke-linecap="round"/>
              <line x1="29" y1="27" x2="29" y2="30" stroke="#0044B5" stroke-width="2.2" stroke-linecap="round"/>
            </svg>
            <div class="item-chip-text">
              <div class="item-chip-title">Furniture</div>
              <ul class="item-chip-bullets">
                <li>Sofas &amp; chairs</li>
                <li>Beds &amp; dressers</li>
              </ul>
            </div>
          </div>
          <div class="item-chip red-b">
            <svg width="22" height="22" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg" style="flex-shrink:0; margin-top:1px;">
              <rect x="4" y="4" width="13" height="28" rx="2" stroke="#D12626" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
              <circle cx="10.5" cy="20" r="5" stroke="#D12626" stroke-width="2.2" stroke-linecap="round"/>
              <circle cx="10.5" cy="20" r="2" stroke="#D12626" stroke-width="1.5" stroke-linecap="round"/>
              <line x1="7" y1="9" x2="9" y2="9" stroke="#D12626" stroke-width="2" stroke-linecap="round"/>
              <circle cx="12.5" cy="9" r="1" fill="#D12626"/>
              <rect x="19" y="4" width="13" height="28" rx="2" stroke="#D12626" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
              <circle cx="25.5" cy="20" r="5" stroke="#D12626" stroke-width="2.2" stroke-linecap="round"/>
              <circle cx="25.5" cy="20" r="2" stroke="#D12626" stroke-width="1.5" stroke-linecap="round"/>
              <line x1="22" y1="9" x2="24" y2="9" stroke="#D12626" stroke-width="2" stroke-linecap="round"/>
              <circle cx="27.5" cy="9" r="1" fill="#D12626"/>
            </svg>
            <div class="item-chip-text">
              <div class="item-chip-title">Washers &amp; Dryers</div>
              <ul class="item-chip-bullets">
                <li>Working units</li>
                <li>Sets or individual</li>
              </ul>
            </div>
          </div>
          <div class="item-chip yel-b">
            <svg width="22" height="22" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg" style="flex-shrink:0; margin-top:1px;">
              <rect x="4" y="13" width="28" height="4" rx="1.5" stroke="#FFBA00" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
              <line x1="9" y1="17" x2="9" y2="28" stroke="#FFBA00" stroke-width="2.2" stroke-linecap="round"/>
              <line x1="27" y1="17" x2="27" y2="28" stroke="#FFBA00" stroke-width="2.2" stroke-linecap="round"/>
              <path d="M5 7a3 3 0 013-3h1a1 1 0 011 1v8H5V7z" stroke="#FFBA00" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              <path d="M31 7a3 3 0 00-3-3h-1a1 1 0 00-1 1v8h5V7z" stroke="#FFBA00" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
            <div class="item-chip-text">
              <div class="item-chip-title">Tables &amp; Chairs</div>
              <ul class="item-chip-bullets">
                <li>Dining &amp; kitchen</li>
                <li>Any size</li>
              </ul>
            </div>
          </div>
          <div class="item-chip grn-b">
            <svg width="22" height="22" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg" style="flex-shrink:0; margin-top:1px;">
              <rect x="4" y="4" width="28" height="4" rx="1.5" stroke="#009464" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
              <rect x="4" y="16" width="28" height="4" rx="1.5" stroke="#009464" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
              <rect x="4" y="28" width="28" height="4" rx="1.5" stroke="#009464" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
              <line x1="6" y1="8" x2="6" y2="16" stroke="#009464" stroke-width="2.2" stroke-linecap="round"/>
              <line x1="30" y1="8" x2="30" y2="16" stroke="#009464" stroke-width="2.2" stroke-linecap="round"/>
              <line x1="6" y1="20" x2="6" y2="28" stroke="#009464" stroke-width="2.2" stroke-linecap="round"/>
              <line x1="30" y1="20" x2="30" y2="28" stroke="#009464" stroke-width="2.2" stroke-linecap="round"/>
            </svg>
            <div class="item-chip-text">
              <div class="item-chip-title">Shelving</div>
              <ul class="item-chip-bullets">
                <li>Industrial or freestanding</li>
                <li>New or used</li>
              </ul>
            </div>
          </div>
          <div class="item-chip">
            <svg width="22" height="22" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg" style="flex-shrink:0; margin-top:1px;">
              <path d="M18 4C13.03 4 9 8.03 9 13c0 3.18 1.62 5.97 4.08 7.64V23a1 1 0 001 1h7.84a1 1 0 001-1v-2.36C25.38 18.97 27 16.18 27 13c0-4.97-4.03-9-9-9z" stroke="#0044B5" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
              <line x1="14" y1="27" x2="22" y2="27" stroke="#0044B5" stroke-width="2.2" stroke-linecap="round"/>
              <line x1="15.5" y1="30.5" x2="20.5" y2="30.5" stroke="#0044B5" stroke-width="2.2" stroke-linecap="round"/>
            </svg>
            <div class="item-chip-text">
              <div class="item-chip-title">Lighting</div>
              <ul class="item-chip-bullets">
                <li>Shop &amp; overhead</li>
                <li>Lamps for families</li>
              </ul>
            </div>
          </div>
          <div class="item-chip red-b">
            <svg width="22" height="22" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg" style="flex-shrink:0; margin-top:1px;">
              <path d="M6 13.5h4l14-7v21l-14-7H6a1.5 1.5 0 01-1.5-1.5v-4A1.5 1.5 0 016 13.5z" stroke="#D12626" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
              <path d="M10 20.5v6a1 1 0 001 1h2.5a1 1 0 001-1v-6" stroke="#D12626" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
              <path d="M28 14.5c1.66 1 2.8 2.8 2.8 4.86s-1.14 3.86-2.8 4.86" stroke="#D12626" stroke-width="2.2" stroke-linecap="round"/>
            </svg>
            <div class="item-chip-text">
              <div class="item-chip-title">Your Network</div>
              <ul class="item-chip-bullets">
                <li>Not public yet</li>
                <li>Personal only</li>
              </ul>
            </div>
          </div>
        </div>
        <div class="network-note">Not yet public — personal conversations only, not a broadcast. One connection could furnish a family's home.</div>
      </div>
    </div>

    <!-- ── SECTION: BOARD ACTIONS ── -->
    <div class="section-header">
      <div class="section-header-label">Board — Three Asks This Month</div>
      <div class="section-header-line"></div>
    </div>

    <div class="row row-3">
      <div class="action-card">
        <div class="action-num" style="background:var(--dkblue);">1</div>
        <div class="action-content">
          <strong>Network for Warehouse Items</strong>
          <span>Quietly source furniture, appliances, shelving, lighting. Personal conversations — not a broadcast.</span>
        </div>
      </div>
      <div class="action-card">
        <div class="action-num" style="background:var(--blue);">2</div>
        <div class="action-content">
          <strong>Share One Social Post</strong>
          <span>Follow us. Share one post this week. One share reaches networks we can't access.</span>
        </div>
      </div>
      <div class="action-card">
        <div class="action-num" style="background:var(--red);">3</div>
        <div class="action-content">
          <strong>Enroll a Child in DPIL</strong>
          <span>Know a family with a child under 5? Free books, birth to kindergarten. uwhmc.org.</span>
        </div>
      </div>
    </div>

  </div><!-- end .body -->

  <!-- ══ FOOTER ════════════════════════════════════════ -->
  <div class="footer">
    <div class="footer-org">United Way · Harvey &amp; Marion Counties · Newton, KS</div>
    <div class="footer-pillars">
      <span class="footer-pill" style="background:var(--blue);">Childcare</span>
      <span class="footer-pill" style="background:var(--red);">Housing</span>
      <span class="footer-pill" style="background:rgba(255,255,255,0.15);">Navigation</span>
      <span class="footer-pill" style="background:var(--green);">Food</span>
      <span class="footer-pill" style="background:#7C3AED;">DPIL</span>
    </div>
  </div>

</div><!-- end .page -->
</body>
</html>
