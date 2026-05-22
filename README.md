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
            display: flex; flex-direction: column; min-width: 0;
        }

        .topbar {
            height: 56px; flex-shrink: 0;
            background: var(--bg2); border-bottom: 1px solid var(--border);
            display: flex; align-items: center; padding: 0 24px; gap: 14px;
        }

        .topbar-breadcrumb { display: flex; align-items: center; gap: 8px; font-size: .78rem; color: var(--muted); }
        .topbar-breadcrumb span { color: var(--white); font-weight: 600; }
        .topbar-sep { color: var(--border); }
        .topbar-actions { margin-left: auto; display: flex; align-items: center; gap: 8px; }

        .btn-topbar {
            background: var(--bg3); border: 1px solid var(--border); border-radius: 10px;
            padding: 7px 14px; font-size: .72rem; color: var(--text); cursor: pointer;
            font-family: 'Plus Jakarta Sans', sans-serif;
            transition: border-color .15s, color .15s, transform .1s;
        }

        .btn-topbar:hover { border-color: var(--violet); color: var(--violet); transform: translateY(-1px); }

        .search-wrap { flex: 1; max-width: 360px; position: relative; margin: 0 10px; }

        .search-input {
            width: 100%; background: var(--bg3); border: 1.5px solid var(--border);
            border-radius: 10px; padding: 8px 14px 8px 36px;
            font-size: .78rem; color: var(--white);
            font-family: 'Plus Jakarta Sans', sans-serif; outline: none;
            transition: border-color .2s, box-shadow .2s;
        }

        .search-input::placeholder { color: var(--muted); }
        .search-input:focus { border-color: var(--violet); box-shadow: 0 0 0 3px rgba(168,85,247,.12); }

        .search-icon {
            position: absolute; left: 11px; top: 50%; transform: translateY(-50%);
            font-size: 14px; color: var(--muted); pointer-events: none;
        }

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

        @media (max-width: 768px) {
            .burger { display: flex; }
            nav {
                position: fixed; top: 0; left: 0; height: 100%;
                width: min(280px, 85vw); z-index: 100;
                transform: translateX(-100%);
                transition: transform .3s cubic-bezier(.4,0,.2,1); overflow-y: auto;
            }
            nav.open { transform: translateX(0); }
            .nav-overlay { display: block; }
            main { width: 100%; }
            .topbar { gap: 8px; padding: 0 14px; }
            .topbar-breadcrumb { display: none; }
            .welcome h1 { font-size: 1.6rem; }
            .welcome-cards { grid-template-columns: 1fr; max-width: 360px; }
            .login-card { padding: 32px 24px; }
            .admin-content { padding: 16px; }
            .gen-form { flex-direction: column; }
            .search-wrap { max-width: none; flex: 1; margin: 0 6px; }
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
            autocomplete="off" autocorrect="off" spellcheck="false">
        <button class="btn-login" id="btn-login" onclick="handleLogin()">Accéder au hub →</button>
        <div class="login-error" id="login-error">
            <span>⚠</span><span id="login-error-msg">Code incorrect ou révoqué.</span>
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
                    <div class="nav-sub">Licence CCA</div>
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
                <li class="menu-item"><div class="item-icon">📘</div><span class="item-label">Matière 1</span><span class="soon-badge">Bientôt</span></li>
                <li class="menu-item"><div class="item-icon">📗</div><span class="item-label">Matière 2</span><span class="soon-badge">Bientôt</span></li>
                <li class="menu-item"><div class="item-icon">📙</div><span class="item-label">Matière 3</span><span class="soon-badge">Bientôt</span></li>
                <li class="menu-item"><div class="item-icon">📕</div><span class="item-label">Matière 4</span><span class="soon-badge">Bientôt</span></li>
            </div>

            <div class="menu-semester" onclick="toggleSem('s2')">
                <span>Semestre 2</span><span class="sem-arrow">›</span>
            </div>
            <div class="sem-items" id="sem-s2">
                <li class="menu-item"><div class="item-icon">📘</div><span class="item-label">Matière 5</span><span class="soon-badge">Bientôt</span></li>
                <li class="menu-item"><div class="item-icon">📗</div><span class="item-label">Matière 6</span><span class="soon-badge">Bientôt</span></li>
                <li class="menu-item"><div class="item-icon">📙</div><span class="item-label">Matière 7</span><span class="soon-badge">Bientôt</span></li>
                <li class="menu-item"><div class="item-icon">📕</div><span class="item-label">Matière 8</span><span class="soon-badge">Bientôt</span></li>
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
                Hub Révisions <span class="topbar-sep">›</span>
                <span id="current-page">Accueil</span>
            </div>
            <div class="search-wrap">
                <span class="search-icon">🔍</span>
                <input type="text" id="search-input" class="search-input"
                    placeholder="Rechercher une notion…"
                    autocomplete="off" autocorrect="off" spellcheck="false"
                    oninput="handleSearch(this.value)" onfocus="showResults()">
                <div class="search-results" id="search-results"></div>
            </div>
            <div class="topbar-actions">
                <button class="btn-topbar" id="btn-home" onclick="goHome()" style="display:none">⌂</button>
                <button class="btn-topbar" onclick="reloadFrame()">↺</button>
                <button class="btn-topbar" onclick="openFullscreen()">⛶</button>
            </div>
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
        </div>
    </main>
</div>

<div class="toast" id="toast"></div>

<script>
const SB_URL = 'https://qridhnhidcrfffzejzgt.supabase.co';
const SB_KEY = 'sb_publishable_iELf6p0T6VpTWFNP6Hc9_g_TAzUmz9E';
const SESSION_KEY = 'hub_sess';

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
        if(adminRes.ok){const data=await adminRes.json();if(data.isAdmin){session={code:val,isAdmin:true};saveSession(session);enterHub();return;}}
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
        sbInsert('connection_logs',{code:val,name:row.name||null});
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
    loadCodes();loadLogs();loadResources();
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
document.addEventListener('keydown',e=>{if(e.key==='Escape')closeSearch();});

function toggleSem(id){const items=document.getElementById('sem-'+id);items.classList.toggle('open');items.previousElementSibling.classList.toggle('open');}
function toggleSidebar(){document.getElementById('sidebar').classList.contains('open')?closeSidebar():openSidebar();}
function openSidebar(){document.getElementById('sidebar').classList.add('open');document.getElementById('nav-overlay').classList.add('visible');}
function closeSidebar(){document.getElementById('sidebar').classList.remove('open');document.getElementById('nav-overlay').classList.remove('visible');}

(function(){const s=getSession();if(s){session=s;enterHub();}})();
</script>
</body>
</html>
