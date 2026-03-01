<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>KLR-Lernwelt – Kosten- & Leistungsrechnung</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700&family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --navy: #1a2744;
    --navy-light: #243560;
    --indigo: #3a57b8;
    --indigo-light: #4f6dd4;
    --amber: #f59e0b;
    --amber-light: #fcd34d;
    --cream: #fafaf7;
    --white: #ffffff;
    --gray-50: #f8f9fa;
    --gray-100: #f0f2f5;
    --gray-200: #e2e6ed;
    --gray-400: #8a94a6;
    --gray-600: #4a5568;
    --gray-800: #1e2532;
    --green: #059669;
    --red: #dc2626;
    --shadow-sm: 0 1px 3px rgba(26,39,68,0.08);
    --shadow-md: 0 4px 16px rgba(26,39,68,0.10);
    --shadow-lg: 0 8px 32px rgba(26,39,68,0.13);
    --radius: 12px;
    --radius-lg: 18px;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }
  
  body {
    font-family: 'Plus Jakarta Sans', sans-serif;
    background: var(--cream);
    color: var(--gray-800);
    line-height: 1.65;
  }

  /* ── NAV ── */
  nav {
    background: var(--white);
    border-bottom: 2px solid var(--gray-100);
    position: sticky; top: 0; z-index: 100;
    box-shadow: var(--shadow-sm);
  }
  .nav-inner {
    max-width: 1200px; margin: 0 auto;
    display: flex; align-items: center; justify-content: space-between;
    padding: 0 24px; height: 64px;
  }
  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem; font-weight: 700;
    color: var(--navy); cursor: pointer;
    display: flex; align-items: center; gap: 10px; text-decoration: none;
  }
  .nav-logo span { color: var(--amber); }
  .nav-logo-icon {
    width: 34px; height: 34px; background: var(--navy);
    border-radius: 8px; display: flex; align-items: center; justify-content: center;
    font-size: 16px;
  }
  .nav-links {
    display: flex; gap: 4px; list-style: none;
  }
  .nav-links li a {
    padding: 7px 13px; border-radius: 8px;
    font-size: 0.85rem; font-weight: 600; text-decoration: none;
    color: var(--gray-600); transition: all 0.2s;
    cursor: pointer;
  }
  .nav-links li a:hover, .nav-links li a.active {
    background: var(--navy); color: var(--white);
  }
  .nav-cta {
    background: var(--amber); color: var(--navy) !important;
    border-radius: 8px; padding: 7px 16px !important;
    font-weight: 700 !important;
  }
  .nav-cta:hover { background: var(--amber-light) !important; color: var(--navy) !important; }

  /* ── PAGES ── */
  .page { display: none; }
  .page.active { display: block; }

  /* ── HERO ── */
  .hero {
    background: var(--navy);
    padding: 80px 24px 70px;
    text-align: center;
    position: relative; overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse 80% 60% at 50% 0%, #3a57b8 0%, transparent 70%);
    pointer-events: none;
  }
  .hero-badge {
    display: inline-block; background: rgba(245,158,11,0.18);
    border: 1px solid rgba(245,158,11,0.4);
    color: var(--amber-light); font-size: 0.78rem; font-weight: 700;
    letter-spacing: 0.08em; text-transform: uppercase;
    padding: 5px 14px; border-radius: 100px; margin-bottom: 22px;
  }
  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.2rem, 5vw, 3.4rem);
    color: var(--white); margin-bottom: 18px;
    line-height: 1.18;
  }
  .hero h1 em { color: var(--amber); font-style: normal; }
  .hero p {
    color: rgba(255,255,255,0.72); font-size: 1.08rem;
    max-width: 540px; margin: 0 auto 36px;
  }
  .hero-actions { display: flex; gap: 12px; justify-content: center; flex-wrap: wrap; }
  .btn-primary {
    background: var(--amber); color: var(--navy);
    font-weight: 700; font-size: 0.95rem; padding: 13px 28px;
    border-radius: 10px; border: none; cursor: pointer;
    transition: all 0.2s; text-decoration: none; display: inline-block;
  }
  .btn-primary:hover { background: var(--amber-light); transform: translateY(-1px); }
  .btn-outline {
    background: transparent; color: var(--white);
    font-weight: 600; font-size: 0.95rem; padding: 13px 28px;
    border-radius: 10px; border: 1.5px solid rgba(255,255,255,0.3); cursor: pointer;
    transition: all 0.2s; text-decoration: none; display: inline-block;
  }
  .btn-outline:hover { border-color: rgba(255,255,255,0.7); background: rgba(255,255,255,0.07); }

  /* ── SECTION ── */
  .section { max-width: 1200px; margin: 0 auto; padding: 64px 24px; }
  .section-sm { max-width: 1200px; margin: 0 auto; padding: 40px 24px; }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: 1.95rem; color: var(--navy); margin-bottom: 10px;
  }
  .section-sub {
    color: var(--gray-400); font-size: 1rem; margin-bottom: 36px;
  }

  /* ── CARDS GRID ── */
  .cards-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
  }
  .card {
    background: var(--white); border-radius: var(--radius-lg);
    padding: 28px 26px; box-shadow: var(--shadow-sm);
    border: 1px solid var(--gray-200);
    transition: transform 0.2s, box-shadow 0.2s;
    cursor: pointer;
  }
  .card:hover { transform: translateY(-4px); box-shadow: var(--shadow-lg); }
  .card-icon {
    width: 48px; height: 48px; border-radius: 12px;
    display: flex; align-items: center; justify-content: center;
    font-size: 22px; margin-bottom: 16px;
  }
  .card h3 { font-size: 1.05rem; font-weight: 700; color: var(--navy); margin-bottom: 8px; }
  .card p { font-size: 0.88rem; color: var(--gray-600); line-height: 1.6; }
  .card-arrow {
    margin-top: 18px; font-size: 0.82rem; font-weight: 700;
    color: var(--indigo); display: flex; align-items: center; gap: 5px;
  }

  /* ── STATS ROW ── */
  .stats-row {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 16px; margin-bottom: 56px;
  }
  .stat-card {
    background: var(--white); border-radius: var(--radius);
    padding: 24px; text-align: center;
    border: 1px solid var(--gray-200);
    box-shadow: var(--shadow-sm);
  }
  .stat-num { font-family: 'Playfair Display', serif; font-size: 2.2rem; color: var(--navy); font-weight: 700; }
  .stat-label { font-size: 0.8rem; color: var(--gray-400); font-weight: 600; text-transform: uppercase; letter-spacing: 0.06em; margin-top: 4px; }

  /* ── CONTENT PAGE STYLES ── */
  .content-header {
    background: var(--navy); padding: 52px 24px 48px; text-align: center;
  }
  .content-header .breadcrumb {
    font-size: 0.8rem; color: rgba(255,255,255,0.5); margin-bottom: 12px;
    text-transform: uppercase; letter-spacing: 0.06em;
  }
  .content-header h1 {
    font-family: 'Playfair Display', serif;
    color: var(--white); font-size: clamp(1.6rem, 4vw, 2.4rem);
  }
  .content-header p { color: rgba(255,255,255,0.65); margin-top: 10px; font-size: 1rem; }

  .content-body { max-width: 900px; margin: 0 auto; padding: 52px 24px; }

  .info-block {
    background: var(--white); border-radius: var(--radius-lg);
    padding: 32px; margin-bottom: 28px;
    border: 1px solid var(--gray-200); box-shadow: var(--shadow-sm);
  }
  .info-block h2 {
    font-family: 'Playfair Display', serif;
    font-size: 1.35rem; color: var(--navy); margin-bottom: 16px;
    display: flex; align-items: center; gap: 10px;
  }
  .info-block h2 .tag {
    font-size: 0.72rem; font-family: 'Plus Jakarta Sans', sans-serif;
    background: var(--gray-100); color: var(--gray-600);
    padding: 3px 10px; border-radius: 100px; font-weight: 700;
  }
  .info-block p { color: var(--gray-600); margin-bottom: 12px; }
  .info-block ul { list-style: none; }
  .info-block ul li {
    padding: 8px 0; border-bottom: 1px solid var(--gray-100);
    color: var(--gray-600); font-size: 0.93rem;
    display: flex; gap: 10px; align-items: flex-start;
  }
  .info-block ul li:last-child { border-bottom: none; }
  .info-block ul li::before { content: '→'; color: var(--indigo); font-weight: 700; flex-shrink: 0; margin-top: 1px; }

  .compare-grid {
    display: grid; grid-template-columns: 1fr 1fr; gap: 16px;
  }
  @media(max-width:600px){ .compare-grid { grid-template-columns: 1fr; } }
  .compare-box {
    background: var(--gray-50); border-radius: var(--radius);
    padding: 20px; border: 2px solid var(--gray-200);
  }
  .compare-box.highlight { border-color: var(--indigo); background: #eef1fb; }
  .compare-box h4 { font-size: 0.9rem; font-weight: 700; color: var(--navy); margin-bottom: 10px; }
  .compare-box ul li::before { content: '✓'; color: var(--green); }
  .compare-box.highlight ul li::before { content: '★'; color: var(--indigo); }

  .ecommerce-tag {
    display: inline-block; background: #fff7ed; border: 1px solid #fed7aa;
    color: #c2410c; font-size: 0.78rem; font-weight: 700;
    padding: 3px 10px; border-radius: 100px; margin-bottom: 10px;
    letter-spacing: 0.04em;
  }

  /* ── KLR AUFBAU DIAGRAM ── */
  .klr-flow {
    display: flex; gap: 0; margin: 24px 0;
    align-items: stretch;
  }
  @media(max-width:700px){ .klr-flow { flex-direction: column; } }
  .klr-step {
    flex: 1; background: var(--white); border: 2px solid var(--gray-200);
    border-radius: 0; padding: 24px 20px; text-align: center;
    position: relative;
  }
  .klr-step:first-child { border-radius: var(--radius) 0 0 var(--radius); }
  .klr-step:last-child { border-radius: 0 var(--radius) var(--radius) 0; }
  .klr-step.active { border-color: var(--indigo); background: #eef1fb; }
  .klr-step-num {
    width: 36px; height: 36px; background: var(--navy); color: var(--white);
    border-radius: 50%; display: flex; align-items: center; justify-content: center;
    font-weight: 700; font-size: 0.95rem; margin: 0 auto 12px;
  }
  .klr-step.active .klr-step-num { background: var(--indigo); }
  .klr-step h4 { font-size: 0.92rem; font-weight: 700; color: var(--navy); margin-bottom: 6px; }
  .klr-step p { font-size: 0.8rem; color: var(--gray-600); }
  .klr-step .klr-q { font-size: 1.3rem; margin-bottom: 8px; }
  .klr-arrow {
    display: flex; align-items: center; color: var(--indigo); font-size: 1.4rem;
    padding: 0 4px; font-weight: 700;
  }
  @media(max-width:700px){ .klr-arrow { transform: rotate(90deg); text-align: center; } }

  /* ── KALKULATOR ── */
  .calc-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 28px; }
  @media(max-width:700px){ .calc-grid { grid-template-columns: 1fr; } }
  .calc-inputs { display: flex; flex-direction: column; gap: 16px; }
  .input-row label { font-size: 0.82rem; font-weight: 700; color: var(--navy); display: block; margin-bottom: 5px; }
  .input-row input {
    width: 100%; padding: 10px 14px; border-radius: 8px;
    border: 1.5px solid var(--gray-200); font-size: 0.95rem;
    font-family: 'Plus Jakarta Sans', sans-serif; color: var(--gray-800);
    background: var(--gray-50); transition: border-color 0.2s;
  }
  .input-row input:focus { outline: none; border-color: var(--indigo); background: var(--white); }
  .input-row .hint { font-size: 0.76rem; color: var(--gray-400); margin-top: 3px; }
  .input-section-title {
    font-size: 0.75rem; font-weight: 700; text-transform: uppercase;
    letter-spacing: 0.08em; color: var(--gray-400);
    border-bottom: 1px solid var(--gray-200); padding-bottom: 8px; margin-bottom: 4px;
  }
  .calc-results { display: flex; flex-direction: column; gap: 10px; }
  .result-row {
    display: flex; justify-content: space-between; align-items: center;
    padding: 12px 16px; border-radius: 10px; background: var(--gray-50);
    border: 1px solid var(--gray-200);
  }
  .result-row.highlight {
    background: var(--navy); border-color: var(--navy);
  }
  .result-row .r-label { font-size: 0.85rem; font-weight: 600; color: var(--gray-600); }
  .result-row .r-value { font-size: 1rem; font-weight: 700; color: var(--navy); }
  .result-row.highlight .r-label { color: rgba(255,255,255,0.7); }
  .result-row.highlight .r-value { color: var(--amber); font-size: 1.1rem; }
  .result-row.green-row { background: #ecfdf5; border-color: #a7f3d0; }
  .result-row.green-row .r-label { color: #065f46; }
  .result-row.green-row .r-value { color: #059669; }
  .result-row.red-row { background: #fef2f2; border-color: #fecaca; }
  .result-row.red-row .r-label { color: #7f1d1d; }
  .result-row.red-row .r-value { color: #dc2626; }
  .calc-btn {
    background: var(--indigo); color: var(--white); border: none;
    padding: 13px; border-radius: 10px; font-size: 0.95rem;
    font-weight: 700; font-family: 'Plus Jakarta Sans', sans-serif;
    cursor: pointer; transition: background 0.2s; margin-top: 4px;
  }
  .calc-btn:hover { background: var(--navy); }
  .result-label-top { font-size: 0.78rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.06em; color: var(--gray-400); padding: 8px 16px 0; }

  /* ── QUIZ ── */
  .quiz-wrap { max-width: 700px; margin: 0 auto; }
  .quiz-progress-bar {
    height: 6px; background: var(--gray-200); border-radius: 100px;
    margin-bottom: 28px; overflow: hidden;
  }
  .quiz-progress-fill {
    height: 100%; background: var(--indigo); border-radius: 100px;
    transition: width 0.4s;
  }
  .quiz-card {
    background: var(--white); border-radius: var(--radius-lg);
    padding: 36px; box-shadow: var(--shadow-md);
    border: 1px solid var(--gray-200);
  }
  .quiz-num { font-size: 0.78rem; font-weight: 700; color: var(--gray-400); text-transform: uppercase; letter-spacing: 0.07em; margin-bottom: 12px; }
  .quiz-question { font-size: 1.12rem; font-weight: 700; color: var(--navy); margin-bottom: 24px; line-height: 1.4; }
  .quiz-options { display: flex; flex-direction: column; gap: 10px; }
  .quiz-opt {
    display: flex; align-items: center; gap: 14px;
    padding: 14px 18px; border-radius: 10px;
    border: 2px solid var(--gray-200); background: var(--gray-50);
    cursor: pointer; font-size: 0.93rem; color: var(--gray-700);
    transition: all 0.18s; font-family: 'Plus Jakarta Sans', sans-serif;
    text-align: left;
  }
  .quiz-opt:hover:not(:disabled) { border-color: var(--indigo); background: #eef1fb; }
  .quiz-opt.correct { border-color: var(--green); background: #ecfdf5; color: #065f46; font-weight: 600; }
  .quiz-opt.wrong { border-color: var(--red); background: #fef2f2; color: #7f1d1d; }
  .quiz-opt:disabled { cursor: not-allowed; }
  .quiz-opt-letter {
    width: 28px; height: 28px; border-radius: 7px;
    background: var(--gray-200); color: var(--gray-600);
    display: flex; align-items: center; justify-content: center;
    font-weight: 700; font-size: 0.8rem; flex-shrink: 0;
    transition: all 0.18s;
  }
  .quiz-opt.correct .quiz-opt-letter { background: var(--green); color: var(--white); }
  .quiz-opt.wrong .quiz-opt-letter { background: var(--red); color: var(--white); }
  .quiz-feedback {
    margin-top: 16px; padding: 14px 18px; border-radius: 10px;
    font-size: 0.9rem; font-weight: 600; display: none;
  }
  .quiz-feedback.show { display: block; }
  .quiz-feedback.ok { background: #ecfdf5; color: #065f46; }
  .quiz-feedback.nok { background: #fef2f2; color: #7f1d1d; }
  .quiz-next-btn {
    margin-top: 20px; background: var(--navy); color: var(--white);
    border: none; padding: 13px 28px; border-radius: 10px;
    font-size: 0.95rem; font-weight: 700; font-family: 'Plus Jakarta Sans', sans-serif;
    cursor: pointer; transition: background 0.2s; display: none;
  }
  .quiz-next-btn.show { display: inline-flex; }
  .quiz-next-btn:hover { background: var(--indigo); }
  .quiz-result {
    text-align: center; padding: 48px 32px;
    background: var(--white); border-radius: var(--radius-lg);
    box-shadow: var(--shadow-md); border: 1px solid var(--gray-200);
    display: none;
  }
  .quiz-result.show { display: block; }
  .quiz-score-big {
    font-family: 'Playfair Display', serif;
    font-size: 4rem; color: var(--navy); margin: 12px 0;
  }
  .quiz-result p { color: var(--gray-600); margin-bottom: 24px; }
  .quiz-restart {
    background: var(--amber); color: var(--navy);
    border: none; padding: 13px 28px; border-radius: 10px;
    font-size: 0.95rem; font-weight: 700; cursor: pointer;
    font-family: 'Plus Jakarta Sans', sans-serif; transition: background 0.2s;
  }
  .quiz-restart:hover { background: var(--amber-light); }

  /* ── ZUORDNUNG ── */
  .zuordnung-wrap { display: flex; gap: 24px; flex-wrap: wrap; }
  .begriffe-pool {
    display: flex; flex-direction: column; gap: 10px; min-width: 200px; flex: 1;
  }
  .begriffe-pool h4, .drop-zone h4 {
    font-size: 0.78rem; font-weight: 700; text-transform: uppercase;
    letter-spacing: 0.07em; color: var(--gray-400); margin-bottom: 8px;
  }
  .begriff-chip {
    background: var(--white); border: 2px solid var(--gray-200);
    border-radius: 8px; padding: 10px 14px;
    font-size: 0.88rem; font-weight: 600; color: var(--navy);
    cursor: grab; user-select: none; transition: all 0.18s;
    box-shadow: var(--shadow-sm);
  }
  .begriff-chip:hover { border-color: var(--indigo); transform: translateX(4px); }
  .begriff-chip.dragging { opacity: 0.4; }
  .begriff-chip.correct-placed { background: #ecfdf5; border-color: var(--green); color: #065f46; cursor: default; }
  .begriffe-drop-container {
    display: flex; gap: 16px; flex: 2; min-width: 280px;
  }
  .drop-zone {
    flex: 1; min-height: 200px; border-radius: var(--radius);
    border: 2px dashed var(--gray-300); padding: 16px; background: var(--gray-50);
    transition: border-color 0.2s, background 0.2s;
  }
  .drop-zone.dragover { border-color: var(--indigo); background: #eef1fb; }
  .drop-zone h4 { display: block; }
  .drop-zone-label {
    font-size: 0.93rem; font-weight: 700; color: var(--navy);
    padding: 8px 14px; border-radius: 8px; margin-bottom: 10px;
    text-align: center;
  }
  .drop-zone .placed-chip {
    background: var(--white); border: 2px solid var(--gray-200);
    border-radius: 8px; padding: 8px 12px;
    font-size: 0.85rem; font-weight: 600; color: var(--navy);
    margin-bottom: 8px; display: flex; justify-content: space-between; align-items: center;
  }
  .placed-chip .remove-btn {
    color: var(--gray-400); cursor: pointer; font-size: 1rem;
    background: none; border: none; padding: 0 2px;
  }
  .placed-chip.correct { border-color: var(--green); background: #ecfdf5; color: #065f46; }
  .placed-chip.wrong { border-color: var(--red); background: #fef2f2; color: #7f1d1d; }
  .zuord-actions { display: flex; gap: 12px; margin-top: 20px; flex-wrap: wrap; }
  .zuord-btn {
    padding: 11px 24px; border-radius: 10px; font-size: 0.92rem;
    font-weight: 700; cursor: pointer; border: none;
    font-family: 'Plus Jakarta Sans', sans-serif; transition: all 0.18s;
  }
  .zuord-btn.primary { background: var(--indigo); color: var(--white); }
  .zuord-btn.primary:hover { background: var(--navy); }
  .zuord-btn.secondary { background: var(--gray-100); color: var(--gray-600); }
  .zuord-btn.secondary:hover { background: var(--gray-200); }
  .zuord-score {
    margin-top: 16px; padding: 14px 18px; border-radius: 10px;
    font-size: 0.92rem; font-weight: 600; display: none;
  }
  .zuord-score.show { display: block; }

  /* ── QUELLEN ── */
  .source-item {
    background: var(--white); border-radius: var(--radius);
    padding: 18px 22px; border: 1px solid var(--gray-200);
    margin-bottom: 12px; display: flex; align-items: flex-start; gap: 14px;
  }
  .source-icon {
    width: 36px; height: 36px; border-radius: 8px;
    background: var(--gray-100); display: flex; align-items: center;
    justify-content: center; font-size: 16px; flex-shrink: 0; margin-top: 2px;
  }
  .source-item h4 { font-size: 0.92rem; font-weight: 700; color: var(--navy); margin-bottom: 3px; }
  .source-item p { font-size: 0.82rem; color: var(--gray-400); }

  /* ── BANNER ── */
  .banner {
    background: linear-gradient(135deg, var(--indigo) 0%, var(--navy) 100%);
    border-radius: var(--radius-lg); padding: 40px 36px;
    display: flex; gap: 24px; align-items: center; justify-content: space-between;
    flex-wrap: wrap; margin-bottom: 28px;
  }
  .banner-text h3 { font-family: 'Playfair Display', serif; color: var(--white); font-size: 1.35rem; margin-bottom: 6px; }
  .banner-text p { color: rgba(255,255,255,0.65); font-size: 0.9rem; }

  /* ── FOOTER ── */
  footer {
    background: var(--navy); color: rgba(255,255,255,0.45);
    text-align: center; padding: 32px 24px; font-size: 0.82rem; margin-top: 40px;
  }
  footer strong { color: rgba(255,255,255,0.7); }

  /* Misc */
  .pill {
    display: inline-block; padding: 3px 12px; border-radius: 100px;
    font-size: 0.76rem; font-weight: 700;
  }
  .pill-blue { background: #eef1fb; color: var(--indigo); }
  .pill-orange { background: #fff7ed; color: #c2410c; }
  .pill-green { background: #ecfdf5; color: #065f46; }

  .divider { border: none; border-top: 1px solid var(--gray-200); margin: 24px 0; }

  .table-wrap { overflow-x: auto; }
  table { width: 100%; border-collapse: collapse; font-size: 0.9rem; }
  thead th { background: var(--navy); color: var(--white); padding: 12px 16px; text-align: left; font-size: 0.82rem; text-transform: uppercase; letter-spacing: 0.06em; }
  tbody tr:nth-child(even) { background: var(--gray-50); }
  tbody td { padding: 11px 16px; border-bottom: 1px solid var(--gray-100); color: var(--gray-700); }
  tbody td:first-child { font-weight: 600; color: var(--navy); }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-inner">
    <a class="nav-logo" onclick="showPage('home')">
      <div class="nav-logo-icon">📊</div>
      KLR<span>-Lernwelt</span>
    </a>
    <ul class="nav-links">
      <li><a onclick="showPage('home')" id="nav-home" class="active">Start</a></li>
      <li><a onclick="showPage('grundbegriffe')" id="nav-grundbegriffe">Grundbegriffe</a></li>
      <li><a onclick="showPage('ziele')" id="nav-ziele">Ziele & Aufgaben</a></li>
      <li><a onclick="showPage('aufbau')" id="nav-aufbau">Aufbau KLR</a></li>
      <li><a onclick="showPage('praxis')" id="nav-praxis">Praxis</a></li>
      <li><a onclick="showPage('spiele')" id="nav-spiele" class="nav-cta">🎮 Lernspiele</a></li>
      <li><a onclick="showPage('quellen')" id="nav-quellen">Quellen</a></li>
    </ul>
  </div>
</nav>

<!-- ══════════ HOME ══════════ -->
<div class="page active" id="page-home">
  <div class="hero">
    <div class="hero-badge">Lernprodukt · E-Commerce · KLR</div>
    <h1>Kosten- &amp; Leistungsrechnung<br><em>einfach erklärt</em></h1>
    <p>Von Grundbegriffen bis Praxiskalkulation – alles Wichtige zur KLR mit Fokus auf den Online-Handel.</p>
    <div class="hero-actions">
      <button class="btn-primary" onclick="showPage('grundbegriffe')">Jetzt lernen →</button>
      <button class="btn-outline" onclick="showPage('spiele')">🎮 Zu den Lernspielen</button>
    </div>
  </div>

  <div class="section">
    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-num">3</div>
        <div class="stat-label">Stufen der KLR</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">3</div>
        <div class="stat-label">Lernspiele</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">€37</div>
        <div class="stat-label">Beispiel-Selbstkosten</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">576</div>
        <div class="stat-label">Break-even Bestellungen</div>
      </div>
    </div>

    <div class="section-title">Was erwartet dich?</div>
    <div class="section-sub">Klicke auf ein Thema, um direkt einzusteigen</div>

    <div class="cards-grid">
      <div class="card" onclick="showPage('grundbegriffe')">
        <div class="card-icon" style="background:#eef1fb">📖</div>
        <h3>Grundbegriffe</h3>
        <p>KLR vs. Finanzbuchhaltung, was sind Kosten und Leistungen? Mit konkreten E-Commerce-Beispielen.</p>
        <div class="card-arrow">Mehr erfahren →</div>
      </div>
      <div class="card" onclick="showPage('ziele')">
        <div class="card-icon" style="background:#fff7ed">🎯</div>
        <h3>Ziele & Aufgaben</h3>
        <p>Kalkulation, Wirtschaftlichkeitskontrolle, Planung – warum brauchen Online-Händler die KLR?</p>
        <div class="card-arrow">Mehr erfahren →</div>
      </div>
      <div class="card" onclick="showPage('aufbau')">
        <div class="card-icon" style="background:#ecfdf5">🏗️</div>
        <h3>Aufbau der KLR</h3>
        <p>Kostenartenrechnung → Kostenstellenrechnung → Kostenträgerrechnung. Schritt für Schritt erklärt.</p>
        <div class="card-arrow">Mehr erfahren →</div>
      </div>
      <div class="card" onclick="showPage('praxis')">
        <div class="card-icon" style="background:#fef3c7">🛒</div>
        <h3>Praxisbeispiel E-Commerce</h3>
        <p>Vollständige Kalkulation eines Online-Shops: variable Kosten, Fixkosten, Verkaufspreis, Break-even.</p>
        <div class="card-arrow">Mehr erfahren →</div>
      </div>
      <div class="card" onclick="showPage('spiele')">
        <div class="card-icon" style="background:#fce7f3">🎮</div>
        <h3>Lernspiele</h3>
        <p>Interaktiver Kalkulator, KLR-Wissensquiz und Begriff-Zuordnungsspiel – Wissen testen &amp; festigen.</p>
        <div class="card-arrow">Losspielen →</div>
      </div>
      <div class="card" onclick="showPage('quellen')">
        <div class="card-icon" style="background:#f5f3ff">📚</div>
        <h3>Quellen</h3>
        <p>Alle verwendeten Quellen und weiterführende Literatur übersichtlich aufgelistet.</p>
        <div class="card-arrow">Zur Quellenangabe →</div>
      </div>
    </div>
  </div>
</div>

<!-- ══════════ GRUNDBEGRIFFE ══════════ -->
<div class="page" id="page-grundbegriffe">
  <div class="content-header">
    <div class="breadcrumb">KLR-Lernwelt → Grundbegriffe</div>
    <h1>Grundbegriffe der KLR</h1>
    <p>Kosten, Leistungen und der Unterschied zur Finanzbuchhaltung</p>
  </div>
  <div class="content-body">

    <div class="info-block">
      <h2>📖 Was ist die KLR? <span class="tag">Definition</span></h2>
      <p>Die <strong>Kosten- und Leistungsrechnung (KLR)</strong> ist ein Teil des internen Rechnungswesens. Sie erfasst alle Kosten und Leistungen eines Unternehmens und dient der internen Steuerung, Kalkulation und Planung.</p>
      <p>Im Gegensatz zur Finanzbuchhaltung ist die KLR <em>nicht</em> gesetzlich vorgeschrieben, aber für gut geführte Unternehmen unverzichtbar.</p>
    </div>

    <div class="info-block">
      <h2>⚖️ KLR vs. Finanzbuchhaltung <span class="tag">Vergleich</span></h2>
      <div class="compare-grid">
        <div class="compare-box">
          <h4>📋 Finanzbuchhaltung (FiBu)</h4>
          <ul>
            <li>Externes Rechnungswesen</li>
            <li>Gesetzlich vorgeschrieben</li>
            <li>Begriffe: Aufwand & Ertrag</li>
            <li>Grundlage für GuV & Bilanz</li>
            <li>Richtet sich nach außen (Finanzamt, Banken)</li>
          </ul>
        </div>
        <div class="compare-box highlight">
          <h4>📊 Kostenrechnung / KLR</h4>
          <ul>
            <li>Internes Rechnungswesen</li>
            <li>Freiwillig, aber sinnvoll</li>
            <li>Begriffe: Kosten & Leistungen</li>
            <li>Grundlage für Entscheidungen</li>
            <li>Richtet sich nach innen (Management)</li>
          </ul>
        </div>
      </div>
      <div style="margin-top:16px; padding:14px 16px; background:#fff7ed; border-radius:8px; border:1px solid #fed7aa; font-size:0.88rem; color:#92400e;">
        ⚠️ <strong>Wichtig:</strong> Aufwand (FiBu) ≠ Kosten (KLR)! Neutrale Aufwendungen (z.B. Spenden, Steuern) werden in der KLR ausgeklammert; kalkulatorische Kosten (z.B. Unternehmerlohn) werden ergänzt.
      </div>
    </div>

    <div class="info-block">
      <h2>💰 Was sind Kosten? <span class="tag">Kernbegriff</span></h2>
      <p><strong>Kosten = bewerteter Verbrauch von Gütern und Leistungen</strong>, der für die betriebliche Leistungserstellung entsteht (in Euro erfasst).</p>
      <div class="ecommerce-tag">🛒 E-Commerce-Beispiele</div>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Kostenart</th><th>Beispiel im Online-Shop</th><th>Fix/Variabel</th></tr></thead>
          <tbody>
            <tr><td>Wareneinsatz</td><td>Einkaufspreis der verkauften Produkte</td><td><span class="pill pill-blue">Variabel</span></td></tr>
            <tr><td>Versand & Verpackung</td><td>Versandlabel + Karton je Paket</td><td><span class="pill pill-blue">Variabel</span></td></tr>
            <tr><td>Marketing (Ads)</td><td>Google Ads, Meta Ads pro Klick/Kauf</td><td><span class="pill pill-blue">Variabel</span></td></tr>
            <tr><td>Zahlungsgebühren</td><td>PayPal-Gebühr % je Transaktion</td><td><span class="pill pill-blue">Variabel</span></td></tr>
            <tr><td>Retourenabwicklung</td><td>Prüfung + Wiedereinlagerung je Retoure</td><td><span class="pill pill-blue">Variabel</span></td></tr>
            <tr><td>Lagermiete</td><td>Monatliche Miete für Lagerfläche</td><td><span class="pill pill-green">Fix</span></td></tr>
            <tr><td>Shop-Software</td><td>Shopify-Abo pro Monat</td><td><span class="pill pill-green">Fix</span></td></tr>
            <tr><td>Personal</td><td>Gehalt Kundenservice & Fulfillment</td><td><span class="pill pill-green">Fix</span></td></tr>
          </tbody>
        </table>
      </div>
    </div>

    <div class="info-block">
      <h2>📦 Was sind Leistungen? <span class="tag">Kernbegriff</span></h2>
      <p><strong>Leistungen = bewertete, betriebliche Outputs</strong> (erbrachte Güter/Dienstleistungen) eines Unternehmens in einer Periode.</p>
      <ul>
        <li>Verkaufte & ausgelieferte Produkte (= Umsatzleistung)</li>
        <li>Serviceleistungen (z.B. Individualisierung, Geschenkverpackung)</li>
        <li>Digitale Produkte / Abonnements</li>
        <li>Beratungsleistungen (z.B. Kundensupport)</li>
      </ul>
      <p style="margin-top:14px; padding:12px 16px; background:#f0f4ff; border-radius:8px; font-size:0.9rem;">
        <strong>Ziel:</strong> Leistungen werden in der KLR den Kosten gegenübergestellt, um den <em>Betriebserfolg</em> zu ermitteln: <br>
        <strong style="color:var(--navy)">Betriebserfolg = Leistungen − Kosten</strong>
      </p>
    </div>

    <div class="banner">
      <div class="banner-text">
        <h3>Bereit fürs nächste Thema?</h3>
        <p>Jetzt die Ziele und Aufgaben der KLR kennenlernen</p>
      </div>
      <button class="btn-primary" onclick="showPage('ziele')">Weiter: Ziele & Aufgaben →</button>
    </div>
  </div>
</div>

<!-- ══════════ ZIELE ══════════ -->
<div class="page" id="page-ziele">
  <div class="content-header">
    <div class="breadcrumb">KLR-Lernwelt → Ziele & Aufgaben</div>
    <h1>Ziele & Aufgaben der KLR</h1>
    <p>Kalkulation, Kontrolle und Planung – was die KLR leistet</p>
  </div>
  <div class="content-body">

    <div class="cards-grid" style="margin-bottom:28px">
      <div class="card" style="cursor:default">
        <div class="card-icon" style="background:#eef1fb">🧮</div>
        <h3>1. Kalkulation</h3>
        <p>Selbstkosten und Deckungsbeiträge ermitteln. Mindestpreise ableiten, damit kein Verlust entsteht.</p>
      </div>
      <div class="card" style="cursor:default">
        <div class="card-icon" style="background:#fff7ed">🔍</div>
        <h3>2. Wirtschaftlichkeitskontrolle</h3>
        <p>Soll-Ist-Vergleiche durchführen, Abweichungen erkennen und deren Ursachen analysieren.</p>
      </div>
      <div class="card" style="cursor:default">
        <div class="card-icon" style="background:#ecfdf5">📅</div>
        <h3>3. Planung & Entscheidungen</h3>
        <p>Budgets erstellen, Break-even-Analysen durchführen, Sortiments- und Kanalentscheidungen vorbereiten.</p>
      </div>
    </div>

    <div class="info-block">
      <h2>🛒 Warum ist KLR für Online-Händler besonders wichtig? <span class="tag">E-Commerce</span></h2>
      <ul>
        <li><strong>Preis- & Margendruck:</strong> Versand- und Werbekosten beeinflussen den Gewinn jeder einzelnen Bestellung direkt.</li>
        <li><strong>Viele variable Kosten je Bestellung:</strong> Verpackung, Versand, Zahlungs- und Marktplatzgebühren müssen pro Produkt/Bestellung sauber berechnet werden.</li>
        <li><strong>Marketing als größter Kostenblock:</strong> Rentabilität je Kanal prüfen (Kosten pro Bestellung vs. Deckungsbeitrag).</li>
        <li><strong>Retouren & Fulfillment:</strong> Verursachen erhebliche Zusatzkosten – die KLR macht diese transparent und planbar.</li>
        <li><strong>Marktplatzgebühren:</strong> Amazon FBA, eBay oder Zalando nehmen bis zu 15–20 % Provision – ohne KLR leicht übersehen.</li>
      </ul>
    </div>

    <div class="info-block">
      <h2>📊 Betriebserfolg berechnen <span class="tag">Kernaufgabe</span></h2>
      <p>Der <strong>Betriebserfolg (= Betriebsergebnis)</strong> zeigt, ob das operative Kerngeschäft profitabel ist:</p>
      <div style="background:var(--navy); color:var(--white); border-radius:12px; padding:24px; text-align:center; margin:16px 0; font-size:1.05rem;">
        <strong style="font-size:1.2rem; color:var(--amber)">Betriebserfolg</strong><br>
        = Betriebliche Leistungen<br>
        − Betriebliche Kosten
      </div>
      <p>Neutrale/außerordentliche Posten (z.B. Erlöse aus Anlageverkäufen) und reine Finanz-Ergebnisse werden dabei <em>separat</em> betrachtet.</p>
    </div>

    <div class="banner">
      <div class="banner-text">
        <h3>Wie ist die KLR aufgebaut?</h3>
        <p>Jetzt die drei Stufen der KLR kennenlernen</p>
      </div>
      <button class="btn-primary" onclick="showPage('aufbau')">Weiter: Aufbau der KLR →</button>
    </div>
  </div>
</div>

<!-- ══════════ AUFBAU ══════════ -->
<div class="page" id="page-aufbau">
  <div class="content-header">
    <div class="breadcrumb">KLR-Lernwelt → Aufbau der KLR</div>
    <h1>Aufbau der KLR</h1>
    <p>Die drei Stufen: Kostenarten – Kostenstellen – Kostenträger</p>
  </div>
  <div class="content-body">

    <div class="info-block">
      <h2>🏗️ Die drei Stufen im Überblick</h2>
      <div class="klr-flow">
        <div class="klr-step">
          <div class="klr-step-num">1</div>
          <div class="klr-q">📋</div>
          <h4>Kostenartenrechnung</h4>
          <p><em>Welche Kosten entstehen?</em><br>Kosten werden nach Art erfasst und kategorisiert.</p>
        </div>
        <div class="klr-arrow">→</div>
        <div class="klr-step active">
          <div class="klr-step-num">2</div>
          <div class="klr-q">📍</div>
          <h4>Kostenstellenrechnung</h4>
          <p><em>Wo entstehen die Kosten?</em><br>Gemeinkosten werden auf Bereiche/Abteilungen verteilt.</p>
        </div>
        <div class="klr-arrow">→</div>
        <div class="klr-step">
          <div class="klr-step-num">3</div>
          <div class="klr-q">🏷️</div>
          <h4>Kostenträgerrechnung</h4>
          <p><em>Wofür entstehen die Kosten?</em><br>Kosten werden Produkten oder Aufträgen zugeordnet.</p>
        </div>
      </div>
    </div>

    <div class="info-block">
      <h2>📋 Stufe 1: Kostenartenrechnung <span class="tag">Welche Kosten?</span></h2>
      <p>Alle Kosten werden systematisch nach ihrer Art erfasst und gegliedert. Grundlegende Unterscheidungen:</p>
      <ul>
        <li><strong>Personalkosten:</strong> Gehälter, Löhne, Sozialabgaben</li>
        <li><strong>Materialkosten:</strong> Wareneinsatz, Verpackungsmaterial</li>
        <li><strong>Betriebsmittelkosten:</strong> Miete, Abschreibungen, Energie</li>
        <li><strong>Dienstleistungskosten:</strong> Versand, Marketing, IT/Software</li>
        <li><strong>Kapitalkosten:</strong> Zinsen (kalkulatorisch)</li>
      </ul>
      <hr class="divider">
      <p><span class="pill pill-green">Fixkosten</span> entstehen unabhängig von der Produktionsmenge (z.B. Lagermiete). <span class="pill pill-blue">Variable Kosten</span> steigen mit der Menge (z.B. Versandkosten je Paket).</p>
    </div>

    <div class="info-block">
      <h2>📍 Stufe 2: Kostenstellenrechnung <span class="tag">Wo entstehen sie?</span></h2>
      <p><strong>Kostenstellen</strong> sind betriebliche Bereiche, denen Kosten zugeordnet werden. Im E-Commerce z.B.:</p>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Kostenstelle</th><th>Beispiele für zugeordnete Kosten</th></tr></thead>
          <tbody>
            <tr><td>🏭 Lager & Fulfillment</td><td>Miete, Lagerarbeit, Verpackungsmaterial</td></tr>
            <tr><td>🚚 Versand</td><td>Paketkosten, DHL-/UPS-Gebühren</td></tr>
            <tr><td>📣 Marketing</td><td>Ads-Budget, Agenturkosten, Rabattaktionen</td></tr>
            <tr><td>💬 Kundenservice</td><td>Personalkosten, CRM-Software</td></tr>
            <tr><td>💻 IT & Shop</td><td>Shopify-Abo, Server, Entwicklungskosten</td></tr>
          </tbody>
        </table>
      </div>
    </div>

    <div class="info-block">
      <h2>🏷️ Stufe 3: Kostenträgerrechnung <span class="tag">Wofür entstehen sie?</span></h2>
      <p>Die Kosten werden den <strong>Kostenträgern</strong> (= Produkte, Aufträge) zugeordnet. Man unterscheidet:</p>
      <ul>
        <li><strong>Einzelkosten:</strong> Direkt einem Produkt zurechenbar (z.B. Wareneinsatz, Verpackung)</li>
        <li><strong>Gemeinkosten:</strong> Nicht direkt zurechenbar, werden über Kostenstellen verteilt (z.B. Lagermiete anteilig je Bestellung)</li>
      </ul>
      <p style="margin-top:14px"><strong>Ergebnis:</strong> Man erhält die <em>Stückkosten</em> je Produkt oder Bestellung → Grundlage für Kalkulation und Preisbildung.</p>
    </div>

    <div class="banner">
      <div class="banner-text">
        <h3>Theorie in der Praxis sehen?</h3>
        <p>Vollständiges E-Commerce-Kalkulationsbeispiel anschauen</p>
      </div>
      <button class="btn-primary" onclick="showPage('praxis')">Weiter: Praxisbeispiel →</button>
    </div>
  </div>
</div>

<!-- ══════════ PRAXIS ══════════ -->
<div class="page" id="page-praxis">
  <div class="content-header">
    <div class="breadcrumb">KLR-Lernwelt → Praxisbeispiel</div>
    <h1>Praxisbeispiel: E-Commerce Kalkulation</h1>
    <p>Preisbildung und Break-even-Analyse für einen Online-Shop – Schritt für Schritt</p>
  </div>
  <div class="content-body">

    <div class="info-block">
      <h2>🛒 Ausgangssituation <span class="tag">Fallbeispiel</span></h2>
      <p>Ein Online-Shop verkauft Produkte (z.B. Elektronik-Zubehör). Wir berechnen den optimalen Verkaufspreis und wann der Shop profitabel wird.</p>
    </div>

    <div class="info-block">
      <h2>🔢 Schritt 1: Variable Kosten je Bestellung</h2>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Kostenposition</th><th>Betrag</th></tr></thead>
          <tbody>
            <tr><td>Wareneinsatz</td><td>20,00 €</td></tr>
            <tr><td>Verpackungsmaterial</td><td>1,00 €</td></tr>
            <tr><td>Versandkosten</td><td>5,00 €</td></tr>
            <tr><td>Marketingkosten pro Verkauf (Ads)</td><td>3,00 €</td></tr>
            <tr><td><strong>Summe variable Kosten</strong></td><td><strong>29,00 €</strong></td></tr>
          </tbody>
        </table>
      </div>
    </div>

    <div class="info-block">
      <h2>🔢 Schritt 2: Fixkosten je Bestellung</h2>
      <div class="table-wrap">
        <table>
          <thead><tr><th>Fixkostenblock</th><th>Monatlich</th></tr></thead>
          <tbody>
            <tr><td>Lagermiete & Nebenkosten</td><td>3.500 €</td></tr>
            <tr><td>Personal (Fulfillment + Service)</td><td>3.200 €</td></tr>
            <tr><td>Shop-Software & IT</td><td>300 €</td></tr>
            <tr><td><strong>Gesamt Fixkosten/Monat</strong></td><td><strong>8.000 €</strong></td></tr>
          </tbody>
        </table>
      </div>
      <p style="margin-top:14px; font-size:0.9rem; color:var(--gray-600);">Bei <strong>1.000 Bestellungen/Monat</strong>: Fixkosten je Bestellung = 8.000 € ÷ 1.000 = <strong>8,00 €</strong></p>
    </div>

    <div class="info-block">
      <h2>🔢 Schritt 3: Selbstkosten & Verkaufspreis</h2>
      <div style="display:flex; flex-direction:column; gap:10px; margin:12px 0">
        <div class="result-row">
          <div class="r-label">Variable Kosten</div>
          <div class="r-value">29,00 €</div>
        </div>
        <div class="result-row">
          <div class="r-label">+ Fixkosten je Bestellung</div>
          <div class="r-value">8,00 €</div>
        </div>
        <div class="result-row highlight">
          <div class="r-label">= Selbstkosten je Bestellung</div>
          <div class="r-value">37,00 €</div>
        </div>
        <div class="result-row">
          <div class="r-label">+ Gewinnzuschlag 15%</div>
          <div class="r-value">5,55 €</div>
        </div>
        <div class="result-row green-row">
          <div class="r-label">= Kalkulierter Verkaufspreis</div>
          <div class="r-value">42,55 € → gerundet: 42,90 €</div>
        </div>
      </div>
    </div>

    <div class="info-block">
      <h2>🔢 Schritt 4: Deckungsbeitrag & Break-even</h2>
      <div style="display:flex; flex-direction:column; gap:10px; margin:12px 0">
        <div class="result-row">
          <div class="r-label">Verkaufspreis</div>
          <div class="r-value">42,90 €</div>
        </div>
        <div class="result-row">
          <div class="r-label">− Variable Kosten je Bestellung</div>
          <div class="r-value">29,00 €</div>
        </div>
        <div class="result-row green-row">
          <div class="r-label">= Deckungsbeitrag (DB) je Bestellung</div>
          <div class="r-value">13,90 €</div>
        </div>
      </div>
      <div style="margin-top:16px; background:var(--gray-50); border-radius:10px; padding:18px 20px; border:1px solid var(--gray-200);">
        <p style="font-size:0.9rem; color:var(--gray-600); margin-bottom:6px;"><strong>Break-even-Bestellmenge:</strong></p>
        <p style="font-size:1.05rem; color:var(--navy);">8.000 € Fixkosten ÷ 13,90 € DB = <strong style="color:var(--indigo); font-size:1.15rem;">≈ 576 Bestellungen/Monat</strong></p>
        <p style="font-size:0.85rem; color:var(--gray-400); margin-top:6px;">Ab der 577. Bestellung beginnt der Shop, echten Gewinn zu machen.</p>
      </div>
    </div>

    <div class="banner">
      <div class="banner-text">
        <h3>Jetzt selbst rechnen!</h3>
        <p>Im interaktiven Kalkulator eigene Werte eingeben</p>
      </div>
      <button class="btn-primary" onclick="showPage('spiele'); showGame('kalkulator')">Zum Kalkulator →</button>
    </div>
  </div>
</div>

<!-- ══════════ SPIELE ══════════ -->
<div class="page" id="page-spiele">
  <div class="content-header">
    <div class="breadcrumb">KLR-Lernwelt → Lernspiele</div>
    <h1>🎮 Lernspiele</h1>
    <p>Wissen testen, Begriffe zuordnen und selbst kalkulieren</p>
  </div>
  <div class="section-sm">
    <!-- Game Tabs -->
    <div style="display:flex; gap:10px; margin-bottom:32px; flex-wrap:wrap">
      <button class="zuord-btn primary" id="tab-kalkulator" onclick="showGame('kalkulator')">🧮 Kalkulator</button>
      <button class="zuord-btn secondary" id="tab-quiz" onclick="showGame('quiz')">❓ Wissensquiz</button>
      <button class="zuord-btn secondary" id="tab-zuordnung" onclick="showGame('zuordnung')">🎯 Begriffe zuordnen</button>
    </div>

    <!-- KALKULATOR -->
    <div id="game-kalkulator">
      <div style="margin-bottom:24px">
        <h2 class="section-title">🧮 Interaktiver Kalkulator</h2>
        <p class="section-sub">Gib eigene Werte ein und sieh sofort das Ergebnis</p>
      </div>
      <div class="info-block" style="cursor:default">
        <div class="calc-grid">
          <div class="calc-inputs">
            <div class="input-section-title">Variable Kosten je Bestellung</div>
            <div class="input-row">
              <label>Wareneinsatz (€)</label>
              <input type="number" id="c-ware" value="20" min="0" step="0.5" oninput="calcUpdate()">
            </div>
            <div class="input-row">
              <label>Verpackung (€)</label>
              <input type="number" id="c-pack" value="1" min="0" step="0.1" oninput="calcUpdate()">
            </div>
            <div class="input-row">
              <label>Versandkosten (€)</label>
              <input type="number" id="c-versand" value="5" min="0" step="0.5" oninput="calcUpdate()">
            </div>
            <div class="input-row">
              <label>Marketingkosten pro Verkauf (€)</label>
              <input type="number" id="c-mktg" value="3" min="0" step="0.5" oninput="calcUpdate()">
            </div>
            <div class="input-section-title" style="margin-top:8px">Fixkosten & Ziele</div>
            <div class="input-row">
              <label>Fixkosten gesamt / Monat (€)</label>
              <input type="number" id="c-fix" value="8000" min="0" step="100" oninput="calcUpdate()">
            </div>
            <div class="input-row">
              <label>Erwartete Bestellungen / Monat</label>
              <input type="number" id="c-orders" value="1000" min="1" step="50" oninput="calcUpdate()">
            </div>
            <div class="input-row">
              <label>Gewinnzuschlag (%)</label>
              <input type="number" id="c-profit" value="15" min="0" max="200" step="1" oninput="calcUpdate()">
            </div>
          </div>
          <div>
            <div class="result-label-top">Ergebnisse</div>
            <div class="calc-results" id="calc-results">
              <!-- filled by JS -->
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- QUIZ -->
    <div id="game-quiz" style="display:none">
      <div style="margin-bottom:24px">
        <h2 class="section-title">❓ KLR-Wissensquiz</h2>
        <p class="section-sub">10 Fragen rund um die Kosten- und Leistungsrechnung</p>
      </div>
      <div class="quiz-wrap">
        <div class="quiz-progress-bar">
          <div class="quiz-progress-fill" id="quiz-prog" style="width:0%"></div>
        </div>
        <div id="quiz-card" class="quiz-card">
          <div class="quiz-num" id="quiz-num">Frage 1 von 10</div>
          <div class="quiz-question" id="quiz-q"></div>
          <div class="quiz-options" id="quiz-opts"></div>
          <div class="quiz-feedback" id="quiz-fb"></div>
          <button class="quiz-next-btn" id="quiz-next" onclick="quizNext()">Nächste Frage →</button>
        </div>
        <div class="quiz-result" id="quiz-result">
          <div style="font-size:2.5rem; margin-bottom:8px" id="quiz-result-emoji">🏆</div>
          <div class="quiz-score-big" id="quiz-score-big">0/10</div>
          <p id="quiz-result-text"></p>
          <button class="quiz-restart" onclick="quizStart()">Nochmal spielen 🔄</button>
        </div>
      </div>
    </div>

    <!-- ZUORDNUNG -->
    <div id="game-zuordnung" style="display:none">
      <div style="margin-bottom:24px">
        <h2 class="section-title">🎯 Begriffe zuordnen</h2>
        <p class="section-sub">Ziehe die Begriffe in die richtige Kategorie (Fix oder Variabel)</p>
      </div>
      <div class="info-block" style="cursor:default">
        <div class="zuordnung-wrap">
          <div class="begriffe-pool">
            <h4>Begriffe / Kosten</h4>
            <div id="begriffe-pool-items"></div>
          </div>
          <div class="begriffe-drop-container">
            <div class="drop-zone" id="drop-fix" ondragover="dragOver(event)" ondrop="dropItem(event,'fix')" ondragenter="dragEnter(event)" ondragleave="dragLeave(event)">
              <div class="drop-zone-label" style="background:#fff7ed; color:#c2410c">🔒 Fixkosten</div>
              <h4>Hierher ziehen</h4>
              <div id="placed-fix"></div>
            </div>
            <div class="drop-zone" id="drop-var" ondragover="dragOver(event)" ondrop="dropItem(event,'variabel')" ondragenter="dragEnter(event)" ondragleave="dragLeave(event)">
              <div class="drop-zone-label" style="background:#eef1fb; color:var(--indigo)">📈 Variable Kosten</div>
              <h4>Hierher ziehen</h4>
              <div id="placed-var"></div>
            </div>
          </div>
        </div>
        <div class="zuord-actions">
          <button class="zuord-btn primary" onclick="zuordnungCheck()">✅ Auswertung</button>
          <button class="zuord-btn secondary" onclick="zuordnungReset()">🔄 Zurücksetzen</button>
        </div>
        <div class="zuord-score" id="zuord-score"></div>
      </div>
    </div>
  </div>
</div>

<!-- ══════════ QUELLEN ══════════ -->
<div class="page" id="page-quellen">
  <div class="content-header">
    <div class="breadcrumb">KLR-Lernwelt → Quellen</div>
    <h1>Quellenangaben</h1>
    <p>Alle verwendeten Quellen und weiterführende Literatur</p>
  </div>
  <div class="content-body">

    <div class="info-block">
      <h2>📚 Wissenschaftliche Quellen</h2>

      <div class="source-item">
        <div class="source-icon">🎓</div>
        <div>
          <h4>Justus-Liebig-Universität Gießen (Prof. Dr. Arnt Wöhrmann)</h4>
          <p>Accounting – Grundlagen der Kostenrechnung (Skript, PDF)</p>
        </div>
      </div>

      <div class="source-item">
        <div class="source-icon">📖</div>
        <div>
          <h4>Universität Oldenburg (Lachnit/Müller)</h4>
          <p>Kosten- und Leistungsrechnung (Leseprobe, PDF, 2015)</p>
        </div>
      </div>

      <div class="source-item">
        <div class="source-icon">🏛️</div>
        <div>
          <h4>Freie und Hansestadt Hamburg, Finanzbehörde</h4>
          <p>Kosten- und Leistungsrechnung in der Hamburger Verwaltung (Leitfaden, PDF, 1996)</p>
        </div>
      </div>
    </div>

    <div class="info-block">
      <h2>🏢 Praxisquellen & Fachportale</h2>

      <div class="source-item">
        <div class="source-icon">💼</div>
        <div>
          <h4>IHK Chemnitz</h4>
          <p>Unternehmensplanung – Controlling: Kostenarten/Kostenstellen/Kostenträger, fix/variabel (Webseite)</p>
        </div>
      </div>

      <div class="source-item">
        <div class="source-icon">📊</div>
        <div>
          <h4>Lexware Unternehmerlexikon</h4>
          <p>Deckungsbeitrag; Betriebsergebnis (Fachlexikon-Webseiten)</p>
        </div>
      </div>

      <div class="source-item">
        <div class="source-icon">🛒</div>
        <div>
          <h4>Shopify Deutschland</h4>
          <p>Versandkosten im Online-Shop berechnen (Webseite)</p>
        </div>
      </div>
    </div>

    <div class="info-block">
      <h2>📦 E-Commerce-spezifische Quellen</h2>

      <div class="source-item">
        <div class="source-icon">📬</div>
        <div>
          <h4>DHL Paket GmbH</h4>
          <p>Preisübersicht DHL Paket (PDF, aktuell)</p>
        </div>
      </div>

      <div class="source-item">
        <div class="source-icon">📦</div>
        <div>
          <h4>Amazon Services Europe</h4>
          <p>Versand durch Amazon (FBA) – Gebührenübersicht (Rate Card, PDF)</p>
        </div>
      </div>

      <div class="source-item">
        <div class="source-icon">💡</div>
        <div>
          <h4>SnapSoft GmbH</h4>
          <p>Preiskalkulation im Onlineshop – Beispielrechnung (Webseite)</p>
        </div>
      </div>
    </div>

  </div>
</div>

<!-- FOOTER -->
<footer>
  <strong>KLR-Lernwelt</strong> · Lernprodukt Kosten- und Leistungsrechnung · E-Commerce-Fokus<br>
  Erstellt als Klausurersatzleistung · Alle Quellen korrekt angegeben
</footer>

<script>
// ── PAGE ROUTING ──
function showPage(name) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.nav-links a').forEach(a => a.classList.remove('active'));
  document.getElementById('page-' + name).classList.add('active');
  document.getElementById('nav-' + name).classList.add('active');
  window.scrollTo({top:0, behavior:'smooth'});
  if(name === 'spiele') { calcUpdate(); }
}

function showGame(name) {
  ['kalkulator','quiz','zuordnung'].forEach(g => {
    document.getElementById('game-' + g).style.display = g === name ? 'block' : 'none';
    document.getElementById('tab-' + g).className = 'zuord-btn ' + (g === name ? 'primary' : 'secondary');
  });
  if(name === 'quiz' && quizState.current === 0) quizStart();
  if(name === 'zuordnung' && !zuordInit) initZuordnung();
}

// ── KALKULATOR ──
function calcUpdate() {
  const ware = +document.getElementById('c-ware').value || 0;
  const pack = +document.getElementById('c-pack').value || 0;
  const versand = +document.getElementById('c-versand').value || 0;
  const mktg = +document.getElementById('c-mktg').value || 0;
  const fix = +document.getElementById('c-fix').value || 0;
  const orders = +document.getElementById('c-orders').value || 1;
  const pct = +document.getElementById('c-profit').value || 0;

  const varTotal = ware + pack + versand + mktg;
  const fixPerOrder = fix / orders;
  const selfcost = varTotal + fixPerOrder;
  const vkp = selfcost * (1 + pct/100);
  const db = vkp - varTotal;
  const be = db > 0 ? fix / db : Infinity;

  const fmt = v => isFinite(v) ? v.toFixed(2).replace('.',',') + ' €' : '–';
  const fmtN = v => isFinite(v) && !isNaN(v) ? Math.ceil(v).toLocaleString('de-DE') + ' Bestellungen' : '–';

  document.getElementById('calc-results').innerHTML = `
    <div class="result-row"><div class="r-label">Variable Kosten / Bestellung</div><div class="r-value">${fmt(varTotal)}</div></div>
    <div class="result-row"><div class="r-label">Fixkosten / Bestellung</div><div class="r-value">${fmt(fixPerOrder)}</div></div>
    <div class="result-row highlight"><div class="r-label">Selbstkosten / Bestellung</div><div class="r-value">${fmt(selfcost)}</div></div>
    <div class="result-row ${vkp >= 0 ? 'green-row' : 'red-row'}"><div class="r-label">Kalkulierter Verkaufspreis</div><div class="r-value">${fmt(vkp)}</div></div>
    <div class="result-row"><div class="r-label">Deckungsbeitrag / Bestellung</div><div class="r-value">${fmt(db)}</div></div>
    <div class="result-row ${db > 0 ? 'green-row' : 'red-row'}"><div class="r-label">Break-even-Bestellmenge</div><div class="r-value">${fmtN(be)}</div></div>
  `;
}
calcUpdate();

// ── QUIZ ──
const quizData = [
  { q: 'Was ist der Unterschied zwischen Aufwand (FiBu) und Kosten (KLR)?', opts: ['Beides bedeutet dasselbe', 'Aufwand ist ein externer Begriff, Kosten bezieht sich auf den betrieblichen Leistungsprozess', 'Kosten sind immer höher als Aufwand', 'Aufwand wird nur in der KLR verwendet'], correct: 1, explain: 'Aufwand (FiBu) umfasst alle Wertminderungen, Kosten (KLR) nur den betrieblichen Verbrauch – neutrale Posten werden ausgeklammert.' },
  { q: 'Ein Online-Shop zahlt monatlich 3.500 € Lagermiete. Um welche Kostenart handelt es sich?', opts: ['Variable Kosten', 'Fixkosten', 'Einzelkosten', 'Kalkulatorische Kosten'], correct: 1, explain: 'Lagermiete ist eine Fixkost – sie fällt unabhängig von der Anzahl der Bestellungen an.' },
  { q: 'Was versteht man unter dem Deckungsbeitrag (DB)?', opts: ['Verkaufspreis abzüglich Fixkosten', 'Verkaufspreis abzüglich variable Kosten', 'Gewinn nach Steuern', 'Umsatz minus Gesamtkosten'], correct: 1, explain: 'DB = Verkaufspreis − variable Kosten. Er zeigt, wie viel zur Deckung der Fixkosten übrig bleibt.' },
  { q: 'Was beantwortet die Kostenstellenrechnung?', opts: ['Welche Kosten entstehen?', 'Wofür entstehen die Kosten?', 'Wo entstehen die Kosten?', 'Wie hoch ist der Gewinn?'], correct: 2, explain: 'Die Kostenstellenrechnung fragt: Wo (in welcher Abteilung/welchem Bereich) entstehen Kosten?' },
  { q: 'Ein Online-Shop hat 8.000 € Fixkosten/Monat und einen DB von 16 € je Bestellung. Wie hoch ist die Break-even-Menge?', opts: ['400 Bestellungen', '500 Bestellungen', '600 Bestellungen', '800 Bestellungen'], correct: 1, explain: 'Break-even = Fixkosten / DB = 8.000 / 16 = 500 Bestellungen.' },
  { q: 'Was ist die Kostenartenrechnung?', opts: ['Erste Stufe der KLR: erfasst welche Kosten entstehen', 'Zweite Stufe der KLR: verteilt Kosten auf Kostenstellen', 'Dritte Stufe der KLR: ordnet Kosten Produkten zu', 'Eine Methode der Finanzbuchhaltung'], correct: 0, explain: 'Kostenartenrechnung ist die 1. Stufe der KLR und beantwortet: Welche Kosten entstehen?' },
  { q: 'Versandkosten von 5 € je Paket sind ein Beispiel für...', opts: ['Fixkosten', 'Gemeinkosten', 'Variable Kosten', 'Kalkulatorische Kosten'], correct: 2, explain: 'Versandkosten entstehen pro Paket – sie steigen mit der Menge, also variable Kosten.' },
  { q: 'Was ist der Betriebserfolg?', opts: ['Umsatz minus Steuern', 'Betriebliche Leistungen minus betriebliche Kosten', 'Gewinn nach Zinsen', 'Fixkosten minus variable Kosten'], correct: 1, explain: 'Betriebserfolg = betriebliche Leistungen − betriebliche Kosten (ohne neutrale Posten).' },
  { q: 'Für welchen Zweck dient die Kostenträgerrechnung?', opts: ['Kostenstellen anlegen', 'Kosten nach Art erfassen', 'Kosten Produkten/Aufträgen zuordnen', 'Liquidität planen'], correct: 2, explain: 'Die Kostenträgerrechnung (3. Stufe) ordnet Kosten den Kostenträgern (Produkten/Aufträgen) zu.' },
  { q: 'Warum ist die KLR für E-Commerce-Unternehmen besonders wichtig?', opts: ['Weil sie gesetzlich vorgeschrieben ist', 'Wegen hohem Preis- und Margendruck sowie vielen variablen Kosten je Bestellung', 'Weil sie die Jahressteuer berechnet', 'Weil sie Lagerbestände verwaltet'], correct: 1, explain: 'Im E-Commerce gibt es viele variable Kosten (Versand, Ads, Zahlungsgebühren) und hohen Wettbewerbsdruck – ohne KLR ist Profitabilität schwer planbar.' }
];

const quizState = { current: 0, score: 0, answered: false };

function quizStart() {
  quizState.current = 0; quizState.score = 0; quizState.answered = false;
  document.getElementById('quiz-result').classList.remove('show');
  document.getElementById('quiz-card').style.display = 'block';
  quizRender();
}

function quizRender() {
  const q = quizData[quizState.current];
  document.getElementById('quiz-num').textContent = `Frage ${quizState.current+1} von ${quizData.length}`;
  document.getElementById('quiz-q').textContent = q.q;
  document.getElementById('quiz-prog').style.width = (quizState.current / quizData.length * 100) + '%';
  document.getElementById('quiz-fb').className = 'quiz-feedback';
  document.getElementById('quiz-next').className = 'quiz-next-btn';
  quizState.answered = false;

  const letters = ['A','B','C','D'];
  document.getElementById('quiz-opts').innerHTML = q.opts.map((opt, i) =>
    `<button class="quiz-opt" onclick="quizAnswer(${i})">
      <span class="quiz-opt-letter">${letters[i]}</span>${opt}
    </button>`
  ).join('');
}

function quizAnswer(i) {
  if(quizState.answered) return;
  quizState.answered = true;
  const q = quizData[quizState.current];
  const opts = document.querySelectorAll('.quiz-opt');
  opts.forEach((btn, idx) => {
    btn.disabled = true;
    if(idx === q.correct) btn.classList.add('correct');
    else if(idx === i && i !== q.correct) btn.classList.add('wrong');
  });
  const isCorrect = i === q.correct;
  if(isCorrect) quizState.score++;
  const fb = document.getElementById('quiz-fb');
  fb.textContent = (isCorrect ? '✅ Richtig! ' : '❌ Falsch. ') + q.explain;
  fb.className = 'quiz-feedback show ' + (isCorrect ? 'ok' : 'nok');
  document.getElementById('quiz-next').className = 'quiz-next-btn show';
}

function quizNext() {
  quizState.current++;
  if(quizState.current >= quizData.length) {
    quizFinish();
  } else {
    quizRender();
  }
}

function quizFinish() {
  document.getElementById('quiz-prog').style.width = '100%';
  document.getElementById('quiz-card').style.display = 'none';
  const res = document.getElementById('quiz-result');
  res.classList.add('show');
  const s = quizState.score;
  const n = quizData.length;
  const emojis = s <= 4 ? '📚' : s <= 7 ? '👍' : '🏆';
  const texts = s <= 4 ? 'Noch etwas üben! Schau dir nochmal die Lernseiten an.' :
                s <= 7 ? 'Gut gemacht! Ein paar Themen kannst du noch vertiefen.' :
                'Ausgezeichnet! Du hast die KLR-Grundlagen sehr gut verstanden!';
  document.getElementById('quiz-result-emoji').textContent = emojis;
  document.getElementById('quiz-score-big').textContent = `${s}/${n}`;
  document.getElementById('quiz-result-text').textContent = texts;
}

// ── ZUORDNUNG ──
const begriffe = [
  { text: '🏠 Lagermiete', type: 'fix' },
  { text: '💻 Shop-Software Abo', type: 'fix' },
  { text: '👤 Festgehalt Kundenservice', type: 'fix' },
  { text: '📦 Versandlabel je Paket', type: 'variabel' },
  { text: '🛍️ Wareneinsatz je Bestellung', type: 'variabel' },
  { text: '📣 Google Ads je Klick', type: 'variabel' },
  { text: '💳 PayPal-Gebühr je Transaktion', type: 'variabel' },
  { text: '🏭 Stromkosten Lager (monatl.)', type: 'fix' },
  { text: '📦 Verpackungsmaterial je Paket', type: 'variabel' },
  { text: '📱 Festnetz-Telefonanlage', type: 'fix' },
];

let zuordState = {};
let zuordInit = false;

function initZuordnung() {
  zuordInit = true;
  zuordnungReset();
}

function zuordnungReset() {
  zuordState = {};
  begriffe.forEach((b,i) => zuordState[i] = null);
  renderPool();
  renderDrops();
  document.getElementById('zuord-score').className = 'zuord-score';
}

function renderPool() {
  const pool = document.getElementById('begriffe-pool-items');
  pool.innerHTML = begriffe.map((b,i) => {
    if(zuordState[i] !== null) return '';
    return `<div class="begriff-chip" draggable="true" data-id="${i}"
      ondragstart="dragStart(event,${i})">${b.text}</div>`;
  }).join('');
}

function renderDrops() {
  ['fix','var'].forEach(zone => {
    const cat = zone === 'fix' ? 'fix' : 'variabel';
    const container = document.getElementById('placed-' + zone);
    container.innerHTML = '';
    Object.entries(zuordState).forEach(([id, placed]) => {
      if(placed === cat) {
        const b = begriffe[id];
        container.innerHTML += `<div class="placed-chip" id="pchip-${id}">
          ${b.text}
          <button class="remove-btn" onclick="removeChip(${id})">✕</button>
        </div>`;
      }
    });
  });
}

function dragStart(e, id) {
  e.dataTransfer.setData('text', id);
  setTimeout(() => e.target.classList.add('dragging'), 0);
}
function dragOver(e) { e.preventDefault(); }
function dragEnter(e) { e.currentTarget.classList.add('dragover'); }
function dragLeave(e) { e.currentTarget.classList.remove('dragover'); }
function dropItem(e, category) {
  e.preventDefault();
  e.currentTarget.classList.remove('dragover');
  const id = parseInt(e.dataTransfer.getData('text'));
  zuordState[id] = category;
  renderPool();
  renderDrops();
}
function removeChip(id) {
  zuordState[id] = null;
  renderPool();
  renderDrops();
}

function zuordnungCheck() {
  let correct = 0, total = 0;
  Object.entries(zuordState).forEach(([id, placed]) => {
    if(placed !== null) {
      total++;
      const chip = document.getElementById('pchip-' + id);
      if(placed === begriffe[id].type) { correct++; if(chip) chip.classList.add('correct'); }
      else { if(chip) chip.classList.add('wrong'); }
    }
  });
  const score = document.getElementById('zuord-score');
  score.className = 'zuord-score show';
  const pct = total > 0 ? Math.round(correct/total*100) : 0;
  score.style.background = pct >= 80 ? '#ecfdf5' : pct >= 50 ? '#fff7ed' : '#fef2f2';
  score.style.color = pct >= 80 ? '#065f46' : pct >= 50 ? '#92400e' : '#7f1d1d';
  score.innerHTML = `Ergebnis: <strong>${correct} von ${total}</strong> richtig zugeordnet (${pct}%). ` +
    (pct === 100 ? '🎉 Perfekt!' : pct >= 80 ? '👍 Sehr gut!' : pct >= 50 ? 'Noch ein bisschen üben!' : '📚 Schau nochmal in die Lernseiten.');
  if(total < begriffe.length) score.innerHTML += ` Noch ${begriffe.length - total} Begriff(e) nicht zugeordnet.`;
}

// init
calcUpdate();
quizStart();
</script>
</body>
</html>
