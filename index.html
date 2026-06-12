<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hub Révisions — CCA</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Clash+Display:wght@400;500;600;700&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --sidebar-w: 280px;
            --bg:        #0f0e17;
            --bg2:       #161522;
            --bg3:       #1e1c2e;
            --border:    rgba(255,255,255,.07);
            --pink:      #ff6b9d;
            --violet:    #a855f7;
            --cyan:      #06d6d6;
            --yellow:    #ffd166;
            --green:     #06d6a0;
            --orange:    #ff9f1c;
            --text:      #c4c0d8;
            --white:     #f5f3ff;
            --muted:     #5a5670;
            --danger:    #ff5c7a;
            --grad1: linear-gradient(135deg, #ff6b9d, #a855f7);
            --grad2: linear-gradient(135deg, #06d6d6, #a855f7);
            --grad3: linear-gradient(135deg, #ffd166, #ff6b9d);
        }

        /* ── THÈME CLAIR ── */
        body.light-theme {
            --bg:        #f5f4fa;
            --bg2:       #ffffff;
            --bg3:       #f0eef8;
            --border:    rgba(15,14,23,.08);
            --text:      #4a4760;
            --white:     #1a1825;
            --muted:     #9b97b5;
        }
        body.light-theme .toast { background: var(--bg2); }
        body.light-theme .login-card { background: rgba(255,255,255,.9); border-color: rgba(15,14,23,.08); }
        body.light-theme .login-blob { opacity: .12; }
        body.light-theme .code-input { background: rgba(15,14,23,.03); border-color: rgba(15,14,23,.1); color: var(--white); }
        body.light-theme .code-input:focus { background: rgba(168,85,247,.04); }
        body.light-theme nav::before { opacity: .5; }
        body.light-theme .topbar { background: rgba(255,255,255,.92); }
        body.light-theme .welcome::before { opacity: .5; }
        body.light-theme .search-input { color: var(--white); }
        body.light-theme .notes-editor i, body.light-theme .notes-editor em { color: #0891a8; }
        body.light-theme ::-webkit-scrollbar-thumb { background: rgba(15,14,23,.15); }
        #btn-theme:hover { background: rgba(255,209,102,.2) !important; border-color: rgba(255,209,102,.4) !important; transform: translateY(-1px); }
        body.light-theme #btn-theme { background: rgba(255,159,28,.12) !important; border-color: rgba(255,159,28,.3) !important; color: #b5650a !important; }
        body.light-theme #btn-theme:hover { background: rgba(255,159,28,.22) !important; }

        *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

        body {
            display: flex; height: 100vh;
            font-family: 'Plus Jakarta Sans', sans-serif;
            background: var(--bg); color: var(--text);
            overflow: hidden;
        }

        /* LOGIN */
        #login-screen {
            display: flex; align-items: center; justify-content: center;
            position: fixed; inset: 0; z-index: 999;
            background: var(--bg); padding: 24px;
        }

        .login-bg { position: absolute; inset: 0; overflow: hidden; pointer-events: none; }

        .login-blob {
            position: absolute; border-radius: 50%; filter: blur(80px); opacity: .25;
            animation: blobFloat 8s ease-in-out infinite;
        }

        .blob1 { width: 500px; height: 500px; background: var(--violet); top: -100px; left: -100px; }
        .blob2 { width: 400px; height: 400px; background: var(--pink); bottom: -80px; right: -80px; animation-delay: -3s; }
        .blob3 { width: 300px; height: 300px; background: var(--cyan); top: 50%; left: 50%; transform: translate(-50%,-50%); animation-delay: -6s; }

        @keyframes blobFloat {
            0%,100% { transform: translate(0,0) scale(1); }
            33% { transform: translate(20px,-20px) scale(1.05); }
            66% { transform: translate(-15px,15px) scale(.95); }
        }

        .blob3 { animation: blobFloat3 8s ease-in-out infinite; animation-delay: -6s; }
        @keyframes blobFloat3 {
            0%,100% { transform: translate(-50%,-50%) scale(1); }
            33% { transform: translate(calc(-50% + 20px),calc(-50% - 20px)) scale(1.05); }
            66% { transform: translate(calc(-50% - 15px),calc(-50% + 15px)) scale(.95); }
        }

        .login-card {
            background: rgba(22,21,34,.85);
            border: 1px solid rgba(255,255,255,.1);
            border-radius: 28px; padding: 48px 44px;
            width: 100%; max-width: 440px;
            position: relative; z-index: 1;
            backdrop-filter: blur(20px);
            animation: cardIn .6s cubic-bezier(.34,1.56,.64,1);
            box-shadow: 0 40px 80px rgba(0,0,0,.5);
        }

        @keyframes cardIn {
            from { opacity:0; transform: translateY(30px) scale(.95); }
            to   { opacity:1; transform: translateY(0) scale(1); }
        }

        .login-logo { display: flex; align-items: center; gap: 14px; margin-bottom: 36px; }

        .login-logo-icon {
            width: 52px; height: 52px; border-radius: 16px;
            background: var(--grad1);
            display: grid; place-items: center; font-size: 24px;
            box-shadow: 0 8px 24px rgba(168,85,247,.4);
        }

        .login-logo-text {
            font-family: 'Clash Display', sans-serif;
            font-size: 1.2rem; font-weight: 700; color: var(--white); line-height: 1.1;
        }

        .login-logo-sub {
            font-size: .65rem; color: var(--muted);
            letter-spacing: 2px; text-transform: uppercase; margin-top: 3px;
        }

        .login-title {
            font-family: 'Clash Display', sans-serif;
            font-size: 1.8rem; font-weight: 700; color: var(--white);
            margin-bottom: 8px; line-height: 1.1;
        }

        .login-title span {
            background: var(--grad1); -webkit-background-clip: text;
            -webkit-text-fill-color: transparent; background-clip: text;
        }

        .login-sub { font-size: .84rem; color: var(--muted); margin-bottom: 36px; line-height: 1.6; }

        .input-label {
            display: block; font-size: .68rem; color: var(--muted);
            letter-spacing: 1.5px; text-transform: uppercase; margin-bottom: 10px; font-weight: 600;
        }

        .code-input {
            width: 100%; background: rgba(255,255,255,.05);
            border: 1.5px solid rgba(255,255,255,.1);
            border-radius: 14px; padding: 16px 20px;
            font-family: 'Clash Display', sans-serif; font-size: 1.2rem; font-weight: 600;
            color: var(--white); letter-spacing: 4px; text-align: center;
            text-transform: uppercase; outline: none;
            transition: border-color .25s, box-shadow .25s, background .25s;
        }

        .code-input:focus {
            border-color: var(--violet);
            box-shadow: 0 0 0 4px rgba(168,85,247,.15);
            background: rgba(168,85,247,.08);
        }

        .code-input.error {
            border-color: var(--danger);
            box-shadow: 0 0 0 4px rgba(255,92,122,.12);
            animation: shake .35s ease;
        }

        @keyframes shake {
            0%,100%{transform:translateX(0)} 20%{transform:translateX(-8px)} 60%{transform:translateX(8px)}
        }

        .btn-login {
            width: 100%; border: none; border-radius: 14px;
            padding: 16px; margin-top: 16px;
            font-family: 'Clash Display', sans-serif; font-size: 1rem; font-weight: 600;
            color: #fff; cursor: pointer; letter-spacing: .5px;
            background: var(--grad1);
            box-shadow: 0 8px 32px rgba(168,85,247,.35);
            transition: transform .15s, box-shadow .15s;
            position: relative; overflow: hidden;
        }

        .btn-login:hover { transform: translateY(-2px); box-shadow: 0 12px 40px rgba(168,85,247,.45); }
        .btn-login:active { transform: scale(.98); }
        .btn-login:disabled { opacity: .6; cursor: not-allowed; transform: none; }

        .login-error {
            display: none; align-items: center; gap: 8px;
            background: rgba(255,92,122,.08); border: 1px solid rgba(255,92,122,.2);
            border-radius: 10px; padding: 10px 14px;
            font-size: .78rem; color: var(--danger); margin-top: 12px;
        }

        .login-error.visible { display: flex; }

        .login-footer {
            margin-top: 28px; padding-top: 20px; border-top: 1px solid var(--border);
            font-size: .68rem; color: var(--muted); text-align: center; line-height: 1.6;
        }
        }

        .last-session {
            display: none; align-items: center; gap: 10px;
            background: rgba(168,85,247,.08); border: 1px solid rgba(168,85,247,.18);
            border-radius: 14px; padding: 12px 16px; margin-top: 14px;
            cursor: pointer; transition: background .2s, border-color .2s;
            animation: cardIn .4s cubic-bezier(.34,1.56,.64,1);
        }
        .last-session:hover { background: rgba(168,85,247,.15); border-color: rgba(168,85,247,.35); }
        .last-session.visible { display: flex; }
        .last-session-avatar {
            width: 36px; height: 36px; border-radius: 10px; flex-shrink: 0;
            background: var(--grad1); display: grid; place-items: center;
            font-size: 15px; font-weight: 700; color: #fff;
        }
        .last-session-info { flex: 1; text-align: left; }
        .last-session-name { font-size: .82rem; font-weight: 600; color: var(--white); }
        .last-session-hint { font-size: .68rem; color: var(--muted); margin-top: 2px; }
        .last-session-arrow { color: var(--violet); font-size: 1rem; }

        .spinner {
            display: inline-block; width: 16px; height: 16px;
            border: 2px solid rgba(255,255,255,.3); border-top-color: #fff;
            border-radius: 50%; animation: spin .6s linear infinite; vertical-align: middle;
        }

        @keyframes spin { to { transform: rotate(360deg); } }

        /* HUB */
        #hub-screen { display: none; height: 100vh; overflow: hidden; }
        #hub-screen.visible { display: flex; }

        nav {
            width: var(--sidebar-w); flex-shrink: 0;
            background: var(--bg2); border-right: 1px solid var(--border);
            display: flex; flex-direction: column;
            position: relative; overflow: hidden;
        }

        nav::before {
            content: ''; position: absolute;
            top: -80px; right: -80px; width: 300px; height: 300px;
            background: radial-gradient(circle, rgba(168,85,247,.12), transparent 70%);
            pointer-events: none;
        }

        nav > * { position: relative; z-index: 1; }

        .nav-header { padding: 24px 20px 20px; border-bottom: 1px solid var(--border); }

        .nav-logo { display: flex; align-items: center; gap: 12px; margin-bottom: 14px; }

        .logo-icon {
            width: 40px; height: 40px; border-radius: 12px;
            background: var(--grad1);
            display: grid; place-items: center; font-size: 18px; flex-shrink: 0;
            box-shadow: 0 4px 16px rgba(168,85,247,.35);
        }

        .nav-title {
            font-family: 'Clash Display', sans-serif;
            font-size: 1rem; font-weight: 700; color: var(--white); line-height: 1.1;
        }

        .nav-sub { font-size: .6rem; color: var(--muted); letter-spacing: 1.5px; text-transform: uppercase; margin-top: 2px; }

        .session-badge {
            display: inline-flex; align-items: center; gap: 7px;
            background: rgba(6,214,160,.1); border: 1px solid rgba(6,214,160,.2);
            border-radius: 20px; padding: 5px 12px;
            font-size: .67rem; color: var(--green); font-weight: 600;
        }

        .session-badge::before {
            content: ''; width: 6px; height: 6px; background: var(--green);
            border-radius: 50%; animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:.4;transform:scale(.6)} }

        .menu-list { list-style: none; padding: 12px 10px; flex-grow: 1; overflow-y: auto; scrollbar-width: none; }
        .menu-list::-webkit-scrollbar { display: none; }

        .menu-section-label {
            padding: 12px 10px 6px;
            font-size: .58rem; letter-spacing: 2px; text-transform: uppercase;
            color: var(--muted); font-weight: 600;
        }

        .menu-semester {
            display: flex; align-items: center; justify-content: space-between;
            padding: 10px 12px; border-radius: 10px; cursor: pointer;
            color: var(--text); font-size: .8rem; font-weight: 600;
            transition: background .15s; margin-bottom: 2px;
        }

        .menu-semester:hover { background: var(--bg3); }
        .sem-arrow { transition: transform .25s; font-size: .7rem; color: var(--muted); }
        .menu-semester.open .sem-arrow { transform: rotate(90deg); }
        .sem-items { display: none; }
        .sem-items.open { display: block; }

        .menu-item {
            display: flex; align-items: center; gap: 12px;
            padding: 10px 12px; border-radius: 10px; cursor: pointer;
            color: var(--text); transition: all .15s; margin-bottom: 2px;
            position: relative;
        }

        .menu-item:hover { background: var(--bg3); color: var(--white); }

        .menu-item.active {
            background: linear-gradient(135deg, rgba(168,85,247,.15), rgba(255,107,157,.1));
            color: var(--white);
        }

        .menu-item.active::before {
            content: ''; position: absolute; left: 0; top: 50%; transform: translateY(-50%);
            width: 3px; height: 60%; background: var(--grad1); border-radius: 0 3px 3px 0;
        }

        .item-icon {
            width: 32px; height: 32px; border-radius: 9px;
            display: grid; place-items: center; font-size: 15px; flex-shrink: 0;
            background: rgba(255,255,255,.05); transition: transform .15s;
        }

        .menu-item:hover .item-icon { transform: scale(1.1); }
        .menu-item.active .item-icon { background: linear-gradient(135deg, rgba(168,85,247,.2), rgba(255,107,157,.15)); }

        .item-label { font-size: .82rem; font-weight: 500; }

        .soon-badge {
            margin-left: auto; font-size: .6rem; padding: 2px 7px;
            background: rgba(255,255,255,.06); border-radius: 20px;
            color: var(--muted);
        }

        .item-arrow {
            margin-left: auto; opacity: 0; color: var(--violet); font-size: .7rem;
            transition: opacity .15s, transform .15s;
        }

        .menu-item:hover .item-arrow, .menu-item.active .item-arrow { opacity: 1; transform: translateX(2px); }

        .menu-divider { height: 1px; background: var(--border); margin: 8px 10px; }

        .menu-item.admin-item .item-icon { background: linear-gradient(135deg, rgba(255,209,102,.15), rgba(255,159,28,.1)); }
        .menu-item.admin-item:hover { color: var(--yellow); }
        .menu-item.admin-item.active { background: rgba(255,209,102,.08); color: var(--yellow); }
        .menu-item.admin-item.active::before { background: var(--grad3); }

        /* Ressources sidebar style */
        .menu-item.res-item .item-icon { background: linear-gradient(135deg, rgba(6,214,214,.15), rgba(6,214,160,.1)); }
        .menu-item.res-item:hover { color: var(--cyan); }

        .menu-semester.res-header { color: var(--cyan); }
        .menu-semester.res-header .sem-arrow { color: var(--cyan); opacity: .6; }

        .nav-footer {
            padding: 14px 16px; border-top: 1px solid var(--border);
            display: flex; align-items: center; gap: 10px;
        }

        .footer-avatar {
            width: 34px; height: 34px; border-radius: 10px;
            background: var(--grad2); display: grid; place-items: center;
            font-size: 14px; font-weight: 700; color: #fff; flex-shrink: 0;
        }

        .footer-info { flex: 1; min-width: 0; }
        .footer-name { font-size: .78rem; font-weight: 600; color: var(--white); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
        .footer-role { font-size: .63rem; color: var(--muted); margin-top: 1px; }

        .btn-logout {
            background: rgba(255,92,122,.08); border: 1px solid rgba(255,92,122,.18);
            border-radius: 8px; padding: 6px 10px; font-size: .75rem; color: var(--danger);
            cursor: pointer; font-family: 'Plus Jakarta Sans', sans-serif;
            transition: background .15s;
        }

        .btn-logout:hover { background: rgba(255,92,122,.18); }

        main {
            flex: 1; position: relative; background: var(--bg);
            display: flex; flex-direction: column; min-width: 0; overflow: hidden;
        }
        .main-body {
            flex: 1; display: flex; flex-direction: row; min-height: 0; overflow: hidden;
        }
        .main-content {
            flex: 1; display: flex; flex-direction: column; min-width: 0; overflow: hidden; position: relative;
        }

        .topbar {
            height: 62px; flex-shrink: 0;
            background: rgba(15,14,23,.96);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--border);
            display: flex; align-items: center; padding: 0 20px; gap: 12px;
            position: relative;
        }
        .topbar::after {
            content: '';
            position: absolute; bottom: 0; left: 0; right: 0; height: 1px;
            background: linear-gradient(90deg, transparent, rgba(168,85,247,.3), rgba(255,107,157,.2), transparent);
            pointer-events: none;
        }

        /* BREADCRUMB */
        .topbar-breadcrumb {
            display: flex; align-items: center; gap: 6px;
            font-size: .72rem; color: var(--muted);
            background: var(--bg3); border: 1px solid var(--border);
            border-radius: 8px; padding: 5px 12px;
            white-space: nowrap; flex-shrink: 0;
        }
        .topbar-breadcrumb .bc-home {
            color: var(--muted); font-size: .78rem;
        }
        .topbar-sep {
            color: var(--muted); opacity: .4; font-size: .8rem;
        }
        .topbar-breadcrumb span#current-page {
            color: var(--white); font-weight: 600; font-size: .72rem;
        }

        /* SEARCH */
        .topbar-actions { display: flex; align-items: center; gap: 7px; margin-left: auto; }

        .search-wrap {
            flex: 1; max-width: 400px; position: relative; margin: 0 6px;
        }

        .search-input {
            width: 100%;
            background: var(--bg3);
            border: 1.5px solid var(--border);
            border-radius: 10px;
            padding: 9px 16px 9px 38px;
            font-size: .78rem; color: var(--white);
            font-family: 'Plus Jakarta Sans', sans-serif; outline: none;
            transition: border-color .25s, box-shadow .25s, background .25s;
        }
        .search-input::placeholder { color: var(--muted); font-size: .75rem; }
        .search-input:focus {
            border-color: rgba(168,85,247,.6);
            box-shadow: 0 0 0 3px rgba(168,85,247,.1), 0 0 20px rgba(168,85,247,.06);
            background: rgba(168,85,247,.04);
        }

        .search-icon {
            position: absolute; left: 12px; top: 50%; transform: translateY(-50%);
            pointer-events: none; display: flex; align-items: center;
        }
        .search-icon svg { width: 15px; height: 15px; stroke: var(--muted); }

        .search-kbd {
            position: absolute; right: 10px; top: 50%; transform: translateY(-50%);
            font-size: .6rem; color: var(--muted); background: var(--bg2);
            border: 1px solid var(--border); border-radius: 5px;
            padding: 2px 6px; pointer-events: none; letter-spacing: .5px;
            font-family: 'Plus Jakarta Sans', sans-serif;
        }

        /* BOUTONS */
        .btn-topbar {
            width: 36px; height: 36px;
            background: var(--bg3); border: 1px solid var(--border);
            border-radius: 9px; color: var(--muted); cursor: pointer;
            display: grid; place-items: center;
            transition: all .15s;
            flex-shrink: 0;
        }
        .btn-topbar svg { width: 16px; height: 16px; stroke: currentColor; }
        .btn-topbar:hover {
            border-color: rgba(168,85,247,.4);
            color: var(--violet);
            background: rgba(168,85,247,.06);
            transform: translateY(-1px);
        }
        .btn-topbar:active { transform: scale(.95); }

        .search-results {
            position: absolute; top: calc(100% + 8px); left: 0; right: 0;
            background: var(--bg2); border: 1px solid rgba(255,255,255,.1);
            border-radius: 14px; z-index: 200; max-height: 320px;
            overflow-y: auto; scrollbar-width: none; display: none;
            box-shadow: 0 20px 60px rgba(0,0,0,.6);
        }

        .search-results.visible { display: block; }
        .search-results::-webkit-scrollbar { display: none; }

        .search-result-item {
            display: flex; align-items: flex-start; gap: 10px;
            padding: 10px 14px; cursor: pointer;
            border-bottom: 1px solid rgba(255,255,255,.04); transition: background .15s;
        }

        .search-result-item:last-child { border-bottom: none; }
        .search-result-item:hover { background: var(--bg3); }

        .sri-icon {
            width: 30px; height: 30px; border-radius: 8px;
            background: linear-gradient(135deg, rgba(168,85,247,.2), rgba(255,107,157,.15));
            display: grid; place-items: center; font-size: 14px; flex-shrink: 0;
        }

        .sri-notion { font-size: .8rem; font-weight: 600; color: var(--white); }
        .sri-mat { font-size: .7rem; color: var(--muted); margin-top: 2px; }
        .sri-mark { color: var(--pink); }
        .search-empty { padding: 20px; text-align: center; font-size: .78rem; color: var(--muted); }

        .loader {
            position: absolute; top: 0; left: 0; height: 3px; width: 0%;
            background: var(--grad1); border-radius: 2px; transition: width .4s ease; z-index: 10;
        }
        .loader.loading { width: 70%; }
        .loader.done { width: 100%; opacity: 0; transition: width .2s, opacity .3s .2s; }

        .welcome {
            flex: 1; display: flex; flex-direction: column;
            align-items: center; justify-content: center;
            gap: 20px; padding: 40px; position: relative;
        }

        .welcome.hidden { display: none; }

        .welcome::before {
            content: ''; position: absolute; inset: 0; pointer-events: none;
            background:
                radial-gradient(ellipse 600px 400px at 30% 40%, rgba(168,85,247,.06), transparent 70%),
                radial-gradient(ellipse 400px 300px at 70% 70%, rgba(255,107,157,.05), transparent 70%);
        }

        .welcome-icon {
            font-size: 3.5rem; animation: float 4s ease-in-out infinite;
            filter: drop-shadow(0 8px 24px rgba(168,85,247,.4));
        }

        @keyframes float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-10px)} }

        .welcome h1 {
            font-family: 'Clash Display', sans-serif;
            font-size: 2.2rem; font-weight: 700; color: var(--white);
            text-align: center; line-height: 1.15;
        }

        .welcome h1 span {
            background: var(--grad1); -webkit-background-clip: text;
            -webkit-text-fill-color: transparent; background-clip: text;
        }

        .welcome p { font-size: .88rem; color: var(--muted); text-align: center; max-width: 380px; line-height: 1.7; }

        .welcome-cards {
            display: grid; grid-template-columns: repeat(3, 1fr);
            gap: 14px; margin-top: 8px; width: 100%; max-width: 680px;
        }

        .welcome-card {
            background: var(--bg2); border: 1px solid var(--border);
            border-radius: 16px; padding: 20px 16px;
            cursor: pointer; transition: all .2s;
            display: flex; flex-direction: column; align-items: center; gap: 10px;
            text-align: center; position: relative; overflow: hidden;
        }

        .welcome-card::before {
            content: ''; position: absolute; inset: 0; opacity: 0; transition: opacity .2s;
        }

        .welcome-card:nth-child(1)::before { background: linear-gradient(135deg, rgba(6,214,214,.08), rgba(168,85,247,.08)); }
        .welcome-card:nth-child(2)::before { background: linear-gradient(135deg, rgba(255,107,157,.08), rgba(255,159,28,.08)); }
        .welcome-card:nth-child(3)::before { background: linear-gradient(135deg, rgba(6,214,160,.08), rgba(6,214,214,.08)); }

        .welcome-card:hover { transform: translateY(-4px); border-color: rgba(255,255,255,.15); }
        .welcome-card:hover::before { opacity: 1; }

        .welcome-card-icon { font-size: 2rem; position: relative; z-index: 1; }
        .welcome-card-label { font-size: .8rem; font-weight: 600; color: var(--white); position: relative; z-index: 1; }
        .welcome-card-sub { font-size: .68rem; color: var(--muted); position: relative; z-index: 1; }

        .iframe-wrapper { display: none; flex: 1; position: relative; }
        .iframe-wrapper.visible { display: block; }
        iframe { width: 100%; height: 100%; border: none; }

        /* ADMIN */
        #admin-panel { display: none; flex: 1; flex-direction: column; overflow: hidden; }
        #admin-panel.visible { display: flex; }

        .admin-content { flex: 1; overflow-y: auto; padding: 28px; }

        .admin-header {
            display: flex; align-items: flex-start; justify-content: space-between;
            margin-bottom: 24px; flex-wrap: wrap; gap: 12px;
        }

        .admin-title { font-family: 'Clash Display', sans-serif; font-size: 1.4rem; font-weight: 700; color: var(--white); }
        .admin-subtitle { font-size: .78rem; color: var(--muted); margin-top: 2px; }

        .stats-row { display: grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap: 12px; margin-bottom: 24px; }

        .stat-card {
            background: var(--bg2); border: 1px solid var(--border);
            border-radius: 16px; padding: 20px; position: relative; overflow: hidden;
        }

        .stat-card::before {
            content: ''; position: absolute; top: -20px; right: -20px;
            width: 80px; height: 80px; border-radius: 50%; opacity: .15;
        }

        .stat-card:nth-child(1)::before { background: var(--violet); }
        .stat-card:nth-child(2)::before { background: var(--green); }
        .stat-card:nth-child(3)::before { background: var(--cyan); }
        .stat-card:nth-child(4)::before { background: var(--muted); }

        .stat-value { font-family: 'Clash Display', sans-serif; font-size: 2rem; font-weight: 700; color: var(--white); }
        .stat-label { font-size: .72rem; color: var(--muted); margin-top: 2px; }

        .section-card { background: var(--bg2); border: 1px solid var(--border); border-radius: 18px; padding: 22px 24px; margin-bottom: 20px; }

        .section-title { font-family: 'Clash Display', sans-serif; font-size: .95rem; font-weight: 700; color: var(--white); margin-bottom: 16px; }

        .gen-form { display: flex; gap: 10px; flex-wrap: wrap; align-items: flex-end; }
        .form-field { display: flex; flex-direction: column; gap: 6px; flex: 1; min-width: 140px; }
        .form-label { font-size: .65rem; color: var(--muted); text-transform: uppercase; letter-spacing: 1px; font-weight: 600; }

        .form-input {
            background: var(--bg); border: 1.5px solid var(--border); border-radius: 10px;
            padding: 10px 14px; font-size: .82rem; color: var(--white);
            font-family: 'Plus Jakarta Sans', sans-serif; outline: none;
            transition: border-color .2s, box-shadow .2s;
        }

        .form-input:focus { border-color: var(--violet); box-shadow: 0 0 0 3px rgba(168,85,247,.1); }

        .btn-gen {
            background: var(--grad1); border: none; border-radius: 10px; padding: 10px 20px;
            font-family: 'Clash Display', sans-serif; font-size: .82rem; font-weight: 600;
            color: #fff; cursor: pointer; white-space: nowrap;
            box-shadow: 0 4px 16px rgba(168,85,247,.3);
            transition: transform .1s, box-shadow .15s;
        }

        .btn-gen:hover { transform: translateY(-1px); box-shadow: 0 6px 20px rgba(168,85,247,.4); }
        .btn-gen:active { transform: scale(.98); }
        .btn-gen:disabled { opacity: .5; cursor: not-allowed; transform: none; }

        .codes-table-wrap { overflow-x: auto; }
        .codes-table { width: 100%; border-collapse: collapse; font-size: .8rem; }

        .codes-table th {
            text-align: left; padding: 10px 14px; font-size: .62rem;
            letter-spacing: 1.2px; text-transform: uppercase; color: var(--muted);
            border-bottom: 1px solid var(--border); font-weight: 600;
        }

        .codes-table td {
            padding: 12px 14px; border-bottom: 1px solid rgba(255,255,255,.03);
            color: var(--text); vertical-align: middle;
        }

        .codes-table tr:last-child td { border-bottom: none; }
        .codes-table tr:hover td { background: rgba(255,255,255,.02); }

        .code-pill {
            font-family: 'Clash Display', sans-serif; font-weight: 700; font-size: .85rem;
            letter-spacing: 2px; color: var(--white);
            background: rgba(168,85,247,.12); border: 1px solid rgba(168,85,247,.2);
            border-radius: 8px; padding: 4px 12px; display: inline-block;
        }

        .badge { display: inline-flex; align-items: center; gap: 5px; border-radius: 20px; padding: 3px 10px; font-size: .68rem; font-weight: 600; }
        .badge::before { content: ''; width: 5px; height: 5px; border-radius: 50%; }

        .badge-active  { background: rgba(6,214,160,.1); color: var(--green); border: 1px solid rgba(6,214,160,.2); }
        .badge-active::before { background: var(--green); }
        .badge-online  { background: rgba(6,214,214,.1); color: var(--cyan); border: 1px solid rgba(6,214,214,.2); }
        .badge-online::before { background: var(--cyan); }
        .badge-revoked { background: rgba(90,86,112,.1); color: var(--muted); border: 1px solid rgba(90,86,112,.2); }
        .badge-revoked::before { background: var(--muted); }

        .actions-cell { display: flex; gap: 6px; flex-wrap: wrap; }

        .btn-action {
            border-radius: 7px; padding: 4px 10px; font-size: .68rem; cursor: pointer;
            font-family: 'Plus Jakarta Sans', sans-serif; transition: all .15s;
            white-space: nowrap; border: 1px solid transparent; background: transparent; font-weight: 500;
        }

        .btn-copy   { border-color: var(--border); color: var(--muted); }
        .btn-copy:hover   { background: var(--bg3); color: var(--text); }
        .btn-revoke { border-color: rgba(255,92,122,.25); color: var(--danger); }
        .btn-revoke:hover { background: rgba(255,92,122,.1); }
        .btn-restore { border-color: rgba(6,214,160,.25); color: var(--green); }
        .btn-restore:hover { background: rgba(6,214,160,.1); }
        .btn-delete { border-color: rgba(255,92,122,.15); color: var(--muted); }
        .btn-delete:hover { background: rgba(255,92,122,.08); color: var(--danger); }
        .btn-kick   { border-color: rgba(6,214,214,.25); color: var(--cyan); }
        .btn-kick:hover   { background: rgba(6,214,214,.1); }

        /* ── BROADCAST BANNER ── */
        .broadcast-banner {
            display: none; align-items: center; gap: 14px;
            padding: 12px 20px;
            background: linear-gradient(135deg, rgba(255,209,102,.08), rgba(255,159,28,.06));
            border-bottom: 1px solid rgba(255,209,102,.2);
            font-size: .82rem; color: var(--text);
            animation: slideDown .4s cubic-bezier(.34,1.56,.64,1);
            position: relative; z-index: 5; flex-shrink: 0;
        }
        @keyframes slideDown { from { opacity:0; transform:translateY(-100%); } to { opacity:1; transform:translateY(0); } }
        .broadcast-banner.visible { display: flex; }
        .broadcast-icon {
            width: 32px; height: 32px; border-radius: 9px; flex-shrink: 0;
            background: rgba(255,209,102,.15); border: 1px solid rgba(255,209,102,.3);
            display: grid; place-items: center; font-size: 15px;
        }
        .broadcast-text { flex: 1; min-width: 0; line-height: 1.5; }
        .broadcast-text strong { color: var(--yellow); font-weight: 600; }
        .broadcast-close {
            width: 26px; height: 26px; border-radius: 7px; flex-shrink: 0;
            background: rgba(255,255,255,.05); border: 1px solid var(--border);
            color: var(--muted); cursor: pointer; font-size: 13px;
            display: grid; place-items: center; transition: all .15s;
        }
        .broadcast-close:hover { color: var(--white); background: rgba(255,255,255,.1); }

        /* ── BROADCAST ADMIN urgency ── */
        .urgency-select {
            background: var(--bg); border: 1.5px solid var(--border); border-radius: 10px;
            padding: 10px 14px; font-size: .82rem; color: var(--white);
            font-family: 'Plus Jakarta Sans', sans-serif; outline: none;
            transition: border-color .2s;
        }
        .urgency-select:focus { border-color: var(--violet); }

        .toast {
            position: fixed; bottom: 24px; right: 24px;
            background: var(--bg2); border: 1px solid var(--border);
            border-radius: 14px; padding: 14px 20px; font-size: .8rem; color: var(--text);
            z-index: 999; display: flex; align-items: center; gap: 10px;
            transform: translateY(80px); opacity: 0;
            transition: transform .3s cubic-bezier(.34,1.56,.64,1), opacity .3s;
            max-width: 340px; box-shadow: 0 20px 60px rgba(0,0,0,.4);
        }

        .toast.visible { transform: translateY(0); opacity: 1; }
        .toast.success { border-color: rgba(6,214,160,.3); color: var(--green); }
        .toast.error   { border-color: rgba(255,92,122,.3); color: var(--danger); }

        .burger {
            display: none; width: 38px; height: 38px; background: var(--bg3);
            border: 1px solid var(--border); border-radius: 10px; cursor: pointer;
            align-items: center; justify-content: center; flex-direction: column;
            gap: 5px; flex-shrink: 0; padding: 0;
        }

        .burger span { display: block; width: 16px; height: 2px; background: var(--text); border-radius: 2px; }

        .nav-overlay {
            display: none; position: fixed; inset: 0;
            background: rgba(0,0,0,.7); backdrop-filter: blur(4px);
            z-index: 99; opacity: 0; transition: opacity .3s; pointer-events: none;
        }

        .nav-overlay.visible { opacity: 1; pointer-events: all; }

        /* ── PC : plein écran ── */
        html, body { width: 100%; height: 100%; overflow: hidden; }
        #hub-screen { width: 100vw; height: 100vh; }

        /* ── MOBILE ── */
        @media (max-width: 768px) {
            .burger { display: flex; }
            nav {
                position: fixed; top: 0; left: 0; height: 100%;
                width: min(300px, 88vw); z-index: 100;
                transform: translateX(-100%);
                transition: transform .3s cubic-bezier(.4,0,.2,1); overflow-y: auto;
            }
            nav.open { transform: translateX(0); }
            .nav-overlay { display: block; }
            main { width: 100%; min-width: 0; }
            .topbar { gap: 6px; padding: 0 12px; height: 54px; }
            .topbar-breadcrumb { display: none; }
            .welcome { padding: 24px 16px; gap: 14px; }
            .welcome h1 { font-size: 1.5rem; }
            .welcome p { font-size: .82rem; }
            .welcome-cards { grid-template-columns: 1fr; max-width: 100%; gap: 10px; }
            .welcome-card { padding: 16px 14px; flex-direction: row; text-align: left; gap: 14px; }
            .welcome-card-icon { font-size: 1.6rem; }
            .login-card { padding: 28px 20px; border-radius: 20px; }
            .login-title { font-size: 1.5rem; }
            .admin-content { padding: 14px; }
            .admin-header { flex-direction: column; }
            .gen-form { flex-direction: column; }
            .search-wrap { max-width: none; flex: 1; margin: 0 4px; }
            .search-kbd { display: none; }
            .stats-row { grid-template-columns: repeat(2, 1fr); }
            .section-card { padding: 16px; }
            .codes-table { font-size: .72rem; }
            .codes-table th, .codes-table td { padding: 8px 10px; }
            .nav-footer { padding: 10px 12px; }
            iframe { width: 100%; height: 100%; }
        }

        @media (max-width: 400px) {
            .topbar { padding: 0 10px; gap: 4px; }
            .btn-topbar { width: 32px; height: 32px; }
            .welcome h1 { font-size: 1.3rem; }
            .login-card { padding: 24px 16px; }
            .stats-row { grid-template-columns: 1fr 1fr; gap: 8px; }
        }
    
        /* ── NOTES PANEL ── */
        .notes-panel {
            display: none; flex-direction: column;
            width: 360px; flex-shrink: 0;
            background: var(--bg2);
            border-left: 1px solid var(--border);
            position: relative; overflow: hidden;
        }
        .notes-panel.open { display: flex; }
        .notes-panel::before {
            content: '';
            position: absolute; top: 0; left: 0; right: 0; height: 2px;
            background: linear-gradient(90deg, var(--violet), var(--cyan));
            z-index: 1;
        }
        .notes-header {
            padding: 20px 20px 16px;
            border-bottom: 1px solid var(--border);
            display: flex; align-items: center; gap: 12px;
            flex-shrink: 0;
        }
        .notes-header-icon {
            width: 38px; height: 38px; border-radius: 11px; flex-shrink: 0;
            background: linear-gradient(135deg, var(--violet), var(--cyan));
            display: grid; place-items: center; font-size: 18px;
            box-shadow: 0 4px 14px rgba(168,85,247,.3);
        }
        .notes-header-info { flex: 1; min-width: 0; }
        .notes-header-title {
            font-family: 'Clash Display', sans-serif;
            font-size: .88rem; font-weight: 700; color: var(--white);
            white-space: nowrap; overflow: hidden; text-overflow: ellipsis;
        }
        .notes-header-sub { font-size: .66rem; color: var(--muted); margin-top: 2px; }
        .notes-close {
            width: 30px; height: 30px; border-radius: 8px; flex-shrink: 0;
            background: var(--bg3); border: 1px solid var(--border);
            color: var(--muted); cursor: pointer; font-size: 14px;
            display: grid; place-items: center; transition: all .15s;
        }
        .notes-close:hover { color: var(--white); background: rgba(255,92,122,.1); border-color: rgba(255,92,122,.3); }
        .notes-toolbar {
            padding: 10px 16px; border-bottom: 1px solid var(--border);
            display: flex; gap: 6px; flex-shrink: 0; background: var(--bg2);
        }
        .notes-btn {
            height: 30px; padding: 0 12px;
            background: var(--bg3); border: 1px solid var(--border);
            border-radius: 7px; color: var(--muted); cursor: pointer;
            font-size: .75rem; font-family: 'Plus Jakarta Sans', sans-serif;
            transition: all .15s; display: flex; align-items: center; gap: 4px;
        }
        .notes-btn:hover { color: var(--white); border-color: rgba(168,85,247,.35); background: rgba(168,85,247,.06); }
        .notes-editor {
            flex: 1; padding: 20px;
            font-size: .85rem; color: var(--white);
            font-family: 'Plus Jakarta Sans', sans-serif;
            line-height: 1.8; outline: none;
            background: transparent; border: none;
            overflow-y: auto; scrollbar-width: thin;
            scrollbar-color: rgba(255,255,255,.06) transparent;
            min-height: 0;
        }
        .notes-editor:empty::before {
            content: attr(data-placeholder);
            color: var(--muted); font-size: .8rem;
            pointer-events: none; white-space: pre-line;
        }
        .notes-editor b, .notes-editor strong { color: var(--white); font-weight: 700; }
        .notes-editor i, .notes-editor em { color: var(--cyan); font-style: italic; }
        .notes-editor u { text-decoration: underline; text-decoration-color: rgba(255,255,255,.4); }
        .notes-editor s { color: var(--muted); }
        .notes-editor h3 {
            font-family: 'Clash Display', sans-serif;
            font-size: 1rem; font-weight: 700; color: var(--violet);
            margin: 14px 0 6px; line-height: 1.2;
        }
        .notes-editor ul, .notes-editor ol {
            padding-left: 20px; margin: 6px 0;
        }
        .notes-editor li { margin: 3px 0; }
        .notes-editor blockquote {
            border-left: 3px solid var(--violet);
            padding: 6px 14px; margin: 8px 0;
            background: rgba(168,85,247,.06);
            border-radius: 0 6px 6px 0;
            color: var(--muted); font-style: italic;
        }
        .notes-footer {
            padding: 12px 18px; border-top: 1px solid var(--border);
            display: flex; align-items: center; justify-content: space-between;
            flex-shrink: 0;
        }
        .notes-save-status {
            font-size: .7rem; color: var(--muted);
            display: flex; align-items: center; gap: 7px;
        }
        .notes-save-dot {
            width: 7px; height: 7px; border-radius: 50%;
            background: var(--muted); transition: background .3s; flex-shrink: 0;
        }
        .notes-save-dot.saved  { background: var(--green); box-shadow: 0 0 6px rgba(6,214,160,.4); }
        .notes-save-dot.saving { background: var(--yellow); animation: pulse 1s ease-in-out infinite; }
        .notes-char-count { font-size: .66rem; color: var(--muted); }
        .notes-toggle-btn {
            width: 26px; height: 26px; border-radius: 7px; flex-shrink: 0;
            background: rgba(168,85,247,.06); border: 1px solid rgba(168,85,247,.12);
            color: var(--violet); cursor: pointer; font-size: 12px;
            display: grid; place-items: center; transition: all .15s;
            margin-left: auto;
        }
        .notes-toggle-btn:hover { background: rgba(168,85,247,.16); border-color: rgba(168,85,247,.3); }
        .notes-toggle-btn.has-notes { background: rgba(168,85,247,.14); border-color: rgba(168,85,247,.35); box-shadow: 0 0 8px rgba(168,85,247,.2); }
        @media (max-width: 768px) {
            .notes-panel {
                position: fixed; right: 0; top: 0; bottom: 0; z-index: 150;
                width: min(360px, 95vw);
                transform: translateX(110%);
                transition: transform .35s cubic-bezier(.4,0,.2,1);
                box-shadow: -20px 0 60px rgba(0,0,0,.5);
            }
            .notes-panel.open { display: flex; transform: translateX(0); }
        }

        
        /* ── ONBOARDING ── */
        .ob-overlay {
            display: none; position: fixed; inset: 0; z-index: 9999;
            background: rgba(0,0,0,.7); backdrop-filter: blur(8px);
            align-items: center; justify-content: center; padding: 20px;
        }
        .ob-overlay.visible { display: flex; }

        .ob-modal {
            background: var(--bg2);
            border: 1px solid rgba(255,255,255,.1);
            border-radius: 24px;
            width: 100%; max-width: 520px;
            overflow: hidden;
            animation: cardIn .5s cubic-bezier(.34,1.56,.64,1);
            box-shadow: 0 40px 80px rgba(0,0,0,.6);
            position: relative;
        }

        .ob-slide { display: none; }
        .ob-slide.active { display: block; }

        .ob-hero {
            padding: 36px 36px 28px;
            text-align: center;
            border-bottom: 1px solid var(--border);
            position: relative;
        }
        .ob-hero::before {
            content: '';
            position: absolute; inset: 0;
            background: radial-gradient(ellipse 400px 200px at 50% 0%, rgba(168,85,247,.08), transparent 70%);
            pointer-events: none;
        }

        .ob-icon-wrap {
            width: 68px; height: 68px; border-radius: 20px;
            display: grid; place-items: center;
            margin: 0 auto 20px; font-size: 32px;
            position: relative;
        }
        .ob-icon-wrap.purple { background: rgba(168,85,247,.12); box-shadow: 0 6px 24px rgba(168,85,247,.2); }
        .ob-icon-wrap.teal   { background: rgba(6,214,214,.12);  box-shadow: 0 6px 24px rgba(6,214,214,.2); }
        .ob-icon-wrap.amber  { background: rgba(255,209,102,.12); box-shadow: 0 6px 24px rgba(255,209,102,.2); }
        .ob-icon-wrap.blue   { background: rgba(78,157,245,.12);  box-shadow: 0 6px 24px rgba(78,157,245,.2); }
        .ob-icon-wrap.green  { background: rgba(62,207,142,.12);  box-shadow: 0 6px 24px rgba(62,207,142,.2); }

        .ob-title {
            font-family: 'Clash Display', sans-serif;
            font-size: 1.4rem; font-weight: 700;
            color: var(--white); margin-bottom: 10px; line-height: 1.2;
        }
        .ob-desc {
            font-size: .83rem; color: var(--muted);
            line-height: 1.75; max-width: 380px; margin: 0 auto;
        }

        .ob-features {
            padding: 20px 28px;
            display: flex; flex-direction: column; gap: 10px;
        }

        .ob-feat {
            display: flex; align-items: flex-start; gap: 14px;
            padding: 12px 14px;
            background: var(--bg3);
            border-radius: 12px;
            border: 1px solid var(--border);
            transition: border-color .2s;
        }
        .ob-feat:hover { border-color: rgba(168,85,247,.25); }

        .ob-feat-icon {
            width: 36px; height: 36px; border-radius: 10px;
            display: grid; place-items: center; font-size: 17px; flex-shrink: 0;
        }
        .ob-feat-icon.purple { background: rgba(168,85,247,.1); }
        .ob-feat-icon.teal   { background: rgba(6,214,214,.1); }
        .ob-feat-icon.amber  { background: rgba(255,209,102,.1); }
        .ob-feat-icon.blue   { background: rgba(78,157,245,.1); }
        .ob-feat-icon.green  { background: rgba(62,207,142,.1); }

        .ob-feat-title { font-size: .82rem; font-weight: 600; color: var(--white); margin-bottom: 2px; }
        .ob-feat-sub { font-size: .73rem; color: var(--muted); line-height: 1.5; }

        .ob-footer {
            padding: 16px 28px;
            border-top: 1px solid var(--border);
            display: flex; align-items: center; justify-content: space-between; gap: 12px;
        }

        .ob-dots { display: flex; gap: 6px; align-items: center; }
        .ob-dot {
            width: 7px; height: 7px; border-radius: 50%;
            background: var(--muted); transition: all .25s;
        }
        .ob-dot.active { width: 22px; border-radius: 4px; background: var(--violet); }

        .ob-btns { display: flex; gap: 8px; align-items: center; }
        .ob-counter { font-size: .7rem; color: var(--muted); margin-right: 4px; }

        .ob-btn {
            height: 36px; padding: 0 18px; border-radius: 10px;
            font-size: .78rem; font-weight: 600; cursor: pointer;
            font-family: 'Clash Display', sans-serif;
            border: 1px solid var(--border);
            background: var(--bg3); color: var(--text);
            transition: all .15s;
        }
        .ob-btn:hover { border-color: rgba(255,255,255,.15); color: var(--white); }
        .ob-btn.primary {
            background: var(--grad1); border-color: transparent; color: #fff;
            box-shadow: 0 4px 16px rgba(168,85,247,.3);
        }
        .ob-btn.primary:hover { box-shadow: 0 6px 20px rgba(168,85,247,.45); transform: translateY(-1px); }

        .ob-checklist {
            padding: 4px 28px 24px;
            display: flex; flex-direction: column; gap: 10px;
        }
        .ob-check-item {
            display: flex; align-items: center; gap: 12px;
            font-size: .8rem; color: var(--text);
        }
        .ob-check-icon {
            width: 22px; height: 22px; border-radius: 6px;
            background: rgba(6,214,160,.1); border: 1px solid rgba(6,214,160,.25);
            display: grid; place-items: center; font-size: 11px;
            color: var(--green); flex-shrink: 0;
        }

        @media (max-width: 600px) {
            .ob-modal { border-radius: 18px; }
            .ob-hero { padding: 28px 20px 22px; }
            .ob-features { padding: 16px 20px; }
            .ob-footer { padding: 14px 20px; }
            .ob-checklist { padding: 4px 20px 20px; }
            .ob-title { font-size: 1.2rem; }
        }

        </style>
</head>
<body>

<div id="login-screen">
    <div class="login-bg">
        <div class="login-blob blob1"></div>
        <div class="login-blob blob2"></div>
        <div class="login-blob blob3"></div>
    </div>
    <div class="login-card">
        <div class="login-logo">
            <div class="login-logo-icon">📚</div>
            <div>
                <div class="login-logo-text">Hub Révisions</div>
                <div class="login-logo-sub">Master CCA</div>
            </div>
        </div>
        <h1 class="login-title">Bienvenue <span>👋</span></h1>
        <p class="login-sub">Si tu veux un code, paie 5€ et contacte Enzo.</p>
        <label class="input-label" for="code-input">Code d'accès</label>
        <input type="text" id="code-input" class="code-input"
            placeholder="XXXXXXXX" maxlength="12"
            autocomplete="username" autocorrect="off" spellcheck="false">
        <button class="btn-login" id="btn-login" onclick="handleLogin()">Accéder au hub →</button>
        <div class="login-error" id="login-error">
            <span>⚠</span><span id="login-error-msg">Code incorrect ou révoqué.</span>
        </div>
        <div class="last-session" id="last-session" onclick="loginWithSaved()">
            <div class="last-session-avatar" id="ls-avatar">?</div>
            <div class="last-session-info">
                <div class="last-session-name" id="ls-name">Continuer</div>
                <div class="last-session-hint">Cliquer pour se reconnecter</div>
            </div>
            <div class="last-session-arrow">›</div>
        </div>
        <div class="login-footer">Accès réservé aux étudiants inscrits</div>
    </div>
</div>

<div id="hub-screen">
    <div class="nav-overlay" id="nav-overlay" onclick="closeSidebar()"></div>

    <nav id="sidebar">
        <div class="nav-header">
            <div class="nav-logo">
                <div class="logo-icon">📚</div>
                <div>
                    <div class="nav-title">Hub Révisions</div>
                    <div class="nav-sub">Master CCA</div>
                </div>
            </div>
            <div class="session-badge">Session active</div>
        </div>

        <ul class="menu-list">
            <div class="menu-section-label">Matières</div>

            <div class="menu-semester" onclick="toggleSem('s1')">
                <span>Semestre 1</span><span class="sem-arrow">›</span>
            </div>
            <div class="sem-items" id="sem-s1">
                <li class="menu-item"><div class="item-icon">📘</div><span class="item-label">Matière 1</span><span class="soon-badge">Bientôt</span><button class="notes-toggle-btn" id="ntb-m1" onclick="openNotes(event,'Matière 1')" title="Mes notes">📝</button></li>
                <li class="menu-item"><div class="item-icon">📗</div><span class="item-label">Matière 2</span><span class="soon-badge">Bientôt</span><button class="notes-toggle-btn" id="ntb-m2" onclick="openNotes(event,'Matière 2')" title="Mes notes">📝</button></li>
                <li class="menu-item"><div class="item-icon">📙</div><span class="item-label">Matière 3</span><span class="soon-badge">Bientôt</span><button class="notes-toggle-btn" id="ntb-m3" onclick="openNotes(event,'Matière 3')" title="Mes notes">📝</button></li>
                <li class="menu-item"><div class="item-icon">📕</div><span class="item-label">Matière 4</span><span class="soon-badge">Bientôt</span><button class="notes-toggle-btn" id="ntb-m4" onclick="openNotes(event,'Matière 4')" title="Mes notes">📝</button></li>
            </div>

            <div class="menu-semester" onclick="toggleSem('s2')">
                <span>Semestre 2</span><span class="sem-arrow">›</span>
            </div>
            <div class="sem-items" id="sem-s2">
                <li class="menu-item"><div class="item-icon">📘</div><span class="item-label">Matière 5</span><span class="soon-badge">Bientôt</span><button class="notes-toggle-btn" id="ntb-m5" onclick="openNotes(event,'Matière 5')" title="Mes notes">📝</button></li>
                <li class="menu-item"><div class="item-icon">📗</div><span class="item-label">Matière 6</span><span class="soon-badge">Bientôt</span><button class="notes-toggle-btn" id="ntb-m6" onclick="openNotes(event,'Matière 6')" title="Mes notes">📝</button></li>
                <li class="menu-item"><div class="item-icon">📙</div><span class="item-label">Matière 7</span><span class="soon-badge">Bientôt</span><button class="notes-toggle-btn" id="ntb-m7" onclick="openNotes(event,'Matière 7')" title="Mes notes">📝</button></li>
                <li class="menu-item"><div class="item-icon">📕</div><span class="item-label">Matière 8</span><span class="soon-badge">Bientôt</span><button class="notes-toggle-btn" id="ntb-m8" onclick="openNotes(event,'Matière 8')" title="Mes notes">📝</button></li>
            </div>

            <!-- ── INFORMATIONS COMPLÉMENTAIRES ── -->
            <div class="menu-divider"></div>
            <div class="menu-semester res-header" onclick="toggleSem('ressources')">
                <span>📎 Infos complémentaires</span><span class="sem-arrow">›</span>
            </div>
            <div class="sem-items" id="sem-ressources">
                <div id="ressources-list-sidebar">
                    <li class="menu-item"><span style="font-size:.72rem;color:var(--muted);padding:0 4px">Chargement…</span></li>
                </div>
            </div>

            <div class="menu-divider" id="admin-divider" style="display:none"></div>
            <li class="menu-item admin-item" id="admin-menu-item" style="display:none" onclick="openAdmin()">
                <div class="item-icon">⚙️</div>
                <span class="item-label">Administration</span>
                <span class="item-arrow">›</span>
            </li>
        </ul>

        <div class="nav-footer">
            <div class="footer-avatar" id="footer-avatar">E</div>
            <div class="footer-info">
                <div class="footer-name" id="footer-name">Session</div>
                <div class="footer-role" id="footer-role">Étudiant</div>
            </div>
            <button class="btn-logout" onclick="handleLogout()">⏏</button>
        </div>
    </nav>

    <main>
        <div class="topbar">
            <button class="burger" onclick="toggleSidebar()">
                <span></span><span></span><span></span>
            </button>

            <div class="topbar-breadcrumb">
                <span class="bc-home">📚</span>
                <span class="topbar-sep">›</span>
                <span id="current-page">Accueil</span>
            </div>

            <div class="search-wrap">
                <span class="search-icon">
                    <svg viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <circle cx="11" cy="11" r="8"/><path d="m21 21-4.35-4.35"/>
                    </svg>
                </span>
                <input type="text" id="search-input" class="search-input"
                    placeholder="Rechercher une notion, une formule…"
                    autocomplete="off" autocorrect="off" spellcheck="false"
                    oninput="handleSearch(this.value)" onfocus="showResults()">
                <span class="search-kbd">⌘K</span>
                <div class="search-results" id="search-results"></div>
            </div>

            <div class="topbar-actions">
                <button class="btn-topbar" id="btn-home" onclick="goHome()" style="display:none" title="Accueil">
                    <svg viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/>
                    </svg>
                </button>
                <button class="btn-topbar" onclick="reloadFrame()" title="Recharger">
                    <svg viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <polyline points="23 4 23 10 17 10"/><path d="M20.49 15a9 9 0 1 1-2.12-9.36L23 10"/>
                    </svg>
                </button>
                <button class="btn-topbar" id="btn-theme" onclick="toggleTheme()" title="Changer de thème" style="background:rgba(255,209,102,.1);border-color:rgba(255,209,102,.25);color:var(--yellow)">
                    <svg id="theme-icon-moon" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/>
                    </svg>
                    <svg id="theme-icon-sun" viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="display:none">
                        <circle cx="12" cy="12" r="5"/>
                        <line x1="12" y1="1" x2="12" y2="3"/><line x1="12" y1="21" x2="12" y2="23"/>
                        <line x1="4.22" y1="4.22" x2="5.64" y2="5.64"/><line x1="18.36" y1="18.36" x2="19.78" y2="19.78"/>
                        <line x1="1" y1="12" x2="3" y2="12"/><line x1="21" y1="12" x2="23" y2="12"/>
                        <line x1="4.22" y1="19.78" x2="5.64" y2="18.36"/><line x1="18.36" y1="5.64" x2="19.78" y2="4.22"/>
                    </svg>
                </button>

            </div>
        </div>

        <div class="main-body" id="main-body">
        <div class="main-content" id="main-content">

        <!-- BROADCAST BANNER -->
        <div class="broadcast-banner" id="broadcast-banner">
            <div class="broadcast-icon" id="broadcast-icon">📢</div>
            <div class="broadcast-text" id="broadcast-text"></div>
            <button class="broadcast-close" onclick="closeBroadcast()">✕</button>
        </div>

        <div class="loader" id="loader"></div>

        <div class="welcome" id="welcome">
            <div class="welcome-icon">🎯</div>
            <h1 id="welcome-title">Bonne <span>révision</span> !</h1>
            <p>Sélectionne une matière dans le menu pour commencer à réviser.</p>
            <div class="welcome-cards">
                <div class="welcome-card" onclick="loadPage('CG.html',null,'Contrôle de Gestion')">
                    <div class="welcome-card-icon">📊</div>
                    <div class="welcome-card-label">Contrôle de Gestion</div>
                    <div class="welcome-card-sub">Fiches & exercices</div>
                </div>
                <div class="welcome-card" onclick="loadPage('mana.html',null,'Management')">
                    <div class="welcome-card-icon">👔</div>
                    <div class="welcome-card-label">Management</div>
                    <div class="welcome-card-sub">Fiches & exercices</div>
                </div>
                <div class="welcome-card" onclick="loadPage('SO.html',null,'Droit des Sociétés')">
                    <div class="welcome-card-icon">⚖️</div>
                    <div class="welcome-card-label">Droit des Sociétés</div>
                    <div class="welcome-card-sub">Fiches & exercices</div>
                </div>
            </div>
        </div>

        <div class="iframe-wrapper" id="iframe-wrapper">
            <iframe id="content-frame"></iframe>
        </div>

        <div id="admin-panel">
            <div class="admin-content">
                <div class="admin-header">
                    <div>
                        <div class="admin-title">⚙️ Administration</div>
                        <div class="admin-subtitle">Gestion des codes d'accès et ressources</div>
                    </div>
                    <div style="display:flex;gap:8px;flex-wrap:wrap">
                        <button class="btn-gen" onclick="loadCodes()" style="background:var(--bg3);border:1px solid var(--border);color:var(--text);box-shadow:none">↺ Actualiser</button>
                        <button class="btn-gen" onclick="kickAll()" style="background:rgba(255,92,122,.12);border:1px solid rgba(255,92,122,.3);color:var(--danger);box-shadow:none">⚡ Déco. tout</button>
                    </div>
                </div>

                <div class="stats-row">
                    <div class="stat-card"><div class="stat-value" id="stat-total">—</div><div class="stat-label">Codes créés</div></div>
                    <div class="stat-card"><div class="stat-value" id="stat-active" style="color:var(--green)">—</div><div class="stat-label">Actifs</div></div>
                    <div class="stat-card"><div class="stat-value" id="stat-online" style="color:var(--cyan)">—</div><div class="stat-label">En ligne</div></div>
                    <div class="stat-card"><div class="stat-value" id="stat-revoked" style="color:var(--muted)">—</div><div class="stat-label">Révoqués</div></div>
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
                            <thead><tr><th>Code</th><th>Nom</th><th>Note</th><th>Statut</th><th>Dernière activité</th><th>Actions</th></tr></thead>
                            <tbody id="codes-tbody"><tr><td colspan="6" style="text-align:center;color:var(--muted);padding:20px">Chargement…</td></tr></tbody>
                        </table>
                    </div>
                </div>

                <!-- ── SECTION RESSOURCES PDF ── -->
                <div class="section-card" style="border-color:rgba(6,214,214,.15)">
                    <div class="section-title" style="display:flex;align-items:center;justify-content:space-between;margin-bottom:16px">
                        <span>📎 Infos complémentaires — Ressources PDF / Liens</span>
                        <button class="btn-gen" onclick="loadResources()" style="padding:6px 14px;font-size:.72rem;background:var(--bg3);border:1px solid var(--border);color:var(--text);box-shadow:none">↺</button>
                    </div>
                    <div class="gen-form" style="margin-bottom:20px">
                        <div class="form-field" style="flex:0 0 70px;min-width:60px">
                            <label class="form-label">Icône</label>
                            <input type="text" class="form-input" id="res-icon" placeholder="📄" maxlength="4" style="text-align:center;font-size:1.1rem">
                        </div>
                        <div class="form-field" style="flex:2">
                            <label class="form-label">Nom du lien</label>
                            <input type="text" class="form-input" id="res-label" placeholder="Ex : Corrigé UE441 DS2">
                        </div>
                        <div class="form-field" style="flex:3">
                            <label class="form-label">URL (PDF, Drive, site…)</label>
                            <input type="text" class="form-input" id="res-url" placeholder="https://…">
                        </div>
                        <button class="btn-gen" id="btn-res-add" onclick="addResource()" style="background:linear-gradient(135deg,#06d6d6,#a855f7)">+ Ajouter</button>
                    </div>
                    <div class="codes-table-wrap">
                        <table class="codes-table">
                            <thead><tr><th style="width:44px">Icône</th><th>Nom</th><th>URL</th><th>Actions</th></tr></thead>
                            <tbody id="res-tbody"><tr><td colspan="4" style="text-align:center;color:var(--muted);padding:20px">Chargement…</td></tr></tbody>
                        </table>
                    </div>
                </div>

                <div class="section-card" style="border-color:rgba(255,209,102,.15)">
                    <div class="section-title">📢 Message broadcast</div>
                    <p style="font-size:.78rem;color:var(--muted);margin-bottom:16px;line-height:1.6">Envoie un message visible par tous les étudiants connectés. Il apparaît en bandeau en haut de leur hub.</p>
                    <div class="gen-form" style="margin-bottom:14px">
                        <div class="form-field" style="flex:3">
                            <label class="form-label">Message</label>
                            <input type="text" class="form-input" id="bc-text" placeholder="Ex : 🆕 Fiche Finance disponible !" maxlength="120">
                        </div>
                        <div class="form-field" style="flex:0 0 130px;min-width:110px">
                            <label class="form-label">Icône</label>
                            <input type="text" class="form-input" id="bc-icon" placeholder="📢" maxlength="4" style="text-align:center;font-size:1.1rem">
                        </div>
                        <button class="btn-gen" id="btn-bc-send" onclick="sendBroadcast()" style="background:linear-gradient(135deg,#ffd166,#ff9f1c);color:#000">Envoyer →</button>
                    </div>
                    <div style="display:flex;gap:8px;flex-wrap:wrap">
                        <button class="btn-action btn-copy" onclick="clearBroadcast()" style="padding:6px 14px;font-size:.75rem">🗑 Effacer le message actuel</button>
                        <div id="bc-current" style="font-size:.75rem;color:var(--muted);display:flex;align-items:center;gap:6px"></div>
                    </div>
                </div>

                <div class="section-card">
                    <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:16px">
                        <div class="section-title" style="margin-bottom:0">🕓 Historique</div>
                        <button class="btn-gen" onclick="loadLogs()" style="padding:6px 14px;font-size:.72rem;background:var(--bg3);border:1px solid var(--border);color:var(--text);box-shadow:none">↺</button>
                    </div>
                    <div class="codes-table-wrap">
                        <table class="codes-table">
                            <thead><tr><th>Nom</th><th>Code</th><th>Connecté le</th></tr></thead>
                            <tbody id="logs-tbody"><tr><td colspan="3" style="text-align:center;color:var(--muted);padding:20px">Chargement…</td></tr></tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div><!-- /admin-panel -->
        </div><!-- /main-content -->

        <!-- NOTES PANEL -->
        <div class="notes-panel" id="notes-panel">
            <div class="notes-header">
                <div class="notes-header-icon">📝</div>
                <div class="notes-header-info">
                    <div class="notes-header-title" id="notes-matiere-title">Mes notes</div>
                    <div class="notes-header-sub">Sauvegarde automatique</div>
                </div>
                <button class="notes-close" onclick="closeNotes()">✕</button>
            </div>
            <div class="notes-toolbar">
                <button class="notes-btn" onclick="fmt('bold')" title="Gras"><b>G</b></button>
                <button class="notes-btn" onclick="fmt('italic')" title="Italique"><i>I</i></button>
                <button class="notes-btn" onclick="fmt('underline')" title="Souligné"><u>S</u></button>
                <button class="notes-btn" onclick="fmt('strikeThrough')" title="Barré"><s>B</s></button>
                <div style="width:1px;background:var(--border);margin:0 2px"></div>
                <button class="notes-btn" onclick="fmtBlock('h3')" title="Titre">T</button>
                <button class="notes-btn" onclick="fmtBlock('insertUnorderedList')" title="Liste">• Liste</button>
                <button class="notes-btn" onclick="fmtBlock('insertOrderedList')" title="Liste numérotée">1. Liste</button>
                <div style="width:1px;background:var(--border);margin:0 2px"></div>
                <button class="notes-btn" onclick="fmtBlock('formatBlock','blockquote')" title="Citation">❝</button>
                <button class="notes-btn" onclick="clearNotes()" style="margin-left:auto;color:var(--danger)" title="Effacer">🗑</button>
            </div>
            <div class="notes-editor" id="notes-editor"
                contenteditable="true"
                spellcheck="false"
                data-placeholder="Tes notes personnelles pour cette matière...&#10;&#10;Sauvegarde automatique activée ✓"
                oninput="onNotesInput()"></div>
            <div class="notes-footer">
                <div class="notes-save-status">
                    <div class="notes-save-dot" id="notes-dot"></div>
                    <span id="notes-status-text">Prêt</span>
                </div>
                <div class="notes-char-count"><span id="notes-char">0</span> car.</div>
            </div>
        </div>

        </div><!-- /main-body -->
    </main>
</div>

<div class="toast" id="toast"></div>

<script>
const SB_URL = 'https://qridhnhidcrfffzejzgt.supabase.co';
const SB_KEY = 'sb_publishable_iELf6p0T6VpTWFNP6Hc9_g_TAzUmz9E';
const SESSION_KEY = 'hub_sess';
const SAVED_CODE_KEY = 'hub_last_code';
function getSavedCode(){try{return JSON.parse(localStorage.getItem(SAVED_CODE_KEY));}catch{return null;}}
function saveLastCode(code,name){localStorage.setItem(SAVED_CODE_KEY,JSON.stringify({code,name}));}

function makeCode() {
    const L='ABCDEFGHJKLMNPQRSTUVWXYZ',D='23456789';
    return Array.from({length:4},()=>L[Math.floor(Math.random()*L.length)]).join('')+
           Array.from({length:4},()=>D[Math.floor(Math.random()*D.length)]).join('');
}
function makeToken(){return Math.random().toString(36).slice(2)+Date.now().toString(36);}
function fmtDate(iso){if(!iso)return'—';return new Date(iso).toLocaleString('fr-FR',{day:'2-digit',month:'2-digit',year:'numeric',hour:'2-digit',minute:'2-digit'});}
function showToast(msg,type='success'){const t=document.getElementById('toast');t.textContent=msg;t.className='toast visible '+type;clearTimeout(t._t);t._t=setTimeout(()=>{t.className='toast';},3200);}

const H=()=>({'apikey':SB_KEY,'Authorization':`Bearer ${SB_KEY}`,'Content-Type':'application/json','Prefer':'return=representation'});
async function sbSelect(q){const r=await fetch(`${SB_URL}/rest/v1/${q}`,{headers:H()});return r.ok?await r.json():null;}
async function sbInsert(t,b){const r=await fetch(`${SB_URL}/rest/v1/${t}`,{method:'POST',headers:H(),body:JSON.stringify(b)});return r.ok?await r.json():null;}
async function sbUpdate(t,f,b){const p=Object.entries(f).map(([k,v])=>`${k}=eq.${encodeURIComponent(v)}`).join('&');const r=await fetch(`${SB_URL}/rest/v1/${t}?${p}`,{method:'PATCH',headers:H(),body:JSON.stringify(b)});return r.ok;}
async function sbDelete(t,f){const p=Object.entries(f).map(([k,v])=>`${k}=eq.${encodeURIComponent(v)}`).join('&');const r=await fetch(`${SB_URL}/rest/v1/${t}?${p}`,{method:'DELETE',headers:H()});return r.ok;}




// ── THÈME CLAIR/SOMBRE ───────────────────────────────────────────────────

const THEME_KEY = 'hub_theme';

function applyTheme(theme) {
    const moon = document.getElementById('theme-icon-moon');
    const sun = document.getElementById('theme-icon-sun');
    if (theme === 'light') {
        document.body.classList.add('light-theme');
        if (moon) moon.style.display = 'none';
        if (sun) sun.style.display = '';
    } else {
        document.body.classList.remove('light-theme');
        if (moon) moon.style.display = '';
        if (sun) sun.style.display = 'none';
    }
}

function toggleTheme() {
    const isLight = document.body.classList.contains('light-theme');
    const next = isLight ? 'dark' : 'light';
    localStorage.setItem(THEME_KEY, next);
    applyTheme(next);
}

function initTheme() {
    const saved = localStorage.getItem(THEME_KEY) || 'dark';
    applyTheme(saved);
}

// ── ONBOARDING ────────────────────────────────────────────────────────────

const OB_KEY = 'hub_onboarding_done';
let obCur = 0;
const obTotal = 5;

function showOnboarding() {
    // Ne pas montrer à l'admin
    if (session && session.isAdmin) return;
    // Ne pas montrer si déjà vu
    if (localStorage.getItem(OB_KEY)) return;
    document.getElementById('ob-overlay').classList.add('visible');
}

function obNext() {
    if (obCur >= obTotal - 1) { obSkip(); return; }
    document.getElementById('ob-slide-' + obCur).classList.remove('active');
    document.getElementById('ob-d' + obCur).classList.remove('active');
    obCur++;
    document.getElementById('ob-slide-' + obCur).classList.add('active');
    document.getElementById('ob-d' + obCur).classList.add('active');
    document.getElementById('ob-counter').textContent = (obCur + 1) + ' / ' + obTotal;
    if (obCur === obTotal - 1) {
        document.getElementById('ob-btn-next').textContent = 'Commencer →';
        document.getElementById('ob-btn-skip').style.display = 'none';
    }
}

function obSkip() {
    document.getElementById('ob-overlay').classList.remove('visible');
    localStorage.setItem(OB_KEY, '1');
}

// ── NOTES PERSONNELLES ────────────────────────────────────────────────────

let currentMatiere = null;
let notesSaveTimer = null;
let notesLoaded = {};

async function openNotes(e, matiere) {
    e.stopPropagation();
    if(window.innerWidth <= 768) closeSidebar();

    // Si même matière déjà ouverte, toggle
    const panel = document.getElementById('notes-panel');
    if (currentMatiere === matiere && panel.classList.contains('open')) {
        closeNotes(); return;
    }

    currentMatiere = matiere;
    document.getElementById('notes-matiere-title').textContent = 'Notes — ' + matiere;
    panel.classList.add('open');

    // Charger les notes depuis Supabase
    setNoteStatus('loading');
    const rows = await sbSelect('notes?code=eq.' + encodeURIComponent(session.code) + '&matiere=eq.' + encodeURIComponent(matiere) + '&select=*');
    const editor = document.getElementById('notes-editor');
    if (rows && rows.length > 0) {
        editor.innerHTML = rows[0].content || '';
        notesLoaded[matiere] = rows[0].id;
    } else {
        editor.innerHTML = '';
        notesLoaded[matiere] = null;
    }
    updateNotesChar();
    setNoteStatus('saved');
}

function closeNotes() {
    document.getElementById('notes-panel').classList.remove('open');
    currentMatiere = null;
}

function fmt(cmd) {
    document.getElementById('notes-editor').focus();
    document.execCommand(cmd, false, null);
    onNotesInput();
}

function fmtBlock(cmd, val) {
    document.getElementById('notes-editor').focus();
    document.execCommand(cmd, false, val || null);
    onNotesInput();
}

function onNotesInput() {
    updateNotesChar();
    setNoteStatus('saving');
    clearTimeout(notesSaveTimer);
    notesSaveTimer = setTimeout(saveNotes, 1200);
}

async function saveNotes() {
    if (!currentMatiere || !session) return;
    const ed = document.getElementById('notes-editor');
    const htmlContent = ed.innerHTML;
    const matiere = currentMatiere;
    const code = session.code;

    if (notesLoaded[matiere]) {
        await sbUpdate('notes', {id: notesLoaded[matiere]}, {content: htmlContent, updated_at: new Date().toISOString()});
    } else {
        const res = await sbInsert('notes', {code, matiere, content: htmlContent});
        if (res && res.length > 0) notesLoaded[matiere] = res[0].id;
    }
    setNoteStatus('saved');
    updateNotesBtns(matiere, ed.innerText.trim().length > 0);
}

function setNoteStatus(state) {
    const dot = document.getElementById('notes-dot');
    const txt = document.getElementById('notes-status-text');
    if (!dot || !txt) return;
    if (state === 'saving') {
        dot.className = 'notes-save-dot saving';
        txt.textContent = 'Sauvegarde...';
    } else if (state === 'saved') {
        dot.className = 'notes-save-dot saved';
        txt.textContent = 'Sauvegardé ✓';
    } else {
        dot.className = 'notes-save-dot';
        txt.textContent = 'Chargement...';
    }
}

function updateNotesChar() {
    const el = document.getElementById('notes-char');
    const ed = document.getElementById('notes-editor');
    if (el && ed) el.textContent = ed.innerText.length;
}

function updateNotesBtns(matiere, hasContent) {
    document.querySelectorAll('.notes-toggle-btn').forEach(btn => {
        if ((btn.getAttribute('onclick') || '').includes("'" + matiere + "'")) {
            btn.classList.toggle('has-notes', hasContent);
        }
    });
}

function clearNotes() {
    if (!confirm('Effacer toutes les notes de cette matière ?')) return;
    const ed = document.getElementById('notes-editor');
    ed.innerHTML = '';
    updateNotesChar();
    saveNotes();
}

// ── BROADCAST ─────────────────────────────────────────────────────────────

let lastBroadcastId = null;

async function loadBroadcast() {
    const rows = await sbSelect('broadcast?order=created_at.desc&limit=1&select=*');
    if (!rows || !rows.length) { hideBroadcastBanner(); updateBcCurrent(null); return; }
    const msg = rows[0];
    updateBcCurrent(msg);
    if (!msg.active) { hideBroadcastBanner(); return; }
    // Ne pas ré-afficher si l'étudiant a déjà fermé ce message
    const dismissed = localStorage.getItem('bc_dismissed');
    if (dismissed === String(msg.id)) return;
    if (lastBroadcastId !== msg.id) {
        lastBroadcastId = msg.id;
        showBroadcastBanner(msg.icon || '📢', msg.message);
    }
}

function showBroadcastBanner(icon, text) {
    const banner = document.getElementById('broadcast-banner');
    document.getElementById('broadcast-icon').textContent = icon;
    document.getElementById('broadcast-text').innerHTML = text;
    banner.classList.add('visible');
}

function hideBroadcastBanner() {
    document.getElementById('broadcast-banner').classList.remove('visible');
}

function closeBroadcast() {
    hideBroadcastBanner();
    if (lastBroadcastId) localStorage.setItem('bc_dismissed', String(lastBroadcastId));
}

function updateBcCurrent(msg) {
    const el = document.getElementById('bc-current');
    if (!el) return;
    if (!msg || !msg.active) { el.innerHTML = '<span style="color:var(--muted)">Aucun message actif</span>'; return; }
    el.innerHTML = `<span style="color:var(--yellow)">${escHtml(msg.icon||'📢')} ${escHtml(msg.message)}</span>`;
}

async function sendBroadcast() {
    const text = document.getElementById('bc-text').value.trim();
    const icon = document.getElementById('bc-icon').value.trim() || '📢';
    if (!text) { showToast('Remplis le message avant d\'envoyer.', 'error'); return; }
    const btn = document.getElementById('btn-bc-send');
    btn.disabled = true; btn.textContent = '…';
    // Désactiver les anciens messages
    await fetch(`${SB_URL}/rest/v1/broadcast?active=eq.true&id=neq.00000000-0000-0000-0000-000000000000`, {
        method: 'PATCH',
        headers: {'apikey': SB_KEY, 'Authorization': `Bearer ${SB_KEY}`, 'Content-Type': 'application/json', 'Prefer': 'return=minimal'},
        body: JSON.stringify({active: false})
    });
    const res = await sbInsert('broadcast', {message: text, icon, active: true});
    if (res) {
        document.getElementById('bc-text').value = '';
        document.getElementById('bc-icon').value = '';
        showToast('✓ Message envoyé à tous les étudiants !');
        await loadBroadcast();
    } else {
        showToast('Erreur lors de l\'envoi.', 'error');
    }
    btn.disabled = false; btn.textContent = 'Envoyer →';
}

async function clearBroadcast() {
    if (!confirm('Effacer le message actuel ?')) return;
    await fetch(`${SB_URL}/rest/v1/broadcast?active=eq.true&id=neq.00000000-0000-0000-0000-000000000000`, {
        method: 'PATCH',
        headers: {'apikey': SB_KEY, 'Authorization': `Bearer ${SB_KEY}`, 'Content-Type': 'application/json', 'Prefer': 'return=minimal'},
        body: JSON.stringify({active: false})
    });
    showToast('Message effacé.');
    hideBroadcastBanner();
    updateBcCurrent(null);
}

function escHtml(s){if(!s)return'';return String(s).replace(/&/g,'&amp;').replace(/"/g,'&quot;').replace(/</g,'&lt;').replace(/>/g,'&gt;');}

let session=null;
function getSession(){try{return JSON.parse(localStorage.getItem(SESSION_KEY));}catch{return null;}}
function saveSession(s){localStorage.setItem(SESSION_KEY,JSON.stringify(s));}
function clearSession(){localStorage.removeItem(SESSION_KEY);}

document.getElementById('code-input').addEventListener('keydown',e=>{if(e.key==='Enter')handleLogin();});

async function handleLogin(){
    const val=document.getElementById('code-input').value.trim().toUpperCase();
    const btn=document.getElementById('btn-login');
    const errEl=document.getElementById('login-error');
    const errMsg=document.getElementById('login-error-msg');
    const input=document.getElementById('code-input');
    if(!val)return;
    input.classList.remove('error');errEl.classList.remove('visible');
    btn.disabled=true;btn.innerHTML='<span class="spinner"></span>';

    try{
        const adminRes=await fetch(`${SB_URL}/functions/v1/admin-login`,{
            method:'POST',headers:{'Content-Type':'application/json'},
            body:JSON.stringify({code:val})
        });
        if(adminRes.ok){const data=await adminRes.json();if(data.isAdmin){session={code:val,isAdmin:true};saveSession(session);saveLastCode(val,'Administrateur');enterHub();return;}}
    }catch(e){}

    try{
        const rows=await sbSelect(`access_codes?code=eq.${val}&select=*`);
        if(!rows||rows.length===0)throw new Error('Code introuvable. Vérifie la saisie.');
        const row=rows[0];
        if(!row.is_active)throw new Error('Ce code a été révoqué. Contacte l\'administrateur.');
        const token=makeToken();
        await sbUpdate('access_codes',{code:val},{session_token:token,last_seen_at:new Date().toISOString()});
        session={code:val,token,isAdmin:false,name:row.name};
        saveSession(session);
        sbInsert('connection_logs',{code:val,name:row.name||null}); saveLastCode(val, row.name||'Étudiant');
        enterHub();
    }catch(err){
        errMsg.textContent=err.message||'Erreur de connexion.';
        errEl.classList.add('visible');input.classList.add('error');
    }
    btn.disabled=false;btn.innerHTML='Accéder au hub →';
}

let heartbeat=null;
function startHeartbeat(){
    heartbeat=setInterval(async()=>{
        if(!session||session.isAdmin)return;
        const rows=await sbSelect(`access_codes?code=eq.${session.code}&select=is_active,session_token`);
        if(!rows||rows.length===0)return;
        const row=rows[0];
        if(!row.is_active){clearSession();showToast('⚠️ Accès révoqué.','error');setTimeout(()=>location.reload(),2500);return;}
        if(row.session_token!==session.token){clearSession();showToast('⚠️ Session expirée : autre appareil.','error');setTimeout(()=>location.reload(),2800);return;}
        await sbUpdate('access_codes',{code:session.code},{last_seen_at:new Date().toISOString()});
        loadResources();
        loadBroadcast();
    },30000);
}

function enterHub(){
    document.getElementById('login-screen').style.display='none';
    document.getElementById('hub-screen').classList.add('visible');
    if(session.isAdmin){
        document.getElementById('admin-menu-item').style.display='flex';
        document.getElementById('admin-divider').style.display='block';
        document.getElementById('footer-name').textContent='Administrateur';
        document.getElementById('footer-role').textContent='Admin';
        document.getElementById('footer-avatar').textContent='A';
        document.getElementById('footer-avatar').style.background='linear-gradient(135deg,#ffd166,#ff9f1c)';
    }else{
        const prenom=session.name?session.name.split(' ')[0]:'Étudiant';
        document.getElementById('footer-name').textContent=session.name||'Étudiant';
        document.getElementById('footer-role').textContent='Étudiant';
        document.getElementById('footer-avatar').textContent=prenom[0].toUpperCase();
        const wt=document.getElementById('welcome-title');
        if(wt)wt.innerHTML=`Bonne <span>révision</span>, ${prenom} !`;
        startHeartbeat();
    }
    loadResources();
    loadBroadcast();
    setTimeout(showOnboarding, 800);
}

async function handleLogout(){
    if(heartbeat)clearInterval(heartbeat);
    if(session&&!session.isAdmin)await sbUpdate('access_codes',{code:session.code},{session_token:null});
    clearSession();location.reload();
}

let currentFile=null;
function loadPage(fileName,el,label){
    currentFile=fileName;
    document.querySelectorAll('.menu-item').forEach(i=>i.classList.remove('active'));
    if(el)el.classList.add('active');
    else document.querySelectorAll('.menu-item').forEach(item=>{if((item.getAttribute('onclick')||'').includes(`'${fileName}'`))item.classList.add('active');});
    document.getElementById('admin-panel').classList.remove('visible');
    document.getElementById('welcome').classList.add('hidden');
    document.getElementById('iframe-wrapper').classList.add('visible');
    document.getElementById('btn-home').style.display='block';
    if(window.innerWidth<=768)closeSidebar();
    if(label)document.getElementById('current-page').textContent=label;
    const loader=document.getElementById('loader');loader.className='loader loading';
    const frame=document.getElementById('content-frame');
    frame.onload=()=>{loader.className='loader done';setTimeout(()=>loader.className='loader',600);};
    frame.src=fileName;
}

function openAdmin(){
    document.querySelectorAll('.menu-item').forEach(i=>i.classList.remove('active'));
    document.getElementById('admin-menu-item').classList.add('active');
    document.getElementById('welcome').classList.add('hidden');
    document.getElementById('iframe-wrapper').classList.remove('visible');
    document.getElementById('admin-panel').classList.add('visible');
    document.getElementById('current-page').textContent='Administration';
    document.getElementById('btn-home').style.display='block';
    if(window.innerWidth<=768)closeSidebar();
    loadCodes();loadLogs();loadResources();loadBroadcast();
}

function goHome(){
    currentFile=null;
    document.querySelectorAll('.menu-item').forEach(i=>i.classList.remove('active'));
    document.getElementById('iframe-wrapper').classList.remove('visible');
    document.getElementById('admin-panel').classList.remove('visible');
    document.getElementById('welcome').classList.remove('hidden');
    document.getElementById('current-page').textContent='Accueil';
    document.getElementById('btn-home').style.display='none';
}

function reloadFrame(){if(!currentFile)return;const loader=document.getElementById('loader');loader.className='loader loading';const frame=document.getElementById('content-frame');frame.onload=()=>{loader.className='loader done';setTimeout(()=>loader.className='loader',600);};frame.src=currentFile;}
function openFullscreen(){const frame=document.getElementById('content-frame');if(frame.requestFullscreen)frame.requestFullscreen();}

async function loadCodes(){
    const tbody=document.getElementById('codes-tbody');
    tbody.innerHTML='<tr><td colspan="6" style="text-align:center;color:var(--muted);padding:20px">Chargement…</td></tr>';
    const rows=await sbSelect('access_codes?order=created_at.desc&select=*');
    if(!rows){tbody.innerHTML='<tr><td colspan="6" style="text-align:center;color:var(--muted);padding:20px">Erreur.</td></tr>';return;}
    const now=Date.now();let active=0,online=0,revoked=0;
    rows.forEach(r=>{if(!r.is_active){revoked++;return;}active++;if(r.last_seen_at&&(now-new Date(r.last_seen_at).getTime())<90000)online++;});
    document.getElementById('stat-total').textContent=rows.length;
    document.getElementById('stat-active').textContent=active;
    document.getElementById('stat-online').textContent=online;
    document.getElementById('stat-revoked').textContent=revoked;
    if(!rows.length){tbody.innerHTML='<tr><td colspan="6" style="text-align:center;color:var(--muted);padding:20px">Aucun code.</td></tr>';return;}
    tbody.innerHTML=rows.map(r=>{
        const isOnline=r.last_seen_at&&(now-new Date(r.last_seen_at).getTime())<90000;
        const badge=!r.is_active?'<span class="badge badge-revoked">Révoqué</span>':isOnline?'<span class="badge badge-online">En ligne</span>':'<span class="badge badge-active">Actif</span>';
        const acts=`<div class="actions-cell"><button class="btn-action btn-copy" onclick="copyCode('${r.code}')">Copier</button>${r.is_active?`<button class="btn-action btn-revoke" onclick="revokeCode('${r.id}')">Révoquer</button>${r.session_token?`<button class="btn-action btn-kick" onclick="kickCode('${r.id}')">Déco.</button>`:''}`:`<button class="btn-action btn-restore" onclick="restoreCode('${r.id}')">Réactiver</button>`}<button class="btn-action btn-delete" onclick="deleteCode('${r.id}','${r.code}')">Suppr.</button></div>`;
        return`<tr><td><span class="code-pill">${r.code}</span></td><td>${r.name||'<span style="color:var(--muted)">—</span>'}</td><td style="color:var(--muted);font-size:.75rem">${r.note||'—'}</td><td>${badge}</td><td style="color:var(--muted);font-size:.75rem">${fmtDate(r.last_seen_at)}</td><td>${acts}</td></tr>`;
    }).join('');
}

async function generateCode(){
    const name=document.getElementById('gen-name').value.trim();
    const note=document.getElementById('gen-note').value.trim();
    const btn=document.getElementById('btn-gen');
    btn.disabled=true;btn.innerHTML='<span class="spinner" style="border-color:rgba(255,255,255,.3);border-top-color:#fff"></span>';
    const code=makeCode();
    const res=await sbInsert('access_codes',{code,name:name||null,note:note||null,is_active:true});
    if(res){document.getElementById('gen-name').value='';document.getElementById('gen-note').value='';showToast(`✓ Code créé : ${code}${name?' — '+name:''}`);await loadCodes();}
    else showToast('Erreur.','error');
    btn.disabled=false;btn.textContent='+ Générer';
}

async function revokeCode(id){if(!confirm('Révoquer ce code ?'))return;const ok=await sbUpdate('access_codes',{id},{is_active:false,session_token:null});ok?showToast('Code révoqué.'):showToast('Erreur.','error');await loadCodes();}
async function restoreCode(id){const ok=await sbUpdate('access_codes',{id},{is_active:true});ok?showToast('Code réactivé.'):showToast('Erreur.','error');await loadCodes();}
async function kickCode(id){const ok=await sbUpdate('access_codes',{id},{session_token:null});ok?showToast('Déconnecté.'):showToast('Erreur.','error');await loadCodes();}
async function deleteCode(id,code){if(!confirm(`Supprimer "${code}" ?`))return;const ok=await sbDelete('access_codes',{id});ok?showToast(`✓ "${code}" supprimé.`):showToast('Erreur.','error');await loadCodes();}

async function loadLogs(){
    const tbody=document.getElementById('logs-tbody');if(!tbody)return;
    const rows=await sbSelect('connection_logs?order=connected_at.desc&limit=50&select=*');
    if(!rows||rows.length===0){tbody.innerHTML='<tr><td colspan="3" style="text-align:center;color:var(--muted);padding:20px">Aucune connexion.</td></tr>';return;}
    tbody.innerHTML=rows.map(r=>`<tr><td>${r.name||'<span style="color:var(--muted)">—</span>'}</td><td><span class="code-pill">${r.code}</span></td><td style="color:var(--muted);font-size:.75rem">${fmtDate(r.connected_at)}</td></tr>`).join('');
}

async function kickAll(){
    if(!confirm("Déconnecter TOUS les étudiants ?"))return;
    const res=await fetch(`${SB_URL}/rest/v1/access_codes?is_active=eq.true`,{method:"PATCH",headers:{"apikey":SB_KEY,"Authorization":`Bearer ${SB_KEY}`,"Content-Type":"application/json"},body:JSON.stringify({session_token:null})});
    if(res.ok){showToast("✓ Tout le monde déconnecté.");await loadCodes();}else showToast("Erreur.","error");
}

function copyCode(code){navigator.clipboard.writeText(code).then(()=>showToast(`✓ "${code}" copié !`)).catch(()=>{const el=document.createElement('textarea');el.value=code;document.body.appendChild(el);el.select();document.execCommand('copy');document.body.removeChild(el);showToast(`✓ "${code}" copié !`);});}

// ── RESSOURCES PDF / LIENS ─────────────────────────────────────────────────

async function loadResources(){
    const rows=await sbSelect('resources?order=created_at.asc&select=*');
    renderResourcesSidebar(rows||[]);
    renderResourcesAdmin(rows||[]);
}

function renderResourcesSidebar(rows){
    const el=document.getElementById('ressources-list-sidebar');
    if(!el)return;
    if(!rows.length){
        el.innerHTML='<li class="menu-item" style="pointer-events:none"><span style="font-size:.72rem;color:var(--muted)">Aucune ressource.</span></li>';
        return;
    }
    el.innerHTML=rows.map(r=>`
        <li class="menu-item res-item" onclick="window.open('${escHtml(r.url)}','_blank')">
            <div class="item-icon" style="font-size:16px">${escHtml(r.icon||'📄')}</div>
            <span class="item-label" style="font-size:.78rem;white-space:nowrap;overflow:hidden;text-overflow:ellipsis">${escHtml(r.label)}</span>
            <span class="item-arrow">↗</span>
        </li>`).join('');
}

function renderResourcesAdmin(rows){
    const tbody=document.getElementById('res-tbody');
    if(!tbody)return;
    if(!rows.length){
        tbody.innerHTML='<tr><td colspan="4" style="text-align:center;color:var(--muted);padding:20px">Aucune ressource. Utilisez le formulaire ci-dessus pour en ajouter.</td></tr>';
        return;
    }
    tbody.innerHTML=rows.map((r,i)=>`
        <tr>
            <td style="font-size:1.3rem;text-align:center">${escHtml(r.icon||'📄')}</td>
            <td style="font-weight:600;color:var(--white);max-width:180px;word-break:break-word">${escHtml(r.label)}</td>
            <td style="max-width:260px">
                <a href="${escHtml(r.url)}" target="_blank"
                   style="color:var(--cyan);font-size:.73rem;word-break:break-all;text-decoration:none;opacity:.85"
                   onmouseover="this.style.opacity=1" onmouseout="this.style.opacity=.85">
                    ${escHtml(r.url.length>55?r.url.slice(0,55)+'…':r.url)}
                </a>
            </td>
            <td>
                <div class="actions-cell">
                    <button class="btn-action btn-copy" onclick="copyCode('${escHtml(r.url)}')">Copier URL</button>
                    ${i>0?`<button class="btn-action" style="border-color:var(--border);color:var(--muted)" onclick="moveResource('${r.id}','up')">↑</button>`:''}
                    ${i<rows.length-1?`<button class="btn-action" style="border-color:var(--border);color:var(--muted)" onclick="moveResource('${r.id}','down')">↓</button>`:''}
                    <button class="btn-action btn-delete" onclick="deleteResource('${r.id}','${escHtml(r.label)}')">Suppr.</button>
                </div>
            </td>
        </tr>`).join('');
}

async function addResource(){
    const icon=document.getElementById('res-icon').value.trim()||'📄';
    const label=document.getElementById('res-label').value.trim();
    const url=document.getElementById('res-url').value.trim();
    if(!label||!url){showToast('Remplis le nom et l\'URL.','error');return;}
    const btn=document.getElementById('btn-res-add');
    btn.disabled=true;btn.innerHTML='<span class="spinner" style="border-color:rgba(255,255,255,.3);border-top-color:#fff"></span>';
    const res=await sbInsert('resources',{icon,label,url});
    if(res){
        document.getElementById('res-icon').value='';
        document.getElementById('res-label').value='';
        document.getElementById('res-url').value='';
        showToast(`✓ "${label}" ajouté.`);
        await loadResources();
    }else{
        showToast('Erreur lors de l\'ajout.','error');
    }
    btn.disabled=false;btn.textContent='+ Ajouter';
}

async function deleteResource(id,label){
    if(!confirm(`Supprimer "${label}" ?`))return;
    const ok=await sbDelete('resources',{id});
    ok?showToast(`✓ "${label}" supprimé.`):showToast('Erreur.','error');
    await loadResources();
}

async function moveResource(id,dir){
    // Reload current list, swap order via created_at trick (swap labels/urls)
    const rows=await sbSelect('resources?order=created_at.asc&select=*');
    if(!rows)return;
    const idx=rows.findIndex(r=>r.id===id);
    if(idx===-1)return;
    const swapIdx=dir==='up'?idx-1:idx+1;
    if(swapIdx<0||swapIdx>=rows.length)return;
    const a=rows[idx],b=rows[swapIdx];
    // Swap content (icon, label, url) between the two rows
    await Promise.all([
        sbUpdate('resources',{id:a.id},{icon:b.icon,label:b.label,url:b.url}),
        sbUpdate('resources',{id:b.id},{icon:a.icon,label:a.label,url:a.url})
    ]);
    await loadResources();
}

// ── SEARCH ─────────────────────────────────────────────────────────────────

const SEARCH_INDEX=[
    {notion:'Seuil de rentabilité',matiere:'Contrôle de Gestion',fichier:'CG.html',ancre:'',icon:'📊'},
    {notion:'Marge sur coût variable',matiere:'Contrôle de Gestion',fichier:'CG.html',ancre:'',icon:'📊'},
    {notion:'Analyse des écarts',matiere:'Contrôle de Gestion',fichier:'CG.html',ancre:'',icon:'📊'},
    {notion:'Bilan financier',matiere:'Finance',fichier:'FI.html',ancre:'',icon:'💰'},
    {notion:"Capacité d'autofinancement",matiere:'Finance',fichier:'FI.html',ancre:'',icon:'💰'},
    {notion:'Management participatif',matiere:'Management',fichier:'mana.html',ancre:'',icon:'👔'},
    {notion:'Capital social',matiere:'Droit des Sociétés',fichier:'SO.html',ancre:'',icon:'⚖️'},
    {notion:'Contrat de travail',matiere:'Droit du Travail',fichier:'DT.html',ancre:'',icon:'👷'},
    {notion:'TVA déductible',matiere:'Droit Fiscal',fichier:'fisca.html',ancre:'',icon:'🧾'},
    {notion:'Amortissement linéaire',matiere:'Comptabilité',fichier:'compta.html',ancre:'',icon:'📑'},
];

function highlight(text,query){if(!query)return text;const e=query.replace(/[.*+?^${}()|[\]\\]/g,'\\$&');return text.replace(new RegExp('('+e+')','gi'),'<span class="sri-mark">$1</span>');}

function handleSearch(val){
    const q=val.trim().toLowerCase();const box=document.getElementById('search-results');
    if(!q){box.innerHTML='';box.classList.remove('visible');return;}
    const results=SEARCH_INDEX.filter(item=>item.notion.toLowerCase().includes(q)||item.matiere.toLowerCase().includes(q)).slice(0,8);
    if(results.length===0){box.innerHTML='<div class="search-empty">Aucun résultat pour "'+val+'"</div>';box.classList.add('visible');return;}
    box.innerHTML=results.map(r=>'<div class="search-result-item" onclick="goToNotion(\''+r.fichier+'\',\''+r.ancre+'\',\''+r.matiere+'\')">'+'<div class="sri-icon">'+r.icon+'</div>'+'<div><div class="sri-notion">'+highlight(r.notion,val)+'</div>'+'<div class="sri-mat">'+r.matiere+'</div></div></div>').join('');
    box.classList.add('visible');
}

function showResults(){const val=document.getElementById('search-input').value.trim();if(val)handleSearch(val);}
function goToNotion(fichier,ancre,matiere){closeSearch();loadPage(fichier,null,matiere);if(ancre)setTimeout(function(){try{document.getElementById('content-frame').contentWindow.location.hash=ancre;}catch(e){}},800);}
function closeSearch(){document.getElementById('search-input').value='';const box=document.getElementById('search-results');box.innerHTML='';box.classList.remove('visible');}

document.addEventListener('click',e=>{if(!e.target.closest('.search-wrap'))document.getElementById('search-results').classList.remove('visible');});
document.addEventListener('keydown',e=>{
    if(e.key==='Escape'){closeSearch();return;}
    if((e.metaKey||e.ctrlKey)&&e.key==='k'){
        e.preventDefault();
        const inp=document.getElementById('search-input');
        inp.focus(); inp.select();
    }
});

function toggleSem(id){
    const items=document.getElementById('sem-'+id);
    if(!items)return;
    items.classList.toggle('open');
    // Trouve le header qui appelle toggleSem(id) via onclick
    const headers=document.querySelectorAll('.menu-semester');
    headers.forEach(h=>{if((h.getAttribute('onclick')||'').includes(`'${id}'`))h.classList.toggle('open');});
}
function toggleSidebar(){document.getElementById('sidebar').classList.contains('open')?closeSidebar():openSidebar();}
function openSidebar(){document.getElementById('sidebar').classList.add('open');document.getElementById('nav-overlay').classList.add('visible');}
function closeSidebar(){document.getElementById('sidebar').classList.remove('open');document.getElementById('nav-overlay').classList.remove('visible');}

function loginWithSaved(){
    const saved=getSavedCode();
    if(!saved)return;
    document.getElementById("code-input").value=saved.code;
    handleLogin();
}

(function(){
    initTheme();
    const s=getSession();
    if(s){session=s;enterHub();return;}
    const saved=getSavedCode();
    if(saved){
        const el=document.getElementById("last-session");
        const av=document.getElementById("ls-avatar");
        const nm=document.getElementById("ls-name");
        if(el&&av&&nm){
            av.textContent=saved.name.charAt(0).toUpperCase();
            if(saved.name==='Administrateur'){av.style.background='linear-gradient(135deg,#ffd166,#ff9f1c)';}
            nm.textContent="Continuer en tant que "+saved.name.split(" ")[0];
            el.classList.add("visible");
        }
    }
})();
</script>

<!-- ── ONBOARDING ── -->
<div class="ob-overlay" id="ob-overlay">
    <div class="ob-modal">

        <!-- Slide 1 — Bienvenue -->
        <div class="ob-slide active" id="ob-slide-0">
            <div class="ob-hero">
                <div class="ob-icon-wrap purple">📚</div>
                <div class="ob-title">Bienvenue sur Hub Révisions</div>
                <div class="ob-desc">Ton espace de révision Master CCA. Voici un rapide tour des fonctionnalités disponibles.</div>
            </div>
            <div class="ob-features">
                <div class="ob-feat">
                    <div class="ob-feat-icon purple">📄</div>
                    <div><div class="ob-feat-title">Fiches de révision</div><div class="ob-feat-sub">Notions clés, formules et annales analysées par matière</div></div>
                </div>
                <div class="ob-feat">
                    <div class="ob-feat-icon teal">🧠</div>
                    <div><div class="ob-feat-title">Quiz interactifs</div><div class="ob-feat-sub">Teste tes connaissances après chaque chapitre</div></div>
                </div>
                <div class="ob-feat">
                    <div class="ob-feat-icon amber">📝</div>
                    <div><div class="ob-feat-title">Notes personnelles</div><div class="ob-feat-sub">Un bloc-notes par matière, sauvegardé automatiquement</div></div>
                </div>
                <div class="ob-feat">
                    <div class="ob-feat-icon blue">📎</div>
                    <div><div class="ob-feat-title">Infos complémentaires</div><div class="ob-feat-sub">PDF et liens utiles ajoutés par ton formateur</div></div>
                </div>
            </div>
        </div>

        <!-- Slide 2 — Fiches -->
        <div class="ob-slide" id="ob-slide-1">
            <div class="ob-hero">
                <div class="ob-icon-wrap purple">📄</div>
                <div class="ob-title">Les fiches de révision</div>
                <div class="ob-desc">Chaque fiche est construite à partir des annales des 3 dernières années pour cibler exactement ce qui tombe au partiel.</div>
            </div>
            <div class="ob-features">
                <div class="ob-feat">
                    <div class="ob-feat-icon purple">🔥</div>
                    <div><div class="ob-feat-title">Tag fréquence</div><div class="ob-feat-sub">Les notions les plus fréquentes sont marquées pour savoir quoi prioriser</div></div>
                </div>
                <div class="ob-feat">
                    <div class="ob-feat-icon teal">🔢</div>
                    <div><div class="ob-feat-title">Formules détaillées</div><div class="ob-feat-sub">Chaque formule avec ses variables expliquées et un exemple chiffré</div></div>
                </div>
                <div class="ob-feat">
                    <div class="ob-feat-icon amber">📊</div>
                    <div><div class="ob-feat-title">Tableau récapitulatif</div><div class="ob-feat-sub">Vois exactement quelles notions sont tombées en 2022, 2023, 2024</div></div>
                </div>
            </div>
        </div>

        <!-- Slide 3 — Quiz -->
        <div class="ob-slide" id="ob-slide-2">
            <div class="ob-hero">
                <div class="ob-icon-wrap teal">🧠</div>
                <div class="ob-title">Les quiz interactifs</div>
                <div class="ob-desc">Un quiz à la fin de chaque chapitre, puis un quiz final mode partiel pour tester l'ensemble de tes connaissances.</div>
            </div>
            <div class="ob-features">
                <div class="ob-feat">
                    <div class="ob-feat-icon teal">✅</div>
                    <div><div class="ob-feat-title">Feedback immédiat</div><div class="ob-feat-sub">Chaque réponse expliquée en détail pour comprendre l'erreur</div></div>
                </div>
                <div class="ob-feat">
                    <div class="ob-feat-icon purple">🏆</div>
                    <div><div class="ob-feat-title">Score et progression</div><div class="ob-feat-sub">Vois ta progression sur chaque section et par matière</div></div>
                </div>

            </div>
        </div>

        <!-- Slide 4 — Notes -->
        <div class="ob-slide" id="ob-slide-3">
            <div class="ob-hero">
                <div class="ob-icon-wrap amber">📝</div>
                <div class="ob-title">Tes notes personnelles</div>
                <div class="ob-desc">Un bloc-notes intégré pour chaque matière. Clique sur le bouton 📝 dans le menu à côté de n'importe quelle matière.</div>
            </div>
            <div class="ob-features">
                <div class="ob-feat">
                    <div class="ob-feat-icon teal">💾</div>
                    <div><div class="ob-feat-title">Sauvegarde automatique</div><div class="ob-feat-sub">Tes notes sont sauvegardées instantanément et accessibles partout</div></div>
                </div>
                <div class="ob-feat">
                    <div class="ob-feat-icon purple">✏️</div>
                    <div><div class="ob-feat-title">Éditeur riche</div><div class="ob-feat-sub">Gras, italique, titres, listes — formate tes notes comme tu veux</div></div>
                </div>
                <div class="ob-feat">
                    <div class="ob-feat-icon blue">📱</div>
                    <div><div class="ob-feat-title">Multi-appareil</div><div class="ob-feat-sub">Consulte tes notes depuis ton téléphone ou ton ordinateur</div></div>
                </div>
            </div>
        </div>

        <!-- Slide 5 — C'est parti -->
        <div class="ob-slide" id="ob-slide-4">
            <div class="ob-hero">
                <div class="ob-icon-wrap green">🚀</div>
                <div class="ob-title">Tout est prêt !</div>
                <div class="ob-desc">Commence par sélectionner une matière dans le menu, ou lance-toi directement sur une fiche en page d'accueil.</div>
            </div>
            <div class="ob-checklist">
                <div class="ob-check-item"><div class="ob-check-icon">✓</div><span>Tes notes sont sauvegardées automatiquement</span></div>
                <div class="ob-check-item"><div class="ob-check-icon">✓</div><span>Utilise <kbd style="font-size:.7rem;padding:1px 6px;border-radius:4px;border:1px solid var(--border);background:var(--bg3)">⌘K</kbd> pour rechercher une notion rapidement</span></div>
                <div class="ob-check-item"><div class="ob-check-icon">✓</div><span>Clique sur 📝 dans le menu pour prendre des notes par matière</span></div>
                <div class="ob-check-item"><div class="ob-check-icon">✓</div><span>Le menu 📎 contient les PDF et ressources utiles</span></div>
                <div class="ob-check-item"><div class="ob-check-icon">✓</div><span>Les notions 🔥 sont les plus fréquentes aux partiels</span></div>
                <div class="ob-check-item"><div class="ob-check-icon">✓</div><span>Bascule entre mode sombre 🌙 et clair ☀️ via le bouton en haut à droite</span></div>
            </div>
        </div>

        <!-- Footer -->
        <div class="ob-footer">
            <div class="ob-dots">
                <div class="ob-dot active" id="ob-d0"></div>
                <div class="ob-dot" id="ob-d1"></div>
                <div class="ob-dot" id="ob-d2"></div>
                <div class="ob-dot" id="ob-d3"></div>
                <div class="ob-dot" id="ob-d4"></div>
            </div>
            <div class="ob-btns">
                <span class="ob-counter" id="ob-counter">1 / 5</span>
                <button class="ob-btn" id="ob-btn-skip" onclick="obSkip()">Passer</button>
                <button class="ob-btn primary" id="ob-btn-next" onclick="obNext()">Suivant →</button>
            </div>
        </div>
    </div>
</div>

</body>
</html>
