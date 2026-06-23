<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>TicketFlow</title>
<style>
  :root {
    --c1: #0f172a; --c2: #3b82f6; --c3: #f59e0b;
    --c1-light: #1e293b; --c1-mid: #334155;
    --text: #f1f5f9; --text-muted: #94a3b8; --border: #1e293b; --card: #1e293b;
    --success: #22c55e; --danger: #ef4444; --radius: 10px;
    --shadow: 0 4px 20px rgba(0,0,0,.35);
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: 'Segoe UI', system-ui, sans-serif; background: var(--c1); color: var(--text); min-height: 100vh; }

  /* LOADING OVERLAY */
  #app-loading {
    position: fixed; inset: 0; background: var(--c1); z-index: 999;
    display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 1rem;
  }
  #app-loading.done { display: none; }
  .spinner { width: 38px; height: 38px; border: 3px solid var(--c1-mid); border-top-color: var(--c2); border-radius: 50%; animation: spin .7s linear infinite; }
  @keyframes spin { to { transform: rotate(360deg); } }
  .loading-label { color: var(--text-muted); font-size: .9rem; }

  /* CONFIG BANNER */
  .config-banner {
    background: rgba(239,68,68,.08); border: 1px solid rgba(239,68,68,.3);
    border-radius: var(--radius); padding: .9rem 1.1rem; margin-bottom: 1.25rem;
    font-size: .87rem; color: #fca5a5; line-height: 1.6; display: none;
  }
  .config-banner.show { display: block; }
  .config-banner code { background: var(--c1-mid); padding: .1rem .45rem; border-radius: 4px; font-size: .82rem; font-family: 'Cascadia Code', monospace; }
  .config-banner a { color: var(--c2); }

  /* NAV */
  nav {
    background: var(--c1-light); border-bottom: 2px solid var(--c2);
    padding: 0 1.5rem; display: flex; align-items: center; justify-content: space-between;
    height: 58px; position: sticky; top: 0; z-index: 100; box-shadow: var(--shadow);
  }
  .nav-brand { font-size: 1.2rem; font-weight: 700; color: var(--c3); display: flex; align-items: center; gap: .4rem; }
  .nav-brand span { color: var(--c2); }
  .nav-mode-badge { font-size: .68rem; font-weight: 700; letter-spacing: .8px; text-transform: uppercase; padding: .18rem .55rem; border-radius: 99px; margin-left: .5rem; }
  .badge-public { background: rgba(34,197,94,.12); color: #4ade80; border: 1px solid rgba(34,197,94,.28); }
  .badge-staff  { background: rgba(245,158,11,.12); color: #fbbf24; border: 1px solid rgba(245,158,11,.28); }
  .nav-tabs { display: flex; gap: .25rem; }
  .nav-tab { padding: .42rem 1rem; border: none; background: transparent; color: var(--text-muted); cursor: pointer; border-radius: var(--radius); font-size: .88rem; font-weight: 500; transition: all .15s; }
  .nav-tab:hover { background: var(--c1-mid); color: var(--text); }
  .nav-tab.active { background: var(--c2); color: #fff; }
  .nav-actions { display: flex; gap: .5rem; align-items: center; }

  /* LAYOUT */
  .container { max-width: 1200px; margin: 0 auto; padding: 1.5rem; }
  .view { display: none; }
  .view.active { display: block; }

  /* BUTTONS */
  .btn { padding: .55rem 1.25rem; border: none; border-radius: var(--radius); font-size: .88rem; font-weight: 600; cursor: pointer; transition: opacity .15s, transform .12s; font-family: inherit; }
  .btn:hover { opacity: .88; transform: translateY(-1px); }
  .btn:active { transform: translateY(0); opacity: 1; }
  .btn:disabled { opacity: .45; cursor: not-allowed; transform: none; }
  .btn-primary { background: var(--c2); color: #fff; }
  .btn-amber   { background: var(--c3); color: #000; }
  .btn-ghost   { background: var(--c1-mid); color: var(--text); }
  .btn-danger  { background: var(--danger); color: #fff; }
  .btn-sm { padding: .28rem .72rem; font-size: .78rem; }
  .btn-lg { padding: .75rem 2rem; font-size: 1rem; }

  /* PANEL */
  .panel { background: var(--card); border-radius: var(--radius); padding: 1.25rem; box-shadow: var(--shadow); }
  .panel-title { font-size: .95rem; font-weight: 700; color: var(--c3); margin-bottom: 1rem; }

  /* FORMS */
  .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  @media (max-width: 520px) { .form-grid { grid-template-columns: 1fr; } }
  .form-group { display: flex; flex-direction: column; gap: .35rem; }
  .form-group.full { grid-column: 1 / -1; }
  label { font-size: .78rem; color: var(--text-muted); font-weight: 600; text-transform: uppercase; letter-spacing: .6px; }
  input[type="text"], input[type="email"], input[type="password"], textarea, select.form-sel {
    background: var(--c1); border: 1.5px solid var(--c1-mid); border-radius: 8px;
    padding: .6rem .9rem; color: var(--text); font-size: .9rem;
    outline: none; transition: border-color .18s; font-family: inherit;
  }
  input:focus, textarea:focus, select.form-sel:focus { border-color: var(--c2); }
  textarea { resize: vertical; min-height: 90px; }
  .form-actions { display: flex; gap: .75rem; justify-content: flex-end; margin-top: 1.25rem; }

  /* PORTAL */
  .portal-hero { text-align: center; padding: 2.5rem 1rem 2rem; }
  .portal-hero h1 { font-size: 1.85rem; font-weight: 800; margin-bottom: .5rem; }
  .portal-hero p  { color: var(--text-muted); font-size: 1rem; max-width: 480px; margin: 0 auto; }
  .portal-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; max-width: 900px; margin: 0 auto; }
  @media (max-width: 720px) { .portal-grid { grid-template-columns: 1fr; } }

  .success-card { background: var(--card); border-radius: 14px; padding: 2rem; text-align: center; border: 1px solid rgba(34,197,94,.22); box-shadow: var(--shadow); }
  .success-icon { font-size: 2.8rem; margin-bottom: .9rem; }
  .success-card h2 { font-size: 1.25rem; font-weight: 700; color: var(--success); margin-bottom: .4rem; }
  .success-card p  { color: var(--text-muted); font-size: .9rem; margin-bottom: 1rem; }
  .ticket-ref { background: var(--c1); border-radius: 8px; padding: .7rem 1.25rem; display: inline-block; font-size: 1.5rem; font-weight: 800; color: var(--c3); letter-spacing: 1.5px; margin-bottom: 1rem; }

  .tracker-result { background: var(--c1); border-radius: 10px; padding: 1.1rem 1.25rem; margin-top: 1rem; display: none; }
  .tracker-result.show { display: block; }
  .tracker-row { display: flex; justify-content: space-between; align-items: center; padding: .42rem 0; border-bottom: 1px solid var(--border); font-size: .87rem; }
  .tracker-row:last-child { border-bottom: none; }
  .tracker-key { color: var(--text-muted); }
  .tracker-comment { background: var(--c1-light); border-left: 3px solid var(--c2); padding: .5rem .8rem; border-radius: 0 6px 6px 0; font-size: .83rem; margin-bottom: .4rem; }
  .tracker-comment-meta { font-size: .7rem; color: var(--text-muted); margin-top: .2rem; }

  /* DASHBOARD */
  .stat-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(155px, 1fr)); gap: 1rem; margin-bottom: 1.5rem; }
  .stat-card { background: var(--card); border-radius: var(--radius); padding: 1.1rem 1.25rem; border-left: 4px solid var(--c2); box-shadow: var(--shadow); transition: transform .15s; }
  .stat-card:hover { transform: translateY(-2px); }
  .stat-card.amber { border-color: var(--c3); }
  .stat-card.green { border-color: var(--success); }
  .stat-card.red   { border-color: var(--danger); }
  .stat-label { font-size: .72rem; color: var(--text-muted); text-transform: uppercase; letter-spacing: 1px; margin-bottom: .3rem; }
  .stat-value { font-size: 2rem; font-weight: 800; }
  .stat-sub   { font-size: .72rem; color: var(--text-muted); margin-top: .2rem; }
  .dash-grid { display: grid; grid-template-columns: 2fr 1fr; gap: 1rem; }
  @media (max-width: 860px) { .dash-grid { grid-template-columns: 1fr; } }
  .bar-chart { display: flex; flex-direction: column; gap: .6rem; }
  .bar-row { display: flex; align-items: center; gap: .75rem; font-size: .82rem; }
  .bar-label { width: 72px; color: var(--text-muted); white-space: nowrap; }
  .bar-track { flex: 1; background: var(--c1); border-radius: 99px; height: 8px; overflow: hidden; }
  .bar-fill  { height: 100%; border-radius: 99px; transition: width .4s ease; }
  .bar-count { width: 26px; text-align: right; color: var(--text-muted); }
  .priority-list { display: flex; flex-direction: column; gap: .6rem; }
  .priority-row { display: flex; align-items: center; justify-content: space-between; font-size: .85rem; }
  .priority-dot { width: 10px; height: 10px; border-radius: 50%; display: inline-block; margin-right: .5rem; }
  .priority-name { display: flex; align-items: center; color: var(--text-muted); }
  .priority-badge { background: var(--c1); padding: .2rem .7rem; border-radius: 99px; font-weight: 700; font-size: .8rem; }
  .ticket-mini { display: flex; flex-direction: column; gap: .45rem; }
  .ticket-mini-row { display: flex; align-items: center; justify-content: space-between; padding: .5rem .7rem; background: var(--c1); border-radius: 7px; font-size: .83rem; cursor: pointer; transition: background .15s; gap: .5rem; }
  .ticket-mini-row:hover { background: var(--c1-mid); }
  .tmr-id { color: var(--c2); font-weight: 700; min-width: 60px; }
  .tmr-title { flex: 1; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; }
  .tmr-sub { min-width: 70px; text-align: right; font-size: .73rem; color: var(--text-muted); }

  /* TICKET TABLE */
  .toolbar { display: flex; gap: .75rem; margin-bottom: 1rem; flex-wrap: wrap; align-items: center; }
  .search-box { flex: 1; min-width: 200px; background: var(--c1-light); border: 1.5px solid var(--c1-mid); border-radius: var(--radius); padding: .55rem 1rem; color: var(--text); font-size: .9rem; outline: none; transition: border-color .18s; }
  .search-box:focus { border-color: var(--c2); }
  select.filter-sel { background: var(--c1-light); border: 1.5px solid var(--c1-mid); border-radius: var(--radius); padding: .55rem .9rem; color: var(--text); font-size: .85rem; outline: none; cursor: pointer; }
  select.filter-sel:focus { border-color: var(--c2); }
  .ticket-table-wrap { overflow-x: auto; }
  .ticket-table { width: 100%; border-collapse: collapse; font-size: .87rem; }
  .ticket-table th { text-align: left; padding: .6rem 1rem; color: var(--text-muted); font-size: .72rem; text-transform: uppercase; letter-spacing: .8px; border-bottom: 1.5px solid var(--c1-mid); cursor: pointer; white-space: nowrap; user-select: none; }
  .ticket-table th:hover { color: var(--c2); }
  .ticket-table td { padding: .7rem 1rem; border-bottom: 1px solid var(--border); vertical-align: middle; }
  .ticket-table tr:hover td { background: var(--c1-light); }
  .ticket-table tr:last-child td { border-bottom: none; }
  .tid-link { color: var(--c2); font-weight: 700; cursor: pointer; }
  .tid-link:hover { text-decoration: underline; }

  /* BADGES */
  .badge { display: inline-flex; align-items: center; padding: .18rem .6rem; border-radius: 99px; font-size: .72rem; font-weight: 700; letter-spacing: .3px; white-space: nowrap; }
  .badge-open       { background: rgba(59,130,246,.14); color: #60a5fa; border: 1px solid rgba(59,130,246,.28); }
  .badge-inprogress { background: rgba(245,158,11,.14); color: #fbbf24; border: 1px solid rgba(245,158,11,.28); }
  .badge-resolved   { background: rgba(34,197,94,.14);  color: #4ade80; border: 1px solid rgba(34,197,94,.28); }
  .badge-closed     { background: rgba(148,163,184,.1); color: #94a3b8; border: 1px solid rgba(148,163,184,.2); }
  .badge-critical   { background: rgba(239,68,68,.14);  color: #f87171; border: 1px solid rgba(239,68,68,.28); }
  .badge-high       { background: rgba(245,158,11,.14); color: #fbbf24; border: 1px solid rgba(245,158,11,.28); }
  .badge-medium     { background: rgba(59,130,246,.14); color: #60a5fa; border: 1px solid rgba(59,130,246,.28); }
  .badge-low        { background: rgba(148,163,184,.1); color: #94a3b8; border: 1px solid rgba(148,163,184,.2); }

  .empty-state { text-align: center; padding: 3rem 1rem; color: var(--text-muted); }
  .empty-state .big { font-size: 3rem; margin-bottom: .75rem; }

  /* MODAL */
  .modal-overlay { display: none; position: fixed; inset: 0; background: rgba(0,0,0,.65); z-index: 200; align-items: center; justify-content: center; padding: 1rem; }
  .modal-overlay.open { display: flex; }
  .modal { background: var(--c1-light); border-radius: 14px; padding: 1.75rem; width: 100%; max-width: 600px; max-height: 92vh; overflow-y: auto; box-shadow: 0 20px 60px rgba(0,0,0,.6); border: 1px solid var(--c1-mid); animation: slideUp .2s ease; }
  @keyframes slideUp { from { transform: translateY(28px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
  .modal-header { display: flex; align-items: center; justify-content: space-between; margin-bottom: 1.25rem; }
  .modal-title  { font-size: 1.1rem; font-weight: 700; color: var(--c3); }
  .modal-close  { background: var(--c1-mid); border: none; color: var(--text-muted); width: 30px; height: 30px; border-radius: 50%; cursor: pointer; font-size: 1rem; display: flex; align-items: center; justify-content: center; transition: background .15s; }
  .modal-close:hover { background: var(--danger); color: #fff; }

  .detail-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin-bottom: 1rem; }
  @media (max-width: 480px) { .detail-grid { grid-template-columns: 1fr; } }
  .detail-section { margin-bottom: 1rem; }
  .detail-label { font-size: .72rem; color: var(--text-muted); text-transform: uppercase; letter-spacing: .7px; margin-bottom: .3rem; }
  .divider { border: none; border-top: 1px solid var(--c1-mid); margin: 1rem 0; }
  .comment-list { display: flex; flex-direction: column; gap: .6rem; max-height: 200px; overflow-y: auto; margin-bottom: .75rem; }
  .comment-item { background: var(--c1); border-radius: 8px; padding: .6rem .85rem; font-size: .84rem; }
  .comment-meta { font-size: .7rem; color: var(--text-muted); margin-top: .2rem; }
  .comment-author { font-weight: 700; color: var(--c2); margin-right: .35rem; }
  .comment-input-row { display: flex; gap: .5rem; }
  .comment-input-row input { flex: 1; }

  .login-box { background: var(--c1-light); border-radius: 14px; padding: 2rem; width: 100%; max-width: 360px; box-shadow: 0 20px 60px rgba(0,0,0,.6); border: 1px solid var(--c1-mid); animation: slideUp .2s ease; }
  .login-box h2 { font-size: 1.1rem; font-weight: 700; color: var(--c3); margin-bottom: .3rem; }
  .login-box p  { font-size: .85rem; color: var(--text-muted); margin-bottom: 1.1rem; }

  #toast-container { position: fixed; bottom: 1.5rem; right: 1.5rem; z-index: 999; display: flex; flex-direction: column; gap: .5rem; }
  .toast { background: var(--c1-light); border: 1px solid var(--c1-mid); border-left: 4px solid var(--c2); padding: .7rem 1rem; border-radius: 8px; font-size: .87rem; box-shadow: var(--shadow); animation: fadeInRight .22s ease; min-width: 200px; max-width: 300px; }
  .toast.success { border-left-color: var(--success); }
  .toast.error   { border-left-color: var(--danger); }
  .toast.warning { border-left-color: var(--c3); }
  @keyframes fadeInRight { from { transform: translateX(28px); opacity: 0; } to { transform: translateX(0); opacity: 1; } }

  ::-webkit-scrollbar { width: 6px; height: 6px; }
  ::-webkit-scrollbar-track { background: var(--c1); }
  ::-webkit-scrollbar-thumb { background: var(--c1-mid); border-radius: 3px; }

  @media (max-width: 640px) {
    nav { padding: 0 .75rem; }
    .nav-brand { font-size: 1rem; }
    .nav-tab { padding: .38rem .65rem; font-size: .82rem; }
    .container { padding: 1rem .75rem; }
    .stat-grid { grid-template-columns: repeat(2, 1fr); }
    .ticket-table th:nth-child(6), .ticket-table td:nth-child(6),
    .ticket-table th:nth-child(7), .ticket-table td:nth-child(7) { display: none; }
  }
</style>
</head>
<body>

<!-- LOADING SCREEN -->
<div id="app-loading">
  <div class="spinner"></div>
  <div class="loading-label">Connecting to database…</div>
</div>

<!-- NAV -->
<nav>
  <div class="nav-brand">&#9670; Ticket<span>Flow</span>
    <span id="mode-badge" class="nav-mode-badge badge-public">Public</span>
  </div>
  <div class="nav-tabs" id="nav-tabs"></div>
  <div class="nav-actions" id="nav-actions"></div>
</nav>

<div class="container">

  <!-- CONFIG WARNING -->
  <div class="config-banner" id="config-banner">
    &#9888;&nbsp; <strong>Firebase not configured.</strong>
    Replace the placeholder values in <code>FIREBASE_CONFIG</code> at the top of the &lt;script&gt;.
    See the <a href="https://console.firebase.google.com/" target="_blank">Firebase Console</a> → Project Settings → Your apps → SDK setup.
    Also set your Firestore rules to allow read/write (test mode is fine to start).
  </div>

  <!-- ── SUBMITTER VIEWS ── -->
  <div id="view-submit" class="view">
    <div class="portal-hero">
      <h1>Submit a Support Ticket</h1>
      <p>Fill in the form and we'll get back to you as soon as possible.</p>
    </div>
    <div class="portal-grid">

      <!-- FORM -->
      <div>
        <div id="submit-form-panel" class="panel">
          <div class="panel-title">&#9670; New Ticket</div>
          <div class="form-grid">
            <div class="form-group">
              <label>Your Name *</label>
              <input type="text" id="s-name" placeholder="Full name…" />
            </div>
            <div class="form-group">
              <label>Email Address *</label>
              <input type="email" id="s-email" placeholder="you@example.com" />
            </div>
            <div class="form-group full">
              <label>Subject *</label>
              <input type="text" id="s-title" placeholder="Brief description of the issue…" />
            </div>
            <div class="form-group full">
              <label>Description</label>
              <textarea id="s-desc" placeholder="Provide as much detail as possible…"></textarea>
            </div>
            <div class="form-group">
              <label>Category</label>
              <select class="form-sel" id="s-category">
                <option>Bug</option><option>Feature</option><option>Support</option><option>Other</option>
              </select>
            </div>
            <div class="form-group">
              <label>Priority</label>
              <select class="form-sel" id="s-priority">
                <option>Low</option><option selected>Medium</option><option>High</option><option>Critical</option>
              </select>
            </div>
          </div>
          <div class="form-actions" style="margin-top:1.25rem">
            <button class="btn btn-primary btn-lg" id="submit-btn" onclick="submitTicket()">Submit Ticket &rarr;</button>
          </div>
        </div>

        <div id="submit-success-panel" class="success-card" style="display:none">
          <div class="success-icon">&#10003;</div>
          <h2>Ticket Submitted!</h2>
          <p>Your ticket reference number is:</p>
          <div class="ticket-ref" id="new-ticket-ref"></div>
          <p style="margin-bottom:1.5rem">Save this number and use it with your email to track your ticket status.</p>
          <button class="btn btn-ghost" onclick="resetSubmitForm()">Submit Another Ticket</button>
        </div>
      </div>

      <!-- TRACKER -->
      <div class="panel">
        <div class="panel-title">&#128269; Track Your Ticket</div>
        <p style="font-size:.85rem;color:var(--text-muted);margin-bottom:1rem">Enter your ticket number and the email you used when submitting.</p>
        <div class="form-group" style="margin-bottom:.75rem">
          <label>Ticket Number</label>
          <input type="text" id="t-id" placeholder="e.g. TF-101" />
        </div>
        <div class="form-group" style="margin-bottom:.75rem">
          <label>Your Email</label>
          <input type="email" id="t-email" placeholder="you@example.com" />
        </div>
        <button class="btn btn-amber" onclick="trackTicket()" id="track-btn" style="width:100%">Track Status</button>
        <div class="tracker-result" id="tracker-result"></div>
      </div>

    </div>
  </div>

  <!-- ── STAFF: DASHBOARD ── -->
  <div id="view-dashboard" class="view">
    <div class="stat-grid" id="stat-grid"></div>
    <div class="dash-grid">
      <div>
        <div class="panel" style="margin-bottom:1rem">
          <div class="panel-title">&#9632; Tickets by Status</div>
          <div class="bar-chart" id="bar-status"></div>
        </div>
        <div class="panel">
          <div class="panel-title">&#9650; Recent Activity</div>
          <div class="ticket-mini" id="recent-tickets"></div>
        </div>
      </div>
      <div>
        <div class="panel" style="margin-bottom:1rem">
          <div class="panel-title">&#9670; Priority Breakdown</div>
          <div class="priority-list" id="priority-list"></div>
        </div>
        <div class="panel">
          <div class="panel-title">&#9632; Category Mix</div>
          <div class="bar-chart" id="bar-category"></div>
        </div>
      </div>
    </div>
  </div>

  <!-- ── STAFF: TICKET LIST ── -->
  <div id="view-tickets" class="view">
    <div class="toolbar">
      <input class="search-box" type="text" id="search-input" placeholder="Search tickets…" oninput="renderTickets()" />
      <select class="filter-sel" id="filter-status" onchange="renderTickets()">
        <option value="">All Status</option>
        <option>Open</option><option>In Progress</option><option>Resolved</option><option>Closed</option>
      </select>
      <select class="filter-sel" id="filter-priority" onchange="renderTickets()">
        <option value="">All Priority</option>
        <option>Critical</option><option>High</option><option>Medium</option><option>Low</option>
      </select>
      <select class="filter-sel" id="filter-category" onchange="renderTickets()">
        <option value="">All Category</option>
        <option>Bug</option><option>Feature</option><option>Support</option><option>Other</option>
      </select>
    </div>
    <div class="panel ticket-table-wrap">
      <table class="ticket-table">
        <thead><tr>
          <th onclick="sortBy('numId')">#ID &#8597;</th>
          <th onclick="sortBy('title')">Subject &#8597;</th>
          <th onclick="sortBy('submitterName')">Submitted By &#8597;</th>
          <th onclick="sortBy('status')">Status &#8597;</th>
          <th onclick="sortBy('priority')">Priority &#8597;</th>
          <th onclick="sortBy('category')">Category &#8597;</th>
          <th onclick="sortBy('created')">Created &#8597;</th>
          <th>Actions</th>
        </tr></thead>
        <tbody id="ticket-tbody"></tbody>
      </table>
      <div id="empty-tickets" class="empty-state" style="display:none">
        <div class="big">&#128203;</div>No tickets match your filters.
      </div>
    </div>
  </div>

</div><!-- /container -->

<!-- STAFF LOGIN -->
<div class="modal-overlay" id="modal-login">
  <div class="login-box">
    <h2>&#128274; Staff Access</h2>
    <p>Enter the staff password to access the dashboard and ticket management.</p>
    <div class="form-group" style="margin-bottom:1rem">
      <label>Password</label>
      <input type="password" id="login-pw" placeholder="Staff password…" onkeydown="if(event.key==='Enter')doLogin()" />
    </div>
    <div style="display:flex;gap:.75rem;justify-content:flex-end">
      <button class="btn btn-ghost" onclick="closeModal('modal-login')">Cancel</button>
      <button class="btn btn-primary" onclick="doLogin()">Login</button>
    </div>
  </div>
</div>

<!-- EDIT TICKET -->
<div class="modal-overlay" id="modal-ticket">
  <div class="modal">
    <div class="modal-header">
      <div class="modal-title" id="modal-ticket-title">Edit Ticket</div>
      <button class="modal-close" onclick="closeModal('modal-ticket')">&#10005;</button>
    </div>
    <div class="form-grid">
      <div class="form-group full"><label>Subject</label><input type="text" id="f-title" /></div>
      <div class="form-group full"><label>Description</label><textarea id="f-desc"></textarea></div>
      <div class="form-group">
        <label>Status</label>
        <select class="form-sel" id="f-status">
          <option>Open</option><option>In Progress</option><option>Resolved</option><option>Closed</option>
        </select>
      </div>
      <div class="form-group">
        <label>Priority</label>
        <select class="form-sel" id="f-priority">
          <option>Low</option><option>Medium</option><option>High</option><option>Critical</option>
        </select>
      </div>
      <div class="form-group">
        <label>Category</label>
        <select class="form-sel" id="f-category">
          <option>Bug</option><option>Feature</option><option>Support</option><option>Other</option>
        </select>
      </div>
      <div class="form-group">
        <label>Assignee (Staff)</label>
        <input type="text" id="f-assignee" placeholder="Staff member name…" />
      </div>
    </div>
    <div class="form-actions">
      <button class="btn btn-ghost" onclick="closeModal('modal-ticket')">Cancel</button>
      <button class="btn btn-primary" id="save-edit-btn" onclick="saveTicketEdit()">Save Changes</button>
    </div>
  </div>
</div>

<!-- DETAIL -->
<div class="modal-overlay" id="modal-detail">
  <div class="modal" style="max-width:660px">
    <div class="modal-header">
      <div class="modal-title" id="detail-header"></div>
      <button class="modal-close" onclick="closeModal('modal-detail')">&#10005;</button>
    </div>
    <div id="detail-body"></div>
  </div>
</div>

<div id="toast-container"></div>

<!-- ══════════════════════════════════════════════════════════
     FIREBASE SDKs  (compat v10 — same v8-style API)
     ══════════════════════════════════════════════════════════ -->
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore-compat.js"></script>

<script>
// ╔══════════════════════════════════════════════════════╗
// ║  STEP 1 — Paste your Firebase config values here    ║
// ║  Firebase Console → Project Settings → Your apps   ║
// ╚══════════════════════════════════════════════════════╝
const FIREBASE_CONFIG = {
  apiKey:            "AIzaSyC3OMTCS3NP7Zn8f-mjZ3IXZ5gClRjN7rA",
  authDomain:        "worktickets2026.firebaseapp.com",
  projectId:         "worktickets2026",
  storageBucket:     "worktickets2026.firebasestorage.app",
  messagingSenderId: "777068839485",
  appId:             "1:777068839485:web:e0046cf678c864a3a5e054"
};

// ╔══════════════════════════════════════════════════════╗
// ║  STEP 2 — Change the staff password                 ║
// ╚══════════════════════════════════════════════════════╝
const STAFF_PASS = 'admin';

// ─── FIREBASE INIT ───────────────────────────────────────
const isConfigured = !Object.values(FIREBASE_CONFIG).some(v => v.startsWith('YOUR_'));
let db, ticketsCol, metaDoc;

if (isConfigured) {
  firebase.initializeApp(FIREBASE_CONFIG);
  db         = firebase.firestore();
  ticketsCol = db.collection('tickets');
  metaDoc    = db.collection('meta').doc('counter');
}

// ─── APP STATE ───────────────────────────────────────────
let isStaff       = false;
let editingDocId  = null;   // Firestore document ID of ticket being edited
let cachedTickets = [];     // latest snapshot (used for render + detail lookup)
let staffListener = null;   // onSnapshot unsubscribe fn
let sortCol = 'numId', sortDir = 'desc';

// ─── INIT ────────────────────────────────────────────────
async function initApp() {
  if (!isConfigured) {
    document.getElementById('config-banner').classList.add('show');
    document.getElementById('app-loading').classList.add('done');
    buildNav(); showView('submit');
    return;
  }
  try {
    // Seed sample data only on first ever load (counter doc absent)
    const snap = await metaDoc.get();
    if (!snap.exists) await seedSampleData();
  } catch (e) {
    console.error('Firestore error:', e);
    document.getElementById('config-banner').classList.add('show');
  }
  document.getElementById('app-loading').classList.add('done');
  buildNav();
  showView('submit');
}

async function seedSampleData() {
  const now = new Date();
  const d   = n => new Date(now - n * 86400000).toISOString();
  const samples = [
    { numId:104, title:'Login page crashes on mobile', desc:'iOS 17 shows white screen after entering credentials.', status:'Open', priority:'Critical', category:'Bug', assignee:'Alice', submitterName:'John Smith', submitterEmail:'john@example.com', created:d(5), updated:d(2), comments:[{text:'Reproduced on iPhone 14 Pro.',author:'Staff',ts:d(3)}] },
    { numId:103, title:'Add dark mode toggle', desc:'Many users have requested a system-level dark/light switch.', status:'In Progress', priority:'Medium', category:'Feature', assignee:'Bob', submitterName:'Sarah Lee', submitterEmail:'sarah@example.com', created:d(10), updated:d(1), comments:[] },
    { numId:102, title:'CSV export hangs on large datasets', desc:'Export times out for files over 10 000 rows.', status:'Open', priority:'High', category:'Bug', assignee:'', submitterName:'Mark Davis', submitterEmail:'mark@example.com', created:d(3), updated:d(3), comments:[] },
    { numId:101, title:'Update onboarding documentation', desc:'Current docs still reference the old UI flow.', status:'Resolved', priority:'Low', category:'Support', assignee:'Carol', submitterName:'Amy Chen', submitterEmail:'amy@example.com', created:d(20), updated:d(7), comments:[{text:'Docs updated and live.',author:'Staff',ts:d(7)}] },
  ];
  const batch = db.batch();
  samples.forEach(t => batch.set(ticketsCol.doc(), t));
  batch.set(metaDoc, { nextId: 105 });
  await batch.commit();
}

// ─── NAV ─────────────────────────────────────────────────
function buildNav() {
  const badge = document.getElementById('mode-badge');
  const tabs  = document.getElementById('nav-tabs');
  const acts  = document.getElementById('nav-actions');
  if (isStaff) {
    badge.textContent = 'Staff'; badge.className = 'nav-mode-badge badge-staff';
    tabs.innerHTML = `
      <button class="nav-tab" onclick="showView('dashboard')">Dashboard</button>
      <button class="nav-tab" onclick="showView('tickets')">Tickets</button>`;
    acts.innerHTML = `<button class="btn btn-ghost btn-sm" onclick="staffLogout()">Logout</button>`;
  } else {
    badge.textContent = 'Public'; badge.className = 'nav-mode-badge badge-public';
    tabs.innerHTML = `<button class="nav-tab active" onclick="showView('submit')">Submit a Ticket</button>`;
    acts.innerHTML = `<button class="btn btn-ghost btn-sm" onclick="openModal('modal-login')">Staff Login</button>`;
  }
}

function showView(name) {
  document.querySelectorAll('.view').forEach(v => v.classList.remove('active'));
  document.querySelectorAll('.nav-tab').forEach(t => t.classList.remove('active'));
  const v = document.getElementById('view-' + name);
  if (v) v.classList.add('active');
  document.querySelectorAll('.nav-tab').forEach(t => {
    if (t.textContent.toLowerCase().includes(name === 'submit' ? 'submit' : name))
      t.classList.add('active');
  });
  if ((name === 'dashboard' || name === 'tickets') && isStaff) startStaffListener();
}

// ─── STAFF LISTENER ──────────────────────────────────────
function startStaffListener() {
  if (staffListener || !isConfigured) return;
  staffListener = ticketsCol.orderBy('numId', 'desc').onSnapshot(snap => {
    cachedTickets = snap.docs.map(d => ({ _docId: d.id, ...d.data() }));
    if (document.getElementById('view-dashboard').classList.contains('active')) renderDashboard();
    if (document.getElementById('view-tickets').classList.contains('active'))   renderTickets();
  }, err => console.error('Snapshot error:', err));
}

function stopStaffListener() {
  if (staffListener) { staffListener(); staffListener = null; }
}

// ─── AUTH ─────────────────────────────────────────────────
function doLogin() {
  const pw = document.getElementById('login-pw').value;
  if (pw === STAFF_PASS) {
    isStaff = true;
    document.getElementById('login-pw').value = '';
    closeModal('modal-login');
    buildNav();
    showView('dashboard');
    toast('Welcome back, staff!', 'success');
  } else {
    toast('Incorrect password.', 'error');
    document.getElementById('login-pw').value = '';
    document.getElementById('login-pw').focus();
  }
}
function staffLogout() {
  isStaff = false;
  stopStaffListener();
  buildNav();
  showView('submit');
  toast('Logged out.', 'warning');
}

// ─── SUBMITTER: SUBMIT ───────────────────────────────────
async function submitTicket() {
  if (!isConfigured) { toast('Firebase not configured yet.', 'error'); return; }
  const name  = document.getElementById('s-name').value.trim();
  const email = document.getElementById('s-email').value.trim().toLowerCase();
  const title = document.getElementById('s-title').value.trim();
  if (!name)               { toast('Please enter your name.', 'error');  return; }
  if (!email.includes('@')){ toast('Please enter a valid email.', 'error'); return; }
  if (!title)              { toast('Please enter a subject.', 'error'); return; }

  const btn = document.getElementById('submit-btn');
  btn.disabled = true; btn.textContent = 'Submitting…';

  try {
    // Atomic counter increment
    const numId = await db.runTransaction(async tx => {
      const snap = await tx.get(metaDoc);
      const next = (snap.exists ? snap.data().nextId : 100) + 1;
      tx.set(metaDoc, { nextId: next });
      return next;
    });

    const now = new Date().toISOString();
    await ticketsCol.add({
      numId,
      title,
      desc:           document.getElementById('s-desc').value.trim(),
      status:         'Open',
      priority:       document.getElementById('s-priority').value,
      category:       document.getElementById('s-category').value,
      assignee:       '',
      submitterName:  name,
      submitterEmail: email,
      created: now,
      updated: now,
      comments: [],
    });

    document.getElementById('new-ticket-ref').textContent = 'TF-' + numId;
    document.getElementById('submit-form-panel').style.display  = 'none';
    document.getElementById('submit-success-panel').style.display = '';
    toast('Ticket submitted!', 'success');
  } catch (e) {
    console.error(e);
    toast('Error submitting ticket. Check your connection.', 'error');
  } finally {
    btn.disabled = false; btn.textContent = 'Submit Ticket →';
  }
}

function resetSubmitForm() {
  ['s-name','s-email','s-title','s-desc'].forEach(id => document.getElementById(id).value = '');
  document.getElementById('s-priority').value = 'Medium';
  document.getElementById('s-category').value = 'Bug';
  document.getElementById('submit-form-panel').style.display  = '';
  document.getElementById('submit-success-panel').style.display = 'none';
}

// ─── SUBMITTER: TRACK ────────────────────────────────────
async function trackTicket() {
  if (!isConfigured) { toast('Firebase not configured yet.', 'error'); return; }
  const rawId = document.getElementById('t-id').value.trim().replace(/^TF-/i, '');
  const email = document.getElementById('t-email').value.trim().toLowerCase();
  const res   = document.getElementById('tracker-result');

  if (!rawId || !email) { toast('Enter both ticket number and email.', 'error'); return; }
  const numId = parseInt(rawId, 10);
  if (isNaN(numId))    { toast('Invalid ticket number.', 'error'); return; }

  const btn = document.getElementById('track-btn');
  btn.disabled = true; btn.textContent = 'Searching…';
  res.className = 'tracker-result';

  try {
    const snap = await ticketsCol.where('numId', '==', numId).limit(1).get();
    if (snap.empty || snap.docs[0].data().submitterEmail !== email) {
      res.className = 'tracker-result show';
      res.innerHTML = `<div style="color:var(--danger);font-size:.88rem">&#10005; No ticket found with that number and email. Please check your details.</div>`;
      return;
    }

    const t = snap.docs[0].data();
    const staffComments = (t.comments || []).filter(c => c.author === 'Staff');
    const commentsHtml  = staffComments.length
      ? staffComments.map(c => `<div class="tracker-comment">${esc(c.text)}<div class="tracker-comment-meta">${fmtDateTime(c.ts)}</div></div>`).join('')
      : `<div style="color:var(--text-muted);font-size:.82rem">No staff updates yet.</div>`;

    res.className = 'tracker-result show';
    res.innerHTML = `
      <div style="font-size:.78rem;color:var(--c3);font-weight:700;margin-bottom:.6rem;text-transform:uppercase;letter-spacing:.8px">TF-${t.numId} &mdash; ${esc(t.title)}</div>
      <div class="tracker-row"><span class="tracker-key">Status</span>${statusBadge(t.status)}</div>
      <div class="tracker-row"><span class="tracker-key">Priority</span>${priorityBadge(t.priority)}</div>
      <div class="tracker-row"><span class="tracker-key">Category</span><span>${t.category}</span></div>
      ${t.assignee ? `<div class="tracker-row"><span class="tracker-key">Assigned To</span><span>${esc(t.assignee)}</span></div>` : ''}
      <div class="tracker-row"><span class="tracker-key">Submitted</span><span style="color:var(--text-muted)">${fmtDate(t.created)}</span></div>
      <div class="tracker-row"><span class="tracker-key">Last Updated</span><span style="color:var(--text-muted)">${fmtDate(t.updated)}</span></div>
      <div style="margin-top:.9rem">
        <div style="font-size:.73rem;color:var(--text-muted);text-transform:uppercase;letter-spacing:.7px;margin-bottom:.5rem">Staff Updates</div>
        ${commentsHtml}
      </div>`;
  } catch (e) {
    console.error(e);
    toast('Error fetching ticket. Check your connection.', 'error');
  } finally {
    btn.disabled = false; btn.textContent = 'Track Status';
  }
}

// ─── DASHBOARD RENDER ────────────────────────────────────
function renderDashboard() {
  const T = cachedTickets;
  const n = fn => T.filter(fn).length;

  document.getElementById('stat-grid').innerHTML = [
    { label:'Total',       value: T.length,                                    sub:'all tickets',    cls:'' },
    { label:'Open',        value: n(t => t.status==='Open'),                   sub:'awaiting action',cls:'' },
    { label:'In Progress', value: n(t => t.status==='In Progress'),            sub:'being handled',  cls:'amber' },
    { label:'Resolved',    value: n(t => t.status==='Resolved'),               sub:'completed',      cls:'green' },
    { label:'Critical',    value: n(t => t.priority==='Critical'),             sub:'urgent',         cls:'red' },
    { label:'Unassigned',  value: n(t => !t.assignee && t.status==='Open'),    sub:'need owner',     cls:'amber' },
  ].map(s=>`<div class="stat-card ${s.cls}">
    <div class="stat-label">${s.label}</div>
    <div class="stat-value">${s.value}</div>
    <div class="stat-sub">${s.sub}</div></div>`).join('');

  const sColors = {Open:'#3b82f6','In Progress':'#f59e0b',Resolved:'#22c55e',Closed:'#64748b'};
  const statuses = ['Open','In Progress','Resolved','Closed'];
  const maxS = Math.max(...statuses.map(s=>n(t=>t.status===s)), 1);
  document.getElementById('bar-status').innerHTML = statuses.map(s=>{
    const c=n(t=>t.status===s);
    return `<div class="bar-row"><div class="bar-label">${s}</div>
      <div class="bar-track"><div class="bar-fill" style="width:${(c/maxS)*100}%;background:${sColors[s]}"></div></div>
      <div class="bar-count">${c}</div></div>`;
  }).join('');

  document.getElementById('priority-list').innerHTML = [
    {name:'Critical',color:'#ef4444'},{name:'High',color:'#f59e0b'},
    {name:'Medium',color:'#3b82f6'},{name:'Low',color:'#64748b'},
  ].map(p=>`<div class="priority-row">
    <div class="priority-name"><span class="priority-dot" style="background:${p.color}"></span>${p.name}</div>
    <div class="priority-badge">${n(t=>t.priority===p.name)}</div></div>`).join('');

  const cColors = {Bug:'#ef4444',Feature:'#3b82f6',Support:'#f59e0b',Other:'#64748b'};
  const cats    = ['Bug','Feature','Support','Other'];
  const maxC = Math.max(...cats.map(c=>n(t=>t.category===c)), 1);
  document.getElementById('bar-category').innerHTML = cats.map(c=>{
    const k=n(t=>t.category===c);
    return `<div class="bar-row"><div class="bar-label">${c}</div>
      <div class="bar-track"><div class="bar-fill" style="width:${(k/maxC)*100}%;background:${cColors[c]}"></div></div>
      <div class="bar-count">${k}</div></div>`;
  }).join('');

  const recent = [...T].sort((a,b)=>new Date(b.updated)-new Date(a.updated)).slice(0,6);
  document.getElementById('recent-tickets').innerHTML = recent.length
    ? recent.map(t=>`<div class="ticket-mini-row" onclick="openDetail('${t._docId}')">
        <span class="tmr-id">TF-${t.numId}</span>
        <span class="tmr-title">${esc(t.title)}</span>
        <span class="tmr-sub">${esc(t.submitterName||'')}</span>
        <span>${statusBadge(t.status)}</span></div>`).join('')
    : '<div style="color:var(--text-muted);font-size:.85rem">No tickets yet.</div>';
}

// ─── TICKET TABLE RENDER ─────────────────────────────────
function renderTickets() {
  const q    = (document.getElementById('search-input')||{value:''}).value.toLowerCase();
  const fSt  = (document.getElementById('filter-status')||{value:''}).value;
  const fPr  = (document.getElementById('filter-priority')||{value:''}).value;
  const fCat = (document.getElementById('filter-category')||{value:''}).value;

  let rows = cachedTickets.filter(t => {
    if (fSt  && t.status   !== fSt)  return false;
    if (fPr  && t.priority !== fPr)  return false;
    if (fCat && t.category !== fCat) return false;
    if (q && ![String(t.numId), t.title, t.desc||'', t.submitterName||'', t.submitterEmail||'', t.assignee||'']
      .some(s => s.toLowerCase().includes(q))) return false;
    return true;
  });

  rows.sort((a,b) => {
    let av = a[sortCol], bv = b[sortCol];
    if (sortCol === 'numId') { av = +av; bv = +bv; }
    if (av < bv) return sortDir === 'asc' ? -1 : 1;
    if (av > bv) return sortDir === 'asc' ?  1 : -1;
    return 0;
  });

  const tbody = document.getElementById('ticket-tbody');
  const empty = document.getElementById('empty-tickets');
  if (!rows.length) { tbody.innerHTML = ''; empty.style.display = ''; return; }
  empty.style.display = 'none';
  tbody.innerHTML = rows.map(t => `<tr>
    <td><span class="tid-link" onclick="openDetail('${t._docId}')">TF-${t.numId}</span></td>
    <td style="max-width:210px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap">${esc(t.title)}</td>
    <td>
      <div style="font-size:.85rem">${esc(t.submitterName||'—')}</div>
      <div style="font-size:.73rem;color:var(--text-muted)">${esc(t.submitterEmail||'')}</div>
    </td>
    <td>${statusBadge(t.status)}</td>
    <td>${priorityBadge(t.priority)}</td>
    <td style="color:var(--text-muted)">${t.category}</td>
    <td style="color:var(--text-muted);white-space:nowrap">${fmtDate(t.created)}</td>
    <td style="white-space:nowrap">
      <button class="btn btn-ghost btn-sm" style="margin-right:.3rem" onclick="openEdit('${t._docId}')">Edit</button>
      <button class="btn btn-danger btn-sm" onclick="deleteTicket('${t._docId}',${t.numId})">Del</button>
    </td></tr>`).join('');
}

function sortBy(col) {
  sortDir = sortCol === col ? (sortDir === 'asc' ? 'desc' : 'asc') : 'asc';
  sortCol = col;
  renderTickets();
}

// ─── STAFF: EDIT ─────────────────────────────────────────
function openEdit(docId) {
  const t = cachedTickets.find(x => x._docId === docId);
  if (!t) return;
  editingDocId = docId;
  document.getElementById('modal-ticket-title').textContent = `Edit Ticket TF-${t.numId}`;
  document.getElementById('f-title').value    = t.title;
  document.getElementById('f-desc').value     = t.desc || '';
  document.getElementById('f-status').value   = t.status;
  document.getElementById('f-priority').value = t.priority;
  document.getElementById('f-category').value = t.category;
  document.getElementById('f-assignee').value = t.assignee || '';
  openModal('modal-ticket');
}

async function saveTicketEdit() {
  const title = document.getElementById('f-title').value.trim();
  if (!title) { toast('Subject is required.', 'error'); return; }
  const btn = document.getElementById('save-edit-btn');
  btn.disabled = true; btn.textContent = 'Saving…';
  try {
    await ticketsCol.doc(editingDocId).update({
      title,
      desc:     document.getElementById('f-desc').value.trim(),
      status:   document.getElementById('f-status').value,
      priority: document.getElementById('f-priority').value,
      category: document.getElementById('f-category').value,
      assignee: document.getElementById('f-assignee').value.trim(),
      updated:  new Date().toISOString(),
    });
    closeModal('modal-ticket');
    toast('Ticket updated.', 'success');
  } catch (e) {
    console.error(e); toast('Error saving changes.', 'error');
  } finally {
    btn.disabled = false; btn.textContent = 'Save Changes';
  }
}

async function deleteTicket(docId, numId) {
  if (!confirm(`Delete ticket TF-${numId}? This cannot be undone.`)) return;
  try {
    await ticketsCol.doc(docId).delete();
    toast(`TF-${numId} deleted.`, 'warning');
  } catch (e) {
    console.error(e); toast('Error deleting ticket.', 'error');
  }
}

// ─── DETAIL MODAL ────────────────────────────────────────
function openDetail(docId) {
  const t = cachedTickets.find(x => x._docId === docId);
  if (!t) return;
  document.getElementById('detail-header').textContent = `TF-${t.numId} — ${t.title}`;

  const comments    = t.comments || [];
  const commentsHtml = comments.length
    ? comments.map(c => `<div class="comment-item">
        <span class="comment-author">${esc(c.author||'Staff')}</span>${esc(c.text)}
        <div class="comment-meta">${fmtDateTime(c.ts)}</div></div>`).join('')
    : '<div style="color:var(--text-muted);font-size:.82rem">No comments yet.</div>';

  document.getElementById('detail-body').innerHTML = `
    <div class="detail-grid">
      <div class="detail-section">
        <div class="detail-label">Submitted By</div>
        <div>${esc(t.submitterName||'—')}</div>
        <div style="font-size:.8rem;color:var(--text-muted)">${esc(t.submitterEmail||'')}</div>
      </div>
      <div class="detail-section">
        <div class="detail-label">Assigned To</div>
        <div>${esc(t.assignee||'Unassigned')}</div>
      </div>
      <div class="detail-section"><div class="detail-label">Status</div>${statusBadge(t.status)}</div>
      <div class="detail-section"><div class="detail-label">Priority</div>${priorityBadge(t.priority)}</div>
      <div class="detail-section"><div class="detail-label">Category</div><div>${t.category}</div></div>
      <div class="detail-section"><div class="detail-label">Created</div>
        <div style="color:var(--text-muted)">${fmtDateTime(t.created)}</div></div>
    </div>
    ${t.desc ? `<div class="detail-section"><div class="detail-label">Description</div>
      <div style="line-height:1.65;font-size:.9rem;margin-top:.3rem">${esc(t.desc)}</div></div>` : ''}
    <hr class="divider"/>
    <div>
      <div class="detail-label" style="margin-bottom:.65rem">Staff Comments (${comments.length}) — visible to submitter via tracker</div>
      <div class="comment-list" id="comment-list-${docId}">${commentsHtml}</div>
      <div class="comment-input-row">
        <input type="text" id="comment-input-${docId}" placeholder="Add a staff comment…"
          onkeydown="if(event.key==='Enter')addComment('${docId}')" />
        <button class="btn btn-primary btn-sm" onclick="addComment('${docId}')">Post</button>
      </div>
    </div>
    <div class="form-actions">
      <button class="btn btn-ghost" onclick="closeModal('modal-detail')">Close</button>
      <button class="btn btn-primary" onclick="closeModal('modal-detail');openEdit('${docId}')">Edit Ticket</button>
    </div>`;
  openModal('modal-detail');
}

async function addComment(docId) {
  const input = document.getElementById(`comment-input-${docId}`);
  const text  = input.value.trim();
  if (!text) return;
  const now = new Date().toISOString();
  const c   = { text, author: 'Staff', ts: now };
  try {
    await ticketsCol.doc(docId).update({
      comments: firebase.firestore.FieldValue.arrayUnion(c),
      updated:  now,
    });
    input.value = '';
    // Optimistically append (snapshot will also update it)
    const list = document.getElementById(`comment-list-${docId}`);
    if (list) {
      const empty = list.querySelector('[style*="color:var(--text-muted)"]');
      if (empty) list.innerHTML = '';
      list.innerHTML += `<div class="comment-item"><span class="comment-author">Staff</span>${esc(c.text)}<div class="comment-meta">${fmtDateTime(c.ts)}</div></div>`;
      list.scrollTop = list.scrollHeight;
    }
    toast('Comment posted.', 'success');
  } catch (e) {
    console.error(e); toast('Error posting comment.', 'error');
  }
}

// ─── MODAL HELPERS ───────────────────────────────────────
function openModal(id)  { document.getElementById(id).classList.add('open'); }
function closeModal(id) { document.getElementById(id).classList.remove('open'); }
document.querySelectorAll('.modal-overlay').forEach(o =>
  o.addEventListener('click', e => { if (e.target === o) o.classList.remove('open'); })
);

// ─── BADGES ──────────────────────────────────────────────
function statusBadge(s) {
  const m={Open:'badge-open','In Progress':'badge-inprogress',Resolved:'badge-resolved',Closed:'badge-closed'};
  return `<span class="badge ${m[s]||'badge-open'}">${s}</span>`;
}
function priorityBadge(p) {
  const m={Critical:'badge-critical',High:'badge-high',Medium:'badge-medium',Low:'badge-low'};
  return `<span class="badge ${m[p]||'badge-medium'}">${p}</span>`;
}

// ─── TOAST ───────────────────────────────────────────────
function toast(msg, type = 'info') {
  const el = document.createElement('div');
  el.className = `toast ${type}`; el.textContent = msg;
  document.getElementById('toast-container').appendChild(el);
  setTimeout(() => el.remove(), 3200);
}

// ─── UTILS ───────────────────────────────────────────────
function esc(s) { return String(s||'').replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;'); }
function fmtDate(iso) {
  if (!iso) return '—';
  return new Date(iso).toLocaleDateString('en-US',{month:'short',day:'numeric',year:'numeric'});
}
function fmtDateTime(iso) {
  if (!iso) return '—';
  const d = new Date(iso);
  return d.toLocaleDateString('en-US',{month:'short',day:'numeric'}) + ' ' +
         d.toLocaleTimeString('en-US',{hour:'2-digit',minute:'2-digit'});
}

// ─── START ───────────────────────────────────────────────
initApp();
</script>
</body>
</html>
