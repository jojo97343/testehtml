<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hub de Révisions — CCA</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=Inter:wght@300;400;500&display=swap" rel="stylesheet">
    <style>
        :root {
            --sidebar-w: 300px;
            --bg-deep:   #0b0c10;
            --bg-card:   #13141a;
            --bg-hover:  #1a1c25;
            --border:    #222430;
            --accent:    #f0c040;
            --accent2:   #4d96ff;
            --text:      #c8c4d8;
            --muted:     #555668;
            --white:     #f0eefc;
            --danger:    #ff5c5c;
            --success:   #4dcc8f;
        }

        *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

        html, body {
            height: 100%;
            width: 100%;
            margin: 0;
            padding: 0;
            overflow: hidden;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--bg-deep);
            color: var(--text);
        }

        /* ══ LOGIN ══════════════════════════════ */
        #login-screen {
            display: flex; align-items: center; justify-content: center;
            height: 100%; padding: 24px;
            position: relative; overflow: hidden;
        }

        #login-screen::before {
            content: ''; position: absolute; inset: 0;
            background:
                radial-gradient(ellipse 600px 400px at 20% 50%, rgba(77,150,255,.07), transparent 70%),
                radial-gradient(ellipse 400px 300px at 80% 30%, rgba(240,192,64,.05), transparent 70%);
            pointer-events: none;
        }

        .login-card {
            background: var(--bg-card); border: 1px solid var(--border);
            border-radius: 20px; padding: 48px 44px;
            width: 100%; max-width: 420px;
            position: relative; z-index: 1;
            animation: slideUp .45s cubic-bezier(.4,0,.2,1);
        }

        @keyframes slideUp {
            from { opacity:0; transform:translateY(20px); }
            to   { opacity:1; transform:translateY(0); }
        }

        .login-logo { display:flex; align-items:center; gap:14px; margin-bottom:32px; }

        .login-logo-icon {
            width:46px; height:46px; background:var(--accent);
            border-radius:12px; display:grid; place-items:center; font-size:22px;
        }

        .login-logo-text {
            font-family:'Syne',sans-serif; font-size:1.15rem;
            font-weight:800; color:var(--white); line-height:1.1;
        }

        .login-logo-sub {
            font-size:.65rem; color:var(--muted);
            letter-spacing:1.5px; text-transform:uppercase; margin-top:2px;
        }

        .login-title {
            font-family:'Syne',sans-serif; font-size:1.5rem;
            font-weight:800; color:var(--white); margin-bottom:6px;
        }

        .login-sub { font-size:.82rem; color:var(--muted); margin-bottom:32px; line-height:1.5; }

        .input-label {
            display:block; font-size:.72rem; color:var(--muted);
            letter-spacing:1px; text-transform:uppercase; margin-bottom:8px; font-weight:500;
        }

        .code-input {
            width:100%; background:var(--bg-deep); border:1px solid var(--border);
            border-radius:10px; padding:14px 18px;
            font-family:'Syne',sans-serif; font-size:1.1rem; font-weight:700;
            color:var(--white); letter-spacing:3px; text-align:center;
            text-transform:uppercase; outline:none;
            transition:border-color .2s, box-shadow .2s;
        }

        .code-input:focus { border-color:var(--accent2); box-shadow:0 0 0 3px rgba(77,150,255,.12); }

        .code-input.error {
            border-color:var(--danger);
            box-shadow:0 0 0 3px rgba(255,92,92,.12);
            animation:shake .3s ease;
        }

        @keyframes shake {
            0%,100%{transform:translateX(0)} 25%{transform:translateX(-6px)} 75%{transform:translateX(6px)}
        }

        .btn-login {
            width:100%; background:var(--accent2); border:none; border-radius:10px;
            padding:14px; font-family:'Syne',sans-serif; font-size:.9rem; font-weight:700;
            color:#fff; cursor:pointer; margin-top:14px; letter-spacing:.5px;
            transition:background .2s, transform .1s;
        }

        .btn-login:hover  { background:#3a80e8; }
        .btn-login:active { transform:scale(.98); }
        .btn-login:disabled { opacity:.5; cursor:not-allowed; }

        .login-error {
            display:none; align-items:center; gap:8px;
            background:rgba(255,92,92,.08); border:1px solid rgba(255,92,92,.25);
            border-radius:8px; padding:10px 14px;
            font-size:.78rem; color:var(--danger); margin-top:12px;
        }

        .login-error.visible { display:flex; }

        .login-footer {
            margin-top:28px; padding-top:20px; border-top:1px solid var(--border);
            font-size:.68rem; color:var(--muted); text-align:center; line-height:1.5;
        }

        .spinner {
            display:inline-block; width:15px; height:15px;
            border:2px solid rgba(255,255,255,.3); border-top-color:#fff;
            border-radius:50%; animation:spin .6s linear infinite; vertical-align:middle;
        }

        @keyframes spin { to { transform:rotate(360deg); } }

        /* ══ HUB ════════════════════════════════ */
        #hub-screen { display:none; height:100vh; overflow:hidden; }
        #hub-screen.visible { display:flex; }

        nav {
            width:var(--sidebar-w); flex-shrink:0;
            background:var(--bg-card); border-right:1px solid var(--border);
            display:flex; flex-direction:column; position:relative; overflow:hidden;
        }

        nav::before {
            content:''; position:absolute; inset:0;
            background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
            pointer-events:none; opacity:.5; z-index:0;
        }

        nav > * { position:relative; z-index:1; }

        .nav-header { padding:28px 24px 24px; border-bottom:1px solid var(--border); }

        .nav-logo { display:flex; align-items:center; gap:12px; margin-bottom:14px; }

        .logo-icon {
            width:38px; height:38px; background:var(--accent); border-radius:10px;
            display:grid; place-items:center; font-size:18px; flex-shrink:0;
        }

        .nav-title {
            font-family:'Syne',sans-serif; font-size:1.05rem; font-weight:800;
            color:var(--white); line-height:1.1; letter-spacing:-.3px;
        }

        .nav-sub { font-size:.65rem; color:var(--muted); letter-spacing:1.5px; text-transform:uppercase; margin-top:2px; }

        .session-badge {
            display:inline-flex; align-items:center; gap:6px;
            background:rgba(77,204,143,.10); border:1px solid rgba(77,204,143,.25);
            border-radius:20px; padding:4px 10px;
            font-size:.68rem; color:var(--success); font-weight:500; letter-spacing:.5px;
        }

        .session-badge::before {
            content:''; width:6px; height:6px; background:var(--success); border-radius:50%;
            animation:pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%,100%{opacity:1;transform:scale(1)} 50%{opacity:.5;transform:scale(.7)}
        }

        .menu-section {
            padding:20px 24px 8px; font-size:.6rem; letter-spacing:2px;
            text-transform:uppercase; color:var(--muted); font-weight:500;
        }

        .menu-list { list-style:none; padding:0 12px; flex-grow:1; overflow-y:auto; scrollbar-width:none; }
        .menu-list::-webkit-scrollbar { display:none; }

        .menu-item {
            display:flex; align-items:center; gap:12px; padding:11px 14px;
            border-radius:10px; cursor:pointer; color:var(--text);
            transition:background .15s, color .15s; margin-bottom:3px;
        }

        .menu-item:hover { background:var(--bg-hover); color:var(--white); }
        .menu-item.active { background:rgba(77,150,255,.12); color:var(--accent2); font-weight:500; }

        .item-icon {
            width:32px; height:32px; border-radius:8px; display:grid; place-items:center;
            font-size:15px; flex-shrink:0; background:rgba(255,255,255,.04);
        }

        .menu-item.active .item-icon { background:rgba(77,150,255,.18); }
        .item-label { font-size:.82rem; }

        .item-arrow {
            margin-left:auto; opacity:0; color:var(--accent2); font-size:.7rem;
            transition:opacity .15s, transform .15s;
        }

        .menu-item:hover .item-arrow,
        .menu-item.active .item-arrow { opacity:1; transform:translateX(2px); }

        .menu-divider { height:1px; background:var(--border); margin:8px 12px; }

        .menu-item.admin-item .item-icon { background:rgba(240,192,64,.12); }
        .menu-item.admin-item:hover { color:var(--accent); }
        .menu-item.admin-item.active { background:rgba(240,192,64,.10); color:var(--accent); }
        .menu-item.admin-item.active .item-icon { background:rgba(240,192,64,.18); }
        .menu-item.admin-item.active .item-arrow { color:var(--accent); }

        .nav-footer {
            padding:16px 20px; border-top:1px solid var(--border);
            display:flex; align-items:center; justify-content:space-between;
        }

        .footer-text { font-size:.65rem; color:var(--muted); line-height:1.4; }
        .footer-text strong { color:var(--text); font-weight:500; }

        .btn-logout {
            background:rgba(255,92,92,.08); border:1px solid rgba(255,92,92,.2);
            border-radius:6px; padding:5px 10px; font-size:.65rem; color:var(--danger);
            cursor:pointer; font-family:'Inter',sans-serif; transition:background .15s;
        }

        .btn-logout:hover { background:rgba(255,92,92,.15); }

        main {
            flex:1; position:relative; background:var(--bg-deep);
            display:flex; flex-direction:column; min-width:0;
        }

        .topbar {
            height:52px; flex-shrink:0; background:var(--bg-card);
            border-bottom:1px solid var(--border);
            display:flex; align-items:center; padding:0 24px; gap:14px;
        }

        .topbar-breadcrumb { display:flex; align-items:center; gap:8px; font-size:.8rem; color:var(--muted); }
        .topbar-breadcrumb span { color:var(--text); font-weight:500; }
        .topbar-sep { color:var(--border); }
        .topbar-actions { margin-left:auto; display:flex; align-items:center; gap:10px; }

        .btn-topbar {
            background:var(--bg-hover); border:1px solid var(--border); border-radius:8px;
            padding:6px 14px; font-size:.72rem; color:var(--text); cursor:pointer;
            font-family:'Inter',sans-serif; transition:border-color .15s, color .15s;
        }

        .btn-topbar:hover { border-color:var(--accent2); color:var(--accent2); }

        .loader {
            position:absolute; top:0; left:0; height:3px; width:0%;
            background:linear-gradient(90deg,var(--accent2),var(--accent));
            border-radius:2px; transition:width .4s ease; z-index:10;
        }

        .loader.loading { width:70%; }
        .loader.done { width:100%; opacity:0; transition:width .2s, opacity .3s .2s; }

        .welcome {
            flex:1; display:flex; flex-direction:column;
            align-items:center; justify-content:center; gap:18px; padding:40px;
        }

        .welcome.hidden { display:none; }

        .welcome-icon { font-size:3rem; animation:float 4s ease-in-out infinite; }

        @keyframes float {
            0%,100%{transform:translateY(0)} 50%{transform:translateY(-8px)}
        }

        .welcome h1 {
            font-family:'Syne',sans-serif; font-size:2rem; font-weight:800;
            color:var(--white); text-align:center; line-height:1.1;
        }

        .welcome p { font-size:.85rem; color:var(--muted); text-align:center; max-width:360px; line-height:1.6; }

        .welcome-cards { display:flex; gap:12px; flex-wrap:wrap; justify-content:center; margin-top:10px; }

        .welcome-card {
            background:var(--bg-card); border:1px solid var(--border); border-radius:12px;
            padding:14px 18px; font-size:.75rem; color:var(--text); cursor:pointer;
            transition:border-color .2s, color .2s, transform .2s;
            display:flex; align-items:center; gap:8px;
        }

        .welcome-card:hover { border-color:var(--accent2); color:var(--white); transform:translateY(-2px); }

        .iframe-wrapper { display:none; flex:1; position:relative; }
        .iframe-wrapper.visible { display:block; }
        iframe { width:100%; height:100%; border:none; }

        /* ══ ADMIN ══════════════════════════════ */
        #admin-panel { display:none; flex:1; flex-direction:column; overflow:hidden; }
        #admin-panel.visible { display:flex; }

        .admin-content { flex:1; overflow-y:auto; padding:28px; }

        .admin-header {
            display:flex; align-items:flex-start; justify-content:space-between;
            margin-bottom:24px; flex-wrap:wrap; gap:12px;
        }

        .admin-title { font-family:'Syne',sans-serif; font-size:1.3rem; font-weight:800; color:var(--white); }
        .admin-subtitle { font-size:.78rem; color:var(--muted); margin-top:2px; }

        .stats-row {
            display:grid; grid-template-columns:repeat(auto-fit,minmax(140px,1fr));
            gap:12px; margin-bottom:24px;
        }

        .stat-card { background:var(--bg-card); border:1px solid var(--border); border-radius:12px; padding:18px 20px; }
        .stat-value { font-family:'Syne',sans-serif; font-size:1.8rem; font-weight:800; color:var(--white); }
        .stat-label { font-size:.72rem; color:var(--muted); margin-top:2px; }

        .section-card {
            background:var(--bg-card); border:1px solid var(--border);
            border-radius:14px; padding:22px 24px; margin-bottom:20px;
        }

        .section-title {
            font-family:'Syne',sans-serif; font-size:.9rem; font-weight:700;
            color:var(--white); margin-bottom:16px;
        }

        .gen-form { display:flex; gap:10px; flex-wrap:wrap; align-items:flex-end; }

        .form-field { display:flex; flex-direction:column; gap:6px; flex:1; min-width:140px; }

        .form-label { font-size:.68rem; color:var(--muted); text-transform:uppercase; letter-spacing:.8px; }

        .form-input {
            background:var(--bg-deep); border:1px solid var(--border); border-radius:8px;
            padding:9px 12px; font-size:.82rem; color:var(--white);
            font-family:'Inter',sans-serif; outline:none; transition:border-color .2s;
        }

        .form-input:focus { border-color:var(--accent2); }

        .btn-gen {
            background:var(--accent); border:none; border-radius:8px; padding:9px 20px;
            font-family:'Syne',sans-serif; font-size:.82rem; font-weight:700;
            color:#1a1200; cursor:pointer; white-space:nowrap;
            transition:background .2s, transform .1s;
        }

        .btn-gen:hover { background:#f5cc55; }
        .btn-gen:active { transform:scale(.98); }
        .btn-gen:disabled { opacity:.5; cursor:not-allowed; }

        .codes-table-wrap { overflow-x:auto; }
        .codes-table { width:100%; border-collapse:collapse; font-size:.8rem; }

        .codes-table th {
            text-align:left; padding:10px 14px; font-size:.65rem;
            letter-spacing:1px; text-transform:uppercase; color:var(--muted);
            border-bottom:1px solid var(--border); font-weight:500;
        }

        .codes-table td {
            padding:12px 14px; border-bottom:1px solid rgba(34,36,48,.6);
            color:var(--text); vertical-align:middle;
        }

        .codes-table tr:last-child td { border-bottom:none; }
        .codes-table tr:hover td { background:rgba(255,255,255,.015); }

        .code-pill {
            font-family:'Syne',sans-serif; font-weight:700; font-size:.85rem;
            letter-spacing:2px; color:var(--white);
            background:var(--bg-deep); border:1px solid var(--border);
            border-radius:6px; padding:4px 10px; display:inline-block;
        }

        .badge {
            display:inline-flex; align-items:center; gap:5px;
            border-radius:20px; padding:3px 10px; font-size:.68rem; font-weight:500;
        }

        .badge::before { content:''; width:5px; height:5px; border-radius:50%; }

        .badge-active   { background:rgba(77,204,143,.12); color:var(--success); border:1px solid rgba(77,204,143,.2); }
        .badge-active::before   { background:var(--success); }
        .badge-online   { background:rgba(77,150,255,.12);  color:var(--accent2); border:1px solid rgba(77,150,255,.2); }
        .badge-online::before   { background:var(--accent2); }
        .badge-revoked  { background:rgba(85,86,104,.12);   color:var(--muted);   border:1px solid rgba(85,86,104,.2); }
        .badge-revoked::before  { background:var(--muted); }

        .actions-cell { display:flex; gap:6px; flex-wrap:wrap; }

        .btn-action {
            border-radius:6px; padding:4px 10px; font-size:.68rem; cursor:pointer;
            font-family:'Inter',sans-serif; transition:background .15s; white-space:nowrap;
            border:1px solid transparent; background:transparent;
        }

        .btn-copy    { border-color:var(--border); color:var(--muted); }
        .btn-copy:hover    { background:var(--bg-hover); color:var(--text); }
        .btn-revoke  { border-color:rgba(255,92,92,.25); color:var(--danger); }
        .btn-revoke:hover  { background:rgba(255,92,92,.1); }
        .btn-restore { border-color:rgba(77,204,143,.25); color:var(--success); }
        .btn-restore:hover { background:rgba(77,204,143,.1); }
        .btn-kick    { border-color:rgba(77,150,255,.25); color:var(--accent2); }
        .btn-kick:hover    { background:rgba(77,150,255,.1); }

        .empty-state { text-align:center; padding:48px 24px; color:var(--muted); font-size:.82rem; }

        /* Setup card */
        .setup-card {
            background:rgba(240,192,64,.06); border:1px solid rgba(240,192,64,.2);
            border-radius:14px; padding:22px 24px; margin-bottom:20px;
        }

        .setup-card .section-title { color:var(--accent); }

        .setup-step {
            display:flex; gap:12px; margin-bottom:14px; font-size:.82rem; line-height:1.6;
        }

        .setup-num {
            width:22px; height:22px; border-radius:50%; background:var(--accent);
            color:#1a1200; font-weight:700; font-size:.7rem; display:grid; place-items:center;
            flex-shrink:0; margin-top:2px;
        }

        .setup-card code {
            background:rgba(240,192,64,.15); border-radius:4px;
            padding:1px 6px; font-family:monospace; font-size:.78rem; color:var(--accent);
        }

        pre.sql {
            background:var(--bg-deep); border:1px solid var(--border);
            border-radius:8px; padding:16px; font-size:.72rem;
            color:var(--text); overflow-x:auto; line-height:1.7;
            font-family:monospace; margin-top:10px;
        }

        /* Toast */
        .toast {
            position:fixed; bottom:24px; right:24px;
            background:var(--bg-card); border:1px solid var(--border);
            border-radius:10px; padding:12px 18px; font-size:.78rem; color:var(--text);
            z-index:999; display:flex; align-items:center; gap:8px;
            transform:translateY(80px); opacity:0;
            transition:transform .3s, opacity .3s; max-width:320px;
        }

        .toast.visible { transform:translateY(0); opacity:1; }
        .toast.success { border-color:rgba(77,204,143,.3); color:var(--success); }
        .toast.error   { border-color:rgba(255,92,92,.3);  color:var(--danger); }

        /* Burger */
        .burger {
            display:none; width:38px; height:38px; background:var(--bg-hover);
            border:1px solid var(--border); border-radius:10px; cursor:pointer;
            align-items:center; justify-content:center; flex-direction:column;
            gap:5px; flex-shrink:0; padding:0;
        }

        .burger span { display:block; width:16px; height:2px; background:var(--text); border-radius:2px; }

        .nav-overlay {
            display:none; position:fixed; inset:0; background:rgba(0,0,0,.6);
            backdrop-filter:blur(2px); z-index:99; opacity:0;
            transition:opacity .3s; pointer-events:none;
        }

        .nav-overlay.visible { opacity:1; pointer-events:all; }

        @media (max-width:768px) {
            .burger { display:flex; }
            nav {
                position:fixed; top:0; left:0; height:100%;
                width:min(300px,85vw); z-index:100;
                transform:translateX(-100%);
                transition:transform .3s cubic-bezier(.4,0,.2,1); overflow-y:auto;
            }
            nav.open { transform:translateX(0); }
            .nav-overlay { display:block; }
            main { width:100%; }
            .topbar { gap:10px; padding:0 14px; }
            .topbar-actions .btn-topbar:first-child { display:none; }
            .welcome h1 { font-size:1.5rem; }
            .welcome-cards { flex-direction:column; align-items:stretch; }
            .login-card { padding:32px 24px; }
            .admin-content { padding:16px; }
            .gen-form { flex-direction:column; }
        }
    </style>
</head>
<body>

<!-- ══ LOGIN ════════════════════════════ -->
<div id="login-screen">
    <div class="login-card">
        <div class="login-logo">
            <div class="login-logo-icon">📚</div>
            <div>
                <div class="login-logo-text">Hub Révisions</div>
                <div class="login-logo-sub">Licence CCA — INTEC</div>
            </div>
        </div>
        <h1 class="login-title">Accès sécurisé</h1>
        <p class="login-sub">Saisis ton code d'accès personnel pour entrer dans le hub.</p>
        <label class="input-label" for="code-input">Code d'accès</label>
        <input type="text" id="code-input" class="code-input"
            placeholder="XXXXXXXX" maxlength="12"
            autocomplete="off" autocorrect="off" spellcheck="false">
        <button class="btn-login" id="btn-login" onclick="handleLogin()">Accéder au hub</button>
        <div class="login-error" id="login-error">
            <span>⚠</span>
            <span id="login-error-msg">Code incorrect ou révoqué.</span>
        </div>
        <div class="login-footer">
            Accès réservé aux étudiants INTEC CCA<br>
            Contacte l'administrateur pour obtenir ton code.
        </div>
    </div>
</div>

<!-- ══ HUB ══════════════════════════════ -->
<div id="hub-screen">
    <div class="nav-overlay" id="nav-overlay" onclick="closeSidebar()"></div>

    <nav id="sidebar">
        <div class="nav-header">
            <div class="nav-logo">
                <div class="logo-icon">📚</div>
                <div>
                    <div class="nav-title">Hub Révisions</div>
                    <div class="nav-sub">Licence CCA</div>
                </div>
            </div>
            <div class="session-badge">Session active</div>
        </div>

        <div class="menu-section">Matières</div>

        <ul class="menu-list">
            <li class="menu-item" onclick="loadPage('CG.html', this, 'Contrôle de Gestion')">
                <div class="item-icon">📊</div>
                <span class="item-label">Contrôle de Gestion</span>
                <span class="item-arrow">›</span>
            </li>
            <li class="menu-item" onclick="loadPage('FI.html', this, 'Finance')">
                <div class="item-icon">💰</div>
                <span class="item-label">Finance</span>
                <span class="item-arrow">›</span>
            </li>
            <li class="menu-item" onclick="loadPage('mana.html', this, 'Management')">
                <div class="item-icon">👔</div>
                <span class="item-label">Management</span>
                <span class="item-arrow">›</span>
            </li>
            <li class="menu-item" onclick="loadPage('SO.html', this, 'Droit des Sociétés')">
                <div class="item-icon">⚖️</div>
                <span class="item-label">Droit des Sociétés</span>
                <span class="item-arrow">›</span>
            </li>
            <li class="menu-item" onclick="loadPage('DT.html', this, 'Droit du Travail')">
                <div class="item-icon">👷</div>
                <span class="item-label">Droit du Travail</span>
                <span class="item-arrow">›</span>
            </li>
            <li class="menu-item" onclick="loadPage('fisca.html', this, 'Droit Fiscal')">
                <div class="item-icon">🧾</div>
                <span class="item-label">Droit Fiscal</span>
                <span class="item-arrow">›</span>
            </li>
            <li class="menu-item" onclick="loadPage('compta.html', this, 'Comptabilité')">
                <div class="item-icon">📑</div>
                <span class="item-label">Comptabilité</span>
                <span class="item-arrow">›</span>
            </li>
            <div class="menu-divider" id="admin-divider" style="display:none"></div>
            <li class="menu-item admin-item" id="admin-menu-item" style="display:none" onclick="openAdmin()">
                <div class="item-icon">⚙️</div>
                <span class="item-label">Administration</span>
                <span class="item-arrow">›</span>
            </li>
        </ul>

        <div class="nav-footer">
            <div class="footer-text">
                <strong>7 matières</strong><br>
                <span id="footer-name">Session</span>
            </div>
            <button class="btn-logout" onclick="handleLogout()">Déconnexion</button>
        </div>
    </nav>

    <main>
        <div class="topbar">
            <button class="burger" onclick="toggleSidebar()">
                <span></span><span></span><span></span>
            </button>
            <div class="topbar-breadcrumb">
                Hub Révisions <span class="topbar-sep">›</span>
                <span id="current-page">Accueil</span>
            </div>
            <div class="topbar-actions">
                <button class="btn-topbar" onclick="reloadFrame()">↺ Recharger</button>
                <button class="btn-topbar" onclick="openFullscreen()">⛶ Plein écran</button>
            </div>
        </div>

        <div class="loader" id="loader"></div>

        <div class="welcome" id="welcome">
            <div class="welcome-icon">🎯</div>
            <h1>Bonne révision !</h1>
            <p>Sélectionne une matière dans le menu pour commencer.</p>
            <div class="welcome-cards">
                <div class="welcome-card" onclick="loadPage('CG.html',null,'Contrôle de Gestion')">📊 Contrôle de Gestion</div>
                <div class="welcome-card" onclick="loadPage('mana.html',null,'Management')">👔 Management</div>
                <div class="welcome-card" onclick="loadPage('SO.html',null,'Droit des Sociétés')">⚖️ Droit des Sociétés</div>
            </div>
        </div>

        <div class="iframe-wrapper" id="iframe-wrapper">
            <iframe id="content-frame"></iframe>
        </div>

        <!-- Panneau admin -->
        <div id="admin-panel">
            <div class="admin-content">

                <!-- Setup guide (masqué une fois configuré) -->
                <div class="setup-card" id="setup-guide" style="display:none">
                    <div class="section-title">🔧 Configuration Supabase requise</div>

                    <div class="setup-step">
                        <div class="setup-num">1</div>
                        <div>Va sur <strong>supabase.com</strong> → crée un projet → attends 2 min</div>
                    </div>
                    <div class="setup-step">
                        <div class="setup-num">2</div>
                        <div>Va dans <strong>SQL Editor → New Query</strong>, colle et exécute ce script :</div>
                    </div>
                    <pre class="sql">CREATE TABLE access_codes (
  id uuid DEFAULT gen_random_uuid() PRIMARY KEY,
  code TEXT UNIQUE NOT NULL,
  name TEXT,
  note TEXT,
  is_active BOOLEAN DEFAULT true,
  session_token TEXT,
  last_seen_at TIMESTAMPTZ,
  created_at TIMESTAMPTZ DEFAULT now()
);

ALTER TABLE access_codes ENABLE ROW LEVEL SECURITY;

CREATE POLICY "anon_read" ON access_codes
  FOR SELECT TO anon USING (true);

CREATE POLICY "anon_update" ON access_codes
  FOR UPDATE TO anon USING (true);</pre>

                    <div class="setup-step" style="margin-top:14px">
                        <div class="setup-num">3</div>
                        <div>Va dans <strong>Project Settings → API</strong>, copie <code>Project URL</code> et <code>anon public</code>, colle-les dans le code source à la place de <code>https://qridhnhidcrfffzejzgt.supabase.co</code> et <code>sb_publishable_iELf6p0T6VpTWFNP6Hc9_g_TAzUmz9E</code></div>
                    </div>
                    <div class="setup-step">
                        <div class="setup-num">4</div>
                        <div>Push sur GitHub → c'est prêt !</div>
                    </div>
                </div>

                <div class="admin-header">
                    <div>
                        <div class="admin-title">⚙️ Administration</div>
                        <div class="admin-subtitle">Gestion des codes d'accès</div>
                    </div>
                    <button class="btn-gen" onclick="loadCodes()" style="padding:8px 16px;font-size:.75rem">↺ Actualiser</button>
                </div>

                <div class="stats-row">
                    <div class="stat-card">
                        <div class="stat-value" id="stat-total">—</div>
                        <div class="stat-label">Codes créés</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="stat-active" style="color:var(--success)">—</div>
                        <div class="stat-label">Actifs</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="stat-online" style="color:var(--accent2)">—</div>
                        <div class="stat-label">Connectés maintenant</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="stat-revoked" style="color:var(--muted)">—</div>
                        <div class="stat-label">Révoqués</div>
                    </div>
                </div>

                <div class="section-card">
                    <div class="section-title">✦ Générer un nouveau code</div>
                    <div class="gen-form">
                        <div class="form-field">
                            <label class="form-label">Nom / prénom</label>
                            <input type="text" class="form-input" id="gen-name" placeholder="Ex : Marie Dupont">
                        </div>
                        <div class="form-field">
                            <label class="form-label">Note (optionnel)</label>
                            <input type="text" class="form-input" id="gen-note" placeholder="Ex : Promo 2026">
                        </div>
                        <button class="btn-gen" id="btn-gen" onclick="generateCode()">+ Générer</button>
                    </div>
                </div>

                <div class="section-card">
                    <div class="section-title">📋 Codes existants</div>
                    <div class="codes-table-wrap">
                        <table class="codes-table">
                            <thead>
                                <tr>
                                    <th>Code</th>
                                    <th>Nom</th>
                                    <th>Note</th>
                                    <th>Statut</th>
                                    <th>Dernière activité</th>
                                    <th>Actions</th>
                                </tr>
                            </thead>
                            <tbody id="codes-tbody">
                                <tr><td colspan="6" class="empty-state">Chargement…</td></tr>
                            </tbody>
                        </table>
                    </div>
                </div>

            </div>
        </div>
    </main>
</div>

<div class="toast" id="toast"></div>

<script>
// ════════════════════════════════════════════════
//  ⚠️  REMPLIS CES 3 VALEURS AVEC TES INFOS SUPABASE
// ════════════════════════════════════════════════
const SB_URL  = 'https://qridhnhidcrfffzejzgt.supabase.co';        // ex: https://xxxx.supabase.co
const SB_KEY  = 'sb_publishable_iELf6p0T6VpTWFNP6Hc9_g_TAzUmz9E';        // clé "anon public"
const ADMIN_CODE = 'ADMIN2025';     // ← ton code admin fixe, change-le !
// ════════════════════════════════════════════════

const CONFIGURED = true;
const SESSION_KEY = 'hub_sess';

// ── Utilitaires ─────────────────────────
function makeCode() {
    const L = 'ABCDEFGHJKLMNPQRSTUVWXYZ';
    const D = '23456789';
    return Array.from({length:4},()=>L[Math.floor(Math.random()*L.length)]).join('') +
           Array.from({length:4},()=>D[Math.floor(Math.random()*D.length)]).join('');
}

function makeToken() {
    return Math.random().toString(36).slice(2) + Date.now().toString(36);
}

function fmtDate(iso) {
    if (!iso) return '—';
    return new Date(iso).toLocaleString('fr-FR',{day:'2-digit',month:'2-digit',year:'numeric',hour:'2-digit',minute:'2-digit'});
}

function showToast(msg, type='success') {
    const t = document.getElementById('toast');
    t.textContent = msg; t.className = 'toast visible ' + type;
    clearTimeout(t._t); t._t = setTimeout(()=>{ t.className='toast'; }, 3200);
}

// ── Supabase REST ────────────────────────
const H = (key=SB_KEY) => ({
    'apikey': key,
    'Authorization': `Bearer ${key}`,
    'Content-Type': 'application/json',
    'Prefer': 'return=representation'
});

async function sbSelect(query) {
    const r = await fetch(`${SB_URL}/rest/v1/${query}`, { headers: H() });
    return r.ok ? await r.json() : null;
}

async function sbInsert(table, body) {
    const r = await fetch(`${SB_URL}/rest/v1/${table}`, {
        method:'POST', headers: H(), body: JSON.stringify(body)
    });
    return r.ok ? await r.json() : null;
}

async function sbUpdate(table, filter, body) {
    const params = Object.entries(filter).map(([k,v])=>`${k}=eq.${encodeURIComponent(v)}`).join('&');
    const r = await fetch(`${SB_URL}/rest/v1/${table}?${params}`, {
        method:'PATCH', headers: H(), body: JSON.stringify(body)
    });
    return r.ok;
}

async function sbDelete(table, filter) {
    const params = Object.entries(filter).map(([k,v])=>`${k}=eq.${encodeURIComponent(v)}`).join('&');
    const r = await fetch(`${SB_URL}/rest/v1/${table}?${params}`, {
        method:'DELETE', headers: H()
    });
    return r.ok;
}

// ── Session ──────────────────────────────
let session = null;

function getSession() {
    try { return JSON.parse(sessionStorage.getItem(SESSION_KEY)); } catch { return null; }
}

function saveSession(s) { sessionStorage.setItem(SESSION_KEY, JSON.stringify(s)); }
function clearSession()  { sessionStorage.removeItem(SESSION_KEY); }

// ── Login ────────────────────────────────
document.getElementById('code-input').addEventListener('keydown', e => {
    if (e.key === 'Enter') handleLogin();
});

async function handleLogin() {
    const val    = document.getElementById('code-input').value.trim().toUpperCase();
    const btn    = document.getElementById('btn-login');
    const errEl  = document.getElementById('login-error');
    const errMsg = document.getElementById('login-error-msg');
    const input  = document.getElementById('code-input');

    if (!val) return;
    input.classList.remove('error');
    errEl.classList.remove('visible');

    // Admin → accès direct, pas de vérif Supabase
    if (val === ADMIN_CODE) {
        session = { code: val, isAdmin: true };
        saveSession(session);
        enterHub();
        return;
    }

    // Étudiant
    if (!CONFIGURED) {
        errMsg.textContent = 'Supabase non configuré. Configure SB_URL et SB_KEY dans le code.';
        errEl.classList.add('visible'); input.classList.add('error');
        return;
    }

    btn.disabled = true;
    btn.innerHTML = '<span class="spinner"></span>';

    try {
        const rows = await sbSelect(`access_codes?code=eq.${val}&select=*`);

        if (!rows || rows.length === 0) throw new Error('Code introuvable. Vérifie la saisie.');
        const row = rows[0];
        if (!row.is_active) throw new Error('Ce code a été révoqué. Contacte l\'administrateur.');

        // Nouveau token → invalide toute autre session avec ce code
        const token = makeToken();
        await sbUpdate('access_codes', {code: val}, {
            session_token: token,
            last_seen_at: new Date().toISOString()
        });

        session = { code: val, token, isAdmin: false, name: row.name };
        saveSession(session);
        enterHub();

    } catch(err) {
        errMsg.textContent = err.message || 'Erreur de connexion.';
        errEl.classList.add('visible');
        input.classList.add('error');
    }

    btn.disabled = false;
    btn.textContent = 'Accéder au hub';
}

// ── Anti-partage heartbeat ───────────────
let heartbeat = null;

function startHeartbeat() {
    heartbeat = setInterval(async () => {
        if (!session || session.isAdmin || !CONFIGURED) return;
        const rows = await sbSelect(`access_codes?code=eq.${session.code}&select=is_active,session_token`);
        if (!rows || rows.length === 0) return;
        const row = rows[0];

        if (!row.is_active) {
            clearSession();
            showToast('⚠️ Accès révoqué par l\'administrateur.', 'error');
            setTimeout(() => location.reload(), 2500);
            return;
        }

        if (row.session_token !== session.token) {
            clearSession();
            showToast('⚠️ Session expirée : connexion détectée sur un autre appareil.', 'error');
            setTimeout(() => location.reload(), 2800);
            return;
        }

        // Maintenir last_seen_at
        await sbUpdate('access_codes', {code: session.code}, {
            last_seen_at: new Date().toISOString()
        });

    }, 30000); // toutes les 30s
}

// ── Entrée dans le hub ───────────────────
function enterHub() {
    document.getElementById('login-screen').style.display = 'none';
    document.getElementById('hub-screen').classList.add('visible');

    if (session.isAdmin) {
        document.getElementById('admin-menu-item').style.display = 'flex';
        document.getElementById('admin-divider').style.display   = 'block';
        document.getElementById('footer-name').textContent = 'Administrateur';
        if (!CONFIGURED) document.getElementById('setup-guide').style.display = 'block';
    } else {
        document.getElementById('footer-name').textContent = session.name || 'Étudiant';
        startHeartbeat();
    }
}

// ── Logout ────────────────────────────────
async function handleLogout() {
    if (heartbeat) clearInterval(heartbeat);
    if (session && !session.isAdmin && CONFIGURED) {
        await sbUpdate('access_codes', {code: session.code}, { session_token: null });
    }
    clearSession();
    location.reload();
}

// ── Navigation ────────────────────────────
let currentFile = null;

function loadPage(fileName, el, label) {
    currentFile = fileName;
    document.querySelectorAll('.menu-item').forEach(i => i.classList.remove('active'));
    if (el) {
        el.classList.add('active');
    } else {
        document.querySelectorAll('.menu-item').forEach(item => {
            if ((item.getAttribute('onclick')||'').includes(`'${fileName}'`)) item.classList.add('active');
        });
    }
    document.getElementById('admin-panel').classList.remove('visible');
    document.getElementById('welcome').classList.add('hidden');
    document.getElementById('iframe-wrapper').classList.add('visible');
    if (window.innerWidth <= 768) closeSidebar();
    if (label) document.getElementById('current-page').textContent = label;
    const loader = document.getElementById('loader');
    loader.className = 'loader loading';
    const frame = document.getElementById('content-frame');
    frame.onload = () => { loader.className='loader done'; setTimeout(()=>loader.className='loader',600); };
    frame.src = fileName;
}

function openAdmin() {
    document.querySelectorAll('.menu-item').forEach(i => i.classList.remove('active'));
    document.getElementById('admin-menu-item').classList.add('active');
    document.getElementById('welcome').classList.add('hidden');
    document.getElementById('iframe-wrapper').classList.remove('visible');
    document.getElementById('admin-panel').classList.add('visible');
    document.getElementById('current-page').textContent = 'Administration';
    if (window.innerWidth <= 768) closeSidebar();
    loadCodes();
}

function reloadFrame() {
    if (!currentFile) return;
    const loader = document.getElementById('loader');
    loader.className = 'loader loading';
    const frame = document.getElementById('content-frame');
    frame.onload = () => { loader.className='loader done'; setTimeout(()=>loader.className='loader',600); };
    frame.src = currentFile;
}

function openFullscreen() {
    const frame = document.getElementById('content-frame');
    if (frame.requestFullscreen) frame.requestFullscreen();
}

// ── Admin : chargement ───────────────────
async function loadCodes() {
    const tbody = document.getElementById('codes-tbody');
    tbody.innerHTML = '<tr><td colspan="6" class="empty-state">Chargement…</td></tr>';

    if (!CONFIGURED) {
        tbody.innerHTML = '<tr><td colspan="6" class="empty-state">Configure Supabase pour voir les codes.</td></tr>';
        ['stat-total','stat-active','stat-online','stat-revoked'].forEach(id => {
            document.getElementById(id).textContent = '—';
        });
        return;
    }

    const rows = await sbSelect('access_codes?order=created_at.desc&select=*');
    if (!rows) {
        tbody.innerHTML = '<tr><td colspan="6" class="empty-state">Erreur de chargement.</td></tr>';
        return;
    }

    const now = Date.now();
    let active=0, online=0, revoked=0;

    rows.forEach(r => {
        if (!r.is_active) { revoked++; return; }
        active++;
        if (r.last_seen_at && (now - new Date(r.last_seen_at).getTime()) < 90000) online++;
    });

    document.getElementById('stat-total').textContent   = rows.length;
    document.getElementById('stat-active').textContent  = active;
    document.getElementById('stat-online').textContent  = online;
    document.getElementById('stat-revoked').textContent = revoked;

    if (!rows.length) {
        tbody.innerHTML = '<tr><td colspan="6" class="empty-state">Aucun code. Génère le premier !</td></tr>';
        return;
    }

    tbody.innerHTML = rows.map(r => {
        const isOnline = r.last_seen_at && (now - new Date(r.last_seen_at).getTime()) < 90000;
        const badge = !r.is_active
            ? '<span class="badge badge-revoked">Révoqué</span>'
            : isOnline
                ? '<span class="badge badge-online">En ligne</span>'
                : '<span class="badge badge-active">Actif</span>';

        const acts = `<div class="actions-cell">
            <button class="btn-action btn-copy" onclick="copyCode('${r.code}')">Copier</button>
            ${r.is_active
                ? `<button class="btn-action btn-revoke" onclick="revokeCode('${r.id}')">Révoquer</button>
                   ${r.session_token ? `<button class="btn-action btn-kick" onclick="kickCode('${r.id}')">Déco.</button>` : ''}`
                : `<button class="btn-action btn-restore" onclick="restoreCode('${r.id}')">Réactiver</button>`
            }
        </div>`;

        return `<tr>
            <td><span class="code-pill">${r.code}</span></td>
            <td>${r.name || '<span style="color:var(--muted)">—</span>'}</td>
            <td style="color:var(--muted);font-size:.75rem">${r.note || '—'}</td>
            <td>${badge}</td>
            <td style="color:var(--muted);font-size:.75rem">${fmtDate(r.last_seen_at)}</td>
            <td>${acts}</td>
        </tr>`;
    }).join('');
}

// ── Admin : actions ──────────────────────
async function generateCode() {
    const name = document.getElementById('gen-name').value.trim();
    const note = document.getElementById('gen-note').value.trim();
    const btn  = document.getElementById('btn-gen');

    if (!CONFIGURED) { showToast('Configure Supabase d\'abord.', 'error'); return; }

    btn.disabled = true;
    btn.innerHTML = '<span class="spinner" style="border-color:rgba(0,0,0,.3);border-top-color:#1a1200"></span>';

    const code = makeCode();
    const res  = await sbInsert('access_codes', {
        code, name: name||null, note: note||null, is_active: true
    });

    if (res) {
        document.getElementById('gen-name').value = '';
        document.getElementById('gen-note').value = '';
        showToast(`✓ Code créé : ${code}${name ? ' — '+name : ''}`);
        await loadCodes();
    } else {
        showToast('Erreur lors de la création.', 'error');
    }

    btn.disabled = false;
    btn.textContent = '+ Générer';
}

async function revokeCode(id) {
    if (!confirm('Révoquer ce code ? L\'étudiant sera déconnecté.')) return;
    const ok = await sbUpdate('access_codes', {id}, {is_active: false, session_token: null});
    ok ? showToast('Code révoqué.') : showToast('Erreur.', 'error');
    await loadCodes();
}

async function restoreCode(id) {
    const ok = await sbUpdate('access_codes', {id}, {is_active: true});
    ok ? showToast('Code réactivé.') : showToast('Erreur.', 'error');
    await loadCodes();
}

async function kickCode(id) {
    // Déconnecte la session sans révoquer le code
    const ok = await sbUpdate('access_codes', {id}, {session_token: null});
    ok ? showToast('Étudiant déconnecté.') : showToast('Erreur.', 'error');
    await loadCodes();
}

function copyCode(code) {
    navigator.clipboard.writeText(code)
        .then(() => showToast(`✓ "${code}" copié !`))
        .catch(() => {
            const el = document.createElement('textarea');
            el.value = code; document.body.appendChild(el);
            el.select(); document.execCommand('copy');
            document.body.removeChild(el);
            showToast(`✓ "${code}" copié !`);
        });
}

// ── Mobile sidebar ────────────────────────
function toggleSidebar() {
    document.getElementById('sidebar').classList.contains('open') ? closeSidebar() : openSidebar();
}

function openSidebar() {
    document.getElementById('sidebar').classList.add('open');
    document.getElementById('nav-overlay').classList.add('visible');
}

function closeSidebar() {
    document.getElementById('sidebar').classList.remove('open');
    document.getElementById('nav-overlay').classList.remove('visible');
}

// ── Init ──────────────────────────────────
(function() {
    const s = getSession();
    if (s) { session = s; enterHub(); }
})();
</script>
</body>
</html>
