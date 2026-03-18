# testehtml
<!DOCTYPE html>
<html lang="fr" data-theme="light">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta name="mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="default">
    <title>Mon Coach Finance</title>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@300;400;500;600;700&family=DM+Serif+Display&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        :root {
            --main: #5b5ef4;
            --main-light: #818cf8;
            --main-glow: rgba(91,94,244,0.18);
            --bg: #f4f6fb;
            --bg2: #e8ecf5;
            --card: #ffffff;
            --card-border: rgba(0,0,0,0.07);
            --text: #1a1d2e;
            --text-muted: #6b7280;
            --text-hint: #9ca3af;
            --danger: #ef4444;
            --success: #10b981;
            --warning: #f59e0b;
            --shadow: 0 1px 3px rgba(0,0,0,0.07), 0 4px 16px rgba(0,0,0,0.04);
            --shadow-hover: 0 4px 24px rgba(91,94,244,0.12);
            --radius: 16px;
            --radius-sm: 10px;
            --transition: 0.22s cubic-bezier(.4,0,.2,1);
            --nav-h: 68px;
            --header-h: 64px;
        }
        [data-theme="dark"] {
            --bg: #111218;
            --bg2: #1c1e2b;
            --card: #1c1e2b;
            --card-border: rgba(255,255,255,0.07);
            --text: #e8eaf2;
            --text-muted: #9ca3af;
            --text-hint: #6b7280;
            --shadow: 0 1px 3px rgba(0,0,0,0.3), 0 4px 16px rgba(0,0,0,0.2);
            --shadow-hover: 0 4px 24px rgba(91,94,244,0.2);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; -webkit-tap-highlight-color: transparent; }

        html, body {
            font-family: 'DM Sans', sans-serif;
            background: var(--bg);
            color: var(--text);
            min-height: 100vh;
            overscroll-behavior: none;
        }

        /* ── MOBILE NAV BAR ── */
        .mobile-nav {
            display: none;
            position: fixed;
            bottom: 0; left: 0; right: 0;
            height: var(--nav-h);
            background: var(--card);
            border-top: 1px solid var(--card-border);
            z-index: 100;
            padding: 0 4px;
            padding-bottom: env(safe-area-inset-bottom);
        }
        .mobile-nav-inner {
            display: flex;
            height: 64px;
            align-items: stretch;
        }
        .nav-btn {
            flex: 1;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 3px;
            background: none;
            border: none;
            cursor: pointer;
            padding: 8px 4px;
            border-radius: 12px;
            transition: background var(--transition);
            color: var(--text-muted);
            font-family: 'DM Sans', sans-serif;
        }
        .nav-btn.active { color: var(--main); }
        .nav-btn svg { width: 22px; height: 22px; }
        .nav-btn span { font-size: 10px; font-weight: 500; letter-spacing: 0.01em; white-space: nowrap; }
        .nav-indicator {
            position: absolute;
            bottom: 0;
            width: 28px;
            height: 3px;
            background: var(--main);
            border-radius: 2px 2px 0 0;
            transition: transform var(--transition);
        }

        /* ── MOBILE HEADER ── */
        .mobile-header {
            display: none;
            position: sticky;
            top: 0;
            height: var(--header-h);
            background: var(--card);
            border-bottom: 1px solid var(--card-border);
            z-index: 90;
            align-items: center;
            justify-content: space-between;
            padding: 0 20px;
        }
        .mobile-header-title {
            font-family: 'DM Serif Display', serif;
            font-size: 1.1rem;
            color: var(--text);
        }
        .mobile-header-actions { display: flex; gap: 8px; align-items: center; }

        /* ── DESKTOP LAYOUT ── */
        .desktop-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 28px 32px 0;
            margin-bottom: 28px;
            gap: 16px;
            flex-wrap: wrap;
        }
        .header-title h1 {
            font-family: 'DM Serif Display', serif;
            font-size: 1.9rem;
            color: var(--text);
            letter-spacing: -0.01em;
        }
        .header-title h1 em { font-style: normal; color: var(--main); }
        .header-title p { color: var(--text-muted); font-size: 0.83rem; margin-top: 3px; }
        .header-actions { display: flex; gap: 10px; align-items: center; }

        .container {
            max-width: 1200px;
            margin: auto;
            padding: 0 24px 40px;
        }

        /* ── PAGES (mobile tab system) ── */
        .page { display: block; }

        /* ── CARDS ── */
        .card {
            background: var(--card);
            padding: 20px;
            border-radius: var(--radius);
            border: 1px solid var(--card-border);
            box-shadow: var(--shadow);
            margin-bottom: 16px;
        }
        .card-title {
            font-size: 0.75rem;
            font-weight: 700;
            letter-spacing: 0.08em;
            text-transform: uppercase;
            color: var(--text-muted);
            margin-bottom: 14px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .card-title .badge {
            width: 20px; height: 20px;
            background: var(--main);
            color: white;
            border-radius: 50%;
            font-size: 0.68rem;
            display: inline-flex; align-items: center; justify-content: center;
        }

        /* ── STAT GRID ── */
        .stat-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 12px;
            margin-bottom: 20px;
        }
        .stat-box {
            background: var(--card);
            border: 1px solid var(--card-border);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            padding: 16px;
            text-align: center;
        }
        .stat-label { font-size: 0.7rem; color: var(--text-muted); font-weight: 600; text-transform: uppercase; letter-spacing: 0.07em; margin-bottom: 6px; }
        .stat-value { font-size: 1.9rem; font-weight: 700; line-height: 1; }
        .stat-value small { font-size: 1.1rem; font-weight: 600; }
        .stat-box-gold { border-color: rgba(245,158,11,0.3); }
        .stat-box-gold .stat-value { color: #b45309; }
        .stat-box-gold .stat-label { color: #d97706; }
        .reset-coffre {
            font-size: 0.68rem; color: #b45309; background: none;
            border: 1px solid #d97706; border-radius: 20px;
            padding: 2px 10px; margin-top: 6px;
            cursor: pointer; font-family: 'DM Sans', sans-serif;
            width: auto; display: inline-block;
            transition: all var(--transition);
        }
        .reset-coffre:hover { background: #fef3c7; }

        /* ── TWO-COL GRID ── */
        .grid-top { display: grid; grid-template-columns: 1fr 2fr; gap: 16px; margin-bottom: 16px; }

        /* ── FORM ELEMENTS ── */
        label { font-size: 0.8rem; font-weight: 500; color: var(--text-muted); display: block; margin-bottom: 4px; }
        input[type="text"], input[type="number"], select, textarea {
            width: 100%;
            padding: 11px 14px;
            margin-bottom: 12px;
            border-radius: var(--radius-sm);
            border: 1.5px solid var(--bg2);
            background: var(--bg);
            color: var(--text);
            font-family: 'DM Sans', sans-serif;
            font-size: 0.95rem;
            transition: border-color var(--transition), box-shadow var(--transition);
            outline: none;
            -webkit-appearance: none;
            appearance: none;
            min-height: 44px;
        }
        input:focus, select:focus { border-color: var(--main); box-shadow: 0 0 0 3px var(--main-glow); }
        [data-theme="dark"] input, [data-theme="dark"] select { background: var(--bg2); border-color: rgba(255,255,255,0.1); }

        /* ── BUTTONS ── */
        .btn {
            display: inline-flex; align-items: center; justify-content: center; gap: 6px;
            padding: 12px 18px;
            border-radius: var(--radius-sm);
            border: none;
            font-family: 'DM Sans', sans-serif;
            font-weight: 600; font-size: 0.9rem;
            cursor: pointer;
            transition: all var(--transition);
            min-height: 44px;
            width: 100%;
        }
        .btn-primary { background: var(--main); color: white; }
        .btn-primary:hover { background: #4a4de0; transform: translateY(-1px); }
        .btn-primary:active { transform: scale(0.98); }
        .btn-secondary { background: var(--bg2); color: var(--text-muted); }
        .btn-secondary:hover { background: var(--bg); }
        .btn-icon-sm {
            width: 36px; height: 36px; padding: 0;
            border-radius: 8px; border: none;
            background: rgba(239,68,68,0.1);
            color: var(--danger);
            font-size: 0.8rem; cursor: pointer;
            transition: all var(--transition);
            display: inline-flex; align-items: center; justify-content: center;
            flex-shrink: 0;
        }
        .btn-icon-sm:hover { background: var(--danger); color: white; }
        .btn-delete { background: none; border: none; color: var(--danger); cursor: pointer; padding: 6px; font-size: 1rem; transition: transform var(--transition); }
        .btn-delete:hover { transform: scale(1.2); }

        /* ── CATEGORY BUDGET ROWS ── */
        .budget-row { display: flex; gap: 8px; align-items: center; margin-bottom: 8px; }
        .budget-row .cat-label { flex: 1; font-size: 0.88rem; font-weight: 500; min-width: 0; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; }
        .budget-row input { width: 100px; margin: 0; flex-shrink: 0; }

        .add-cat-box { display: flex; gap: 8px; margin-top: 14px; padding-top: 14px; border-top: 1px dashed var(--bg2); }
        .add-cat-box input { margin: 0; flex: 1; }
        .btn-add-cat { width: 44px; height: 44px; padding: 0; flex-shrink: 0; border-radius: var(--radius-sm); border: none; background: var(--main); color: white; font-size: 1.4rem; cursor: pointer; display: flex; align-items: center; justify-content: center; }

        /* ── PLAN SUMMARY ── */
        .plan-summary { margin-top: 14px; padding: 14px; border-radius: 12px; background: var(--bg); border: 1px solid var(--bg2); font-size: 0.85rem; }
        .plan-row { display: flex; justify-content: space-between; align-items: center; margin-bottom: 5px; }
        .plan-row:last-child { margin-bottom: 0; }
        .text-danger { color: var(--danger); font-weight: 700; }
        .text-success { color: var(--success); font-weight: 700; }

        /* ── EXPENSE FORM ── */
        .expense-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
        .expense-grid .field-full { grid-column: span 2; }
        .recurring-row { display: flex; align-items: center; gap: 10px; font-size: 0.85rem; color: var(--text-muted); margin-bottom: 14px; }
        .recurring-row input[type="checkbox"] { width: 18px; height: 18px; accent-color: var(--main); cursor: pointer; margin: 0; flex-shrink: 0; }

        /* ── TABLE ── */
        .table-scroll { overflow-x: auto; border-radius: var(--radius-sm); border: 1px solid var(--bg2); -webkit-overflow-scrolling: touch; }
        .table-scroll table { width: 100%; border-collapse: collapse; min-width: 400px; }
        thead th { text-align: left; font-size: 0.72rem; color: var(--text-muted); padding: 10px 14px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.06em; border-bottom: 1.5px solid var(--bg2); background: var(--bg); position: sticky; top: 0; z-index: 2; white-space: nowrap; }
        tbody td { padding: 11px 14px; border-top: 1px solid var(--bg2); font-size: 0.86rem; vertical-align: middle; }
        tbody tr { transition: background var(--transition); }
        tbody tr:hover { background: var(--bg); }
        [data-theme="dark"] thead th { background: var(--bg2); }

        .cat-pill { background: var(--bg2); padding: 2px 10px; border-radius: 20px; font-size: 0.75rem; white-space: nowrap; }
        .recurring-tag { font-size: 0.65rem; color: var(--main); font-weight: 700; margin-left: 4px; background: var(--main-glow); padding: 1px 6px; border-radius: 20px; }
        .status-ok { background: rgba(16,185,129,0.1); color: #059669; border: 1px solid rgba(16,185,129,0.25); padding: 2px 8px; border-radius: 20px; font-size: 0.68rem; font-weight: 700; white-space: nowrap; }
        .status-over { background: rgba(239,68,68,0.1); color: #dc2626; border: 1px solid rgba(239,68,68,0.2); padding: 2px 8px; border-radius: 20px; font-size: 0.68rem; font-weight: 700; white-space: nowrap; }

        /* ── SEARCH ── */
        .search-wrap { margin-bottom: 10px; }
        .search-wrap input { margin: 0; }

        /* ── PROGRESS BAR ── */
        .progress-wrap { display: flex; align-items: center; gap: 8px; min-width: 100px; }
        .progress-bg { flex: 1; height: 6px; border-radius: 3px; background: var(--bg2); overflow: hidden; }
        .progress-fill { height: 100%; border-radius: 3px; background: var(--main); transition: width 0.7s cubic-bezier(.4,0,.2,1); }
        .progress-fill.over { background: var(--danger); }
        .progress-pct { font-size: 0.72rem; color: var(--text-muted); min-width: 30px; text-align: right; }

        /* ── BILAN LAYOUT ── */
        .bilan-layout { display: flex; gap: 24px; align-items: flex-start; flex-wrap: wrap; }
        .bilan-table-side { flex: 2; min-width: 280px; overflow: hidden; }
        .bilan-chart-side { flex: 0 0 260px; }

        /* ── EPARGNE TOTAL ── */
        .epargne-total { display: flex; justify-content: space-between; align-items: center; margin-top: 12px; padding: 14px 16px; background: rgba(245,158,11,0.06); border: 1px solid rgba(245,158,11,0.25); border-radius: 12px; }
        .epargne-total .label { font-size: 0.85rem; color: #b45309; font-weight: 600; }
        .epargne-total .value { font-size: 1.25rem; font-weight: 700; color: #b45309; }

        /* ── ARCHIVES ── */
        .archives-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 14px; }
        .archive-card { background: var(--bg); border: 1px solid var(--bg2); border-radius: 14px; padding: 16px; }
        .arc-name { font-weight: 700; font-size: 0.9rem; margin-bottom: 2px; }
        .arc-date { font-size: 0.7rem; color: var(--text-muted); margin-bottom: 12px; }
        .arc-chart-wrap { display: flex; justify-content: center; margin-bottom: 12px; }
        .arc-stats { font-size: 0.78rem; color: var(--text-muted); }
        .arc-stat-row { display: flex; justify-content: space-between; align-items: center; padding: 4px 0; border-bottom: 1px solid var(--bg2); }
        .arc-stat-row:last-child { border-bottom: none; }
        .arc-stat-row strong { color: var(--text); font-weight: 600; }
        .arc-actions { display: flex; gap: 8px; margin-top: 12px; }
        .arc-actions .btn { flex: 1; padding: 8px 10px; font-size: 0.78rem; border-radius: 8px; min-height: 36px; }
        .btn-pdf { background: var(--main); color: white; }
        .btn-pdf:hover { background: #4a4de0; }
        .btn-del { background: var(--bg2); color: var(--text-muted); }
        .btn-del:hover { background: rgba(239,68,68,0.1); color: var(--danger); }
        .empty-state { text-align: center; padding: 48px 20px; color: var(--text-muted); }
        .empty-icon { font-size: 2.5rem; margin-bottom: 10px; }
        .empty-state p { font-size: 0.85rem; line-height: 1.6; }

        /* ── EVOLUTION CHART ── */
        #evolution-section { margin-bottom: 24px; }
        .chart-title { font-size: 0.72rem; font-weight: 700; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.07em; margin-bottom: 12px; }
        .evolution-wrap { position: relative; height: 220px; }

        /* ── THEME TOGGLE ── */
        .theme-toggle {
            width: 48px; height: 26px;
            background: var(--bg2);
            border-radius: 999px;
            border: 1.5px solid var(--card-border);
            cursor: pointer;
            position: relative;
            transition: background var(--transition);
            flex-shrink: 0;
        }
        .theme-toggle::after {
            content: '☀️';
            position: absolute; top: 1px; left: 1px;
            width: 20px; height: 20px;
            background: white;
            border-radius: 50%;
            font-size: 11px;
            display: flex; align-items: center; justify-content: center;
            transition: transform var(--transition);
            text-align: center; line-height: 20px;
        }
        [data-theme="dark"] .theme-toggle::after { content: '🌙'; transform: translateX(22px); }

        /* ── CLOSE MONTH BTN (desktop) ── */
        .btn-cloture { background: var(--bg2); color: var(--text-muted); padding: 10px 18px; border-radius: var(--radius-sm); border: none; font-family: 'DM Sans', sans-serif; font-weight: 600; font-size: 0.85rem; cursor: pointer; transition: all var(--transition); width: auto; min-height: 44px; white-space: nowrap; }
        .btn-cloture:hover { background: var(--main); color: white; }

        /* ── MODAL ── */
        .modal-overlay { position: fixed; inset: 0; background: rgba(0,0,0,0.5); backdrop-filter: blur(6px); z-index: 200; display: flex; align-items: center; justify-content: center; padding: 20px; }
        .modal-box { background: var(--card); border: 1px solid var(--card-border); border-radius: var(--radius); padding: 28px; width: 100%; max-width: 420px; box-shadow: 0 24px 64px rgba(0,0,0,0.25); }
        .modal-box h3 { font-family: 'DM Serif Display', serif; font-size: 1.3rem; margin-bottom: 8px; }
        .modal-box p { color: var(--text-muted); font-size: 0.85rem; margin-bottom: 20px; line-height: 1.6; }
        .modal-actions { display: flex; gap: 10px; margin-top: 4px; }
        .modal-actions .btn { flex: 1; margin: 0; }
        .btn-cancel { background: var(--bg2); color: var(--text-muted); }

        /* ── TOAST ── */
        #toast-container { position: fixed; top: 16px; right: 16px; z-index: 9999; display: flex; flex-direction: column; gap: 8px; pointer-events: none; max-width: calc(100vw - 32px); }
        .toast { padding: 12px 18px; border-radius: 12px; font-size: 0.85rem; font-weight: 600; color: white; box-shadow: 0 8px 24px rgba(0,0,0,0.2); display: flex; align-items: center; gap: 8px; pointer-events: auto; animation: toastIn 0.3s ease; white-space: nowrap; max-width: 360px; overflow: hidden; text-overflow: ellipsis; }
        .toast.success { background: linear-gradient(135deg, #10b981, #059669); }
        .toast.danger { background: linear-gradient(135deg, #ef4444, #dc2626); }
        .toast.info { background: linear-gradient(135deg, var(--main), #818cf8); }
        .toast.warning { background: linear-gradient(135deg, #f59e0b, #d97706); }
        @keyframes toastIn { from { opacity: 0; transform: translateX(40px); } to { opacity: 1; transform: translateX(0); } }
        @keyframes toastOut { from { opacity: 1; } to { opacity: 0; transform: translateX(40px); } }

        /* ── MOBILE FAB (clôture) ── */
        .mobile-fab {
            display: none;
            position: fixed;
            bottom: calc(var(--nav-h) + 12px);
            right: 16px;
            width: 52px; height: 52px;
            background: var(--main);
            color: white;
            border: none;
            border-radius: 50%;
            font-size: 1.4rem;
            cursor: pointer;
            box-shadow: 0 4px 20px var(--main-glow);
            z-index: 80;
            align-items: center; justify-content: center;
            transition: all var(--transition);
        }
        .mobile-fab:active { transform: scale(0.95); }

        /* ── MOBILE-ONLY STAT ROWS ── */
        .mobile-stat-row {
            display: none;
            gap: 10px;
            margin-bottom: 14px;
        }
        .mobile-stat-row .stat-box {
            flex: 1;
            padding: 12px 10px;
        }
        .mobile-stat-row .stat-value { font-size: 1.4rem; }

        /* ── RESPONSIVE ── */
        @media (max-width: 768px) {
            .desktop-header { display: none !important; }
            .mobile-header { display: flex; }
            .mobile-nav { display: block; }
            .mobile-fab { display: flex; }

            body { padding-bottom: var(--nav-h); }

            .container { padding: 12px 14px calc(var(--nav-h) + 16px); }

            /* Pages hidden by default on mobile, shown via JS */
            .page { display: none; }
            .page.active { display: block; }

            .stat-grid { display: none; }
            .mobile-stat-row { display: flex; }

            .grid-top { grid-template-columns: 1fr; gap: 14px; }

            .bilan-layout { flex-direction: column; }
            .bilan-chart-side { width: 100%; flex: none; display: flex; justify-content: center; }
            .bilan-chart-side canvas { max-width: 220px; max-height: 220px; }

            .archives-grid { grid-template-columns: 1fr; }

            .expense-grid { grid-template-columns: 1fr; }
            .expense-grid .field-full { grid-column: span 1; }

            .budget-row input { width: 80px; }

            .table-scroll { margin: 0 -14px; border-radius: 0; border-left: none; border-right: none; }

            .modal-box { border-radius: 20px 20px 0 0; position: fixed; bottom: 0; left: 0; right: 0; width: 100%; max-width: 100%; padding: 24px 20px; padding-bottom: calc(24px + env(safe-area-inset-bottom)); }
            .modal-overlay { align-items: flex-end; }

            #toast-container { top: auto; bottom: calc(var(--nav-h) + 16px); right: 12px; left: 12px; }
            .toast { max-width: 100%; }

            .card { border-radius: 14px; padding: 16px; }
        }

        @media (min-width: 769px) {
            .page { display: block !important; }
            .desktop-header { display: flex; }
        }

        @media (max-width: 480px) {
            .stat-grid { grid-template-columns: repeat(2, 1fr); }
        }
    </style>
</head>
<body>

<!-- ── TOAST CONTAINER ── -->
<div id="toast-container"></div>

<!-- ── MODAL CLOTURE ── -->
<div id="modal-cloture" class="modal-overlay" style="display:none;">
    <div class="modal-box">
        <h3>📁 Clôturer le mois</h3>
        <p>Donne un nom à ce mois pour l'archiver avec son graphique. Tu pourras le télécharger en PDF et comparer les mois.</p>
        <label>Nom du mois</label>
        <input type="text" id="modal-mois-nom" placeholder="Ex : Janvier 2025...">
        <div class="modal-actions">
            <button class="btn btn-cancel" onclick="fermerModal()">Annuler</button>
            <button class="btn btn-primary" onclick="confirmerCloture()">✅ Archiver</button>
        </div>
    </div>
</div>

<!-- ── MOBILE HEADER ── -->
<div class="mobile-header">
    <span class="mobile-header-title">💰 Mon Coach Finance</span>
    <div class="mobile-header-actions">
        <button class="theme-toggle" onclick="toggleTheme()" title="Thème"></button>
    </div>
</div>

<!-- ── MOBILE BOTTOM NAV ── -->
<nav class="mobile-nav">
    <div class="mobile-nav-inner">
        <button class="nav-btn active" id="nav-dashboard" onclick="goTo('dashboard',0)">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="3" width="7" height="7" rx="1"/><rect x="14" y="3" width="7" height="7" rx="1"/><rect x="3" y="14" width="7" height="7" rx="1"/><rect x="14" y="14" width="7" height="7" rx="1"/></svg>
            <span>Tableau</span>
        </button>
        <button class="nav-btn" id="nav-budget" onclick="goTo('budget',1)">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2v20M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"/></svg>
            <span>Budget</span>
        </button>
        <button class="nav-btn" id="nav-depenses" onclick="goTo('depenses',2)">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
            <span>Dépense</span>
        </button>
        <button class="nav-btn" id="nav-bilan" onclick="goTo('bilan',3)">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="22 12 18 12 15 21 9 3 6 12 2 12"/></svg>
            <span>Bilan</span>
        </button>
        <button class="nav-btn" id="nav-archives" onclick="goTo('archives',4)">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="21 8 21 21 3 21 3 8"/><rect x="1" y="3" width="22" height="5"/><line x1="10" y1="12" x2="14" y2="12"/></svg>
            <span>Archives</span>
        </button>
    </div>
</nav>

<!-- ── MOBILE FAB ── -->
<button class="mobile-fab" onclick="ouvrirModal()" title="Clôturer le mois">📁</button>

<!-- ── DESKTOP HEADER ── -->
<div class="desktop-header">
    <div class="header-title">
        <h1>Mon Coach <em>Finance</em></h1>
        <p>Prévu vs Réel — suivi de budget mensuel</p>
    </div>
    <div class="header-actions">
        <button class="theme-toggle" onclick="toggleTheme()" title="Changer de thème"></button>
        <button class="btn-cloture" onclick="ouvrirModal()">📁 Clôturer le mois</button>
    </div>
</div>

<div class="container">

    <!-- ── STAT GRID (desktop) ── -->
    <div class="stat-grid">
        <div class="stat-box">
            <div class="stat-label">💸 Dépensé</div>
            <div class="stat-value"><span id="view_total_dep">0</span><small> €</small></div>
        </div>
        <div class="stat-box">
            <div class="stat-label">🌱 Épargné</div>
            <div class="stat-value" style="color:var(--success)"><span id="view_total_ep">0</span><small> €</small></div>
        </div>
        <div class="stat-box">
            <div class="stat-label">⚖️ Solde</div>
            <div class="stat-value" id="view_solde_wrapper"><span id="view_solde">0</span><small> €</small></div>
        </div>
        <div class="stat-box stat-box-gold">
            <div class="stat-label">🏦 Coffre-fort</div>
            <div class="stat-value"><span id="view_global_ep">0</span><small> €</small></div>
            <button class="reset-coffre" onclick="resetCoffre()">Reset</button>
        </div>
    </div>

    <!-- ── MOBILE STAT ROWS ── -->
    <!-- Page: dashboard -->
    <div id="page-dashboard" class="page active">
        <div class="mobile-stat-row">
            <div class="stat-box">
                <div class="stat-label">💸 Dépensé</div>
                <div class="stat-value"><span id="m_dep">0</span><small> €</small></div>
            </div>
            <div class="stat-box">
                <div class="stat-label">🌱 Épargné</div>
                <div class="stat-value" style="color:var(--success)"><span id="m_ep">0</span><small> €</small></div>
            </div>
        </div>
        <div class="mobile-stat-row">
            <div class="stat-box">
                <div class="stat-label">⚖️ Solde</div>
                <div class="stat-value" id="m_solde_wrap"><span id="m_solde">0</span><small> €</small></div>
            </div>
            <div class="stat-box stat-box-gold">
                <div class="stat-label">🏦 Coffre-fort</div>
                <div class="stat-value"><span id="m_coffre">0</span><small> €</small></div>
                <button class="reset-coffre" onclick="resetCoffre()">Reset</button>
            </div>
        </div>

        <!-- Historique des dépenses -->
        <div class="card">
            <div class="card-title">🧾 Historique des dépenses</div>
            <div class="search-wrap">
                <input type="text" id="search_input" placeholder="Rechercher..." oninput="majAffichage()">
            </div>
            <div class="table-scroll">
                <table id="log_table">
                    <thead><tr><th>Date</th><th>Nom</th><th>Catégorie</th><th>Prix</th><th></th></tr></thead>
                    <tbody></tbody>
                </table>
            </div>
        </div>

        <!-- Espace Épargne -->
        <div class="card">
            <div class="card-title">🏦 Espace Épargne</div>
            <div class="table-scroll">
                <table id="epargne_history_table">
                    <thead><tr><th>Date</th><th>Nom</th><th>Montant</th><th></th></tr></thead>
                    <tbody></tbody>
                </table>
            </div>
            <div class="epargne-total">
                <span class="label">Total de cet espace</span>
                <span class="value"><span id="local_epargne_total">0</span> €</span>
            </div>
        </div>
    </div>

    <!-- Page: budget (mobile) / Section always visible on desktop -->
    <div id="page-budget" class="page">
        <div class="grid-top">
            <div class="card">
                <div class="card-title"><span class="badge">1</span> Je prévois mon mois</div>
                <label>Salaire / Revenus (€)</label>
                <input type="number" inputmode="decimal" id="prev_revenu" placeholder="Ex: 1800" onchange="sauvegarder()">
                <p style="font-size:0.78rem;color:var(--text-muted);margin-bottom:10px;font-weight:500;">Limites par catégorie :</p>
                <div id="setup_categories"></div>
                <div class="add-cat-box">
                    <input type="text" id="new_cat_name" placeholder="Nouvelle catégorie...">
                    <button class="btn-add-cat" onclick="ajouterNouvelleCategorie()">+</button>
                </div>
                <div class="plan-summary">
                    <div class="plan-row"><span>Total planifié</span> <strong id="total_prevu_val">0 €</strong></div>
                    <div class="plan-row" id="status_plan_container">
                        <span>Reste à répartir</span> <span class="text-success" id="reste_a_repartir">0 €</span>
                    </div>
                </div>
                <button class="btn btn-primary" onclick="sauvegarder()" style="margin-top:14px;">Mettre à jour</button>
            </div>

            <!-- Desktop: historique dépenses next to budget -->
            <div class="card desktop-only" id="desktop-depenses-card">
                <div class="card-title"><span class="badge">2</span> J'ajoute mes dépenses</div>
                <div class="expense-grid">
                    <div><label>Objet</label><input type="text" id="add_desc_d" placeholder="Ex: Courses Lidl"></div>
                    <div><label>Montant (€)</label><input type="number" inputmode="decimal" id="add_mt_d" placeholder="0.00"></div>
                    <div class="field-full"><label>Catégorie</label><select id="add_cat_d"></select></div>
                </div>
                <div class="recurring-row">
                    <input type="checkbox" id="add_recurring_d">
                    <label for="add_recurring_d" style="margin:0;cursor:pointer;">🔄 Dépense récurrente (conservée en fin de mois)</label>
                </div>
                <button class="btn btn-primary" onclick="ajouterDepense('d')">+ Ajouter la dépense</button>
                <div style="margin-top:16px;">
                    <div class="card-title" style="margin-top:8px;">🔎 Historique</div>
                    <div class="search-wrap">
                        <input type="text" id="search_input_d" placeholder="Rechercher..." oninput="majAffichage()">
                    </div>
                    <div class="table-scroll" style="max-height:200px;overflow-y:auto;">
                        <table id="log_table_d">
                            <thead><tr><th>Date</th><th>Nom</th><th>Cat.</th><th>Prix</th><th></th></tr></thead>
                            <tbody></tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Page: depenses (mobile only) -->
    <div id="page-depenses" class="page">
        <div class="card">
            <div class="card-title"><span class="badge">2</span> Ajouter une dépense</div>
            <div class="expense-grid">
                <div class="field-full"><label>Objet</label><input type="text" id="add_desc" placeholder="Ex: Courses Lidl"></div>
                <div><label>Montant (€)</label><input type="number" inputmode="decimal" id="add_mt" placeholder="0.00"></div>
                <div><label>Catégorie</label><select id="add_cat"></select></div>
            </div>
            <div class="recurring-row">
                <input type="checkbox" id="add_recurring">
                <label for="add_recurring" style="margin:0;cursor:pointer;">🔄 Dépense récurrente</label>
            </div>
            <button class="btn btn-primary" onclick="ajouterDepense('m')">+ Ajouter</button>
        </div>
    </div>

    <!-- Page: bilan -->
    <div id="page-bilan" class="page">
        <div class="card">
            <div class="card-title"><span class="badge">3</span> Bilan — Ai-je respecté mes engagements ?</div>
            <div class="bilan-layout">
                <div class="bilan-table-side">
                    <div class="table-scroll">
                        <table id="bilan_table">
                            <thead><tr><th>Catégorie</th><th>Prévu</th><th>Réel</th><th>Écart</th><th>%</th><th>Statut</th></tr></thead>
                            <tbody></tbody>
                        </table>
                    </div>
                </div>
                <div class="bilan-chart-side">
                    <canvas id="budgetChart" style="max-width:260px;max-height:260px;"></canvas>
                </div>
            </div>
        </div>
        <!-- Epargne on bilan page (desktop shows separately) -->
        <div class="card show-mobile-only">
            <div class="card-title">🏦 Espace Épargne (détail)</div>
            <div class="table-scroll">
                <table id="epargne_history_table_b">
                    <thead><tr><th>Date</th><th>Nom</th><th>Montant</th><th></th></tr></thead>
                    <tbody></tbody>
                </table>
            </div>
            <div class="epargne-total">
                <span class="label">Total</span>
                <span class="value"><span id="local_epargne_total_b">0</span> €</span>
            </div>
        </div>
    </div>

    <!-- Page: archives -->
    <div id="page-archives" class="page">
        <div class="card">
            <div class="card-title">📅 Mois archivés</div>
            <div id="evolution-section" style="display:none;margin-bottom:24px;">
                <div class="chart-title">📈 Évolution mois par mois</div>
                <div class="evolution-wrap"><canvas id="evolutionChart"></canvas></div>
            </div>
            <div id="archives-container"></div>
        </div>
    </div>

    <!-- Desktop-only: epargne and archives (always visible) -->
    <div class="desktop-only" id="desktop-extra">
        <div class="card">
            <div class="card-title">🏦 Espace Épargne (Suivi détaillé)</div>
            <div class="table-scroll" style="max-height:220px;overflow-y:auto;">
                <table id="epargne_history_table_desk">
                    <thead><tr><th>Date</th><th>Nom</th><th>Montant</th><th></th></tr></thead>
                    <tbody></tbody>
                </table>
            </div>
            <div class="epargne-total">
                <span class="label">Total de cet espace</span>
                <span class="value"><span id="local_epargne_total_desk">0</span> €</span>
            </div>
        </div>

        <div class="card">
            <div class="card-title">📅 Historique des mois archivés</div>
            <div id="evolution-section-desk" style="display:none;margin-bottom:24px;">
                <div class="chart-title">📈 Évolution mois par mois</div>
                <div class="evolution-wrap"><canvas id="evolutionChartDesk"></canvas></div>
            </div>
            <div id="archives-container-desk"></div>
        </div>
    </div>

</div>

<style>
    .desktop-only { display: block; }
    @media (max-width: 768px) {
        .desktop-only { display: none !important; }
        .show-mobile-only { display: block; }
        /* On desktop, hide the mobile-only epargne on bilan */
    }
    @media (min-width: 769px) {
        .show-mobile-only { display: none !important; }
        #page-dashboard, #page-budget, #page-bilan, #page-archives { display: block !important; }
        #page-depenses { display: none !important; }
        /* show desktop depenses inside budget grid */
        #desktop-depenses-card { display: block !important; }
    }
</style>

<script>
    /* ── DATA ── */
    let db = JSON.parse(localStorage.getItem('budget_vGestion')) || {
        revenu: 0,
        categories: [
            { id: "Fixe", label: "Loyers/Charges" },
            { id: "Courses", label: "Alimentation" },
            { id: "Loisirs", label: "Sorties/Plaisirs" },
            { id: "Epargne", label: "Épargne" },
            { id: "Autres", label: "Divers" }
        ],
        previsions: { Fixe: 0, Courses: 0, Loisirs: 0, Epargne: 0, Autres: 0 },
        depenses: [],
        historiqueEpargne: []
    };

    let globalSavings = parseFloat(localStorage.getItem('globalSavings')) || 0;
    let archives = JSON.parse(localStorage.getItem('budget_archives')) || [];
    let chartInstance = null;
    let evolutionChartInstance = null;
    let evolutionChartInstanceDesk = null;
    const colors = ['#5b5ef4','#10b981','#f59e0b','#ef4444','#94a3b8','#06b6d4','#a855f7','#f97316'];

    /* ── THEME ── */
    const savedTheme = localStorage.getItem('theme') || 'light';
    document.documentElement.setAttribute('data-theme', savedTheme);
    function toggleTheme() {
        const next = document.documentElement.getAttribute('data-theme') === 'light' ? 'dark' : 'light';
        document.documentElement.setAttribute('data-theme', next);
        localStorage.setItem('theme', next);
        majAffichage();
        afficherEvolution();
    }

    /* ── MOBILE NAV ── */
    const pages = ['dashboard', 'budget', 'depenses', 'bilan', 'archives'];
    function goTo(page, idx) {
        pages.forEach(p => {
            const el = document.getElementById('page-' + p);
            if (el) el.classList.remove('active');
            const btn = document.getElementById('nav-' + p);
            if (btn) btn.classList.remove('active');
        });
        const el = document.getElementById('page-' + page);
        if (el) el.classList.add('active');
        const btn = document.getElementById('nav-' + page);
        if (btn) btn.classList.add('active');
        window.scrollTo(0, 0);
    }

    /* ── TOAST ── */
    function showToast(msg, type = 'success', duration = 3000) {
        const icons = { success: '✅', danger: '❌', info: 'ℹ️', warning: '⚠️' };
        const container = document.getElementById('toast-container');
        const toast = document.createElement('div');
        toast.className = `toast ${type}`;
        toast.innerHTML = `<span>${icons[type]||'📢'}</span> ${msg}`;
        container.appendChild(toast);
        setTimeout(() => { toast.style.animation = 'toastOut 0.3s ease both'; setTimeout(() => toast.remove(), 300); }, duration);
    }

    /* ── MODAL ── */
    function ouvrirModal() {
        const now = new Date();
        const moisNoms = ['Janvier','Février','Mars','Avril','Mai','Juin','Juillet','Août','Septembre','Octobre','Novembre','Décembre'];
        document.getElementById('modal-mois-nom').value = `${moisNoms[now.getMonth()]} ${now.getFullYear()}`;
        document.getElementById('modal-cloture').style.display = 'flex';
        setTimeout(() => document.getElementById('modal-mois-nom').focus(), 100);
    }
    function fermerModal() { document.getElementById('modal-cloture').style.display = 'none'; }
    document.getElementById('modal-cloture').addEventListener('click', e => { if (e.target === e.currentTarget) fermerModal(); });
    document.getElementById('modal-mois-nom').addEventListener('keydown', e => {
        if (e.key === 'Enter') confirmerCloture();
        if (e.key === 'Escape') fermerModal();
    });

    function confirmerCloture() {
        const nom = document.getElementById('modal-mois-nom').value.trim() || 'Mois sans nom';
        fermerModal();
        let totaux = {};
        db.categories.forEach(c => totaux[c.id] = 0);
        let totalDep = 0, totalEp = 0;
        db.depenses.forEach(d => {
            if (totaux.hasOwnProperty(d.ct)) totaux[d.ct] += d.mt;
            const cat = db.categories.find(c => c.id === d.ct);
            if (cat && cat.label.toLowerCase().includes("épargne")) totalEp += d.mt;
            else totalDep += d.mt;
        });
        const archive = {
            id: Date.now(), nom, date: new Date().toLocaleDateString('fr-FR'),
            revenu: db.revenu, totalDep, totalEp,
            solde: db.revenu - totalDep - totalEp,
            labels: db.categories.map(c => c.label),
            data: db.categories.map(c => totaux[c.id] || 0)
        };
        archives.push(archive);
        localStorage.setItem('budget_archives', JSON.stringify(archives));
        let epargneMois = 0;
        db.depenses.forEach(d => {
            const cat = db.categories.find(c => c.id == d.ct);
            if (cat && cat.label.toLowerCase().includes("épargne")) epargneMois += d.mt;
        });
        globalSavings += epargneMois;
        localStorage.setItem('globalSavings', globalSavings);
        db.depenses = db.depenses.filter(d => d.recurring === true);
        sauvegarder();
        afficherArchives();
        afficherEvolution();
        showToast(`"${nom}" archivé ! +${epargneMois}€ au coffre-fort 🎉`, 'success', 4000);
    }

    /* ── ARCHIVES ── */
    function buildArchiveCard(arc) {
        const card = document.createElement('div');
        card.className = 'archive-card';
        const soldeColor = arc.solde < 0 ? 'var(--danger)' : 'var(--success)';
        card.innerHTML = `
            <div class="arc-name">${arc.nom}</div>
            <div class="arc-date">Archivé le ${arc.date}</div>
            <div class="arc-chart-wrap"><canvas id="arc-chart-${arc.id}" width="130" height="130"></canvas></div>
            <div class="arc-stats">
                <div class="arc-stat-row"><span>💸 Dépensé</span><strong>${arc.totalDep} €</strong></div>
                <div class="arc-stat-row"><span>🌱 Épargné</span><strong style="color:var(--success)">${arc.totalEp} €</strong></div>
                <div class="arc-stat-row"><span>⚖️ Solde</span><strong style="color:${soldeColor}">${arc.solde} €</strong></div>
                <div class="arc-stat-row"><span>📥 Revenus</span><strong>${arc.revenu} €</strong></div>
            </div>
            <div class="arc-actions">
                <button class="btn btn-pdf" onclick="telechargerPDF(${arc.id})">📄 PDF</button>
                <button class="btn btn-del" onclick="supprimerArchive(${arc.id})">🗑️</button>
            </div>`;
        return card;
    }

    function renderArchiveCharts() {
        archives.slice().reverse().forEach(arc => {
            setTimeout(() => {
                const ctx = document.getElementById(`arc-chart-${arc.id}`);
                if (!ctx || ctx._chartDone) return;
                ctx._chartDone = true;
                new Chart(ctx, {
                    type: 'pie',
                    data: { labels: arc.labels, datasets: [{ data: arc.data, backgroundColor: colors.slice(0, arc.labels.length), borderWidth: 2, borderColor: '#ffffff', hoverOffset: 4 }] },
                    options: { responsive: false, plugins: { legend: { display: false }, tooltip: { callbacks: { label: c => ` ${c.label}: ${c.parsed}€` } } }, animation: { duration: 600 } }
                });
            }, 80);
        });
    }

    function afficherArchives() {
        const containers = ['archives-container', 'archives-container-desk'].map(id => document.getElementById(id)).filter(Boolean);
        if (archives.length === 0) {
            const html = `<div class="empty-state"><div class="empty-icon">📭</div><p>Aucun mois archivé.<br>Clôture ton premier mois pour le voir ici.</p></div>`;
            containers.forEach(c => c.innerHTML = html);
            return;
        }
        containers.forEach(c => {
            c.innerHTML = '<div class="archives-grid"></div>';
            const grid = c.querySelector('.archives-grid');
            archives.slice().reverse().forEach(arc => grid.appendChild(buildArchiveCard(arc)));
        });
        renderArchiveCharts();
    }

    function buildEvolutionChart(canvasId) {
        const section = document.getElementById(canvasId === 'evolutionChart' ? 'evolution-section' : 'evolution-section-desk');
        if (!section) return;
        if (archives.length < 1) { section.style.display = 'none'; return; }
        section.style.display = 'block';
        const sorted = [...archives].sort((a, b) => a.id - b.id);
        const isDark = document.documentElement.getAttribute('data-theme') === 'dark';
        const gridColor = isDark ? 'rgba(255,255,255,0.06)' : 'rgba(0,0,0,0.05)';
        const textColor = isDark ? '#9ca3af' : '#6b7280';
        const ctx = document.getElementById(canvasId);
        if (!ctx) return;
        const existing = canvasId === 'evolutionChart' ? evolutionChartInstance : evolutionChartInstanceDesk;
        if (existing) existing.destroy();
        const inst = new Chart(ctx, {
            type: 'line',
            data: {
                labels: sorted.map(a => a.nom),
                datasets: [
                    { label: 'Revenus', data: sorted.map(a => a.revenu), borderColor: '#5b5ef4', borderWidth: 2.5, pointBackgroundColor: '#5b5ef4', pointRadius: 4, fill: false, tension: 0.35 },
                    { label: 'Dépenses', data: sorted.map(a => a.totalDep), borderColor: '#ef4444', borderWidth: 2.5, pointBackgroundColor: '#ef4444', pointRadius: 4, fill: false, tension: 0.35 },
                    { label: 'Épargne', data: sorted.map(a => a.totalEp), borderColor: '#10b981', borderWidth: 2.5, pointBackgroundColor: '#10b981', pointRadius: 4, fill: false, tension: 0.35 },
                    { label: 'Solde', data: sorted.map(a => a.solde), borderColor: '#f59e0b', borderWidth: 2, borderDash: [5,3], pointBackgroundColor: '#f59e0b', pointRadius: 3, fill: false, tension: 0.35 }
                ]
            },
            options: {
                responsive: true, maintainAspectRatio: false,
                interaction: { mode: 'index', intersect: false },
                plugins: {
                    legend: { position: 'top', labels: { color: textColor, font: { family: 'DM Sans', size: 11 }, padding: 14, usePointStyle: true, pointStyleWidth: 7 } },
                    tooltip: { backgroundColor: isDark ? '#1c1e2b' : '#fff', titleColor: isDark ? '#e8eaf2' : '#1a1d2e', bodyColor: textColor, borderColor: isDark ? 'rgba(255,255,255,0.1)' : '#e5e7eb', borderWidth: 1, padding: 10, callbacks: { label: c => ` ${c.dataset.label} : ${c.parsed.y} €` } }
                },
                scales: {
                    x: { ticks: { color: textColor, font: { family: 'DM Sans', size: 10 } }, grid: { color: gridColor } },
                    y: { ticks: { color: textColor, font: { family: 'DM Sans', size: 10 }, callback: v => v + ' €' }, grid: { color: gridColor } }
                },
                animation: { duration: 700 }
            }
        });
        if (canvasId === 'evolutionChart') evolutionChartInstance = inst;
        else evolutionChartInstanceDesk = inst;
    }

    function afficherEvolution() {
        buildEvolutionChart('evolutionChart');
        buildEvolutionChart('evolutionChartDesk');
    }

    function supprimerArchive(id) {
        if (!confirm("Supprimer cette archive ?")) return;
        archives = archives.filter(a => a.id !== id);
        localStorage.setItem('budget_archives', JSON.stringify(archives));
        afficherArchives();
        afficherEvolution();
        showToast('Archive supprimée', 'warning');
    }

    function telechargerPDF(id) {
        const arc = archives.find(a => a.id === id);
        if (!arc) return;
        const chartCanvas = document.getElementById(`arc-chart-${arc.id}`);
        const chartImg = chartCanvas ? chartCanvas.toDataURL('image/png') : '';
        const soldeColor = arc.solde < 0 ? '#ef4444' : '#10b981';
        const legendRows = arc.labels.map((l, i) => `<div style="display:flex;align-items:center;gap:8px;margin-bottom:6px;"><span style="display:inline-block;width:12px;height:12px;border-radius:50%;background:${colors[i%colors.length]};flex-shrink:0;"></span><span style="flex:1;">${l}</span><strong>${arc.data[i]} €</strong></div>`).join('');
        const html = `<!DOCTYPE html><html lang="fr"><head><meta charset="UTF-8"><title>Bilan ${arc.nom}</title><style>@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;600;700&display=swap');*{box-sizing:border-box;margin:0;padding:0;}body{font-family:'DM Sans',Arial,sans-serif;background:white;color:#1a1d2e;padding:48px 40px;max-width:620px;margin:auto;}.header{border-bottom:3px solid #5b5ef4;padding-bottom:18px;margin-bottom:28px;}.title{font-size:1.7rem;font-weight:700;color:#5b5ef4;margin-bottom:4px;}.sub{color:#6b7280;font-size:0.85rem;}.chart-section{display:flex;gap:32px;align-items:center;margin-bottom:28px;}.chart-section img{width:160px;height:160px;}.legend{flex:1;font-size:0.85rem;}.stats-grid{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:28px;}.stat{background:#f9fafb;border:1px solid #e5e7eb;border-radius:12px;padding:16px;text-align:center;}.stat .lbl{font-size:0.7rem;color:#6b7280;text-transform:uppercase;letter-spacing:0.08em;margin-bottom:6px;}.stat .val{font-size:1.6rem;font-weight:700;}.footer{margin-top:32px;font-size:0.72rem;color:#9ca3af;text-align:center;border-top:1px solid #e5e7eb;padding-top:16px;}@media print{body{padding:20px;}}</style></head><body><div class="header"><div class="title">📊 ${arc.nom}</div><div class="sub">Archivé le ${arc.date} · Mon Coach Finance</div></div><div class="chart-section">${chartImg?`<img src="${chartImg}">`:''}<div class="legend">${legendRows}</div></div><div class="stats-grid"><div class="stat"><div class="lbl">💸 Dépensé</div><div class="val">${arc.totalDep} €</div></div><div class="stat"><div class="lbl">🌱 Épargné</div><div class="val" style="color:#10b981">${arc.totalEp} €</div></div><div class="stat"><div class="lbl">⚖️ Solde</div><div class="val" style="color:${soldeColor}">${arc.solde} €</div></div><div class="stat"><div class="lbl">📥 Revenus</div><div class="val">${arc.revenu} €</div></div></div><div class="footer">Généré par Mon Coach Finance</div></body></html>`;
        const blob = new Blob([html], { type: 'text/html' });
        const url = URL.createObjectURL(blob);
        const win = window.open(url, '_blank');
        if (win) win.addEventListener('load', () => setTimeout(() => win.print(), 500));
        showToast('PDF prêt — utilise "Enregistrer en PDF"', 'info', 4000);
    }

    /* ── CATEGORIES ── */
    function ajouterNouvelleCategorie() {
        const input = document.getElementById('new_cat_name');
        const name = input.value.trim();
        if (!name) return;
        const newId = "cat_" + Date.now();
        db.categories.push({ id: newId, label: name });
        db.previsions[newId] = 0;
        input.value = "";
        sauvegarder();
        showToast(`Catégorie "${name}" ajoutée`, 'info');
    }
    function supprimerCategorie(id) {
        const cat = db.categories.find(c => c.id === id);
        if (confirm(`Supprimer "${cat ? cat.label : ''}" ?`)) {
            db.categories = db.categories.filter(c => c.id !== id);
            delete db.previsions[id];
            sauvegarder();
            showToast('Catégorie supprimée', 'warning');
        }
    }

    /* ── DEPENSES ── */
    function ajouterDepense(source) {
        // source: 'm' = mobile form, 'd' = desktop form
        const sfx = source === 'd' ? '_d' : '';
        const desc = document.getElementById('add_desc' + sfx).value;
        const mt = parseFloat(document.getElementById('add_mt' + sfx).value);
        const ctId = document.getElementById('add_cat' + sfx).value;
        const isRecurring = document.getElementById('add_recurring' + sfx).checked;
        if (!desc || isNaN(mt) || mt <= 0) { showToast('Remplis tous les champs', 'warning'); return; }
        const expense = { id: Date.now(), date: new Date().toLocaleDateString('fr-FR'), desc, mt, ct: ctId, recurring: isRecurring };
        db.depenses.push(expense);
        const catObj = db.categories.find(c => c.id === ctId);
        if (catObj && catObj.label.toLowerCase().includes("épargne")) db.historiqueEpargne.push(expense);
        document.getElementById('add_desc' + sfx).value = '';
        document.getElementById('add_mt' + sfx).value = '';
        document.getElementById('add_recurring' + sfx).checked = false;
        sauvegarder();
        showToast(`${desc} — ${mt}€ ajouté${isRecurring ? ' 🔄' : ''}`, 'success');
    }

    function supprimer(id) {
        const idx = db.historiqueEpargne.findIndex(d => d.id === id);
        if (idx !== -1) {
            globalSavings = Math.max(0, globalSavings - db.historiqueEpargne[idx].mt);
            localStorage.setItem('globalSavings', globalSavings);
            db.historiqueEpargne.splice(idx, 1);
        }
        db.depenses = db.depenses.filter(d => d.id !== id);
        sauvegarder();
        showToast('Dépense supprimée', 'danger');
    }

    function resetCoffre() {
        if (confirm("Vider tout le coffre-fort ET l'historique d'épargne ?")) {
            globalSavings = 0;
            db.historiqueEpargne = [];
            localStorage.setItem('globalSavings', 0);
            sauvegarder();
            showToast('Coffre-fort vidé', 'warning');
        }
    }

    /* ── SAVE ── */
    function sauvegarder() {
        db.revenu = parseFloat(document.getElementById('prev_revenu').value) || 0;
        document.querySelectorAll('.prev-input').forEach(input => {
            db.previsions[input.dataset.cat] = parseFloat(input.value) || 0;
        });
        localStorage.setItem('budget_vGestion', JSON.stringify(db));
        majAffichage();
    }

    /* ── ANIMATE VALUE ── */
    let prevStats = { dep: 0, ep: 0, solde: 0, coffre: 0 };
    function animateValue(el, from, to, duration = 500) {
        if (!el) return;
        const start = performance.now();
        const update = now => {
            const p = Math.min((now - start) / duration, 1);
            const e = 1 - Math.pow(1 - p, 3);
            el.innerText = Math.round(from + (to - from) * e);
            if (p < 1) requestAnimationFrame(update);
        };
        requestAnimationFrame(update);
    }

    /* ── MAIN DISPLAY ── */
    function majAffichage() {
        const isMobile = window.innerWidth <= 768;
        const searchInput = isMobile ? document.getElementById('search_input') : document.getElementById('search_input_d');
        const searchTerm = (searchInput ? searchInput.value : '').toLowerCase();

        /* Épargne table */
        db.historiqueEpargne.sort((a, b) => a.desc.toLowerCase().localeCompare(b.desc.toLowerCase()));
        const renderEpargne = (tbodyId, totalId) => {
            const tbody = document.querySelector(`#${tbodyId} tbody`);
            if (!tbody) return 0;
            tbody.innerHTML = '';
            let total = 0;
            db.historiqueEpargne.forEach(d => {
                tbody.innerHTML += `<tr><td style="color:var(--text-muted);font-size:0.78rem">${d.date}</td><td>${d.desc}${d.recurring ? '<span class="recurring-tag">🔄</span>' : ''}</td><td><strong>${d.mt}€</strong></td><td><button class="btn-delete" onclick="supprimer(${d.id})">✕</button></td></tr>`;
                total += d.mt;
            });
            const el = document.getElementById(totalId);
            if (el) el.innerText = total.toFixed(0);
            return total;
        };
        renderEpargne('epargne_history_table', 'local_epargne_total');
        renderEpargne('epargne_history_table_b', 'local_epargne_total_b');
        renderEpargne('epargne_history_table_desk', 'local_epargne_total_desk');

        /* Categories setup */
        const setupDiv = document.getElementById('setup_categories');
        setupDiv.innerHTML = "";
        let totalPlanifie = 0;

        const populateSelect = (selectId) => {
            const sel = document.getElementById(selectId);
            if (!sel) return;
            sel.innerHTML = "";
            db.categories.forEach(cat => { sel.innerHTML += `<option value="${cat.id}">${cat.label}</option>`; });
        };
        populateSelect('add_cat'); populateSelect('add_cat_d');

        db.categories.forEach(cat => {
            const val = db.previsions[cat.id] || 0;
            totalPlanifie += val;
            setupDiv.innerHTML += `<div class="budget-row">
                <button class="btn-icon-sm" onclick="supprimerCategorie('${cat.id}')">✕</button>
                <span class="cat-label">${cat.label}</span>
                <input type="number" inputmode="decimal" class="prev-input" data-cat="${cat.id}" value="${val}" onchange="sauvegarder()" style="width:90px;margin:0;">
            </div>`;
        });

        document.getElementById('total_prevu_val').innerText = totalPlanifie.toFixed(0) + " €";
        const reste = db.revenu - totalPlanifie;
        const statusCont = document.getElementById('status_plan_container');
        statusCont.innerHTML = reste < 0
            ? `<span>Dépassement</span> <span class="text-danger">${Math.abs(reste).toFixed(0)} €</span>`
            : `<span>Reste à répartir</span> <span class="text-success">${reste.toFixed(0)} €</span>`;
        document.getElementById('prev_revenu').value = db.revenu;

        /* Calculs */
        let totaux = {};
        db.categories.forEach(c => totaux[c.id] = 0);
        let totalGeneral = 0, totalEpargne = 0;

        const renderLog = (tbodyId) => {
            const tbody = document.querySelector(`#${tbodyId} tbody`);
            if (!tbody) return;
            tbody.innerHTML = '';
            [...db.depenses].reverse().forEach(d => {
                if (totaux.hasOwnProperty(d.ct)) totaux[d.ct] += d.mt;
                const catObj = db.categories.find(c => c.id === d.ct);
                const catLabel = catObj ? catObj.label.toLowerCase() : '';
                if (d.desc.toLowerCase().includes(searchTerm) || catLabel.includes(searchTerm)) {
                    tbody.innerHTML += `<tr>
                        <td style="color:var(--text-muted);font-size:0.78rem;white-space:nowrap">${d.date}</td>
                        <td>${d.desc}${d.recurring ? '<span class="recurring-tag">🔄</span>' : ''}</td>
                        <td><span class="cat-pill">${catObj ? catObj.label : 'N/A'}</span></td>
                        <td><strong>${d.mt}€</strong></td>
                        <td><button class="btn-delete" onclick="supprimer(${d.id})">✕</button></td>
                    </tr>`;
                }
            });
        };

        // Reset totaux before rendering
        db.categories.forEach(c => totaux[c.id] = 0);
        db.depenses.forEach(d => {
            if (totaux.hasOwnProperty(d.ct)) totaux[d.ct] += d.mt;
            const catObj = db.categories.find(c => c.id === d.ct);
            if (catObj && catObj.label.toLowerCase().includes("épargne")) totalEpargne += d.mt;
            else totalGeneral += d.mt;
        });

        renderLog('log_table');
        renderLog('log_table_d');

        const solde = db.revenu - totalGeneral - totalEpargne;

        /* Stats */
        const setVal = (id, val) => { const el = document.getElementById(id); if (el) el.innerText = Math.round(val); };
        animateValue(document.getElementById('view_total_dep'), prevStats.dep, totalGeneral);
        animateValue(document.getElementById('view_total_ep'), prevStats.ep, totalEpargne);
        animateValue(document.getElementById('view_solde'), prevStats.solde, solde);
        animateValue(document.getElementById('view_global_ep'), prevStats.coffre, globalSavings);
        animateValue(document.getElementById('m_dep'), prevStats.dep, totalGeneral);
        animateValue(document.getElementById('m_ep'), prevStats.ep, totalEpargne);
        animateValue(document.getElementById('m_solde'), prevStats.solde, solde);
        animateValue(document.getElementById('m_coffre'), prevStats.coffre, globalSavings);
        prevStats = { dep: totalGeneral, ep: totalEpargne, solde, coffre: globalSavings };

        const soldeColor = solde < 0 ? 'var(--danger)' : 'var(--success)';
        ['view_solde_wrapper','m_solde_wrap'].forEach(id => { const el = document.getElementById(id); if (el) el.style.color = soldeColor; });

        /* Bilan table */
        const bilanBody = document.querySelector('#bilan_table tbody');
        bilanBody.innerHTML = '';
        let labelsChart = [], dataChart = [];
        db.categories.forEach((cat) => {
            const prev = db.previsions[cat.id] || 0;
            const reel = totaux[cat.id] || 0;
            const pct = prev > 0 ? Math.min((reel / prev) * 100, 100) : 0;
            const over = reel > prev;
            const ecart = prev - reel;
            bilanBody.innerHTML += `<tr style="${over ? 'background:rgba(239,68,68,0.03)' : ''}">
                <td style="font-weight:600;white-space:nowrap">${cat.label}</td>
                <td style="color:var(--text-muted);white-space:nowrap">${prev} €</td>
                <td style="font-weight:700;white-space:nowrap">${reel} €</td>
                <td style="color:${ecart<0?'var(--danger)':'var(--success)'};font-weight:700;white-space:nowrap">${ecart>=0?'+':''}${ecart.toFixed(0)} €</td>
                <td>
                    <div class="progress-wrap">
                        <div class="progress-bg"><div class="progress-fill ${over?'over':''}" style="width:${pct}%"></div></div>
                        <span class="progress-pct">${pct.toFixed(0)}%</span>
                    </div>
                </td>
                <td>${over ? '<span class="status-over">⚠ Dépassé</span>' : '<span class="status-ok">✓ OK</span>'}</td>
            </tr>`;
            labelsChart.push(cat.label);
            dataChart.push(reel);
        });

        /* Pie chart */
        if (chartInstance) chartInstance.destroy();
        const isDark = document.documentElement.getAttribute('data-theme') === 'dark';
        const ctx = document.getElementById('budgetChart');
        if (ctx) {
            chartInstance = new Chart(ctx, {
                type: 'pie',
                data: { labels: labelsChart, datasets: [{ data: dataChart, backgroundColor: colors.slice(0, labelsChart.length), borderWidth: 3, borderColor: isDark ? '#1c1e2b' : '#ffffff', hoverOffset: 6 }] },
                options: {
                    responsive: true, maintainAspectRatio: true, aspectRatio: 1,
                    plugins: {
                        legend: { position: 'bottom', labels: { color: isDark ? '#9ca3af' : '#6b7280', font: { family: 'DM Sans', size: 11 }, padding: 10, usePointStyle: true, pointStyleWidth: 7 } },
                        tooltip: { callbacks: { label: c => ` ${c.label}: ${c.parsed}€` } }
                    },
                    animation: { animateRotate: true, duration: 700 }
                }
            });
        }
    }

    /* ── ENTER KEY SHORTCUTS ── */
    document.getElementById('new_cat_name').addEventListener('keydown', e => { if (e.key === 'Enter') ajouterNouvelleCategorie(); });
    document.addEventListener('keydown', e => {
        if (e.key === 'Enter') {
            const active = document.querySelector('.nav-btn.active');
            if (active && active.id === 'nav-depenses') ajouterDepense('m');
        }
    });

    /* ── INIT ── */
    majAffichage();
    afficherArchives();
    afficherEvolution();
</script>
</body>
</html>
