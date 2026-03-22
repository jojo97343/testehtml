<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Contrats à Long Terme – DCG 441</title>
<style>
* { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: 'Segoe UI', Arial, sans-serif; background: #f4f6fa; color: #222; font-size: 15px; }

.header { background: linear-gradient(135deg, #1a3a5c 0%, #2d6a9f 100%); color: white; padding: 28px 40px 20px; }
.header h1 { font-size: 22px; font-weight: 700; margin-bottom: 6px; }
.header p { font-size: 13px; opacity: 0.85; }
.badge { display: inline-block; background: rgba(255,255,255,0.2); border-radius: 20px; padding: 3px 12px; font-size: 12px; margin-top: 8px; margin-right: 6px; }

.tabs { display: flex; background: #fff; border-bottom: 2px solid #e0e6f0; padding: 0 30px; gap: 0; flex-wrap: wrap; }
.tab { padding: 11px 16px; cursor: pointer; font-size: 13px; font-weight: 500; color: #666; border-bottom: 3px solid transparent; margin-bottom: -2px; transition: all 0.2s; white-space: nowrap; }
.tab:hover { color: #2d6a9f; }
.tab.active { color: #2d6a9f; border-bottom-color: #2d6a9f; font-weight: 700; }

.content { padding: 26px 36px; max-width: 980px; margin: 0 auto; }
.section { display: none; }
.section.active { display: block; }

.scenario-box { background: linear-gradient(135deg, #1a3a5c, #2d6a9f); color: white; border-radius: 12px; padding: 22px 26px; margin-bottom: 22px; }
.scenario-box h2 { font-size: 19px; margin-bottom: 8px; }
.scenario-box p { font-size: 14px; line-height: 1.7; opacity: 0.92; }

.card { background: white; border-radius: 10px; padding: 20px 24px; margin-bottom: 18px; border: 1px solid #e0e6f0; box-shadow: 0 2px 6px rgba(0,0,0,0.05); }
.card h3 { font-size: 15px; font-weight: 700; color: #1a3a5c; margin-bottom: 12px; border-bottom: 2px solid #e8ecf5; padding-bottom: 7px; }

table { width: 100%; border-collapse: collapse; font-size: 14px; margin: 8px 0; }
th { background: #1a3a5c; color: white; padding: 8px 11px; text-align: left; font-weight: 600; }
td { padding: 7px 11px; border-bottom: 1px solid #eef0f5; }
tr:last-child td { border-bottom: none; }
tr:nth-child(even) { background: #f8fafc; }
.num { text-align: right; font-variant-numeric: tabular-nums; }
.highlight { background: #fff3cd !important; font-weight: 600; }
.total-row { background: #e8ecf5 !important; font-weight: 700; }

.two-col { display: grid; grid-template-columns: 1fr 1fr; gap: 18px; }
@media (max-width: 680px) { .two-col { grid-template-columns: 1fr; } .content { padding: 18px; } .tabs { padding: 0 10px; } }

/* ---- ZONE QUESTION ---- */
.question-block { background: white; border-radius: 10px; border-left: 5px solid #2d6a9f; padding: 18px 20px; margin-bottom: 18px; box-shadow: 0 2px 5px rgba(0,0,0,0.05); }
.q-label { font-size: 11px; font-weight: 700; color: #2d6a9f; text-transform: uppercase; letter-spacing: 0.6px; margin-bottom: 6px; }
.q-text { font-size: 14px; line-height: 1.65; color: #333; margin-bottom: 12px; }
.q-hint { font-size: 12px; color: #888; font-style: italic; margin-bottom: 12px; padding: 7px 10px; background: #f8fafc; border-radius: 6px; border-left: 3px solid #c8d8f0; }

/* zones de saisie */
.input-zone { width: 100%; min-height: 90px; border: 1.5px solid #c8d8f0; border-radius: 8px; padding: 10px 12px; font-size: 13px; font-family: inherit; resize: vertical; background: #f8fbff; color: #222; line-height: 1.6; transition: border-color 0.2s; }
.input-zone:focus { outline: none; border-color: #2d6a9f; background: #fff; }
.input-zone::placeholder { color: #aab; font-style: italic; }
.input-zone.filled { border-color: #2d9f6a; background: #f8fff8; }

/* tableau de saisie journal */
.journal-grid { width: 100%; border-collapse: collapse; font-size: 13px; margin: 10px 0; }
.journal-grid th { background: #1a3a5c; color: white; padding: 7px 10px; font-weight: 600; text-align: center; font-size: 12px; }
.journal-grid td { border: 1px solid #d0d8e8; padding: 4px 6px; }
.journal-grid .date-cell { background: #eef2fa; font-weight: 700; text-align: center; color: #1a3a5c; font-size: 12px; width: 90px; }
.journal-grid input[type=text], .journal-grid input[type=number] {
  width: 100%; border: none; background: transparent; font-size: 13px; font-family: inherit; padding: 2px 4px; color: #222;
}
.journal-grid input[type=text]:focus, .journal-grid input[type=number]:focus { outline: 2px solid #2d6a9f; border-radius: 3px; background: #f0f6ff; }
.journal-grid input[type=number] { text-align: right; }
.journal-grid .compte-col { width: 70px; }
.journal-grid .libelle-col { }
.journal-grid .montant-col { width: 110px; }
.journal-grid .credit-row td:nth-child(2) { padding-left: 28px; }
.journal-grid .credit-row { background: #f8fff8; }
.journal-grid .debit-row { background: #f8fbff; }

/* boutons */
.btn-reveal { display: inline-flex; align-items: center; gap: 6px; margin-top: 12px; background: #b0c8e0; color: #fff; border: none; border-radius: 20px; padding: 7px 18px; font-size: 13px; cursor: not-allowed; transition: background 0.2s, transform 0.1s; opacity: 0.75; }
.btn-reveal.ready { background: #2d6a9f; cursor: pointer; opacity: 1; }
.btn-reveal.ready:hover { background: #1a3a5c; }
.btn-reveal.done { background: #2d9f6a; cursor: default; opacity: 1; }
@keyframes shake { 0%,100%{transform:translateX(0)} 20%{transform:translateX(-6px)} 40%{transform:translateX(6px)} 60%{transform:translateX(-4px)} 80%{transform:translateX(4px)} }
.btn-reveal.shake { animation: shake 0.4s ease; }
.btn-clear { display: inline-flex; align-items: center; gap: 6px; margin-top: 12px; margin-left: 8px; background: transparent; color: #888; border: 1px solid #c8d8f0; border-radius: 20px; padding: 7px 14px; font-size: 12px; cursor: pointer; transition: all 0.2s; }
.btn-clear:hover { background: #f0f6ff; color: #2d6a9f; border-color: #2d6a9f; }
.warn-fill { font-size: 12px; color: #b05500; background: #fff3cd; border: 1px solid #f0c040; border-radius: 6px; padding: 6px 12px; margin-top: 8px; display: none; }
.warn-fill.show { display: block; }

/* correction */
.correction-box { display: none; margin-top: 14px; background: #efffef; border: 1.5px solid #2d9f6a; border-radius: 8px; padding: 14px 16px; }
.correction-box.show { display: block; animation: fadeIn 0.3s ease; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(-4px); } to { opacity: 1; transform: translateY(0); } }
.correction-box .corr-title { font-size: 12px; font-weight: 700; color: #1a5c3a; text-transform: uppercase; letter-spacing: 0.5px; margin-bottom: 8px; }
.corr-formula { background: white; border: 1px solid #b0dfc0; border-radius: 6px; padding: 9px 12px; margin: 6px 0; font-size: 13px; line-height: 1.6; font-family: 'Courier New', monospace; color: #1a3a5c; }
.journal-corr { width: 100%; border-collapse: collapse; font-size: 13px; margin: 8px 0; font-family: 'Courier New', monospace; }
.journal-corr td { padding: 4px 10px; border: 1px solid #c0e0c0; }
.journal-corr .jc-date { background: #1a3a5c; color: white; font-weight: 700; text-align: center; }
.journal-corr .jc-d { background: #f0f8ff; }
.journal-corr .jc-c { background: #f8fff8; }
.journal-corr .jc-compte { font-weight: 700; color: #1a3a5c; width: 65px; }
.journal-corr .jc-indent { padding-left: 28px; }
.journal-corr .jc-num { text-align: right; width: 110px; }

.alert { border-radius: 7px; padding: 10px 14px; font-size: 13px; margin: 8px 0; line-height: 1.6; }
.alert-info { background: #e8f4fd; border-left: 4px solid #2d6a9f; color: #1a3a5c; }
.alert-success { background: #e8fdf4; border-left: 4px solid #2d9f6a; color: #1a5c3a; }
.alert-warning { background: #fff8e1; border-left: 4px solid #f0a500; color: #7a4e00; }
.alert-danger { background: #fdecea; border-left: 4px solid #d9534f; color: #7a1a1a; }

.info-pill { display: inline-flex; align-items: center; background: #e8f4fd; color: #1a3a5c; border-radius: 20px; padding: 3px 11px; font-size: 12px; font-weight: 600; margin: 2px; }
.info-pill.green { background: #e8fdf4; color: #1a5c3a; }
.info-pill.orange { background: #fff3cd; color: #7a4e00; }
.info-pill.red { background: #fdecea; color: #7a1a1a; }

.timeline { position: relative; padding-left: 22px; margin: 12px 0; }
.timeline::before { content:''; position:absolute; left:6px; top:0; bottom:0; width:2px; background:#c8d8f0; border-radius:2px; }
.tl-item { position: relative; margin-bottom: 12px; font-size: 13px; }
.tl-item::before { content:''; position:absolute; left:-18px; top:4px; width:10px; height:10px; border-radius:50%; background:#2d6a9f; border:2px solid white; box-shadow:0 0 0 2px #2d6a9f; }

.recap-table { width: 100%; border-collapse: collapse; font-size: 13px; }
.recap-table th { background: #1a3a5c; color: white; padding: 8px 10px; }
.recap-table td { padding: 7px 10px; border-bottom: 1px solid #e0e6f0; text-align: right; }
.recap-table td:first-child { text-align: left; font-weight: 600; }
.recap-table .blank { background: #f0f6ff; color: #aaa; font-style: italic; text-align: center; }
.recap-table .revealed { background: #f0fff6; font-weight: 700; color: #1a5c3a; }

/* quiz */
.quiz-option { display: block; width: 100%; text-align: left; padding: 9px 14px; border-radius: 8px; border: 1.5px solid #c8d8f0; background: white; cursor: pointer; font-size: 13px; margin-bottom: 7px; transition: all 0.2s; }
.quiz-option:hover:not(:disabled) { border-color: #2d6a9f; background: #f0f6ff; }
.quiz-option.correct { border-color: #2d9f6a !important; background: #e8fdf4 !important; color: #1a5c3a; font-weight: 600; }
.quiz-option.wrong { border-color: #d9534f !important; background: #fdecea !important; color: #7a1a1a; }

.score-display { text-align: center; padding: 16px; background: #f0f6ff; border-radius: 10px; border: 2px solid #2d6a9f; margin-top: 16px; display: none; }
.score-num { font-size: 42px; font-weight: 700; color: #2d6a9f; }

.method-card { border-radius: 10px; padding: 16px 18px; border: 2px solid; }
.method-card.achevement { border-color: #2d6a9f; background: #f0f6ff; }
.method-card.avancement { border-color: #2d9f6a; background: #f0fff6; }
.method-card h4 { font-size: 14px; font-weight: 700; margin-bottom: 8px; }
.method-card.achevement h4 { color: #1a3a5c; }
.method-card.avancement h4 { color: #1a5c3a; }
.method-card p { font-size: 13px; line-height: 1.65; }
</style>
</head>
<body>

<div class="header">
  <h1>🏗️ Chantier "La Vague" — Contrats à Long Terme</h1>
  <p>Comptabilité approfondie — UE 441 — Thème 18</p>
  <span class="badge">✏️ Exercice étudiant</span>
  <span class="badge">✅ Corrections à révéler</span>
  <span class="badge">🎯 Niveau DCG</span>
</div>

<div class="tabs">
  <div class="tab active" onclick="show('contexte')">🏄 Contexte</div>
  <div class="tab" onclick="show('rappels')">📖 Rappels</div>
  <div class="tab" onclick="show('achevement')">⏹ Méthode Achèvement</div>
  <div class="tab" onclick="show('avancement')">📈 Méthode Avancement</div>
  <div class="tab" onclick="show('deficit')">🔴 Contrat Déficitaire</div>
  <div class="tab" onclick="show('quiz')">🎯 Quiz</div>
  <div class="tab" onclick="show('comparatif')">📊 Comparatif</div>
</div>

<!-- ========== CONTEXTE ========== -->
<div id="contexte" class="content section active">
  <div class="scenario-box">
    <h2>🌊 Le chantier "La Vague" — OUESTBUILD SA</h2>
    <p>La société <strong>OUESTBUILD SA</strong> est spécialisée dans la construction d'équipements sportifs. Elle vient de décrocher un <strong>contrat de 3 ans</strong> pour construire la nouvelle piscine olympique de Biarritz, baptisée <em>"La Vague"</em>. C'est le plus gros contrat de son histoire !</p>
  </div>

  <div class="two-col">
    <div class="card">
      <h3>📋 Données du contrat</h3>
      <table>
        <tr><td>Client</td><td><strong>Ville de Biarritz</strong></td></tr>
        <tr><td>Début</td><td>1er janvier 2023</td></tr>
        <tr><td>Livraison prévue</td><td>31 décembre 2025</td></tr>
        <tr class="highlight"><td><strong>Prix de vente HT</strong></td><td><strong>3 000 000 €</strong></td></tr>
        <tr class="highlight"><td><strong>Coût total prévu HT</strong></td><td><strong>2 400 000 €</strong></td></tr>
        <tr><td>Marge prévue</td><td>600 000 € (20%)</td></tr>
      </table>
    </div>
    <div class="card">
      <h3>📅 Charges réelles engagées</h3>
      <table>
        <tr><th>Exercice</th><th>Charges de l'exercice</th><th>Cumulé</th></tr>
        <tr><td>2023</td><td class="num">600 000 €</td><td class="num">600 000 €</td></tr>
        <tr><td>2024</td><td class="num">1 080 000 €</td><td class="num">1 680 000 €</td></tr>
        <tr><td>2025</td><td class="num">720 000 €</td><td class="num">2 400 000 €</td></tr>
        <tr class="total-row"><td>TOTAL</td><td class="num">2 400 000 €</td><td></td></tr>
      </table>
      <div style="margin-top:10px;">
        <span class="info-pill">2023 : 25% avancé</span>
        <span class="info-pill">2024 : 70% avancé</span>
        <span class="info-pill green">2025 : 100% livré ✓</span>
      </div>
    </div>
  </div>

  <div class="card">
    <h3>🗓️ Chronologie</h3>
    <div class="timeline">
      <div class="tl-item"><strong>1er jan. 2023 :</strong> Démarrage — Fondations et terrassement</div>
      <div class="tl-item"><strong>31 déc. 2023 :</strong> Clôture N — 600 000 € engagés (25% du coût total)</div>
      <div class="tl-item"><strong>31 déc. 2024 :</strong> Clôture N+1 — 1 680 000 € cumulés (70% du coût total)</div>
      <div class="tl-item"><strong>31 déc. 2025 :</strong> Livraison et réception par la Ville de Biarritz — Facturation finale</div>
    </div>
  </div>

  <div class="alert alert-info">
    💡 <strong>Le problème comptable :</strong> Les travaux démarrent en 2023 mais la piscine n'est livrée qu'en 2025. Quand faut-il comptabiliser le CA et la marge ? Deux méthodes s'affrontent : <strong>l'achèvement</strong> et <strong>l'avancement</strong>.
  </div>
</div>

<!-- ========== RAPPELS ========== -->
<div id="rappels" class="content section">
  <div class="card">
    <h3>📖 Définition d'un contrat à long terme</h3>
    <p style="font-size:14px;line-height:1.7;margin-bottom:10px;">Un CLT est un contrat dont l'exécution s'étend sur <strong>au moins deux exercices comptables</strong>. Il concerne le BTP, la construction navale, les travaux publics, l'ingénierie industrielle…</p>
  </div>

  <div class="two-col">
    <div class="method-card achevement">
      <h4>⏹ Méthode de l'achèvement</h4>
      <p>CA et résultat reconnus <strong>uniquement à la livraison</strong>. En cours de chantier, seule la production stockée est constatée (compte 335).</p>
      <br><p style="font-size:12px;color:#555;"><strong>Principe :</strong> Prudence maximale.</p>
    </div>
    <div class="method-card avancement">
      <h4>📈 Méthode de l'avancement</h4>
      <p>CA et résultat constatés <strong>au fur et à mesure</strong> de l'avancement réel des travaux, proportionnellement aux charges engagées.</p>
      <br><p style="font-size:12px;color:#555;"><strong>Principe :</strong> Image fidèle.</p>
    </div>
  </div>

  <div class="card">
    <h3>🧮 Formule clé — Taux d'avancement</h3>
    <div style="background:#f0f6ff;border:2px solid #2d6a9f;border-radius:10px;padding:16px;text-align:center;font-size:15px;font-weight:700;color:#1a3a5c;margin-bottom:10px;">
      Taux d'avancement = Charges cumulées ÷ Charges totales prévues
    </div>
    <div style="background:#f0fff6;border:2px solid #2d9f6a;border-radius:10px;padding:16px;text-align:center;font-size:15px;font-weight:700;color:#1a5c3a;">
      CA cumulé à reconnaître = Prix de vente × Taux d'avancement
    </div>
  </div>

  <div class="card">
    <h3>📝 Comptes utilisés</h3>
    <table>
      <tr><th>Compte</th><th>Intitulé</th><th>Méthode</th></tr>
      <tr><td><strong>335</strong></td><td>Travaux en cours</td><td>Achèvement</td></tr>
      <tr><td><strong>7135</strong></td><td>Variation des travaux en cours</td><td>Achèvement</td></tr>
      <tr><td><strong>418</strong></td><td>Clients — Produits non encore facturés</td><td>Avancement</td></tr>
      <tr><td><strong>706</strong></td><td>Prestations de services</td><td>Avancement + livraison</td></tr>
      <tr><td><strong>1518</strong></td><td>Provisions pour pertes à terminaison</td><td>Les deux</td></tr>
      <tr><td><strong>6815</strong></td><td>Dotation aux provisions risques et charges</td><td>Les deux</td></tr>
    </table>
  </div>

  <div class="alert alert-danger">
    🔴 <strong>Contrat déficitaire :</strong> dès qu'une perte à terminaison est probable, elle doit être intégralement provisionnée (compte 1518), quelle que soit la méthode. Principe de prudence.
  </div>
</div>

<!-- ========== ACHEVEMENT ========== -->
<div id="achevement" class="content section">
  <div class="alert alert-info">
    📌 Avec la méthode de l'achèvement : les charges sont stockées en travaux en cours (compte 335 / 7135). Aucun CA n'est reconnu avant la livraison.
  </div>

  <!-- Q1 -->
  <div class="question-block">
    <div class="q-label">Question 1 — Exercice 2023</div>
    <div class="q-text">Calculez la valeur des travaux en cours au 31/12/2023 et présentez l'écriture de régularisation au journal.</div>
    <div class="q-hint">💡 Méthode de l'achèvement = on stocke les charges à leur coût de production. Aucun CA n'est constaté.</div>

    <p style="font-size:13px;font-weight:600;color:#1a3a5c;margin-bottom:6px;">Votre calcul :</p>
    <textarea class="input-zone" id="calc-a1" placeholder="Exemple : Travaux en cours = charges cumulées = …" oninput="checkFilled('calc-a1')"></textarea>

    <p style="font-size:13px;font-weight:600;color:#1a3a5c;margin:10px 0 6px;">Votre écriture au journal (31/12/2023) :</p>
    <table class="journal-grid">
      <tr><th>Date</th><th>N° Compte</th><th class="libelle-col">Libellé</th><th>Débit</th><th>Crédit</th></tr>
      <tr class="debit-row">
        <td class="date-cell" rowspan="2">31/12/2023</td>
        <td class="compte-col"><input type="text" id="a1-d-cpt" placeholder="3xx" oninput="checkFilled('a1-d-cpt')"></td>
        <td><input type="text" id="a1-d-lib" placeholder="Libellé débit…" oninput="checkFilled('a1-d-lib')"></td>
        <td class="montant-col"><input type="number" id="a1-d-mt" placeholder="0" oninput="checkFilled('a1-d-mt')"></td>
        <td class="montant-col"></td>
      </tr>
      <tr class="credit-row">
        <td class="compte-col"><input type="text" id="a1-c-cpt" placeholder="7xxx" oninput="checkFilled('a1-c-cpt')"></td>
        <td><input type="text" id="a1-c-lib" placeholder="Libellé crédit…" oninput="checkFilled('a1-c-lib')"></td>
        <td class="montant-col"></td>
        <td class="montant-col"><input type="number" id="a1-c-mt" placeholder="0" oninput="checkFilled('a1-c-mt')"></td>
      </tr>
    </table>

    <button class="btn-reveal" id="btn-corr-a1" data-corr="corr-a1" data-fields="calc-a1,a1-d-cpt,a1-d-lib,a1-d-mt,a1-c-cpt,a1-c-lib,a1-c-mt" onclick="tryReveal(this)">🔒 Voir la correction</button>
    <button class="btn-clear" onclick="clearBlock(['calc-a1','a1-d-cpt','a1-d-lib','a1-d-mt','a1-c-cpt','a1-c-lib','a1-c-mt'],'btn-corr-a1')">🗑 Effacer</button>
    <div class="warn-fill" id="warn-corr-a1">✏️ Complétez d'abord tous les champs avant de voir la correction.</div>

    <div id="corr-a1" class="correction-box">
      <div class="corr-title">✅ Correction</div>
      <div class="corr-formula">Travaux en cours au 31/12/2023 = Charges de production cumulées = <strong>600 000 €</strong></div>
      <table class="journal-corr">
        <tr><td class="jc-date" colspan="4">31/12/2023 — Constatation des travaux en cours</td></tr>
        <tr class="jc-d"><td class="jc-compte">335</td><td>Travaux en cours</td><td class="jc-num">600 000</td><td class="jc-num"></td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;7135</td><td>Variation des travaux en cours</td><td class="jc-num"></td><td class="jc-num">600 000</td></tr>
      </table>
      <div class="alert alert-warning" style="margin-top:8px;">⚠️ Aucun CA comptabilisé en 2023 avec cette méthode. Résultat = 0.</div>
    </div>
  </div>

  <!-- Q2 -->
  <div class="question-block">
    <div class="q-label">Question 2 — Exercice 2024</div>
    <div class="q-text">Présentez les deux écritures de régularisation au 31/12/2024 : extourne du stock N-1 puis constatation du nouveau stock.</div>
    <div class="q-hint">💡 Il faut d'abord extourner le stock de 2023 (au 01/01/2024), puis constater le nouveau stock cumulé.</div>

    <p style="font-size:13px;font-weight:600;color:#1a3a5c;margin-bottom:6px;">Votre calcul du nouveau stock :</p>
    <textarea class="input-zone" id="calc-a2" placeholder="Travaux en cours cumulés au 31/12/2024 = …" style="min-height:60px;" oninput="checkFilled('calc-a2')"></textarea>

    <p style="font-size:13px;font-weight:600;color:#1a3a5c;margin:10px 0 6px;">Écriture 1 — Extourne au 01/01/2024 :</p>
    <table class="journal-grid">
      <tr><th>Date</th><th>N° Compte</th><th class="libelle-col">Libellé</th><th>Débit</th><th>Crédit</th></tr>
      <tr class="debit-row">
        <td class="date-cell" rowspan="2">01/01/2024</td>
        <td><input type="text" id="a2e-d-cpt" placeholder="" oninput="checkFilled('a2e-d-cpt')"></td>
        <td><input type="text" id="a2e-d-lib" placeholder="" oninput="checkFilled('a2e-d-lib')"></td>
        <td><input type="number" id="a2e-d-mt" placeholder="0" oninput="checkFilled('a2e-d-mt')"></td>
        <td></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="a2e-c-cpt" placeholder="" oninput="checkFilled('a2e-c-cpt')"></td>
        <td><input type="text" id="a2e-c-lib" placeholder="" oninput="checkFilled('a2e-c-lib')"></td>
        <td></td>
        <td><input type="number" id="a2e-c-mt" placeholder="0" oninput="checkFilled('a2e-c-mt')"></td>
      </tr>
    </table>

    <p style="font-size:13px;font-weight:600;color:#1a3a5c;margin:10px 0 6px;">Écriture 2 — Nouveau stock au 31/12/2024 :</p>
    <table class="journal-grid">
      <tr><th>Date</th><th>N° Compte</th><th class="libelle-col">Libellé</th><th>Débit</th><th>Crédit</th></tr>
      <tr class="debit-row">
        <td class="date-cell" rowspan="2">31/12/2024</td>
        <td><input type="text" id="a2n-d-cpt" placeholder="" oninput="checkFilled('a2n-d-cpt')"></td>
        <td><input type="text" id="a2n-d-lib" placeholder="" oninput="checkFilled('a2n-d-lib')"></td>
        <td><input type="number" id="a2n-d-mt" placeholder="0" oninput="checkFilled('a2n-d-mt')"></td>
        <td></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="a2n-c-cpt" placeholder="" oninput="checkFilled('a2n-c-cpt')"></td>
        <td><input type="text" id="a2n-c-lib" placeholder="" oninput="checkFilled('a2n-c-lib')"></td>
        <td></td>
        <td><input type="number" id="a2n-c-mt" placeholder="0" oninput="checkFilled('a2n-c-mt')"></td>
      </tr>
    </table>

    <button class="btn-reveal" id="btn-corr-a2" data-corr="corr-a2" data-fields="calc-a2,a2e-d-cpt,a2e-d-lib,a2e-d-mt,a2e-c-cpt,a2e-c-lib,a2e-c-mt,a2n-d-cpt,a2n-d-lib,a2n-d-mt,a2n-c-cpt,a2n-c-lib,a2n-c-mt" onclick="tryReveal(this)">🔒 Voir la correction</button>
    <button class="btn-clear" onclick="clearBlock(['calc-a2','a2e-d-cpt','a2e-d-lib','a2e-d-mt','a2e-c-cpt','a2e-c-lib','a2e-c-mt','a2n-d-cpt','a2n-d-lib','a2n-d-mt','a2n-c-cpt','a2n-c-lib','a2n-c-mt'],'btn-corr-a2')">🗑 Effacer</button>
    <div class="warn-fill" id="warn-corr-a2">✏️ Complétez d'abord tous les champs avant de voir la correction.</div>

    <div id="corr-a2" class="correction-box">
      <div class="corr-title">✅ Correction</div>
      <div class="corr-formula">Stock cumulé au 31/12/2024 = 600 000 + 1 080 000 = <strong>1 680 000 €</strong></div>
      <table class="journal-corr">
        <tr><td class="jc-date" colspan="4">01/01/2024 — Extourne du stock 2023</td></tr>
        <tr class="jc-d"><td class="jc-compte">7135</td><td>Variation des travaux en cours</td><td class="jc-num">600 000</td><td></td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;335</td><td>Travaux en cours</td><td></td><td class="jc-num">600 000</td></tr>
      </table>
      <table class="journal-corr" style="margin-top:8px;">
        <tr><td class="jc-date" colspan="4">31/12/2024 — Nouveau stock cumulé</td></tr>
        <tr class="jc-d"><td class="jc-compte">335</td><td>Travaux en cours</td><td class="jc-num">1 680 000</td><td></td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;7135</td><td>Variation des travaux en cours</td><td></td><td class="jc-num">1 680 000</td></tr>
      </table>
      <div class="alert alert-info" style="margin-top:8px;">📊 Impact 7135 sur 2024 = +1 680 000 − 600 000 (extourne) = +1 080 000 €. Résultat 2024 = 0.</div>
    </div>
  </div>

  <!-- Q3 -->
  <div class="question-block">
    <div class="q-label">Question 3 — Exercice 2025 (livraison)</div>
    <div class="q-text">Présentez toutes les écritures au 31/12/2025 : extourne du stock 2024, facturation définitive au client. Calculez le résultat de l'exercice 2025.</div>
    <div class="q-hint">💡 En 2025 : on solde le stock (extourne), on facture le prix total au client (706), et toute la marge apparaît sur cet exercice.</div>

    <p style="font-size:13px;font-weight:600;color:#1a3a5c;margin-bottom:6px;">Votre calcul du résultat 2025 :</p>
    <textarea class="input-zone" id="calc-a3" placeholder="CA = …   Charges 2025 = …   Stock extourné = …   Résultat = …" style="min-height:70px;" oninput="checkFilled('calc-a3')"></textarea>

    <p style="font-size:13px;font-weight:600;color:#1a3a5c;margin:10px 0 6px;">Vos écritures au journal :</p>
    <table class="journal-grid">
      <tr><th>Date</th><th>N° Compte</th><th class="libelle-col">Libellé</th><th>Débit</th><th>Crédit</th></tr>
      <tr class="debit-row">
        <td class="date-cell" rowspan="2">01/01/2025</td>
        <td><input type="text" id="a3-1d-cpt" placeholder=""></td>
        <td><input type="text" id="a3-1d-lib" placeholder="Extourne…"></td>
        <td><input type="number" id="a3-1d-mt" placeholder="0"></td>
        <td></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="a3-1c-cpt" placeholder=""></td>
        <td><input type="text" id="a3-1c-lib" placeholder=""></td>
        <td></td>
        <td><input type="number" id="a3-1c-mt" placeholder="0"></td>
      </tr>
      <tr class="debit-row">
        <td class="date-cell" rowspan="3">31/12/2025</td>
        <td><input type="text" id="a3-2d-cpt" placeholder=""></td>
        <td><input type="text" id="a3-2d-lib" placeholder="Facturation…"></td>
        <td><input type="number" id="a3-2d-mt" placeholder="0"></td>
        <td></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="a3-2c1-cpt" placeholder=""></td>
        <td><input type="text" id="a3-2c1-lib" placeholder="Produit…"></td>
        <td></td>
        <td><input type="number" id="a3-2c1-mt" placeholder="0"></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="a3-2c2-cpt" placeholder=""></td>
        <td><input type="text" id="a3-2c2-lib" placeholder="TVA…"></td>
        <td></td>
        <td><input type="number" id="a3-2c2-mt" placeholder="0"></td>
      </tr>
    </table>

    <button class="btn-reveal" id="btn-corr-a3" data-corr="corr-a3" data-fields="calc-a3,a3-1d-cpt,a3-1d-lib,a3-1d-mt,a3-1c-cpt,a3-1c-lib,a3-1c-mt,a3-2d-cpt,a3-2d-lib,a3-2d-mt,a3-2c1-cpt,a3-2c1-lib,a3-2c1-mt,a3-2c2-cpt,a3-2c2-lib,a3-2c2-mt" onclick="tryReveal(this)">🔒 Voir la correction</button>
    <button class="btn-clear" onclick="clearBlock(['calc-a3','a3-1d-cpt','a3-1d-lib','a3-1d-mt','a3-1c-cpt','a3-1c-lib','a3-1c-mt','a3-2d-cpt','a3-2d-lib','a3-2d-mt','a3-2c1-cpt','a3-2c1-lib','a3-2c1-mt','a3-2c2-cpt','a3-2c2-lib','a3-2c2-mt'],'btn-corr-a3')">🗑 Effacer</button>
    <div class="warn-fill" id="warn-corr-a3">✏️ Complétez d'abord tous les champs avant de voir la correction.</div>

    <div id="corr-a3" class="correction-box">
      <div class="corr-title">✅ Correction</div>
      <table class="journal-corr">
        <tr><td class="jc-date" colspan="4">01/01/2025 — Extourne stock 2024</td></tr>
        <tr class="jc-d"><td class="jc-compte">7135</td><td>Variation des travaux en cours</td><td class="jc-num">1 680 000</td><td></td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;335</td><td>Travaux en cours</td><td></td><td class="jc-num">1 680 000</td></tr>
      </table>
      <table class="journal-corr" style="margin-top:8px;">
        <tr><td class="jc-date" colspan="4">31/12/2025 — Facturation à la Ville de Biarritz</td></tr>
        <tr class="jc-d"><td class="jc-compte">411</td><td>Clients — Ville de Biarritz</td><td class="jc-num">3 600 000</td><td></td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;706</td><td>Prestations de services</td><td></td><td class="jc-num">3 000 000</td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;44571</td><td>TVA collectée (20%)</td><td></td><td class="jc-num">600 000</td></tr>
      </table>
      <div class="alert alert-success" style="margin-top:8px;">✅ Résultat 2025 = 3 000 000 (CA) − 720 000 (charges) + 1 680 000 (extourne stock) − 1 680 000 = <strong>600 000 €</strong> — Toute la marge est reconnue en une seule année.</div>
    </div>
  </div>
</div>

<!-- ========== AVANCEMENT ========== -->
<div id="avancement" class="content section">
  <div class="alert alert-success">
    📌 Avec la méthode de l'avancement : CA et marge sont reconnus proportionnellement aux charges engagées. Taux = charges cumulées ÷ charges totales prévues.
  </div>

  <!-- Q4 -->
  <div class="question-block">
    <div class="q-label">Question 4 — Calcul des taux d'avancement</div>
    <div class="q-text">Complétez le tableau de calcul des taux d'avancement et du CA cumulé à reconnaître pour chaque exercice.</div>
    <div class="q-hint">💡 Taux = Charges cumulées / Charges totales prévues (2 400 000 €) &nbsp;|&nbsp; CA cumulé = Prix total × Taux</div>

    <table style="margin:10px 0; font-size:13px;">
      <tr>
        <th>Exercice</th><th>Charges cumulées</th><th>Taux d'avancement</th><th>CA cumulé à reconnaître</th><th>CA de l'exercice</th>
      </tr>
      <tr>
        <td><strong>2023</strong></td>
        <td class="num">600 000 €</td>
        <td><input type="text" style="width:80px;border:1px solid #c8d8f0;border-radius:4px;padding:3px 6px;font-size:13px;" id="tx23" placeholder="…%"></td>
        <td><input type="text" style="width:110px;border:1px solid #c8d8f0;border-radius:4px;padding:3px 6px;font-size:13px;" id="ca23" placeholder="… €"></td>
        <td><input type="text" style="width:110px;border:1px solid #c8d8f0;border-radius:4px;padding:3px 6px;font-size:13px;" id="cae23" placeholder="… €"></td>
      </tr>
      <tr>
        <td><strong>2024</strong></td>
        <td class="num">1 680 000 €</td>
        <td><input type="text" style="width:80px;border:1px solid #c8d8f0;border-radius:4px;padding:3px 6px;font-size:13px;" id="tx24" placeholder="…%"></td>
        <td><input type="text" style="width:110px;border:1px solid #c8d8f0;border-radius:4px;padding:3px 6px;font-size:13px;" id="ca24" placeholder="… €"></td>
        <td><input type="text" style="width:110px;border:1px solid #c8d8f0;border-radius:4px;padding:3px 6px;font-size:13px;" id="cae24" placeholder="… €"></td>
      </tr>
      <tr>
        <td><strong>2025</strong></td>
        <td class="num">2 400 000 €</td>
        <td><input type="text" style="width:80px;border:1px solid #c8d8f0;border-radius:4px;padding:3px 6px;font-size:13px;" id="tx25" placeholder="…%"></td>
        <td><input type="text" style="width:110px;border:1px solid #c8d8f0;border-radius:4px;padding:3px 6px;font-size:13px;" id="ca25" placeholder="… €"></td>
        <td><input type="text" style="width:110px;border:1px solid #c8d8f0;border-radius:4px;padding:3px 6px;font-size:13px;" id="cae25" placeholder="… €"></td>
      </tr>
    </table>

    <button class="btn-reveal" id="btn-corr-b0" data-corr="corr-b0" data-fields="tx23,ca23,cae23,tx24,ca24,cae24,tx25,ca25,cae25" onclick="tryReveal(this)">🔒 Voir la correction</button>
    <div class="warn-fill" id="warn-corr-b0">✏️ Complétez d'abord tous les champs du tableau avant de voir la correction.</div>
    <div id="corr-b0" class="correction-box">
      <div class="corr-title">✅ Correction</div>
      <table class="journal-corr" style="font-family:inherit;">
        <tr><th style="background:#1a3a5c;color:white;padding:7px;">Exercice</th><th style="background:#1a3a5c;color:white;padding:7px;">Taux</th><th style="background:#1a3a5c;color:white;padding:7px;">CA cumulé</th><th style="background:#1a3a5c;color:white;padding:7px;">CA exercice</th><th style="background:#1a3a5c;color:white;padding:7px;">Marge</th></tr>
        <tr><td style="padding:6px 10px;">2023</td><td style="padding:6px 10px;font-weight:700;">25%</td><td style="padding:6px 10px;">750 000 €</td><td style="padding:6px 10px;font-weight:700;">750 000 €</td><td style="padding:6px 10px;color:#1a5c3a;font-weight:700;">150 000 €</td></tr>
        <tr style="background:#f8fafc;"><td style="padding:6px 10px;">2024</td><td style="padding:6px 10px;font-weight:700;">70%</td><td style="padding:6px 10px;">2 100 000 €</td><td style="padding:6px 10px;font-weight:700;">1 350 000 €</td><td style="padding:6px 10px;color:#1a5c3a;font-weight:700;">270 000 €</td></tr>
        <tr><td style="padding:6px 10px;">2025</td><td style="padding:6px 10px;font-weight:700;">100%</td><td style="padding:6px 10px;">3 000 000 €</td><td style="padding:6px 10px;font-weight:700;">900 000 €</td><td style="padding:6px 10px;color:#1a5c3a;font-weight:700;">180 000 €</td></tr>
      </table>
      <div class="alert alert-success" style="margin-top:8px;">✅ Vérification : 150 000 + 270 000 + 180 000 = <strong>600 000 €</strong> = marge totale prévue ✓</div>
    </div>
  </div>

  <!-- Q5 -->
  <div class="question-block">
    <div class="q-label">Question 5 — Écritures 2023 et 2024 (avancement)</div>
    <div class="q-text">Présentez les écritures de fin 2023 (CA reconnu) puis l'extourne du 01/01/2024 et l'écriture de fin 2024.</div>
    <div class="q-hint">💡 Le CA non encore facturé passe par le compte 418 (actif). Il faut l'extourner en début d'exercice suivant pour ne comptabiliser que le différentiel de l'année.</div>

    <p style="font-size:13px;font-weight:600;color:#1a3a5c;margin-bottom:6px;">Vos écritures :</p>
    <table class="journal-grid">
      <tr><th>Date</th><th>N° Compte</th><th class="libelle-col">Libellé</th><th>Débit</th><th>Crédit</th></tr>
      <tr class="debit-row">
        <td class="date-cell" rowspan="2">31/12/2023</td>
        <td><input type="text" id="b1-d-cpt" placeholder="4xx"></td>
        <td><input type="text" id="b1-d-lib" placeholder="Clients…"></td>
        <td><input type="number" id="b1-d-mt" placeholder="0"></td>
        <td></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="b1-c-cpt" placeholder="7xx"></td>
        <td><input type="text" id="b1-c-lib" placeholder="Prestations…"></td>
        <td></td>
        <td><input type="number" id="b1-c-mt" placeholder="0"></td>
      </tr>
      <tr class="debit-row">
        <td class="date-cell" rowspan="2">01/01/2024</td>
        <td><input type="text" id="b2-d-cpt" placeholder="7xx"></td>
        <td><input type="text" id="b2-d-lib" placeholder="Extourne…"></td>
        <td><input type="number" id="b2-d-mt" placeholder="0"></td>
        <td></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="b2-c-cpt" placeholder="4xx"></td>
        <td><input type="text" id="b2-c-lib" placeholder=""></td>
        <td></td>
        <td><input type="number" id="b2-c-mt" placeholder="0"></td>
      </tr>
      <tr class="debit-row">
        <td class="date-cell" rowspan="2">31/12/2024</td>
        <td><input type="text" id="b3-d-cpt" placeholder="4xx"></td>
        <td><input type="text" id="b3-d-lib" placeholder="CA cumulé…"></td>
        <td><input type="number" id="b3-d-mt" placeholder="0"></td>
        <td></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="b3-c-cpt" placeholder="7xx"></td>
        <td><input type="text" id="b3-c-lib" placeholder=""></td>
        <td></td>
        <td><input type="number" id="b3-c-mt" placeholder="0"></td>
      </tr>
    </table>

    <button class="btn-reveal" id="btn-corr-b1" data-corr="corr-b1" data-fields="b1-d-cpt,b1-d-lib,b1-d-mt,b1-c-cpt,b1-c-lib,b1-c-mt,b2-d-cpt,b2-d-lib,b2-d-mt,b2-c-cpt,b2-c-lib,b2-c-mt,b3-d-cpt,b3-d-lib,b3-d-mt,b3-c-cpt,b3-c-lib,b3-c-mt" onclick="tryReveal(this)">🔒 Voir la correction</button>
    <button class="btn-clear" onclick="clearBlock(['b1-d-cpt','b1-d-lib','b1-d-mt','b1-c-cpt','b1-c-lib','b1-c-mt','b2-d-cpt','b2-d-lib','b2-d-mt','b2-c-cpt','b2-c-lib','b2-c-mt','b3-d-cpt','b3-d-lib','b3-d-mt','b3-c-cpt','b3-c-lib','b3-c-mt'],'btn-corr-b1')">🗑 Effacer</button>
    <div class="warn-fill" id="warn-corr-b1">✏️ Complétez d'abord tous les champs du journal avant de voir la correction.</div>

    <div id="corr-b1" class="correction-box">
      <div class="corr-title">✅ Correction</div>
      <table class="journal-corr">
        <tr><td class="jc-date" colspan="4">31/12/2023 — CA selon avancement (25%)</td></tr>
        <tr class="jc-d"><td class="jc-compte">418</td><td>Clients — Produits non encore facturés</td><td class="jc-num">750 000</td><td></td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;706</td><td>Prestations de services</td><td></td><td class="jc-num">750 000</td></tr>
      </table>
      <table class="journal-corr" style="margin-top:8px;">
        <tr><td class="jc-date" colspan="4">01/01/2024 — Extourne du compte 418</td></tr>
        <tr class="jc-d"><td class="jc-compte">706</td><td>Prestations de services</td><td class="jc-num">750 000</td><td></td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;418</td><td>Clients — Produits non encore facturés</td><td></td><td class="jc-num">750 000</td></tr>
      </table>
      <table class="journal-corr" style="margin-top:8px;">
        <tr><td class="jc-date" colspan="4">31/12/2024 — CA cumulé selon avancement (70%)</td></tr>
        <tr class="jc-d"><td class="jc-compte">418</td><td>Clients — Produits non encore facturés</td><td class="jc-num">2 100 000</td><td></td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;706</td><td>Prestations de services</td><td></td><td class="jc-num">2 100 000</td></tr>
      </table>
      <div class="alert alert-info" style="margin-top:8px;">📊 CA 2024 = 2 100 000 (crédit 706) − 750 000 (extourne) = <strong>1 350 000 €</strong> net sur l'exercice.</div>
    </div>
  </div>

  <!-- Q6 -->
  <div class="question-block">
    <div class="q-label">Question 6 — Exercice 2025 (livraison + avancement)</div>
    <div class="q-text">Présentez l'extourne du 01/01/2025 et la facturation définitive au 31/12/2025. Vérifiez que la somme des marges = 600 000 €.</div>

    <textarea class="input-zone" id="calc-b3" placeholder="Calcul du CA 2025 = CA total − CA déjà reconnu cumulé = …&#10;Marge 2025 = …&#10;Vérification : 150 000 + 270 000 + 180 000 = …" style="min-height:80px;" oninput="checkFilled('calc-b3')"></textarea>

    <p style="font-size:13px;font-weight:600;color:#1a3a5c;margin:10px 0 6px;">Vos écritures :</p>
    <table class="journal-grid">
      <tr><th>Date</th><th>N° Compte</th><th class="libelle-col">Libellé</th><th>Débit</th><th>Crédit</th></tr>
      <tr class="debit-row">
        <td class="date-cell" rowspan="2">01/01/2025</td>
        <td><input type="text" id="b6-1d-cpt"></td>
        <td><input type="text" id="b6-1d-lib" placeholder="Extourne…"></td>
        <td><input type="number" id="b6-1d-mt" placeholder="0"></td>
        <td></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="b6-1c-cpt"></td>
        <td><input type="text" id="b6-1c-lib"></td>
        <td></td>
        <td><input type="number" id="b6-1c-mt" placeholder="0"></td>
      </tr>
      <tr class="debit-row">
        <td class="date-cell" rowspan="3">31/12/2025</td>
        <td><input type="text" id="b6-2d-cpt"></td>
        <td><input type="text" id="b6-2d-lib" placeholder="Facturation…"></td>
        <td><input type="number" id="b6-2d-mt" placeholder="0"></td>
        <td></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="b6-2c1-cpt"></td>
        <td><input type="text" id="b6-2c1-lib" placeholder="Produit…"></td>
        <td></td>
        <td><input type="number" id="b6-2c1-mt" placeholder="0"></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="b6-2c2-cpt"></td>
        <td><input type="text" id="b6-2c2-lib" placeholder="TVA…"></td>
        <td></td>
        <td><input type="number" id="b6-2c2-mt" placeholder="0"></td>
      </tr>
    </table>

    <button class="btn-reveal" id="btn-corr-b3" data-corr="corr-b3" data-fields="calc-b3,b6-1d-cpt,b6-1d-lib,b6-1d-mt,b6-1c-cpt,b6-1c-lib,b6-1c-mt,b6-2d-cpt,b6-2d-lib,b6-2d-mt,b6-2c1-cpt,b6-2c1-lib,b6-2c1-mt,b6-2c2-cpt,b6-2c2-lib,b6-2c2-mt" onclick="tryReveal(this)">🔒 Voir la correction</button>
    <div class="warn-fill" id="warn-corr-b3">✏️ Complétez d'abord tous les champs avant de voir la correction.</div>
    <div id="corr-b3" class="correction-box">
      <div class="corr-title">✅ Correction</div>
      <div class="corr-formula">CA 2025 = 3 000 000 − 2 100 000 = <strong>900 000 €</strong> &nbsp;|&nbsp; Marge 2025 = 900 000 − 720 000 = <strong>180 000 €</strong></div>
      <table class="journal-corr">
        <tr><td class="jc-date" colspan="4">01/01/2025 — Extourne du compte 418</td></tr>
        <tr class="jc-d"><td class="jc-compte">706</td><td>Prestations de services</td><td class="jc-num">2 100 000</td><td></td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;418</td><td>Clients — Produits non encore facturés</td><td></td><td class="jc-num">2 100 000</td></tr>
      </table>
      <table class="journal-corr" style="margin-top:8px;">
        <tr><td class="jc-date" colspan="4">31/12/2025 — Facturation définitive</td></tr>
        <tr class="jc-d"><td class="jc-compte">411</td><td>Clients — Ville de Biarritz</td><td class="jc-num">3 600 000</td><td></td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;706</td><td>Prestations de services</td><td></td><td class="jc-num">3 000 000</td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;44571</td><td>TVA collectée</td><td></td><td class="jc-num">600 000</td></tr>
      </table>
      <div class="alert alert-success" style="margin-top:8px;">✅ 150 000 + 270 000 + 180 000 = <strong>600 000 €</strong> ✓</div>
    </div>
  </div>
</div>

<!-- ========== DEFICIT ========== -->
<div id="deficit" class="content section">
  <div class="scenario-box" style="background:linear-gradient(135deg,#7a1a1a,#c0392b);">
    <h2>🚨 Scénario catastrophe — Le chantier dérape !</h2>
    <p>Des découvertes archéologiques imposent des travaux supplémentaires. Le coût total révisé passe à <strong>3 200 000 €</strong> au lieu de 2 400 000 €. Le prix de vente reste bloqué à <strong>3 000 000 €</strong>.</p>
  </div>

  <div class="two-col">
    <div class="card">
      <h3>📋 Contrat initial</h3>
      <table>
        <tr><td>Prix de vente</td><td class="num">3 000 000 €</td></tr>
        <tr><td>Coût prévu initial</td><td class="num">2 400 000 €</td></tr>
        <tr><td style="color:#2d9f6a;"><strong>Marge initiale</strong></td><td class="num" style="color:#2d9f6a;"><strong>+ 600 000 €</strong></td></tr>
      </table>
    </div>
    <div class="card">
      <h3>⚠️ Après révision (fin 2023)</h3>
      <table>
        <tr><td>Prix de vente</td><td class="num">3 000 000 €</td></tr>
        <tr><td>Coût total révisé</td><td class="num">3 200 000 €</td></tr>
        <tr><td style="color:#d9534f;"><strong>Perte à terminaison</strong></td><td class="num" style="color:#d9534f;"><strong>− 200 000 €</strong></td></tr>
      </table>
    </div>
  </div>

  <!-- Q7 -->
  <div class="question-block">
    <div class="q-label">Question 7 — Méthode de l'achèvement</div>
    <div class="q-text">Calculez la perte à terminaison et présentez l'écriture de provision à constater au 31/12/2023.</div>
    <div class="q-hint">💡 La perte à terminaison = Coût total révisé − Prix de vente. Elle doit être provisionnée intégralement dès sa détection (principe de prudence).</div>

    <textarea class="input-zone" id="calc-d1" placeholder="Perte à terminaison = … − … = … €" style="min-height:60px;" oninput="checkFilled('calc-d1')"></textarea>

    <p style="font-size:13px;font-weight:600;color:#1a3a5c;margin:10px 0 6px;">Écriture au journal :</p>
    <table class="journal-grid">
      <tr><th>Date</th><th>N° Compte</th><th class="libelle-col">Libellé</th><th>Débit</th><th>Crédit</th></tr>
      <tr class="debit-row">
        <td class="date-cell" rowspan="2">31/12/2023</td>
        <td><input type="text" id="d1-d-cpt" placeholder="6xxx"></td>
        <td><input type="text" id="d1-d-lib" placeholder="Dotation…"></td>
        <td><input type="number" id="d1-d-mt" placeholder="0"></td>
        <td></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="d1-c-cpt" placeholder="1xxx"></td>
        <td><input type="text" id="d1-c-lib" placeholder="Provision…"></td>
        <td></td>
        <td><input type="number" id="d1-c-mt" placeholder="0"></td>
      </tr>
    </table>

    <button class="btn-reveal" id="btn-corr-d1" data-corr="corr-d1" data-fields="calc-d1,d1-d-cpt,d1-d-lib,d1-d-mt,d1-c-cpt,d1-c-lib,d1-c-mt" onclick="tryReveal(this)">🔒 Voir la correction</button>
    <button class="btn-clear" onclick="clearBlock(['calc-d1','d1-d-cpt','d1-d-lib','d1-d-mt','d1-c-cpt','d1-c-lib','d1-c-mt'],'btn-corr-d1')">🗑 Effacer</button>
    <div class="warn-fill" id="warn-corr-d1">✏️ Complétez d'abord tous les champs avant de voir la correction.</div>

    <div id="corr-d1" class="correction-box">
      <div class="corr-title">✅ Correction</div>
      <div class="corr-formula">Perte à terminaison = 3 200 000 − 3 000 000 = <strong>200 000 €</strong></div>
      <table class="journal-corr">
        <tr><td class="jc-date" colspan="4">31/12/2023 — Provision pour perte à terminaison</td></tr>
        <tr class="jc-d"><td class="jc-compte">6815</td><td>Dotation aux provisions pour risques et charges</td><td class="jc-num">200 000</td><td></td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;1518</td><td>Provisions pour pertes à terminaison</td><td></td><td class="jc-num">200 000</td></tr>
      </table>
      <div class="alert alert-warning" style="margin-top:8px;">⚠️ Toute la perte est provisionnée en 2023 même si les travaux ne sont pas terminés. Résultat 2023 = −200 000 €.</div>
    </div>
  </div>

  <!-- Q8 -->
  <div class="question-block">
    <div class="q-label">Question 8 — Méthode de l'avancement (contrat déficitaire)</div>
    <div class="q-text">Avec la méthode de l'avancement et le coût révisé de 3 200 000 €, calculez : le nouveau taux d'avancement 2023, le CA à reconnaître, la perte dégagée sur 2023, et la provision complémentaire à constituer.</div>
    <div class="q-hint">💡 Taux d'avancement = 600 000 / 3 200 000. La perte dégagée via le résultat vient s'imputer sur la perte totale : la provision = perte totale − perte déjà constatée.</div>

    <textarea class="input-zone" id="calc-d2" placeholder="Nouveau taux = … / … = …%&#10;CA 2023 = 3 000 000 × … = … €&#10;Perte 2023 = CA − charges = … − 600 000 = … €&#10;Provision complémentaire = 200 000 − … = … €" oninput="checkFilled('calc-d2')"></textarea>

    <p style="font-size:13px;font-weight:600;color:#1a3a5c;margin:10px 0 6px;">Vos deux écritures au 31/12/2023 :</p>
    <table class="journal-grid">
      <tr><th>Date</th><th>N° Compte</th><th class="libelle-col">Libellé</th><th>Débit</th><th>Crédit</th></tr>
      <tr class="debit-row">
        <td class="date-cell" rowspan="2">31/12/2023 (1)</td>
        <td><input type="text" id="d2-1d-cpt" placeholder=""></td>
        <td><input type="text" id="d2-1d-lib" placeholder="CA avancement…"></td>
        <td><input type="number" id="d2-1d-mt" placeholder="0"></td>
        <td></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="d2-1c-cpt" placeholder=""></td>
        <td><input type="text" id="d2-1c-lib" placeholder=""></td>
        <td></td>
        <td><input type="number" id="d2-1c-mt" placeholder="0"></td>
      </tr>
      <tr class="debit-row">
        <td class="date-cell" rowspan="2">31/12/2023 (2)</td>
        <td><input type="text" id="d2-2d-cpt" placeholder=""></td>
        <td><input type="text" id="d2-2d-lib" placeholder="Provision…"></td>
        <td><input type="number" id="d2-2d-mt" placeholder="0"></td>
        <td></td>
      </tr>
      <tr class="credit-row">
        <td><input type="text" id="d2-2c-cpt" placeholder=""></td>
        <td><input type="text" id="d2-2c-lib" placeholder=""></td>
        <td></td>
        <td><input type="number" id="d2-2c-mt" placeholder="0"></td>
      </tr>
    </table>

    <button class="btn-reveal" id="btn-corr-d2" data-corr="corr-d2" data-fields="calc-d2,d2-1d-cpt,d2-1d-lib,d2-1d-mt,d2-1c-cpt,d2-1c-lib,d2-1c-mt,d2-2d-cpt,d2-2d-lib,d2-2d-mt,d2-2c-cpt,d2-2c-lib,d2-2c-mt" onclick="tryReveal(this)">🔒 Voir la correction</button>
    <div class="warn-fill" id="warn-corr-d2">✏️ Complétez d'abord tous les champs avant de voir la correction.</div>
    <div id="corr-d2" class="correction-box">
      <div class="corr-title">✅ Correction</div>
      <div class="corr-formula">Taux = 600 000 / 3 200 000 = <strong>18,75%</strong><br>CA 2023 = 3 000 000 × 18,75% = <strong>562 500 €</strong><br>Perte constatée = 562 500 − 600 000 = <strong>−37 500 €</strong><br>Provision complémentaire = 200 000 − 37 500 = <strong>162 500 €</strong></div>
      <table class="journal-corr">
        <tr><td class="jc-date" colspan="4">31/12/2023 — CA selon avancement</td></tr>
        <tr class="jc-d"><td class="jc-compte">418</td><td>Clients — Produits non encore facturés</td><td class="jc-num">562 500</td><td></td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;706</td><td>Prestations de services</td><td></td><td class="jc-num">562 500</td></tr>
      </table>
      <table class="journal-corr" style="margin-top:8px;">
        <tr><td class="jc-date" colspan="4">31/12/2023 — Provision perte complémentaire</td></tr>
        <tr class="jc-d"><td class="jc-compte">6815</td><td>Dotation aux provisions risques et charges</td><td class="jc-num">162 500</td><td></td></tr>
        <tr class="jc-c"><td class="jc-compte jc-indent">&nbsp;&nbsp;1518</td><td>Provisions pour pertes à terminaison</td><td></td><td class="jc-num">162 500</td></tr>
      </table>
      <div class="alert alert-danger" style="margin-top:8px;">🔴 Résultat 2023 = −37 500 (résultat) − 162 500 (provision) = <strong>−200 000 €</strong> au total. Cohérent avec la perte totale.</div>
    </div>
  </div>
</div>

<!-- ========== QUIZ ========== -->
<div id="quiz" class="content section">
  <div class="card">
    <h3>🎯 Quiz — 5 questions pour valider vos acquis</h3>
    <p style="font-size:13px;color:#666;margin-bottom:18px;">Cliquez sur la bonne réponse. Vous n'avez qu'une chance !</p>

    <div style="margin-bottom:18px;">
      <p style="font-weight:600;font-size:14px;margin-bottom:8px;">1. La méthode de l'achèvement est-elle la méthode de référence du PCG ?</p>
      <button class="quiz-option" id="q1a" onclick="checkQ(1,'a','b')">A — Oui, c'est la méthode recommandée par défaut</button>
      <button class="quiz-option" id="q1b" onclick="checkQ(1,'b','b')">B — Non, le PCG ne retient pas de méthode de référence entre les deux</button>
      <button class="quiz-option" id="q1c" onclick="checkQ(1,'c','b')">C — Non, la méthode de l'avancement est la seule méthode autorisée</button>
      <div id="fb1" class="alert alert-success" style="display:none;margin-top:6px;">✅ Exact ! Le PCG autorise les deux méthodes. En revanche, les normes IFRS (IFRS 15) imposent uniquement la méthode de l'avancement.</div>
    </div>

    <div style="margin-bottom:18px;">
      <p style="font-weight:600;font-size:14px;margin-bottom:8px;">2. Quel compte est débité pour constater le CA non encore facturé (méthode avancement) ?</p>
      <button class="quiz-option" id="q2a" onclick="checkQ(2,'a','b')">A — 335 Travaux en cours</button>
      <button class="quiz-option" id="q2b" onclick="checkQ(2,'b','b')">B — 418 Clients, produits non encore facturés</button>
      <button class="quiz-option" id="q2c" onclick="checkQ(2,'c','b')">C — 411 Clients</button>
      <div id="fb2" class="alert alert-success" style="display:none;margin-top:6px;">✅ Exact ! Le compte 418 est un compte de bilan (actif) qui matérialise la créance sur le client avant facturation officielle.</div>
    </div>

    <div style="margin-bottom:18px;">
      <p style="font-weight:600;font-size:14px;margin-bottom:8px;">3. Avec la méthode de l'avancement, charges cumulées = 840 000 € sur 1 200 000 € prévus. Quel est le taux d'avancement ?</p>
      <button class="quiz-option" id="q3a" onclick="checkQ(3,'a','b')">A — 50%</button>
      <button class="quiz-option" id="q3b" onclick="checkQ(3,'b','b')">B — 70%</button>
      <button class="quiz-option" id="q3c" onclick="checkQ(3,'c','b')">C — 60%</button>
      <div id="fb3" class="alert alert-success" style="display:none;margin-top:6px;">✅ Exact ! 840 000 / 1 200 000 = <strong>70%</strong>. Simple division des charges cumulées par les charges totales prévues.</div>
    </div>

    <div style="margin-bottom:18px;">
      <p style="font-weight:600;font-size:14px;margin-bottom:8px;">4. Une perte à terminaison de 120 000 € est détectée en cours de chantier. Que faut-il faire ?</p>
      <button class="quiz-option" id="q4a" onclick="checkQ(4,'a','a')">A — Provisionner 120 000 € immédiatement, quelle que soit la méthode</button>
      <button class="quiz-option" id="q4b" onclick="checkQ(4,'b','a')">B — Attendre la livraison pour constater la perte réelle</button>
      <button class="quiz-option" id="q4c" onclick="checkQ(4,'c','a')">C — Provisionner uniquement avec la méthode de l'achèvement</button>
      <div id="fb4" class="alert alert-success" style="display:none;margin-top:6px;">✅ Bravo ! Principe de prudence : toute perte probable est provisionnée dès sa détection, sans attendre la réalisation (compte 1518).</div>
    </div>

    <div style="margin-bottom:18px;">
      <p style="font-weight:600;font-size:14px;margin-bottom:8px;">5. À la fin du chantier (toutes années confondues), quelle méthode dégage la plus grande marge totale ?</p>
      <button class="quiz-option" id="q5a" onclick="checkQ(5,'a','c')">A — La méthode de l'achèvement</button>
      <button class="quiz-option" id="q5b" onclick="checkQ(5,'b','c')">B — La méthode de l'avancement</button>
      <button class="quiz-option" id="q5c" onclick="checkQ(5,'c','c')">C — Elles dégagent exactement la même marge totale</button>
      <div id="fb5" class="alert alert-success" style="display:none;margin-top:6px;">✅ Exactement ! La marge totale est identique avec les deux méthodes (600 000 €). La différence porte uniquement sur la <em>répartition dans le temps</em>.</div>
    </div>

    <div id="score-box" class="score-display">
      <div class="score-num" id="score-num">0/5</div>
      <div class="score-label">Votre score</div>
    </div>
  </div>
</div>

<!-- ========== COMPARATIF ========== -->
<div id="comparatif" class="content section">
  <div class="card">
    <h3>📊 Tableau comparatif final — Les 2 méthodes face à face</h3>
    <table>
      <tr><th>Exercice</th><th colspan="2" style="text-align:center;background:#2d6a9f;">⏹ Achèvement</th><th colspan="2" style="text-align:center;background:#2d9f6a;">📈 Avancement</th></tr>
      <tr><th></th><th>CA</th><th>Résultat</th><th>CA</th><th>Résultat</th></tr>
      <tr><td><strong>2023</strong></td><td class="num">0 €</td><td class="num">0 €</td><td class="num">750 000 €</td><td class="num" style="color:#2d9f6a;font-weight:700;">150 000 €</td></tr>
      <tr><td><strong>2024</strong></td><td class="num">0 €</td><td class="num">0 €</td><td class="num">1 350 000 €</td><td class="num" style="color:#2d9f6a;font-weight:700;">270 000 €</td></tr>
      <tr class="highlight"><td><strong>2025</strong></td><td class="num">3 000 000 €</td><td class="num" style="color:#2d9f6a;font-weight:700;">600 000 €</td><td class="num">900 000 €</td><td class="num" style="color:#2d9f6a;font-weight:700;">180 000 €</td></tr>
      <tr class="total-row"><td><strong>TOTAL</strong></td><td class="num">3 000 000 €</td><td class="num">600 000 €</td><td class="num">3 000 000 €</td><td class="num">600 000 €</td></tr>
    </table>
  </div>

  <div class="two-col">
    <div class="method-card achevement">
      <h4>⏹ Achèvement — Points clés</h4>
      <p>✅ Simple à appliquer<br>✅ Très prudent<br>❌ Image distordue : tout en 2025<br>❌ Résultat = 0 pendant 2 ans<br>❌ Non conforme IFRS</p>
    </div>
    <div class="method-card avancement">
      <h4>📈 Avancement — Points clés</h4>
      <p>✅ Image fidèle de la performance<br>✅ Marge lissée sur 3 exercices<br>✅ Conforme IFRS<br>❌ Plus complexe<br>❌ Requiert des estimations fiables</p>
    </div>
  </div>

  <div class="card">
    <h3>🏆 À retenir absolument pour l'examen</h3>
    <div class="alert alert-info" style="margin-bottom:8px;">📌 La marge totale est <strong>identique</strong> avec les deux méthodes. Seule la répartition temporelle diffère.</div>
    <div class="alert alert-warning" style="margin-bottom:8px;">📌 Toujours <strong>vérifier</strong> que la somme des CA sur toutes les années = prix de vente total du contrat.</div>
    <div class="alert alert-success" style="margin-bottom:8px;">📌 Avec l'avancement : <strong>extourner le compte 418</strong> en début d'exercice suivant pour ne comptabiliser que le différentiel annuel.</div>
    <div class="alert alert-danger">📌 <strong>Perte à terminaison</strong> = provisionnée immédiatement et intégralement (compte 1518), sans attendre la livraison.</div>
  </div>
</div>

<script>
const tabIds = ['contexte','rappels','achevement','avancement','deficit','quiz','comparatif'];

function show(id) {
  document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  const i = tabIds.indexOf(id);
  document.querySelectorAll('.tab')[i].classList.add('active');
}

/* ---- Vérifie si un champ est rempli ---- */
function isFilled(el) {
  if (!el) return false;
  return el.value.trim().length > 0;
}

/* ---- Mise à jour visuelle d'un champ ---- */
function checkFilled(id) {
  const el = document.getElementById(id);
  if (!el) return;
  el.classList.toggle('filled', isFilled(el));
  /* après chaque frappe, mettre à jour l'état du bouton de la question parente */
  const block = el.closest('.question-block');
  if (block) {
    const btn = block.querySelector('.btn-reveal');
    if (btn && !btn.classList.contains('done')) updateBtnState(btn);
  }
}

/* ---- Met à jour l'apparence du bouton selon si tous les champs sont remplis ---- */
function updateBtnState(btn) {
  const fieldIds = btn.dataset.fields ? btn.dataset.fields.split(',') : [];
  const allFilled = fieldIds.every(id => {
    const el = document.getElementById(id.trim());
    return el && isFilled(el);
  });
  if (allFilled) {
    btn.classList.add('ready');
    btn.textContent = '👁 Voir la correction';
  } else {
    btn.classList.remove('ready');
    btn.textContent = '🔒 Voir la correction';
  }
}

/* ---- Tentative de révélation : bloquée si champs incomplets ---- */
function tryReveal(btn) {
  /* Si déjà révélé, ne rien faire */
  if (btn.classList.contains('done')) return;

  const corrId  = btn.dataset.corr;
  const warnId  = 'warn-' + corrId;
  const fieldIds = btn.dataset.fields ? btn.dataset.fields.split(',') : [];

  /* Identifier les champs vides */
  const emptyIds = fieldIds.filter(id => {
    const el = document.getElementById(id.trim());
    return !el || !isFilled(el);
  });

  if (emptyIds.length > 0) {
    /* Mettre en évidence les champs vides */
    emptyIds.forEach(id => {
      const el = document.getElementById(id.trim());
      if (!el) return;
      el.style.outline = '2px solid #e07000';
      el.style.background = '#fff8e1';
      /* Retirer la mise en évidence après 2 s */
      setTimeout(() => {
        el.style.outline = '';
        el.style.background = el.classList.contains('filled') ? '#f8fff8' : '';
      }, 2000);
    });

    /* Afficher l'avertissement */
    const warn = document.getElementById(warnId);
    if (warn) {
      warn.classList.add('show');
      setTimeout(() => warn.classList.remove('show'), 3500);
    }

    /* Animation de secousse sur le bouton */
    btn.classList.remove('shake');
    void btn.offsetWidth; /* force reflow pour redémarrer l'animation */
    btn.classList.add('shake');
    setTimeout(() => btn.classList.remove('shake'), 500);
    return;
  }

  /* Tous les champs sont remplis → révéler */
  const corrBox = document.getElementById(corrId);
  if (corrBox) {
    corrBox.classList.add('show');
    corrBox.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
  }
  btn.classList.remove('ready');
  btn.classList.add('done');
  btn.textContent = '✅ Correction affichée';

  /* Masquer l'avertissement si visible */
  const warn = document.getElementById(warnId);
  if (warn) warn.classList.remove('show');
}

/* ---- Effacer tous les champs d'un bloc et réinitialiser le bouton ---- */
function clearBlock(ids, btnId) {
  ids.forEach(id => {
    const el = document.getElementById(id);
    if (!el) return;
    el.value = '';
    el.classList.remove('filled');
    el.style.outline = '';
    el.style.background = '';
  });

  if (btnId) {
    const btn = document.getElementById(btnId);
    if (btn) {
      btn.classList.remove('ready','done','shake');
      btn.textContent = '🔒 Voir la correction';
    }
    /* Masquer la correction */
    const corrId = btn ? btn.dataset.corr : null;
    if (corrId) {
      const corrBox = document.getElementById(corrId);
      if (corrBox) corrBox.classList.remove('show');
    }
    /* Masquer l'avertissement */
    const warn = document.getElementById('warn-' + (btn ? btn.dataset.corr : ''));
    if (warn) warn.classList.remove('show');
  }
}

/* ---- Initialisation : écouter les changements sur tous les inputs du journal ---- */
document.addEventListener('DOMContentLoaded', () => {
  /* Couvre tous les inputs/textareas à l'intérieur des blocs question */
  document.querySelectorAll('.question-block input, .question-block textarea').forEach(inp => {
    inp.addEventListener('input', () => {
      inp.classList.toggle('filled', isFilled(inp));
      const block = inp.closest('.question-block');
      if (block) {
        const btn = block.querySelector('.btn-reveal');
        if (btn && !btn.classList.contains('done')) updateBtnState(btn);
      }
    });
  });
  /* Initialiser l'état de tous les boutons */
  document.querySelectorAll('.btn-reveal[data-fields]').forEach(btn => updateBtnState(btn));
});

/* ---- Quiz ---- */
let quizScore = 0;
let answered = {};

function checkQ(qNum, choice, correct) {
  if (answered[qNum]) return;
  answered[qNum] = true;

  const letters = ['a','b','c'];
  letters.forEach(l => {
    const btn = document.getElementById('q' + qNum + l);
    if (!btn) return;
    btn.disabled = true;
    if (l === correct) btn.classList.add('correct');
    else if (l === choice && choice !== correct) btn.classList.add('wrong');
  });

  const fb = document.getElementById('fb' + qNum);
  if (fb) fb.style.display = 'block';

  if (choice === correct) quizScore++;

  if (Object.keys(answered).length === 5) {
    const box = document.getElementById('score-box');
    document.getElementById('score-num').textContent = quizScore + '/5';
    box.style.display = 'block';
    box.scrollIntoView({ behavior: 'smooth' });
  }
}
</script>
</body>
</html>
