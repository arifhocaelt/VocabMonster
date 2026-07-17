<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YDT Vocab Monster - PC Web</title>
    <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;800;900&display=swap" rel="stylesheet">
    
    <script src="https://www.gstatic.com/firebasejs/10.8.1/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.8.1/firebase-firestore-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.8.1/firebase-auth-compat.js"></script>

    <style>
        :root {
            --bg-color: #2d3436; --container-bg: #353b48; --primary: #6c5ce7;
            --secondary: #00b894; --accent: #fab1a0; --text-color: #dfe6e9;
            --danger: #ff7675; --correct: #00b894; --wrong: #d63031; --locked: #636e72;
            --p1-c: #6c5ce7; --p2-c: #d63031; --p3-c: #0984e3; --p4-c: #e17055;
            --safe-top: env(safe-area-inset-top, 0px);
            --safe-bottom: env(safe-area-inset-bottom, 0px);
            --top-safe-gap: calc(34px + var(--safe-top));
            --bottom-safe-gap: calc(78px + var(--safe-bottom));
            --game-top-gap: calc(94px + var(--safe-top));
            --battle-action-gap: calc(72px + var(--bottom-safe-gap));
        }
        * { box-sizing: border-box; user-select: none; -webkit-user-select: none; }
        body { margin: 0; padding: 0; font-family: 'Nunito', sans-serif; background-color: var(--bg-color); color: var(--text-color); display: flex; justify-content: center; align-items: center; height: 100vh; height: 100dvh; overflow: hidden; touch-action: none; }
        #app { width: 100%; height: 100%; max-width: 1000px; background: var(--container-bg); padding: 10px 10px calc(10px + var(--bottom-safe-gap)); position: relative; box-shadow: 0 0 50px rgba(0,0,0,0.5); display: flex; flex-direction: column; overflow-y: auto; overflow-x: hidden; }
        #app, #app * { text-transform: none !important; }
        @media (min-width: 768px) { :root { --top-safe-gap: 20px; --bottom-safe-gap: 24px; --game-top-gap: 92px; } #app { height: 95vh; border-radius: 20px; border: 2px solid var(--primary); padding: 20px; } }
        
        /* SABİT ÜST BAR (AVATAR, FS, ANA MENÜ, ARKADAŞLAR, ÇIKIŞ) */
        #top-bar { position: absolute; top: var(--top-safe-gap); left: 10px; right: 10px; display: none; justify-content: space-between; align-items: center; z-index: 100; }
        .top-left-profile { display: flex; align-items: center; gap: 8px; background: rgba(0,0,0,0.3); padding: 5px 12px 5px 5px; border-radius: 30px; cursor: pointer; transition: 0.2s;}
        .top-left-profile:active { transform: scale(0.95); background: rgba(0,0,0,0.5);}
        .profile-avatar-btn { background: rgba(0,0,0,0.6); border: 2px solid var(--primary); border-radius: 50%; width: 40px; height: 40px; display: flex; justify-content: center; align-items: center; font-size: 1.4rem; box-shadow: 0 2px 5px rgba(0,0,0,0.5);}
        .profile-info-text { display: flex; flex-direction: column; justify-content: center; text-align: left; }
        .profile-info-text .name { color: white; font-weight: 900; font-size: 1rem; line-height: 1; margin-bottom: 2px;}
        .profile-info-text .level { color: gold; font-weight: 800; font-size: 0.75rem; line-height: 1; text-transform: uppercase;}
        
        .top-right-controls { display: flex; gap: 6px; }
        
        .screen { display: none; flex-direction: column; align-items: center; width: 100%; flex-grow: 1; min-height: 0; animation: fadeIn 0.4s ease-out; margin-top: calc(88px + var(--safe-top)); padding-bottom: calc(40px + var(--bottom-safe-gap)); }
        #screen-home { margin-top: calc(104px + var(--safe-top)); padding-bottom: calc(96px + var(--safe-bottom)); justify-content: flex-start; position: relative; gap: 8px; }
        #screen-login { margin-top: 0; justify-content: center; padding-bottom: 0;} 
        .active { display: flex; }
        h1 { text-align: center; margin: 5px 0 10px 0; font-weight: 800; color: var(--primary); font-size: 1.8rem; letter-spacing: 1px; text-shadow: 2px 2px 0 #000; }
        h2 { color: var(--text-color); margin-bottom: 15px; font-weight: 600;}
        
        .btn { background: var(--primary); color: white; border: none; padding: 12px 15px; border-radius: 12px; font-size: 1.1rem; cursor: pointer; font-family: inherit; font-weight: 800; transition: transform 0.1s; box-shadow: 0 4px 0 #4834d4; width: 100%; touch-action: manipulation; }
        .btn:active { transform: translateY(3px); box-shadow: 0 1px 0 #4834d4; }
        .btn-secondary { background: var(--secondary); box-shadow: 0 4px 0 #008f72; color: #2d3436; }
        .btn-secondary:active { box-shadow: 0 1px 0 #008f72; }
        .btn-danger { background: var(--danger); box-shadow: 0 4px 0 #d63031; }
        .btn-danger:active { box-shadow: 0 1px 0 #d63031; }
        .btn-arena { background: #fab1a0; color: #2d3436; box-shadow: 0 4px 0 #e17055; }
        .btn-sm { width: auto; padding: 8px 12px; font-size: 1rem; }
        .btn:disabled { opacity: 0.5; cursor: not-allowed; transform: none; box-shadow: none; background: #555 !important; color: #999 !important; }
        
        .nav-buttons { margin-top: auto; margin-bottom: var(--bottom-safe-gap); display: flex; gap: 10px; width: 100%; justify-content: center; flex-shrink: 0; }

        .ig-floating-btn { position: absolute; bottom: var(--bottom-safe-gap); right: 15px; background: rgba(0,0,0,0.8); border: 2px solid #e1306c; border-radius: 30px; padding: 8px 12px; display: none; align-items: center; gap: 6px; color: white; text-decoration: none; z-index: 120; font-weight: 800; font-size: 0.9rem; transition: transform 0.2s; box-shadow: 0 4px 10px rgba(0,0,0,0.7); }
        .ig-floating-btn:active { transform: scale(0.95); }
        .ig-icon { font-size: 1.2rem; color: #e1306c; }
        .support-floating-btn { position: absolute; bottom: var(--bottom-safe-gap); left: 15px; background: rgba(0,0,0,0.8); border: 2px solid var(--secondary); border-radius: 30px; padding: 8px 12px; display: none; align-items: center; gap: 6px; color: white; z-index: 120; font-weight: 800; font-size: 0.9rem; transition: transform 0.2s; box-shadow: 0 4px 10px rgba(0,0,0,0.7); cursor:pointer; }
        .support-floating-btn:active { transform: scale(0.95); }
        .screen-back-btn { position: absolute; top: calc(var(--top-safe-gap) + 56px); left: 12px; width: 42px; height: 42px; border-radius: 50%; border: 2px solid rgba(255,255,255,0.25); background: rgba(0,0,0,0.72); color: white; display: none; align-items: center; justify-content: center; z-index: 130; font-size: 1.4rem; font-weight: 900; box-shadow: 0 4px 12px rgba(0,0,0,0.45); cursor: pointer; }
        .screen-back-btn:active { transform: scale(0.94); }

        #intro-overlay { position: fixed; inset: 0; z-index: 20000; display: flex; align-items: center; justify-content: center; background: radial-gradient(circle at center, #1d2140 0%, #070812 72%); overflow: hidden; transition: opacity 0.55s ease, visibility 0.55s ease; }
        #intro-overlay.hide { opacity: 0; visibility: hidden; pointer-events: none; }
        .intro-stage { width: min(88vw, 520px); display: flex; flex-direction: column; align-items: center; gap: 10px; animation: introPop 2.6s ease both; }
        .intro-logo { width: min(82vw, 430px); aspect-ratio: 1 / 1; object-fit: contain; filter: drop-shadow(0 0 28px rgba(0, 225, 255, 0.55)); animation: introFloat 1.9s ease-in-out infinite; }
        .intro-title { font-size: clamp(2rem, 9vw, 4.8rem); line-height: 0.9; font-weight: 900; text-align: center; color: #18d9ff; text-shadow: 0 4px 0 #005f9f, 0 0 22px rgba(255, 213, 0, 0.65); }
        .intro-subtitle { font-size: clamp(1rem, 4vw, 1.6rem); font-weight: 900; color: #ffd84a; letter-spacing: 0; text-shadow: 0 2px 8px rgba(0,0,0,0.8); }
        .intro-spark { position: absolute; width: 12px; height: 12px; border-radius: 50%; background: #ffd84a; box-shadow: 0 0 18px #ffd84a; animation: introSpark 2.4s ease-in-out infinite; }
        .intro-spark.s1 { top: 18%; left: 18%; }
        .intro-spark.s2 { top: 23%; right: 20%; animation-delay: 0.35s; background:#18d9ff; box-shadow:0 0 18px #18d9ff; }
        .intro-spark.s3 { bottom: 18%; left: 24%; animation-delay: 0.7s; background:#ff6bd6; box-shadow:0 0 18px #ff6bd6; }
        .intro-spark.s4 { bottom: 24%; right: 18%; animation-delay: 1.05s; }

        .main-menu-grid { display: grid; grid-template-columns: 1fr 1fr; grid-template-rows: auto auto; gap: 12px; width: 100%; max-width: 500px; flex-grow: 0; margin-bottom: calc(18px + var(--bottom-safe-gap)); }
        .menu-sq-btn { display: flex; flex-direction: column; justify-content: center; align-items: center; aspect-ratio: 1 / 1; min-height: 0; border-radius: 18px; border: none; color: white; cursor: pointer; transition: transform 0.1s; box-shadow: 0 6px 15px rgba(0,0,0,0.4); text-transform: uppercase; font-weight: 900; font-size: clamp(0.9rem, 3.7vw, 1.05rem); line-height: 1.15; touch-action: manipulation; padding: 10px;}
        .menu-sq-btn:active { transform: scale(0.95); }
        .btn-fc { background: linear-gradient(135deg, #0984e3, #74b9ff); }
        .btn-ch { background: linear-gradient(135deg, #6c5ce7, #a29bfe); }
        .btn-tm { background: linear-gradient(135deg, #e17055, #fab1a0); }
        .btn-mb { background: linear-gradient(135deg, #d63031, #ff7675); }
        .menu-sq-btn .icon { font-size: clamp(2.25rem, 8vw, 3.1rem); margin-bottom: 5px; text-shadow: 2px 2px 5px rgba(0,0,0,0.3); animation: float 3s infinite ease-in-out; }
        
        .cat-select-row { display: flex; gap: 10px; width: 100%; max-width: 500px; margin-bottom: 10px; align-items: center;}
        .category-switch { display: flex; gap: 5px; background: #222; padding: 5px; border-radius: 12px; flex: 1; margin: 0; }
        .cat-btn { background: transparent; color: #777; box-shadow: none; margin: 0; flex: 1; border-radius: 8px; font-size: 0.9rem; padding: 10px 5px; font-weight:800; transition: 0.2s;}
        .cat-btn.active-cat { background: var(--accent); color: #2d3436; box-shadow: 0 2px 0 #e17055; }
        select, input { padding: 10px; border-radius: 10px; border: 2px solid #555; background: #2d3436; color: white; font-family: inherit; font-weight:600; font-size: 0.95rem; outline: none; width: 100%; text-align: center;}
        .monster-avatar { font-size: 60px; margin-bottom: 5px; animation: float 3s infinite ease-in-out; }
        
        .card-container { perspective: 1000px; width: 100%; max-width: 500px; height: 280px; cursor: pointer; margin-bottom: 15px; flex-grow: 1; max-height: 400px; }
        .card { width: 100%; height: 100%; position: relative; transform-style: preserve-3d; transition: transform 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275); border-radius: 20px; }
        .card.flipped { transform: rotateY(180deg); }
        .card-face { position: absolute; width: 100%; height: 100%; backface-visibility: hidden; display: flex; flex-direction: column; justify-content: center; align-items: center; border-radius: 20px; padding: 15px; text-align: center; background: #2d3436; border: 3px solid var(--primary); box-shadow: 0 8px 20px rgba(0,0,0,0.3); }
        .card-back { transform: rotateY(180deg); border-color: var(--secondary); background: #2d3436; }
        .word-title { font-size: 2.2rem; color: var(--primary); margin-bottom: 10px; font-weight: 800; }
        .meaning-text { font-size: 1.8rem; color: var(--secondary); margin-bottom: 10px; font-weight: 800;}
        .synonym { color: var(--accent); font-style: italic; margin: 10px 0; font-size: 1.2rem; font-weight:600;}
        
        .question-box { background: #dfe6e9; color: #2d3436; padding: 15px; border-radius: 15px; width: 100%; max-width: 600px; text-align: center; font-size: 1.4rem; font-weight: 800; margin-bottom: 15px; box-shadow: inset 0 0 10px rgba(0,0,0,0.2);}
        .options-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; width: 100%; max-width: 600px; flex-grow: 1; }
        .option-btn { width: 100%; margin: 0; background: #636e72; box-shadow: 0 4px 0 #222; min-height: 60px; font-size: 0.95rem; font-weight:800; white-space: normal; padding: 5px; display: flex; align-items: center; justify-content: center; touch-action: manipulation; border-radius: 10px; border: none; color: white; transition: background 0.2s, opacity 0.2s;}
        .option-btn:active { transform: translateY(4px); box-shadow: 0 0 0 #222; }
        .option-btn.correct { background: var(--correct) !important; box-shadow: 0 4px 0 #008f72; color: #fff; }
        .option-btn.wrong { background: var(--wrong) !important; box-shadow: 0 4px 0 #a02020; color: #fff; }
        
        .player-list { display: flex; flex-wrap: wrap; gap: 5px; justify-content: center; margin-bottom: 10px; width: 100%; max-height: 120px; overflow-y: auto; }
        #screen-local-tour-setup { overflow-y: auto; gap: 6px; }
        #screen-local-tour-setup .player-list { min-height: 58px; max-height: clamp(92px, 22vh, 170px); align-content: flex-start; justify-content: flex-start; padding: 8px; background: rgba(0,0,0,0.24); border: 2px solid rgba(255,255,255,0.08); border-radius: 14px; }
        #screen-local-tour-setup .nav-buttons { margin-top: 8px; }
        .player-tag { background: #555; padding: 5px 10px; border-radius: 15px; font-size: 0.8rem; font-weight:600; animation: popIn 0.3s; display: flex; align-items: center; gap: 5px;}
        #screen-local-tour-setup .player-tag { background: linear-gradient(135deg, rgba(0,184,148,0.95), rgba(9,132,227,0.9)); color: white; border: 1px solid rgba(255,255,255,0.25); box-shadow: 0 3px 8px rgba(0,0,0,0.25); }
        #player-emoji, #battle-names-area select { width: 82px !important; min-width: 82px; font-size: 1.35rem; line-height: 1; padding: 8px 6px; }
        #battle-names-area > div { width: 100%; max-width: 390px; }
        #battle-names-area input { flex: 1; }
        .tournament-bracket-screen { align-items: stretch; overflow: hidden; }
        .bracket-stage { width: 100%; flex: 1 1 auto; min-height: 0; display: flex; gap: 12px; align-items: stretch; }
        .bracket-scroll { width: 100%; min-width: 0; min-height: 0; overflow: auto; padding: 10px 10px 20px; display: flex; justify-content: flex-start; align-items: flex-start; flex: 1 1 auto; background: rgba(0,0,0,0.18); border: 2px solid rgba(255,255,255,0.08); border-radius: 14px; touch-action: pan-x pan-y !important; -webkit-overflow-scrolling: touch; overscroll-behavior: contain; }
        .bracket-tree { display: flex; flex-direction: row; align-items: flex-start; gap: 30px; padding: 10px; min-width: max-content; min-height: max-content; }
        .bracket-round { display: flex; flex-direction: column; justify-content: flex-start; gap: 15px; min-width: 150px; }
        .round-title { text-align: center; color: var(--secondary); font-size: 0.8rem; font-weight:900; margin-bottom: 5px; text-transform: uppercase; letter-spacing: 1px;}
        .match-node { background: #2d3436; border: 2px solid #555; padding: 8px; border-radius: 10px; width: 140px; position: relative; cursor: pointer; transition: 0.2s; text-align: center; font-weight:600; box-shadow: 0 4px 6px rgba(0,0,0,0.3);}
        .match-node.active-match { border-color: var(--accent); background: #353b48; box-shadow: 0 0 10px rgba(250, 177, 160, 0.5);}
        .match-node.finished { border-color: var(--secondary); opacity: 0.8; }
        .match-player { display: flex; justify-content: space-between; align-items: center; font-size: 0.85rem; padding: 2px 0;}
        .match-player.winner { color: var(--correct); font-weight: 900; }
        .score-badge { background: #222; padding: 2px 6px; border-radius: 6px; font-size: 0.7rem; color: #fff; font-weight:900;}
        .tournament-champion-card { display: none; flex: 0 0 220px; flex-direction: column; justify-content: center; align-items: center; gap: 8px; min-height: 180px; padding: 16px; border-radius: 18px; color: white; text-align: center; background: linear-gradient(145deg, rgba(250,177,160,0.98), rgba(108,92,231,0.95)); border: 3px solid rgba(255,216,74,0.85); box-shadow: 0 10px 25px rgba(0,0,0,0.42), inset 0 0 20px rgba(255,255,255,0.12); }
        .champion-crown { font-size: clamp(2.4rem, 7vw, 4.2rem); line-height: 1; filter: drop-shadow(0 4px 8px rgba(0,0,0,0.55)); }
        .champion-label { color: #ffd84a; font-size: 0.95rem; font-weight: 900; letter-spacing: 0; }
        .champion-name { width: 100%; color: white; font-size: clamp(1.25rem, 4vw, 1.8rem); line-height: 1.08; font-weight: 900; overflow-wrap: anywhere; text-shadow: 2px 2px 0 rgba(0,0,0,0.4); }
        .champion-note { color: rgba(255,255,255,0.86); font-size: 0.86rem; font-weight: 800; line-height: 1.25; }

        /* BATTLE ARENA (VS) YEREL VE ONLINE */
        .battle-container { display: flex; flex-direction: column; width: 100%; position: absolute; top: var(--game-top-gap); bottom: var(--battle-action-gap); left:0; background: #222; min-height: 0; }
        .battle-top-bar { height: 70px; background: rgba(0,0,0,0.8); display: flex; justify-content: center; align-items: center; position: relative; z-index: 10; border-bottom: 2px solid #444;}
        .battle-word { background: #ff9f43; color: #222; padding: 8px 30px; border-radius: 30px; font-weight: 900; font-size: 2rem; box-shadow: 0 5px 15px rgba(0,0,0,0.7); z-index: 12; border: 3px solid #fff; text-transform: uppercase; letter-spacing: 1px; text-align:center;}
        .battle-timer { position: absolute; right: 15px; font-size: 1.8rem; color: var(--accent); font-weight: 900; }
        .battle-grid { flex: 1 1 auto; min-height: 0; display: flex; flex-direction: column; }
        .player-zone { flex: 1 1 0; min-height: 0; display: flex; flex-direction: column; justify-content: center; align-items: center; padding: 5px; position: relative; border-bottom: 2px solid rgba(0,0,0,0.4); overflow: hidden; }
        .pz-1 { background-color: var(--p1-c); } .pz-2 { background-color: var(--p2-c); } .pz-3 { background-color: var(--p3-c); } .pz-4 { background-color: var(--p4-c); }
        .player-box { background: rgba(0,0,0,0.6); padding: 5px 15px; border-radius: 10px; border: 2px solid rgba(255,255,255,0.3); display: flex; justify-content: space-between; align-items: center; width: 90%; margin-bottom: 5px; }
        .player-name-text { font-weight: 900; font-size: 1.2rem; color: #fff; text-shadow: 1px 1px 2px black; display: flex; align-items: center; gap: 5px; }
        .p-score { font-size: 2.2rem; font-weight: 900; color: gold; text-shadow: 2px 2px 5px black; }
        .battle-options { display: grid; grid-template-columns: 1fr 1fr; gap: 6px; width: 100%; flex: 1 1 auto; min-height: 0; padding: 5px; }
        .b-opt-btn { background: rgba(255,255,255,0.2); border: 2px solid rgba(255,255,255,0.1); color: white; font-weight: 800; font-size: 1rem; border-radius: 12px; cursor: pointer; display: flex; align-items: center; justify-content: center; text-align: center; min-height: 0; overflow-wrap: anywhere; line-height: 1.1; padding: 4px; }
        .b-opt-btn.selected { border-color: gold; box-shadow: 0 0 10px rgba(255,215,0,0.5); opacity: 0.8;}
        .b-opt-btn.correct { background: var(--correct) !important; color: white; border-color: white; opacity: 1 !important;}
        .b-opt-btn.wrong { background: var(--wrong) !important; opacity: 0.6; }
        #screen-battle-arena > .nav-buttons { bottom: calc(14px + var(--safe-bottom)) !important; left: 0; right: 0; margin: 0; z-index: 260; }
        
        .intro-overlay { position: absolute; inset: 0; background: rgba(0,0,0,0.95); z-index: 200; display: flex; flex-direction: column; justify-content: center; align-items: center; animation: fadeIn 0.3s; }
        .modal-overlay { position: fixed; top: 0; left: 0; width: 100vw; height: 100vh; height: 100dvh; background: rgba(0,0,0,0.85); z-index: 9999; display: none; justify-content: center; align-items: center; padding: calc(14px + var(--safe-top)) 14px calc(14px + var(--safe-bottom)); animation: fadeIn 0.2s; }
        .modal-box { background: var(--container-bg); width: 100%; max-width: 450px; border-radius: 20px; border: 3px solid var(--accent); padding: 18px; display: flex; flex-direction: column; max-height: 85vh; max-height: calc(100dvh - var(--safe-top) - var(--safe-bottom) - 28px); min-height: 0; text-align: center; box-shadow: 0 10px 40px rgba(0,0,0,0.7); overflow: hidden; }
        .modal-title { color: var(--accent); margin-bottom: 15px; font-size: 1.5rem; font-weight: 900;}
        
        .podium-container { display: flex; align-items: flex-end; justify-content: center; gap: 8px; margin: 20px 0 30px 0; width: 100%; height: 200px; pointer-events: auto; flex-shrink: 0;}
        .podium-bar { display: flex; flex-direction: column; align-items: center; justify-content: flex-start; color: white; font-weight: 800; border-radius: 15px 15px 0 0; text-align: center; width: 30%; max-width: 100px; position: relative; padding-top: 5px; box-shadow: 0 -2px 10px rgba(0,0,0,0.5); cursor: pointer; transition: transform 0.2s;}
        .podium-bar:active { transform: scale(0.95); }
        .p-rank-1 { height: 100%; background: linear-gradient(to top, #f1c40f, #f39c12); order: 2; z-index: 2; border: 2px solid #fff; border-bottom: none; box-shadow: 0 0 20px rgba(241,196,15,0.6);}
        .p-rank-2 { height: 75%; background: linear-gradient(to top, #bdc3c7, #95a5a6); order: 1; }
        .p-rank-3 { height: 60%; background: linear-gradient(to top, #cd7f32, #d35400); order: 3; }
        .avatar { font-size: 30px; filter: drop-shadow(2px 4px 6px black); margin-top: -40px; }
        .p-name { font-size: 0.8rem; width: 100%; padding: 3px; white-space: normal; overflow: visible; word-break: break-all; line-height: 1.1; color: #fff; font-weight: 900; text-shadow: 1px 1px 2px #000;}
        .p-score-txt { font-size: 1.1rem; color: gold; margin-top: auto; margin-bottom: 10px; font-weight: 900; text-shadow: 1px 1px 2px #000;}

        .lb-list { overflow-y: auto; flex-grow: 1; min-height: 0; margin-bottom: 15px; text-align: left; background: rgba(0,0,0,0.2); border-radius: 10px; padding: 5px;}
        .lb-row { display: flex; justify-content: space-between; align-items: center; padding: 10px; border-bottom: 1px solid rgba(255,255,255,0.1); font-weight: 800; font-size: 0.95rem; cursor: pointer; transition: background 0.2s;}
        .lb-row:active { background: rgba(255,255,255,0.1); }
        .lb-row:last-child { border-bottom: none; }
        .lb-row.me { background: rgba(255,255,255,0.15); border-radius: 8px; color: gold;}
        .lb-rank { width: 30px; color: #aaa; }
        .lb-score { color: var(--secondary); font-size: 0.95rem; }
        .friend-row { display: flex; justify-content: space-between; align-items: center; padding: 10px; border-bottom: 1px solid rgba(255,255,255,0.1); font-weight: 800; font-size: 1rem;}
        
        .my-rank-box { background: linear-gradient(135deg, var(--primary), var(--secondary)); border-radius: 12px; padding: 12px; margin-top: 10px; text-align: center; border: 2px solid gold; box-shadow: 0 4px 15px rgba(0,0,0,0.6); }
        .my-rank-title { font-size: 0.9rem; color: #fff; margin-bottom: 5px; font-weight: 900; text-transform: uppercase; letter-spacing: 1px; }
        .my-rank-details { display: flex; justify-content: space-between; align-items: center; font-size: 1.2rem; font-weight: 900; color: gold; text-shadow: 1px 1px 2px #000; }

        .avatar-selection { display: grid; grid-template-columns: repeat(4, 1fr); gap: 10px; margin: 15px 0; max-height: 132px; overflow-y: auto; padding: 5px; flex-shrink: 0;}
        .avatar-option { font-size: 2.5rem; cursor: pointer; padding: 5px; border-radius: 15px; background: rgba(0,0,0,0.2); transition: 0.2s; border: 3px solid transparent; text-align:center;}
        .avatar-option.selected { border-color: gold; background: rgba(255, 215, 0, 0.2); transform: scale(1.1); box-shadow: 0 0 10px rgba(255,215,0,0.5);}
        .badges-container { background: rgba(0,0,0,0.3); border-radius: 15px; padding: 12px; margin-bottom: 12px; text-align: left; max-height: min(34vh, 240px); overflow-y: auto; flex-shrink: 1; min-height: 0;}
        .badge-item { display: flex; align-items: center; gap: 10px; font-weight: bold; color: #fff; margin-bottom: 8px; font-size: 1rem; }
        .profile-section-title { color:#aaa; margin: 12px 0 6px; font-size:0.9rem; font-weight:900; text-align:left; width:100%; }
        .badge-tabs { display:flex; gap:6px; background:#222; padding:5px; border-radius:12px; margin-bottom:10px; position: sticky; top: 0; z-index: 2; }
        .badge-tabs .cat-btn { padding:8px 6px; font-size:0.85rem; }
        .badge-grid { display:grid; grid-template-columns: repeat(4, minmax(58px, 1fr)); gap:8px; min-height:58px; max-height: 156px; overflow-y: auto; align-content: start; padding-right: 2px; }
        .achievement-badge { background:rgba(255,255,255,0.08); border:2px solid rgba(255,255,255,0.12); border-radius:12px; min-height:86px; display:flex; flex-direction:column; align-items:center; justify-content:center; transition:transform 0.15s, border-color 0.15s; text-align:center; padding:7px 4px; }
        .achievement-badge.rank-1 { border-color:#f1c40f; box-shadow:0 0 10px rgba(241,196,15,0.25); }
        .achievement-badge.rank-2 { border-color:#bdc3c7; box-shadow:0 0 10px rgba(189,195,199,0.18); }
        .achievement-badge.rank-3 { border-color:#cd7f32; box-shadow:0 0 10px rgba(205,127,50,0.18); }
        .badge-symbol { font-size:2rem; line-height:1; }
        .achievement-badge.rank-2 .general-symbol { filter: grayscale(1) brightness(1.45); }
        .achievement-badge.rank-3 .general-symbol { filter: sepia(1) saturate(1.8) hue-rotate(335deg) brightness(0.9); }
        .badge-caption { font-size:0.67rem; color:#ddd; margin-top:6px; font-weight:900; line-height:1.12; word-break:break-word; }
        .badge-empty { color:#888; font-size:0.85rem; text-align:center; grid-column:1 / -1; padding:12px 4px; }
        .profile-scroll { overflow-y:auto; padding-right:4px; min-height: 0; flex: 1 1 auto; }
        .modal-box > .btn { flex-shrink: 0; }
        #public-profile-modal .monster-avatar { flex-shrink: 0; margin-bottom: 0; }
        #public-profile-modal .modal-title { flex-shrink: 0; margin-bottom: 4px; }
        #public-profile-modal .clap-box { flex-shrink: 0; margin-bottom: 8px; }
        .friend-search-box { background:rgba(0,0,0,0.25); border-radius:12px; padding:10px; margin-bottom:10px; }
        .friend-search-row { display:flex; gap:6px; }
        .friend-search-results { display:flex; flex-direction:column; gap:8px; margin-top:8px; }
        .friend-row { display:flex; justify-content:space-between; align-items:center; gap:8px; padding:9px; background:rgba(255,255,255,0.06); border-radius:10px; font-weight:800; }
        .clap-box { background:rgba(0,0,0,0.28); border-radius:14px; padding:12px; margin-bottom:12px; display:flex; align-items:center; justify-content:space-between; gap:10px; color:white; font-weight:900; }
        .clap-count { color:gold; font-size:1.2rem; }
        .account-action-list { display:flex; flex-direction:column; gap:10px; width:100%; }
        .account-warning { background:rgba(214,48,49,0.18); border:2px solid rgba(255,118,117,0.6); color:white; border-radius:14px; padding:12px; margin:10px 0; font-weight:800; line-height:1.4; text-align:left; }
        .delete-confirm-row { display:flex; align-items:flex-start; gap:10px; color:white; font-weight:800; text-align:left; margin:10px 0 14px; }
        .delete-confirm-row input { width:22px; height:22px; min-width:22px; margin-top:2px; }
        
        .info-icon { background: rgba(255,255,255,0.1); border-radius: 50%; width: 45px; height: 45px; display: flex; justify-content: center; align-items: center; font-size: 1.2rem; cursor: pointer; transition: 0.2s; border: 1px solid rgba(255,255,255,0.2);}
        .info-icon:active { transform: scale(0.9); background: rgba(255,255,255,0.3); }

        .ol-header { display: flex; justify-content: space-between; align-items: center; width: 100%; font-size: 1.2rem; font-weight: bold; margin-bottom: 10px; }
        .ol-lives { color: #ff4757; font-size: 1.5rem; text-shadow: 1px 1px 2px #000; letter-spacing: 2px;}
        .ol-timer-bar { width: 100%; height: 15px; background: #555; border-radius: 10px; overflow: hidden; margin-bottom: 15px; position: relative; box-shadow: inset 0 0 5px rgba(0,0,0,0.5);}
        .ol-timer-fill { height: 100%; background: var(--accent); width: 100%; transition: width 0.1s linear;}
        .ol-timer-text { position: absolute; width: 100%; text-align: center; top: -3px; font-size: 0.9rem; font-weight: 900; color: #222; }

        .room-setup-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-top:15px; text-align:left;}
        .room-setup-item { display: flex; flex-direction: column; }
        .room-setup-item label { font-size:0.8rem; color:#aaa; margin-bottom:3px; }

        .login-box { background: rgba(0,0,0,0.3); padding: 25px; border-radius: 15px; width: 100%; max-width: 400px; text-align: center; border: 2px solid rgba(255,255,255,0.1); }
        .login-box input { text-align: center; font-size: 1.1rem; font-weight: 800; margin-bottom: 10px;}
        .auth-toggle { color: var(--accent); cursor: pointer; font-weight: bold; margin-top: 15px; text-decoration: underline; font-size: 0.9rem;}
        .checkbox-container { display: flex; align-items: center; justify-content: center; gap: 8px; margin-bottom: 10px; color: white; font-weight: bold; font-size: 1rem; cursor: pointer;}
        .checkbox-container input { width: 20px; height: 20px; margin: 0; cursor: pointer;}
        
        .map-wrapper { width: 100%; flex-grow: 1; overflow-y: hidden; overflow-x: auto; display: flex; flex-direction: row; align-items: center; padding: 20px 40px; scroll-behavior: smooth; position: relative; gap: 60px; cursor: grab;}
        .map-wrapper:active { cursor: grabbing; }
        .map-wrapper::-webkit-scrollbar { height: 10px; }
        .map-wrapper::-webkit-scrollbar-track { background: rgba(0,0,0,0.2); border-radius: 10px; }
        .map-wrapper::-webkit-scrollbar-thumb { background: var(--primary); border-radius: 10px; }

        .level-node { display: flex; flex-direction: column; align-items: center; position: relative; flex-shrink: 0; z-index: 5; }
        .level-node:nth-child(odd) { transform: translateY(-40px); }
        .level-node:nth-child(even) { transform: translateY(40px); }
        
        .level-circle { width: 85px; height: 85px; border-radius: 50%; background: var(--primary); border: 4px solid white; display: flex; flex-direction: column; justify-content: center; align-items: center; color: white; font-weight: 900; font-size: 1.2rem; text-align: center; box-shadow: 0 5px 15px rgba(0,0,0,0.5); cursor: pointer; position: relative; z-index: 10; transition: transform 0.2s; }
        .level-circle:active { transform: scale(0.9); }
        .level-circle.locked { background: var(--locked); border-color: #aaa; color: #aaa; cursor: not-allowed; }
        
        .level-stars { position: absolute; top: -22px; display: flex; gap: 2px; }
        .star { font-size: 1.3rem; color: #555; text-shadow: 1px 1px 0 #000; }
        .star.earned { color: gold; text-shadow: 0 0 5px orange; }

        .leaderboard-btn { position: absolute; top: -10px; right: -20px; width: 35px; height: 35px; border-radius: 50%; background: #f1c40f; display: flex; justify-content: center; align-items: center; font-size: 1.1rem; box-shadow: 0 3px 0 #f39c12; cursor: pointer; z-index: 10; transition: transform 0.1s;}
        .leaderboard-btn:active { transform: translateY(3px); box-shadow: 0 1px 0 #f39c12; }
        .path-line { position: absolute; border-top: 5px dashed rgba(255,255,255,0.4); width: 70px; top: 40px; right: -65px; z-index: 1; }
        .level-node:nth-child(odd) .path-line { transform: rotate(45deg); transform-origin: left center;}
        .level-node:nth-child(even) .path-line { transform: rotate(-45deg); transform-origin: left center;}
        .level-node:last-child .path-line { display: none; }

        .tour-lobby-box { background: rgba(0,0,0,0.4); padding: 20px; border-radius: 15px; width: 100%; max-width: 450px; text-align: center; margin-top: 15px; border: 2px solid rgba(255,255,255,0.1); }
        .tour-code-display { font-size: 3rem; color: gold; font-weight: 900; letter-spacing: 5px; margin: 10px 0; text-shadow: 2px 2px 0 #000;}
        .tour-player-count { font-size: 1.2rem; color: var(--accent); font-weight: 800; margin-bottom: 15px;}
        .action-row { display: flex; gap: 10px; justify-content: center; margin-bottom: 20px;}
        .big-countdown { font-size: 6rem; color: var(--accent); font-weight: 900; text-shadow: 3px 3px 0 #000; margin: 20px 0;}
        .draw-slot { display: inline-block; transition: color 0.3s, transform 0.3s; }
        #screen-result { justify-content: flex-start; overflow-y: auto; margin-top: calc(42px + var(--safe-top)); padding-bottom: calc(24px + var(--bottom-safe-gap)); }
        #screen-result .monster-avatar { font-size: 48px; margin-bottom: 0; flex-shrink: 0; }
        #screen-result h2 { margin: 0 0 8px; font-size: 1.45rem; text-align: center; }
        #screen-result .podium-container { height: clamp(145px, 30vh, 210px); margin: 8px 0 14px; max-width: 460px; }
        #screen-result h1 { margin: 4px 0; font-size: 1.6rem; }
        #screen-result p { margin: 6px 0 12px; text-align: center; font-weight: 800; }
        #screen-result.battle-result-screen.active { display: flex; flex-direction: column; justify-content: center; align-items: center; }
        #screen-result.battle-result-screen { overflow: hidden; margin-top: calc(104px + var(--safe-top)); padding: 0 8px 14px; height: calc(100dvh - 128px - var(--safe-top) - var(--bottom-safe-gap)); min-height: 360px; }
        #screen-result.battle-result-screen .monster-avatar,
        #screen-result.battle-result-screen #result-title,
        #screen-result.battle-result-screen #result-score,
        #screen-result.battle-result-screen #result-message { display: none !important; }
        #screen-result.battle-result-screen #tour-podium-area { display: block !important; width: 100%; max-width: 540px; height: auto !important; min-height: 0; margin: 0 auto; flex: 0 1 auto; }
        .battle-celebration-card { width: 100%; min-height: 0; height: auto; max-height: none; display: flex; flex-direction: column; gap: 10px; align-items: stretch; justify-content: flex-start; padding: 13px; border-radius: 20px; background: radial-gradient(circle at 50% 0%, rgba(255,216,74,0.25), transparent 35%), linear-gradient(145deg, rgba(108,92,231,0.96), rgba(9,132,227,0.92) 48%, rgba(214,48,49,0.94)); border: 3px solid rgba(255,255,255,0.22); box-shadow: 0 12px 28px rgba(0,0,0,0.5); overflow: visible; margin: 0 auto; }
        .battle-celebration-kicker { font-size: 0.8rem; letter-spacing: 1px; color: rgba(255,255,255,0.82); font-weight: 900; text-transform: uppercase; }
        .battle-winner-box { width: 100%; display: grid; grid-template-columns: auto 1fr auto; align-items: center; gap: 12px; background: rgba(0,0,0,0.42); border: 3px solid rgba(255,216,74,0.75); border-radius: 20px; padding: 14px 14px; box-shadow: 0 0 20px rgba(255,216,74,0.22), inset 0 0 20px rgba(255,255,255,0.08); }
        .battle-winner-avatar { font-size: clamp(3.2rem, 12vw, 5rem); line-height: 1; filter: drop-shadow(0 5px 9px rgba(0,0,0,0.7)); }
        .battle-winner-copy { min-width: 0; text-align: left; }
        .battle-winner-label { color: #ffd84a; font-weight: 900; font-size: 0.88rem; text-transform: uppercase; }
        .battle-winner-name { color: white; font-size: clamp(1.5rem, 6vw, 2.4rem); font-weight: 900; line-height: 1.05; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; text-shadow: 2px 2px 0 rgba(0,0,0,0.45); }
        .battle-winner-score { color: #ffd84a; font-size: clamp(1.85rem, 7vw, 2.8rem); font-weight: 900; text-align: center; }
        .battle-podium-compact { width: 100%; display: flex; flex-direction: column; gap: 7px; flex: 0 0 auto; min-height: 0; }
        .battle-rank-card { min-height: 48px; width: 100%; display: grid; grid-template-columns: 38px 38px minmax(0, 1fr) auto; align-items: center; gap: 8px; border-radius: 14px; padding: 7px 10px; color: white; text-align: left; background: rgba(0,0,0,0.28); border: 2px solid rgba(255,255,255,0.18); box-shadow: inset 0 0 18px rgba(255,255,255,0.06); }
        .battle-rank-card.rank-2 { background: linear-gradient(to top, #7f8c8d, #dfe6e9); color: #1f2526; }
        .battle-rank-card.rank-3 { background: linear-gradient(to top, #b05f2c, #e17055); color: #241006; }
        .battle-rank-card.rank-4 { background: linear-gradient(to top, #34495e, #74b9ff); color: #071522; }
        .battle-rank-medal { font-size: 1.1rem; font-weight: 900; line-height: 1; text-align: center; }
        .battle-rank-avatar { font-size: 1.55rem; line-height: 1; text-align: center; }
        .battle-rank-name { width: 100%; font-size: clamp(0.86rem, 3vw, 1.02rem); font-weight: 900; line-height: 1.05; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; overflow-wrap: anywhere; }
        .battle-rank-score { font-size: clamp(0.9rem, 3.5vw, 1.15rem); font-weight: 900; white-space: nowrap; }
        .battle-scoreboard-mini { width: 100%; display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 6px; max-height: 82px; overflow-y: auto; flex-shrink: 0; }
        .battle-score-row { display: flex; justify-content: space-between; align-items: center; gap: 6px; background: rgba(0,0,0,0.28); border-radius: 10px; padding: 6px 8px; color: white; font-weight: 900; min-width: 0; }
        .battle-score-row span:first-child { overflow: hidden; text-overflow: ellipsis; white-space: nowrap; }
        .battle-score-row span:last-child { color: #ffd84a; }
        #screen-career-map { padding-bottom: var(--bottom-safe-gap) !important; }
        #screen-online-game, #screen-online-tour-match, #screen-online-battle-arena { overflow-y: auto; }
        #screen-online-game .options-grid, #screen-online-tour-match .options-grid, #screen-online-battle-arena .options-grid { min-height: 260px; }

        @media (min-width: 768px) {
            .arena { flex-direction: row; height: 500px; }
            .arena-left { border-bottom: none; border-right: 3px solid rgba(255,255,255,0.1); }
            .player-header { flex-direction: column; gap: 5px; }
            .p-score { font-size: 4rem; margin-bottom: 20px; }
            .arena-timer { left: 50%; transform: translateX(-50%); top: 70px; right: auto; font-size: 2rem; }
            .options-grid { grid-template-columns: 1fr 1fr; }
            .battle-grid { flex-direction: row; flex-wrap: wrap; }
            .player-zone { width: 50%; height: 50%; border: 1px solid rgba(0,0,0,0.1); }
            .battle-grid[data-players="2"] .player-zone { width: 50%; height: 100%; }
            .battle-grid[data-players="3"] .player-zone { width: 33.33%; height: 100%; }
        }
        @media (max-width: 520px) {
            :root { --game-top-gap: calc(88px + var(--safe-top)); --battle-action-gap: calc(66px + var(--bottom-safe-gap)); }
            .battle-top-bar { height: 58px; }
            .battle-word { max-width: calc(100% - 82px); padding: 6px 18px; font-size: 1.25rem; letter-spacing: 0; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; }
            .battle-timer { right: 10px; font-size: 1.35rem; }
            .player-zone { padding: 4px; }
            .player-box { width: 94%; padding: 4px 10px; margin-bottom: 4px; border-radius: 8px; }
            .player-name-text { font-size: 0.92rem; min-width: 0; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; }
            .p-score { font-size: 1.55rem; }
            .battle-options { gap: 4px; padding: 4px; }
            .b-opt-btn { font-size: clamp(0.74rem, 3vw, 0.95rem); border-radius: 9px; padding: 2px 4px; }
            #screen-battle-arena > .nav-buttons .btn-sm { min-width: 84px; min-height: 42px; }
            .modal-box { padding: 14px; border-radius: 16px; }
            .modal-title { font-size: 1.25rem; margin-bottom: 10px; }
            .avatar-selection { grid-template-columns: repeat(5, 1fr); gap: 6px; max-height: 104px; margin: 8px 0 10px; }
            .avatar-option { font-size: 1.9rem; padding: 3px; border-radius: 10px; }
            .badges-container { max-height: min(31vh, 214px); padding: 10px; }
            .badges-container h3 { margin-top: 0 !important; margin-bottom: 7px !important; }
            .badge-tabs { margin-bottom: 7px; }
            .badge-grid { grid-template-columns: repeat(3, minmax(58px, 1fr)); max-height: 132px; gap: 6px; }
            .achievement-badge { min-height: 74px; padding: 5px 3px; }
            .badge-symbol { font-size: 1.65rem; }
            .badge-caption { font-size: 0.62rem; }
            #public-profile-modal .monster-avatar { font-size: 3.4rem !important; }
            #pub-prof-level { margin-bottom: 8px !important; }
            .clap-box { padding: 9px; }
            .battle-celebration-card { padding: 10px; gap: 7px; border-radius: 16px; }
            .battle-winner-box { padding: 10px; border-radius: 16px; gap: 8px; }
            .battle-winner-avatar { font-size: clamp(2.55rem, 11vw, 3.4rem); }
            .battle-winner-name { font-size: clamp(1.25rem, 5.2vw, 1.7rem); }
            .battle-winner-score { font-size: clamp(1.45rem, 6vw, 2rem); }
            .battle-podium-compact { gap: 6px; }
            .battle-rank-card { min-height: 44px; grid-template-columns: 34px 34px minmax(0, 1fr) auto; border-radius: 12px; padding: 6px 8px; gap: 7px; }
            .battle-scoreboard-mini { max-height: 70px; }
            .battle-score-row { padding: 5px 7px; font-size: 0.82rem; }
            .bracket-stage { flex-direction: column; }
            .tournament-champion-card { flex: 0 0 auto; min-height: 120px; width: 100%; }
        }
        @media (max-width: 430px) {
            .top-right-controls { gap: 5px; }
            .top-right-controls .btn-sm { min-width: 46px; padding: 6px 8px !important; }
            .profile-avatar-btn { width: 38px; height: 38px; font-size: 1.25rem; }
            .profile-info-text .name { max-width: 112px; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; }
            .profile-info-text .level { font-size: 0.72rem; }
            h1 { font-size: 1.55rem; margin-bottom: 6px; }
            .cat-select-row { gap: 8px; margin-bottom: 6px; }
            .cat-btn { font-size: 0.82rem; }
            .support-floating-btn, .ig-floating-btn { font-size: 0.82rem; padding: 7px 10px; }
        }
        @media (max-height: 760px) {
            #screen-home { margin-top: calc(96px + var(--safe-top)); gap: 5px; }
            .main-menu-grid { max-width: 440px; gap: 10px; }
            .menu-sq-btn .icon { font-size: clamp(2rem, 7vw, 2.7rem); }
            .modal-box { max-height: calc(100dvh - var(--safe-top) - var(--safe-bottom) - 18px); }
            .badges-container { max-height: min(28vh, 196px); }
            .badge-grid { max-height: 118px; }
            #screen-result .podium-container { height: 138px; }
            #screen-result .monster-avatar { font-size: 42px; }
            #screen-result h2 { font-size: 1.25rem; }
            #screen-result.battle-result-screen { margin-top: calc(92px + var(--safe-top)); height: calc(100dvh - 112px - var(--safe-top) - var(--bottom-safe-gap)); min-height: 320px; }
            .battle-celebration-kicker { font-size: 0.7rem; }
            .battle-winner-avatar { font-size: 2.55rem; }
            .battle-winner-name { font-size: 1.25rem; }
            .battle-winner-score { font-size: 1.45rem; }
            .battle-rank-card { min-height: 40px; gap: 6px; padding: 5px 7px; }
            .battle-rank-avatar { font-size: 1.3rem; }
            .battle-rank-medal { font-size: 0.95rem; }
            .battle-rank-score { font-size: 0.9rem; }
            .battle-scoreboard-mini { max-height: 58px; }
            .battle-top-bar { height: 54px; }
            .battle-word { font-size: 1.12rem; }
        }
        @media (orientation: landscape) and (max-height: 620px) {
            :root { --top-safe-gap: calc(8px + var(--safe-top)); --bottom-safe-gap: calc(14px + var(--safe-bottom)); --game-top-gap: calc(58px + var(--safe-top)); --battle-action-gap: calc(52px + var(--bottom-safe-gap)); }
            #app { padding: 8px 8px calc(8px + var(--bottom-safe-gap)); max-width: none; }
            #top-bar { top: var(--top-safe-gap); }
            .screen { margin-top: calc(58px + var(--safe-top)); padding-bottom: calc(12px + var(--bottom-safe-gap)); }
            #screen-home { margin-top: calc(54px + var(--safe-top)); padding-bottom: calc(18px + var(--bottom-safe-gap)); gap: 6px; }
            h1 { font-size: clamp(1.25rem, 4vw, 1.8rem); margin: 0 0 4px; }
            h2 { margin: 0 0 8px; font-size: clamp(1rem, 3vw, 1.35rem); }
            .monster-avatar { font-size: 42px; margin-bottom: 0; }
            .cat-select-row { max-width: 820px; margin-bottom: 4px; }
            .main-menu-grid { grid-template-columns: repeat(4, minmax(0, 1fr)); grid-template-rows: 1fr; max-width: 920px; gap: 10px; margin-bottom: 10px; }
            .menu-sq-btn { aspect-ratio: 1.35 / 1; padding: 8px; font-size: clamp(0.78rem, 2.2vw, 0.98rem); border-radius: 14px; }
            .menu-sq-btn .icon { font-size: clamp(1.6rem, 5vw, 2.4rem); margin-bottom: 4px; }
            .tournament-bracket-screen { margin-top: calc(58px + var(--safe-top)); }
            .bracket-stage { gap: 8px; }
            .bracket-scroll { padding: 8px 8px 16px; }
            .tournament-champion-card { flex-basis: 190px; min-height: 130px; padding: 12px; }
            .match-node { width: 132px; padding: 7px; }
            .bracket-round { min-width: 140px; gap: 10px; }
            #screen-battle-arena > .nav-buttons { bottom: calc(8px + var(--safe-bottom)) !important; }
        }


        /* PC WEB UYARLAMASI - GitHub Pages masaustu surumu */
        @media (min-width: 1024px) and (min-height: 700px) {
            :root {
                --top-safe-gap: 22px;
                --bottom-safe-gap: 22px;
                --game-top-gap: 104px;
                --battle-action-gap: 92px;
            }
            body {
                align-items: stretch;
                min-height: 100vh;
                min-height: 100dvh;
                overflow: hidden;
                touch-action: auto;
                background:
                    radial-gradient(circle at 18% 18%, rgba(9,132,227,0.28), transparent 30%),
                    radial-gradient(circle at 82% 14%, rgba(0,184,148,0.20), transparent 28%),
                    linear-gradient(135deg, #151a25 0%, #252d3a 48%, #10131c 100%);
            }
            #app {
                width: min(1480px, calc(100vw - 40px));
                height: calc(100dvh - 40px);
                max-width: 1480px;
                margin: 20px auto;
                border-radius: 18px;
                border: 2px solid rgba(255,255,255,0.14);
                padding: 24px 32px calc(24px + var(--bottom-safe-gap));
                box-shadow: 0 24px 90px rgba(0,0,0,0.55);
                overflow: hidden;
            }
            #top-bar {
                left: 32px;
                right: 32px;
                top: 22px;
            }
            .top-left-profile {
                min-width: 230px;
                padding-right: 18px;
            }
            .top-right-controls {
                gap: 10px;
            }
            .top-right-controls .btn-sm {
                min-width: 52px;
                min-height: 44px;
            }
            .screen {
                margin-top: 86px;
                padding-bottom: 26px;
                width: 100%;
                overflow: hidden;
            }
            #screen-login {
                margin-top: 0;
                display: none;
                justify-content: center;
                align-items: center;
            }
            #screen-login.active { display: flex; }
            #screen-login .monster-avatar { font-size: 82px; }
            .login-box {
                max-width: 460px;
                padding: 30px;
                border-radius: 16px;
                box-shadow: 0 18px 50px rgba(0,0,0,0.34);
            }
            #screen-home {
                margin-top: 74px;
                gap: 14px;
                justify-content: center;
                padding-bottom: 70px;
            }
            #screen-home h1 {
                font-size: clamp(2rem, 3.1vw, 3.45rem);
                margin-bottom: 8px;
            }
            #screen-home .monster-avatar {
                font-size: 72px;
            }
            .cat-select-row {
                max-width: 960px;
                gap: 14px;
            }
            .main-menu-grid {
                width: min(100%, 1040px);
                max-width: 1040px;
                grid-template-columns: repeat(4, minmax(0, 1fr));
                grid-template-rows: 1fr;
                gap: 16px;
                margin: 4px auto 18px;
            }
            .menu-sq-btn {
                aspect-ratio: 1.18 / 1;
                border-radius: 16px;
                font-size: 1.02rem;
                padding: 18px 12px;
            }
            .menu-sq-btn .icon {
                font-size: 3rem;
            }
            .support-floating-btn,
            .ig-floating-btn {
                position: absolute;
                bottom: 24px;
                padding: 10px 15px;
            }
            .card-container {
                max-width: 780px;
                height: min(46vh, 440px);
                margin-top: 8px;
            }
            .word-title { font-size: clamp(2.7rem, 4vw, 4.3rem); }
            .meaning-text { font-size: clamp(2.2rem, 3.4vw, 3.4rem); }
            .synonym { font-size: 1.45rem; }
            #screen-flashcards .nav-buttons {
                max-width: 780px;
                margin-left: auto;
                margin-right: auto;
            }
            .question-box {
                max-width: 920px;
                font-size: clamp(1.6rem, 2.2vw, 2.4rem);
                padding: 22px 28px;
                margin-bottom: 18px;
            }
            .options-grid {
                width: min(100%, 920px);
                max-width: 920px;
                grid-template-columns: repeat(2, minmax(0, 1fr));
                gap: 14px;
                flex-grow: 0;
            }
            #screen-online-game .options-grid,
            #screen-online-tour-match .options-grid,
            #screen-online-battle-arena .options-grid {
                min-height: 330px;
            }
            .option-btn,
            .b-opt-btn {
                min-height: 86px;
                font-size: 1.14rem;
            }
            .ol-header,
            .ol-timer-bar {
                width: min(100%, 920px);
                max-width: 920px;
            }
            .ol-timer-bar {
                height: 18px;
            }
            .modal-box {
                max-width: min(620px, calc(100vw - 96px));
                border-radius: 16px;
                padding: 24px;
            }
            #friends-modal .modal-box {
                max-width: 760px;
            }
            .avatar-selection {
                grid-template-columns: repeat(6, 1fr);
                max-height: 176px;
            }
            .badge-grid {
                grid-template-columns: repeat(5, minmax(72px, 1fr));
                max-height: 210px;
            }
            .map-wrapper {
                padding: 44px 72px;
                gap: 84px;
            }
            .level-circle {
                width: 102px;
                height: 102px;
                font-size: 1.32rem;
            }
            .path-line {
                width: 94px;
                right: -88px;
                top: 50px;
            }
            .tournament-bracket-screen {
                margin-top: 74px;
            }
            .bracket-stage {
                width: 100%;
                min-height: 0;
            }
            .bracket-scroll {
                padding: 18px 20px 28px;
            }
            .bracket-tree {
                gap: 46px;
            }
            .match-node {
                width: 170px;
                padding: 11px;
            }
            .tournament-champion-card {
                flex-basis: 300px;
                min-height: 260px;
            }
            #screen-battle-setup,
            #screen-local-tour-setup,
            #screen-tour-menu,
            #screen-battle-menu,
            #screen-online-hub,
            #screen-create-room {
                overflow-y: auto;
            }
            #battle-names-area > div,
            #screen-battle-setup > select,
            #screen-battle-setup > .nav-buttons,
            #screen-local-tour-setup > .nav-buttons {
                max-width: 560px;
            }
            .battle-container {
                top: 96px;
                bottom: 92px;
                left: 16px;
                right: 16px;
                width: auto;
                border-radius: 16px;
                overflow: hidden;
                box-shadow: inset 0 0 0 2px rgba(255,255,255,0.08), 0 18px 44px rgba(0,0,0,0.32);
            }
            .battle-top-bar {
                height: 86px;
            }
            .battle-word {
                font-size: clamp(2rem, 3.1vw, 3.3rem);
                max-width: calc(100% - 180px);
            }
            .battle-timer {
                right: 30px;
                font-size: 2.4rem;
            }
            .battle-grid {
                flex-direction: row;
                flex-wrap: wrap;
            }
            .battle-grid[data-players="2"] .player-zone { width: 50%; height: 100%; }
            .battle-grid[data-players="3"] .player-zone { width: 33.333%; height: 100%; }
            .battle-grid[data-players="4"] .player-zone { width: 50%; height: 50%; }
            .player-zone {
                border: 1px solid rgba(0,0,0,0.22);
                padding: 10px;
            }
            .player-box {
                width: min(94%, 520px);
                padding: 8px 18px;
                border-radius: 12px;
            }
            .player-name-text {
                font-size: 1.25rem;
                max-width: 70%;
                overflow: hidden;
                text-overflow: ellipsis;
                white-space: nowrap;
            }
            .p-score {
                font-size: clamp(2.6rem, 4vw, 4.7rem);
            }
            .battle-options {
                max-width: 620px;
                gap: 10px;
            }
            #screen-battle-arena > .nav-buttons {
                bottom: 28px !important;
                padding: 0 32px;
            }
            #screen-result.battle-result-screen {
                height: auto;
                min-height: 0;
                margin-top: 74px;
                padding-bottom: 24px;
                overflow-y: auto;
            }
            #screen-result.battle-result-screen #tour-podium-area {
                max-width: 720px;
            }
            .battle-celebration-card {
                max-width: 720px;
                padding: 20px;
                border-radius: 18px;
            }
        }

        @media (min-width: 1440px) and (min-height: 820px) {
            #app {
                width: min(1600px, calc(100vw - 56px));
                height: calc(100dvh - 56px);
                margin: 28px auto;
            }
            .main-menu-grid { max-width: 1160px; }
            .menu-sq-btn { min-height: 210px; }
            .card-container { max-width: 860px; }
            .question-box,
            .options-grid,
            .ol-header,
            .ol-timer-bar { max-width: 1040px; }
        }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        @keyframes float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-15px)} }
        @keyframes growUp { from { height: 0; } }
        @keyframes scorePop { 0%{opacity:1; transform:translateY(0) scale(0.5)} 100%{opacity:0; transform:translateY(-50px) scale(1.5)} }
        @keyframes popIn { from{transform:scale(0)} to{transform:scale(1)} }
        @keyframes introPop { 0%{opacity:0; transform:scale(0.82)} 18%{opacity:1; transform:scale(1.04)} 78%{opacity:1; transform:scale(1)} 100%{opacity:1; transform:scale(0.98)} }
        @keyframes introFloat { 0%,100%{transform:translateY(0) rotate(-1deg)} 50%{transform:translateY(-10px) rotate(1deg)} }
        @keyframes introSpark { 0%,100%{opacity:0.25; transform:scale(0.75)} 50%{opacity:1; transform:scale(1.35)} }
    </style>
</head>
<body>

<script>
// =========================================================================
// 1. KELİME DATALARI
// =========================================================================
const vocabData={1:[{w:"abandon",m:"terk etmek",s:"leave"},{w:"abrupt",m:"ani",s:"sudden"},{w:"basis",m:"temel",s:"foundation"},{w:"candidate",m:"aday",s:"applicant"},{w:"considerable",m:"kayda değer",s:"significant"},{w:"deceive",m:"kandırmak",s:"trick"},{w:"extensive",m:"kapsamlı",s:"comprehensive"},{w:"grief",m:"keder",s:"sadness"},{w:"hesitate",m:"tereddüt etmek",s:"pause"},{w:"inherently",m:"doğası gereği",s:"naturally"},{w:"intense",m:"yoğun",s:"strong"},{w:"measure",m:"önlem",s:"precaution"},{w:"notably",m:"özellikle",s:"particularly"},{w:"novelty",m:"yenilik",s:"innovation"},{w:"obtain",m:"edinmek",s:"acquire"},{w:"outstanding",m:"olağanüstü",s:"exceptional"},{w:"praise",m:"övmek",s:"compliment"},{w:"response",m:"yanıt",s:"reaction"},{w:"rigid",m:"katı",s:"inflexible"},{w:"severely",m:"şiddetli biçimde",s:"harshly"},{w:"absence",m:"yokluk",s:"lack"},{w:"audible",m:"duyulabilir",s:"loud enough"},{w:"benefit",m:"fayda",s:"advantage"},{w:"broadly",m:"genel olarak",s:"generally"},{w:"collapse",m:"çökmek",s:"fall down"},{w:"consecutively",m:"peş peşe",s:"successively"},{w:"devote",m:"adamak",s:"dedicate"},{w:"discrimination",m:"ayrımcılık",s:"bias"},{w:"durable",m:"dayanıklı",s:"long-lasting"},{w:"elaborately",m:"detaylıca",s:"intricately"},{w:"fierce",m:"şiddetli",s:"violent"},{w:"halt",m:"durma",s:"stop"},{w:"impair",m:"bozmak",s:"weaken"},{w:"moderate",m:"ölçülü",s:"reasonable"},{w:"negotiate",m:"müzakere etmek",s:"discuss"},{w:"outbreak",m:"patlak verme",s:"eruption"},{w:"predominantly",m:"ağırlıklı olarak",s:"mainly"},{w:"recruit",m:"işe almak",s:"employ"},{w:"sparse",m:"seyrek",s:"thin"},{w:"tension",m:"gerilim",s:"strain"}],2:[{w:"abolish",m:"yürürlükten kaldırmak",s:"end"},{w:"barren",m:"çorak",s:"infertile"},{w:"bold",m:"cesur",s:"brave"},{w:"controversy",m:"tartışma",s:"debate"},{w:"destiny",m:"kader",s:"fate"},{w:"eagerly",m:"istekle",s:"keenly"},{w:"encounter",m:"karşılaşmak",s:"meet"},{w:"endeavour",m:"çaba",s:"effort"},{w:"fee",m:"ücret",s:"charge"},{w:"fertile",m:"bereketli",s:"productive"},{w:"immensely",m:"son derece/çok",s:"extremely"},{w:"maintain",m:"sürdürmek",s:"sustain"},{w:"morally",m:"ahlaken",s:"ethically"},{w:"notify",m:"bildirmek",s:"inform"},{w:"peculiar",m:"tuhaf",s:"strange"},{w:"phase",m:"aşama",s:"stage"},{w:"promote",m:"teşvik etmek",s:"encourage"},{w:"reckless",m:"dikkatsiz",s:"careless"},{w:"resist",m:"direnmek",s:"oppose"},{w:"steady",m:"sabit",s:"stable"},{w:"adverse",m:"olumsuz",s:"unfavourable"},{w:"altitude",m:"rakım",s:"height"},{w:"bearable",m:"katlanılabilir",s:"endurable"},{w:"collide",m:"çarpışmak",s:"crash"},{w:"conclusive",m:"kesin",s:"definitive"},{w:"decline",m:"azalmak/reddetmek",s:"decrease/refuse"},{w:"emphasis",m:"vurgu",s:"stress"},{w:"extraterrestrial",m:"dünya dışı",s:"alien"},{w:"hinder",m:"engel olmak",s:"hamper"},{w:"irreversibly",m:"geri dönülmez şekilde",s:"permanently"},{w:"menace",m:"tehdit",s:"threat"},{w:"negligence",m:"ihmal",s:"carelessness"},{w:"outlook",m:"bakış açısı",s:"viewpoint"},{w:"precisely",m:"tam olarak",s:"exactly"},{w:"prone",m:"yatkın",s:"susceptible"},{w:"recipe",m:"tarif",s:"formula"},{w:"resemble",m:"benzemek",s:"look like"},{w:"thoroughly",m:"iyice",s:"completely"},{w:"urgent",m:"acil",s:"pressing"},{w:"utilize",m:"kullanmak",s:"use"}],3:[{w:"acknowledge",m:"kabul etmek",s:"admit"},{w:"artefact",m:"tarihi eser",s:"relic"},{w:"budget",m:"bütçe",s:"plan"},{w:"competent",m:"yetkin",s:"capable"},{w:"decent",m:"makul/terbiyeli",s:"proper"},{w:"greed",m:"açgözlülük",s:"avarice"},{w:"inferior",m:"aşağı/düşük",s:"lower"},{w:"interpret",m:"yorumlamak",s:"explain"},{w:"legacy",m:"miras",s:"inheritance"},{w:"misuse",m:"kötüye kullanmak",s:"abuse"},{w:"noticeable",m:"farkedilebilir",s:"distinct"},{w:"odour",m:"koku",s:"smell"},{w:"outdated",m:"modası geçmiş",s:"old-fashioned"},{w:"partially",m:"kısmen",s:"partly"},{w:"participate",m:"katılmak",s:"take part"},{w:"persistently",m:"ısrarla",s:"continuously"},{w:"qualify",m:"hak kazanmak",s:"be eligible"},{w:"rear",m:"yetiştirmek",s:"raise"},{w:"ruthless",m:"acımasız",s:"merciless"},{w:"tendency",m:"eğilim",s:"inclination"},{w:"abundant",m:"bol",s:"plentiful"},{w:"adjust",m:"ayarlamak",s:"adapt"},{w:"commodity",m:"ticari mal",s:"goods"},{w:"desperately",m:"çaresizce",s:"hopelessly"},{w:"diverse",m:"çeşitli",s:"various"},{w:"emerge",m:"ortaya çıkmak",s:"appear"},{w:"gadget",m:"alet",s:"device"},{w:"inhabitant",m:"sakin/yerli",s:"resident"},{w:"internal",m:"dahili",s:"inner"},{w:"justify",m:"haklı çıkarmak",s:"validate"},{w:"manually",m:"elle",s:"by hand"},{w:"mild",m:"ılıman",s:"gentle"},{w:"necessitate",m:"gerektirmek",s:"require"},{w:"obligation",m:"zorunluluk",s:"duty"},{w:"obstacle",m:"engel",s:"barrier"},{w:"overwhelming",m:"ezici",s:"staggering"},{w:"primarily",m:"öncelikle",s:"mainly"},{w:"recover",m:"iyileşmek",s:"get well"},{w:"spill",m:"dökmek",s:"pour"},{w:"vacant",m:"boş",s:"empty"}],4:[{w:"achieve",m:"başarmak",s:"accomplish"},{w:"adequate",m:"yeterli",s:"enough"},{w:"avoid",m:"kaçınmak",s:"evade"},{w:"commit",m:"işlemek/adamak",s:"perform/dedicate"},{w:"compulsory",m:"zorunlu",s:"obligatory"},{w:"conflict",m:"çatışma",s:"clash"},{w:"constantly",m:"sürekli",s:"continuously"},{w:"demanding",m:"zahmetli",s:"challenging"},{w:"diagnosis",m:"teşhis",s:"identification"},{w:"dramatically",m:"çarpıcı biçimde",s:"significantly"},{w:"entire",m:"tüm",s:"whole"},{w:"expose",m:"açığa çıkarmak/maruz bırakmak",s:"reveal"},{w:"gain",m:"kazanmak",s:"acquire"},{w:"lack",m:"eksiklik",s:"shortage"},{w:"mutually",m:"karşılıklı",s:"reciprocally"},{w:"occupy",m:"işgal/meşgul etmek",s:"inhabit"},{w:"output",m:"çıktı",s:"production"},{w:"persuasive",m:"ikna edici",s:"convincing"},{w:"previous",m:"önceki",s:"prior"},{w:"profit",m:"kâr",s:"gain"},{w:"adopt",m:"benimsemek",s:"embrace"},{w:"aim",m:"amaç",s:"goal"},{w:"barely",m:"zar zor",s:"hardly"},{w:"burden",m:"yük",s:"load"},{w:"commercial",m:"ticari",s:"mercantile"},{w:"compile",m:"derlemek",s:"assemble"},{w:"deliberately",m:"kasten",s:"intentionally"},{w:"disorder",m:"düzensizlik",s:"chaos"},{w:"evident",m:"belirgin",s:"obvious"},{w:"extrovert",m:"dışa dönük",s:"outgoing"},{w:"foresee",m:"öngörmek",s:"predict"},{w:"glance",m:"bakış",s:"peek"},{w:"hazard",m:"tehlike",s:"danger"},{w:"illiterate",m:"okuma yazma bilmeyen",s:"uneducated"},{w:"interact",m:"etkileşmek",s:"communicate"},{w:"misleading",m:"yanıltıcı",s:"deceptive"},{w:"object",m:"itiraz etmek",s:"oppose"},{w:"outcome",m:"sonuç",s:"result"},{w:"particularly",m:"özellikle",s:"especially"},{w:"reject",m:"reddetmek",s:"refuse"}],5:[{w:"astonish",m:"şaşırtmak",s:"amaze"},{w:"aware",m:"farkında",s:"conscious"},{w:"crucial",m:"hayati",s:"vital"},{w:"evenly",m:"eşit şekilde",s:"equally"},{w:"expand",m:"genişlemek",s:"enlarge"},{w:"flaw",m:"kusur",s:"defect"},{w:"humid",m:"nemli",s:"damp"},{w:"irrational",m:"mantıksız",s:"illogical"},{w:"mortality",m:"ölüm oranı",s:"death rate"},{w:"offence",m:"suç",s:"crime"},{w:"precaution",m:"önlem",s:"safeguard"},{w:"reduce",m:"azaltmak",s:"decrease"},{w:"reluctantly",m:"gönülsüzce",s:"unwillingly"},{w:"retain",m:"muhafaza etmek",s:"keep"},{w:"slightly",m:"hafifçe",s:"a little"},{w:"substance",m:"madde",s:"matter"},{w:"thrive",m:"gelişmek",s:"flourish"},{w:"undergo",m:"geçirmek (süreç)",s:"experience"},{w:"vivid",m:"canlı",s:"bright"},{w:"wise",m:"bilge",s:"sensible"},{w:"access",m:"erişim",s:"entry"},{w:"annual",m:"yıllık",s:"yearly"},{w:"briefly",m:"kısaca",s:"shortly"},{w:"challenge",m:"meydan okuma",s:"difficulty"},{w:"clumsy",m:"sakar",s:"awkward"},{w:"consist",m:"oluşmak",s:"comprise"},{w:"delay",m:"gecikmek/ertelemek",s:"postpone"},{w:"depiction",m:"tasvir",s:"portrayal"},{w:"enable",m:"olanak sağlamak",s:"allow"},{w:"eventually",m:"sonunda",s:"finally"},{w:"forbid",m:"yasaklamak",s:"prohibit"},{w:"hint",m:"ipucu",s:"clue"},{w:"initially",m:"başlangıçta",s:"at first"},{w:"merciful",m:"merhametli",s:"forgiving"},{w:"native",m:"yerli",s:"indigenous"},{w:"opponent",m:"rakip",s:"rival"},{w:"overcome",m:"üstesinden gelmek",s:"conquer"},{w:"precious",m:"değerli",s:"valuable"},{w:"profoundly",m:"derinden",s:"deeply"},{w:"reveal",m:"açığa çıkarmak",s:"disclose"}],6:[{w:"affordable",m:"hesaplı",s:"inexpensive"},{w:"alert",m:"tetikte",s:"vigilant"},{w:"conceal",m:"gizlemek",s:"hide"},{w:"content",m:"içerik",s:"substance"},{w:"distract",m:"dikkat dağıtmak",s:"divert"},{w:"evacuate",m:"tahliye etmek",s:"vacate"},{w:"futile",m:"nafile",s:"useless"},{w:"gradually",m:"yavaş yavaş",s:"slowly"},{w:"handle",m:"ele almak",s:"manage"},{w:"indication",m:"belirti",s:"sign"},{w:"infer",m:"çıkarım yapmak",s:"deduce"},{w:"launch",m:"başlatmak",s:"start"},{w:"liable",m:"sorumlu/eğilimli",s:"responsible"},{w:"necessarily",m:"muhakkak",s:"inevitably"},{w:"permanently",m:"kalıcı olarak",s:"forever"},{w:"proposal",m:"teklif",s:"offer"},{w:"span",m:"süre",s:"duration"},{w:"spoil",m:"bozmak",s:"ruin"},{w:"stunning",m:"çarpıcı",s:"spectacular"},{w:"trivial",m:"önemsiz",s:"insignificant"},{w:"aid",m:"yardım etmek",s:"assist"},{w:"appreciation",m:"takdir",s:"gratitude"},{w:"contribute",m:"katkı yapmak",s:"donate"},{w:"dismiss",m:"kovmak/reddetmek",s:"fire/reject"},{w:"distant",m:"uzak",s:"remote"},{w:"exclusively",m:"sadece",s:"solely"},{w:"excuse",m:"bahane",s:"pretext"},{w:"host",m:"ev sahibi/sunucu",s:"presenter"},{w:"identical",m:"özdeş",s:"same"},{w:"insight",m:"kavrayış",s:"perception"},{w:"jointly",m:"ortaklaşa",s:"together"},{w:"labour",m:"emek",s:"work"},{w:"remnant",m:"kalıntı",s:"remains"},{w:"provide",m:"sağlamak",s:"supply"},{w:"scarce",m:"kıt",s:"rare"},{w:"shallow",m:"sığ",s:"not deep"},{w:"undertake",m:"üstlenmek",s:"take on"},{w:"vanish",m:"yok olmak",s:"disappear"},{w:"versatile",m:"çok yönlü",s:"adaptable"},{w:"virtually",m:"neredeyse",s:"almost"}],7:[{w:"amusing",m:"eğlenceli",s:"entertaining"},{w:"arise",m:"ortaya çıkmak",s:"occur"},{w:"bilingual",m:"iki dilli",s:"speaking 2 langs"},{w:"convince",m:"ikna etmek",s:"persuade"},{w:"cue",m:"ipucu",s:"signal"},{w:"debt",m:"borç",s:"liability"},{w:"extinct",m:"nesli tükenmiş",s:"vanished"},{w:"fragile",m:"kırılgan",s:"delicate"},{w:"grasp",m:"kavrama",s:"grip"},{w:"modest",m:"mütevazı",s:"humble"},{w:"obediently",m:"itaatle",s:"submissively"},{w:"purchase",m:"satın almak/satın alma",s:"buy"},{w:"require",m:"gerektirmek",s:"need"},{w:"restrict",m:"kısıtlamak",s:"limit"},{w:"solely",m:"yalnızca",s:"only"},{w:"swiftly",m:"hızla",s:"quickly"},{w:"trait",m:"özellik",s:"characteristic"},{w:"vary",m:"değişmek",s:"differ"},{w:"voluntary",m:"gönüllü",s:"willing"},{w:"withdraw",m:"çekilmek",s:"retreat"},{w:"accommodate",m:"barındırmak",s:"house"},{w:"accustomed",m:"alışkın",s:"used to"},{w:"combat",m:"savaşmak",s:"fight"},{w:"comparatively",m:"nispeten",s:"relatively"},{w:"crop",m:"ekin",s:"harvest"},{w:"deficient",m:"yetersiz",s:"lacking"},{w:"derive",m:"türetmek/kaynaklanmak",s:"originate"},{w:"extent",m:"boyut",s:"degree"},{w:"fatigue",m:"yorgunluk",s:"exhaustion"},{w:"firmly",m:"sıkıca",s:"strongly"},{w:"fortunate",m:"şanslı",s:"lucky"},{w:"genuine",m:"hakiki",s:"authentic"},{w:"hostility",m:"düşmanlık",s:"animosity"},{w:"ignore",m:"görmezden gelmek",s:"disregard"},{w:"influence",m:"etki",s:"impact"},{w:"invest",m:"yatırım yapmak",s:"fund"},{w:"lethal",m:"ölümcül",s:"deadly"},{w:"namely",m:"yani",s:"specifically"},{w:"reliable",m:"güvenilir",s:"trustworthy"},{w:"tackle",m:"ele almak",s:"address"}],8:[{w:"addiction",m:"bağımlılık",s:"dependence"},{w:"ample",m:"bol",s:"plenty"},{w:"beg",m:"yalvarmak",s:"plead"},{w:"cautiously",m:"dikkatlice",s:"carefully"},{w:"combine",m:"birleştirmek",s:"merge"},{w:"digestion",m:"sindirim",s:"breakdown"},{w:"engaged",m:"nişanlı/meşgul",s:"betrothed/busy"},{w:"excavation",m:"kazı",s:"digging"},{w:"faithful",m:"sadık",s:"loyal"},{w:"habitat",m:"yaşam alanı",s:"environment"},{w:"hospitable",m:"misafirperver",s:"welcoming"},{w:"imperative",m:"zorunluluk",s:"necessity"},{w:"impulsively",m:"dürtüsel olarak",s:"spontaneously"},{w:"infinite",m:"sonsuz",s:"endless"},{w:"monitor",m:"izlemek",s:"observe"},{w:"nutrient",m:"besin",s:"nourishment"},{w:"occur",m:"meydana gelmek",s:"happen"},{w:"prove",m:"kanıtlamak",s:"demonstrate"},{w:"recall",m:"hatırlamak",s:"remember"},{w:"simply",m:"sadece",s:"merely"},{w:"aspect",m:"yön",s:"feature"},{w:"confirm",m:"onaylamak",s:"verify"},{w:"consider",m:"düşünmek",s:"think of"},{w:"formerly",m:"eskiden",s:"previously"},{w:"heal",m:"iyileşmek",s:"cure"},{w:"herd",m:"sürü",s:"flock"},{w:"inevitable",m:"kaçınılmaz",s:"unavoidable"},{w:"insane",m:"çılgın",s:"mad"},{w:"miserable",m:"sefil",s:"unhappy"},{w:"opt",m:"seçmek",s:"choose"},{w:"plain",m:"sade",s:"simple"},{w:"regret",m:"pişman olmak",s:"rue"},{w:"root",m:"kök",s:"origin"},{w:"schedule",m:"program",s:"timetable"},{w:"split",m:"bölmek",s:"divide"},{w:"starvation",m:"açlık",s:"famine"},{w:"suspiciously",m:"şüpheyle",s:"doubtfully"},{w:"tough",m:"sert",s:"hard"},{w:"violate",m:"ihlal etmek",s:"breach"},{w:"witness",m:"tanık",s:"observer"}],9:[{w:"administer",m:"yönetmek",s:"manage"},{w:"ancestor",m:"ata",s:"forefather"},{w:"beware",m:"sakınmak",s:"watch out"},{w:"collaboratively",m:"iş birliğiyle",s:"cooperatively"},{w:"compatible",m:"uyumlu",s:"consistent"},{w:"competitive",m:"rekabetçi",s:"rivalrous"},{w:"contamination",m:"kirlilik",s:"pollution"},{w:"defect",m:"kusur",s:"fault"},{w:"envious",m:"kıskanç",s:"jealous"},{w:"flavour",m:"tat",s:"taste"},{w:"identify",m:"tanımlamak",s:"recognize"},{w:"indifferent",m:"ilgisiz",s:"uninterested"},{w:"instantly",m:"anında",s:"immediately"},{w:"omit",m:"hariç tutmak",s:"exclude"},{w:"pace",m:"hız",s:"speed"},{w:"randomly",m:"rastgele",s:"arbitrarily"},{w:"reflect",m:"yansıtmak",s:"mirror"},{w:"rival",m:"rakip",s:"opponent"},{w:"sack",m:"kovmak",s:"fire"},{w:"tedious",m:"sıkıcı",s:"boring"},{w:"advance",m:"ilerleme",s:"progress"},{w:"appeal",m:"cezbetmek",s:"attract"},{w:"bankrupt",m:"iflas etmiş",s:"insolvent"},{w:"captivity",m:"esaret",s:"imprisonment"},{w:"compose",m:"oluşturmak",s:"create"},{w:"convenient",m:"uygun",s:"suitable"},{w:"deserve",m:"hak etmek",s:"merit"},{w:"distinct",m:"belirgin",s:"clear"},{w:"dull",m:"sıkıcı",s:"boring"},{w:"expedition",m:"keşif gezisi",s:"journey"},{w:"favour",m:"iyilik",s:"kindness"},{w:"hastily",m:"aceleyle",s:"hurriedly"},{w:"impress",m:"etkilemek",s:"awe"},{w:"infancy",m:"bebeklik",s:"beginning"},{w:"mend",m:"tamir etmek",s:"repair"},{w:"passionately",m:"tutkuyla",s:"intensely"},{w:"postpone",m:"ertelemek",s:"delay"},{w:"practically",m:"hemen hemen",s:"almost"},{w:"rigorous",m:"titiz",s:"strict"},{w:"sound",m:"sağlam",s:"solid"}],10:[{w:"abstract",m:"soyut",s:"conceptual"},{w:"accompany",m:"eşlik etmek",s:"escort"},{w:"blend",m:"karışım/karıştırmak",s:"mix"},{w:"capture",m:"yakalamak",s:"catch"},{w:"charge",m:"ücretlendirmek",s:"bill"},{w:"crew",m:"mürettebat",s:"team"},{w:"deprivation",m:"yoksunluk",s:"lack"},{w:"dreadful",m:"korkunç",s:"terrible"},{w:"edible",m:"yenilebilir",s:"eatable"},{w:"ensure",m:"garantiye almak",s:"guarantee"},{w:"fever",m:"ateş",s:"temperature"},{w:"indefinitely",m:"süresiz olarak",s:"forever"},{w:"latter",m:"ikincisi",s:"second"},{w:"manufacture",m:"üretmek",s:"produce"},{w:"miracle",m:"mucize",s:"wonder"},{w:"potentially",m:"potansiyel olarak",s:"possibly"},{w:"predator",m:"yırtıcı",s:"hunter"},{w:"raw",m:"çiğ",s:"uncooked"},{w:"smooth",m:"pürüzsüz",s:"flat"},{w:"trigger",m:"tetiklemek",s:"activate"},{w:"associate",m:"ilişkilendirmek",s:"link"},{w:"cover",m:"kapsamak",s:"include"},{w:"failure",m:"başarısızlık",s:"defeat"},{w:"fit",m:"uygun",s:"suitable"},{w:"grip",m:"kavrama",s:"hold"},{w:"humorous",m:"komik",s:"funny"},{w:"inspire",m:"ilham vermek",s:"motivate"},{w:"item",m:"öge",s:"object"},{w:"massive",m:"devasa",s:"huge"},{w:"naval",m:"donanmaya/denize ait",s:"marine"},{w:"pose",m:"teşkil etmek",s:"present"},{w:"replace",m:"değiştirmek",s:"substitute"},{w:"roughly",m:"kabaca",s:"approximately"},{w:"spectator",m:"seyirci",s:"onlooker"},{w:"superior",m:"üstün",s:"better"},{w:"survey",m:"anket",s:"poll"},{w:"typically",m:"tipik olarak",s:"usually"},{w:"vague",m:"belirsiz",s:"unclear"},{w:"urge",m:"dürtü",s:"desire"},{w:"worship",m:"ibadet etmek",s:"pray"}],11:[{w:"accelerate",m:"hızlandırmak",s:"speed up"},{w:"actually",m:"aslında",s:"in fact"},{w:"bitterly",m:"acı bir şekilde",s:"resentfully"},{w:"congestion",m:"tıkanıklık",s:"jam"},{w:"distinguishable",m:"ayırt edilebilir",s:"distinct"},{w:"expense",m:"masraf",s:"cost"},{w:"flourish",m:"gelişmek",s:"thrive"},{w:"intact",m:"bozulmamış",s:"undamaged"},{w:"memorize",m:"ezberlemek",s:"learn by heart"},{w:"mysterious",m:"gizemli",s:"secretive"},{w:"nonsense",m:"saçmalık",s:"rubbish"},{w:"ornament",m:"süs",s:"decoration"},{w:"possess",m:"sahip olmak",s:"own"},{w:"pursue",m:"takip etmek",s:"chase"},{w:"purposefully",m:"amaçlı olarak/bilerek",s:"deliberately"},{w:"remark",m:"söz/yorum",s:"comment"},{w:"solitary",m:"yalnız",s:"alone"},{w:"subtle",m:"ince/kurnaz",s:"faint"},{w:"surpass",m:"aşmak",s:"exceed"},{w:"widespread",m:"yaygın",s:"common"},{w:"accuracy",m:"doğruluk",s:"precision"},{w:"conclude",m:"sonuçlandırmak",s:"finish"},{w:"convert",m:"dönüştürmek",s:"transform"},{w:"critically",m:"ciddi şekilde",s:"severely"},{w:"eligible",m:"uygun",s:"qualified"},{w:"endanger",m:"tehlikeye atmak",s:"imperil"},{w:"familiar",m:"tanıdık",s:"well-known"},{w:"gap",m:"boşluk",s:"space"},{w:"hereditary",m:"kalıtsal",s:"genetic"},{w:"lead",m:"yol açmak",s:"cause"},{w:"manner",m:"tarz",s:"way"},{w:"mourn",m:"yas tutmak",s:"grieve"},{w:"orbit",m:"yörünge",s:"circle"},{w:"plentiful",m:"bol",s:"abundant"},{w:"primitive",m:"ilkel",s:"undeveloped"},{w:"scene",m:"sahne",s:"setting"},{w:"scent",m:"koku",s:"smell"},{w:"unmistakably",m:"açıkça/şüphe götürmez şekilde",s:"distinctly"},{w:"utterly",m:"tamamen",s:"completely"},{w:"visible",m:"görünür",s:"apparent"}],12:[{w:"acquainted",m:"aşina",s:"familiar"},{w:"applause",m:"alkış",s:"clapping"},{w:"compensate",m:"telafi etmek",s:"make up for"},{w:"cope",m:"başa çıkmak",s:"manage"},{w:"debut",m:"ilk çıkış",s:"premiere"},{w:"differ",m:"farklılaşmak",s:"vary"},{w:"effective",m:"etkili",s:"efficient"},{w:"faintly",m:"zayıfça",s:"dimly"},{w:"infamous",m:"kötü şöhretli",s:"notorious"},{w:"interrupt",m:"bölmek",s:"disturb"},{w:"mark",m:"işaretlemek",s:"label"},{w:"merrily",m:"neşeyle",s:"happily"},{w:"onset",m:"başlangıç",s:"beginning"},{w:"operate",m:"işletmek",s:"run"},{w:"rumour",m:"söylenti",s:"hearsay"},{w:"strike",m:"vurmak/grev",s:"hit"},{w:"tame",m:"evcil",s:"domesticated"},{w:"tax",m:"vergi",s:"levy"},{w:"transmit",m:"iletmek",s:"send"},{w:"unfavourable",m:"olumsuz",s:"negative"},{w:"assign",m:"atamak",s:"allocate"},{w:"border",m:"sınır",s:"frontier"},{w:"concrete",m:"somut",s:"solid"},{w:"confident",m:"kendine güvenen",s:"sure"},{w:"conform",m:"uymak",s:"comply"},{w:"conventional",m:"geleneksel",s:"traditional"},{w:"discount",m:"indirim",s:"reduction"},{w:"dispose of",m:"kurtulmak",s:"get rid of"},{w:"frank",m:"dobra",s:"honest"},{w:"instinctively",m:"içgüdüsel olarak",s:"intuitively"},{w:"leisurely",m:"acelesizce",s:"unhurriedly"},{w:"match",m:"eşleşmek",s:"correspond"},{w:"misty",m:"puslu",s:"foggy"},{w:"numerous",m:"sayısız",s:"many"},{w:"opportunity",m:"fırsat",s:"chance"},{w:"periodically",m:"periyodik olarak",s:"regularly"},{w:"spark",m:"tetiklemek/kıvılcım",s:"trigger"},{w:"strain",m:"gerginlik",s:"stress"},{w:"trial",m:"deneme",s:"test"},{w:"yield",m:"ürün vermek",s:"produce"}],13:[{w:"advocate",m:"savunmak",s:"defend"},{w:"blossom",m:"çiçek açmak",s:"bloom"},{w:"celestial",m:"göksel",s:"heavenly"},{w:"client",m:"müşteri",s:"customer"},{w:"contest",m:"yarışma",s:"competition"},{w:"elegant",m:"zarif",s:"chic"},{w:"enrich",m:"zenginleştirmek",s:"improve"},{w:"fare",m:"ücret",s:"ticket price"},{w:"finite",m:"sınırlı",s:"limited"},{w:"frantically",m:"çılgınca",s:"crazily"},{w:"impression",m:"izlenim",s:"effect"},{w:"incidentally",m:"bu arada",s:"by the way"},{w:"liberate",m:"özgürleştirmek",s:"set free"},{w:"loathe",m:"nefret etmek",s:"hate"},{w:"massacre",m:"katliam",s:"slaughter"},{w:"medieval",m:"orta çağa ait",s:"Middle Ages"},{w:"oppress",m:"zulmetmek",s:"persecute"},{w:"overt",m:"açık",s:"apparent"},{w:"patriot",m:"vatansever",s:"nationalist"},{w:"royal",m:"kraliyet",s:"regal"},{w:"arrogant",m:"kibirli",s:"conceited"},{w:"complaint",m:"şikayet",s:"grumble"},{w:"convey",m:"iletmek",s:"transmit"},{w:"courageously",m:"cesurca",s:"bravely"},{w:"delight",m:"zevk",s:"joy"},{w:"eminent",m:"seçkin",s:"famous"},{w:"found",m:"kurmak",s:"establish"},{w:"holy",m:"kutsal",s:"sacred"},{w:"intend",m:"niyet etmek",s:"plan"},{w:"limb",m:"uzuv",s:"arm/leg"},{w:"marvel",m:"hayret etmek",s:"be amazed"},{w:"ongoing",m:"devam eden",s:"continuing"},{w:"properly",m:"düzgünce",s:"correctly"},{w:"quote",m:"alıntı",s:"citation"},{w:"restless",m:"huzursuz",s:"uneasy"},{w:"steep",m:"dik",s:"sharp"},{w:"swear",m:"yemin etmek",s:"vow"},{w:"unearth",m:"ortaya çıkarmak",s:"discover"},{w:"vessel",m:"gemi/damar",s:"ship/vein"},{w:"wage",m:"maaş",s:"salary"}],14:[{w:"absorb",m:"emmek",s:"soak up"},{w:"accuse",m:"suçlamak",s:"blame"},{w:"barter",m:"takas",s:"trade"},{w:"comprehensible",m:"anlaşılır",s:"intelligible"},{w:"concisely",m:"kısaca",s:"briefly"},{w:"conquest",m:"fetih",s:"takeover"},{w:"conscious",m:"bilinçli",s:"aware"},{w:"decisively",m:"kararlı şekilde",s:"firmly"},{w:"descend",m:"inmek",s:"go down"},{w:"entrepreneur",m:"girişimci",s:"business person"},{w:"eternal",m:"ebedi",s:"endless"},{w:"famine",m:"kıtlık",s:"starvation"},{w:"gigantic",m:"devasa",s:"huge"},{w:"illustrate",m:"örneklemek",s:"demonstrate"},{w:"landscape",m:"manzara",s:"scenery"},{w:"nutritious",m:"besleyici",s:"nourishing"},{w:"oppose",m:"karşı çıkmak",s:"resist"},{w:"pastoral",m:"kırsal",s:"rural"},{w:"rebel",m:"isyan etmek",s:"revolt"},{w:"settlement",m:"yerleşim",s:"colony"},{w:"assure",m:"garanti etmek",s:"convince"},{w:"credible",m:"inanılır",s:"plausible"},{w:"doubtful",m:"şüpheli",s:"uncertain"},{w:"extinguish",m:"söndürmek",s:"put out"},{w:"funeral",m:"cenaze",s:"burial"},{w:"invalid",m:"geçersiz",s:"void"},{w:"issue",m:"sorun/sayı",s:"matter"},{w:"lively",m:"canlı",s:"energetic"},{w:"moderately",m:"orta derecede/ılımlı şekilde",s:"modestly"},{w:"motion",m:"hareket",s:"movement"},{w:"overlap",m:"örtüşmek",s:"coincide"},{w:"prosperous",m:"zengin",s:"wealthy"},{w:"radically",m:"köklü biçimde",s:"fundamentally"},{w:"roam",m:"dolaşmak",s:"wander"},{w:"roar",m:"kükremek",s:"bellow"},{w:"ruin",m:"harabe",s:"destruction"},{w:"surroundings",m:"çevre",s:"environment"},{w:"summit",m:"zirve",s:"peak"},{w:"unlikely",m:"olası olmayan",s:"improbable"},{w:"yell",m:"bağırmak",s:"shout"}],15:[{w:"accumulate",m:"birikmek",s:"gather"},{w:"admiration",m:"hayranlık",s:"respect"},{w:"adolescence",m:"ergenlik",s:"puberty"},{w:"boastful",m:"övüngen",s:"arrogant"},{w:"boundary",m:"sınır",s:"limit"},{w:"brutal",m:"acımasız",s:"cruel"},{w:"clarify",m:"açıklamak",s:"explain"},{w:"emotion",m:"duygu",s:"feeling"},{w:"guidance",m:"rehberlik",s:"direction"},{w:"illogical",m:"mantıksız",s:"irrational"},{w:"judge",m:"yargılamak",s:"decide"},{w:"loyal",m:"sadık",s:"faithful"},{w:"naturally",m:"doğal olarak",s:"of course"},{w:"obstruct",m:"engellemek",s:"block"},{w:"outrageous",m:"çok kötü/çirkin",s:"shocking"},{w:"presumably",m:"muhtemelen",s:"probably"},{w:"refer",m:"bahsetmek",s:"mention"},{w:"request",m:"istek",s:"demand"},{w:"timid",m:"utangaç",s:"shy"},{w:"trap",m:"tuzak",s:"snare"},{w:"absurd",m:"saçma",s:"ridiculous"},{w:"average",m:"ortalama",s:"normal"},{w:"clue",m:"ipucu",s:"hint"},{w:"dispute",m:"tartışma",s:"argument"},{w:"exceed",m:"aşmak",s:"surpass"},{w:"fade",m:"solmak",s:"vanish"},{w:"float",m:"yüzmek (su üstünde)",s:"drift"},{w:"inheritance",m:"miras",s:"legacy"},{w:"layer",m:"katman",s:"stratum"},{w:"mighty",m:"güçlü",s:"powerful"},{w:"optionally",m:"isteğe bağlı olarak",s:"by choice"},{w:"particle",m:"parçacık",s:"bit"},{w:"portray",m:"betimlemek",s:"depict"},{w:"restore",m:"onarmak",s:"renew"},{w:"superficial",m:"yüzeysel",s:"shallow"},{w:"sustain",m:"sürdürmek",s:"maintain"},{w:"unstable",m:"istikrarsız",s:"unsteady"},{w:"vital",m:"hayati",s:"crucial"},{w:"willingly",m:"isteyerek",s:"gladly"},{w:"zone",m:"bölge",s:"area"}],16:[{w:"accordingly",m:"buna göre",s:"therefore"},{w:"agony",m:"ızdırap",s:"suffering"},{w:"application",m:"başvuru",s:"request"},{w:"coherent",m:"tutarlı",s:"consistent"},{w:"currently",m:"şu anda",s:"presently"},{w:"deadline",m:"son tarih",s:"due date"},{w:"diligent",m:"çalışkan",s:"hard-working"},{w:"embrace",m:"kucaklamak",s:"hug"},{w:"feasible",m:"mümkün",s:"doable"},{w:"impact",m:"etki",s:"effect"},{w:"medium",m:"araç/orta",s:"means"},{w:"neutral",m:"tarafsız",s:"impartial"},{w:"purify",m:"arındırmak",s:"cleanse"},{w:"reckon",m:"sanmak",s:"believe"},{w:"rehearsal",m:"prova",s:"practice"},{w:"rotten",m:"çürük",s:"decayed"},{w:"savage",m:"vahşi",s:"wild"},{w:"skip",m:"atlamak",s:"miss"},{w:"startle",m:"ürkütmek",s:"frighten"},{w:"vandalize",m:"tahrip etmek",s:"damage"},{w:"assume",m:"varsaymak",s:"suppose"},{w:"consent",m:"rıza",s:"agreement"},{w:"destructive",m:"yıkıcı",s:"devastating"},{w:"domestic",m:"evcil/yerel",s:"household"},{w:"feature",m:"özellik",s:"characteristic"},{w:"gear",m:"vites/ekipman",s:"equipment"},{w:"innate",m:"doğuştan",s:"inborn"},{w:"merge",m:"birleşmek",s:"unite"},{w:"overlook",m:"gözden kaçırmak",s:"miss"},{w:"pesticide",m:"böcek ilacı",s:"insecticide"},{w:"remote",m:"uzak",s:"distant"},{w:"remarkable",m:"dikkat çekici",s:"extraordinary"},{w:"soar",m:"fırlamak",s:"rise high"},{w:"spy",m:"casus",s:"agent"},{w:"supervise",m:"denetlemek",s:"oversee"},{w:"temporary",m:"geçici",s:"provisional"},{w:"terminate",m:"sonlandırmak",s:"end"},{w:"ultimately",m:"sonuçta",s:"finally"},{w:"vastly",m:"büyük ölçüde",s:"immensely"},{w:"will",m:"irade",s:"determination"}],
    17:[{w:"accountable",m:"sorumlu",s:"responsible"},{w:"anonymously",m:"isimsiz olarak",s:"namelessly"},{w:"bargain",m:"kelepir",s:"deal"},{w:"circulate",m:"dolaşmak",s:"flow"},{w:"comprise",m:"oluşmak",s:"consist of"},{w:"detect",m:"tespit etmek",s:"find"},{w:"groundless",m:"asılsız",s:"baseless"},{w:"hectic",m:"yoğun/telaşlı",s:"busy"},{w:"ingredient",m:"malzeme",s:"component"},{w:"landmark",m:"dönüm noktası",s:"milestone"},{w:"literary",m:"edebi",s:"written"},{w:"misbehave",m:"yaramazlık yapmak",s:"act badly"},{w:"noble",m:"soylu",s:"aristocratic"},{w:"outline",m:"özetlemek",s:"summarize"},{w:"potent",m:"güçlü",s:"powerful"},{w:"pride",m:"gurur",s:"self-respect"},{w:"quarrel",m:"tartışma",s:"argument"},{w:"ripe",m:"olgun",s:"mature"},{w:"routinely",m:"düzenli olarak",s:"regularly"},{w:"sweep",m:"süpürmek",s:"clean"},{w:"article",m:"makale",s:"piece"},{w:"cease",m:"durdurmak",s:"stop"},{w:"compelling",m:"ilgi uyandıran",s:"engaging"},{w:"distinctively",m:"belirgin şekilde",s:"characteristically"},{w:"exaggerate",m:"abartmak",s:"overstate"},{w:"fabric",m:"kumaş",s:"cloth"},{w:"formal",m:"resmi",s:"official"},{w:"humble",m:"alçakgönüllü",s:"modest"},{w:"influential",m:"etkili",s:"powerful"},{w:"irrigate",m:"sulamak",s:"water"},{w:"notorious",m:"adı çıkmış",s:"infamous"},{w:"present",m:"sunmak",s:"give"},{w:"privilege",m:"ayrıcalık",s:"advantage"},{w:"refugee",m:"mülteci",s:"exile"},{w:"restrain",m:"dizginlemek",s:"control"},{w:"sanity",m:"akıl sağlığı",s:"mental health"},{w:"solemnly",m:"ciddiyetle",s:"seriously"},{w:"stiff",m:"kaskatı",s:"rigid"},{w:"surrender",m:"teslim olmak",s:"give in"},{w:"tip",m:"bahşiş/ipucu",s:"gratuity"}],
    18:[{w:"address",m:"hitap/çözmek",s:"deal with"},{w:"appliance",m:"ev aleti",s:"device"},{w:"betray",m:"ihanet etmek",s:"deceive"},{w:"central",m:"merkezi",s:"middle"},{w:"cunning",m:"kurnaz",s:"sly"},{w:"dawn",m:"şafak",s:"daybreak"},{w:"deliver",m:"teslim etmek/dağıtmak",s:"distribute"},{w:"drought",m:"kuraklık",s:"dryness"},{w:"figurative",m:"mecazi",s:"metaphorical"},{w:"fulfil",m:"yerine getirmek",s:"complete"},{w:"handy",m:"kullanışlı",s:"useful"},{w:"imply",m:"ima etmek",s:"suggest"},{w:"innovation",m:"yenilik",s:"invention"},{w:"mentally",m:"zihinsel olarak",s:"psychologically"},{w:"monument",m:"anıt",s:"memorial"},{w:"obsessive",m:"takıntılı",s:"compulsive"},{w:"owe",m:"borçlu olmak",s:"be in debt"},{w:"preferably",m:"tercihen",s:"ideally"},{w:"staple",m:"temel",s:"main"},{w:"territory",m:"bölge",s:"area"},{w:"absolute",m:"mutlak",s:"total"},{w:"abuse",m:"istismar/kötüye kullanmak",s:"mistreat"},{w:"catastrophe",m:"felaket",s:"disaster"},{w:"corrupt",m:"yozlaşmış",s:"dishonest"},{w:"curious",m:"meraklı",s:"inquisitive"},{w:"dealer",m:"satıcı",s:"trader"},{w:"deforestation",m:"ormansızlaşma",s:"clearing"},{w:"display",m:"sergilemek",s:"show"},{w:"dormant",m:"uykuda",s:"inactive"},{w:"explode",m:"patlamak",s:"blow up"},{w:"exploration",m:"keşif",s:"investigation"},{w:"fabricate",m:"uydurmak/üretmek",s:"invent"},{w:"glow",m:"parlamak",s:"shine"},{w:"humiliate",m:"aşağılamak",s:"embarrass"},{w:"nuisance",m:"dert/sıkıntı",s:"annoyance"},{w:"predictable",m:"öngörülebilir",s:"expected"},{w:"promptly",m:"derhal",s:"immediately"},{w:"radiant",m:"parlak",s:"shining"},{w:"sharply",m:"keskin bir şekilde",s:"abruptly"},{w:"torture",m:"işkence",s:"torment"}],
    19:[{w:"ailment",m:"rahatsızlık",s:"illness"},{w:"assemble",m:"toplamak",s:"gather"},{w:"blackmail",m:"şantaj",s:"extortion"},{w:"consequently",m:"sonuç olarak",s:"therefore"},{w:"damp",m:"nemli",s:"moist"},{w:"defy",m:"karşı gelmek",s:"resist"},{w:"disruptive",m:"yıkıcı",s:"disturbing"},{w:"emission",m:"yayılım",s:"discharge"},{w:"extravagant",m:"savurgan",s:"wasteful"},{w:"giggle",m:"kıkırdamak",s:"laugh"},{w:"inquiry",m:"soruşturma",s:"investigation"},{w:"proceed",m:"ilerlemek",s:"continue"},{w:"record",m:"kaydetmek",s:"log"},{w:"robust",m:"sağlam",s:"strong"},{w:"spare",m:"yedek",s:"extra"},{w:"stuff",m:"şeyler",s:"things"},{w:"tomb",m:"mezar",s:"grave"},{w:"treasure",m:"hazine",s:"riches"},{w:"underestimate",m:"küçümsemek",s:"undervalue"},{w:"unfairly",m:"haksızca",s:"unjustly"},{w:"alien",m:"yabancı/uzaylı",s:"foreigner"},{w:"attach",m:"iliştirmek",s:"fasten"},{w:"coincidentally",m:"tesadüfen",s:"accidentally"},{w:"concern",m:"endişe",s:"worry"},{w:"costly",m:"pahalı",s:"expensive"},{w:"craft",m:"zanaat",s:"skill"},{w:"crawl",m:"emeklemek",s:"creep"},{w:"devoid",m:"yoksun",s:"lacking"},{w:"extract",m:"çıkarmak",s:"remove"},{w:"gloomy",m:"kasvetli",s:"dark"},{w:"ignorance",m:"cehalet",s:"unawareness"},{w:"inspection",m:"denetim",s:"examination"},{w:"label",m:"etiketlemek",s:"tag"},{w:"nod",m:"başını sallamak/onaylamak",s:"gesture"},{w:"overall",m:"genel",s:"general"},{w:"regard",m:"saygı/bakım",s:"respect"},{w:"sentimentally",m:"duygusalca",s:"emotionally"},{w:"spontaneous",m:"kendiliğinden",s:"unplanned"},{w:"substitute",m:"yedek",s:"replacement"},{w:"uneasy",m:"huzursuz",s:"anxious"}],
    20:[{w:"assimilate",m:"özümsemek",s:"absorb"},{w:"attentively",m:"dikkatle",s:"carefully"},{w:"charity",m:"hayır kurumu",s:"aid"},{w:"detrimental",m:"zararlı",s:"harmful"},{w:"divert",m:"saptırmak",s:"redirect"},{w:"elderly",m:"yaşlı",s:"old"},{w:"exhaust",m:"tüketmek",s:"deplete"},{w:"flame",m:"alev",s:"fire"},{w:"fond",m:"düşkün",s:"keen"},{w:"greasy",m:"yağlı",s:"oily"},{w:"hatred",m:"nefret",s:"hate"},{w:"lure",m:"cezbetmek",s:"tempt"},{w:"reputation",m:"itibar",s:"fame"},{w:"reward",m:"ödül",s:"prize"},{w:"spin",m:"dönmek",s:"rotate"},{w:"stationary",m:"sabit",s:"fixed"},{w:"temptation",m:"baştan çıkma",s:"desire"},{w:"tranquil",m:"huzurlu",s:"calm"},{w:"truly",m:"gerçekten",s:"really"},{w:"verdict",m:"karar",s:"judgment"},{w:"ardently",m:"şevkle",s:"passionately"},{w:"choke",m:"boğulmak",s:"suffocate"},{w:"complicated",m:"karmaşık",s:"complex"},{w:"conduct",m:"yürütmek",s:"carry out"},{w:"differentiate",m:"ayırt etmek",s:"distinguish"},{w:"idle",m:"boş/aylak",s:"lazy"},{w:"intellectual",m:"entelektüel",s:"smart"},{w:"manuscript",m:"el yazması",s:"document"},{w:"modification",m:"değişiklik",s:"alteration"},{w:"penalty",m:"ceza",s:"punishment"},{w:"progressive",m:"ilerici",s:"advanced"},{w:"repetitive",m:"tekrarlayan",s:"monotonous"},{w:"resume",m:"devam etmek/yeniden başlamak",s:"continue"},{w:"revenue",m:"gelir",s:"income"},{w:"scale",m:"ölçek",s:"extent"},{w:"shrink",m:"küçülmek",s:"reduce"},{w:"spot",m:"fark etmek",s:"detect"},{w:"stamina",m:"dayanıklılık",s:"endurance"},{w:"utter",m:"söylemek",s:"speak"},{w:"watchfully",m:"dikkatle",s:"vigilantly"}],
    21:[{w:"affectionately",m:"sevgiyle",s:"lovingly"},{w:"ally",m:"müttefik",s:"partner"},{w:"assist",m:"yardım etmek",s:"help"},{w:"bet",m:"bahis",s:"gamble"},{w:"breakdown",m:"arıza/çöküş",s:"failure"},{w:"customary",m:"geleneksel",s:"traditional"},{w:"disagreeable",m:"hoşa gitmeyen",s:"unpleasant"},{w:"drawback",m:"dezavantaj",s:"disadvantage"},{w:"enlighten",m:"aydınlatmak",s:"inform"},{w:"exploit",m:"kullanmak/sömürmek",s:"utilize"},{w:"frustration",m:"hayal kırıklığı",s:"disappointment"},{w:"industrious",m:"çalışkan",s:"hard-working"},{w:"insure",m:"sigortalamak",s:"cover"},{w:"lonesome",m:"yapayalnız",s:"lonely"},{w:"mean",m:"cimri/kaba",s:"unkind"},{w:"post",m:"tayin etmek",s:"assign"},{w:"quantity",m:"miktar",s:"amount"},{w:"seek",m:"aramak",s:"search for"},{w:"unintentionally",m:"kazara",s:"accidentally"},{w:"vibrant",m:"canlı",s:"lively"},{w:"animate",m:"canlı",s:"living"},{w:"comment",m:"yorum",s:"remark"},{w:"confront",m:"yüzleşmek",s:"face"},{w:"deceptively",m:"aldatıcı biçimde",s:"misleadingly"},{w:"dissatisfied",m:"memnuniyetsiz",s:"unhappy"},{w:"evolve",m:"evrimleşmek",s:"develop"},{w:"forthcoming",m:"yaklaşan",s:"approaching"},{w:"inhale",m:"nefes almak",s:"breathe in"},{w:"irritate",m:"rahatsız etmek",s:"annoy"},{w:"manifest",m:"göstermek",s:"display"},{w:"merit",m:"liyakat",s:"worth"},{w:"plague",m:"veba/bela",s:"disease"},{w:"principle",m:"ilke",s:"rule"},{w:"resentful",m:"alıngan",s:"bitter"},{w:"rugged",m:"engebeli",s:"rough"},{w:"scheme",m:"tasarı",s:"plan"},{w:"state",m:"belirtmek",s:"declare"},{w:"threshold",m:"eşik",s:"limit"},{w:"unquestionably",m:"şüphesiz",s:"undoubtedly"},{w:"verbal",m:"sözlü",s:"oral"}],
    22:[{w:"adhesive",m:"yapışkan",s:"sticky"},{w:"ascend",m:"yükselmek",s:"climb"},{w:"contented",m:"memnun",s:"satisfied"},{w:"conversely",m:"aksine",s:"contrarily"},{w:"evaporation",m:"buharlaşma",s:"vaporization"},{w:"erect",m:"dikmek",s:"build"},{w:"harshly",m:"sertçe",s:"severely"},{w:"insert",m:"yerleştirmek",s:"put in"},{w:"magnitude",m:"büyüklük",s:"size"},{w:"moist",m:"nemli",s:"damp"},{w:"network",m:"ağ",s:"system"},{w:"oblige",m:"zorunda bırakmak",s:"force"},{w:"poll",m:"anket",s:"survey"},{w:"register",m:"kaydetmek",s:"record"},{w:"relevant",m:"ilgili",s:"related"},{w:"residence",m:"konut",s:"home"},{w:"sacrifice",m:"feda etmek",s:"give up"},{w:"setback",m:"aksilik",s:"problem"},{w:"unique",m:"eşsiz",s:"distinct"},{w:"viable",m:"uygulanabilir",s:"feasible"},{w:"acutely",m:"şiddetle",s:"intensely"},{w:"anticipate",m:"ummak",s:"expect"},{w:"aptitude",m:"yetenek",s:"talent"},{w:"aspire",m:"arzulamak",s:"desire"},{w:"awkward",m:"garip",s:"clumsy"},{w:"bias",m:"ön yargı",s:"prejudice"},{w:"contagious",m:"bulaşıcı",s:"infectious"},{w:"cooperative",m:"işbirlikçi",s:"helpful"},{w:"disability",m:"engellilik",s:"handicap"},{w:"escalate",m:"tırmanmak",s:"increase"},{w:"establishment",m:"kuruluş",s:"institution"},{w:"foremost",m:"önde gelen",s:"leading"},{w:"grant",m:"vermek",s:"allow"},{w:"harvest",m:"hasat",s:"crop"},{w:"initiate",m:"başlatmak",s:"start"},{w:"legitimate",m:"meşru",s:"legal"},{w:"misfortune",m:"talihsizlik",s:"bad luck"},{w:"pact",m:"antlaşma",s:"treaty"},{w:"seemingly",m:"görünüşte",s:"apparently"},{w:"vigorous",m:"güçlü",s:"energetic"}],
    23:[{w:"absorbing",m:"ilgi çekici",s:"gripping"},{w:"alter",m:"değiştirmek",s:"change"},{w:"announcement",m:"duyuru",s:"statement"},{w:"banish",m:"sürgün etmek",s:"exile"},{w:"blank",m:"boş",s:"empty"},{w:"consistent",m:"tutarlı",s:"steady"},{w:"erroneously",m:"hatalı olarak",s:"incorrectly"},{w:"harbour",m:"liman/barındırmak",s:"shelter"},{w:"incline",m:"eğilimi olmak",s:"tend"},{w:"legible",m:"okunaklı",s:"readable"},{w:"mount",m:"binmek/artmak",s:"climb"},{w:"pity",m:"acıma",s:"mercy"},{w:"recreation",m:"eğlence",s:"leisure"},{w:"succeed",m:"başarmak",s:"achieve"},{w:"suffocate",m:"boğulmak",s:"choke"},{w:"transparent",m:"şeffaf",s:"clear"},{w:"unforgivable",m:"affedilemez",s:"inexcusable"},{w:"unrest",m:"kargaşa",s:"turmoil"},{w:"vegetation",m:"bitki örtüsü",s:"plants"},{w:"violently",m:"şiddetle",s:"fiercely"},{w:"aggravate",m:"kötüleştirmek",s:"worsen"},{w:"ambiguous",m:"belirsiz",s:"vague"},{w:"arduous",m:"çetin",s:"difficult"},{w:"beam",m:"ışın/gülümseme",s:"ray/smile"},{w:"bond",m:"bağ",s:"connection"},{w:"cast",m:"fırlatmak/rol vermek",s:"throw"},{w:"clergy",m:"ruhban sınıfı",s:"priesthood"},{w:"commute",m:"gidip gelmek",s:"travel"},{w:"contemporary",m:"çağdaş",s:"modern"},{w:"detest",m:"tiksinmek",s:"hate"},{w:"fluently",m:"akıcı biçimde",s:"smoothly"},{w:"misinterpret",m:"yanlış yorumlamak",s:"misunderstand"},{w:"nomination",m:"adaylık",s:"candidacy"},{w:"parade",m:"geçit töreni",s:"procession"},{w:"receptive",m:"açık (fikirli)",s:"open"},{w:"secular",m:"laik",s:"worldly"},{w:"treaty",m:"antlaşma",s:"agreement"},{w:"uneven",m:"düzensiz",s:"irregular"},{w:"verify",m:"doğrulamak",s:"confirm"},{w:"visually",m:"görsel olarak",s:"optically"}],
    24:[{w:"basically",m:"temelde",s:"essentially"},{w:"contradiction",m:"çelişki",s:"conflict"},{w:"courteous",m:"kibar",s:"polite"},{w:"endurance",m:"dayanıklılık",s:"stamina"},{w:"evaluate",m:"değerlendirmek",s:"assess"},{w:"heritage",m:"miras",s:"legacy"},{w:"memorable",m:"unutulmaz",s:"unforgettable"},{w:"narrative",m:"hikaye",s:"story"},{w:"perish",m:"yok olmak",s:"die"},{w:"plausible",m:"akla yatkın",s:"reasonable"},{w:"redundant",m:"gereksiz",s:"unnecessary"},{w:"repulse",m:"püskürtmek",s:"reject"},{w:"seize",m:"ele geçirmek",s:"grab"},{w:"solidarity",m:"dayanışma",s:"unity"},{w:"straightforward",m:"açık/basit",s:"simple"},{w:"temper",m:"ruh hali",s:"mood"},{w:"trace",m:"izini sürmek",s:"track"},{w:"undoubtedly",m:"şüphesiz",s:"certainly"},{w:"unify",m:"birleştirmek",s:"unite"},{w:"vulnerable",m:"savunmasız",s:"weak"},{w:"acclaim",m:"övmek",s:"praise"},{w:"arbitrary",m:"keyfi",s:"random"},{w:"arouse",m:"uyandırmak",s:"awaken"},{w:"artificial",m:"yapay",s:"synthetic"},{w:"beast",m:"canavar",s:"monster"},{w:"boom",m:"patlama/artış",s:"growth"},{w:"censorship",m:"sansür",s:"restriction"},{w:"colloquially",m:"konuşma dilinde",s:"informally"},{w:"confess",m:"itiraf etmek",s:"admit"},{w:"deed",m:"eylem",s:"act"},{w:"enhance",m:"geliştirmek",s:"improve"},{w:"invaluable",m:"paha biçilmez",s:"priceless"},{w:"minute",m:"ufak",s:"tiny"},{w:"patrol",m:"devriye gezmek",s:"guard"},{w:"prospect",m:"olasılık",s:"possibility"},{w:"realm",m:"alem/alan",s:"kingdom"},{w:"respectively",m:"sırasıyla",s:"in order"},{w:"slaughter",m:"katletmek",s:"kill"},{w:"virtuous",m:"erdemli",s:"moral"},{w:"worthy",m:"değerli/layık",s:"deserving"}],
    25:[{w:"adore",m:"tapmak",s:"love"},{w:"alike",m:"benzer",s:"similar"},{w:"augment",m:"artırmak",s:"increase"},{w:"bruise",m:"çürük",s:"contusion"},{w:"commerce",m:"ticaret",s:"trade"},{w:"commonplace",m:"sıradan",s:"ordinary"},{w:"conditionally",m:"şartlı olarak",s:"provisionally"},{w:"crack",m:"çatlak",s:"split"},{w:"despair",m:"umutsuzluk",s:"misery"},{w:"eradicate",m:"kökünü kazımak",s:"eliminate"},{w:"immortal",m:"ölümsüz",s:"eternal"},{w:"intimate",m:"samimi",s:"close"},{w:"intrude",m:"izinsiz girmek",s:"invade"},{w:"neat",m:"düzenli",s:"tidy"},{w:"obscure",m:"belirsiz",s:"vague"},{w:"plead",m:"yalvarmak",s:"beg"},{w:"prohibit",m:"yasaklamak",s:"ban"},{w:"rage",m:"öfke",s:"anger"},{w:"revival",m:"canlanma",s:"rebirth"},{w:"spacious",m:"geniş",s:"roomy"},{w:"allocate",m:"tahsis etmek",s:"assign"},{w:"apprehend",m:"yakalamak/anlamak",s:"arrest"},{w:"bizarre",m:"tuhaf",s:"weird"},{w:"dilemma",m:"ikilem",s:"predicament"},{w:"excessively",m:"aşırı derecede",s:"too much"},{w:"exempt",m:"muaf",s:"free from"},{w:"flee",m:"kaçmak",s:"escape"},{w:"forgery",m:"sahtecilik",s:"falsification"},{w:"glitter",m:"parıldamak",s:"sparkle"},{w:"inconvenience",m:"zahmet",s:"trouble"},{w:"meticulous",m:"titiz",s:"careful"},{w:"multiple",m:"çoklu",s:"numerous"},{w:"optimal",m:"en uygun",s:"best"},{w:"overthrow",m:"devirmek",s:"topple"},{w:"proportion",m:"oran",s:"ratio"},{w:"remedy",m:"çare",s:"cure"},{w:"ritual",m:"ayin",s:"ceremony"},{w:"shiver",m:"titremek",s:"tremble"},{w:"strictly",m:"katı bir şekilde",s:"rigidly"},{w:"striking",m:"çarpıcı",s:"impressive"}],
    26:[{w:"acquire",m:"edinmek",s:"gain"},{w:"anguish",m:"ızdırap",s:"suffering"},{w:"apparently",m:"görünüşe göre",s:"evidently"},{w:"attribute",m:"atfetmek",s:"ascribe"},{w:"benign",m:"iyi huylu",s:"kind/harmless"},{w:"brand",m:"marka",s:"make"},{w:"commemorate",m:"anmak",s:"honour"},{w:"compassion",m:"şefkat",s:"sympathy"},{w:"cultivation",m:"tarım",s:"farming"},{w:"entail",m:"gerektirmek",s:"involve"},{w:"equivalent",m:"eşdeğer",s:"equal"},{w:"hideously",m:"iğrenç bir şekilde",s:"horribly"},{w:"intrinsic",m:"içsel",s:"inherent"},{w:"merchandise",m:"ticari eşya",s:"goods"},{w:"notion",m:"kavram",s:"idea"},{w:"peak",m:"zirve",s:"top"},{w:"provisional",m:"geçici",s:"temporary"},{w:"reasonable",m:"makul",s:"sensible"},{w:"refute",m:"çürütmek",s:"disprove"},{w:"sophisticated",m:"gelişmiş",s:"advanced"},{w:"breezy",m:"esintili",s:"windy"},{w:"bulk",m:"yığın",s:"mass"},{w:"conserve",m:"korumak",s:"save"},{w:"consistently",m:"tutarlı şekilde",s:"constantly"},{w:"dazzle",m:"göz kamaştırmak",s:"amaze"},{w:"debris",m:"enkaz",s:"rubble"},{w:"dependable",m:"güvenilir",s:"reliable"},{w:"explicit",m:"açık",s:"clear"},{w:"fruitful",m:"verimli",s:"productive"},{w:"implement",m:"uygulamak",s:"execute"},{w:"manipulate",m:"yönlendirmek",s:"control"},{w:"paramount",m:"en önemli",s:"supreme"},{w:"rank",m:"rütbe",s:"status"},{w:"sigh",m:"iç çekmek",s:"breathe out"},{w:"snack",m:"atıştırmalık",s:"bite"},{w:"splendid",m:"muhteşem",s:"magnificent"},{w:"tissue",m:"doku",s:"body material"},{w:"tentatively",m:"tereddütle/geçici olarak",s:"hesitantly"},{w:"warehouse",m:"depo",s:"storehouse"},{w:"wrap",m:"sarmak",s:"cover"}],
    27:[{w:"accessible",m:"erişilebilir",s:"reachable"},{w:"board",m:"binmek",s:"get on"},{w:"brink",m:"eşik",s:"verge"},{w:"clash",m:"çatışma",s:"conflict"},{w:"conceive",m:"tasarlamak",s:"imagine"},{w:"constitute",m:"oluşturmak",s:"form"},{w:"convincingly",m:"ikna edici şekilde",s:"persuasively"},{w:"disorderly",m:"düzensiz",s:"untidy"},{w:"erosion",m:"erozyon",s:"wearing away"},{w:"fanciful",m:"hayali",s:"imaginary"},{w:"grave",m:"ciddi/mezar",s:"serious"},{w:"hijack",m:"kaçırmak (uçak)",s:"seize"},{w:"indispensable",m:"vazgeçilmez",s:"essential"},{w:"legislation",m:"mevzuat",s:"law"},{w:"mildly",m:"hafifçe/nazikçe",s:"gently"},{w:"minority",m:"azınlık",s:"smaller group"},{w:"outskirts",m:"kenar mahalle",s:"suburbs"},{w:"persevere",m:"azmetmek",s:"persist"},{w:"remind",m:"hatırlatmak",s:"prompt"},{w:"sensible",m:"mantıklı",s:"reasonable"},{w:"bare",m:"çıplak",s:"naked"},{w:"disposition",m:"mizaç",s:"character"},{w:"evict",m:"tahliye etmek",s:"kick out"},{w:"forceful",m:"güçlü",s:"powerful"},{w:"gaze",m:"dik dik bakmak",s:"stare"},{w:"indeed",m:"gerçekten",s:"actually"},{w:"interfere",m:"müdahale etmek",s:"meddle"},{w:"prejudice",m:"ön yargı",s:"bias"},{w:"regulation",m:"düzenleme",s:"rule"},{w:"reminiscent",m:"hatırlatan",s:"evocative"},{w:"representative",m:"temsilci",s:"delegate"},{w:"retreat",m:"geri çekilmek",s:"withdraw"},{w:"revise",m:"gözden geçirmek",s:"review"},{w:"rhyme",m:"kafiye/uyak",s:"end sound"},{w:"suppress",m:"bastırmak",s:"repress"},{w:"theme",m:"tema",s:"subject"},{w:"triumph",m:"zafer",s:"victory"},{w:"unanimous",m:"oy birliğiyle",s:"united"},{w:"vehemently",m:"şiddetle",s:"intensely"},{w:"weary",m:"yorgun",s:"tired"}],
    28:[{w:"blizzard",m:"tipi",s:"snowstorm"},{w:"blush",m:"kızarmak",s:"flush"},{w:"captivate",m:"büyülemek",s:"charm"},{w:"coward",m:"korkak",s:"chicken"},{w:"delicate",m:"hassas",s:"fragile"},{w:"despise",m:"küçümsemek",s:"scorn"},{w:"distort",m:"saptırmak",s:"warp"},{w:"earnestly",m:"ciddiyetle",s:"seriously"},{w:"entity",m:"varlık",s:"being"},{w:"expire",m:"süresi dolmak",s:"end"},{w:"fracture",m:"kırık",s:"break"},{w:"horizontal",m:"yatay",s:"flat"},{w:"implicit",m:"ima edilen",s:"implied"},{w:"infectious",m:"bulaşıcı",s:"contagious"},{w:"integrity",m:"bütünlük/dürüstlük",s:"honesty"},{w:"overhear",m:"kulak misafiri olmak",s:"hear accidentally"},{w:"perplexing",m:"kafa karıştırıcı",s:"confusing"},{w:"perception",m:"algı",s:"view"},{w:"previously",m:"önceden",s:"before"},{w:"reign",m:"hüküm sürmek",s:"rule"},{w:"apt",m:"uygun",s:"suitable"},{w:"contrary",m:"karşıt",s:"opposite"},{w:"elapse",m:"geçmek (zaman)",s:"pass"},{w:"genocide",m:"soykırım",s:"massacre"},{w:"hysterically",m:"çılgınca",s:"wildly"},{w:"intuition",m:"sezgi",s:"instinct"},{w:"limp",m:"topallamak",s:"hobble"},{w:"moody",m:"huysuz",s:"temperamental"},{w:"nomadic",m:"göçebe",s:"wandering"},{w:"pioneer",m:"öncü",s:"trailblazer"},{w:"precede",m:"önce gelmek",s:"come before"},{w:"recite",m:"ezberden okumak",s:"repeat"},{w:"regrettably",m:"ne yazık ki",s:"sadly"},{w:"scratch",m:"kaşımak/çizmek",s:"scrape"},{w:"staggering",m:"şaşırtıcı",s:"astounding"},{w:"standstill",m:"duraklama",s:"halt"},{w:"sufficient",m:"yeterli",s:"enough"},{w:"summon",m:"çağırmak",s:"call"},{w:"tutor",m:"özel hoca",s:"teacher"},{w:"twist",m:"bükmek",s:"turn"}],
    29:[{w:"boost",m:"artırmak",s:"enhance"},{w:"confidential",m:"gizli",s:"secret"},{w:"eccentric",m:"eksantrik",s:"odd"},{w:"fascination",m:"büyülenme",s:"attraction"},{w:"foster",m:"teşvik etmek",s:"promote"},{w:"harness",m:"kullanmak",s:"utilize"},{w:"intrigue",m:"ilgisini çekmek",s:"fascinate"},{w:"juvenile",m:"çocuksu",s:"youthful"},{w:"longevity",m:"uzun ömür",s:"long life"},{w:"mischievously",m:"yaramazca",s:"naughtily"},{w:"offspring",m:"yavru",s:"children"},{w:"posture",m:"duruş",s:"stance"},{w:"prolong",m:"uzatmak",s:"extend"},{w:"revolt",m:"isyan",s:"rebellion"},{w:"specific",m:"belirli",s:"particular"},{w:"stretch",m:"esnemek",s:"extend"},{w:"successively",m:"ardışık olarak/peş peşe",s:"consecutively"},{w:"tender",m:"nazik",s:"gentle"},{w:"threatening",m:"tehditkar",s:"menacing"},{w:"venture",m:"girişim",s:"project"},{w:"bachelor",m:"bekar",s:"single"},{w:"cling",m:"tutunmak",s:"hold on"},{w:"command",m:"emretmek",s:"order"},{w:"component",m:"bileşen",s:"part"},{w:"conceited",m:"kibirli",s:"arrogant"},{w:"disqualify",m:"diskalifiye etmek",s:"exclude"},{w:"drastically",m:"köklü biçimde",s:"severely"},{w:"exceptional",m:"olağanüstü",s:"outstanding"},{w:"farewell",m:"veda",s:"goodbye"},{w:"focus",m:"odak",s:"center"},{w:"ingenious",m:"dahice",s:"clever"},{w:"interior",m:"iç",s:"inside"},{w:"irresistible",m:"dayanılmaz",s:"compelling"},{w:"licence",m:"lisans",s:"permit"},{w:"overpower",m:"etkisiz hale getirmek",s:"overwhelm"},{w:"pitifully",m:"acınacak şekilde",s:"sadly"},{w:"poverty",m:"yoksulluk",s:"poorness"},{w:"reinforce",m:"güçlendirmek",s:"strengthen"},{w:"resort",m:"başvurmak",s:"turn to"},{w:"sour",m:"ekşi",s:"acidic"}],
    30:[{w:"adherent",m:"taraftar",s:"follower"},{w:"alternatively",m:"alternatif olarak",s:"instead"},{w:"bind",m:"bağlamak",s:"tie"},{w:"cherish",m:"değer vermek",s:"treasure"},{w:"contrast",m:"zıtlık",s:"difference"},{w:"drift",m:"sürüklenmek",s:"float"},{w:"enclose",m:"çevrelemek",s:"surround"},{w:"factual",m:"gerçekçi",s:"real"},{w:"intensive",m:"yoğun",s:"concentrated"},{w:"lavish",m:"savurgan/bol",s:"extravagant"},{w:"maturity",m:"olgunluk",s:"adulthood"},{w:"misconception",m:"yanlış kanı",s:"mistake"},{w:"nurture",m:"beslemek",s:"care for"},{w:"overdue",m:"vadesi geçmiş",s:"late"},{w:"ponder",m:"düşünmek",s:"contemplate"},{w:"preventive",m:"önleyici",s:"precautionary"},{w:"priority",m:"öncelik",s:"precedence"},{w:"scarcely",m:"neredeyse hiç",s:"hardly"},{w:"sensation",m:"his/duyum",s:"feeling"},{w:"slender",m:"ince",s:"slim"},{w:"abusive",m:"kaba/saldırgan",s:"offensive"},{w:"approximately",m:"yaklaşık",s:"roughly"},{w:"autonomous",m:"özerk",s:"independent"},{w:"curriculum",m:"müfredat",s:"syllabus"},{w:"domain",m:"alan",s:"field"},{w:"dwell",m:"ikamet etmek",s:"live"},{w:"empirical",m:"deneysel/gözleme dayalı",s:"observational"},{w:"engross",m:"kendini kaptırmak",s:"absorb"},{w:"exhale",m:"nefes vermek",s:"breathe out"},{w:"exhibition",m:"sergi",s:"show"},{w:"facility",m:"tesis",s:"amenity"},{w:"impose",m:"dayatmak",s:"force"},{w:"inclusive",m:"kapsayıcı",s:"comprehensive"},{w:"longingly",m:"özlemle",s:"yearningly"},{w:"marine",m:"denizle ilgili",s:"nautical"},{w:"naive",m:"saf",s:"innocent"},{w:"scholar",m:"bilgin",s:"academic"},{w:"settle",m:"yerleşmek/çözmek",s:"resolve"},{w:"speculate",m:"tahmin yürütmek",s:"guess"},{w:"transition",m:"geçiş",s:"change"}]};

const phrasalData={1:[{w:"account for",m:"karşılamak/açıklamak",s:"form/explain"},{w:"answer back",m:"kaba cevap vermek",s:"reply rudely"},{w:"ask out",m:"çıkma teklif etmek",s:"invite out"},{w:"ask for",m:"istemek",s:"request"},{w:"back up",m:"desteklemek",s:"support"},{w:"beat up",m:"dövmek",s:"hit hard"},{w:"believe in",m:"inanmak",s:"trust"},{w:"blow up",m:"patlamak/şişirmek",s:"explode"},{w:"blow out",m:"söndürmek",s:"extinguish"},{w:"break away",m:"kaçmak",s:"escape"},{w:"break down",m:"bozulmak",s:"stop working"},{w:"break in",m:"zorla girmek",s:"intrude"},{w:"break off",m:"bitirmek (ilişki)",s:"end"},{w:"break out",m:"patlak vermek",s:"start suddenly"},{w:"break up",m:"ayrılmak",s:"split"},{w:"bring about",m:"neden olmak",s:"cause"},{w:"bring back",m:"geri getirmek",s:"return"},{w:"bring up",m:"yetiştirmek",s:"raise"},{w:"build up",m:"geliştirmek",s:"develop"},{w:"bump into",m:"karşılaşmak",s:"meet by chance"}],2:[{w:"burst into",m:"aniden başlamak",s:"start suddenly"},{w:"call for",m:"talep etmek",s:"require"},{w:"call off",m:"iptal etmek",s:"cancel"},{w:"calm down",m:"sakinleşmek",s:"relax"},{w:"care for",m:"bakmak",s:"look after"},{w:"carry on",m:"devam etmek",s:"continue"},{w:"carry out",m:"uygulamak",s:"perform"},{w:"catch up",m:"yetişmek",s:"reach"},{w:"check in",m:"giriş yapmak",s:"register"},{w:"check out",m:"çıkış yapmak",s:"leave"},{w:"clear up",m:"temizlemek/açıklamak",s:"tidy"},{w:"come across",m:"karşılaşmak",s:"find"},{w:"come apart",m:"parçalanmak",s:"break"},{w:"come around",m:"uğramak",s:"visit"},{w:"come down with",m:"hastalanmak",s:"get ill"},{w:"come out",m:"ortaya çıkmak",s:"appear"},{w:"come up",m:"meydana gelmek",s:"happen"},{w:"come up with",m:"bulmak (fikir)",s:"create"},{w:"count in",m:"dahil etmek",s:"include"},{w:"count on",m:"güvenmek",s:"rely on"}],3:[{w:"cross out",m:"üstünü çizmek",s:"delete"},{w:"cut down on",m:"azaltmak",s:"reduce"},{w:"cut off",m:"kesmek",s:"disconnect"},{w:"deal with",m:"başa çıkmak",s:"handle"},{w:"die out",m:"yok olmak",s:"become extinct"},{w:"draw back",m:"geri çekilmek",s:"retreat"},{w:"dress up",m:"giyinmek",s:"wear formal"},{w:"drop by",m:"uğramak",s:"visit"},{w:"drop out",m:"bırakmak (okul)",s:"quit"},{w:"end up",m:"sonuçlanmak",s:"finish"},{w:"face up to",m:"yüzleşmek",s:"accept"},{w:"fall apart",m:"dağılmak",s:"break up"},{w:"fall out",m:"kavga etmek",s:"argue"},{w:"fall through",m:"suya düşmek",s:"fail"},{w:"feel for",m:"acımak",s:"sympathize"},{w:"figure out",m:"çözmek",s:"solve"},{w:"fill in",m:"doldurmak",s:"complete"},{w:"find out",m:"öğrenmek",s:"discover"},{w:"get ahead",m:"öne geçmek",s:"succeed"},{w:"get along",m:"geçinmek",s:"be friendly"}],4:[{w:"get at",m:"ulaşmak",s:"reach"},{w:"get away",m:"kaçmak",s:"escape"},{w:"get back",m:"dönmek",s:"return"},{w:"get behind",m:"geride kalmak",s:"lag"},{w:"get by",m:"idare etmek",s:"manage"},{w:"get off",m:"inmek",s:"leave"},{w:"get out",m:"çıkmak",s:"exit"},{w:"get over",m:"atlatmak",s:"recover"},{w:"get rid of",m:"kurtulmak",s:"eliminate"},{w:"get round to",m:"vakit bulmak",s:"find time"},{w:"give away",m:"vermek/ifşa",s:"donate"},{w:"give in",m:"teslim olmak",s:"surrender"},{w:"give off",m:"yaymak",s:"emit"},{w:"give out",m:"dağıtmak",s:"distribute"},{w:"give up",m:"vazgeçmek",s:"quit"},{w:"go ahead",m:"devam etmek",s:"proceed"},{w:"go along",m:"sürdürmek",s:"continue"},{w:"go along with",m:"katılmak",s:"agree"},{w:"go away",m:"gitmek",s:"leave"},{w:"go down",m:"düşmek",s:"decrease"}],5:[{w:"go for",m:"seçmek",s:"choose"},{w:"go off",m:"patlamak",s:"explode"},{w:"go on",m:"devam etmek",s:"continue"},{w:"go out",m:"dışarı çıkmak",s:"exit"},{w:"go over",m:"incelemek",s:"review"},{w:"go up",m:"artmak",s:"rise"},{w:"go with",m:"uymak",s:"match"},{w:"grow apart",m:"uzaklaşmak",s:"separate"},{w:"grow out of",m:"büyüyüp bırakmak",s:"outgrow"},{w:"hand in",m:"teslim etmek",s:"submit"},{w:"hand out",m:"dağıtmak",s:"distribute"},{w:"hang out",m:"takılmak",s:"socialize"},{w:"hang up",m:"kapatmak (tel)",s:"end call"},{w:"hold on",m:"beklemek",s:"wait"},{w:"hurry up",m:"acele etmek",s:"rush"},{w:"keep away",m:"uzak durmak",s:"avoid"},{w:"keep on",m:"devam etmek",s:"continue"},{w:"keep up with",m:"ayak uydurmak",s:"match pace"},{w:"kick out",m:"kovmak",s:"expel"},{w:"lay off",m:"işten çıkarmak",s:"fire"}],6:[{w:"let down",m:"hayal kırıklığına uğratmak",s:"disappoint"},{w:"let out",m:"ses çıkarmak",s:"emit sound"},{w:"line up",m:"sıraya girmek",s:"queue"},{w:"live for",m:"için yaşamak",s:"devote"},{w:"live on",m:"ile geçinmek",s:"survive"},{w:"live up to",m:"karşılamak",s:"meet"},{w:"look after",m:"bakmak",s:"care for"},{w:"look back",m:"hatırlamak",s:"remember"},{w:"look down on",m:"küçümsemek",s:"despise"},{w:"look for",m:"aramak",s:"search"},{w:"look forward to",m:"dört gözle beklemek",s:"anticipate"},{w:"look into",m:"araştırmak",s:"investigate"},{w:"look over",m:"gözden geçirmek",s:"examine"},{w:"look up",m:"aramak (bilgi)",s:"search"},{w:"make up",m:"uydurmak",s:"invent"},{w:"make up for",m:"telafi etmek",s:"compensate"},{w:"miss out",m:"kaçırmak",s:"lose out"},{w:"mistake for",m:"karıştırmak",s:"confuse"},{w:"name after",m:"adını vermek",s:"call after"},{w:"narrow down",m:"daraltmak",s:"reduce"}],7:[{w:"occur to",m:"aklına gelmek",s:"come to mind"},{w:"pass away",m:"vefat etmek",s:"die"},{w:"pass by",m:"geçip gitmek",s:"go past"},{w:"pass on",m:"iletmek",s:"transmit"},{w:"pass out",m:"bayılmak",s:"faint"},{w:"pay back",m:"geri ödemek",s:"repay"},{w:"pay for",m:"bedel ödemek",s:"suffer"},{w:"pick up",m:"almak",s:"collect"},{w:"play off",m:"karşılaşmak",s:"compete"},{w:"point out",m:"işaret etmek",s:"indicate"},{w:"pop in",m:"uğramak",s:"visit"},{w:"pull down",m:"yıkmak",s:"destroy"},{w:"pull over",m:"kenara çekmek",s:"stop"},{w:"pull through",m:"iyileşmek",s:"recover"},{w:"put aside",m:"kenara koymak",s:"save"},{w:"put away",m:"yerine koymak",s:"store"},{w:"put down",m:"yere koymak",s:"place"},{w:"put forward",m:"önermek",s:"propose"},{w:"put off",m:"ertelemek",s:"postpone"},{w:"put on",m:"giymek",s:"wear"}],8:[{w:"put out",m:"söndürmek",s:"extinguish"},{w:"put up with",m:"katlanmak",s:"tolerate"},{w:"ring up",m:"aramak",s:"call"},{w:"run across",m:"karşılaşmak",s:"encounter"},{w:"run away",m:"kaçmak",s:"flee"},{w:"run into",m:"rastlamak",s:"meet"},{w:"run out of",m:"tükenmek",s:"finish"},{w:"run over",m:"ezmek",s:"hit"},{w:"see off",m:"uğurlamak",s:"say bye"},{w:"sell out",m:"tükenmek",s:"be sold"},{w:"send out",m:"göndermek",s:"distribute"},{w:"set aside",m:"ayırmak",s:"reserve"},{w:"set off",m:"yola çıkmak",s:"depart"},{w:"set out",m:"yola koyulmak",s:"start"},{w:"set up",m:"kurmak",s:"establish"},{w:"settle down",m:"yerleşmek",s:"settle"},{w:"show off",m:"hava atmak",s:"boast"},{w:"show up",m:"gelmek",s:"arrive"},{w:"shut down",m:"kapatmak",s:"close"},{w:"sign up",m:"kaydolmak",s:"register"}],9:[{w:"sort out",m:"çözümlemek",s:"resolve"},{w:"speak up",m:"yüksek sesle konuşmak",s:"speak louder"},{w:"stand by",m:"desteklemek",s:"support"},{w:"stand for",m:"temsil etmek",s:"represent"},{w:"take after",m:"çekmek/benzemek",s:"resemble"},{w:"take away",m:"götürmek",s:"remove"},{w:"take back",m:"geri almak",s:"return"},{w:"take down",m:"not almak",s:"write"},{w:"take in",m:"anlamak",s:"understand"},{w:"take off",m:"havalanmak",s:"depart"},{w:"take out",m:"çıkarmak",s:"extract"},{w:"take over",m:"devralmak",s:"control"},{w:"take up",m:"başlamak",s:"start"},{w:"talk over",m:"tartışmak",s:"discuss"},{w:"tell apart",m:"ayırt etmek",s:"distinguish"},{w:"tell off",m:"azarlamak",s:"scold"},{w:"think over",m:"düşünmek",s:"consider"},{w:"throw away",m:"atmak",s:"discard"},{w:"throw up",m:"kusmak",s:"vomit"},{w:"tick off",m:"işaretlemek",s:"mark"}],10:[{w:"try on",m:"denemek",s:"test"},{w:"turn away",m:"geri çevirmek",s:"refuse"},{w:"turn down",m:"reddetmek",s:"reject"},{w:"turn into",m:"dönüşmek",s:"become"},{w:"turn off",m:"kapatmak",s:"switch off"},{w:"turn on",m:"açmak",s:"switch on"},{w:"turn out",m:"sonuçlanmak",s:"result"},{w:"turn to",m:"başvurmak",s:"consult"},{w:"use up",m:"tüketmek",s:"consume"},{w:"wake up",m:"uyanmak",s:"awaken"},{w:"walk away",m:"uzaklaşmak",s:"leave"},{w:"warm up",m:"ısınmak",s:"prepare"},{w:"wash away",m:"sürüklemek",s:"carry off"},{w:"watch out",m:"dikkat etmek",s:"be careful"},{w:"watch over",m:"göz kulak olmak",s:"guard"},{w:"wear out",m:"eskimek",s:"deteriorate"},{w:"wipe out",m:"yok etmek",s:"destroy"},{w:"work out",m:"çözmek",s:"solve"},{w:"wrap up",m:"bitirmek",s:"finish"},{w:"write down",m:"yazmak",s:"record"}]};
</script>

<div id="intro-overlay" aria-hidden="true">
    <span class="intro-spark s1"></span>
    <span class="intro-spark s2"></span>
    <span class="intro-spark s3"></span>
    <span class="intro-spark s4"></span>
    <div class="intro-stage">
        <img class="intro-logo" src="../assets/intro_monster.png" alt="">
        <div class="intro-title">Vocab Monster</div>
        <div class="intro-subtitle">YDT/YDS Kelime Arenası</div>
    </div>
</div>

<div id="app">
    <!-- SABİT ÜST BAR -->
    <div id="top-bar">
        <div class="top-left-profile" onclick="openProfileModal()">
            <div id="top-avatar-btn" class="profile-avatar-btn">🤠</div>
            <div class="profile-info-text">
                <div class="name" id="top-username">Player</div>
                <div class="level" id="top-level">Seviye 0</div>
            </div>
        </div>
        <div class="top-right-controls">
            <button class="btn btn-secondary btn-sm" style="padding: 5px 10px; font-size: 1.2rem;" onclick="openFriendsModal()">👥</button>
            <button id="fs-btn" style="position:static;" class="btn btn-secondary btn-sm" style="padding: 5px 10px; font-size: 1.2rem;" onclick="toggleFullScreen()">⛶</button>
            <button class="btn btn-secondary btn-sm" style="padding: 5px 10px; font-size: 1rem; font-weight:900;" onclick="goHome()">🏠</button>
            <button class="btn btn-danger btn-sm" style="padding: 5px 10px; font-size: 1.2rem;" onclick="doLogout()">🚪</button>
        </div>
    </div>
    <button id="screen-back-btn" class="screen-back-btn" onclick="goBackScreen()" aria-label="Geri">&larr;</button>

    <!-- YÜZEN DESTEK VE INSTAGRAM BUTONLARI -->
    <button class="support-floating-btn" onclick="openSupportModal()">
        <span>💚</span> Destek Ol
    </button>
    <a href="https://instagram.com/arifhocaelt" target="_blank" class="ig-floating-btn">
        <span class="ig-icon">📸</span> arifhocaelt
    </a>

    <canvas id="confetti-canvas"></canvas>

    <!-- EKRANLAR -->
    <div id="screen-login" class="screen active">
        <div class="monster-avatar">🌍</div>
        <h2 id="auth-title">Oturum Aç</h2>
        <div class="login-box" id="login-form-box">
            <input type="email" id="login-email" placeholder="E-posta Adresi">
            <input type="password" id="login-pass" placeholder="Şifre">
            <label class="checkbox-container"><input type="checkbox" id="remember-me" checked> Beni Hatırla</label>
            <button class="btn" style="background: linear-gradient(135deg, #0984e3, #6c5ce7); width: 100%; margin-top: 5px; padding: 15px; font-size: 1.1rem;" onclick="doLogin()">GİRİŞ YAP</button>
            <div class="auth-toggle" onclick="toggleAuthForms()">Üyeliğin yok mu? Kayıt Ol.</div>
            <div class="auth-toggle" onclick="resetPassword()" style="color: var(--danger); font-size: 0.85rem; margin-top: 5px;">Şifremi Unuttum</div>
        </div>
        <div class="login-box" id="register-form-box" style="display:none;">
            <input type="email" id="reg-email" placeholder="E-posta Adresi">
            <input type="password" id="reg-pass" placeholder="Şifre (En az 6 hane)">
            <input type="text" id="reg-nick" placeholder="Oyuncu Adı" maxlength="15">
            <button class="btn btn-secondary" style="width: 100%; margin-top: 15px; padding: 15px; font-size: 1.1rem;" onclick="doRegister()">KAYIT OL</button>
            <div class="auth-toggle" onclick="toggleAuthForms()">Zaten hesabın var mı? Giriş Yap.</div>
        </div>
    </div>

    <div id="screen-home" class="screen">
        <h1>VOCAB MONSTER</h1>
        <div class="cat-select-row">
            <div class="category-switch"><button class="btn cat-btn active-cat" onclick="setCategory('vocab')" id="btn-cat-vocab">Vocab</button><button class="btn cat-btn" onclick="setCategory('phrasal')" id="btn-cat-phrasal">Phrasal</button></div>
            <select id="unit-select" style="flex:0.6; margin:0;"></select>
        </div>
        <div class="main-menu-grid">
            <button class="menu-sq-btn btn-fc" onclick="startFlashcards()"><div class="icon">🎴</div><div class="title">Flashcards</div></button>
            <button class="menu-sq-btn btn-ch" onclick="openCareerMap()"><div class="icon">🌍</div><div class="title">Challenge<br>Mode</div></button>
            <button class="menu-sq-btn btn-tm" onclick="openTournamentMenu()"><div class="icon">🏆</div><div class="title">Tournament<br>Mode</div></button>
            <button class="menu-sq-btn btn-mb" onclick="openBattleMenu()"><div class="icon">⚔️</div><div class="title">Monster<br>Battle Vs.</div></button>
        </div>
    </div>

    <div id="screen-tour-menu" class="screen">
        <div class="monster-avatar">🏆</div>
        <h2>Turnuva Modu Seçimi</h2>
        <div style="display:flex; flex-direction:column; gap:15px; width:100%; max-width:400px; margin-top:20px;">
            <button class="btn" style="padding: 20px; font-size:1.3rem;" onclick="setupLocalTournament()">📱 Yerel Cihazda Turnuva</button>
            <button class="btn btn-online" style="padding: 20px; font-size:1.3rem; height:auto;" onclick="openOnlineHub('tour')">🌍 Online Turnuva</button>
        </div>
    </div>

    <div id="screen-battle-menu" class="screen">
        <div class="monster-avatar">⚔️</div>
        <h2>Battle Modu Seçimi</h2>
        <div style="display:flex; flex-direction:column; gap:15px; width:100%; max-width:400px; margin-top:20px;">
            <button class="btn" style="padding: 20px; font-size:1.3rem;" onclick="setupLocalBattle()">📱 Yerel Cihazda Vs</button>
            <button class="btn btn-online" style="padding: 20px; font-size:1.3rem; height:auto;" onclick="openOnlineHub('battle')">🌍 Online Vs</button>
        </div>
    </div>

    <div id="screen-online-tour-hub" class="screen">
        <h2 id="hub-title">🌍 Online Mod</h2>
        <div class="tour-lobby-box">
            <h3 style="color:var(--accent); margin-top:0;">Odaya Katıl</h3>
            <input type="text" id="join-room-code" placeholder="5 Haneli Oda Kodu" maxlength="5" style="text-align:center; font-size:1.5rem; letter-spacing:3px; text-transform:uppercase;">
            <button class="btn" style="margin-top:10px;" onclick="joinOnlineRoom()">Katıl</button>
        </div>
        <div style="margin:20px 0; font-weight:bold; color:#777;">VEYA</div>
        <button class="btn btn-secondary" style="max-width:450px;" onclick="openCreateOnlineRoom()">Yeni Oda Oluştur</button>
    </div>

    <div id="screen-create-room" class="screen">
        <h2 id="cr-title">Oda Ayarları</h2>
        <div class="tour-lobby-box" style="text-align:left;">
            <label>Oda Adı:</label>
            <input type="text" id="create-room-name" placeholder="Örn: 9. Sınıflar Kapışması" maxlength="20">
            
            <div class="room-setup-grid">
                <div class="room-setup-item">
                    <label>Kategori:</label>
                    <select id="create-room-cat" onchange="updateRoomUnitSelect()"><option value="vocab">Vocabulary</option><option value="phrasal">Phrasal Verbs</option></select>
                </div>
                <div class="room-setup-item">
                    <label>Ünite:</label>
                    <select id="create-room-unit"></select>
                </div>
            </div>

            <label style="display:block; margin-top:15px;">Soru Tipi:</label>
            <select id="create-room-type"><option value="mix">Karışık (Tr + Eş Anlam)</option><option value="tr">Sadece Türkçe</option><option value="syn">Sadece Eş Anlam</option></select>
            
            <div id="cr-tour-options">
                <label class="checkbox-container" style="margin-top:15px; justify-content:flex-start;"><input type="checkbox" id="create-room-isplayer" checked> Kendim de Oynayacağım</label>
            </div>
            
            <div id="cr-battle-options" style="display:none; margin-top:15px;">
                <label>Hedef Puan (Oyun Bitişi):</label>
                <input type="number" id="create-room-target" value="20" min="5" max="100">
            </div>
        </div>
        <div class="nav-buttons">
            <button class="btn btn-online" onclick="createOnlineRoom()">Oluştur ve Lobiye Git</button>
        </div>
    </div>

    <div id="screen-admin-lobby" class="screen">
        <h2 id="admin-tour-name">Oda Adı</h2>
        <div class="tour-lobby-box">
            <div style="color:#aaa; font-size:0.9rem; text-transform:uppercase;">Katılım Kodu</div>
            <div class="tour-code-display" id="admin-tour-code">ABCDE</div>
            <div class="action-row"><button class="btn btn-secondary btn-sm" onclick="copyTourCode()">📋 Kopyala</button><button class="btn btn-sm" style="background:#25D366;" onclick="shareTourCode()">💬 WhatsApp</button></div>
            <div class="tour-player-count">Katılan Oyuncular (<span id="admin-player-count">0</span>)</div>
            <div class="player-list" id="admin-player-list"></div>
        </div>
        <div class="nav-buttons">
            <button class="btn btn-danger" onclick="cancelOnlineRoom()">İptal Et</button>
            <button class="btn btn-online" id="admin-draw-btn" onclick="drawOnlineBracket()">🎲 Fikstürü Oluştur</button>
            <button class="btn btn-online" id="admin-start-battle-btn" style="display:none;" onclick="startOnlineBattle()">🚀 Savaş Başlasın</button>
        </div>
    </div>

    <div id="screen-player-lobby" class="screen">
        <h2 id="player-tour-name">Oda Adı</h2>
        <div class="monster-avatar" style="animation: float 2s infinite ease-in-out;">⏳</div>
        <h3 style="color:var(--accent); text-align:center; margin-top:20px;">Odaya Başarıyla Katıldın!</h3>
        <p style="text-align:center; font-size:1.2rem; font-weight:800;">Oyunun yönetici tarafından başlatılması bekleniyor...</p>
        <div class="tour-player-count" style="margin-top:20px;">Odadaki Kişi Sayısı: <span id="player-lobby-count">0</span></div>
        <div class="nav-buttons"><button class="btn btn-danger" onclick="leaveOnlineRoom()">Odadan Ayrıl</button></div>
    </div>

    <div id="screen-online-bracket" class="screen tournament-bracket-screen">
        <h2 id="ob-tour-name">Turnuva Ağacı</h2>
        <div class="intro-overlay" id="ob-countdown-overlay" style="display:none;"><h1 style="color:white; font-size:3rem; text-align:center;" id="ob-overlay-title">TURNUVA BAŞLIYOR!</h1><h3 style="color:var(--secondary);" id="ob-overlay-sub">Karşılaşmalar hazırlanıyor...</h3><div class="big-countdown" id="ob-timer">15</div></div>
        <div class="intro-overlay" id="ob-waiting-overlay" style="display:none; background:rgba(0,0,0,0.8);"><div class="monster-avatar" style="font-size:4rem;">🍿</div><h2 style="color:var(--accent); text-align:center;">Lütfen Bekleyin...</h2><p style="color:white; font-size:1.2rem; font-weight:800; text-align:center; padding:20px;" id="ob-waiting-text">Diğer karşılaşmalar devam ediyor.</p></div>
        <div class="bracket-stage">
            <div class="bracket-scroll"><div class="bracket-tree" id="ob-bracket-container"></div></div>
            <div class="tournament-champion-card" id="online-champion-card"></div>
        </div>
        <div class="nav-buttons" id="ob-admin-controls" style="display:none; flex-direction:column; align-items:center; gap:10px;">
            <button class="btn btn-online" id="ob-admin-start-btn" style="display:none; width:100%; max-width:400px;" onclick="startOnlineTournamentCountdown()">🚀 Turnuvayı Başlat</button>
            <button class="btn btn-danger" style="width:100%; max-width:400px;" onclick="cancelOnlineRoom()">Turnuvayı Bitir / Çık</button>
        </div>
    </div>

    <div id="screen-online-tour-match" class="screen">
        <div class="ol-header" style="justify-content: space-around; font-size: 1.5rem; background: rgba(0,0,0,0.5); padding: 10px; border-radius: 15px; margin-bottom: 15px;">
            <div style="color:var(--p1-c); display:flex; flex-direction:column; align-items:center;"><span style="font-size:0.8rem; color:white; text-transform:uppercase;" id="otm-p1-name">P1</span><span id="otm-p1-score" style="font-weight:900; color:gold; font-size: 2rem;">0</span></div>
            <div style="display:flex; flex-direction:column; align-items:center;"><div id="otm-vs-text" style="color:white; font-size:1.2rem;">VS</div><div id="otm-progress" style="font-size:0.8rem; color:#aaa;">1/5</div></div>
            <div style="color:var(--p2-c); display:flex; flex-direction:column; align-items:center;"><span style="font-size:0.8rem; color:white; text-transform:uppercase;" id="otm-p2-name">P2</span><span id="otm-p2-score" style="font-weight:900; color:gold; font-size: 2rem;">0</span></div>
        </div>
        <div class="ol-timer-bar"><div class="ol-timer-fill" id="otm-timer-fill"></div><div class="ol-timer-text" id="otm-timer-text">10.00</div></div>
        <div class="question-box" id="otm-question">...</div>
        <div class="options-grid" id="otm-options"></div>
        <div id="otm-feedback" style="height: 30px; margin-top: 15px; font-weight: 900; color: var(--secondary); text-align:center; font-size:1.5rem; text-shadow:1px 1px 2px black;"></div>
        <div class="nav-buttons"><button class="btn btn-secondary" onclick="speakCurrentWord()">🔊</button></div>
    </div>

    <!-- ONLİNE BATTLE EKRANI -->
    <div id="screen-online-battle-arena" class="screen">
        <div class="ol-header" id="obattle-scores-header" style="justify-content:center; gap:15px; flex-wrap:wrap; font-size:1.1rem; background:rgba(0,0,0,0.5); padding:10px; border-radius:15px; margin-bottom:15px;"></div>
        <div class="ol-timer-bar"><div class="ol-timer-fill" id="obattle-timer-fill"></div><div class="ol-timer-text" id="obattle-timer-text">10.00</div></div>
        <div class="intro-overlay" id="obattle-result-overlay" style="display:none; background:rgba(0,0,0,0.85); z-index:200;"><h1 style="color:var(--accent);" id="obattle-res-title">Sonuçlar!</h1><div id="obattle-res-content" style="text-align:center;"></div></div>
        <div class="question-box" id="obattle-question">...</div>
        <div class="options-grid" id="obattle-options"></div>
        <div id="obattle-feedback" style="height: 30px; margin-top: 15px; font-weight: 900; color: var(--secondary); text-align:center; font-size:1.5rem; text-shadow:1px 1px 2px black;"></div>
        <div class="nav-buttons" id="obattle-admin-controls" style="display:none;"><button class="btn btn-danger" onclick="cancelOnlineRoom()">Oyunu Bitir</button></div>
    </div>

    <!-- MODALLAR -->
    <div id="profile-modal" class="modal-overlay">
        <div class="modal-box">
            <h2 class="modal-title" style="color:white; font-size: 1.2rem;">Profilim</h2>
            <div class="profile-scroll">
                <div id="prof-nickname" style="font-size: 1.3rem; color: var(--accent); font-weight: 900;">Player</div>
                <div class="profile-section-title">Avatarını Seç</div>
                <div class="avatar-selection" id="avatar-grid-area"></div>
                <div class="badges-container">
                    <h3 style="color:var(--secondary); margin-bottom: 10px;">Rozetler</h3>
                    <div class="badge-tabs">
                        <button class="btn cat-btn active-cat" id="my-badge-tab-monthly" onclick="showBadgeTab('my','monthly')">Aylık</button>
                        <button class="btn cat-btn" id="my-badge-tab-general" onclick="showBadgeTab('my','general')">Genel</button>
                    </div>
                    <div class="badge-grid" id="my-badges-monthly"></div>
                    <div class="badge-grid" id="my-badges-general" style="display:none;"></div>
                </div>
            </div>
            <button class="btn btn-secondary" style="margin-bottom:10px;" onclick="openAccountSettingsModal()">Hesap Ayarları</button>
            <button class="btn btn-danger" onclick="closeProfileModal()">Kapat</button>
        </div>
    </div>

    <div id="account-settings-modal" class="modal-overlay" style="z-index: 10006;">
        <div class="modal-box">
            <h2 class="modal-title" style="color:white;">Hesap Ayarları</h2>
            <div class="account-action-list">
                <button class="btn btn-secondary" onclick="openChangeNicknameModal()">Kullanıcı Adı Değiştir</button>
                <button class="btn" onclick="openChangePasswordModal()">Şifre Değiştir</button>
                <button class="btn btn-danger" onclick="openDeleteAccountModal()">Hesabı Sil</button>
            </div>
            <button class="btn btn-secondary" style="margin-top:15px;" onclick="closeAccountSettingsModal()">Kapat</button>
        </div>
    </div>

    <div id="change-nickname-modal" class="modal-overlay" style="z-index: 10007;">
        <div class="modal-box">
            <h2 class="modal-title" style="color:var(--secondary);">Kullanıcı Adı Değiştir</h2>
            <input type="text" id="new-nickname-input" placeholder="Yeni kullanıcı adı" maxlength="15" style="text-align:center;">
            <button class="btn btn-secondary" style="margin: 15px 0 10px 0;" onclick="updateUserNickname()">Kaydet</button>
            <button class="btn btn-danger" onclick="closeChangeNicknameModal()">İptal</button>
        </div>
    </div>

    <div id="public-profile-modal" class="modal-overlay" style="z-index: 10005;">
        <div class="modal-box">
            <div class="monster-avatar" id="pub-prof-avatar" style="font-size:5rem;">🤠</div>
            <h2 class="modal-title" id="pub-prof-nickname" style="color:white; margin-bottom:5px;">Player</h2>
            <div style="color:gold; font-weight:800; margin-bottom:15px;" id="pub-prof-level">Seviye 0</div>
            <div class="badges-container">
                <h3 style="color:var(--secondary); margin-bottom: 10px;">Rozetleri</h3>
                <div class="badge-tabs">
                    <button class="btn cat-btn active-cat" id="pub-badge-tab-monthly" onclick="showBadgeTab('pub','monthly')">Aylık</button>
                    <button class="btn cat-btn" id="pub-badge-tab-general" onclick="showBadgeTab('pub','general')">Genel</button>
                </div>
                <div class="badge-grid" id="pub-badges-monthly"></div>
                <div class="badge-grid" id="pub-badges-general" style="display:none;"></div>
            </div>
            <div class="clap-box">
                <span>Oyuncuyu tebrik et</span>
                <button class="btn btn-secondary btn-sm" id="pub-prof-clap-btn" style="width:auto;" onclick="sendProfileClap()">👏 <span id="pub-prof-claps" class="clap-count">0</span></button>
            </div>
            <button class="btn btn-online" id="pub-prof-add-btn" style="margin-bottom:10px;">Arkadaş Ekle</button>
            <button class="btn btn-danger" onclick="closePublicProfile()">Kapat</button>
        </div>
    </div>

    <div id="friends-modal" class="modal-overlay" style="z-index: 10003;">
        <div class="modal-box" style="padding: 15px; display:flex; flex-direction:column; height:80vh;">
            <div class="category-switch" style="margin-bottom: 10px;"><button class="btn cat-btn active-cat" id="tab-friends-list" onclick="showFriendsTab('list')">Arkadaşlarım</button><button class="btn cat-btn" id="tab-friends-reqs" onclick="showFriendsTab('reqs')">İstekler <span id="req-badge" style="background:red; color:white; border-radius:50%; padding:2px 6px; font-size:0.7rem; display:none;">0</span></button></div>
            <div class="friend-search-box">
                <div class="friend-search-row">
                    <input id="friend-search-input" placeholder="Oyuncu adı ara" autocomplete="off" oninput="queueFriendSearchSuggestions()" onkeypress="handleEnter(event, searchFriendByName)" style="margin:0; flex:1;">
                    <button class="btn btn-secondary btn-sm" style="width:auto;" onclick="searchFriendByName()">Ara</button>
                </div>
                <div class="friend-search-results" id="friend-search-results"></div>
            </div>
            <div id="friends-content-area" style="overflow-y:auto; flex-grow:1; text-align:left; background: rgba(0,0,0,0.2); border-radius:10px; padding:10px;"></div>
            <button class="btn btn-danger" style="margin-top:15px;" onclick="closeFriendsModal()">Kapat</button>
        </div>
    </div>

    <div id="change-pass-modal" class="modal-overlay" style="z-index: 10002;">
        <div class="modal-box">
            <h2 class="modal-title" style="color:var(--danger);">Şifre Değiştir</h2>
            <input type="password" id="new-password-input" placeholder="Yeni Şifre (En az 6 hane)" style="text-align:center;">
            <button class="btn" style="margin: 15px 0 10px 0;" onclick="updateUserPassword()">Kaydet</button>
            <button class="btn btn-secondary" onclick="closeChangePasswordModal()">İptal</button>
        </div>
    </div>

    <div id="delete-account-modal" class="modal-overlay" style="z-index: 10008;">
        <div class="modal-box">
            <h2 class="modal-title" style="color:var(--danger);">Hesabı Sil</h2>
            <div class="account-warning">
                Bu işlem geri alınamaz. Hesabın, kullanıcı bilgilerin, arkadaşlık kayıtların, sıralama kayıtların ve oyun ilerlemen silinecek.
            </div>
            <input type="password" id="delete-account-password" placeholder="Onay için şifreni yaz" style="text-align:center;">
            <label class="delete-confirm-row">
                <input type="checkbox" id="delete-account-confirm-check" onchange="toggleDeleteAccountButton()">
                <span>Hesap bilgilerimin ve tüm oyun ilerlememin kalıcı olarak silineceğini onaylıyorum.</span>
            </label>
            <button class="btn btn-danger" id="delete-account-final-btn" style="margin-bottom:10px;" onclick="deleteCurrentAccount()" disabled>Hesabımı Kalıcı Olarak Sil</button>
            <button class="btn btn-secondary" onclick="closeDeleteAccountModal()">Vazgeç</button>
        </div>
    </div>

    <div id="support-modal" class="modal-overlay" style="z-index: 10009;">
        <div class="modal-box">
            <h2 class="modal-title">Destek Ol</h2>
            <p style="color:white; font-weight:800; line-height:1.45;">Bu uygulama tamamen ücretsizdir ve her zaman ücretsiz olacaktır. Uygulamanın gelişimine katkıda bulunmak için reklam izlemek istiyor musunuz?</p>
            <div style="display:flex; gap:10px; margin-top:15px;">
                <button class="btn btn-secondary" onclick="watchSupportAd()">Reklamı İzle</button>
                <button class="btn btn-danger" onclick="closeSupportModal()">Kapat</button>
            </div>
        </div>
    </div>

    <div id="level-info-modal" class="modal-overlay">
        <div class="modal-box">
            <h2 class="modal-title" id="li-title">Bölüm 1</h2>
            <div style="font-size: 2.5rem; margin-bottom: 10px;" id="li-stars">☆☆☆</div>
            <p style="font-size: 1.1rem; font-weight: 800; color: #aaa; margin-bottom: 20px;">Bölüm Rekorun: <span id="li-highscore" style="color:gold;">0</span></p>
            <div style="display:flex; flex-direction:column; gap:10px; margin-bottom: 20px; width: 100%;">
                <div style="display:flex; align-items:stretch; gap:5px; width:100%;"><button class="btn" id="btn-mode-1" onclick="startOnlineLevel(1)" style="flex-grow:1;">1. Yıldız (Eng-Tr)</button><div class="info-icon" onclick="showRuleInfo(1)">ℹ️</div></div>
                <div style="display:flex; align-items:stretch; gap:5px; width:100%;"><button class="btn" id="btn-mode-2" onclick="startOnlineLevel(2)" style="flex-grow:1;">2. Yıldız (Eng-Eng)</button><div class="info-icon" onclick="showRuleInfo(2)">ℹ️</div></div>
                <div style="display:flex; align-items:stretch; gap:5px; width:100%;"><button class="btn btn-arena" id="btn-mode-3" onclick="startOnlineLevel(3)" style="flex-grow:1;">🔥 CHALLENGE (Rekor)</button><div class="info-icon" onclick="showRuleInfo(3)">ℹ️</div></div>
            </div>
            <button class="btn btn-danger" onclick="closeLevelInfo()">Kapat</button>
        </div>
    </div>

    <div id="rule-info-modal" class="modal-overlay" style="z-index: 10001;">
        <div class="modal-box" style="border-color: #0984e3;"><h2 class="modal-title" id="rule-title" style="color: #0984e3;">Mod Kuralları</h2><div style="text-align:left; font-size:1.1rem; color:white; line-height:1.6; margin-bottom:20px;" id="rule-desc"></div><button class="btn" style="background:#0984e3;" onclick="closeRuleInfo()">Anladım</button></div>
    </div>

    <div id="leaderboard-overlay" class="modal-overlay">
        <div class="modal-box">
            <div class="modal-title" id="lb-title">Bölüm 1 Sıralaması</div>
            <div class="category-switch" style="margin: 0 auto 10px auto; max-width: 350px;">
                <button class="btn cat-btn" id="tab-monthly" onclick="showLbTab('monthly')">Aylık</button>
                <button class="btn cat-btn active-cat" id="tab-alltime" onclick="showLbTab('alltime')">Genel</button>
            </div>
            <div id="lb-podium-area" class="podium-container" style="display: none;"></div>
            <div class="lb-list" id="lb-list" style="margin-top: 10px;"></div>
            <button class="btn btn-danger" onclick="closeLeaderboard()">Kapat</button>
        </div>
    </div>

    <div id="screen-online-game" class="screen">
        <div class="ol-header"><div class="ol-lives" id="ol-lives">❤️❤️❤️</div><div id="ol-progress">1/40</div><div class="ol-score" id="ol-score-display">Puan: 0</div></div>
        <div class="ol-timer-bar"><div class="ol-timer-fill" id="ol-timer-fill"></div><div class="ol-timer-text" id="ol-timer-text">10.00</div></div>
        <div class="question-box" id="ol-question">...</div>
        <div class="options-grid" id="ol-options"></div>
        <div id="ol-feedback" style="height: 30px; margin-top: 15px; font-weight: 800; color: var(--secondary);"></div>
        <div class="nav-buttons"><button class="btn btn-secondary" onclick="speakCurrentWord()">🔊</button><button class="btn btn-danger" onclick="abandonOnlineGame()">Pes Et</button></div>
    </div>

    <div id="screen-online-result" class="screen">
        <div class="monster-avatar" id="ol-res-avatar">🏆</div>
        <h2 id="ol-res-title" style="font-size:2rem; color:var(--accent);">Görev Tamamlandı!</h2>
        <div style="font-size: 3rem; margin: 10px 0;" id="ol-res-stars">★★★</div>
        <div style="background:rgba(0,0,0,0.4); padding: 15px; border-radius: 15px; text-align: center; width: 100%; max-width: 400px; margin-bottom: 20px;">
            <div style="font-size:1.1rem; color:#aaa; font-weight:bold;">Doğru Sayısı</div><div style="font-size:1.8rem; color:white; font-weight:900; margin-bottom:5px;" id="ol-res-correct">30/40</div>
            <div style="font-size:1.1rem; color:#aaa; font-weight:bold; display:none;" id="ol-res-score-title">Kazanılan Puan</div><div style="font-size:2.2rem; color:gold; font-weight:900; text-shadow: 2px 2px 0 #000; display:none;" id="ol-res-score">0</div>
        </div>
        <div id="ol-res-ranks" style="display:none; width:100%; max-width:400px; margin-bottom: 20px; font-size:1.1rem; text-align:center;">Hesaplanıyor... ⏳</div>
        <div class="nav-buttons"><button class="btn btn-online" onclick="showScreen('screen-career-map')">Haritaya Dön</button></div>
    </div>

    <div id="screen-flashcards" class="screen"><h2>Kartlar</h2><div class="card-container" onclick="flipCard()"><div class="card" id="flashcard"><div class="card-face card-front"><div class="word-title" id="fc-word">...</div><small style="color:#aaa; position:absolute; bottom:20px;">Çevirmek için tıkla</small></div><div class="card-face card-back"><div class="meaning-text" id="fc-meaning">...</div><div class="synonym" id="fc-synonym">...</div></div></div></div><div class="nav-buttons"><button class="btn" onclick="prevCard()">⬅️</button><button class="btn btn-secondary" onclick="speakCurrentWord()">🔊</button><button class="btn btn-danger" onclick="showScreen('screen-home')">🏠</button><button class="btn" onclick="nextCard()">➡️</button></div></div>

    <div id="screen-career-map" class="screen" style="padding: 0;">
        <div style="width:100%; background:rgba(0,0,0,0.5); padding:15px; display:flex; flex-direction:column; align-items:center; z-index:100; flex-shrink: 0; border-bottom: 2px solid #555;">
            <div style="display:flex; justify-content:center; width:100%; align-items:center; margin-bottom: 10px;">
                <div style="font-weight:900; font-size:1.2rem;" id="career-title">Challenge Mode</div>
            </div>
            <div class="category-switch" style="margin: 0; width: 100%; max-width: 400px;"><button class="btn cat-btn active-cat" id="ol-cat-vocab" onclick="setOnlineCategory('vocab')">Vocabulary</button><button class="btn cat-btn" id="ol-cat-phrasal" onclick="setOnlineCategory('phrasal')">Phrasal Verbs</button></div>
        </div>
        <div class="map-wrapper" id="map-container"></div>
    </div>

    <!-- YEREL TURNUVA KISMI -->
    <div id="screen-local-tour-setup" class="screen">
        <h2>📱 Yerel Turnuva</h2>
        <div style="display:flex; gap:5px; margin-bottom: 10px; width:100%; justify-content:center; align-items:center;"><input type="text" id="player-name" placeholder="Oyuncu Adı" onkeypress="handleEnter(event, addPlayer)" style="width:150px;"><select id="player-emoji" style="width:70px;"><option value="😎">😎</option><option value="🦁">🦁</option><option value="🐯">🐯</option><option value="🦅">🦅</option><option value="🦈">🦈</option><option value="🦖">🦖</option><option value="🚀">🚀</option><option value="🌟">🌟</option><option value="🔥">🔥</option><option value="💎">💎</option><option value="⚡">⚡</option><option value="👾">👾</option></select><button class="btn" style="width:auto;" onclick="addPlayer()">Ekle</button></div>
        <div style="text-align:center; margin-bottom: 10px;"><label>Soru Tipi:</label><br><select id="tour-quiz-type"><option value="mix">Karışık</option><option value="tr">Türkçe</option><option value="syn">Eş Anlam</option></select></div>
        <div style="text-align:center; margin-bottom: 10px;"><label>Maç Soru Sayısı:</label><br><select id="tour-q-limit"><option value="3">3</option><option value="5" selected>5</option><option value="7">7</option><option value="10">10</option></select></div>
        <div class="player-list" id="player-list"></div>
        <div class="nav-buttons"><button class="btn btn-secondary" onclick="generateLocalBracket()">Fikstür</button></div>
    </div>
    <div id="screen-local-bracket" class="screen tournament-bracket-screen">
        <h2>Fikstür</h2>
        <div class="bracket-stage">
            <div class="bracket-scroll"><div class="bracket-tree" id="local-bracket-container"></div></div>
            <div class="tournament-champion-card" id="local-champion-card"></div>
        </div>
    </div>
    
    <!-- YEREL BATTLE KISMI -->
    <div id="screen-battle-setup" class="screen">
        <h2>⚔️ Battle Arena</h2>
        <label>Oyuncu Sayısı:</label>
        <select id="battle-count" onchange="updateBattleInputs()"><option value="2">2 Kişi</option><option value="3">3 Kişi</option><option value="4">4 Kişi</option></select>
        <div id="battle-names-area" style="width:100%; display:flex; flex-direction:column; align-items:center;"></div>
        <label>Soru Tipi:</label>
        <select id="battle-quiz-type"><option value="mix">Karışık</option><option value="tr">Türkçe</option><option value="syn">Eş Anlam</option></select>
        <label>Hedef Puan:</label>
        <select id="battle-score-limit"><option value="10">10</option><option value="15" selected>15</option><option value="20">20</option><option value="30">30</option></select>
        <div class="nav-buttons"><button class="btn btn-arena" onclick="startBattleIntro()">🔥 Savaş Başlasın</button></div>
    </div>
    
    <!-- YEREL BATTLE ARENASI -->
    <div id="screen-battle-arena" class="screen" style="padding:0;">
        <div class="intro-overlay" id="battle-intro-overlay" style="display:none;"><h1 style="color:white; font-size:3rem;">Hazırlanın!</h1><div class="intro-box" id="battle-intro-box"></div><h2 id="battle-intro-timer" style="font-size:4rem; color:var(--accent);">3</h2></div>
        
        <div class="arena-overlay" id="battle-reveal-overlay" style="position:absolute; inset:0; z-index:200; display:none; flex-direction:column; justify-content:center; align-items:center; background:rgba(0,0,0,0.85);">
            <h1 style="color:var(--accent);" id="br-title">Sonuçlar!</h1>
            <div id="br-content" style="text-align:center;"></div>
        </div>
        
        <div class="intro-overlay" id="battle-alert-overlay" style="display:none; z-index: 300;">
            <h1 style="color:var(--accent); font-size: 3rem; text-align:center; text-shadow: 3px 3px 0 #000;" id="ba-title">DOĞRU BİLEN KAZANIR!</h1>
        </div>

        <div class="battle-container"><div class="battle-top-bar"><div class="battle-word" id="b-question">WORD</div><div class="battle-timer" id="b-timer">10</div></div><div class="battle-grid" id="battle-grid"></div></div>
        <div class="nav-buttons" style="position:absolute; bottom:10px; width:100%; padding:0 15px;"><button class="btn btn-danger btn-sm" style="width:auto;" onclick="endBattleEarly()">Çıkış</button><button class="btn btn-secondary btn-sm" style="width:auto;" onclick="speakCurrentWord()">🔊</button></div>
    </div>
    
    <!-- ORTAK SONUÇ EKRANI -->
    <div id="screen-result" class="screen"><div class="monster-avatar">🏆</div><h2 id="result-title">Sonuçlar</h2><div class="podium-container" id="tour-podium-area"></div><h1 id="result-score"></h1><p id="result-message"></p></div>
</div>

<script>
    const AVATAR_LIST = ["👾","👽","👻","👹","👺","🤡","🎃","🤖","🧟","🧛","🦇","🦉","🦅","🦆","🐺","🕷️","🦂","🦖","🦕","🐙"];
    const PLAYER_EMOJI_LIST = ["😎","🤓","🧠","🦁","🐯","🦅","🦈","🦖","🦕","🐉","🦊","🐺","🐼","🐵","🐙","🦂","🦇","🦉","👾","👽","🤖","👻","🎃","🔥","⚡","🌟","💎","🚀","🏆","🥇","🎯","🧩","📚","✏️","🎓","💪","🛡️","⚔️","🪄","🌈","☄️","🍀","🧿","🎲","🎮","🥷","🦸","🧙"];
    let db = null, auth = null;
    try {
        const firebaseConfig = { apiKey: "AIzaSyB7PuSqxsAxUdM79bDX_xKxWH2PtPYtF8c", authDomain: "vocabmonster-dae94.firebaseapp.com", databaseURL: "https://vocabmonster-dae94-default-rtdb.europe-west1.firebasedatabase.app", projectId: "vocabmonster-dae94", storageBucket: "vocabmonster-dae94.firebasestorage.app", messagingSenderId: "36198656241", appId: "1:36198656241:web:b404075c578dc12f5f6150" };
        firebase.initializeApp(firebaseConfig); db = firebase.firestore(); auth = firebase.auth();
    } catch (e) { console.error("Firebase Başlatılamadı:", e); }

    let currentDbUser = null; let isRegisterMode = true; let currentCategory='vocab', currentData=vocabData, gameWords=[], fcIndex=0, currentWordObj=null; let quizScore=0, timerInterval;
    let currentPublicProfileUid = null, currentPublicProfileClaps = 0;
    let friendSearchTimer = null;
    
    // Battle & Local Tour
    let players=[], rounds=[], currentMatch=null, activeArena=false; 
    let battlePlayers=[], battleRoundAnswers=[]; 
    let isLocalTourBattle = false; let currentBattleRound = 0; let battlePhase = 'normal'; 
    let askedQuestions = [], tourWordPool = [], battleWordPool = [], battleQuestionPool = []; let battleQuestionMode = null; let battleMaxQ = 5, tournamentMaxQuestions = 5, battleScoreLimit = 15;
    
    // Online Tour/Battle
    let roomCreateType = 'tour'; 
    let onlineCategory = 'vocab', olPart = 1, olTargetStar = 1, olLives = 3, olScore = 0, olQuestions = [], olQIndex = 0, olCorrect = 0, olReqCorrect = 30, olStartTime = 0, olTimerInt = null;
    let otCode = null, otListener = null, otData = null, otIsAdmin = false, otSyncInterval = null, otMyMatch = null; let otCurrentPhase = '';
    let englishVoice=null, synth=window.speechSynthesis; 

    // Online Battle Özel
    let obLocalHasAnswered = false; let obLocalQIndex = -1; let obHostTimer = null;
    let screenNavToken = 0;
    let flashcardSpeakTimeout = null, olNextQuestionTimeout = null, otmTransitionTimeout = null, onlineBattleNextTimeout = null;
    let battleIntroInterval = null, battleAlertTimeout = null, battleRevealTimeout = null, localTourReturnTimeout = null, onlineTourFinishTimeout = null;
    let otmAnimTimeout = null, obattleAnimTimeout = null, bracketDrawInterval = null, bracketDrawResetTimeout = null;
    let otMatchUnsub = null, otMatchDocRef = null, otMatchRole = null, otCurrentQIndex = -1, otLocalHasAnswered = false, quizQ = [];

    window.addEventListener('load', ()=>{
        init();
        const intro = document.getElementById('intro-overlay');
        if(intro) {
            const closeIntro = () => intro.classList.add('hide');
            setTimeout(closeIntro, 2700);
            intro.addEventListener('click', closeIntro);
        }
        const mapCont = document.getElementById('map-container');
        if(mapCont) {
            let isDown = false; let startX; let scrollLeft;
            mapCont.addEventListener('mousedown', (e) => { isDown = true; startX = e.pageX - mapCont.offsetLeft; scrollLeft = mapCont.scrollLeft; });
            mapCont.addEventListener('mouseleave', () => { isDown = false; });
            mapCont.addEventListener('mouseup', () => { isDown = false; });
            mapCont.addEventListener('mousemove', (e) => { if (!isDown) return; e.preventDefault(); const x = e.pageX - mapCont.offsetLeft; const walk = (x - startX) * 2; mapCont.scrollLeft = scrollLeft - walk; });
        }
        try{ if(synth && synth.onvoiceschanged!==undefined) speechSynthesis.onvoiceschanged=loadVoices; loadVoices();}catch(e){}
    });
    
    function init(){ 
        setCategory('vocab'); setTimeout(()=>{ const sel=document.getElementById('unit-select'); if(sel&&sel.options.length>0) sel.selectedIndex=0; },500); 
        populatePlayerEmojiSelect(document.getElementById('player-emoji'), '😎');
        const ag = document.getElementById('avatar-grid-area');
        if(ag) { ag.innerHTML = ''; AVATAR_LIST.forEach(av => { ag.innerHTML += `<span class="avatar-option" onclick="selectAvatar('${av}')">${av}</span>`; }); }
    }

    function populatePlayerEmojiSelect(selectEl, preferredValue) {
        if(!selectEl) return;
        const current = preferredValue || selectEl.value || PLAYER_EMOJI_LIST[0];
        selectEl.innerHTML = '';
        PLAYER_EMOJI_LIST.forEach(e => {
            const opt = document.createElement('option');
            opt.value = e;
            opt.innerText = e;
            selectEl.appendChild(opt);
        });
        selectEl.value = PLAYER_EMOJI_LIST.includes(current) ? current : PLAYER_EMOJI_LIST[0];
    }

    function parseDataSafe(arr) {
        if(!arr || !Array.isArray(arr)) return []; let safeArr = [];
        for (let i = 0; i < arr.length; i++) {
            let item = arr[i]; if (!item) continue;
            let w = item.w || item.word || item.W || item.Word || item.WORD || item.kelime || item.Kelime;
            let m = item.m || item.meaning || item.M || item.Meaning || item.MEANING || item.anlam || item.Anlam;
            let s = item.s || item.syn || item.S || item.Syn || item.synonym || item.Synonym || item.SYNONYM || item.esanlam || item.Esanlam;
            if (!w) { let keys = Object.keys(item); if(keys.length >= 3) { w = item[keys[0]]; m = item[keys[1]]; s = item[keys[2]]; } }
            if (w) {
                const word = String(w).trim(), meaning = String(m || "Bilinmiyor").trim(), syn = String(s || "Bilinmiyor").trim();
                const rawPos = item.pos || item.POS || item.type || item.wordType || item.partOfSpeech || item.tur || item.Tur || item.kind;
                safeArr.push({ word: word, meaning: meaning, syn: syn, pos: normalizeWordType(rawPos) || inferWordType(word, meaning, syn) });
            }
        } return safeArr;
    }

    function normalizeWordType(raw) {
        if(!raw) return "";
        const v = String(raw).toLowerCase().trim();
        if(['n','noun','isim','ad','substantive'].includes(v)) return 'noun';
        if(['v','verb','fiil','phrasal','phrasal verb'].includes(v)) return 'verb';
        if(['adj','adjective','sıfat','sifat'].includes(v)) return 'adjective';
        if(['adv','adverb','zarf'].includes(v)) return 'adverb';
        return "";
    }

    function inferWordType(word, meaning, syn) {
        const w = String(word || '').toLowerCase();
        const m = String(meaning || '').toLowerCase();
        const s = String(syn || '').toLowerCase();
        if(/\b(etmek|olmak|yapmak|kılmak|almak|vermek)\b/.test(m) || /(mak|mek)(\)|$|\s|\/)/.test(m) || w.includes(' ') || /\b(to|do|make|be|get|take|give|go|come|put|set)\b/.test(s)) return 'verb';
        if(w.endsWith('ly') || m.includes('olarak') || m.includes('şekilde')) return 'adverb';
        if(/(able|ible|ive|ous|al|ic|ful|less|ent|ant|ary|ory|ate)$/.test(w) || /(lı|li|lu|lü|siz|sız|suz|süz|sal|sel)\b/.test(m)) return 'adjective';
        return 'noun';
    }

    function getWordType(wordObj) { return (wordObj && wordObj.pos) ? wordObj.pos : inferWordType(wordObj && wordObj.word, wordObj && wordObj.meaning, wordObj && wordObj.syn); }
    function getAnswerText(wordObj, type) { return type === 'tr' ? wordObj.meaning : wordObj.syn; }
    function shuffleArray(arr) { return [...arr].sort(()=>Math.random()-0.5); }
    function makeQuestionPool(words, modePref) {
        const pool = [];
        (words || []).forEach(w => {
            if(modePref === 'tr' || modePref === 'mix') pool.push({wordObj:w, type:'tr'});
            if(modePref === 'syn' || modePref === 'mix') pool.push({wordObj:w, type:'syn'});
        });
        return pool;
    }
    function flattenDataForOptions(cat) {
        const data = cat === 'phrasal' ? phrasalData : vocabData;
        return Object.keys(data || {}).flatMap(k => parseDataSafe(data[k]));
    }
    function buildQuestionOptions(correctWord, type, sourceWords, catForFallback) {
        const correctAnswer = getAnswerText(correctWord, type);
        const targetPos = getWordType(correctWord);
        let bank = [...(sourceWords || [])];
        const fallback = [...flattenDataForOptions(catForFallback || currentCategory), ...flattenDataForOptions((catForFallback || currentCategory) === 'vocab' ? 'phrasal' : 'vocab')];
        fallback.forEach(w => { if(!bank.find(x => x.word === w.word)) bank.push(w); });
        let candidates = bank.filter(w => w.word !== correctWord.word && getWordType(w) === targetPos && getAnswerText(w, type) && getAnswerText(w, type) !== correctAnswer);
        const picked = [];
        shuffleArray(candidates).forEach(w => {
            const answer = getAnswerText(w, type);
            if(picked.length < 3 && !picked.find(x => getAnswerText(x, type) === answer)) picked.push(w);
        });
        return shuffleArray([...picked, correctWord]).map(w => getAnswerText(w, type));
    }
    function buildQuestionObject(wordObj, type, sourceWords, catForFallback) {
        return { wordObj: wordObj, type: type, correct: getAnswerText(wordObj, type), opts: buildQuestionOptions(wordObj, type, sourceWords, catForFallback) };
    }
    function hashString(str) {
        let h = 2166136261;
        for(let i=0; i<str.length; i++) { h ^= str.charCodeAt(i); h = Math.imul(h, 16777619); }
        return h >>> 0;
    }
    function deterministicQuestionItem(words, modePref, index, seeds) {
        const pool = makeQuestionPool(words, modePref);
        if(pool.length === 0) return null;
        const cycle = Math.floor(index / pool.length);
        const seed = (seeds && seeds.length) ? seeds[cycle % seeds.length] : 1;
        const ordered = [...pool].sort((a,b) => hashString(`${seed}|${a.wordObj.word}|${a.type}`) - hashString(`${seed}|${b.wordObj.word}|${b.type}`));
        return ordered[index % ordered.length];
    }

    const MONTH_NAMES_TR = ["Ocak","Şubat","Mart","Nisan","Mayıs","Haziran","Temmuz","Ağustos","Eylül","Ekim","Kasım","Aralık"];

    function calculateLevelFromProgress(progObj) {
        let totalStars = 0;
        if(!progObj) return 0;
        Object.values(progObj).forEach(cat => {
            if(!cat) return;
            Object.values(cat).forEach(p => { totalStars += Math.max(0, parseInt((p && p.stars) || 0)); });
        });
        return totalStars;
    }
    function calculateLevel(progressObj) { return calculateLevelFromProgress(progressObj); }
    function getTotalScore(progObj) { let t = 0; if(!progObj) return 0; Object.values(progObj).forEach(cat => { if(cat) Object.values(cat).forEach(p => { t += (p.highScore || 0); }); }); return t; }
    function emptyBadges() { return { monthly: [], general: [] }; }
    function normalizeBadges(badges) { return { monthly: (badges && Array.isArray(badges.monthly)) ? badges.monthly : [], general: (badges && Array.isArray(badges.general)) ? badges.general : [] }; }
    function getCategoryLabel(cat) { return cat === 'phrasal' ? 'Phrasal Verb' : 'Vocabulary'; }
    function getPartLabel(cat, part) { return `${getCategoryLabel(cat)} Part ${part}`; }
    function getRankName(rank) { return rank === 1 ? 'Altın' : rank === 2 ? 'Gümüş' : 'Bronz'; }
    function getBadgeSymbol(type, rank) { return type === 'monthly' ? (rank === 1 ? '🥇' : rank === 2 ? '🥈' : '🥉') : '🏆'; }
    function getBadgeCaption(badge) { return badge.type === 'monthly' ? `${getPartLabel(badge.category, badge.part)}<br>${MONTH_NAMES_TR[badge.month]} ${badge.year}` : getPartLabel(badge.category, badge.part); }
    function timestampToMillis(ts) {
        if(!ts) return null;
        if(typeof ts.toMillis === 'function') return ts.toMillis();
        if(typeof ts.seconds === 'number') return ts.seconds * 1000;
        if(typeof ts === 'number') return ts;
        return null;
    }
    function isCompletedMonth(year, month) {
        const now = new Date();
        return year < now.getFullYear() || (year === now.getFullYear() && month < now.getMonth());
    }
    function sortBestEntries(entries) {
        const byUser = new Map();
        entries.forEach(item => {
            if(!item || !item.uid) return;
            const current = byUser.get(item.uid);
            if(!current || Number(item.score || 0) > Number(current.score || 0)) byUser.set(item.uid, item);
        });
        return Array.from(byUser.values()).sort((a,b) => Number(b.score || 0) - Number(a.score || 0));
    }
    function renderBadgeCollection(scope, badges) {
        badges = normalizeBadges(badges);
        renderBadgeList(`${scope}-badges-monthly`, badges.monthly, 'monthly');
        renderBadgeList(`${scope}-badges-general`, badges.general, 'general');
        showBadgeTab(scope, 'monthly');
    }
    function renderBadgeList(containerId, list, type) {
        const area = document.getElementById(containerId);
        if(!area) return;
        area.innerHTML = '';
        if(!list || list.length === 0) {
            const empty = document.createElement('div');
            empty.className = 'badge-empty';
            empty.innerText = type === 'monthly' ? 'Henüz aylık madalya yok.' : 'Şu an genel kupa yok.';
            area.appendChild(empty);
            return;
        }
        list.forEach(badge => {
            const card = document.createElement('div');
            card.className = `achievement-badge rank-${badge.rank || 3}`;
            card.innerHTML = `<div class="badge-symbol ${type === 'general' ? 'general-symbol' : ''}">${getBadgeSymbol(type, badge.rank)}</div><div class="badge-caption">${getBadgeCaption(badge)}</div>`;
            area.appendChild(card);
        });
    }
    function showBadgeTab(scope, tab) {
        ['monthly','general'].forEach(t => {
            const btn = document.getElementById(`${scope}-badge-tab-${t}`);
            const grid = document.getElementById(`${scope}-badges-${t}`);
            if(btn) btn.classList.toggle('active-cat', t === tab);
            if(grid) grid.style.display = t === tab ? 'grid' : 'none';
        });
    }
    async function computeBadgesForUser(uid) {
        const badges = emptyBadges();
        if(!db || !uid) return badges;
        const snap = await db.collection("leaderboards").get();
        const entries = [];
        snap.forEach(doc => {
            const d = doc.data();
            if(d && d.uid && d.category && d.part !== undefined && d.score !== undefined) entries.push(d);
        });
        const partGroups = {};
        entries.forEach(item => {
            const key = `${item.category}|${item.part}`;
            if(!partGroups[key]) partGroups[key] = [];
            partGroups[key].push(item);
        });
        Object.keys(partGroups).forEach(key => {
            const [category, partRaw] = key.split('|');
            const part = parseInt(partRaw);
            const partEntries = partGroups[key];
            const generalTop = sortBestEntries(partEntries).slice(0, 3);
            const generalIndex = generalTop.findIndex(x => x.uid === uid);
            if(generalIndex !== -1) badges.general.push({ id:`general-${category}-${part}`, type:'general', category, part, rank: generalIndex + 1 });

            const monthGroups = {};
            partEntries.forEach(item => {
                const ms = timestampToMillis(item.timestamp);
                if(!ms) return;
                const dt = new Date(ms);
                const year = dt.getFullYear();
                const month = dt.getMonth();
                if(!isCompletedMonth(year, month)) return;
                const monthKey = `${year}-${month}`;
                if(!monthGroups[monthKey]) monthGroups[monthKey] = [];
                monthGroups[monthKey].push(item);
            });
            Object.keys(monthGroups).forEach(monthKey => {
                const [yearRaw, monthRaw] = monthKey.split('-');
                const year = parseInt(yearRaw);
                const month = parseInt(monthRaw);
                const monthlyTop = sortBestEntries(monthGroups[monthKey]).slice(0, 3);
                const monthlyIndex = monthlyTop.findIndex(x => x.uid === uid);
                if(monthlyIndex !== -1) badges.monthly.push({ id:`monthly-${category}-${part}-${year}-${month}`, type:'monthly', category, part, year, month, rank: monthlyIndex + 1 });
            });
        });
        badges.monthly.sort((a,b) => (b.year - a.year) || (b.month - a.month) || a.category.localeCompare(b.category) || (a.part - b.part) || (a.rank - b.rank));
        badges.general.sort((a,b) => a.category.localeCompare(b.category) || (a.part - b.part) || (a.rank - b.rank));
        return badges;
    }
    async function syncBadgesForUser(uid, persist) {
        const badges = await computeBadgesForUser(uid);
        if(persist && currentDbUser && currentDbUser.uid === uid) {
            currentDbUser.badges = badges;
            try { await db.collection("users").doc(uid).set({ badges: badges }, {merge: true}); } catch(e) {}
        }
        return badges;
    }
    async function syncAndRenderMyBadges() {
        if(!currentDbUser) return;
        renderBadgeCollection('my', currentDbUser.badges || emptyBadges());
        try { const freshBadges = await syncBadgesForUser(currentDbUser.uid, true); renderBadgeCollection('my', freshBadges); } catch(e) {}
    }
    function escapeHtml(value) {
        const div = document.createElement('div');
        div.textContent = String(value ?? '');
        return div.innerHTML;
    }
    function setResultScreenMode(mode) {
        const resultScreen = document.getElementById('screen-result');
        if(!resultScreen) return;
        resultScreen.classList.remove('battle-result-screen');
        if(mode === 'battle') resultScreen.classList.add('battle-result-screen');
    }
    function renderBattleEndCelebration(playersForResult, options = {}) {
        let sourcePlayers = Array.isArray(playersForResult) ? playersForResult : [];
        if(sourcePlayers.length < 2 && Array.isArray(battlePlayers) && battlePlayers.length > sourcePlayers.length) {
            sourcePlayers = battlePlayers;
        }
        if(sourcePlayers.length < 2 && otData && Array.isArray(otData.players) && otData.players.length > sourcePlayers.length) {
            sourcePlayers = otData.players.map(p => ({...p, score: (otData.scores && otData.scores[p.uid]) || 0}));
        }

        const normalized = sourcePlayers.map((p, index) => ({
            name: p.name || p.nickname || `Oyuncu ${index + 1}`,
            avatar: p.avatar || p.emoji || "👾",
            score: Number(p.score || 0)
        })).sort((a,b) => b.score - a.score);

        const winner = normalized[0] || { name: "Kazanan", avatar: "🏆", score: 0 };
        const rankBadges = ["🥈", "🥉", "4."];
        const slots = normalized.slice(1, 4).map((data, index) => ({
            data,
            rank: index + 2,
            medal: rankBadges[index]
        }));

        setResultScreenMode('battle');
        document.getElementById('result-title').innerText = options.title || "Monster Battle";
        document.getElementById('result-score').style.display = 'none';
        document.getElementById('result-message').innerText = "";

        const podium = document.getElementById('tour-podium-area');
        podium.innerHTML = `
            <div class="battle-celebration-card">
                <div class="battle-celebration-kicker">${escapeHtml(options.kicker || "Monster Battle tamamlandı")}</div>
                <div class="battle-winner-box">
                    <div class="battle-winner-avatar">${escapeHtml(winner.avatar)}</div>
                    <div class="battle-winner-copy">
                        <div class="battle-winner-label">Kazanan</div>
                        <div class="battle-winner-name">${escapeHtml(winner.name)}</div>
                    </div>
                    <div class="battle-winner-score">${winner.score}<div style="font-size:0.7rem; color:inherit;">puan</div></div>
                </div>
                <div class="battle-podium-compact">
                    ${slots.map(slot => `
                        <div class="battle-rank-card rank-${slot.rank}">
                            <div class="battle-rank-medal">${slot.medal}</div>
                            <div class="battle-rank-avatar">${escapeHtml(slot.data.avatar)}</div>
                            <div class="battle-rank-name">${escapeHtml(slot.data.name)}</div>
                            <div class="battle-rank-score">${slot.data.score} puan</div>
                        </div>
                    `).join('')}
                </div>
            </div>`;
    }
    function setTournamentChampionCard(scope, winner, note) {
        const card = document.getElementById(`${scope}-champion-card`);
        if(!card) return;
        if(!winner) {
            card.style.display = 'none';
            card.innerHTML = '';
            return;
        }
        const winnerName = winner.name || winner.nickname || 'Kazanan';
        card.innerHTML = `
            <div class="champion-crown">👑</div>
            <div class="champion-label">Şampiyon</div>
            <div class="champion-name">${escapeHtml(winnerName)}</div>
            <div class="champion-note">${escapeHtml(note || 'Final tamamlandı')}</div>
        `;
        card.style.display = 'flex';
    }
    function scrollBracketToFinal(scope) {
        const screenId = scope === 'online' ? 'screen-online-bracket' : 'screen-local-bracket';
        const scroller = document.querySelector(`#${screenId} .bracket-scroll`);
        if(!scroller) return;
        requestAnimationFrame(() => {
            scroller.scrollLeft = scroller.scrollWidth;
            scroller.scrollTop = 0;
        });
    }
    function getActiveScreenId() { const active = document.querySelector('.screen.active'); return active ? active.id : null; }
    function isGameplayScreen(id) { return ['screen-flashcards','screen-online-game','screen-online-tour-match','screen-online-battle-arena','screen-battle-arena'].includes(id); }
    function isScreenActive(id, token) { return getActiveScreenId() === id && (token === undefined || token === screenNavToken); }
    function canSpeakOnActiveScreen() { return isGameplayScreen(getActiveScreenId()); }
    function scheduleScreenTimeout(screenId, cb, delay) {
        const token = screenNavToken;
        return setTimeout(() => { if(isScreenActive(screenId, token)) cb(); }, delay);
    }
    function clearGameTimers() {
        [flashcardSpeakTimeout, olNextQuestionTimeout, otmTransitionTimeout, onlineBattleNextTimeout, battleAlertTimeout, battleRevealTimeout, localTourReturnTimeout, onlineTourFinishTimeout, otmAnimTimeout, obattleAnimTimeout, bracketDrawResetTimeout, obHostTimer].forEach(t => { if(t) clearTimeout(t); });
        flashcardSpeakTimeout = olNextQuestionTimeout = otmTransitionTimeout = onlineBattleNextTimeout = null;
        battleAlertTimeout = battleRevealTimeout = localTourReturnTimeout = onlineTourFinishTimeout = null;
        otmAnimTimeout = obattleAnimTimeout = bracketDrawResetTimeout = obHostTimer = null;
        [timerInterval, olTimerInt, battleIntroInterval, bracketDrawInterval].forEach(i => { if(i) clearInterval(i); });
        timerInterval = olTimerInt = battleIntroInterval = bracketDrawInterval = null;
    }
    function stopGameplayRuntime(targetScreen) {
        clearGameTimers();
        activeArena = false;
        obLocalHasAnswered = true;
        otLocalHasAnswered = true;
        if(targetScreen === 'screen-home' || targetScreen === 'screen-login') {
            if(otListener) { try { otListener(); } catch(e){} otListener = null; }
            if(otMatchUnsub) { try { otMatchUnsub(); } catch(e){} otMatchUnsub = null; }
            currentWordObj = null;
            otCurrentPhase = '';
        }
        ['battle-intro-overlay','battle-reveal-overlay','battle-alert-overlay','obattle-result-overlay','ob-countdown-overlay','ob-waiting-overlay'].forEach(id => {
            const el = document.getElementById(id);
            if(el && (targetScreen === 'screen-home' || targetScreen === 'screen-login')) el.style.display = 'none';
        });
    }
    function shouldStopGameplayOnNavigation(fromScreen, toScreen) {
        return toScreen === 'screen-home' || toScreen === 'screen-login' || isGameplayScreen(fromScreen);
    }
    function stopTTS() { try { if(synth) synth.cancel(); if(window.AndroidTTS && typeof window.AndroidTTS.stop === 'function') window.AndroidTTS.stop(); } catch(e){} }
    function getBackTargetForScreen(id) {
        const map = {
            'screen-flashcards': 'screen-home',
            'screen-career-map': 'screen-home',
            'screen-tour-menu': 'screen-home',
            'screen-battle-menu': 'screen-home',
            'screen-create-room': 'screen-online-tour-hub',
            'screen-local-tour-setup': 'screen-tour-menu',
            'screen-local-bracket': 'screen-local-tour-setup',
            'screen-battle-setup': 'screen-battle-menu',
            'screen-online-result': 'screen-career-map',
            'screen-result': 'screen-home'
        };
        if(id === 'screen-online-tour-hub') return roomCreateType === 'battle' ? 'screen-battle-menu' : 'screen-tour-menu';
        return map[id] || null;
    }
    function updateScreenChrome(id) {
        const showFooter = id === 'screen-home';
        document.querySelectorAll('.support-floating-btn,.ig-floating-btn').forEach(el => {
            el.style.display = showFooter ? 'flex' : 'none';
        });
        const backBtn = document.getElementById('screen-back-btn');
        if(backBtn) backBtn.style.display = getBackTargetForScreen(id) ? 'flex' : 'none';
    }
    function goBackScreen() {
        const current = getActiveScreenId();
        const target = getBackTargetForScreen(current);
        if(!target) return;
        stopTTS();
        showScreen(target);
    }
    const ENGLISH_TTS_LANG = 'en-GB';
    function loadVoices(){ try{ const vs=synth.getVoices(); englishVoice=vs.find(v=>v.lang==='en-GB'&&v.name.includes('Google'))||vs.find(v=>v.lang==='en-GB')||vs.find(v=>v.lang==='en-US'&&v.name.includes('Google'))||vs.find(v=>v.lang==='en-US')||vs.find(v=>v.lang&&v.lang.startsWith('en'));}catch(e){} } 
    function speakCurrentWord(){ try{ if(!currentWordObj || !canSpeakOnActiveScreen()) return; const word = currentWordObj.word; if(window.AndroidTTS){ if(typeof window.AndroidTTS.setLanguage === "function") window.AndroidTTS.setLanguage(ENGLISH_TTS_LANG); if(typeof window.AndroidTTS.speakEnglish === "function"){ window.AndroidTTS.speakEnglish(word); return; } if(typeof window.AndroidTTS.speak === "function"){ window.AndroidTTS.speak(word); return; } } if(!synth) return; loadVoices(); synth.cancel(); const u = new SpeechSynthesisUtterance(word); u.lang = (englishVoice && englishVoice.lang) ? englishVoice.lang : ENGLISH_TTS_LANG; u.rate = 0.8; if(englishVoice) u.voice = englishVoice; synth.speak(u); }catch(e){} }
    
    function showScreen(id){ 
        if(id === 'screen-home' && !currentDbUser) return; 
        const previousScreen = getActiveScreenId();
        if(previousScreen !== id) {
            screenNavToken++;
            stopTTS();
            if(shouldStopGameplayOnNavigation(previousScreen, id)) stopGameplayRuntime(id);
        }
        document.querySelectorAll('.screen').forEach(s=>s.classList.remove('active')); 
        const targetEl = document.getElementById(id);
        targetEl.classList.add('active'); 
        if(id === 'screen-result') {
            targetEl.scrollTop = 0;
            const appEl = document.getElementById('app');
            if(appEl) appEl.scrollTop = 0;
        }
        updateScreenChrome(id);
        stopConfetti(); 
    }
    
    function goHome(){ stopTTS(); stopGameplayRuntime(currentDbUser ? 'screen-home' : 'screen-login'); if(currentDbUser) showScreen('screen-home'); else showScreen('screen-login'); }
    function toggleFullScreen(){ if(!document.fullscreenElement) document.documentElement.requestFullscreen().catch(e=>{}); else if(document.exitFullscreen) document.exitFullscreen(); }
    function startConfetti(){ stopConfetti(); }
    const canvas=document.getElementById("confetti-canvas"), ctx=canvas.getContext("2d"); let confettiActive=false, particles=[]; function stopConfetti(){ confettiActive=false; canvas.style.display='none'; }
    function loopConfetti(){ if(!confettiActive) return; ctx.clearRect(0,0,canvas.width,canvas.height); particles.forEach(p=>{ p.y+=p.v; if(p.y>canvas.height)p.y=-20; ctx.fillStyle=p.c; ctx.fillRect(p.x,p.y,p.s,p.s); }); requestAnimationFrame(loopConfetti); }
    function startTimer(s,id,cb){ clearInterval(timerInterval); const timerScreen = getActiveScreenId(); const timerToken = screenNavToken; let t=s; document.getElementById(id).innerText=t; timerInterval=setInterval(()=>{ if(!isScreenActive(timerScreen, timerToken)) { clearInterval(timerInterval); return; } t--; document.getElementById(id).innerText=t; if(t<=0){clearInterval(timerInterval);cb();} },1000); }
    const BANNED_NICKNAME_WORDS = ["amk","aq","orospu","siktir","sik","got","göt","pic","piç","ibne","yarrak","yarak","kahpe","puşt","pust","salak","aptal","mal","gerizekali","gerizekalı","fuck","shit","bitch","asshole"];
    function normalizeSearchText(text) { return String(text || '').toLocaleLowerCase('tr-TR').normalize('NFD').replace(/[\u0300-\u036f]/g,'').replace(/ı/g,'i').replace(/ğ/g,'g').replace(/ü/g,'u').replace(/ş/g,'s').replace(/ö/g,'o').replace(/ç/g,'c').trim(); }
    function makeNicknameKey(nick) { return normalizeSearchText(nick).replace(/[^a-z0-9]/g, ''); }
    function isNicknameAllowed(nick) {
        const visible = String(nick || '').trim();
        if(visible.length < 3 || visible.length > 15) return false;
        if(!/^[a-zA-Z0-9ğüşöçıİĞÜŞÖÇ _.-]+$/.test(visible)) return false;
        const key = makeNicknameKey(visible);
        if(key.length < 3) return false;
        return !BANNED_NICKNAME_WORDS.some(bad => key.includes(makeNicknameKey(bad)));
    }
    function openSupportModal() { document.getElementById('support-modal').style.display = 'flex'; }
    function closeSupportModal() { document.getElementById('support-modal').style.display = 'none'; }
    function watchSupportAd() {
        if(window.AndroidAds && typeof window.AndroidAds.showRewardedAd === 'function') {
            closeSupportModal();
            window.AndroidAds.showRewardedAd();
        } else {
            alert("Reklam sistemi APK tarafında AdMob ile bağlandığında burada çalışacak.");
        }
    }

    // AUTH
    function toggleAuthForms() { const loginBox = document.getElementById('login-form-box'); const regBox = document.getElementById('register-form-box'); const title = document.getElementById('auth-title'); if (loginBox.style.display !== 'none') { loginBox.style.display = 'none'; regBox.style.display = 'block'; title.innerText = "Yeni Kayıt Oluştur"; } else { loginBox.style.display = 'block'; regBox.style.display = 'none'; title.innerText = "Oturum Aç"; } }
    async function doLogin() { const email = document.getElementById('login-email').value.trim(); const pass = document.getElementById('login-pass').value.trim(); const remember = document.getElementById('remember-me').checked; if(!email || !pass) return alert("E-posta ve şifre giriniz!"); try { let persistence = remember ? firebase.auth.Auth.Persistence.LOCAL : firebase.auth.Auth.Persistence.SESSION; await auth.setPersistence(persistence); await auth.signInWithEmailAndPassword(email, pass); } catch(e) { alert("Giriş başarısız: " + e.message); } }
    async function doRegister() { const email = document.getElementById('reg-email').value.trim(); const pass = document.getElementById('reg-pass').value.trim(); const nick = document.getElementById('reg-nick').value.trim(); if(!email || pass.length < 6 || nick.length < 3) return alert("Bilgileri eksiksiz girin!"); if(!isNicknameAllowed(nick)) return alert("Bu kullanıcı adı uygun değil. Lütfen argo/küfür içermeyen, 3-15 karakterlik başka bir ad seçin."); try { const nickKey = makeNicknameKey(nick); const checkNick = await db.collection("users").where("nicknameKey", "==", nickKey).get(); const legacyNick = await db.collection("users").where("nickname", "==", nick).limit(1).get(); if(!checkNick.empty || !legacyNick.empty) return alert("Bu isim alınmış!"); await auth.setPersistence(firebase.auth.Auth.Persistence.LOCAL); const userCred = await auth.createUserWithEmailAndPassword(email, pass); await db.collection("users").doc(userCred.user.uid).set({ nickname: nick, nicknameKey: nickKey, email: email, avatar: "👾", claps: 0, createdAt: firebase.firestore.FieldValue.serverTimestamp(), progress: { "vocab": {}, "phrasal": {} }, badges: emptyBadges() }); alert("Aramıza hoş geldin " + nick + "!"); } catch(e) { alert("Kayıt hatası: " + e.message); } }
    async function doLogout() { try { stopTTS(); await auth.signOut(); currentDbUser = null; document.getElementById('top-bar').style.display = 'none'; showScreen('screen-login'); } catch(e) {} }
    async function resetPassword() { const email = document.getElementById('login-email').value.trim(); if(!email) return alert("Şifre sıfırlamak için önce e-posta adresinizi giriş kutusuna yazın!"); try { await auth.sendPasswordResetEmail(email); alert("Şifre sıfırlama bağlantısı e-posta adresine gönderildi."); } catch(e) { alert("Hata: " + e.message); } }

    if(auth) { 
        auth.onAuthStateChanged(async (user) => { 
            if (user) { 
                const docSnap = await db.collection("users").doc(user.uid).get(); 
                if (docSnap.exists) { 
                    currentDbUser = docSnap.data(); currentDbUser.uid = user.uid; 
                    if(!currentDbUser.progress) currentDbUser.progress = { "vocab": {}, "phrasal": {} };
                    currentDbUser.badges = normalizeBadges(currentDbUser.badges);
                    if(!currentDbUser.nicknameKey && currentDbUser.nickname) { currentDbUser.nicknameKey = makeNicknameKey(currentDbUser.nickname); try { await db.collection("users").doc(user.uid).set({ nicknameKey: currentDbUser.nicknameKey, claps: currentDbUser.claps || 0 }, {merge:true}); } catch(e) {} }
                    document.getElementById('top-avatar-btn').innerText = currentDbUser.avatar || "👾"; document.getElementById('top-username').innerText = currentDbUser.nickname; document.getElementById('top-level').innerText = "Seviye " + calculateLevel(currentDbUser.progress); document.getElementById('top-bar').style.display = 'flex'; showScreen('screen-home'); 
                } else {
                    currentDbUser = { nickname: user.email.split('@')[0], email: user.email, avatar: "👾", claps: 0, progress: { "vocab": {}, "phrasal": {} }, badges: emptyBadges() }; currentDbUser.nicknameKey = makeNicknameKey(currentDbUser.nickname); currentDbUser.uid = user.uid;
                    await db.collection("users").doc(user.uid).set({ ...currentDbUser, createdAt: firebase.firestore.FieldValue.serverTimestamp() });
                    document.getElementById('top-avatar-btn').innerText = currentDbUser.avatar; document.getElementById('top-username').innerText = currentDbUser.nickname; document.getElementById('top-level').innerText = "Seviye 0"; document.getElementById('top-bar').style.display = 'flex'; showScreen('screen-home');
                }
            } else { currentDbUser = null; document.getElementById('top-bar').style.display = 'none'; showScreen('screen-login'); } 
        }); 
    }

    // PROFIL VE ARKADAŞLIK
    function openProfileModal() { if(!currentDbUser) return; document.getElementById('prof-nickname').innerText = currentDbUser.nickname; let currentAv = currentDbUser.avatar || "👾"; document.querySelectorAll('.avatar-option').forEach(el => { el.classList.remove('selected'); if(el.innerText === currentAv) el.classList.add('selected'); }); renderBadgeCollection('my', currentDbUser.badges || emptyBadges()); document.getElementById('profile-modal').style.display = 'flex'; syncAndRenderMyBadges(); }
    function closeProfileModal() { document.getElementById('profile-modal').style.display = 'none'; }
    async function selectAvatar(emoji) { if(!currentDbUser) return; document.querySelectorAll('.avatar-option').forEach(el => el.classList.remove('selected')); event.target.classList.add('selected'); document.getElementById('top-avatar-btn').innerText = emoji; currentDbUser.avatar = emoji; try { await db.collection("users").doc(currentDbUser.uid).update({ avatar: emoji }); } catch(e) {} }
    function openAccountSettingsModal() { closeProfileModal(); document.getElementById('account-settings-modal').style.display = 'flex'; }
    function closeAccountSettingsModal() { document.getElementById('account-settings-modal').style.display = 'none'; }
    function openChangeNicknameModal() { closeAccountSettingsModal(); document.getElementById('new-nickname-input').value = currentDbUser ? (currentDbUser.nickname || "") : ""; document.getElementById('change-nickname-modal').style.display = 'flex'; }
    function closeChangeNicknameModal() { document.getElementById('change-nickname-modal').style.display = 'none'; }
    function openChangePasswordModal() { closeProfileModal(); closeAccountSettingsModal(); document.getElementById('new-password-input').value = ""; document.getElementById('change-pass-modal').style.display = 'flex'; }
    function closeChangePasswordModal() { document.getElementById('change-pass-modal').style.display = 'none'; }
    async function updateUserPassword() { const newPass = document.getElementById('new-password-input').value.trim(); if(newPass.length < 6) return alert("Şifre en az 6 hane olmalıdır!"); try { await auth.currentUser.updatePassword(newPass); alert("Şifren başarıyla güncellendi!"); closeChangePasswordModal(); } catch(e) { if(e.code === 'auth/requires-recent-login') { alert("Güvenlik nedeniyle çıkış yapıp tekrar girmelisin."); closeChangePasswordModal(); doLogout(); } else { alert("Hata: " + e.message); } } }
    function openDeleteAccountModal() { closeAccountSettingsModal(); document.getElementById('delete-account-password').value = ""; document.getElementById('delete-account-confirm-check').checked = false; toggleDeleteAccountButton(); document.getElementById('delete-account-modal').style.display = 'flex'; }
    function closeDeleteAccountModal() { document.getElementById('delete-account-modal').style.display = 'none'; }
    function toggleDeleteAccountButton() { const btn = document.getElementById('delete-account-final-btn'); const check = document.getElementById('delete-account-confirm-check'); if(btn && check) btn.disabled = !check.checked; }
    function authErrorMessage(e) {
        if(!e || !e.code) return e && e.message ? e.message : "Bilinmeyen hata";
        if(e.code === 'auth/wrong-password' || e.code === 'auth/invalid-credential') return "Şifre yanlış görünüyor.";
        if(e.code === 'auth/requires-recent-login') return "Güvenlik nedeniyle tekrar giriş yapman gerekiyor.";
        if(e.code === 'auth/too-many-requests') return "Çok fazla deneme yapıldı. Biraz bekleyip tekrar dene.";
        return e.message || e.code;
    }
    async function reauthenticateCurrentUser(password) {
        const user = auth && auth.currentUser;
        if(!user || !user.email) throw new Error("Aktif kullanıcı bulunamadı.");
        const credential = firebase.auth.EmailAuthProvider.credential(user.email, password);
        await user.reauthenticateWithCredential(credential);
    }
    async function commitDocsInBatches(docs, applyWrite) {
        let batch = db.batch();
        let count = 0;
        for(const doc of docs) {
            applyWrite(batch, doc);
            count++;
            if(count >= 450) {
                await batch.commit();
                batch = db.batch();
                count = 0;
            }
        }
        if(count > 0) await batch.commit();
    }
    async function updateDocsByQuery(query, data) {
        const snap = await query.get();
        if(snap.empty) return;
        await commitDocsInBatches(snap.docs, (batch, doc) => batch.set(doc.ref, data, {merge:true}));
    }
    async function deleteDocsByQuery(query) {
        const snap = await query.get();
        if(snap.empty) return;
        await commitDocsInBatches(snap.docs, (batch, doc) => batch.delete(doc.ref));
    }
    async function updateUserInFriendLists(uid, patch) {
        const snap = await db.collection("users").limit(500).get();
        const changes = [];
        snap.forEach(doc => {
            const data = doc.data();
            const friends = Array.isArray(data.friends) ? data.friends : [];
            let changed = false;
            const updated = friends.map(f => {
                if(f && f.uid === uid) {
                    changed = true;
                    return {...f, ...patch};
                }
                return f;
            });
            if(changed) changes.push({ref: doc.ref, friends: updated});
        });
        await commitDocsInBatches(changes, (batch, item) => batch.set(item.ref, {friends: item.friends}, {merge:true}));
    }
    async function removeUserFromFriendLists(uid) {
        const snap = await db.collection("users").limit(500).get();
        const changes = [];
        snap.forEach(doc => {
            if(doc.id === uid) return;
            const data = doc.data();
            const friends = Array.isArray(data.friends) ? data.friends : [];
            const filtered = friends.filter(f => f && f.uid !== uid);
            if(filtered.length !== friends.length) changes.push({ref: doc.ref, friends: filtered});
        });
        await commitDocsInBatches(changes, (batch, item) => batch.set(item.ref, {friends: item.friends}, {merge:true}));
    }
    async function updateNicknameReferences(uid, nickname, avatar) {
        await updateDocsByQuery(db.collection("leaderboards").where("uid", "==", uid), { nickname, avatar });
        await updateDocsByQuery(db.collection("friend_requests").where("fromUid", "==", uid), { fromName: nickname, fromAvatar: avatar });
        await updateDocsByQuery(db.collection("friend_requests").where("toUid", "==", uid), { toName: nickname, toAvatar: avatar });
        try { await updateUserInFriendLists(uid, { name: nickname, nickname, avatar }); } catch(e) {}
    }
    async function updateUserNickname() {
        if(!currentDbUser) return;
        const input = document.getElementById('new-nickname-input');
        const newNick = input.value.trim();
        if(!isNicknameAllowed(newNick)) return alert("Bu kullanıcı adı uygun değil. Lütfen argo/küfür içermeyen, 3-15 karakterlik başka bir ad seçin.");
        if(newNick === currentDbUser.nickname) { closeChangeNicknameModal(); return; }
        try {
            const uid = currentDbUser.uid;
            const nickKey = makeNicknameKey(newNick);
            let taken = false;
            const checkNick = await db.collection("users").where("nicknameKey", "==", nickKey).limit(5).get();
            checkNick.forEach(doc => { if(doc.id !== uid) taken = true; });
            const legacyNick = await db.collection("users").where("nickname", "==", newNick).limit(5).get();
            legacyNick.forEach(doc => { if(doc.id !== uid) taken = true; });
            if(taken) return alert("Bu isim alınmış!");
            const avatar = currentDbUser.avatar || "👾";
            await db.collection("users").doc(uid).set({ nickname: newNick, nicknameKey: nickKey }, {merge:true});
            currentDbUser.nickname = newNick;
            currentDbUser.nicknameKey = nickKey;
            document.getElementById('top-username').innerText = newNick;
            document.getElementById('prof-nickname').innerText = newNick;
            try { await updateNicknameReferences(uid, newNick, avatar); } catch(e) {}
            alert("Kullanıcı adın güncellendi!");
            closeChangeNicknameModal();
        } catch(e) { alert("Kullanıcı adı güncellenemedi: " + (e.message || e)); }
    }
    async function deleteAccountFirestoreData(uid) {
        await deleteDocsByQuery(db.collection("leaderboards").where("uid", "==", uid));
        await deleteDocsByQuery(db.collection("profile_claps").where("fromUid", "==", uid));
        await deleteDocsByQuery(db.collection("profile_claps").where("toUid", "==", uid));
        await deleteDocsByQuery(db.collection("friend_requests").where("fromUid", "==", uid));
        await deleteDocsByQuery(db.collection("friend_requests").where("toUid", "==", uid));
        try { await removeUserFromFriendLists(uid); } catch(e) {}
        await db.collection("users").doc(uid).delete();
    }
    async function deleteCurrentAccount() {
        if(!currentDbUser || !auth || !auth.currentUser) return alert("Aktif hesap bulunamadı.");
        const check = document.getElementById('delete-account-confirm-check');
        const pass = document.getElementById('delete-account-password').value.trim();
        const btn = document.getElementById('delete-account-final-btn');
        if(!check.checked) return alert("Silme onay kutucuğunu işaretlemelisin.");
        if(!pass) return alert("Güvenlik için şifreni yazmalısın.");
        const user = auth.currentUser;
        const uid = user.uid;
        try {
            btn.disabled = true;
            btn.innerText = "Hesap siliniyor...";
            await reauthenticateCurrentUser(pass);
            await deleteAccountFirestoreData(uid);
            await user.delete();
            currentDbUser = null;
            document.getElementById('top-bar').style.display = 'none';
            closeDeleteAccountModal();
            alert("Hesabın ve oyun ilerlemen silindi.");
            showScreen('screen-login');
        } catch(e) {
            btn.disabled = false;
            btn.innerText = "Hesabımı Kalıcı Olarak Sil";
            alert("Hesap silinemedi: " + authErrorMessage(e));
        }
    }
    
    async function openPublicProfile(uid, name, avatar, score) {
        if(uid === currentDbUser.uid) { openProfileModal(); return; }
        currentPublicProfileUid = uid;
        currentPublicProfileClaps = 0;
        const clapBtn = document.getElementById('pub-prof-clap-btn');
        if(clapBtn) { clapBtn.disabled = false; clapBtn.childNodes[0].nodeValue = "👏 "; }
        document.getElementById('pub-prof-avatar').innerText = avatar || "👾";
        document.getElementById('pub-prof-nickname').innerText = name;
        document.getElementById('pub-prof-level').innerText = "Seviye 0";
        document.getElementById('pub-prof-claps').innerText = "0";
        renderBadgeCollection('pub', emptyBadges());
        document.getElementById('pub-prof-add-btn').onclick = () => sendFriendRequest(uid, name, avatar);
        document.getElementById('public-profile-modal').style.display = 'flex';
        try {
            const userSnap = await db.collection("users").doc(uid).get();
            let userData = userSnap.exists ? userSnap.data() : {};
            document.getElementById('pub-prof-level').innerText = "Seviye " + calculateLevel(userData.progress || {});
            currentPublicProfileClaps = parseInt(userData.claps || 0);
            document.getElementById('pub-prof-claps').innerText = currentPublicProfileClaps;
            const clapDoc = await db.collection("profile_claps").doc(`${currentDbUser.uid}_${uid}`).get();
            if(clapDoc.exists && clapBtn) { clapBtn.disabled = true; clapBtn.childNodes[0].nodeValue = "👏 Tebrik Edildi "; }
            const freshBadges = await computeBadgesForUser(uid);
            renderBadgeCollection('pub', freshBadges);
        } catch(e) {}
    }
    function closePublicProfile() { document.getElementById('public-profile-modal').style.display = 'none'; }
    async function sendProfileClap() {
        if(!currentPublicProfileUid || !currentDbUser || currentPublicProfileUid === currentDbUser.uid) return;
        const clapBtn = document.getElementById('pub-prof-clap-btn');
        if(clapBtn) { clapBtn.disabled = true; clapBtn.childNodes[0].nodeValue = "👏 Gönderiliyor "; }
        try {
            const clapRef = db.collection("profile_claps").doc(`${currentDbUser.uid}_${currentPublicProfileUid}`);
            const userRef = db.collection("users").doc(currentPublicProfileUid);
            let alreadyClapped = false;
            await db.runTransaction(async (tx) => {
                const existing = await tx.get(clapRef);
                if(existing.exists) { alreadyClapped = true; return; }
                tx.set(clapRef, { fromUid: currentDbUser.uid, toUid: currentPublicProfileUid, timestamp: firebase.firestore.FieldValue.serverTimestamp() });
                tx.set(userRef, { claps: firebase.firestore.FieldValue.increment(1) }, {merge:true});
            });
            if(alreadyClapped) {
                if(clapBtn) { clapBtn.disabled = true; clapBtn.childNodes[0].nodeValue = "👏 Tebrik Edildi "; }
                return alert("Bu oyuncuyu zaten tebrik ettin.");
            }
            currentPublicProfileClaps++;
            document.getElementById('pub-prof-claps').innerText = currentPublicProfileClaps;
            if(clapBtn) { clapBtn.disabled = true; clapBtn.childNodes[0].nodeValue = "👏 Tebrik Edildi "; }
        } catch(e) {
            if(clapBtn) { clapBtn.disabled = false; clapBtn.childNodes[0].nodeValue = "👏 "; }
            alert("Tebrik gönderilemedi.");
        }
    }
    async function sendFriendRequest(toUid, toName, toAvatar) {
        if(!currentDbUser) return;
        if((currentDbUser.friends || []).find(f => f.uid === toUid)) return alert("Bu oyuncu zaten arkadaşın.");
        try {
            const existing = await db.collection("friend_requests").where("fromUid", "==", currentDbUser.uid).where("toUid", "==", toUid).where("status", "==", "pending").get();
            if(!existing.empty) return alert("Bu oyuncuya zaten istek gönderdin.");
            await db.collection("friend_requests").add({ fromUid: currentDbUser.uid, fromName: currentDbUser.nickname, fromAvatar: currentDbUser.avatar || '👾', toUid: toUid, toName: toName, toAvatar: toAvatar || '👾', status: 'pending', timestamp: firebase.firestore.FieldValue.serverTimestamp() });
            alert(toName + " adlı oyuncuya istek gönderildi!");
            closePublicProfile();
        } catch(e) { alert("İstek gönderilemedi."); }
    }
    function openFriendsModal() { if(!currentDbUser) return; document.getElementById('friends-modal').style.display = 'flex'; document.getElementById('friend-search-input').value=''; document.getElementById('friend-search-results').innerHTML=''; showFriendsTab('list'); }
    function closeFriendsModal() { document.getElementById('friends-modal').style.display = 'none'; }
    function showFriendsTab(tab) { document.querySelectorAll('#friends-modal .cat-btn').forEach(b => b.classList.remove('active-cat')); document.getElementById(`tab-friends-${tab}`).classList.add('active-cat'); loadFriendsData(tab); }
    function dedupeFriends(list) {
        const map = new Map();
        (list || []).forEach(f => {
            if(f && f.uid && f.uid !== currentDbUser.uid && !map.has(f.uid)) map.set(f.uid, {uid:f.uid, name:f.name || f.nickname || 'Oyuncu', avatar:f.avatar || '👾'});
        });
        return Array.from(map.values());
    }
    function queueFriendSearchSuggestions() {
        clearTimeout(friendSearchTimer);
        const input = document.getElementById('friend-search-input');
        const area = document.getElementById('friend-search-results');
        if(!input || !area) return;
        const q = input.value.trim();
        if(q.length < 2) { area.innerHTML = ""; return; }
        area.innerHTML = "<div class='badge-empty'>Öneriler hazırlanıyor...</div>";
        friendSearchTimer = setTimeout(() => searchFriendByName(true), 350);
    }
    function renderFriendRow(container, friend) {
        const row = document.createElement('div');
        row.className = 'friend-row';
        const left = document.createElement('div');
        left.style.display = 'flex'; left.style.alignItems = 'center'; left.style.gap = '8px';
        const av = document.createElement('span'); av.innerText = friend.avatar || '👾';
        const name = document.createElement('span'); name.innerText = friend.name || friend.nickname || 'Oyuncu';
        left.appendChild(av); left.appendChild(name);
        const btn = document.createElement('button');
        btn.className = 'btn btn-secondary btn-sm'; btn.style.width = 'auto'; btn.innerText = 'Profil';
        btn.onclick = () => openPublicProfile(friend.uid, friend.name || friend.nickname || 'Oyuncu', friend.avatar || '👾', 0);
        row.appendChild(left); row.appendChild(btn); container.appendChild(row);
    }
    async function syncAcceptedFriendsFromRequests() {
        const friendMap = new Map();
        dedupeFriends(currentDbUser.friends || []).forEach(f => friendMap.set(f.uid, f));
        let changed = false;
        const addFriend = (uid, name, avatar) => {
            if(!uid || uid === currentDbUser.uid || friendMap.has(uid)) return;
            friendMap.set(uid, {uid: uid, name: name || 'Oyuncu', avatar: avatar || '👾'});
            changed = true;
        };
        try {
            const incoming = await db.collection("friend_requests").where("toUid", "==", currentDbUser.uid).where("status", "==", "accepted").get();
            incoming.forEach(doc => { const req = doc.data(); addFriend(req.fromUid, req.fromName, req.fromAvatar); });
            const outgoing = await db.collection("friend_requests").where("fromUid", "==", currentDbUser.uid).where("status", "==", "accepted").get();
            outgoing.forEach(doc => { const req = doc.data(); addFriend(req.toUid, req.toName, req.toAvatar); });
        } catch(e) {}
        const friends = Array.from(friendMap.values());
        currentDbUser.friends = friends;
        if(changed) {
            try { await db.collection("users").doc(currentDbUser.uid).set({ friends: friends }, {merge:true}); } catch(e) {}
        }
        return friends;
    }
    async function loadFriendsData(tab = 'list') {
        const area = document.getElementById('friends-content-area');
        area.innerHTML = "<div style='text-align:center; color:#aaa;'>Yükleniyor...</div>";
        if(tab === 'list') {
            try {
                const userSnap = await db.collection("users").doc(currentDbUser.uid).get();
                if(userSnap.exists) {
                    const fresh = userSnap.data();
                    currentDbUser.friends = dedupeFriends(fresh.friends || []);
                }
            } catch(e) {}
            let friends = await syncAcceptedFriendsFromRequests();
            area.innerHTML = '';
            if(friends.length === 0) { area.innerHTML = "<div style='text-align:center; color:#aaa; margin-top:20px;'>Henüz arkadaşın yok. Oyuncu adı arayarak ekleyebilirsin!</div>"; return; }
            friends.forEach(f => renderFriendRow(area, f));
        } else {
            try {
                const snap = await db.collection("friend_requests").where("toUid", "==", currentDbUser.uid).where("status", "==", "pending").get();
                if(snap.empty) { document.getElementById('req-badge').style.display='none'; area.innerHTML = "<div style='text-align:center; color:#aaa; margin-top:20px;'>Bekleyen istek yok.</div>"; return; }
                document.getElementById('req-badge').innerText = snap.size; document.getElementById('req-badge').style.display='inline-block'; area.innerHTML = '';
                snap.forEach(doc => {
                    let req = doc.data();
                    const row = document.createElement('div'); row.className = 'friend-row'; row.style.flexDirection = 'column'; row.style.alignItems = 'stretch';
                    const who = document.createElement('div'); who.style.display='flex'; who.style.alignItems='center'; who.style.gap='8px'; who.innerHTML = `<span>${req.fromAvatar || '👾'}</span>`;
                    const nm = document.createElement('span'); nm.style.color='var(--accent)'; nm.innerText = req.fromName || 'Oyuncu'; who.appendChild(nm);
                    const actions = document.createElement('div'); actions.style.display='flex'; actions.style.gap='5px'; actions.style.width='100%';
                    const ok = document.createElement('button'); ok.className='btn btn-online btn-sm'; ok.style.flex='1'; ok.innerText='Kabul Et'; ok.onclick=()=>acceptFriend(doc.id, req.fromUid, req.fromName, req.fromAvatar);
                    const del = document.createElement('button'); del.className='btn btn-danger btn-sm'; del.style.flex='1'; del.innerText='Sil'; del.onclick=()=>rejectFriend(doc.id);
                    actions.appendChild(ok); actions.appendChild(del); row.appendChild(who); row.appendChild(actions); area.appendChild(row);
                });
            } catch(e) { area.innerHTML = "<div style='text-align:center; color:var(--danger);'>Hata oluştu.</div>"; }
        }
    }
    async function acceptFriend(reqId, fUid, fName, fAv) {
        try {
            await db.collection("friend_requests").doc(reqId).update({ status: 'accepted' });
            const fObj = {uid: fUid, name: fName, avatar: fAv || '👾'};
            const meObj = {uid: currentDbUser.uid, name: currentDbUser.nickname, avatar: currentDbUser.avatar || '👾'};
            await db.collection("users").doc(currentDbUser.uid).set({ friends: firebase.firestore.FieldValue.arrayUnion(fObj) }, {merge:true});
            await db.collection("users").doc(fUid).set({ friends: firebase.firestore.FieldValue.arrayUnion(meObj) }, {merge:true});
            currentDbUser.friends = dedupeFriends([...(currentDbUser.friends || []), fObj]);
            showFriendsTab('list');
            alert("Arkadaş eklendi!");
        } catch(e){ alert("Arkadaş eklenemedi."); }
    }
    async function rejectFriend(reqId) { try { await db.collection("friend_requests").doc(reqId).update({ status: 'rejected' }); loadFriendsData('reqs'); } catch(e){} }
    function nicknameDistance(a, b) {
        a = makeNicknameKey(a); b = makeNicknameKey(b);
        if(!a || !b) return 99;
        const dp = Array.from({length:a.length+1}, () => Array(b.length+1).fill(0));
        for(let i=0;i<=a.length;i++) dp[i][0]=i;
        for(let j=0;j<=b.length;j++) dp[0][j]=j;
        for(let i=1;i<=a.length;i++) {
            for(let j=1;j<=b.length;j++) {
                dp[i][j] = Math.min(dp[i-1][j]+1, dp[i][j-1]+1, dp[i-1][j-1] + (a[i-1] === b[j-1] ? 0 : 1));
            }
        }
        return dp[a.length][b.length];
    }
    function addFriendSearchCandidate(map, doc, key, loose) {
        const u = doc.data();
        const name = u.nickname || "Oyuncu";
        const candidateKey = u.nicknameKey || makeNicknameKey(name);
        if(doc.id === currentDbUser.uid || !candidateKey) return;
        const score = candidateKey.startsWith(key) ? 0 : candidateKey.includes(key) ? 1 : (key.length >= 4 && nicknameDistance(candidateKey, key) <= 2 ? 2 : 9);
        if(!loose && score > 0) return;
        if(score > 2) return;
        if(!map.has(doc.id)) map.set(doc.id, {uid: doc.id, name: name, avatar: u.avatar || "👾", score: score});
    }
    async function searchFriendByName(isSuggestion = false) {
        const q = document.getElementById('friend-search-input').value.trim();
        const area = document.getElementById('friend-search-results');
        if(!q) { area.innerHTML = isSuggestion ? "" : "<div class='badge-empty'>Aramak için oyuncu adı yaz.</div>"; return; }
        area.innerHTML = "<div class='badge-empty'>Aranıyor...</div>";
        try {
            const key = makeNicknameKey(q);
            if(key.length < 2) { area.innerHTML = "<div class='badge-empty'>En az 2 karakter yaz.</div>"; return; }
            const results = new Map();
            try {
                const snap = await db.collection("users").orderBy("nicknameKey").startAt(key).endAt(key + "\uf8ff").limit(10).get();
                snap.forEach(doc => addFriendSearchCandidate(results, doc, key, false));
            } catch(e) {}
            if(results.size < 10) {
                try {
                    const looseSnap = await db.collection("users").limit(80).get();
                    looseSnap.forEach(doc => addFriendSearchCandidate(results, doc, key, true));
                } catch(e) {}
            }
            area.innerHTML = "";
            if(results.size === 0) { area.innerHTML = "<div class='badge-empty'>Bu isimle alakalı oyuncu bulunamadı.</div>"; return; }
            Array.from(results.values()).sort((a,b) => a.score - b.score || a.name.localeCompare(b.name, 'tr')).slice(0, 10).forEach(friend => renderFriendRow(area, friend));
            if(!area.children.length) area.innerHTML = "<div class='badge-empty'>Kendi profilin dışında sonuç yok.</div>";
        } catch(e) { area.innerHTML = "<div class='badge-empty'>Arama yapılamadı.</div>"; }
    }

    // ==========================================
    // CHALLENGE MODE & LİDERLİK TABLOSU
    // ==========================================
    function setCategory(cat){ currentCategory=cat; if(cat === 'vocab') { currentData = vocabData; } else { currentData = phrasalData; } document.querySelectorAll('.cat-btn').forEach(b=>b.classList.remove('active-cat')); document.getElementById(`btn-cat-${cat}`).classList.add('active-cat'); updateUnitDropdown(); }
    function updateUnitDropdown(){ const sel=document.getElementById('unit-select'); sel.innerHTML=''; const keys = Object.keys(currentData); if (keys.length === 0) return; const pre = (currentCategory === 'vocab') ? 'Vocabulary Part' : 'Phrasal Verb Part'; keys.forEach(k => { const opt = document.createElement('option'); opt.value = k; opt.innerText = `${pre} ${k}`; sel.appendChild(opt); }); sel.selectedIndex = 0; }
    
    // GÜVENLİ KELİME ÇEKME
    function getSelectedWords(overrideCat, overrideUnit){ 
        let catData = currentData;
        if(overrideCat) { catData = overrideCat === 'vocab' ? vocabData : phrasalData; }
        const sel=document.getElementById('unit-select'); 
        let u= overrideUnit || (sel ? sel.value : "1"); 
        let raw = catData[u] || catData[String(u)]; 
        if(!raw) return []; return parseDataSafe(raw); 
    }
    
    function getAvailableWord(modePref) { 
        let pool = makeQuestionPool(gameWords, modePref).filter(item => !askedQuestions.includes(item.wordObj.word + "-" + item.type)); 
        if (pool.length === 0) { 
            askedQuestions = []; 
            pool = makeQuestionPool(gameWords, modePref);
        } 
        let picked = pool[Math.floor(Math.random() * pool.length)]; askedQuestions.push(picked.wordObj.word + "-" + picked.type); return picked; 
    }

    function setOnlineCategory(cat) { onlineCategory = cat; document.getElementById('ol-cat-vocab').classList.remove('active-cat'); document.getElementById('ol-cat-phrasal').classList.remove('active-cat'); document.getElementById(`ol-cat-${cat}`).classList.add('active-cat'); renderCareerMap(); }
    function openCareerMap() { if(!currentDbUser) { alert("Lütfen giriş yapın!"); return doLogout(); } setOnlineCategory('vocab'); showScreen('screen-career-map'); }
    function renderCareerMap() {
        const container = document.getElementById('map-container'); container.innerHTML = ''; let onlineData = onlineCategory === 'vocab' ? vocabData : phrasalData; const partsCount = Object.keys(onlineData).length;
        if(partsCount === 0) { container.innerHTML = `<h3 style="color:var(--accent); text-align:center; padding:20px;">Veri Bulunamadı.</h3>`; return; }
        const progressData = currentDbUser.progress[onlineCategory] || {}; const sceneries = ['🌲', '⛰️', '☁️', '🍄', '🏕️', '🌴', '🏰', '🗿', '⛺', '🪵']; let maxUnlocked = 1;
        Object.keys(onlineData).forEach((k, idx) => {
            let i = idx + 1; const node = document.createElement('div'); node.className = 'level-node'; node.id = `level-node-${i}`;
            let isUnlocked = (i === 1) || (progressData[i-1] && progressData[i-1].stars > 0); if(isUnlocked) maxUnlocked = i; let myStars = progressData[i] ? progressData[i].stars : 0;
            let starsHtml = `<div class="level-stars"><span class="star ${myStars >= 1 ? 'earned' : ''}">★</span><span class="star ${myStars >= 2 ? 'earned' : ''}">★</span><span class="star ${myStars >= 3 ? 'earned' : ''}">★</span></div>`;
            let s1 = sceneries[Math.floor(Math.random() * sceneries.length)]; let decorHtml = `<div class="map-decor" style="${i%2===1 ? 'top: -60px;' : 'bottom: -60px;'} right: -20px;">${s1}</div>`;
            node.innerHTML = `${decorHtml}<div class="path-line"></div><div class="level-circle ${!isUnlocked ? 'locked' : ''}" onclick="clickLevel(${i}, ${isUnlocked}, ${myStars})">${isUnlocked ? starsHtml : '🔒'}<div>P${i}</div></div><div class="leaderboard-btn" onclick="openLeaderboard(${i})" title="Sıralama">🏆</div>`; container.appendChild(node);
        });
        setTimeout(() => { const targetNode = document.getElementById(`level-node-${maxUnlocked}`); if(targetNode) { container.scrollTo({ left: targetNode.offsetLeft - (container.clientWidth / 2) + 40, behavior: 'smooth' }); } }, 200);
    }
    function clickLevel(partNum, isUnlocked, myStars) {
        if(!isUnlocked) return alert("Bu bölüm kilitli!"); olPart = partNum; const prog = (currentDbUser.progress[onlineCategory] || {})[partNum] || {highScore: 0};
        document.getElementById('li-title').innerText = "Bölüm " + partNum; document.getElementById('li-stars').innerHTML = `<span class="star ${myStars >= 1 ? 'earned' : ''}">★</span><span class="star ${myStars >= 2 ? 'earned' : ''}">★</span><span class="star ${myStars >= 3 ? 'earned' : ''}">★</span>`; document.getElementById('li-highscore').innerText = prog.highScore || 0;
        document.getElementById('btn-mode-1').innerText = "1. Yıldız (Eng-Tr) " + (myStars>=1?"✅":""); document.getElementById('btn-mode-2').innerText = "2. Yıldız (Eng-Eng) " + (myStars>=2?"✅":"");
        let btnChal = document.getElementById('btn-mode-3'); if(myStars >= 2) { btnChal.disabled = false; btnChal.innerText = "🔥 CHALLENGE (Rekor) " + (myStars>=3?"✅":""); btnChal.classList.remove('btn-secondary'); btnChal.classList.add('btn-arena'); } else { btnChal.disabled = true; btnChal.innerText = "🔒 Challenge (Kilidi Aç)"; btnChal.classList.add('btn-secondary'); btnChal.classList.remove('btn-arena'); }
        document.getElementById('level-info-modal').style.display = 'flex';
    }
    function closeLevelInfo() { document.getElementById('level-info-modal').style.display = 'none'; }
    function showRuleInfo(mode) {
        let isVocab = (onlineCategory === 'vocab'); let qCount = isVocab ? (mode === 3 ? 80 : 40) : (mode === 3 ? 40 : 20); let lives = (mode === 3) ? 1 : (isVocab ? 3 : 2); let req = isVocab ? 30 : (mode === 3 ? 30 : 15);
        let title = mode === 1 ? "1. Yıldız (Eng-Tr)" : mode === 2 ? "2. Yıldız (Eng-Eng)" : "🔥 Challenge Modu"; let desc = `<b>Soru Sayısı:</b> ${qCount}<br><b>Can Hakkı:</b> ${lives}<br><b>Geçme Şartı:</b> En az ${req} Doğru<br><br>${mode === 3 ? "Zamana karşı yarışırsın, kalan saniyeler puanına eklenir." : "Hedefi tamamla!"}`;
        document.getElementById('rule-title').innerText = title; document.getElementById('rule-desc').innerHTML = desc; document.getElementById('rule-info-modal').style.display = 'flex';
    }
    function closeRuleInfo() { document.getElementById('rule-info-modal').style.display = 'none'; }
    function startOnlineLevel(mode) {
        closeLevelInfo(); showScreen('screen-online-game'); olTargetStar = mode; 
        
        gameWords = getSelectedWords(onlineCategory, olPart); 
        if(!gameWords || gameWords.length === 0) return alert("Bu bölümde kelime yok!");
        
        olQuestions = []; olScore = 0; olCorrect = 0; olQIndex = 0; let isVocab = (onlineCategory === 'vocab'); let totalQs = 0;
        if (isVocab) { if(mode === 1 || mode === 2) { olLives = 3; olReqCorrect = 30; totalQs = 40; } else { olLives = 1; olReqCorrect = 30; totalQs = 80; } } else { if(mode === 1 || mode === 2) { olLives = 2; olReqCorrect = 15; totalQs = 20; } else { olLives = 1; olReqCorrect = 30; totalQs = 40; } }
        document.getElementById('ol-score-display').style.display = (mode === 3) ? 'block' : 'none'; document.getElementById('ol-score-display').innerText = "Puan: 0"; updateHearts();
        
        askedQuestions = []; 
        for(let i=0; i<totalQs; i++) {
            let itemData = getAvailableWord(mode === 1 ? 'tr' : (mode === 2 ? 'syn' : 'mix'));
            const w = itemData.wordObj; const t = itemData.type; 
            olQuestions.push(buildQuestionObject(w, t, gameWords, onlineCategory)); 
        }
        loadOlQuestion();
    }
    
    function updateHearts() { let h = ""; for(let i=0; i<olLives; i++) h += "❤️"; document.getElementById('ol-lives').innerText = h || "💔"; }
    function loadOlQuestion() {
        if(!isScreenActive('screen-online-game')) return;
        if(olLives <= 0 || olQIndex >= olQuestions.length) { finishOlGame(); return; }
        const q = olQuestions[olQIndex]; currentWordObj = q.wordObj; document.getElementById('ol-progress').innerText = `${olQIndex + 1}/${olQuestions.length}`; document.getElementById('ol-question').innerText = q.wordObj.word; document.getElementById('ol-feedback').innerText = "";
        const g = document.getElementById('ol-options'); g.innerHTML = ''; q.opts.forEach(txt => { const b = document.createElement('button'); b.className = 'btn option-btn'; b.innerText = txt; b.onclick = () => handleOlAnswer(b, txt, q.correct); g.appendChild(b); });
        try{ speakCurrentWord(); } catch(e){} olStartTime = Date.now(); startOlTimer();
    }
    function startOlTimer() {
        clearInterval(olTimerInt); document.getElementById('ol-timer-fill').style.transition = "none"; document.getElementById('ol-timer-fill').style.width = "100%"; clearTimeout(otmAnimTimeout); otmAnimTimeout = scheduleScreenTimeout('screen-online-game', ()=>{ document.getElementById('ol-timer-fill').style.transition = "width 10s linear"; document.getElementById('ol-timer-fill').style.width = "0%"; }, 50);
        olTimerInt = setInterval(() => { if(!isScreenActive('screen-online-game')) { clearInterval(olTimerInt); return; } let elapsed = Date.now() - olStartTime; let left = 10000 - elapsed; if(left <= 0) { clearInterval(olTimerInt); document.getElementById('ol-timer-text').innerText = "0.00"; handleOlAnswer(null, null, olQuestions[olQIndex].correct); } else { document.getElementById('ol-timer-text').innerText = (left / 1000).toFixed(2); } }, 50);
    }
    function handleOlAnswer(btn, ans, cor) {
        if(!isScreenActive('screen-online-game')) return;
        clearInterval(olTimerInt); document.getElementById('ol-timer-fill').style.width = "0%"; document.querySelectorAll('#ol-options .option-btn').forEach(b => b.disabled = true);
        let elapsed = Date.now() - olStartTime; let left = 10000 - elapsed;
        if(ans === cor) { if(btn) btn.classList.add('correct'); document.getElementById('ol-feedback').innerText = "Harika!"; olCorrect++; if(olTargetStar === 3 && left > 0) { olScore += Math.floor(left / 10); document.getElementById('ol-score-display').innerText = "Puan: " + olScore; } } else { if(btn) btn.classList.add('wrong'); document.querySelectorAll('#ol-options .option-btn').forEach(b => { if(b.innerText === cor) b.classList.add('correct') }); document.getElementById('ol-feedback').innerText = "Yanlış!"; olLives--; updateHearts(); }
        clearTimeout(olNextQuestionTimeout);
        olNextQuestionTimeout = scheduleScreenTimeout('screen-online-game', () => { if(olLives <= 0) finishOlGame(); else { olQIndex++; loadOlQuestion(); } }, 1500);
    }
    function abandonOnlineGame() { clearInterval(olTimerInt); clearTimeout(olNextQuestionTimeout); olLives = 0; finishOlGame(); }
    async function finishOlGame() {
        clearInterval(olTimerInt); showScreen('screen-online-result');
        let isWin = (olCorrect >= olReqCorrect); document.getElementById('ol-res-title').innerText = isWin ? "Görev Başarılı!" : "Görev Başarısız..."; document.getElementById('ol-res-title').style.color = isWin ? "var(--correct)" : "var(--danger)"; document.getElementById('ol-res-correct').innerText = `${olCorrect} / ${olQuestions.length}`;
        let prog = currentDbUser.progress[onlineCategory] || {}; if(!prog[olPart]) prog[olPart] = {stars:0, highScore:0}; let oldStars = prog[olPart].stars; let earnedStars = oldStars; if(isWin) { earnedStars = Math.max(oldStars, olTargetStar); }
        document.getElementById('ol-res-stars').innerHTML = `<span class="star ${earnedStars >= 1 ? 'earned' : ''}">★</span><span class="star ${earnedStars >= 2 ? 'earned' : ''}">★</span><span class="star ${earnedStars >= 3 ? 'earned' : ''}">★</span>`;
        const stTitle = document.getElementById('ol-res-score-title'); const stVal = document.getElementById('ol-res-score'); const rankBox = document.getElementById('ol-res-ranks');
        if(olTargetStar === 3) { stTitle.style.display = 'block'; stVal.style.display = 'block'; stVal.innerText = olScore; rankBox.style.display = 'block'; rankBox.innerHTML = "Sıralamalar Hesaplanıyor... ⏳"; } else { stTitle.style.display = 'none'; stVal.style.display = 'none'; rankBox.style.display = 'none'; }
        let newHigh = Math.max(prog[olPart].highScore || 0, olScore); prog[olPart] = { stars: earnedStars, highScore: newHigh }; currentDbUser.progress[onlineCategory] = prog;
        let newLevel = calculateLevel(currentDbUser.progress); document.getElementById('top-level').innerText = "Seviye " + newLevel;
        try {
            await db.collection("users").doc(currentDbUser.uid).set({ progress: currentDbUser.progress }, {merge: true});
            if(olTargetStar === 3 && olScore > 0) {
                await db.collection("leaderboards").add({ category: onlineCategory, part: olPart, uid: currentDbUser.uid, nickname: currentDbUser.nickname, avatar: currentDbUser.avatar || "👾", score: olScore, timestamp: firebase.firestore.FieldValue.serverTimestamp() });
                await calculateAndShowResultRanks(olScore);
                await syncBadgesForUser(currentDbUser.uid, true);
            }
        } catch(e) {}
    }
    async function calculateAndShowResultRanks(myScore) {
        try {
            let snap = await db.collection("leaderboards").where("category", "==", onlineCategory).where("part", "==", olPart).get(); let allData = []; snap.forEach(d => allData.push(d.data()));
            let now = new Date(); let startOfMonth = new Date(now.getFullYear(), now.getMonth(), 1).getTime();
            function getRank(dataList) {
                let uniqueMap = new Map(); dataList.forEach(item => { if(!uniqueMap.has(item.uid)) uniqueMap.set(item.uid, item); else if(item.score > uniqueMap.get(item.uid).score) uniqueMap.set(item.uid, item); });
                if(!uniqueMap.has(currentDbUser.uid) || myScore > uniqueMap.get(currentDbUser.uid).score) { uniqueMap.set(currentDbUser.uid, {uid: currentDbUser.uid, score: myScore}); }
                let sorted = Array.from(uniqueMap.values()).sort((a,b) => b.score - a.score); let index = sorted.findIndex(x => x.uid === currentDbUser.uid); return index !== -1 ? index + 1 : "-";
            }
            let monthlyList = allData.filter(i => { const ms = timestampToMillis(i.timestamp); return ms && ms >= startOfMonth; }); let mRank = getRank(monthlyList); let aRank = getRank(allData);
            document.getElementById('ol-res-ranks').innerHTML = `Aylık Sıran: <span style="color:gold;">${mRank}.</span> <br>Genel Sıran: <span style="color:gold;">${aRank}.</span>`;
        } catch(e) {}
    }
    async function openLeaderboard(partNum) { currentLeaderboardPart = partNum; document.getElementById('lb-title').innerText = `Bölüm ${partNum} Sıralaması`; document.getElementById('leaderboard-overlay').style.display = 'flex'; document.getElementById('lb-podium-area').style.display = 'none'; document.getElementById('lb-list').innerHTML = "<div style='text-align:center; color:#aaa;'>Yükleniyor...</div>"; try { const snapshot = await db.collection("leaderboards").where("category", "==", onlineCategory).where("part", "==", partNum).get(); lbDataCache = []; snapshot.forEach(doc => { lbDataCache.push(doc.data()); }); showLbTab('alltime'); } catch(e) {} }
    function closeLeaderboard() { document.getElementById('leaderboard-overlay').style.display = 'none'; }
    function showLbTab(tab) {
        document.querySelectorAll('#leaderboard-overlay .cat-btn').forEach(b => b.classList.remove('active-cat')); document.getElementById(`tab-${tab}`).classList.add('active-cat');
        let now = new Date(); let filtered = [];
        if (tab === 'monthly') { let startOfMonth = new Date(now.getFullYear(), now.getMonth(), 1).getTime(); filtered = lbDataCache.filter(item => { const ms = timestampToMillis(item.timestamp); return ms && ms >= startOfMonth; }); } else { filtered = [...lbDataCache]; }
        let uniqueMap = new Map(); filtered.forEach(item => { if(!uniqueMap.has(item.uid)) uniqueMap.set(item.uid, item); else if(item.score > uniqueMap.get(item.uid).score) uniqueMap.set(item.uid, item); }); filtered = Array.from(uniqueMap.values()).sort((a,b) => b.score - a.score);
        const podiumArea = document.getElementById('lb-podium-area'); const listArea = document.getElementById('lb-list');
        if(filtered.length === 0) { podiumArea.style.display = 'none'; listArea.innerHTML = "<div style='text-align:center; color:#aaa; margin-top:20px;'>Kayıt yok.</div>"; return; }
        
        podiumArea.style.display = 'flex'; podiumArea.innerHTML = ''; let top3 = filtered.slice(0, 3);
        if(top3[1]) podiumArea.innerHTML += `<div class="podium-bar p-rank-2" onclick="openPublicProfile('${top3[1].uid}','${top3[1].nickname}','${top3[1].avatar}',${top3[1].score})"><div class="avatar">${top3[1].avatar || "👾"}</div><div class="p-name">${top3[1].nickname}</div><div class="p-score-txt">${top3[1].score}</div></div>`;
        if(top3[0]) podiumArea.innerHTML += `<div class="podium-bar p-rank-1" onclick="openPublicProfile('${top3[0].uid}','${top3[0].nickname}','${top3[0].avatar}',${top3[0].score})"><div class="avatar">${top3[0].avatar || "👾"}</div><div class="p-name">${top3[0].nickname}</div><div class="p-score-txt">${top3[0].score}</div></div>`;
        if(top3[2]) podiumArea.innerHTML += `<div class="podium-bar p-rank-3" onclick="openPublicProfile('${top3[2].uid}','${top3[2].nickname}','${top3[2].avatar}',${top3[2].score})"><div class="avatar">${top3[2].avatar || "👾"}</div><div class="p-name">${top3[2].nickname}</div><div class="p-score-txt">${top3[2].score}</div></div>`;
        
        let html = ""; filtered.slice(3, 10).forEach((item, index) => { let rank = index + 4; let isMe = item.uid === currentDbUser.uid; html += `<div class="lb-row ${isMe ? 'me' : ''}" onclick="openPublicProfile('${item.uid}','${item.nickname}','${item.avatar}',${item.score})"><div style="display:flex; gap:10px; align-items:center;"><span class="lb-rank">${rank}</span><span>${item.nickname}</span></div><span class="lb-score">${item.score}</span></div>`; });
        let myIndex = filtered.findIndex(item => item.uid === currentDbUser.uid);
        if (myIndex !== -1 && currentDbUser) { let myItem = filtered[myIndex]; html += `<div class="my-rank-box"><div class="my-rank-title">Sizin Sıranız: ${myIndex+1}.</div><div class="my-rank-details"><span>${myItem.nickname}</span><span>${myItem.score} Puan</span></div></div>`; } 
        else if (currentDbUser) { html += `<div class="my-rank-box"><div class="my-rank-title">Henüz Sıralamanız Yok</div><div class="my-rank-details"><span>${currentDbUser.nickname}</span><span>0 Puan</span></div></div>`; }
        listArea.innerHTML = html;
    }

    // ==========================================
    // KARTLAR
    // ==========================================
    function startFlashcards(){ gameWords=getSelectedWords(); if(gameWords.length===0) return alert("Veri Yok!"); fcIndex=0; loadFC(0); showScreen('screen-flashcards'); }
    function loadFC(i){ const it=gameWords[i]; currentWordObj=it; document.getElementById('fc-word').innerText=it.word; document.getElementById('fc-meaning').innerText=it.meaning; document.getElementById('fc-synonym').innerText=it.syn; document.getElementById('flashcard').classList.remove('flipped'); clearTimeout(flashcardSpeakTimeout); flashcardSpeakTimeout = scheduleScreenTimeout('screen-flashcards', speakCurrentWord, 400); }
    function flipCard(){ document.getElementById('flashcard').classList.toggle('flipped'); }
    function nextCard(){ if(fcIndex<gameWords.length-1){ fcIndex++; loadFC(fcIndex); } }
    function prevCard(){ if(fcIndex>0){ fcIndex--; loadFC(fcIndex); } }

    function openTournamentMenu() { showScreen('screen-tour-menu'); }
    function openBattleMenu() { showScreen('screen-battle-menu'); }

    // ==========================================
    // ORTAK ONLINE HUB (TURNUVA VE BATTLE)
    // ==========================================
    function openOnlineHub(type) { 
        roomCreateType = type;
        document.getElementById('hub-title').innerText = type === 'tour' ? "🌍 Online Turnuva" : "🌍 Online Monster Battle";
        showScreen('screen-online-tour-hub'); 
    }
    
    function openCreateOnlineRoom() { 
        if (roomCreateType === 'battle') {
            document.getElementById('cr-tour-options').style.display = 'none';
            document.getElementById('cr-battle-options').style.display = 'block';
            document.getElementById('cr-title').innerText = "Online Battle Ayarları";
        } else {
            document.getElementById('cr-tour-options').style.display = 'block';
            document.getElementById('cr-battle-options').style.display = 'none';
            document.getElementById('cr-title').innerText = "Online Turnuva Ayarları";
        }
        updateRoomUnitSelect();
        showScreen('screen-create-room'); 
    }
    
    function updateRoomUnitSelect() {
        const cat = document.getElementById('create-room-cat').value;
        const sel = document.getElementById('create-room-unit'); sel.innerHTML = '';
        const catData = cat === 'vocab' ? vocabData : phrasalData; const keys = Object.keys(catData);
        if(keys.length === 0) return; const pre = cat === 'vocab' ? 'Vocab Part' : 'Phrasal Part';
        keys.forEach(k => { sel.innerHTML += `<option value="${k}">${pre} ${k}</option>`; }); sel.selectedIndex = 0;
    }

    async function createOnlineRoom() { 
        const tName = document.getElementById('create-room-name').value.trim() || "YDT Kapışması"; 
        const isPlayer = document.getElementById('create-room-isplayer').checked; 
        const qType = document.getElementById('create-room-type').value; 
        const cat = document.getElementById('create-room-cat').value;
        const unit = document.getElementById('create-room-unit').value;
        const targetScore = parseInt(document.getElementById('create-room-target').value) || 20;

        otCode = Math.random().toString(36).substring(2, 7).toUpperCase(); otIsAdmin = true; 
        let initialPlayers = []; 
        if(roomCreateType === 'battle' || isPlayer) { initialPlayers.push({ uid: currentDbUser.uid, name: currentDbUser.nickname, avatar: currentDbUser.avatar || "👾" }); }
        
        let qs = []; for(let i=0; i<100; i++) qs.push(Math.floor(Math.random() * 100000));
        
        otData = { 
            code: otCode, name: tName, hostUid: currentDbUser.uid, status: 'lobby', 
            type: roomCreateType, players: initialPlayers, scores: {}, nextTime: 0, questionSeeds: qs,
            gameConfig: { cat: cat, unit: unit, qType: qType, targetScore: targetScore }
        }; 
        
        if (roomCreateType === 'tour') { otData.bracket = "[]"; otData.round = 0; } 
        else { otData.currentQIndex = 0; otData.answers = {}; otData.showResult = false; }

        try { 
            await db.collection("tournaments").doc(otCode).set(otData); 
            document.getElementById('admin-tour-name').innerText = tName; 
            document.getElementById('admin-tour-code').innerText = otCode; 
            if(roomCreateType === 'battle') {
                document.getElementById('admin-draw-btn').style.display = 'none'; document.getElementById('admin-start-battle-btn').style.display = 'inline-block';
            } else {
                document.getElementById('admin-draw-btn').style.display = 'inline-block'; document.getElementById('admin-start-battle-btn').style.display = 'none';
            }
            listenToOnlineRoom(); showScreen('screen-admin-lobby'); 
        } catch(e) { alert("Oda oluşturulamadı!"); } 
    }
    
    async function joinOnlineRoom() { 
        const codeInput = document.getElementById('join-room-code').value.trim().toUpperCase(); if(codeInput.length !== 5) return alert("Geçerli bir kod girin!"); 
        try { 
            const docRef = db.collection("tournaments").doc(codeInput); const doc = await docRef.get(); 
            if(!doc.exists) return alert("Oda bulunamadı!"); 
            let d = doc.data();
            if(d.type === 'battle' && d.players.length >= 4) return alert("Bu oda dolu! (Maks 4 kişi)");

            otCode = codeInput; otIsAdmin = false; roomCreateType = d.type;
            await docRef.update({ players: firebase.firestore.FieldValue.arrayUnion({ uid: currentDbUser.uid, name: currentDbUser.nickname, avatar: currentDbUser.avatar || "👾" }) }); 
            document.getElementById('player-tour-name').innerText = d.name; listenToOnlineRoom(); showScreen('screen-player-lobby'); 
        } catch(e) { alert("Odaya katılamadınız!"); } 
    }

    function listenToOnlineRoom() { 
        if(otListener) otListener(); 
        otListener = db.collection("tournaments").doc(otCode).onSnapshot((doc) => { 
            if(!doc.exists) { alert("Oda kapatıldı!"); return showScreen('screen-home'); } 
            let data = doc.data(); otData = data; 
            
            if(data.status === 'lobby') { 
                if(otIsAdmin) { 
                    document.getElementById('admin-player-count').innerText = data.players.length; 
                    const list = document.getElementById('admin-player-list'); list.innerHTML = ''; 
                    data.players.forEach(p => { list.innerHTML += `<div class="player-tag">${p.avatar||"👾"} ${p.name}</div>`; }); 
                } 
                else { document.getElementById('player-lobby-count').innerText = data.players.length; } 
            } 
            else if(data.type === 'tour') {
                if(data.status === 'drawing') { if(otCurrentPhase !== 'drawing') { otCurrentPhase = 'drawing'; startBracketDrawAnimation(data); } }
                else if(data.status === 'countdown') { if(otCurrentPhase !== 'countdown') { otCurrentPhase = 'countdown'; handleOnlineCountdown(data); } } 
                else if(data.status === 'finished') { if(otCurrentPhase !== 'finished') { otCurrentPhase = 'finished'; clearInterval(otSyncInterval); clearTimeout(onlineTourFinishTimeout); document.getElementById('ob-countdown-overlay').style.display = 'none'; document.getElementById('ob-waiting-overlay').style.display = 'none'; showScreen('screen-online-bracket'); renderOnlineBracket(JSON.parse(data.bracket), false); setTournamentChampionCard('online', data.winner, 'Online turnuva tamamlandı'); scrollBracketToFinal('online'); } } 
                if(otIsAdmin && data.status === 'countdown') { checkOnlineRoundCompletion(data); } 
            }
            else if(data.type === 'battle') {
                if(data.status === 'playing') {
                    showScreen('screen-online-battle-arena');
                    let sHtml = "";
                    data.players.forEach(p => {
                        let sc = data.scores[p.uid] || 0;
                        sHtml += `<div style="display:flex; flex-direction:column; align-items:center;"><span style="font-size:0.8rem; color:white;">${p.name}</span><span style="font-weight:900; color:gold; font-size:1.8rem;">${sc}</span></div>`;
                    });
                    document.getElementById('obattle-scores-header').innerHTML = sHtml;

                    if(data.showResult) {
                        showOnlineBattleResults(data);
                    } else {
                        document.getElementById('obattle-result-overlay').style.display = 'none';
                        if(!data.currentQ || !data.currentQ.wordObj) {
                            document.getElementById('obattle-question').innerText = "Soru hazırlanıyor...";
                            document.getElementById('obattle-options').innerHTML = "";
                            document.getElementById('obattle-feedback').innerText = "";
                            return;
                        }
                        if(obLocalQIndex !== data.currentQIndex) {
                            obLocalQIndex = data.currentQIndex; obLocalHasAnswered = false; renderOnlineBattleQuestion(data);
                        }
                    }
                    if(otIsAdmin && !data.showResult) { checkOnlineBattleAnswers(data); }
                }
                else if(data.status === 'finished') {
                    if(otCurrentPhase === 'battleFinished') return;
                    otCurrentPhase = 'battleFinished';
                    clearInterval(timerInterval); 
                    showScreen('screen-result'); 
                    let sorted = [...data.players].map(p => ({...p, score: data.scores[p.uid] || 0})).sort((a,b) => b.score - a.score);
                    renderBattleEndCelebration(sorted, { title: "Online Monster Battle", kicker: "Online savaş tamamlandı" });
                    startConfetti();
                }
            }
        }); 
    }
    
    function copyTourCode() { navigator.clipboard.writeText(otCode); alert("Kod kopyalandı: " + otCode); }
    function shareTourCode() { window.open("https://wa.me/?text=" + encodeURIComponent("YDT Monster Battle'a Katıl! Kod: " + otCode)); }
    async function cancelOnlineRoom() { if(confirm("Emin misiniz?")) { if(otListener) { otListener(); otListener = null; } if(otMatchUnsub) { otMatchUnsub(); otMatchUnsub = null; } if(otIsAdmin) await db.collection("tournaments").doc(otCode).delete(); showScreen('screen-home'); } }
    async function leaveOnlineRoom() { if(otListener) { otListener(); otListener = null; } if(otMatchUnsub) { otMatchUnsub(); otMatchUnsub = null; } try { await db.collection("tournaments").doc(otCode).update({ players: otData.players.filter(p => p.uid !== currentDbUser.uid) }); } catch(e){} showScreen('screen-home'); }

    // ==========================================
    // ONLİNE TURNUVA İŞLEMLERİ (AĞAÇ VE MAÇLAR)
    // ==========================================
    async function drawOnlineBracket() { 
        if(otData.players.length < 2) return alert("En az 2 kişi olmalı!"); 
        setTournamentChampionCard('online', null);
        let generatedBracket = buildBracketLogic(otData.players); 
        try { await db.collection("tournaments").doc(otCode).update({ status: 'drawing', bracket: JSON.stringify(generatedBracket), round: 0, scores: {} }); } catch(e) { alert("Fikstür oluşturulamadı!"); } 
    }

    function startBracketDrawAnimation(data) {
        showScreen('screen-online-bracket'); 
        setTournamentChampionCard('online', null);
        if(otIsAdmin) document.getElementById('ob-admin-controls').style.display = 'flex';
        let startBtn = document.getElementById('ob-admin-start-btn'); if(startBtn) startBtn.style.display = 'none';
        document.getElementById('ob-countdown-overlay').style.display = 'none'; document.getElementById('ob-waiting-overlay').style.display = 'none';
        
        renderOnlineBracket(JSON.parse(data.bracket), true); 
        
        let slots = document.querySelectorAll('.draw-slot'); let idx = 0;
        if(slots.length === 0) { if(otIsAdmin && startBtn) startBtn.style.display = 'block'; return; }
        
        clearInterval(bracketDrawInterval);
        bracketDrawInterval = setInterval(() => {
            if(!isScreenActive('screen-online-bracket')) { clearInterval(bracketDrawInterval); return; }
            if(idx >= slots.length) { clearInterval(bracketDrawInterval); if(otIsAdmin && startBtn) startBtn.style.display = 'block'; return; }
            slots[idx].innerText = slots[idx].getAttribute('data-realname'); slots[idx].style.color = "gold"; slots[idx].style.transform = "scale(1.2)";
            clearTimeout(bracketDrawResetTimeout);
            bracketDrawResetTimeout = scheduleScreenTimeout('screen-online-bracket', () => { if(slots[idx]) { slots[idx].style.color = ""; slots[idx].style.transform = "scale(1)"; } }, 300);
            idx++;
        }, 400); 
    }

    async function startOnlineTournamentCountdown() { try { await db.collection("tournaments").doc(otCode).update({ status: 'countdown', nextTime: Date.now() + 15000 }); } catch(e) {} }

    function handleOnlineCountdown(data) { 
        showScreen('screen-online-bracket'); 
        setTournamentChampionCard('online', null);
        if(otIsAdmin) { document.getElementById('ob-admin-controls').style.display = 'flex'; let startBtn = document.getElementById('ob-admin-start-btn'); if(startBtn) startBtn.style.display = 'none'; }
        renderOnlineBracket(JSON.parse(data.bracket), false); document.getElementById('ob-waiting-overlay').style.display = 'none'; document.getElementById('ob-countdown-overlay').style.display = 'flex'; 
        clearInterval(otSyncInterval); 
        otSyncInterval = setInterval(() => { 
            if(!isScreenActive('screen-online-bracket')) { clearInterval(otSyncInterval); return; }
            let left = Math.round((data.nextTime - Date.now()) / 1000); 
            if(left <= 0) { clearInterval(otSyncInterval); document.getElementById('ob-countdown-overlay').style.display = 'none'; evaluateOnlinePlayerStatus(data); } 
            else { document.getElementById('ob-timer').innerText = left; } 
        }, 1000); 
    }

    function renderOnlineBracket(bracketData, isDrawing = false) { 
        const c=document.getElementById('ob-bracket-container'); c.innerHTML=''; 
        bracketData.forEach((r,i)=>{ 
            const col=document.createElement('div'); col.className='bracket-round'; let t=i===0&&r.length<bracketData[1].length?"Ön Eleme":`Tur ${i+1}`; if(i===bracketData.length-1)t="Final"; col.innerHTML=`<div class="round-title">${t}</div>`; 
            r.forEach(m=>{ 
                const d=document.createElement('div'); d.className='match-node'; 
                let p1Name = m.p1 ? m.p1.name : "..."; let p2Name = m.p2 ? m.p2.name : (m.isBye ? "BYE" : "..."); 
                if(m.winner) d.classList.add('finished'); else if(m.p1 && m.p2 && !m.isBye && i === otData.round && !isDrawing) d.classList.add('active-match'); 
                let s1=m.winner?` <span class="score-badge">${m.p1s||0}</span>`:''; let s2=m.winner && !m.isBye?` <span class="score-badge">${m.p2s||0}</span>`:''; 
                let w1=m.winner&&m.winner.uid===m.p1.uid?'winner':''; let w2=m.winner&&m.p2&&m.winner.uid===m.p2.uid?'winner':''; 
                let displayP1 = p1Name; let displayP2 = p2Name; let p1Attr = ''; let p2Attr = '';
                if(isDrawing && p1Name !== "..." && p1Name !== "BYE" && !m.winner) { displayP1 = "???"; p1Attr = `class="draw-slot" data-realname="${p1Name}"`; }
                if(isDrawing && p2Name !== "..." && p2Name !== "BYE" && !m.winner) { displayP2 = "???"; p2Attr = `class="draw-slot" data-realname="${p2Name}"`; }
                d.innerHTML=`<div class="match-player ${w1}"><span ${p1Attr}>${displayP1}</span>${s1}</div><div style="height:1px; background:#555; margin:5px 0"></div><div class="match-player ${w2}"><span ${p2Attr}>${displayP2}</span>${s2}</div>`; col.appendChild(d); 
            }); c.appendChild(col); 
        }); 
    }

    function evaluateOnlinePlayerStatus(data) { 
        if(otIsAdmin && !data.players.find(p=>p.uid === currentDbUser.uid)) return; 
        let bracket = JSON.parse(data.bracket); let currentMatches = bracket[data.round]; 
        otMyMatch = currentMatches.find(m => (m.p1 && m.p1.uid === currentDbUser.uid) || (m.p2 && m.p2.uid === currentDbUser.uid)); 
        if(otMyMatch && !otMyMatch.winner && !otMyMatch.isBye) { startOnlineTourMatch(otMyMatch, data); } 
        else if (otMyMatch && otMyMatch.isBye) { document.getElementById('ob-waiting-overlay').style.display = 'flex'; document.getElementById('ob-waiting-text').innerText = "Bu turu BAY geçiyorsun. Bekle..."; } 
        else { document.getElementById('ob-waiting-overlay').style.display = 'flex'; document.getElementById('ob-waiting-text').innerText = "Üzgünüz, elendiniz! Diğer maçları buradan takip edebilirsiniz."; } 
    }

    function startOnlineTourMatch(match, data) { 
        showScreen('screen-online-tour-match'); 
        otMatchRole = (match.p1.uid === currentDbUser.uid) ? 'p1' : 'p2';
        let opName = otMatchRole === 'p1' ? match.p2.name : match.p1.name;
        document.getElementById('otm-p1-name').innerText = (otMatchRole === 'p1') ? "SEN" : opName;
        document.getElementById('otm-p2-name').innerText = (otMatchRole === 'p2') ? "SEN" : opName;
        
        otMatchDocRef = db.collection("tournaments").doc(otCode).collection("matches").doc(match.id.toString());
        
        quizQ = []; 
        let matchSeedIndex = (data.round * 20) + (parseInt(match.id) || 0); 
        gameWords = getSelectedWords(data.gameConfig.cat, data.gameConfig.unit);
        for(let i=0; i<30; i++) { 
            let itemData = deterministicQuestionItem(gameWords, data.gameConfig.qType, (matchSeedIndex * 30) + i, data.questionSeeds);
            if(itemData) quizQ.push(buildQuestionObject(itemData.wordObj, itemData.type, gameWords, data.gameConfig.cat));
        }
        
        if(otMatchRole === 'p1') { otMatchDocRef.set({ qIndex: 0, p1Score: 0, p2Score: 0, p1Ans: null, p2Ans: null, p1Time: 0, p2Time: 0, phase: 'normal' }); }
        
        otCurrentQIndex = -1;
        if(otMatchUnsub) otMatchUnsub();
        otMatchUnsub = otMatchDocRef.onSnapshot(doc => {
            if(!doc.exists) return;
            let md = doc.data();
            if(md.qIndex !== otCurrentQIndex && md.p1Ans === null && md.p2Ans === null) { otCurrentQIndex = md.qIndex; loadOnlineTourMatchQ(md); }
            if(md.p1Ans !== null && md.p2Ans !== null) { resolveOnlineMatchRound(md); }
        });
    }

    function loadOnlineTourMatchQ(md) {
        if(!isScreenActive('screen-online-tour-match')) return;
        otLocalHasAnswered = false;
        const q = quizQ[md.qIndex]; currentWordObj = q.wordObj;
        
        let headerSub = "";
        if(md.phase === 'penalty_accuracy') headerSub = "<br><span style='font-size:0.8rem; color:yellow;'>EŞİTLİK! DOĞRU BİLEN KAZANIR!</span>";
        else if(md.phase === 'penalty_speed') headerSub = "<br><span style='font-size:0.8rem; color:yellow;'>EŞİTLİK BOZULMADI! HIZLI BİLEN KAZANIR!</span>";

        document.getElementById('otm-progress').innerText = `${md.qIndex+1}`;
        document.getElementById('otm-question').innerHTML = `<span style="font-size: 1.3em; font-weight: 900;">${q.wordObj.word}</span>${headerSub}`;
        document.getElementById('otm-feedback').innerText = "Cevap Bekleniyor...";
        document.getElementById('otm-p1-score').innerText = md.p1Score; document.getElementById('otm-p2-score').innerText = md.p2Score;

        const g = document.getElementById('otm-options'); g.innerHTML = '';
        q.opts.forEach(txt => {
            const b = document.createElement('button'); b.className = 'btn option-btn'; b.innerText = txt;
            b.onclick = () => submitOnlineMatchAns(txt); g.appendChild(b);
        });
        
        try{ speakCurrentWord(); }catch(e){}
        clearInterval(timerInterval);
        document.getElementById('otm-timer-fill').style.transition = "none"; document.getElementById('otm-timer-fill').style.width = "100%"; 
        clearTimeout(otmAnimTimeout);
        otmAnimTimeout = scheduleScreenTimeout('screen-online-tour-match', ()=>{ document.getElementById('otm-timer-fill').style.transition = "width 10s linear"; document.getElementById('otm-timer-fill').style.width = "0%"; }, 50);
        olStartTime = Date.now();
        timerInterval = setInterval(() => {
            if(!isScreenActive('screen-online-tour-match')) { clearInterval(timerInterval); return; }
            let left = 10000 - (Date.now() - olStartTime);
            if(left <= 0) { clearInterval(timerInterval); if(!otLocalHasAnswered) submitOnlineMatchAns('TIMEOUT'); } 
            else { document.getElementById('otm-timer-text').innerText = (left / 1000).toFixed(2); }
        }, 50);
    }

    function submitOnlineMatchAns(ans) {
        if(!isScreenActive('screen-online-tour-match')) return;
        if(otLocalHasAnswered) return; otLocalHasAnswered = true; clearInterval(timerInterval); document.getElementById('otm-timer-fill').style.width = "0%";
        document.querySelectorAll('#otm-options .option-btn').forEach(b => { b.disabled = true; if(b.innerText === ans && ans !== 'TIMEOUT') b.classList.add('selected'); else b.style.opacity = '0.4'; });
        document.getElementById('otm-feedback').innerText = "Rakip Bekleniyor...";
        otMatchDocRef.set({ [otMatchRole + 'Ans']: ans, [otMatchRole + 'Time']: Date.now() }, {merge: true});
    }

    function resolveOnlineMatchRound(md) {
        if(!isScreenActive('screen-online-tour-match')) return;
        const q = quizQ[md.qIndex]; let p1Correct = (md.p1Ans === q.correct); let p2Correct = (md.p2Ans === q.correct);
        let newP1Score = md.p1Score; let newP2Score = md.p2Score;

        if (md.phase === 'normal' || md.phase === 'penalty_accuracy') { if(p1Correct) newP1Score++; if(p2Correct) newP2Score++; } 
        else if (md.phase === 'penalty_speed') { if(p1Correct && p2Correct) { if(md.p1Time < md.p2Time) newP1Score++; else newP2Score++; } else { if(p1Correct) newP1Score++; if(p2Correct) newP2Score++; } }

        document.getElementById('otm-p1-score').innerText = newP1Score; document.getElementById('otm-p2-score').innerText = newP2Score;
        document.querySelectorAll('#otm-options .option-btn').forEach(b => { b.style.opacity = '1'; if(b.innerText === q.correct) b.classList.add('correct'); else if(b.classList.contains('selected')) b.classList.add('wrong'); });
        
        let myAns = otMatchRole === 'p1' ? md.p1Ans : md.p2Ans; let myCorrect = otMatchRole === 'p1' ? p1Correct : p2Correct;
        if(myAns === 'TIMEOUT') document.getElementById('otm-feedback').innerText = "Süre Bitti!"; else if(myCorrect) document.getElementById('otm-feedback').innerText = "Doğru!"; else document.getElementById('otm-feedback').innerText = "Yanlış!";

        clearTimeout(otmTransitionTimeout);
        otmTransitionTimeout = scheduleScreenTimeout('screen-online-tour-match', () => {
            if(otMatchRole === 'p1') {
                let nextPhase = md.phase; let matchOver = false;
                if(md.phase === 'normal') { if(md.qIndex >= 4) { if(newP1Score !== newP2Score) matchOver = true; else nextPhase = 'penalty_accuracy'; } } 
                else if (md.phase === 'penalty_accuracy') { if(newP1Score !== newP2Score) matchOver = true; else if (md.qIndex >= 7) nextPhase = 'penalty_speed'; } 
                else if (md.phase === 'penalty_speed') { if(newP1Score !== newP2Score) matchOver = true; }

                if(matchOver) { db.collection("tournaments").doc(otCode).update({ [`scores.${otMyMatch.id}_${otMyMatch.p1.uid}`]: newP1Score, [`scores.${otMyMatch.id}_${otMyMatch.p2.uid}`]: newP2Score }); } 
                else { otMatchDocRef.update({ qIndex: md.qIndex + 1, p1Score: newP1Score, p2Score: newP2Score, p1Ans: null, p2Ans: null, phase: nextPhase }); }
            }
            if ( (md.phase === 'normal' && md.qIndex >= 4 && newP1Score !== newP2Score) || (md.phase === 'penalty_accuracy' && newP1Score !== newP2Score) || (md.phase === 'penalty_speed' && newP1Score !== newP2Score) ) {
                if(otMatchUnsub) otMatchUnsub(); showScreen('screen-online-bracket'); document.getElementById('ob-waiting-overlay').style.display = 'flex'; document.getElementById('ob-waiting-text').innerText = "Maç Bitti! Diğer sonuçlar bekleniyor...";
            }
        }, 2000);
    }

    function checkOnlineRoundCompletion(data) { 
        if(!otIsAdmin) return; 
        let bracket = JSON.parse(data.bracket); let currentRoundMatches = bracket[data.round]; let allFinished = true; let needUpdate = false; 
        currentRoundMatches.forEach(m => { 
            if(!m.winner) { 
                if(m.isBye) { m.winner = m.p1; needUpdate = true; } 
                else { 
                    let s1 = data.scores[m.id + "_" + m.p1.uid]; let s2 = data.scores[m.id + "_" + m.p2.uid]; 
                    if(s1 !== undefined && s2 !== undefined) { m.winner = s1 >= s2 ? m.p1 : m.p2; m.p1s = s1; m.p2s = s2; needUpdate = true; } 
                    else { allFinished = false; } 
                } 
            } 
        }); 
        if(allFinished && needUpdate) { 
            let nextR = data.round + 1; 
            if(nextR < bracket.length) { 
                currentRoundMatches.forEach(m => { let nextMatch = bracket.flat().find(x => x.id === m.next); if(nextMatch) { if(!nextMatch.p1) { nextMatch.p1 = m.winner; } else { nextMatch.p2 = m.winner; } } }); 
                db.collection('tournaments').doc(otCode).update({ bracket: JSON.stringify(bracket), round: nextR, status: 'countdown', nextTime: Date.now() + 15000, scores: {} }); 
            } else { db.collection('tournaments').doc(otCode).update({ bracket: JSON.stringify(bracket), status: 'finished', winner: currentRoundMatches[0].winner }); } 
        } else if (needUpdate) { db.collection('tournaments').doc(otCode).update({ bracket: JSON.stringify(bracket) }); } 
    }

    // ==========================================
    // ONLİNE BATTLE (KAHOOT STYLE)
    // ==========================================
    async function startOnlineBattle() {
        if(otData.players.length < 2) return alert("En az 2 kişi olmalı!");
        let sc = {}; otData.players.forEach(p => sc[p.uid] = 0);
        try { 
            await db.collection("tournaments").doc(otCode).update({ status: 'playing', currentQIndex: 0, scores: sc, answers: {}, showResult: false }); 
            pushNextOnlineBattleQuestion(0, otData);
        } catch(e) { alert("Başlatılamadı!"); }
    }

    function pushNextOnlineBattleQuestion(index, data) {
        if(!otIsAdmin) return;
        gameWords = getSelectedWords(data.gameConfig.cat, data.gameConfig.unit);
        if(gameWords.length < 4) return alert("Hata: Yetersiz Kelime!");

        const itemData = deterministicQuestionItem(gameWords, data.gameConfig.qType, index, data.questionSeeds);
        if(!itemData) return alert("Soru üretilemedi!");
        let newQ = buildQuestionObject(itemData.wordObj, itemData.type, gameWords, data.gameConfig.cat);
        db.collection("tournaments").doc(otCode).update({ currentQ: newQ, currentQIndex: index, answers: {}, showResult: false, qStartTime: Date.now() + 1000 });
        
        clearTimeout(obHostTimer);
        obHostTimer = setTimeout(() => { checkOnlineBattleAnswers(otData); }, 11500); 
    }

    function renderOnlineBattleQuestion(data) {
        if(!isScreenActive('screen-online-battle-arena')) return;
        const q = data.currentQ;
        if(!q || !q.wordObj) return;
        currentWordObj = q.wordObj;
        document.getElementById('obattle-question').innerHTML = `<span style="font-size: 1.3em; font-weight: 900;">${q.wordObj.word}</span>`;
        document.getElementById('obattle-feedback').innerText = "";
        
        const g = document.getElementById('obattle-options'); g.innerHTML = '';
        q.opts.forEach(txt => { 
            const b = document.createElement('button'); b.className = 'btn option-btn'; b.innerText = txt; 
            b.onclick = () => submitOnlineBattleAnswer(txt, data); g.appendChild(b); 
        });
        
        try{ speakCurrentWord(); } catch(e){} 
        clearInterval(timerInterval); 
        document.getElementById('obattle-timer-fill').style.transition = "none"; document.getElementById('obattle-timer-fill').style.width = "100%"; 
        clearTimeout(obattleAnimTimeout);
        obattleAnimTimeout = scheduleScreenTimeout('screen-online-battle-arena', ()=>{ document.getElementById('obattle-timer-fill').style.transition = "width 10s linear"; document.getElementById('obattle-timer-fill').style.width = "0%"; }, 50);
        
        olStartTime = Date.now();
        timerInterval = setInterval(() => { 
            if(!isScreenActive('screen-online-battle-arena')) { clearInterval(timerInterval); return; }
            let left = 10000 - (Date.now() - olStartTime); 
            if(left <= 0) { 
                clearInterval(timerInterval); document.getElementById('obattle-timer-text').innerText = "0.00"; 
                if(!obLocalHasAnswered) submitOnlineBattleAnswer('TIMEOUT', data); 
            } else { document.getElementById('obattle-timer-text').innerText = (left / 1000).toFixed(2); } 
        }, 50);
    }

    function submitOnlineBattleAnswer(ans, data) {
        if(!isScreenActive('screen-online-battle-arena')) return;
        if(obLocalHasAnswered) return; obLocalHasAnswered = true; clearInterval(timerInterval); document.getElementById('obattle-timer-fill').style.width = "0%";
        document.querySelectorAll('#obattle-options .option-btn').forEach(b => { 
            b.disabled = true; if(b.innerText === ans && ans !== 'TIMEOUT') b.classList.add('selected'); else b.style.opacity = '0.4'; 
        });
        document.getElementById('obattle-feedback').innerText = "Diğerleri Bekleniyor...";
        db.collection("tournaments").doc(otCode).update({ [`answers.${currentDbUser.uid}`]: { ans: ans, time: Date.now() } });
    }

    function checkOnlineBattleAnswers(data) {
        if(!isScreenActive('screen-online-battle-arena')) return;
        if(!otIsAdmin || data.showResult || !data.currentQ || !data.currentQ.wordObj) return;
        let ansCount = Object.keys(data.answers || {}).length;
        let timeUp = Date.now() >= (data.qStartTime + 10000);
        
        if(ansCount >= data.players.length || timeUp) {
            clearTimeout(obHostTimer);
            let ansArr = Object.entries(data.answers || {}).map(([uid, a]) => ({uid, ...a}));
            let correctAns = ansArr.filter(a => a.ans === data.currentQ.correct).sort((a,b) => a.time - b.time);
            
            let roundResults = {}; let newScores = {...data.scores};
            correctAns.forEach((a, i) => {
                let pts = 0; if(i === 0) pts = 3; else if(i === 1) pts = 2; else if(i === 2) pts = 1;
                if(pts > 0) { newScores[a.uid] = (newScores[a.uid] || 0) + pts; roundResults[a.uid] = pts; }
            });
            
            db.collection("tournaments").doc(otCode).update({ scores: newScores, roundResults: roundResults, showResult: true });
            
            clearTimeout(onlineBattleNextTimeout);
            onlineBattleNextTimeout = scheduleScreenTimeout('screen-online-battle-arena', () => {
                let winner = Object.entries(newScores).find(([uid, s]) => s >= data.gameConfig.targetScore);
                if(winner) { db.collection("tournaments").doc(otCode).update({ status: 'finished' }); } 
                else { pushNextOnlineBattleQuestion(data.currentQIndex + 1, data); }
            }, 3000);
        }
    }

    function showOnlineBattleResults(data) {
        if(!data.currentQ) return;
        document.querySelectorAll('#obattle-options .option-btn').forEach(b => {
            b.style.opacity = '1';
            if(b.innerText === data.currentQ.correct) b.classList.add('correct'); 
            else if(b.classList.contains('selected')) b.classList.add('wrong');
        });

        let myAnsData = (data.answers || {})[currentDbUser.uid];
        if(!myAnsData || myAnsData.ans === 'TIMEOUT') document.getElementById('obattle-feedback').innerText = "Süre Bitti!"; 
        else if(myAnsData.ans === data.currentQ.correct) document.getElementById('obattle-feedback').innerText = "Doğru!"; 
        else document.getElementById('obattle-feedback').innerText = "Yanlış!";

        let scoresText = "";
        data.players.forEach(p => {
            let pts = (data.roundResults || {})[p.uid];
            if(pts) scoresText += `<div style="font-size:1.5rem; font-weight:900; color:white;">${p.name}: <span style="color:gold;">+${pts}</span></div>`;
        });
        
        const overlay = document.getElementById('obattle-result-overlay'); 
        document.getElementById('obattle-res-title').innerText = "Sonuçlar!"; 
        document.getElementById('obattle-res-content').innerHTML = scoresText || `<div style="color:var(--danger); font-weight:bold; font-size:1.5rem;">Puan Alan Yok!</div>`; 
        overlay.style.display = 'flex';
    }


    // ==========================================
    // YEREL TURNUVA
    // ==========================================
    function setupLocalTournament(){ 
        players=[]; 
        document.getElementById('player-list').innerHTML=''; 
        setTournamentChampionCard('local', null);
        const limitEl = document.getElementById('tour-q-limit'); 
        if(limitEl) limitEl.value = 5; 
        battleWordPool = []; battleQuestionPool = []; battleQuestionMode = null;
        showScreen('screen-local-tour-setup'); 
    }
    
    function addPlayer(){ 
        const inp=document.getElementById('player-name'); 
        const val=inp.value.trim(); 
        const em=document.getElementById('player-emoji').value; 
        if(val){ 
            players.push({uid: Math.random().toString(), name: val + " " + em}); 
            const d=document.createElement('div'); 
            d.className='player-tag'; 
            d.innerText=val + " " + em; 
            const list = document.getElementById('player-list');
            list.appendChild(d); 
            list.scrollTop = list.scrollHeight;
            inp.value=''; 
            inp.focus();
        } 
    }
    
    function handleEnter(e,cb){ if(e.key==='Enter') cb(); }

    function generateLocalBracket(){ 
        if(players.length<2) return alert("En az 2 oyuncu!"); 
        gameWords=getSelectedWords(); 
        if(gameWords.length<5) return alert("Veri Yok."); 
        
        battleWordPool = []; battleQuestionPool = []; battleQuestionMode = null; // Güvenlik sıfırlaması
        const limitEl = document.getElementById('tour-q-limit');
        tournamentMaxQuestions = parseInt(limitEl ? limitEl.value : 5) || 5; 
        
        setTournamentChampionCard('local', null);
        rounds = buildBracketLogic(players); 
        renderLocalBracket(); 
        showScreen('screen-local-bracket'); 
    }

    function buildBracketLogic(playerList) {
        let pool=[...playerList].sort(()=>Math.random()-0.5); let nextPower=2; while(nextPower<pool.length) nextPower*=2; let excess=pool.length-(nextPower/2); let r1Matches=[], matchId=0; 
        for(let i=0;i<excess;i++) r1Matches.push({id:matchId++, p1:pool.shift(), p2:pool.shift(), winner:null, next:null}); 
        let builtRounds=[]; builtRounds.push(r1Matches); let r2Matches=[], r2Slots=[]; 
        while(pool.length>0) r2Slots.push({type:'player', data:pool.shift()}); 
        r1Matches.forEach(m=>r2Slots.push({type:'match', matchId:m.id})); 
        for(let i=0;i<r2Slots.length;i+=2){ 
            let s1=r2Slots[i], s2=r2Slots[i+1]; 
            if(!s2) { let nm={id:matchId++, p1:s1.type==='player'?s1.data:null, p2:null, winner:s1.type==='player'?s1.data:null, next:null, isBye:true}; r2Matches.push(nm); if(s1.type==='match') r1Matches.find(x=>x.id===s1.matchId).next=nm.id; continue; } 
            let p1Data=s1.type==='player'?s1.data:null; let p2Data=s2.type==='player'?s2.data:null; 
            let newMatch={id:matchId++, p1:p1Data, p2:p2Data, winner:null, next:null, isBye:false}; r2Matches.push(newMatch); 
            if(s1.type==='match') r1Matches.find(x=>x.id===s1.matchId).next=newMatch.id; if(s2.type==='match') r1Matches.find(x=>x.id===s2.matchId).next=newMatch.id; 
        } 
        builtRounds.push(r2Matches); let curr=r2Matches; 
        while(curr.length>1){ 
            let nextR=[]; 
            for(let i=0;i<curr.length;i+=2){ 
                let nm={id:matchId++, p1:null, p2:null, winner:null, next:null, isBye:false}; curr[i].next=nm.id; 
                if(curr[i+1]) { curr[i+1].next=nm.id; }
                if(curr[i].isBye) nm.p1 = curr[i].winner; if(curr[i+1] && curr[i+1].isBye) nm.p2 = curr[i+1].winner;
                nextR.push(nm); 
            } 
            builtRounds.push(nextR); curr=nextR; 
        }
        return builtRounds;
    }

    function renderLocalBracket(){ 
        const c=document.getElementById('local-bracket-container'); c.innerHTML=''; 
        rounds.forEach((r,i)=>{ 
            const col=document.createElement('div'); col.className='bracket-round'; let t=i===0&&r.length<rounds[1].length?"Ön Eleme":`Tur ${i+1}`; if(i===rounds.length-1)t="Final"; 
            col.innerHTML=`<div class="round-title">${t}</div>`; 
            r.forEach(m=>{ 
                const d=document.createElement('div'); d.className='match-node'; 
                let p1Name = m.p1 ? m.p1.name : "..."; let p2Name = m.p2 ? m.p2.name : (m.isBye ? "BYE" : "...");
                if(m.winner) d.classList.add('finished'); else if(m.p1 && m.p2 && !m.isBye) d.classList.add('active-match'); 
                let s1=m.winner?` <span class="score-badge">${m.p1s||0}</span>`:''; let s2=m.winner && !m.isBye?` <span class="score-badge">${m.p2s||0}</span>`:''; 
                let w1=m.winner&&m.winner.uid===m.p1.uid?'winner':''; let w2=m.winner&&m.p2&&m.winner.uid===m.p2.uid?'winner':'';
                d.innerHTML=`<div class="match-player ${w1}"><span>${p1Name}</span>${s1}</div><div style="height:1px; background:#555; margin:5px 0"></div><div class="match-player ${w2}"><span>${p2Name}</span>${s2}</div>`; 
                d.onclick=()=>{if(d.classList.contains('active-match')) startLocalMatch(m)}; col.appendChild(d); 
            }); 
            c.appendChild(col); 
        }); 
    }

    function startLocalMatch(m) { 
        currentMatch = m; 
        battlePlayers = [ {id: 1, name: m.p1.name, emoji: '', score: 0, tourPlayer: m.p1}, {id: 2, name: m.p2.name, emoji: '', score: 0, tourPlayer: m.p2} ];
        battleMaxQ = tournamentMaxQuestions; 
        isLocalTourBattle = true;
        currentBattleRound = 0; 
        battlePhase = 'normal';
        document.getElementById('battle-quiz-type').value = document.getElementById('tour-quiz-type').value; 
        battleQuestionPool = []; battleQuestionMode = null;
        showScreen('screen-battle-arena'); 
        startBattleGame(true); 
    }

    function finishLocalTourMatch(winnerPlayer) {
        document.getElementById('battle-reveal-overlay').style.display = 'none';
        let p1Score = battlePlayers[0].score; let p2Score = battlePlayers[1].score;
        currentMatch.winner = winnerPlayer; currentMatch.p1s = p1Score; currentMatch.p2s = p2Score;
        if(currentMatch.next!==null){ for(let r of rounds){ let nm=r.find(x=>x.id===currentMatch.next); if(nm){ if(!nm.p1) nm.p1=winnerPlayer; else nm.p2=winnerPlayer; } } } 
        let isFinal=rounds[rounds.length-1][0].id===currentMatch.id; 
        if(isFinal) { isLocalTourBattle = false; endLocalTournament(winnerPlayer); } 
        else { 
            document.getElementById('br-title').innerText = "KAZANAN";
            document.getElementById('br-content').innerHTML = `<div style="font-size:3rem;">🏆</div><h2 style="color:white;">${winnerPlayer.name}</h2>`;
            document.getElementById('battle-reveal-overlay').style.display = 'flex';
            clearTimeout(localTourReturnTimeout);
            localTourReturnTimeout = scheduleScreenTimeout('screen-battle-arena', ()=>{ document.getElementById('battle-reveal-overlay').style.display = 'none'; renderLocalBracket(); showScreen('screen-local-bracket'); },2500); 
        } 
    }

    function endLocalTournament(winner) { 
        isLocalTourBattle = false;
        setResultScreenMode(null);
        renderLocalBracket();
        setTournamentChampionCard('local', winner, 'Yerel turnuva tamamlandı');
        showScreen('screen-local-bracket');
        scrollBracketToFinal('local');
    }

    // ==========================================
    // YEREL BATTLE
    // ==========================================
    function setupLocalBattle(){ 
        battlePlayers=[]; 
        battleWordPool = []; battleQuestionPool = []; battleQuestionMode = null;
        document.getElementById('battle-names-area').innerHTML=''; 
        updateBattleInputs(); 
        showScreen('screen-battle-setup'); 
    }
    
    function updateBattleInputs(){ 
        const c=parseInt(document.getElementById('battle-count').value); 
        const div=document.getElementById('battle-names-area'); 
        div.innerHTML=''; 
        for(let i=1;i<=c;i++){ 
            const row = document.createElement('div'); row.style.display = 'flex'; row.style.gap = '5px'; row.style.marginBottom = '5px'; 
            const inp=document.createElement('input'); inp.placeholder=`Oyuncu ${i} Adı`; inp.id=`bp-${i}`; 
            const sel=document.createElement('select'); sel.id=`be-${i}`; sel.style.width='60px'; 
            populatePlayerEmojiSelect(sel, PLAYER_EMOJI_LIST[(i - 1) % PLAYER_EMOJI_LIST.length]); 
            row.appendChild(inp); row.appendChild(sel); div.appendChild(row); 
        } 
    }
    
    function showBattleAlert(text, cb) {
        document.getElementById('ba-title').innerText = text; document.getElementById('battle-alert-overlay').style.display = 'flex';
        clearTimeout(battleAlertTimeout);
        battleAlertTimeout = scheduleScreenTimeout('screen-battle-arena', ()=>{ document.getElementById('battle-alert-overlay').style.display = 'none'; if(cb) cb(); }, 2500); 
    }

    function startBattleIntro() { 
        gameWords=getSelectedWords(); 
        if(!gameWords || gameWords.length < 5) return alert("Hata: Ünitede yeterli kelime yok!"); 
        
        battleWordPool = []; battleQuestionPool = []; battleQuestionMode = null; // Güvenlik sıfırlaması
        const c = parseInt(document.getElementById('battle-count').value); 
        const scoreLimitEl = document.getElementById('battle-score-limit'); 
        battleScoreLimit = parseInt(scoreLimitEl ? scoreLimitEl.value : 15) || 15; 
        
        battlePlayers=[]; 
        for(let i=1;i<=c;i++){ 
            const n=document.getElementById(`bp-${i}`).value.trim()||`P${i}`; 
            const e=document.getElementById(`be-${i}`).value; 
            battlePlayers.push({id:i, name:n, emoji:e, score:0}); 
        } 
        
        isLocalTourBattle = false; 
        currentBattleRound = 0; 
        battlePhase = 'normal'; 
        showScreen('screen-battle-arena'); 
        startBattleGame(false); 
    }

    function startBattleGame(skipIntro = false){ 
        const grid=document.getElementById('battle-grid'); grid.innerHTML=''; grid.setAttribute('data-players', battlePlayers.length); 
        
        battlePlayers.forEach(p=>{ 
            const z=document.createElement('div'); z.className=`player-zone pz-${p.id}`; z.id=`bz-${p.id}`; 
            z.innerHTML=`<div class="player-box"><span class="player-name-text">${p.name} ${p.emoji}</span><span class="p-score" id="b-score-${p.id}">0</span></div><div class="battle-options" id="b-opt-${p.id}"></div>`; 
            grid.appendChild(z); 
        }); 
        
        // ZORUNLU GÜVENLİK KONTROLÜ (FALLBACK)
        if(!gameWords || gameWords.length === 0) gameWords = getSelectedWords();
        battleWordPool = [...gameWords].sort(()=>Math.random()-0.5); 

        if(!skipIntro) { 
            const introBox = document.getElementById('battle-intro-box'); introBox.innerHTML = ''; 
            battlePlayers.forEach(p => { introBox.innerHTML += `<div class="intro-p pz-${p.id}">${p.name} ${p.emoji}</div>`; }); 
            document.getElementById('battle-intro-overlay').style.display = 'flex'; 
            let countdown = 3; document.getElementById('battle-intro-timer').innerText = countdown; 
            
            clearInterval(battleIntroInterval);
            battleIntroInterval = setInterval(() => { 
                if(!isScreenActive('screen-battle-arena')) { clearInterval(battleIntroInterval); return; }
                countdown--; 
                if(countdown > 0) document.getElementById('battle-intro-timer').innerText = countdown; 
                else { clearInterval(battleIntroInterval); document.getElementById('battle-intro-overlay').style.display = 'none'; nextBattleQuestion(); } 
            }, 1000); 
        } else { nextBattleQuestion(); } 
    }

    function nextBattleQuestion(){ 
        if(!isScreenActive('screen-battle-arena')) { activeArena = false; return; }
        activeArena=true; battleRoundAnswers=[]; 
        const pref=document.getElementById('battle-quiz-type').value; 
        
        if(!gameWords || gameWords.length === 0) gameWords = getSelectedWords();
        if(!gameWords || gameWords.length === 0) {
            alert("Kelime çekilemedi! Lütfen ünitenizde kelime olduğundan emin olun."); 
            return endBattleEarly(); 
        }
        if(battleQuestionMode !== pref || !battleQuestionPool || battleQuestionPool.length === 0) {
            battleQuestionMode = pref;
            battleQuestionPool = shuffleArray(makeQuestionPool(gameWords, pref));
        }
        
        const pickedQuestion = battleQuestionPool.pop();
        if(!pickedQuestion) {
            alert("Soru çekilemedi! Lütfen tekrar deneyin.");
            return endBattleEarly();
        }
        const item = pickedQuestion.wordObj;
        
        currentWordObj = item; 
        let type = pickedQuestion.type; 
        
        let headerSub = "";
        if(isLocalTourBattle) {
            if(battlePhase === 'penalty_accuracy') headerSub = "<br><span style='font-size:0.8rem; color:yellow;'>DOĞRU BİLEN KAZANIR!</span>";
            else if(battlePhase === 'penalty_speed') headerSub = "<br><span style='font-size:0.8rem; color:yellow;'>HIZLI BİLEN KAZANIR!</span>";
        }

        document.getElementById('b-question').innerHTML = `<span style="font-size: 1.3em; font-weight: 900;">${item.word}</span>${headerSub}`; 
        document.getElementById('battle-reveal-overlay').style.display = 'none'; 
        
        const qData = buildQuestionObject(item, type, gameWords, currentCategory);
        const corTxt=qData.correct; 
        const optTxt=qData.opts; 
        
        battlePlayers.forEach(p=>{ 
            const d=document.getElementById(`b-opt-${p.id}`); d.innerHTML=''; 
            optTxt.forEach(txt=>{ 
                const b=document.createElement('button'); b.className='b-opt-btn'; b.innerText=txt; 
                b.addEventListener('pointerdown',(e)=>{ 
                    e.preventDefault(); 
                    if(!activeArena || battleRoundAnswers.find(x=>x.id===p.id)) return; 
                    
                    b.classList.add('selected'); 
                    battleRoundAnswers.push({id: p.id, ans: txt, correct: (txt === corTxt), time: Date.now(), btn: b}); 
                    document.querySelectorAll(`#b-opt-${p.id} .b-opt-btn`).forEach(btn => { if(btn !== b) btn.style.opacity = '0.3'; });

                    if (battleRoundAnswers.length === battlePlayers.length) { revealBattleResults(); } 
                }); 
                d.appendChild(b); 
            }); 
        }); 
        try{speakCurrentWord();}catch(e){} 
        startTimer(10,'b-timer',revealBattleResults); 
    }

    function revealBattleResults() { 
        if (!activeArena) return; 
        clearInterval(timerInterval); activeArena = false; 
        let correctAnswers = battleRoundAnswers.filter(a => a.correct).sort((a,b) => a.time - b.time); 
        let scoresText = ""; 
        
        if (isLocalTourBattle) {
            currentBattleRound++;
            let p1 = battlePlayers[0]; let p2 = battlePlayers[1];
            
            if (battlePhase === 'normal' || battlePhase === 'penalty_accuracy') {
                correctAnswers.forEach(ans => { 
                    let p = battlePlayers.find(x => x.id === ans.id); p.score += 1; 
                    document.getElementById(`b-score-${p.id}`).innerText = p.score; 
                    scoresText += `<div style="font-size:1.5rem; font-weight:900; color:white;">${p.name}: <span style="color:gold;">+1</span></div>`; 
                });
            } else if (battlePhase === 'penalty_speed') {
                if(correctAnswers.length > 0) { 
                    let fastest = correctAnswers[0]; let p = battlePlayers.find(x => x.id === fastest.id); 
                    p.score += 1; document.getElementById(`b-score-${p.id}`).innerText = p.score; 
                    scoresText += `<div style="font-size:1.5rem; font-weight:900; color:white;">${p.name}: <span style="color:gold;">+1 (HIZLI!)</span></div>`; 
                }
            }
        } else {
            correctAnswers.forEach((ans, index) => { 
                let pts = 0; if(index === 0) pts = 3; else if(index === 1) pts = 2; else if(index === 2) pts = 1; 
                if(pts > 0) { 
                    let p = battlePlayers.find(x => x.id === ans.id); p.score += pts; 
                    document.getElementById(`b-score-${p.id}`).innerText = p.score; 
                    scoresText += `<div style="font-size:1.5rem; font-weight:900; color:white;">${p.name}: <span style="color:gold;">+${pts}</span></div>`; 
                } 
            }); 
        }

        correctAnswers.forEach(ans => ans.btn.classList.add('correct'));
        battleRoundAnswers.filter(a => !a.correct).forEach(a => { a.btn.classList.add('wrong'); }); 
        
        const overlay = document.getElementById('battle-reveal-overlay'); 
        document.getElementById('br-title').innerText = "Sonuçlar!"; 
        document.getElementById('br-content').innerHTML = scoresText || `<div style="color:var(--danger); font-weight:bold; font-size:1.5rem;">İki Oyuncu da Bilemedi!</div>`; 
        overlay.style.display = 'flex'; 
        
        clearTimeout(battleRevealTimeout);
        battleRevealTimeout = scheduleScreenTimeout('screen-battle-arena', () => { 
            overlay.style.display = 'none';
            if(isLocalTourBattle) {
                let p1 = battlePlayers[0]; let p2 = battlePlayers[1];
                if (battlePhase === 'normal') {
                    if (currentBattleRound >= tournamentMaxQuestions) {
                        if (p1.score !== p2.score) { finishLocalTourMatch(p1.score > p2.score ? p1.tourPlayer : p2.tourPlayer); } 
                        else { battlePhase = 'penalty_accuracy'; showBattleAlert("EŞİTLİK!\nDOĞRU BİLEN KAZANIR!", nextBattleQuestion); }
                    } else { nextBattleQuestion(); }
                } else if (battlePhase === 'penalty_accuracy') {
                    if (p1.score !== p2.score) { finishLocalTourMatch(p1.score > p2.score ? p1.tourPlayer : p2.tourPlayer); } 
                    else { if (currentBattleRound >= tournamentMaxQuestions + 3) { battlePhase = 'penalty_speed'; showBattleAlert("EŞİTLİK BOZULMADI!\nHIZLI BİLEN KAZANIR!", nextBattleQuestion); } else { nextBattleQuestion(); } }
                } else if (battlePhase === 'penalty_speed') {
                    if (p1.score !== p2.score) { finishLocalTourMatch(p1.score > p2.score ? p1.tourPlayer : p2.tourPlayer); } else { nextBattleQuestion(); }
                }
            } else {
                let winner = battlePlayers.find(p => p.score >= battleScoreLimit); 
                if(winner) endBattle(); else nextBattleQuestion(); 
            }
        }, 2000); 
    }

    function endBattle(){ 
        isLocalTourBattle = false; battlePlayers.sort((a,b)=>b.score-a.score); 
        showScreen('screen-result'); 
        renderBattleEndCelebration(battlePlayers, { title: "Monster Battle", kicker: "Yerel savaş tamamlandı" });
        startConfetti(); 
    }
    
    function endBattleEarly() { isLocalTourBattle = false; stopGameplayRuntime('screen-home'); showScreen('screen-home'); }
</script>
</body>
</html>
