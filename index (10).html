<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<!-- Hide everything until we've stripped any host-platform wrappers (Jekyll, etc.) -->
<style id="cleanup-shield">html { visibility: hidden; }</style>
<script>
  // Remove any wrapper elements injected by hosts like Jekyll/GitHub Pages defaults.
  // Strategy: keep only our app's expected top-level elements; nuke everything else.
  (function () {
    function cleanup() {
      var body = document.body;
      if (!body) return;

      // Whitelist: tag names / selectors that belong to our app
      var keepSelectors = ['HEADER', 'MAIN', 'SCRIPT', 'STYLE'];
      var keepClasses = ['toast-container', 'modal-overlay'];

      Array.prototype.slice.call(body.children).forEach(function (el) {
        var tag = el.tagName;
        var keep = keepSelectors.indexOf(tag) !== -1;
        if (!keep && el.className) {
          for (var i = 0; i < keepClasses.length; i++) {
            if (String(el.className).indexOf(keepClasses[i]) !== -1) { keep = true; break; }
          }
        }
        if (!keep) el.remove();
      });

      // Also strip any text-node nieces (raw text Jekyll may dump between tags)
      Array.prototype.slice.call(body.childNodes).forEach(function (n) {
        if (n.nodeType === 3 && n.textContent.trim()) n.remove();
      });

      // Strip <h1> tags Jekyll's default theme injects before our header
      var firstHeader = document.querySelector('header');
      if (firstHeader) {
        var sib = firstHeader.previousSibling;
        while (sib) {
          var prev = sib.previousSibling;
          sib.remove();
          sib = prev;
        }
      }

      // Reveal page once cleaned
      var shield = document.getElementById('cleanup-shield');
      if (shield) shield.remove();
      document.documentElement.style.visibility = 'visible';
    }

    if (document.readyState === 'loading') {
      document.addEventListener('DOMContentLoaded', cleanup);
    } else {
      cleanup();
    }
    // Safety: also run on full load in case host injects late
    window.addEventListener('load', cleanup);
  })();
</script>
<title>وردل عربي · Arabic Wordle</title>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0f0f10;
    --bg-2: #161618;
    --surface: #1c1c1e;
    --surface-2: #26262a;
    --surface-3: #2f2f33;
    --text: #ffffff;
    --muted: #9b9b9e;
    --muted-2: #6b6b6e;
    --border: #2f2f33;
    --border-2: #424246;
    --border-filled: #5a5a5e;
    --correct: #4ea355;
    --correct-glow: rgba(78, 163, 85, 0.45);
    --present: #c5a13a;
    --present-glow: rgba(197, 161, 58, 0.4);
    --absent: #36363a;
    --key-bg: #5b5b60;
    --key-bg-hover: #6a6a70;
    --key-text: #ffffff;
    --accent: #4ea355;
    --gold: #ffd86b;
    --silver: #c8c8c8;
    --bronze: #d59060;
    --shadow-key: 0 1px 0 rgba(0,0,0,0.35), inset 0 1px 0 rgba(255,255,255,0.06);
    --shadow-tile-correct: 0 0 0 1px rgba(255,255,255,0.04), 0 4px 14px var(--correct-glow);
    --shadow-tile-present: 0 0 0 1px rgba(255,255,255,0.04), 0 4px 14px var(--present-glow);
  }

  html, body {
    height: 100%;
    background: radial-gradient(ellipse at top, #1a1a1d 0%, var(--bg) 60%) fixed;
    color: var(--text);
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Tahoma",
                 "Geeza Pro", "Damascus", "Al Bayan", system-ui, sans-serif;
    overflow: hidden;
    -webkit-tap-highlight-color: transparent;
    -webkit-font-smoothing: antialiased;
    overscroll-behavior: none;
    touch-action: manipulation;
  }

  body {
    display: flex; flex-direction: column; align-items: center;
    height: 100vh;
    height: 100dvh; /* dynamic viewport — accounts for mobile address bar */
  }

  header {
    width: 100%;
    padding: 11px 14px;
    border-bottom: 1px solid var(--border);
    background: linear-gradient(180deg, rgba(255,255,255,0.02), transparent);
    display: flex; align-items: center; justify-content: space-between;
    gap: 8px; flex-shrink: 0;
    position: relative;
  }
  header::after {
    content: ''; position: absolute; bottom: -1px; left: 50%; transform: translateX(-50%);
    width: 60%; height: 1px;
    background: linear-gradient(90deg, transparent, var(--accent), transparent);
    opacity: 0.5;
  }

  h1 {
    font-size: clamp(20px, 4.8vw, 28px);
    font-weight: 800; letter-spacing: 0.5px;
    flex: 1; text-align: center;
    background: linear-gradient(180deg, #ffffff, #c8c8cc);
    -webkit-background-clip: text; background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .header-actions { display: flex; gap: 6px; }

  .icon-btn {
    background: var(--surface-2); border: 1px solid var(--border-2); color: var(--text);
    width: 38px; height: 38px; border-radius: 10px; cursor: pointer; font-size: 17px;
    display: flex; align-items: center; justify-content: center;
    transition: background 0.18s, border-color 0.18s, transform 0.08s;
    flex-shrink: 0;
  }
  .icon-btn:hover { background: var(--surface-3); border-color: var(--border-filled); }
  .icon-btn:active { transform: scale(0.93); }

  .name-pill {
    background: var(--surface-2); border: 1px solid var(--border-2); color: var(--text);
    height: 38px; border-radius: 10px; padding: 0 14px; font-family: inherit; font-size: 13px;
    font-weight: 700; cursor: pointer; max-width: 130px; overflow: hidden;
    text-overflow: ellipsis; white-space: nowrap;
    transition: background 0.18s, border-color 0.18s, transform 0.08s;
    flex-shrink: 0;
  }
  .name-pill:hover { background: var(--surface-3); border-color: var(--border-filled); }
  .name-pill:active { transform: scale(0.96); }

  main {
    flex: 1; width: 100%; max-width: 560px;
    display: flex; flex-direction: column; align-items: center;
    padding: 4px 6px; overflow: hidden; min-height: 0;
    padding-bottom: env(safe-area-inset-bottom, 0);
  }

  .info-bar {
    width: 100%; display: flex; align-items: center; justify-content: center;
    gap: 8px; flex-wrap: wrap; padding: 4px 0; flex-shrink: 0;
    font-size: 11.5px; color: var(--muted);
  }
  .info-bar strong { color: var(--text); }
  .timer-badge {
    background: var(--surface-2); border: 1px solid var(--border-2);
    padding: 3px 9px; border-radius: 999px; font-size: 11px;
    color: var(--muted); font-weight: 600; display: inline-flex; align-items: center; gap: 5px;
  }
  .timer-badge .dot { width: 5px; height: 5px; border-radius: 50%; background: var(--accent); animation: pulse 2s ease-in-out infinite; }
  .timer-badge #mainTimer { color: var(--text); font-variant-numeric: tabular-nums; direction: ltr; font-weight: 700; }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.85); }
  }

  /* Board takes available vertical space; keyboard always sits at the bottom */
  .board-wrap {
    display: flex; align-items: center; justify-content: center;
    flex: 1 1 auto; width: 100%; padding: 4px 0; min-height: 0;
  }

  .board {
    display: grid; grid-template-rows: repeat(6, 1fr); gap: 5px;
    /* Tighter math: reserve more room for header/keyboard, especially when embedded. */
    aspect-ratio: 5 / 6;
    width: 100%;
    max-width: min(310px, 78vw, calc((100dvh - 310px) * 5/6));
    height: auto;
  }

  .row { display: grid; grid-template-columns: repeat(5, 1fr); gap: 6px; direction: rtl; }

  .tile {
    border: 2px solid var(--border-2); border-radius: 4px;
    display: flex; align-items: center; justify-content: center;
    font-size: clamp(22px, 6.5vw, 32px); font-weight: 800; line-height: 1;
    user-select: none; transition: border-color 0.12s, transform 0.08s;
    background: transparent;
  }
  .tile.filled {
    border-color: var(--border-filled);
    animation: pop 0.14s ease;
  }
  .tile.flip { animation: flip 0.6s ease forwards; }
  .tile.correct { background: var(--correct); border-color: var(--correct); color: #fff; box-shadow: var(--shadow-tile-correct); }
  .tile.present { background: var(--present); border-color: var(--present); color: #fff; box-shadow: var(--shadow-tile-present); }
  .tile.absent  { background: var(--absent);  border-color: var(--absent);  color: #fff; }

  .row.shake { animation: shake 0.45s ease; }
  .row.win .tile { animation: bounce 0.6s ease; }
  .row.win .tile:nth-child(1) { animation-delay: 0.0s; }
  .row.win .tile:nth-child(2) { animation-delay: 0.1s; }
  .row.win .tile:nth-child(3) { animation-delay: 0.2s; }
  .row.win .tile:nth-child(4) { animation-delay: 0.3s; }
  .row.win .tile:nth-child(5) { animation-delay: 0.4s; }

  @keyframes pop { 0% { transform: scale(0.85); } 60% { transform: scale(1.08); } 100% { transform: scale(1); } }
  @keyframes flip { 0% { transform: rotateX(0); } 50% { transform: rotateX(-90deg); } 100% { transform: rotateX(0); } }
  @keyframes shake { 0%,100% { transform: translateX(0); } 20%,60% { transform: translateX(-9px); } 40%,80% { transform: translateX(9px); } }
  @keyframes bounce { 0%,100% { transform: translateY(0); } 40% { transform: translateY(-22px); } 70% { transform: translateY(-5px); } }

  /* Keyboard always at the bottom, sized in viewport units so keys are always visible */
  .keyboard {
    width: 100%; max-width: 560px;
    padding: 6px 4px calc(8px + env(safe-area-inset-bottom, 0));
    direction: rtl; flex-shrink: 0;
    display: flex; flex-direction: column; gap: 5px;
  }
  .keyboard-row {
    display: flex; justify-content: center; gap: 4px;
    /* Each row: ~7vh tall, capped so it doesn't get huge on tablets */
    height: clamp(38px, 7vh, 56px);
  }

  .key {
    flex: 1; min-width: 0; height: 100%;
    border: none; border-radius: 6px;
    background: var(--key-bg); color: var(--key-text); font-family: inherit;
    font-size: clamp(13px, 4.2vw, 19px); font-weight: 700; cursor: pointer; user-select: none;
    box-shadow: var(--shadow-key);
    transition: background 0.22s, transform 0.06s, box-shadow 0.15s;
    padding: 0;
  }
  .key:hover { background: var(--key-bg-hover); }
  .key:active { transform: translateY(1px) scale(0.96); box-shadow: 0 0 0 rgba(0,0,0,0); }
  .key.wide { flex: 1.7; font-size: clamp(11px, 3vw, 14px); }
  .key.correct { background: var(--correct); box-shadow: var(--shadow-tile-correct); }
  .key.present { background: var(--present); box-shadow: var(--shadow-tile-present); }
  .key.absent  { background: var(--absent); color: #b6b6b9; box-shadow: none; }

  .toast-container { position: fixed; top: 70px; left: 50%; transform: translateX(-50%); z-index: 300; display: flex; flex-direction: column; gap: 8px; pointer-events: none; }
  .toast {
    background: #ffffff; color: #0e0e10; padding: 12px 22px; border-radius: 8px;
    font-weight: 700; font-size: 14px; animation: toastIn 0.2s ease;
    box-shadow: 0 8px 22px rgba(0,0,0,0.5); white-space: nowrap;
  }
  .toast.fade { animation: toastOut 0.45s ease forwards; }
  @keyframes toastIn  { from { opacity: 0; transform: translateY(-12px); } to { opacity: 1; transform: translateY(0); } }
  @keyframes toastOut { from { opacity: 1; } to { opacity: 0; transform: translateY(-6px); } }

  .modal-overlay {
    position: fixed; inset: 0; background: rgba(0,0,0,0.78);
    display: none; align-items: center; justify-content: center;
    z-index: 200; padding: 16px; backdrop-filter: blur(6px); -webkit-backdrop-filter: blur(6px);
    overflow-y: auto;
  }
  .modal-overlay.show { display: flex; animation: fadeIn 0.25s ease; }

  .modal {
    background: linear-gradient(180deg, var(--surface), var(--bg-2));
    border: 1px solid var(--border-2); border-radius: 16px;
    padding: 28px 24px 22px; max-width: 400px; width: 100%; text-align: center;
    animation: scaleIn 0.32s cubic-bezier(0.34, 1.56, 0.64, 1);
    max-height: calc(100vh - 32px); overflow-y: auto;
    box-shadow: 0 24px 60px rgba(0,0,0,0.55);
  }
  .modal h2 { font-size: 24px; margin-bottom: 8px; font-weight: 800; }
  .modal p  { margin-bottom: 6px; font-size: 14px; color: var(--muted); }

  .modal .word { font-size: 32px; font-weight: 800; color: var(--correct); margin: 14px 0 4px; letter-spacing: 3px; }
  .modal .word.lose { color: var(--present); }
  .modal .meaning {
    font-size: 13.5px; color: #d2d2d5; margin: 4px 8px 10px;
    padding: 10px 14px; background: var(--surface-2);
    border-right: 3px solid var(--accent); border-radius: 6px;
    text-align: right; line-height: 1.55;
  }
  .modal .meaning.empty { display: none; }
  .modal .meaning .label { color: var(--muted); font-size: 11px; display: block; margin-bottom: 3px; font-weight: 700; letter-spacing: 0.5px; }

  .stats { display: flex; justify-content: center; gap: 22px; margin: 14px 0 4px; font-size: 14px; color: var(--muted); }
  .stats strong { color: var(--text); font-weight: 700; }

  .stats-container { display: flex; justify-content: space-around; margin: 14px 0 18px; gap: 4px; }
  .stat-box {
    display: flex; flex-direction: column; align-items: center;
    flex: 1; padding: 10px 4px;
    background: var(--surface-2); border-radius: 10px;
    border: 1px solid var(--border);
  }
  .stat-num { font-size: 24px; font-weight: 800; color: var(--text); line-height: 1.1; }
  .stat-label { font-size: 10.5px; color: var(--muted); text-align: center; margin-top: 4px; line-height: 1.2; font-weight: 600; }

  .dist-container { width: 100%; padding: 4px 0; }
  .dist-row { display: flex; align-items: center; gap: 8px; margin-bottom: 5px; font-size: 12px; font-weight: 700; }
  .dist-label { width: 16px; text-align: center; color: var(--text); flex-shrink: 0; }
  .dist-bar-bg { flex: 1; background: var(--surface-2); border-radius: 4px; overflow: hidden; height: 22px; display: flex; }
  .dist-bar {
    background: linear-gradient(90deg, #424246, #5a5a5e);
    color: white; text-align: end; padding: 0 8px;
    border-radius: 4px; min-width: 22px;
    display: flex; align-items: center; justify-content: flex-end;
    transition: width 0.6s cubic-bezier(0.4, 0, 0.2, 1);
    direction: ltr; font-weight: 700;
  }
  .dist-bar.highlight {
    background: linear-gradient(90deg, var(--correct), #6dbf66);
    box-shadow: 0 0 12px var(--correct-glow);
  }

  .modal-btn {
    margin-top: 16px;
    background: linear-gradient(180deg, var(--correct), #3e8b44);
    color: #fff; border: none; padding: 13px 32px; border-radius: 10px;
    cursor: pointer; font-family: inherit; font-size: 15px; font-weight: 700;
    transition: opacity 0.2s, transform 0.08s, box-shadow 0.15s;
    width: 100%;
    box-shadow: 0 4px 14px var(--correct-glow);
  }
  .modal-btn:hover { opacity: 0.95; box-shadow: 0 6px 18px var(--correct-glow); }
  .modal-btn:active { transform: scale(0.97); }
  .modal-btn.secondary {
    background: var(--surface-3); border: 1px solid var(--border-2);
    box-shadow: none; margin-top: 8px;
  }
  .modal-btn.secondary:hover { background: var(--border-2); box-shadow: none; }

  .name-input {
    width: 100%; background: var(--surface-2); border: 1px solid var(--border-2);
    color: var(--text); padding: 14px 14px; border-radius: 10px; font-family: inherit;
    font-size: 16px; font-weight: 600; text-align: center; margin: 14px 0 4px;
    direction: rtl; outline: none; transition: border-color 0.2s, background 0.2s;
  }
  .name-input:focus { border-color: var(--accent); background: var(--surface-3); }
  .name-input::placeholder { color: var(--muted); font-weight: 400; }

  .lb-section { margin-top: 18px; padding-top: 16px; border-top: 1px solid var(--border); }
  .lb-section h3 { font-size: 14px; margin-bottom: 10px; font-weight: 700; color: var(--muted); text-align: center; }

  .lb-list { text-align: right; max-height: 260px; overflow-y: auto; padding-left: 2px; }
  .lb-row {
    display: grid; grid-template-columns: 30px 1fr auto; align-items: center;
    gap: 10px; padding: 9px 12px; background: var(--surface-2); border-radius: 8px;
    margin-bottom: 5px; font-size: 13px;
    border: 1px solid transparent;
    transition: background 0.15s;
  }
  .lb-row:hover { background: var(--surface-3); }
  .lb-row.me { background: rgba(78, 163, 85, 0.16); border-color: var(--correct); }
  .lb-rank { font-weight: 800; text-align: center; color: var(--muted); font-size: 13px; }
  .lb-row:nth-child(1) .lb-rank { color: var(--gold); font-size: 18px; }
  .lb-row:nth-child(2) .lb-rank { color: var(--silver); font-size: 16px; }
  .lb-row:nth-child(3) .lb-rank { color: var(--bronze); font-size: 16px; }
  .lb-name { font-weight: 700; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; }
  .lb-meta { color: var(--muted); font-size: 12px; font-weight: 600; text-align: left; direction: ltr; font-variant-numeric: tabular-nums; }
  .lb-meta .res-win { color: #6dbf66; font-weight: 700; }
  .lb-meta .res-loss { color: #c46a6a; font-weight: 700; }

  .empty-lb { text-align: center; color: var(--muted); padding: 22px 0; font-size: 13px; }
  .lb-date { font-size: 12px; color: var(--muted); margin-bottom: 10px; font-variant-numeric: tabular-nums; direction: ltr; text-align: center; }

  .replay-note {
    margin: 14px 0 0; padding: 10px 14px;
    background: rgba(197, 161, 58, 0.12);
    border: 1px solid rgba(197, 161, 58, 0.3);
    border-radius: 8px; font-size: 12.5px; color: #e2c878;
    font-weight: 600;
  }

  @keyframes fadeIn  { from { opacity: 0; } to { opacity: 1; } }
  @keyframes scaleIn { from { opacity: 0; transform: scale(0.92); } to { opacity: 1; transform: scale(1); } }

  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: var(--border-2); border-radius: 3px; }
  ::-webkit-scrollbar-thumb:hover { background: var(--border-filled); }

  /* Phone-specific: aggressive shrinking */
  @media (max-width: 480px) {
    header { padding: 6px 10px; }
    h1 { font-size: 17px; }
    .icon-btn { width: 32px; height: 32px; font-size: 14px; border-radius: 8px; }
    .name-pill { height: 32px; font-size: 11.5px; padding: 0 9px; max-width: 90px; border-radius: 8px; }
    .info-bar { font-size: 10.5px; padding: 2px 0; gap: 5px; }
    .timer-badge { padding: 2px 8px; font-size: 10.5px; }
    .modal { padding: 22px 18px 18px; }
    .tile { font-size: clamp(18px, 6vw, 26px); border-width: 2px; }
    .keyboard-row { height: clamp(34px, 6vh, 48px); }
    .keyboard { padding: 4px 3px calc(6px + env(safe-area-inset-bottom, 0)); gap: 4px; }
    .board { gap: 4px; max-width: min(280px, 74vw, calc((100dvh - 270px) * 5/6)); }
    .row { gap: 4px; }
    .key { font-size: clamp(13px, 4vw, 17px); border-radius: 5px; }
    .key.wide { font-size: clamp(10px, 2.8vw, 12px); }
  }

  /* Short viewports (e.g. embedded preview frames that eat ~150px of chrome) */
  @media (max-height: 720px) {
    header { padding: 5px 10px; }
    h1 { font-size: 16px; }
    .info-bar { padding: 1px 0; }
    .icon-btn { width: 30px; height: 30px; font-size: 13px; }
    .name-pill { height: 30px; font-size: 11px; padding: 0 8px; max-width: 80px; }
    .keyboard-row { height: clamp(30px, 5.2vh, 42px); }
    .keyboard { padding: 3px 3px 5px; gap: 3px; }
    .board { gap: 3px; max-width: min(240px, 68vw, calc((100dvh - 220px) * 5/6)); }
    .row { gap: 3px; }
    .tile { font-size: clamp(16px, 5.5vw, 24px); }
    .key { font-size: clamp(12px, 3.8vw, 16px); }
  }

  /* Very short viewports — landscape phones or heavy embed chrome */
  @media (max-height: 600px) {
    .keyboard-row { height: clamp(28px, 5vh, 38px); }
    .board { max-width: min(200px, 56vw, calc((100dvh - 200px) * 5/6)); }
    .tile { font-size: clamp(14px, 5vw, 20px); }
    h1 { font-size: 15px; }
    header { padding: 3px 10px; }
  }

  @media (min-height: 820px) and (min-width: 481px) {
    .board { max-width: min(360px, 84vw, calc((100dvh - 280px) * 5/6)); }
  }
</style>
</head>
<body>
  <header>
    <div class="header-actions">
      <button class="icon-btn" id="lbBtn" title="لوحة المتصدرين">🏆</button>
      <button class="icon-btn" id="statsBtn" title="الإحصائيات">📊</button>
    </div>
    <h1>وردل عربي</h1>
    <button class="name-pill" id="namePill" title="تغيير الاسم">—</button>
  </header>

  <main>
    <div class="info-bar">
      <span id="infoDateStr">لغز اليوم</span>
      <span class="timer-badge"><span class="dot"></span>التالي: <span id="mainTimer">00:00:00</span></span>
    </div>
    <div class="board-wrap"><div class="board" id="board"></div></div>
    <div class="keyboard" id="keyboard"></div>
  </main>

  <div class="toast-container" id="toastContainer"></div>

  <div class="modal-overlay show" id="nameModal">
    <div class="modal">
      <h2>وردل عربي</h2>
      <p>اكتب اسمك للظهور في لوحة المتصدرين</p>
      <input type="text" class="name-input" id="nameInput" maxlength="20" placeholder="اسم اللاعب" autocomplete="off">
      <button class="modal-btn" id="startBtn">ابدأ اللعب</button>
    </div>
  </div>

  <div class="modal-overlay" id="endModal">
    <div class="modal">
      <h2 id="endTitle"></h2>
      <p id="endText"></p>
      <div class="word" id="endWord"></div>
      <div class="meaning empty" id="endMeaning"></div>
      <div class="stats">
        <span>المحاولات: <strong id="endAttempts"></strong></span>
        <span>الوقت: <strong id="endTime"></strong></span>
      </div>
      <div class="lb-section">
        <h3>🏆 لوحة المتصدرين اليوم</h3>
        <div class="lb-date" id="endLbDate"></div>
        <div class="lb-list" id="endLbList"></div>
      </div>
      <div class="replay-note">
        ⏰ لغز جديد كل يوم في الساعة 12:00 منتصف الليل (توقيت السعودية)
      </div>
      <button class="modal-btn secondary" id="closeEndBtn">إغلاق</button>
    </div>
  </div>

  <div class="modal-overlay" id="statsModal">
    <div class="modal">
      <h2>📊 إحصائياتك</h2>
      <div class="stats-container">
        <div class="stat-box"><span class="stat-num" id="statPlayed">0</span><span class="stat-label">لُعبت</span></div>
        <div class="stat-box"><span class="stat-num" id="statWinPct">0</span><span class="stat-label">نسبة الفوز %</span></div>
        <div class="stat-box"><span class="stat-num" id="statStreak">0</span><span class="stat-label">السلسلة الحالية</span></div>
        <div class="stat-box"><span class="stat-num" id="statMaxStreak">0</span><span class="stat-label">أطول سلسلة</span></div>
      </div>
      <div class="lb-section">
        <h3>توزيع المحاولات</h3>
        <div class="dist-container" id="distContainer"></div>
      </div>
      <button class="modal-btn secondary" id="closeStatsBtn">إغلاق</button>
    </div>
  </div>

  <div class="modal-overlay" id="lbModal">
    <div class="modal">
      <h2>🏆 لوحة المتصدرين</h2>
      <p>لغز اليوم</p>
      <div class="lb-date" id="lbDate"></div>
      <div class="lb-list" id="lbList"></div>
      <button class="modal-btn secondary" id="closeLbBtn">إغلاق</button>
    </div>
  </div>

<script>
  // ============================================================
  // SOLUTION WORDS — every word is exactly 5 chars and uses
  // ONLY letters that exist on the keyboard (no أ إ آ ء ئ ؤ ى).
  // ============================================================
  const WORDS = [
    'مدرسة','مكتبة','سيارة','طاولة','نافذة','دراجة','زجاجة','حقيبة','خزانة','نظارة',
    'مصباح','ملعقة','منشار','مسمار','تفاحة','زرافة','مدينة','حديقة','بحيرة','جزيرة',
    'بطاقة','ثلاجة','سفينة','صحيفة','فستان','قاموس','قبيلة','منديل','وسادة','ميدان',
    'مفتاح','بستان','ستارة','سجادة','بنطال','كنيسة','مذكرة','مزرعة','مصيدة','مكتوب',
    'حمامة','عصفور','فراشة','زيتون','وثيقة','وسيلة','مسطرة','هواية','هندسة','حضارة',
    'سحابة','سفارة','مهارة','منطقة','منظمة','نهاية','وزارة','مدارس','دفاتر','جوارب',
    'عربات','عناصر','فنانة','مكاتب','مقاعد','مناطق','متاجر','متاحف','مصانع','نوافذ',
    'طبيبة','مهندس','معلمة','جامعة','رسالة','جريدة','قصيدة','حبيبة','مساعد','مدافع',
    'مغامر','مقاتل','عروسة','حكاية','جريمة','عاصمة','ساعات','دقيقة','ثانية','ثلاثة',
    'مليون','مليار','يومية','جميلة','بسيطة','خفيفة','جديدة','قصيرة','طويلة','صغيرة',
    'كبيرة','لطيفة','قديمة','بعيدة','قريبة','سريعة','نظيفة','صحيحة','فقيرة','مرتاح',
    'رمادي','مثالي','متعدد','متنوع','متوسط','مثيرة','محمول','مرفوع','مزدحم','مستمر',
    'معروف','معلوم','مفقود','مكسور','موجود','موضوع','منشور','دجاجة','بطيخة','ثعبان',
    'طماطم','بطاطس','فاكهة','عربية','سعادة','عدالة','عبارة','عمارة','عملية','مشاعر',
    'مشاكل','مشروع','مشترك','نتيجة','نظافة','صداقة','فقاعة','قاعدة','كتابة','شريحة',
    'خياطة','رياضة','شجرات','ملابس','مرايا','نشرات','مبارك','نافعة','تاريخ','ثقافة',
    'طبيعة','وظيفة','قانون','تجربة','تعليم','تصميم','تطبيق','حاسوب','حقيقة','سياسة',
    'حكومة','مرحلة','مساحة','مسافة','حماية','ضرورة','سلامة','صعوبة','صناعة','شجاعة',
    'شهادة','شهيرة','عقوبة','علاقة','علامة','عاصفة','غابات','غريبة','فضيحة','قافلة',
    'قاهرة','كرامة','لياقة','مباشر','مبسوط','متابع','متعلم','مجموع','محبوب','محسوب',
    'مدفوع','ممتاز','ممنوع','مشهور','مصنوع','معدات','معركة','مفهوم','مكتوم','منزلي',
    'موافق','نادرة','ناشطة','ناعمة','هواتف','هندية','واسعة','واضحة','وحيدة','وردية',
    'وطنية','حركات','حساسة','حلوية','ساحرة','ساخنة','سادسة','سعودي','شركات','شعبية',
    'شفافة','شمالي','صادقة','صاروخ','صالحة','ضعيفة','حادثة','هاتفة','عاكفة','عالمي',
    'عاملة','عظيمة','غاضبة','غامضة','فاسدة','فاشلة','فعالة','قاسية','قبيحة','قطنية',
    // ===== USER-REQUESTED =====
    'غالية',
    // ===== Family / people / relations =====
    'سعيدة','حزينة','حنونة','شفيقة','بخيلة','عاشقة','مغرمة','شغوفة','عاقلة','حكيمة',
    'شريفة','نبيلة','عريقة','شريرة','عطوفة','ودودة','رفيقة','زميلة','صاحبة','جارتي',
    'حبيبي','زوجها','زوجته','زوجتي','بنتها','صديقي','صديقة','زميلي','صاحبي','حبيبه',
    'ابنته','ابنها','ابنتي','جدتها','عمتها','خالتي','شاكرة','كاملة','ناقصة','مرضية',
    // ===== Verbs (we did) =====
    'ضربنا','وقفنا','جرينا','حملنا','خرجنا','دخلنا','صعدنا','نزلنا','ركبنا','وضعنا',
    'رسمنا','طبخنا','غنينا','بكينا','ضحكنا','صلينا','حفظنا','فهمنا','تركنا','وصلنا',
    'نشرنا','زرعنا','بحثنا','وجدنا','عرفنا','نسينا','نظفنا','رتبنا','شكرنا','فرحنا',
    'لبسنا','رفعنا','دفعنا','سحبنا','منعنا','سمحنا','جمعنا','بلغنا','وصفنا','حضرنا',
    // ===== Verbs (they did - masc plural) =====
    'كتبوا','شربوا','لعبوا','ذهبوا','سمعوا','جلسوا','نظروا','درسوا','ضربوا','وقفوا',
    'خرجوا','دخلوا','صعدوا','نزلوا','ركبوا','وضعوا','رسموا','طبخوا','ضحكوا','حفظوا',
    'فهموا','لبسوا','شكروا','جمعوا','منعوا','سمحوا','نشروا','عرفوا','وجدوا','تركوا',
    'زرعوا','بحثوا','رفعوا','دفعوا','سحبوا','رحلوا','وصلوا','حملوا','بلغوا','وصفوا',
    // ===== Verbs (they - fem plural present) =====
    'يكتبن','يدرسن','يلعبن','يشربن','يفهمن','يجلسن','يسمعن','ينظرن','يطبخن','يرسمن',
    'يخرجن','يدخلن','يصعدن','ينزلن','يركبن','يلبسن','يحملن','يضربن','يفعلن','يقولن',
    'يبكين','يضحكن','يفرحن','يحفظن','يعرفن','تكتبن','تدرسن','تلعبن','تشربن','تجلسن',
    // ===== Cities, countries, nationalities =====
    'لبنان','عراقي','دمشقي','بغداد','بيروت','طهران','موسكو','طوكيو','باريس','مدريد',
    'برلين','نابلس','مصرية','سورية','يمنية','قطرية','تركية','صينية','قروية','ريفية',
    'مدنية','بحرية','نهرية','حضرية','بيتية','عماني','يابان','جنوبي','شموعة','جدارة',
    // ===== Time / nature =====
    'صباحه','يومها','صباحي','حاليا','سابقا','لاحقا','يوميا','شهرية','سنوات','صيفية',
    'شتوية','ربيعي','حرارة','جبلية','سواحل','جوامع','كواكب','صخرية','قارات','سماوي',
    'ظهيرة','صباحا','نهارا','رياحه','صلوات','مساجد','مشايخ','مكيدة','عبادة','عاطفة',
    // ===== Daily life / objects =====
    'مطابخ','صالات','محلات','عملات','دولار','دينار','محفظة','مالية','واحدة','ضمانة',
    'حضانة','مجلات','شاشات','شبكات','مواقع',
    'هاتفي','هاتفه','مطعمي','بطاطا','مانجو','مشروب','شطيرة','حليبه','فطيرة','كعكات',
    // ===== Sports / arts / culture =====
    'لاعبة','مدربة','منتخب','خاسرة','تصويت','محطات','طيران','مسافر','رياضي','لوحات',
    'رسامة','مغنية','شاعرة','مسرحي','سينما','رواية','خيالي','ملحمة','نغمات','جيتار',
    // ===== Education =====
    'دراسة','محاضر','فصلية','نحوية','صرفية','بلاغة','نقدية','شعرية','نثرية','لغوية',
    'خاتمة','منطقي','فلسفة','توابع','طالبة','مقولة','علوما','مكتشف','حكمته','دروسه',
    // ===== Body parts / possessives =====
    'عضلات','دماغه','جسدها','صدرها','بطنها','كتفها','ظهرها','رقبتي','عينها','شعرها',
    'لسانه','وجهها','يديها','قدمها','قدماه','شفتيه','حواسه','عقلها','قلبها','روحها',
    // ===== Adjectives & states =====
    'متينة','رقيقة','غليظة','ثقيلة','كسولة','مريضة','سليمة','مظلمة','مشرقة','مالحة',
    'مرجوة','مزيلة','مكوية','مزينة','كثيرة','قليلة','فرحان','تعبان','شبعان','جوعان',
    'نعسان','يقظان','ندمان','سكران','جالبة','طازجة','جذابة','حيوية','مثقفة','متخصص',
    'مبدعة',
    // remove the رائعة line, replace with safe word:
    'مفتوح','مطلوب','مظنون','معدلة','مفعمة','مقابل','منهاج','منهجي','مسلسل','محسوس',
    // ===== Verbs (commands fem) =====
    'اكتبي','العبي','اشربي','اذهبي','اجلسي','اسمعي','ادرسي','انتظر','اكتشف','استمر',
    // ===== Misc =====
    'فكرته','فكرتي','نوعها','هدفها','وقتها','وعدها','مبلغه','جلسته','رغبات','رواتب',
    'صفقات','صبيان','شواهد','ضواحي','طلابي','ظنوني','عظمتك','عناية','فحولة','فكاهة',
    'قاتله','كاتبه','كاتبي','كرتون','لاحقة','لمسات','مجزرة','مجالا','مجدول','مدخول',
    'مذيعة','مدفون','مرفوض','محبوس','محترف','محذور',
    // safe additions:
    'محسود','محظوظ','مكنون','مزروع','مزهرة','مسامح','مكتسب','منتظم','نازحة','نسرين',
    // ===== More =====
    'ابتسم','ابتدع',
    // safe replacements:
    'مكشوف','محجوب','مرسوم',
    // safe:
    'مفتول','مهضوم','منزوع','محشور','مسحور','معروض','مكدود','ملعوب','منكوب','موسوم'
  ];

  // ============================================================
  // EXTRA accepted guesses (not used as answers, but valid to type)
  // ============================================================
  const EXTRA_GUESSES = [
    'حسابي','حسابه','حياته','حياتي','حماقة','جلسات','جنازة','جواهر','حافلة','حاملة',
    'حالات','حسابك','حشرات','حصانة','حلقات','حكمات','حياتك','خادمة','خبيرة','خدمات',
    'خرافة','خسارة','خصومة','خطورة','خطيبة','خلافة','خليفة','خميرة','خنزير','داخلي',
    'درجات','دكتور','دلالة','ديانة','ديكور','ذاكرة','ذراعك','رحبات','رابعة','راحلة',
    'راديو','ربيعة','رحلات','رخامي','رمزية','روحية','روسية','زمالة','زهرات','زيارة',
    'سلامة','سياحة','صابون','صافية','صامتة','صحفية','صفحات','صياغة','صيانة','ضحكات',
    'ضيافة','طاقات','طاهرة','طلبات','ظاهرة','ظلامي','عاجزة','عادية','عتبات','عجوزة',
    'عرسان','عريضة','عطشان','علاقة','عمرها','عميقة','غريبة','غسالة','فاخرة','فترات',
    'فخامة','فرعون','فرقها','فرنسي','فلاحة','فنادق','فهارس','فيروس','قادرة','قاسية',
    'قبضات','قتلوا','قدراه','قراره','قرنفل','كاتبة','كاذبة','كافية','كاميل','كرامة',
    'كريمة','كسلان','لباقة','لحظات','لذيذة','مادية','مباشر','مبتسم','مبكرة','متاعب',
    'متبدل','متفهم','متكلم','مجالس','مجاني','مجاهد','مجمدة','محترم','محذور','محرقة',
    'محسنة','محظوظ','محكوم','مخدرة','مخلصة','مخمور','مدرسي','مدفون','مديرة','مذكور',
    'مذهلة','مراحل','مراسل','مراكز','مربعة','مرتبة','مرحبا','مرحلة','مرشحة','مزخرف',
    'مزدوج','مساحة','مسبوق','مستحق','مسحوق','مسروق','مسطحة','مسلمة','مسموح','مصابة',
    'مصارع','معاصر','معبدة','معركة','معطلة','معقدة','معلقة','مفترش','مفتول','مفعمة',
    'مقالة','مقتول','مقدسة','مقدمة','مكاسب','مكتظة','مكشوف','ملاكم','ملاهي','ملعون',
    'مليار','مليون','ممثلة','ممرضة','مناخه','منازل','منافذ','مناهج','منتصر','منتصف',
    'منتظر','منحرف','مهجور','موافق','موهبة','نازلة','ناصعة','ناطقة','نباتي','نسيان',
    'نسرين','نشيطة','نظرات','نوعية','هاشمي','هاوية','هزيمة','هلامي','واقعي','وحيدة',
    'وداعا','وديعة','وراثة','وردية','يمامة','يمينا','ينادي','يهودي','يونان','حقولي'
  ];

  // ============================================================
  // MEANINGS (for ~100 of the most common solution words)
  // ============================================================
  const WORD_MEANINGS = {
    'مدرسة': 'مكان يتلقى فيه الطلاب العلم والتعليم',
    'مكتبة': 'مكان لجمع وحفظ الكتب والمراجع',
    'سيارة': 'مركبة آلية تسير على الطرق',
    'طاولة': 'قطعة أثاث ذات سطح مستوٍ توضع عليها الأشياء',
    'نافذة': 'فتحة في الجدار للضوء والهواء',
    'دراجة': 'مركبة بعجلتين تسير بقوة الدفع',
    'زجاجة': 'وعاء مصنوع من الزجاج للسوائل',
    'حقيبة': 'وعاء يحمل فيه الإنسان أغراضه',
    'خزانة': 'دولاب لحفظ الملابس أو الأدوات',
    'نظارة': 'أداة تُلبس على العين لتحسين الرؤية',
    'مصباح': 'أداة تنير المكان',
    'ملعقة': 'أداة لتناول الطعام السائل',
    'منشار': 'أداة لقطع الخشب أو المعدن',
    'مسمار': 'قطعة معدنية مدببة لتثبيت الأشياء',
    'تفاحة': 'ثمرة شجرة التفاح',
    'زرافة': 'حيوان طويل العنق يعيش في إفريقيا',
    'مدينة': 'تجمع سكاني كبير',
    'حديقة': 'مساحة مزروعة بالنباتات والأزهار',
    'بحيرة': 'مسطح مائي محاط باليابسة',
    'جزيرة': 'قطعة أرض تحيط بها المياه',
    'بطاقة': 'قطعة ورق أو بلاستيك للتعريف أو التهنئة',
    'ثلاجة': 'جهاز لحفظ الطعام بارداً',
    'سفينة': 'مركبة كبيرة تسير في البحار',
    'صحيفة': 'مطبوعة دورية تحوي الأخبار',
    'فستان': 'ثوب نسائي يُلبس فوق الجسم',
    'قاموس': 'كتاب يضم مفردات اللغة ومعانيها',
    'قبيلة': 'مجموعة من الناس تربطهم قرابة الدم',
    'منديل': 'قطعة قماش أو ورق للمسح',
    'وسادة': 'قطعة طرية يُسند عليها الرأس',
    'ميدان': 'ساحة واسعة في المدينة',
    'مفتاح': 'أداة لفتح الأقفال',
    'بستان': 'حديقة كبيرة فيها أشجار مثمرة',
    'ستارة': 'قماش يغطي النافذة',
    'سجادة': 'قطعة قماش سميكة تُفرش على الأرض',
    'بنطال': 'سروال طويل يُلبس في الجزء السفلي',
    'كنيسة': 'دار العبادة عند المسيحيين',
    'مذكرة': 'دفتر صغير لتسجيل الملاحظات',
    'مزرعة': 'أرض تُزرع وتُربى فيها الحيوانات',
    'مكتوب': 'ما تم تدوينه على الورق',
    'حمامة': 'طائر معروف بسلميته',
    'عصفور': 'طائر صغير يغرد',
    'فراشة': 'حشرة جميلة الأجنحة',
    'زيتون': 'ثمرة شجرة الزيتون',
    'وثيقة': 'مستند مكتوب رسمي',
    'وسيلة': 'الطريقة المستخدمة لتحقيق هدف',
    'مسطرة': 'أداة لرسم الخطوط المستقيمة وقياسها',
    'هواية': 'نشاط يمارسه الإنسان للترفيه',
    'هندسة': 'علم تصميم وبناء المنشآت والآلات',
    'حضارة': 'مرحلة متقدمة من الرقي الثقافي',
    'سحابة': 'كتلة من بخار الماء في السماء',
    'سفارة': 'مقر تمثيل دولة في دولة أخرى',
    'مهارة': 'إتقان عمل أو فن',
    'منطقة': 'جزء محدد من الأرض',
    'منظمة': 'هيئة لها أهداف ومسؤوليات',
    'نهاية': 'آخر الشيء وختامه',
    'وزارة': 'إدارة حكومية يرأسها وزير',
    'طبيبة': 'امرأة تعالج المرضى',
    'مهندس': 'متخصص في الهندسة والتصميم',
    'معلمة': 'امرأة تُدرِّس الطلاب',
    'جامعة': 'مؤسسة للتعليم العالي',
    'رسالة': 'نص مكتوب يُرسل للتواصل',
    'جريدة': 'صحيفة يومية تنشر الأخبار',
    'قصيدة': 'قطعة من الشعر',
    'حبيبة': 'المرأة التي يُحبها الإنسان',
    'مساعد': 'من يقدم العون لشخص آخر',
    'عاصمة': 'المدينة الرئيسية في الدولة',
    'دقيقة': 'وحدة زمنية تساوي 60 ثانية',
    'ثانية': 'أصغر وحدة زمنية شائعة',
    'ثلاثة': 'العدد بين الاثنين والأربعة',
    'مليون': 'ألف ألف، عدد كبير جداً',
    'تاريخ': 'علم دراسة الأحداث الماضية',
    'ثقافة': 'حصيلة المعرفة والفنون لمجتمع',
    'طبيعة': 'العالم المادي وما فيه من ظواهر',
    'وظيفة': 'عمل يتقاضى عليه الإنسان أجراً',
    'قانون': 'قواعد تنظم المجتمع',
    'تجربة': 'محاولة أو اختبار',
    'تعليم': 'نقل المعرفة من شخص لآخر',
    'تصميم': 'التخطيط لشكل أو فكرة',
    'تطبيق': 'تنفيذ شيء على أرض الواقع',
    'حاسوب': 'جهاز إلكتروني لمعالجة البيانات',
    'حقيقة': 'الواقع والصدق',
    'سياسة': 'فن إدارة شؤون الدولة',
    'حكومة': 'الجهة التي تحكم البلاد',
    'مرحلة': 'فترة محددة من الزمن',
    'حماية': 'الدفاع والوقاية من الأذى',
    'صناعة': 'إنتاج السلع من المواد الخام',
    'شجاعة': 'الإقدام والجرأة',
    'شهادة': 'إخبار بحقيقة شيء',
    'علاقة': 'الرابط بين شيئين أو شخصين',
    'كرامة': 'العزة والاحترام للنفس',
    'مشروع': 'خطة أو عمل منظم لهدف معين',
    'نتيجة': 'ما يترتب على شيء',
    'صداقة': 'علاقة المودة بين الأصدقاء',
    'كتابة': 'تدوين الكلمات بالحروف',
    'رياضة': 'نشاط بدني للصحة والترفيه',
    'ملابس': 'الثياب التي يُلبسها الإنسان',
    'فاكهة': 'ثمار الأشجار التي تُؤكل',
    'سعادة': 'شعور بالرضا والبهجة',
    'عدالة': 'إعطاء كل ذي حق حقه'
  };

  const VALID_GUESSES = new Set([...WORDS, ...EXTRA_GUESSES]);

  const KEYBOARD_LAYOUT = [
    ['ض','ص','ث','ق','ف','غ','ع','ه','خ','ح','ج'],
    ['ش','س','ي','ب','ل','ا','ت','ن','م','ك','ة'],
    ['ENTER','ء','ظ','ط','ذ','د','ز','ر','و','ى','BACK']
  ];

  const WORD_LENGTH = 5;
  const MAX_GUESSES = 6;
  const LB_KEY = 'arabicWordle_leaderboard_v1';
  const NAME_KEY = 'arabicWordle_playerName';
  const STATE_KEY = 'arabicWordle_gameState';
  const STATS_KEY = 'arabicWordle_personalStats';

  // ===== Saudi-time helpers =====
  function getSaudiDateString() {
    const fmt = new Intl.DateTimeFormat('en-CA', {
      timeZone: 'Asia/Riyadh', year: 'numeric', month: '2-digit', day: '2-digit'
    });
    return fmt.format(new Date());
  }
  function getDailyWordIndex() {
    const dateStr = getSaudiDateString();
    const epoch = Date.UTC(2024, 0, 1);
    const today = Date.UTC(
      parseInt(dateStr.slice(0, 4), 10),
      parseInt(dateStr.slice(5, 7), 10) - 1,
      parseInt(dateStr.slice(8, 10), 10)
    );
    const days = Math.floor((today - epoch) / 86400000);
    return ((days % WORDS.length) + WORDS.length) % WORDS.length;
  }
  function getDailyWord() { return WORDS[getDailyWordIndex()]; }

  // ===== localStorage helpers =====
  function safeGet(key, fallback) {
    try { const r = localStorage.getItem(key); return r ? JSON.parse(r) : fallback; }
    catch { return fallback; }
  }
  function safeSet(key, val) { try { localStorage.setItem(key, JSON.stringify(val)); } catch {} }

  function loadLeaderboard() { const a = safeGet(LB_KEY, []); return Array.isArray(a) ? a : []; }
  function saveLeaderboard(arr) { safeSet(LB_KEY, arr); }
  function loadName() { try { return (localStorage.getItem(NAME_KEY) || '').trim(); } catch { return ''; } }
  function saveName(n) { try { localStorage.setItem(NAME_KEY, n); } catch {} }

  function loadStats() {
    const def = { played: 0, won: 0, currentStreak: 0, maxStreak: 0, distribution: [0,0,0,0,0,0], lastWonDate: '' };
    const s = safeGet(STATS_KEY, def);
    return { ...def, ...s };
  }
  function saveStats(s) { safeSet(STATS_KEY, s); }

  function loadGameState() { return safeGet(STATE_KEY, null); }
  function saveGameState(s) { safeSet(STATE_KEY, s); }

  // ===== Leaderboard sorting =====
  function compareEntries(a, b) {
    if (a.won !== b.won) return a.won ? -1 : 1;
    if (a.won) {
      if (a.attempts !== b.attempts) return a.attempts - b.attempts;
      return a.timeMs - b.timeMs;
    }
    return a.timeMs - b.timeMs;
  }
  function addToLeaderboard(entry) {
    const all = loadLeaderboard();
    const idx = all.findIndex(e => e.date === entry.date && e.name === entry.name);
    if (idx >= 0) { if (compareEntries(entry, all[idx]) < 0) all[idx] = entry; }
    else { all.push(entry); }
    saveLeaderboard(all);
  }
  function getDailyEntries(date) { return loadLeaderboard().filter(e => e.date === date).sort(compareEntries); }

  // ===== Letter helpers =====
  function splitArabic(word) { return Array.from(word); }
  function normalizeChar(ch) {
    if (ch === 'أ' || ch === 'إ' || ch === 'آ') return 'ا';
    if (ch === 'ى') return 'ي';
    return ch;
  }
  function isArabicLetter(ch) {
    if (!ch || ch.length !== 1) return false;
    const code = ch.charCodeAt(0);
    return (code >= 0x0621 && code <= 0x064A) || ch === 'ة' || ch === 'ى';
  }
  function isOnKeyboard(ch) { for (const row of KEYBOARD_LAYOUT) if (row.includes(ch)) return true; return false; }
  function formatTime(ms) {
    const totalSec = Math.max(0, Math.floor(ms / 1000));
    const m = Math.floor(totalSec / 60); const s = totalSec % 60;
    return `${m}:${s.toString().padStart(2, '0')}`;
  }

  // ===== Game state =====
  let playerName = '';
  let targetWord = '';
  let targetLetters = [];
  let currentGuess = [];
  let boardState = [];
  let currentRow = 0;
  let gameOver = false;
  let gameWon = false;
  let isAnimating = false;
  let keyStates = {};
  let startTime = 0;
  let endTimeFinal = 0;
  let puzzleDate = '';
  let timerInterval = null;

  function buildBoard() {
    const board = document.getElementById('board');
    board.innerHTML = '';
    for (let r = 0; r < MAX_GUESSES; r++) {
      const row = document.createElement('div');
      row.className = 'row'; row.id = `row-${r}`;
      for (let c = 0; c < WORD_LENGTH; c++) {
        const tile = document.createElement('div');
        tile.className = 'tile'; tile.id = `tile-${r}-${c}`;
        row.appendChild(tile);
      }
      board.appendChild(row);
    }
  }

  function buildKeyboard() {
    const keyboard = document.getElementById('keyboard');
    keyboard.innerHTML = '';
    KEYBOARD_LAYOUT.forEach(rowKeys => {
      const row = document.createElement('div');
      row.className = 'keyboard-row';
      rowKeys.forEach(key => {
        const btn = document.createElement('button');
        btn.className = 'key'; btn.type = 'button';
        if (key === 'ENTER') { btn.textContent = 'إدخال'; btn.classList.add('wide'); btn.dataset.key = 'ENTER'; }
        else if (key === 'BACK') { btn.textContent = 'حذف'; btn.classList.add('wide'); btn.dataset.key = 'BACK'; }
        else { btn.textContent = key; btn.dataset.key = key; btn.id = `key-${key}`; }
        btn.addEventListener('click', (e) => { e.preventDefault(); handleKey(btn.dataset.key); btn.blur(); });
        row.appendChild(btn);
      });
      keyboard.appendChild(row);
    });
  }

  function handleKey(key) {
    if (gameOver || isAnimating) return;
    if (key === 'ENTER') submitGuess();
    else if (key === 'BACK') { if (currentGuess.length > 0) { currentGuess.pop(); updateRow(); } }
    else if (isArabicLetter(key) && isOnKeyboard(key)) {
      // Normalize ى → ي (keys are visually shown as iPhone but stored as base form)
      const ch = normalizeChar(key);
      if (currentGuess.length < WORD_LENGTH) { currentGuess.push(ch); updateRow(); }
    }
  }

  function updateRow() {
    for (let c = 0; c < WORD_LENGTH; c++) {
      const tile = document.getElementById(`tile-${currentRow}-${c}`);
      const letter = currentGuess[c];
      if (letter) { if (tile.textContent !== letter) { tile.textContent = letter; tile.classList.add('filled'); } }
      else { tile.textContent = ''; tile.classList.remove('filled'); }
    }
  }

  function showToast(message, duration = 1400) {
    const container = document.getElementById('toastContainer');
    const toast = document.createElement('div');
    toast.className = 'toast'; toast.textContent = message;
    container.appendChild(toast);
    setTimeout(() => { toast.classList.add('fade'); setTimeout(() => toast.remove(), 450); }, duration);
  }

  function shakeRow() {
    const row = document.getElementById(`row-${currentRow}`);
    row.classList.remove('shake'); void row.offsetWidth; row.classList.add('shake');
    setTimeout(() => row.classList.remove('shake'), 500);
  }

  function evaluateGuess(guessArr, target) {
    const result = new Array(WORD_LENGTH).fill('absent');
    const counts = {};
    for (let i = 0; i < WORD_LENGTH; i++) {
      if (guessArr[i] === target[i]) result[i] = 'correct';
      else counts[target[i]] = (counts[target[i]] || 0) + 1;
    }
    for (let i = 0; i < WORD_LENGTH; i++) {
      if (result[i] === 'correct') continue;
      const ch = guessArr[i];
      if (counts[ch] > 0) { result[i] = 'present'; counts[ch]--; }
    }
    return result;
  }

  function submitGuess() {
    if (currentGuess.length !== WORD_LENGTH) { showToast('يجب إدخال 5 أحرف'); shakeRow(); return; }
    const guessStr = currentGuess.join('');
    if (!VALID_GUESSES.has(guessStr)) { showToast('كلمة غير موجودة في القاموس'); shakeRow(); return; }

    isAnimating = true;
    const guessArr = currentGuess.slice();
    const result = evaluateGuess(guessArr, targetLetters);

    for (let c = 0; c < WORD_LENGTH; c++) {
      const tile = document.getElementById(`tile-${currentRow}-${c}`);
      setTimeout(() => {
        tile.classList.add('flip');
        setTimeout(() => { tile.classList.add(result[c]); }, 300);
      }, c * 220);
    }

    const totalAnimTime = WORD_LENGTH * 220 + 350;

    setTimeout(() => {
      for (let c = 0; c < WORD_LENGTH; c++) {
        const ch = guessArr[c]; const newState = result[c]; const cur = keyStates[ch];
        if (cur === 'correct') continue;
        if (cur === 'present' && newState === 'absent') continue;
        keyStates[ch] = newState;
        const keyEl = document.getElementById(`key-${ch}`);
        if (keyEl) { keyEl.classList.remove('correct','present','absent'); keyEl.classList.add(newState); }
      }
    }, totalAnimTime);

    const isWin = result.every(r => r === 'correct');
    const attemptsUsed = currentRow + 1;
    boardState.push(guessStr);

    setTimeout(() => {
      if (isWin) {
        gameOver = true; gameWon = true;
        endTimeFinal = Date.now();
        document.getElementById(`row-${currentRow}`).classList.add('win');
        recordResult(true, attemptsUsed);
        persistCurrentState();
        setTimeout(() => { isAnimating = false; showEndModal(true); }, 950);
      } else if (currentRow === MAX_GUESSES - 1) {
        gameOver = true; gameWon = false;
        endTimeFinal = Date.now();
        recordResult(false, MAX_GUESSES);
        persistCurrentState();
        isAnimating = false;
        setTimeout(() => showEndModal(false), 450);
      } else {
        currentRow++; currentGuess = []; isAnimating = false;
        persistCurrentState();
      }
    }, totalAnimTime + 50);
  }

  function persistCurrentState() {
    saveGameState({
      date: puzzleDate,
      guesses: boardState,
      gameOver: gameOver,
      gameWon: gameWon,
      startTime: startTime,
      endTime: gameOver ? endTimeFinal : null,
      keyStates: keyStates
    });
  }

  function recordResult(won, attempts) {
    const totalTime = Date.now() - startTime;
    addToLeaderboard({ name: playerName, won, attempts, timeMs: totalTime, date: puzzleDate });
    const stats = loadStats();
    if (stats.lastWonDate === puzzleDate || stats.lastLossDate === puzzleDate) {
      // already counted (shouldn't happen, but guard)
      return;
    }
    stats.played++;
    if (won) {
      stats.won++;
      stats.currentStreak++;
      if (stats.currentStreak > stats.maxStreak) stats.maxStreak = stats.currentStreak;
      stats.distribution[attempts - 1]++;
      stats.lastWonDate = puzzleDate;
    } else {
      stats.currentStreak = 0;
      stats.lastLossDate = puzzleDate;
    }
    saveStats(stats);
  }

  function attemptsText(n) {
    if (n === 1) return 'محاولة واحدة';
    if (n === 2) return 'محاولتين';
    if (n >= 3 && n <= 10) return `${n} محاولات`;
    return `${n} محاولة`;
  }

  function renderLeaderboardList(containerEl, dateEl) {
    const entries = getDailyEntries(puzzleDate);
    if (dateEl) dateEl.textContent = puzzleDate;
    if (!entries.length) {
      containerEl.innerHTML = '<div class="empty-lb">لا توجد نتائج بعد. كن أول لاعب!</div>';
      return;
    }
    containerEl.innerHTML = '';
    entries.slice(0, 50).forEach((e, i) => {
      const div = document.createElement('div');
      div.className = 'lb-row' + (e.name === playerName ? ' me' : '');
      const rankEmoji = i === 0 ? '🥇' : i === 1 ? '🥈' : i === 2 ? '🥉' : (i + 1);
      const resCls = e.won ? 'res-win' : 'res-loss';
      const resText = e.won ? `${e.attempts}/6` : 'خسارة';
      div.innerHTML = `<div class="lb-rank">${rankEmoji}</div><div class="lb-name"></div><div class="lb-meta"><span class="${resCls}">${resText}</span> · ${formatTime(e.timeMs)}</div>`;
      div.querySelector('.lb-name').textContent = e.name;
      containerEl.appendChild(div);
    });
  }

  // ===== Countdown to next Saudi midnight =====
  function startNextPuzzleTimer() {
    if (timerInterval) clearInterval(timerInterval);
    const tEl = document.getElementById('mainTimer');

    function tick() {
      // Get current time in Riyadh as components
      const fmt = new Intl.DateTimeFormat('en-GB', {
        timeZone: 'Asia/Riyadh', hour12: false,
        hour: '2-digit', minute: '2-digit', second: '2-digit'
      });
      const parts = fmt.formatToParts(new Date());
      const get = (type) => parseInt(parts.find(p => p.type === type).value, 10);
      let h = get('hour'), m = get('minute'), s = get('second');
      // Some browsers report 24 instead of 0
      if (h === 24) h = 0;

      const secsLeft = (24 * 3600) - (h * 3600 + m * 60 + s);
      const hh = Math.floor(secsLeft / 3600);
      const mm = Math.floor((secsLeft % 3600) / 60);
      const ss = secsLeft % 60;
      tEl.textContent = `${hh.toString().padStart(2,'0')}:${mm.toString().padStart(2,'0')}:${ss.toString().padStart(2,'0')}`;

      // If we just rolled over to a new day, reload to start the new puzzle
      const todayStr = getSaudiDateString();
      if (puzzleDate && todayStr !== puzzleDate && !isAnimating) {
        clearInterval(timerInterval);
        location.reload();
      }
    }
    tick();
    timerInterval = setInterval(tick, 1000);
  }

  function showEndModal(won) {
    const modal = document.getElementById('endModal');
    const title = document.getElementById('endTitle');
    const text  = document.getElementById('endText');
    const wordEl = document.getElementById('endWord');
    const meaningEl = document.getElementById('endMeaning');
    const attEl = document.getElementById('endAttempts');
    const timeEl = document.getElementById('endTime');

    const attemptsUsed = boardState.length;
    if (won) {
      title.textContent = '🎉 أحسنت!';
      text.textContent = `لقد فزت في ${attemptsText(attemptsUsed)}`;
      wordEl.textContent = targetWord; wordEl.classList.remove('lose');
      attEl.textContent = `${attemptsUsed}/6`;
    } else {
      title.textContent = '😔 انتهت المحاولات';
      text.textContent = 'الكلمة الصحيحة كانت:';
      wordEl.textContent = targetWord; wordEl.classList.add('lose');
      attEl.textContent = '—';
    }

    const meaning = WORD_MEANINGS[targetWord];
    if (meaning) {
      meaningEl.classList.remove('empty');
      meaningEl.innerHTML = `<span class="label">المعنى</span>${meaning}`;
    } else {
      meaningEl.classList.add('empty');
      meaningEl.textContent = '';
    }

    const finalMs = endTimeFinal && startTime ? (endTimeFinal - startTime) : 0;
    timeEl.textContent = formatTime(finalMs);

    renderLeaderboardList(document.getElementById('endLbList'), document.getElementById('endLbDate'));
    modal.classList.add('show');
  }

  function renderStatsModal() {
    const stats = loadStats();
    document.getElementById('statPlayed').textContent = stats.played;
    const winPct = stats.played > 0 ? Math.round((stats.won / stats.played) * 100) : 0;
    document.getElementById('statWinPct').textContent = winPct;
    document.getElementById('statStreak').textContent = stats.currentStreak;
    document.getElementById('statMaxStreak').textContent = stats.maxStreak;

    const distContainer = document.getElementById('distContainer');
    distContainer.innerHTML = '';
    const maxDist = Math.max(...stats.distribution, 1);
    stats.distribution.forEach((val, idx) => {
      const w = val === 0 ? 7 : Math.max(10, Math.round((val / maxDist) * 100));
      const isCurrent = (gameOver && gameWon && boardState.length === idx + 1);
      const row = document.createElement('div');
      row.className = 'dist-row';
      row.innerHTML = `
        <div class="dist-label">${idx + 1}</div>
        <div class="dist-bar-bg">
          <div class="dist-bar ${isCurrent ? 'highlight' : ''}" style="width: ${w}%">${val}</div>
        </div>
      `;
      distContainer.appendChild(row);
    });
  }

  function showStatsModal() {
    renderStatsModal();
    document.getElementById('statsModal').classList.add('show');
  }

  function restoreGameState(savedState) {
    startTime = savedState.startTime;
    endTimeFinal = savedState.endTime || 0;
    boardState = savedState.guesses || [];
    gameOver = !!savedState.gameOver;
    gameWon = !!savedState.gameWon;

    boardState.forEach((guessStr, idx) => {
      const guessArr = splitArabic(guessStr);
      const result = evaluateGuess(guessArr, targetLetters);
      for (let c = 0; c < WORD_LENGTH; c++) {
        const tile = document.getElementById(`tile-${idx}-${c}`);
        tile.textContent = guessArr[c];
        tile.classList.add('filled', result[c]);
        const ch = guessArr[c];
        const newState = result[c];
        const cur = keyStates[ch];
        if (cur === 'correct') continue;
        if (cur === 'present' && newState === 'absent') continue;
        keyStates[ch] = newState;
        const keyEl = document.getElementById(`key-${ch}`);
        if (keyEl) { keyEl.classList.remove('correct','present','absent'); keyEl.classList.add(newState); }
      }
    });

    currentRow = boardState.length;

    if (gameOver) {
      if (gameWon && currentRow > 0) {
        document.getElementById(`row-${currentRow - 1}`).classList.add('win');
      }
      setTimeout(() => showEndModal(gameWon), 400);
    }
  }

  function startGame() {
    puzzleDate = getSaudiDateString();
    targetWord = getDailyWord();
    targetLetters = splitArabic(targetWord);
    currentGuess = []; boardState = []; currentRow = 0;
    gameOver = false; gameWon = false; isAnimating = false; keyStates = {};
    startTime = Date.now(); endTimeFinal = 0;

    document.getElementById('endModal').classList.remove('show');
    document.getElementById('infoDateStr').innerHTML = `لغز اليوم · <strong>${puzzleDate}</strong>`;
    buildBoard();
    document.querySelectorAll('.key').forEach(k => k.classList.remove('correct', 'present', 'absent'));

    // Restore prior progress for this puzzle date
    const savedState = loadGameState();
    if (savedState && savedState.date === puzzleDate) {
      restoreGameState(savedState);
    } else {
      // wipe stale state from a previous day
      saveGameState(null);
    }
  }

  function updateNamePill() { document.getElementById('namePill').textContent = playerName || '—'; }

  function showNameModal(initial) {
    const modal = document.getElementById('nameModal');
    const input = document.getElementById('nameInput');
    input.value = playerName || '';
    modal.classList.add('show'); setTimeout(() => input.focus(), 100);
    modal.dataset.initial = initial ? '1' : '0';
  }

  function commitName() {
    const input = document.getElementById('nameInput');
    const val = (input.value || '').trim().slice(0, 20);
    if (!val) {
      input.style.borderColor = '#c46a6a';
      setTimeout(() => { input.style.borderColor = ''; }, 600);
      return;
    }
    const wasInitial = document.getElementById('nameModal').dataset.initial === '1';
    playerName = val; saveName(playerName); updateNamePill();
    document.getElementById('nameModal').classList.remove('show');
    if (wasInitial) startGame();
  }

  // ===== Init =====
  startNextPuzzleTimer();
  buildKeyboard();
  playerName = loadName();
  updateNamePill();
  if (playerName) {
    document.getElementById('nameModal').classList.remove('show');
    startGame();
  } else {
    showNameModal(true);
  }

  // ===== Event listeners =====
  document.getElementById('startBtn').addEventListener('click', commitName);
  document.getElementById('nameInput').addEventListener('keydown', (e) => {
    if (e.key === 'Enter') { e.preventDefault(); commitName(); }
  });
  document.getElementById('namePill').addEventListener('click', () => showNameModal(false));

  document.getElementById('lbBtn').addEventListener('click', () => {
    renderLeaderboardList(document.getElementById('lbList'), document.getElementById('lbDate'));
    document.getElementById('lbModal').classList.add('show');
  });
  document.getElementById('closeLbBtn').addEventListener('click', () =>
    document.getElementById('lbModal').classList.remove('show'));

  document.getElementById('statsBtn').addEventListener('click', showStatsModal);
  document.getElementById('closeStatsBtn').addEventListener('click', () =>
    document.getElementById('statsModal').classList.remove('show'));
  document.getElementById('closeEndBtn').addEventListener('click', () =>
    document.getElementById('endModal').classList.remove('show'));

  document.addEventListener('keydown', (e) => {
    if (e.ctrlKey || e.metaKey || e.altKey) return;
    const anyModal = document.querySelector('.modal-overlay.show');
    if (anyModal) return;
    if (gameOver) return;
    if (e.key === 'Enter') { e.preventDefault(); handleKey('ENTER'); }
    else if (e.key === 'Backspace') { e.preventDefault(); handleKey('BACK'); }
    else if (e.key && e.key.length === 1) {
      const ch = normalizeChar(e.key);
      if (isArabicLetter(ch) && isOnKeyboard(ch)) handleKey(ch);
    }
  });

  document.addEventListener('contextmenu', (e) => {
    if (e.target.classList && e.target.classList.contains('key')) e.preventDefault();
  });
</script>
</body>
</html>
