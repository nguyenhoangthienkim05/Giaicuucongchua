# Giải Cứu Công Chúa
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Hành Trình Giải Cứu Công Chúa Sơn Ca</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@500;600;700;800&family=Cinzel+Decorative:wght@700;900&family=Be+Vietnam+Pro:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --night:#5B6EE8;
    --forest-deep:#4A9C82;
    --forest:#6FBFA0;
    --forest-light:#9EDBC3;
    --parchment:#FFF3D6;
    --parchment-2:#FFFBF0;
    --ink:#3A3226;
    --ink-soft:#8A8066;
    --gold:#F4C15C;
    --gold-deep:#D9A03E;
    --ember:#F0906A;
    --coral:#F0837E;
    --teal:#4EBFAE;
    --sky:#7FB8E8;
    --line:#F3DFA8;
    --radius:20px;
    --shadow:0 8px 22px rgba(120,100,60,0.16);
  }
  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    background:
      radial-gradient(ellipse at top, #BFE3D4 0%, #9EDBC3 45%, #7FCBAE 100%);
    color:var(--ink);
    font-family:'Be Vietnam Pro',sans-serif;
    min-height:100vh;
  }
  h1,h2,h3,.display{font-family:'Baloo 2',cursive;}
  .fantasy{font-family:'Cinzel Decorative',serif;}
  button{font-family:inherit;cursor:pointer;}
  img,svg{display:block;}

  /* ===================== HUD ===================== */
  .hud{
    position:sticky;top:0;z-index:40;
    background:linear-gradient(180deg,var(--forest-deep),var(--forest));
    color:#FFFDF6;padding:10px 16px 16px;
    box-shadow:0 4px 14px rgba(60,90,80,.2);
  }
  .hud-row{max-width:1000px;margin:0 auto;display:flex;align-items:center;justify-content:space-between;gap:10px;flex-wrap:wrap;}
  .hero-chip{display:flex;align-items:center;gap:8px;}
  .hero-avatar{width:38px;height:38px;border-radius:50%;background:var(--gold);display:flex;align-items:center;justify-content:center;font-size:1.2rem;border:2px solid #FFFDF6;flex-shrink:0;}
  .hero-name{font-weight:700;font-size:.92rem;line-height:1.1;}
  .hero-name small{display:block;font-weight:500;font-size:.68rem;color:#E4F3EC;}
  .hearts{display:flex;gap:3px;font-size:1rem;}
  .heart.lost{filter:grayscale(1) opacity(.35);}
  .gems{display:flex;align-items:center;gap:5px;background:rgba(255,255,255,.16);border-radius:999px;padding:5px 12px;font-weight:700;font-size:.85rem;}
  .soundbtn{
    width:34px;height:34px;border-radius:50%;border:1px solid rgba(255,255,255,.35);
    background:rgba(255,255,255,.14);color:#FFFDF6;font-size:1rem;display:flex;align-items:center;justify-content:center;
  }
  .bosswrap{max-width:1000px;margin:10px auto 0;}
  .bossbar-label{display:flex;justify-content:space-between;font-size:.72rem;color:#FFE9C2;margin-bottom:3px;font-weight:700;letter-spacing:.3px;text-transform:uppercase;}
  .bossbar{height:12px;background:rgba(0,0,0,.22);border-radius:999px;overflow:hidden;border:1px solid rgba(255,255,255,.2);}
  .bossbar-fill{height:100%;background:linear-gradient(90deg,var(--coral),#C4665F);transition:width .5s ease;}

  /* ===================== MAIN LAYOUT ===================== */
  main{max-width:860px;margin:0 auto;padding:26px 16px 100px;}
  section.panel{display:none;animation:fadeUp .4s ease;}
  section.panel.active{display:block;}
  @keyframes fadeUp{from{opacity:0;transform:translateY(12px);}to{opacity:1;transform:translateY(0);}}

  .scroll-card{
    background:var(--parchment-2);
    border:2px solid var(--gold-deep);
    border-radius:22px;
    box-shadow:var(--shadow);
    padding:26px;position:relative;
  }
  .scroll-card::before{
    content:"";position:absolute;inset:6px;border:1px dashed var(--gold-deep);border-radius:16px;pointer-events:none;opacity:.4;
  }
  .card{
    background:var(--parchment-2);border-radius:var(--radius);
    box-shadow:var(--shadow);padding:20px;margin-bottom:14px;border:1px solid var(--line);
  }
  .eyebrow{
    display:inline-block;background:var(--gold);color:#4A3406;
    font-weight:700;font-size:.7rem;letter-spacing:.5px;text-transform:uppercase;
    padding:4px 12px;border-radius:999px;margin-bottom:10px;
  }
  .panel-head h2{font-size:1.55rem;margin:0 0 6px;color:var(--forest-deep);}
  .panel-head p{margin:0;color:var(--ink-soft);font-size:.92rem;}
  .btn{
    border:none;border-radius:14px;padding:13px 22px;font-weight:700;font-size:.95rem;
    background:var(--gold);color:#4A3406;box-shadow:var(--shadow);
    transition:transform .15s ease;
  }
  .btn:active{transform:scale(.97);}
  .btn.outline{background:transparent;color:var(--forest-deep);box-shadow:none;border:2px solid var(--forest-deep);}
  .btn.teal{background:var(--teal);color:#fff;}
  .btn.big{padding:16px 30px;font-size:1.05rem;}
  .btn:disabled{opacity:.4;cursor:not-allowed;}
  .navrow{display:flex;justify-content:space-between;gap:10px;margin-top:20px;}

  /* ===================== TITLE / STORY SCREEN ===================== */
  .title-screen{
    text-align:center;color:#FFFDF6;padding:60px 18px 40px;max-width:640px;margin:0 auto;
  }
  .title-screen .badge{font-size:3.2rem;margin-bottom:6px;}
  .title-screen h1{font-family:'Cinzel Decorative';font-size:1.9rem;margin:0 0 10px;color:var(--gold);text-shadow:0 2px 6px rgba(60,60,40,.25);}
  .title-screen p{color:#F3FFF9;line-height:1.7;font-size:.98rem;}
  .villain-card{
    background:rgba(255,255,255,.2);border:1px solid rgba(255,255,255,.3);border-radius:18px;
    padding:16px;margin:20px 0;text-align:left;display:flex;gap:14px;align-items:flex-start;
    backdrop-filter:blur(2px);
  }
  .villain-card .ic{font-size:2rem;}
  .villain-card b{color:#FFE9B0;}

  /* ===================== CHARACTER SETUP ===================== */
  .avatar-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px;margin:16px 0;}
  .avatar-opt{
    border:2px solid var(--line);border-radius:18px;padding:14px 10px;text-align:center;background:var(--parchment-2);
  }
  .avatar-opt .em{font-size:2.1rem;}
  .avatar-opt b{display:block;margin-top:4px;font-size:.9rem;}
  .avatar-opt span{display:block;font-size:.72rem;color:var(--ink-soft);margin-top:2px;}
  .avatar-opt.picked{border-color:var(--gold);background:#FFF3D6;box-shadow:0 0 0 3px rgba(217,160,62,.2);}
  input.nameinput{
    width:100%;padding:12px 14px;border:2px solid var(--line);border-radius:14px;font-size:1rem;font-family:inherit;margin-top:4px;
  }
  input.nameinput:focus{outline:none;border-color:var(--gold);}

  /* ===================== MAP ===================== */
  .map-wrap{
    background:linear-gradient(180deg,#FFF3D6,var(--parchment));
    border:3px solid var(--gold-deep);border-radius:24px;padding:26px 16px;
    box-shadow:var(--shadow);position:relative;overflow:hidden;
  }
  .map-path{position:relative;max-width:420px;margin:0 auto;}
  .map-node{
    display:flex;align-items:center;gap:12px;background:var(--parchment-2);
    border:2px solid var(--gold-deep);border-radius:18px;padding:12px 14px;margin-bottom:0;
    position:relative;cursor:pointer;
  }
  .map-node + .map-node{margin-top:26px;}
  .map-node::before{
    content:"";position:absolute;left:29px;bottom:100%;width:3px;height:26px;
    background:repeating-linear-gradient(180deg,var(--gold-deep) 0 5px, transparent 5px 10px);
  }
  .map-node:first-child::before{display:none;}
  .map-node.locked{opacity:.5;cursor:not-allowed;filter:grayscale(.5);}
  .map-node.done{border-color:var(--teal);}
  .map-node.current{box-shadow:0 0 0 4px rgba(217,160,62,.22);animation:glow 1.6s infinite;}
  @keyframes glow{50%{box-shadow:0 0 0 8px rgba(217,160,62,.1);}}
  .map-ic{
    width:46px;height:46px;border-radius:50%;background:var(--forest);color:#FFFDF6;
    display:flex;align-items:center;justify-content:center;font-size:1.35rem;flex-shrink:0;
  }
  .map-node.done .map-ic{background:var(--teal);}
  .map-node.locked .map-ic{background:#D8CDA9;}
  .map-txt b{display:block;font-size:.95rem;color:var(--forest-deep);}
  .map-txt span{font-size:.76rem;color:var(--ink-soft);}
  .map-node .status{margin-left:auto;font-size:1.1rem;}
  .castle-node{
    margin-top:26px;text-align:center;position:relative;
  }
  .castle-node::before{
    content:"";position:absolute;left:50%;bottom:100%;width:3px;height:26px;transform:translateX(-50%);
    background:repeating-linear-gradient(180deg,var(--coral) 0 5px, transparent 5px 10px);
  }
  .castle-box{
    display:inline-flex;flex-direction:column;align-items:center;gap:4px;
    background:linear-gradient(180deg,#C98FCB,#9C7FE0);color:#FFF8FD;border:2px solid var(--coral);
    border-radius:20px;padding:16px 22px;cursor:pointer;
  }
  .castle-box.locked{opacity:.55;cursor:not-allowed;}
  .castle-box .cic{font-size:2.4rem;}

  /* ===================== READING ===================== */
  .story p{line-height:1.9;font-size:1.02rem;margin:0 0 14px;}
  .wd{
    background:#FFF3D6;color:var(--gold-deep);border-bottom:2px dashed var(--gold-deep);
    padding:0 2px;border-radius:4px;font-weight:600;cursor:pointer;
  }
  .wd:hover{background:var(--gold);color:#4A3406;}
  /* ===================== COMPANION (Chích Bông) ===================== */
  .companion-wrap{
    position:fixed;right:16px;bottom:16px;z-index:65;
    display:none;
  }
  .companion-wrap.show{display:flex;}
  .companion-avatar-btn{
    width:58px;height:58px;border-radius:50%;background:var(--forest);border:3px solid var(--parchment-2);
    display:flex;align-items:center;justify-content:center;font-size:1.7rem;box-shadow:var(--shadow);
    animation:bob 2.4s ease-in-out infinite;flex-shrink:0;
  }
  @keyframes bob{0%,100%{transform:translateY(0);}50%{transform:translateY(-6px);}}

  .companion-modal{
    position:fixed;inset:0;background:rgba(60,80,70,0.45);
    display:none;align-items:center;justify-content:center;z-index:80;padding:20px;
  }
  .companion-modal.show{display:flex;}
  .companion-card{
    background:#FFFFFF;border:3px solid var(--gold-deep);border-radius:26px;
    max-width:420px;width:100%;padding:28px 24px 24px;text-align:center;position:relative;
    box-shadow:0 16px 40px rgba(80,70,50,.28);
    animation:popIn .35s cubic-bezier(.34,1.56,.64,1);
  }
  @keyframes popIn{0%{transform:scale(.5) translateY(30px);opacity:0;}100%{transform:scale(1) translateY(0);opacity:1;}}
  .companion-card .bigbird{font-size:3.4rem;margin-bottom:8px;display:inline-block;animation:bob 1.8s ease-in-out infinite;}
  .companion-card .cname{display:block;font-family:'Baloo 2';font-weight:700;color:var(--gold-deep);font-size:1.05rem;margin-bottom:6px;}
  .companion-card .msg{color:#3A3226;font-size:1rem;line-height:1.65;font-weight:500;}
  .companion-card .msg b{color:var(--gold-deep);}
  .companion-card .closebtn{
    margin-top:20px;background:var(--teal);color:#fff;border:none;border-radius:14px;
    padding:11px 26px;font-weight:700;font-size:.92rem;
  }
  .companion-card .closebtn:active{transform:scale(.97);}
  .companion-card .closex{position:absolute;top:12px;right:14px;background:none;border:none;font-size:1.35rem;color:#9a9578;}

  .hintbtn{
    display:inline-flex;align-items:center;gap:5px;background:var(--forest);border:none;
    color:#FFFFFF;border-radius:12px;padding:7px 12px;font-size:.78rem;font-weight:700;margin-top:8px;
  }
  .hintbtn:hover{background:var(--forest-deep);}

  .map-companion{
    position:absolute;left:-6px;font-size:1.9rem;transition:top .6s cubic-bezier(.34,1.4,.64,1);
    filter:drop-shadow(0 4px 4px rgba(0,0,0,.15));animation:bob 2.4s ease-in-out infinite;
    z-index:5;
  }
  .map-hero{
    position:absolute;left:32px;font-size:1.7rem;transition:top .6s cubic-bezier(.34,1.4,.64,1) .08s;
    filter:drop-shadow(0 4px 4px rgba(0,0,0,.15));animation:bob 2.4s ease-in-out infinite .3s;
    z-index:6;display:flex;align-items:center;gap:1px;
  }
  .map-hero .gearic{font-size:1.05rem;transform:translateY(2px);}

  .glossary-pop{
    position:fixed;inset:0;background:rgba(50,60,55,0.45);
    display:none;align-items:center;justify-content:center;z-index:60;padding:16px;
  }
  .glossary-pop.show{display:flex;}
  .glossary-box{
    background:var(--parchment-2);border-radius:22px;max-width:420px;width:100%;
    padding:24px;box-shadow:0 16px 40px rgba(80,70,50,.28);position:relative;border:2px solid var(--gold-deep);
  }
  .glossary-box h3{margin:0 0 6px;color:var(--forest-deep);font-size:1.3rem;}
  .glossary-box .tag{font-size:.72rem;color:var(--sky);font-weight:700;text-transform:uppercase;letter-spacing:.4px;}
  .glossary-box p{margin:10px 0;line-height:1.6;font-size:.95rem;}
  .glossary-box .ex{background:#FFF3D6;border-radius:12px;padding:10px 12px;font-style:italic;font-size:.9rem;color:var(--ink-soft);}
  .glossary-box .tip{margin-top:12px;background:#FDF1E6;border:1px solid #F0D6AE;border-radius:12px;padding:10px 12px;font-size:.88rem;display:flex;gap:8px;}
  .close-x{position:absolute;top:14px;right:16px;border:none;background:none;font-size:1.3rem;color:var(--ink-soft);}

  /* ===================== QUIZ / GENERIC ===================== */
  .qcard h4{margin:0 0 12px;font-size:1.02rem;}
  .opt{display:block;width:100%;text-align:left;background:var(--parchment-2);border:2px solid var(--line);border-radius:14px;padding:11px 14px;margin-bottom:8px;font-size:.94rem;}
  .opt:hover{border-color:var(--gold);}
  .opt.correct{border-color:var(--teal);background:#E9F7F1;}
  .opt.wrong{border-color:var(--coral);background:#FCEEEC;}
  .qfeedback{font-size:.85rem;margin-top:6px;padding:8px 10px;border-radius:10px;display:none;}
  .qfeedback.show{display:block;}
  .qfeedback.ok{background:#E9F7F1;color:#2E7A63;}
  .qfeedback.no{background:#FCEEEC;color:#B15850;}
  .tok{display:inline-block;background:var(--parchment-2);border:2px solid var(--line);border-radius:10px;padding:3px 9px;margin:2px;font-size:.98rem;}
  .tok.picked{border-color:var(--gold);background:#FFF3D6;}
  .tok.right{border-color:var(--teal);background:#E9F7F1;}
  .tok.miss{border-color:var(--coral);background:#FCEEEC;}
  .tok.punct{border:none;background:none;padding:0 2px;color:var(--ink-soft);}
  .hunt-sentence{font-size:1.08rem;line-height:2.4;margin-bottom:14px;}

  /* ===================== DICTATION ===================== */
  .dict-sentence{font-size:1.15rem;font-weight:600;text-align:center;background:#FFF3D6;border-radius:16px;padding:18px;margin-bottom:14px;color:var(--gold-deep);}
  .countdown{text-align:center;font-family:'Baloo 2';font-size:2rem;color:var(--forest-deep);margin-bottom:6px;}
  textarea{width:100%;border:2px solid var(--line);border-radius:14px;padding:14px;font-size:1rem;font-family:inherit;resize:vertical;min-height:70px;}
  textarea:focus{outline:none;border-color:var(--gold);}
  .diff-line{font-size:1.05rem;line-height:2;margin-top:12px;}
  .diff-line .ok{color:var(--teal);font-weight:600;}
  .diff-line .bad{color:var(--coral);font-weight:700;text-decoration:underline wavy;}
  .memo{background:#FDF1E6;border:1px solid #F0D6AE;border-radius:16px;padding:14px 16px;margin-top:14px;font-size:.9rem;}
  .memo b{display:flex;align-items:center;gap:6px;color:var(--gold-deep);margin-bottom:4px;}

  /* ===================== VOCAB ===================== */
  .vocab-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(180px,1fr));gap:12px;margin-bottom:20px;}
  .flip-card{perspective:900px;height:126px;cursor:pointer;}
  .flip-inner{position:relative;width:100%;height:100%;transition:transform .5s;transform-style:preserve-3d;}
  .flip-card.open .flip-inner{transform:rotateY(180deg);}
  .flip-face{position:absolute;inset:0;border-radius:16px;display:flex;flex-direction:column;align-items:center;justify-content:center;padding:10px;text-align:center;backface-visibility:hidden;box-shadow:var(--shadow);}
  .flip-front{background:var(--forest);color:#FFFDF6;font-family:'Baloo 2';font-weight:600;font-size:1.02rem;}
  .flip-back{background:var(--parchment-2);transform:rotateY(180deg);font-size:.76rem;line-height:1.4;border:1px solid var(--line);}
  .flip-back b{display:block;font-family:'Baloo 2';color:var(--gold-deep);font-size:.88rem;margin-bottom:3px;}
  .match-wrap{display:grid;grid-template-columns:repeat(auto-fill,minmax(105px,1fr));gap:10px;}
  .mcard{background:var(--forest);color:#FFFDF6;border-radius:14px;min-height:76px;display:flex;align-items:center;justify-content:center;text-align:center;padding:8px;font-size:.8rem;font-weight:600;box-shadow:var(--shadow);transition:transform .2s;}
  .mcard.flipped{background:var(--parchment-2);color:var(--ink);border:2px solid var(--gold);}
  .mcard.matched{background:#E9F7F1;color:#2E7A63;border:2px solid var(--teal);opacity:.7;}
  .mcard.shake{animation:shake .35s;}
  @keyframes shake{25%{transform:translateX(-4px);}75%{transform:translateX(4px);}}
  .match-status{margin-top:12px;font-size:.9rem;color:var(--ink-soft);text-align:center;}

  /* ===================== MINI WRITE ===================== */
  .hint-box{background:#FFF3D6;border-radius:16px;padding:14px 16px;font-size:.88rem;margin-bottom:14px;}
  .hint-box ul{margin:6px 0 0;padding-left:18px;}
  .wordcount{text-align:right;font-size:.8rem;color:var(--ink-soft);margin-top:6px;}

  /* ===================== BOSS / ENDING ===================== */
  .boss-hero{text-align:center;background:linear-gradient(160deg,#C98FCB,#9C7FE0);color:#FFF8FD;border-radius:22px;padding:30px 20px;margin-bottom:18px;border:2px solid var(--coral);}
  .boss-hero .em{font-size:3.4rem;}
  .boss-hero h3{margin:8px 0 4px;font-size:1.4rem;color:#FFE9B0;}
  .boss-hero p{margin:0;color:#FFF0F8;font-size:.9rem;}
  .final-fight-bar{height:16px;background:rgba(0,0,0,.25);border-radius:999px;overflow:hidden;margin:14px 0;border:1px solid rgba(255,255,255,.2);}
  .final-fight-fill{height:100%;background:linear-gradient(90deg,var(--coral),#C4665F);transition:width .4s ease;}
  .victory-scene{text-align:center;padding:10px;}
  .victory-scene .em{font-size:4rem;}
  .notebook{list-style:none;margin:0;padding:0;display:grid;gap:10px;}
  .notebook li{background:var(--parchment-2);border:1px solid var(--line);border-radius:14px;padding:12px 14px;font-size:.88rem;}
  .notebook li b{color:var(--coral);}
  .empty-note{text-align:center;color:var(--ink-soft);font-size:.9rem;padding:16px;}

  @media(max-width:640px){
    .panel-head h2{font-size:1.3rem;}
    .title-screen h1{font-size:1.5rem;}
    .avatar-grid{grid-template-columns:1fr 1fr;}
  }
</style>
</head>
<body>

<div class="hud" id="hud" style="display:none;">
  <div class="hud-row">
    <div class="hero-chip">
      <div class="hero-avatar" id="hudAvatar">🛡️</div>
      <div class="hero-name" id="hudName">Hiệp sĩ<small>Hành trình giải cứu công chúa</small></div>
    </div>
    <div class="hearts" id="hudHearts"></div>
    <div class="gems">💎 <span id="hudGems">0</span></div>
    <button class="soundbtn" id="soundBtn" onclick="toggleMusic()">🔊</button>
  </div>
  <div class="bosswrap">
    <div class="bossbar-label"><span>🐉 Sức mạnh Ác Long Lạc Điệu</span><span id="bossPct">100%</span></div>
    <div class="bossbar"><div class="bossbar-fill" id="bossFill" style="width:100%;"></div></div>
  </div>
</div>

<main>

  <!-- SCREEN A: TITLE -->
  <section class="panel active" id="pTitle">
    <div class="title-screen">
      <div class="badge">🏰</div>
      <h1>HÀNH TRÌNH GIẢI CỨU<br>CÔNG CHÚA SƠN CA</h1>
      <p>Ngày xưa, khu rừng Thi Nhạc luôn rộn ràng tiếng đàn, tiếng hót. Nhưng từ khi <b>Ác Long Lạc Điệu</b> xuất hiện, mọi âm thanh đều trở nên sai lệch, chữ nghĩa đảo lộn, và <b>Công chúa Sơn Ca</b> (người giữ giọng hát trong trẻo nhất khu rừng) đã bị giam trong Tháp Lạc Điệu.</p>
      <div class="villain-card">
        <div class="ic">🐉</div>
        <div><b>Ác Long Lạc Điệu</b> chuyên đánh cắp chữ đúng, thay bằng lỗi chính tả và làm quên mất nghĩa của từ. Chỉ có một chiến binh nhỏ tuổi, giỏi ngôn ngữ, mới phá được phép của nó.</div>
      </div>
      <div class="villain-card">
        <div class="ic">🐦</div>
        <div><b>Chích Bông</b>, trợ lý nhỏ của công chúa Sơn Ca, đã trốn thoát và sẽ đồng hành cùng bạn suốt hành trình. Bí quá thì bấm vào Chích Bông ở góc màn hình để xin gợi ý nhé!</div>
      </div>
      <p>Bạn sẽ vượt qua 7 vùng đất trong khu rừng, thu thập <b>Ngọc Âm Thanh</b> 💎, rồi bước vào Tháp Lạc Điệu để giải cứu công chúa!</p>
      <button class="btn big" onclick="startAdventure()">🎵 Bắt đầu phiêu lưu</button>
    </div>
  </section>

  <!-- SCREEN B: CHARACTER SETUP -->
  <section class="panel" id="pSetup">
    <div class="scroll-card">
      <span class="eyebrow">Tạo nhân vật</span>
      <h2 style="margin:0 0 4px;color:var(--forest-deep);">Bạn là ai trong hành trình này?</h2>
      <p style="color:var(--ink-soft);margin:0 0 16px;">Đặt tên và chọn lớp nhân vật của mình.</p>
      <label style="font-weight:700;font-size:.9rem;">Tên chiến binh</label>
      <input class="nameinput" id="heroNameInput" placeholder="Nhập tên của em..." maxlength="18">
      <div class="avatar-grid" id="avatarGrid"></div>
      <button class="btn big" style="width:100%;margin-top:6px;" onclick="confirmCharacter()">Xác nhận và mở bản đồ 🗺️</button>
    </div>
  </section>

  <!-- SCREEN C: MAP -->
  <section class="panel" id="pMap">
    <div class="panel-head">
      <span class="eyebrow">Bản đồ khu rừng Thi Nhạc</span>
      <h2>Chọn vùng đất tiếp theo</h2>
      <p>Hoàn thành mỗi vùng đất để mở khoá vùng kế tiếp và làm suy yếu Ác Long.</p>
    </div>
    <div class="map-wrap" id="mapWrap" style="position:relative;">
      <div class="map-companion" id="mapCompanion">🐦</div>
      <div class="map-hero" id="mapHero"><span>🧍</span><span class="gearic">🎻</span></div>
      <div class="map-path" id="mapPath"></div>
      <div class="castle-node">
        <div class="castle-box locked" id="castleNode" onclick="tryGo(8)">
          <div class="cic">🏰</div>
          <b>Tháp Lạc Điệu, trận chiến cuối</b>
          <span id="castleStatus" style="font-size:.72rem;">🔒 Hoàn thành 7 vùng đất để mở</span>
        </div>
      </div>
    </div>
  </section>

  <!-- 1. WARM UP -->
  <section class="panel" id="p1">
    <div class="panel-head">
      <span class="eyebrow">Vùng 1 · Cổng Yêu Tinh Chữ · ⏳10 phút</span>
      <h2>🐛 Bắt lỗi nhanh</h2>
      <p>Yêu tinh đã giấu 1 lỗi chính tả trong mỗi câu thần chú. Bấm đúng từ sai để phá phép!</p>
    </div>
    <div id="warmupWrap"></div>
    <div class="navrow"><button class="btn outline" onclick="go('pMap')">◀ Về bản đồ</button><button class="btn" id="w1next" onclick="finishStation(1)" disabled>Hoàn thành vùng 1 ▶</button></div>
  </section>

  <!-- 2. READING -->
  <section class="panel" id="p2">
    <div class="panel-head">
      <span class="eyebrow">Vùng 2 · Cuộn Giấy Cổ · ⏳20 phút</span>
      <h2>📜 Giải mã truyện "Thi nhạc"</h2>
      <p>Đọc cuộn giấy cổ để hiểu vì sao Ác Long ghét âm nhạc. Từ <span class="wd" style="cursor:default;">gạch vàng</span> là từ mới, bấm để xem nghĩa.</p>
    </div>
    <div class="card story" id="storyWrap"></div>
    <div class="navrow"><button class="btn outline" onclick="go('pMap')">◀ Về bản đồ</button><button class="btn" onclick="finishStation(2)">Hoàn thành vùng 2 ▶</button></div>
  </section>

  <!-- 3. QUIZ -->
  <section class="panel" id="p3">
    <div class="panel-head">
      <span class="eyebrow">Vùng 3 · Cầu Thử Thách · ⏳5 phút</span>
      <h2>🌉 Trả lời để qua cầu</h2>
      <p>Trả lời đúng để cầu hiện ra, tránh rơi xuống vực của Ác Long!</p>
    </div>
    <div id="quizWrap"></div>
    <div class="navrow"><button class="btn outline" onclick="go('pMap')">◀ Về bản đồ</button><button class="btn" id="w3next" onclick="finishStation(3)" disabled>Hoàn thành vùng 3 ▶</button></div>
  </section>

  <!-- 4. DICTATION -->
  <section class="panel" id="p4">
    <div class="panel-head">
      <span class="eyebrow">Vùng 4 · Hang Yêu Tinh Chính Tả · ⏳20 phút</span>
      <h2>✍️ Hang tối chính tả</h2>
      <p>Nhìn câu thần chú trong 8 giây, ghi nhớ, rồi viết lại đúng để xua tan bóng tối.</p>
    </div>
    <div class="card" id="dictWrap"></div>
    <div class="navrow"><button class="btn outline" onclick="go('pMap')">◀ Về bản đồ</button><button class="btn" id="w4next" onclick="finishStation(4)" disabled>Hoàn thành vùng 4 ▶</button></div>
  </section>

  <!-- 5. VOCAB -->
  <section class="panel" id="p5">
    <div class="panel-head">
      <span class="eyebrow">Vùng 5 · Vườn Phép Thuật Từ Vựng · ⏳15 phút</span>
      <h2>🌿 Thu thập phép từ vựng</h2>
      <p>Bấm từng thẻ để học phép mới, rồi chơi ghép thẻ trí nhớ để khoá phép vào tâm trí.</p>
    </div>
    <div class="vocab-grid" id="vocabGrid"></div>
    <div class="card">
      <h3 style="margin:0 0 4px;">🃏 Ghép thẻ trí nhớ</h3>
      <p style="margin:0 0 14px;color:var(--ink-soft);font-size:.88rem;">Lật 2 thẻ, nếu từ khớp đúng nghĩa thì phép được khoá lại vĩnh viễn.</p>
      <div class="match-wrap" id="matchWrap"></div>
      <div class="match-status" id="matchStatus"></div>
      <div style="text-align:center;margin-top:12px;"><button class="btn outline" onclick="newMatchGame()">🔄 Ván phép mới</button></div>
    </div>
    <div class="navrow"><button class="btn outline" onclick="go('pMap')">◀ Về bản đồ</button><button class="btn" onclick="finishStation(5)">Hoàn thành vùng 5 ▶</button></div>
  </section>

  <!-- 6. NOUN HUNT -->
  <section class="panel" id="p6">
    <div class="panel-head">
      <span class="eyebrow">Vùng 6 · Đầm Lầy Danh Từ · ⏳10 phút</span>
      <h2>🎯 Săn danh từ trong đầm lầy</h2>
      <p>Bấm vào các từ là <b>danh từ</b> (chỉ người, vật, con vật) để dọn sạch đầm lầy.</p>
    </div>
    <div id="huntWrap"></div>
    <div class="navrow"><button class="btn outline" onclick="go('pMap')">◀ Về bản đồ</button><button class="btn" id="w6next" onclick="finishStation(6)" disabled>Hoàn thành vùng 6 ▶</button></div>
  </section>

  <!-- 7. MINI WRITE -->
  <section class="panel" id="p7">
    <div class="panel-head">
      <span class="eyebrow">Vùng 7 · Tháp Phù Thuỷ · ⏳8 phút</span>
      <h2>📝 Viết câu thần chú cuối</h2>
      <p>Viết 2 đến 3 câu nêu lí do em thích một nhân vật trong "Thi nhạc". Đây chính là câu thần chú mạnh nhất để bước vào Tháp Lạc Điệu.</p>
    </div>
    <div class="card">
      <div class="hint-box">
        💡 <b>Công thức thần chú:</b>
        <ul>
          <li>Mở đầu: Em thích nhân vật nào?</li>
          <li>Triển khai: Vì sao em thích? (ngoại hình, tiết mục, tính cách...)</li>
          <li>Kết thúc: Nhắc lại tình cảm của em với nhân vật đó.</li>
        </ul>
      </div>
      <textarea id="miniWrite" placeholder="Em thích nhân vật... vì..."></textarea>
      <div class="wordcount" id="wcount">0 từ</div>
    </div>
    <div class="navrow"><button class="btn outline" onclick="go('pMap')">◀ Về bản đồ</button><button class="btn" id="w7next" onclick="finishStation(7)" disabled>Hoàn thành vùng 7 ▶</button></div>
  </section>

  <!-- 8. BOSS / ENDING -->
  <section class="panel" id="p8">
    <div class="panel-head">
      <span class="eyebrow">Tháp Lạc Điệu · Trận chiến cuối</span>
      <h2>🐉 Đối đầu Ác Long Lạc Điệu</h2>
      <p>Dùng toàn bộ phép đã học để hạ gục Ác Long và giải cứu công chúa!</p>
    </div>
    <div class="boss-hero" id="bossHero"></div>
    <div class="card" id="finalFightCard" style="display:none;">
      <h3 style="margin:0 0 8px;color:var(--forest-deep);">⚔️ Đòn phép cuối cùng</h3>
      <p style="color:var(--ink-soft);font-size:.88rem;margin:0 0 12px;">Trả lời nhanh để tung đòn phép cuối, hạ gục Ác Long hoàn toàn!</p>
      <div id="finalFightWrap"></div>
    </div>
    <div class="card">
      <h3 style="margin:0 0 10px;">📓 Sổ tay phép thuật (những chỗ cần ôn lại)</h3>
      <ul class="notebook" id="notebook"></ul>
    </div>
    <div class="navrow"><button class="btn outline" onclick="restartAll()">🔄 Bắt đầu hành trình mới</button><span></span></div>
  </section>

</main>

<div class="companion-wrap" id="companionWrap">
  <button class="companion-avatar-btn" id="companionBtn" onclick="companionTapped()">🐦</button>
</div>

<div class="companion-modal" id="companionModal">
  <div class="companion-card">
    <button class="closex" onclick="closeCompanion()">✕</button>
    <div class="bigbird">🐦</div>
    <span class="cname">Chích Bông nói</span>
    <div class="msg" id="companionMsg"></div>
    <button class="closebtn" onclick="closeCompanion()">Đã hiểu rồi! 👍</button>
  </div>
</div>

<div class="glossary-pop" id="glossPop">
  <div class="glossary-box">
    <button class="close-x" onclick="closeGloss()">✕</button>
    <span class="tag" id="gTag">Phép mới</span>
    <h3 id="gWord"></h3>
    <p id="gMean"></p>
    <div class="ex" id="gEx"></div>
    <div class="tip" id="gTip"></div>
  </div>
</div>

<script>
/* ================= AUDIO ENGINE (procedural, no copyrighted files) ================= */
const Audio1 = (()=>{
  let ctx=null, master=null, musicOn=true, musicTimer=null, step=0;
  const bass = [110,110,146.83,110, 98,98,130.81,98];
  const arp  = [220,261.63,329.63,392, 349.23,329.63,261.63,220];
  function init(){
    if(ctx) return;
    ctx = new (window.AudioContext||window.webkitAudioContext)();
    master = ctx.createGain(); master.gain.value=0.06; master.connect(ctx.destination);
  }
  function tone(freq,dur,type,gainVal,delay){
    if(!ctx) return;
    const o = ctx.createOscillator(); const g = ctx.createGain();
    o.type=type||'triangle'; o.frequency.value=freq;
    g.gain.value=0;
    o.connect(g); g.connect(master);
    const t0 = ctx.currentTime+(delay||0);
    g.gain.setValueAtTime(0,t0);
    g.gain.linearRampToValueAtTime(gainVal||0.5, t0+0.02);
    g.gain.exponentialRampToValueAtTime(0.001, t0+dur);
    o.start(t0); o.stop(t0+dur+0.05);
  }
  function loopStep(){
    if(!musicOn||!ctx) return;
    tone(bass[step%bass.length],0.35,'sine',0.9,0);
    tone(arp[step%arp.length],0.28,'triangle',0.55,0.1);
    step++;
  }
  function startMusic(){
    init();
    if(ctx.state==='suspended') ctx.resume();
    if(musicTimer) return;
    musicTimer = setInterval(loopStep,300);
  }
  function stopMusic(){ if(musicTimer){clearInterval(musicTimer); musicTimer=null;} }
  function toggle(){
    musicOn = !musicOn;
    if(musicOn) startMusic(); else stopMusic();
    return musicOn;
  }
  function correct(){ init(); tone(660,0.12,'square',0.35,0); tone(880,0.16,'square',0.3,0.09); }
  function wrong(){ init(); tone(180,0.28,'sawtooth',0.3,0); }
  function heartLost(){ init(); tone(140,0.35,'sawtooth',0.32,0); tone(100,0.4,'sawtooth',0.25,0.1); }
  function victory(){
    init();
    [523.25,659.25,783.99,1046.5].forEach((f,i)=>tone(f,0.35,'triangle',0.4,i*0.14));
  }
  return {startMusic,stopMusic,toggle,correct,wrong,heartLost,victory,get on(){return musicOn;}};
})();
function toggleMusic(){
  const on = Audio1.toggle();
  document.getElementById('soundBtn').textContent = on? '🔊':'🔇';
}

/* ================= DATA (nội dung học) ================= */
const AVATARS = [
 {em:"🎻",name:"Nhạc Sĩ Nhí",desc:"Cảm âm tốt, nghe tinh",gear:"🎻"},
 {em:"🛡️",name:"Hiệp Sĩ Chữ",desc:"Dũng cảm, không sợ lỗi sai",gear:"🗡️"},
 {em:"🏹",name:"Thợ Săn Từ",desc:"Tinh mắt tìm từ đúng",gear:"🏹"},
 {em:"🔮",name:"Phù Thuỷ Ngôn Từ",desc:"Phép thuật từ vựng mạnh",gear:"🪄"}
];

const VOCAB = [
 {w:"kiêu hãnh",m:"Cảm thấy rất vui và tự hào về điều mình vừa làm được, giống như khi em được cô khen trước cả lớp.",ex:"Gà trống kiêu hãnh bước lên sân khấu.",wrong:"kiêu hảnh",tip:"“Hãnh” viết dấu ngã (~), giống chữ “hãnh” trong “hãnh diện”."},
 {w:"đĩnh đạc",m:"Đi đứng và nói năng chậm rãi, đàng hoàng, không vội vàng, giống dáng đi của một người lớn tự tin.",ex:"Dế mèn bước ra đĩnh đạc và tự tin.",wrong:"định đạc",tip:"“Đĩnh” tả dáng đi, viết dấu ngã (~). Khác với “định” là quyết định, viết dấu nặng."},
 {w:"dịu dàng",m:"Nhẹ nhàng, êm ái, dễ thương, không ồn ào hay gắt gỏng.",ex:"Chị hoạ mi hát rất dịu dàng.",wrong:"giịu dàng",tip:"“Dịu” viết bằng chữ D, không viết bằng GI."},
 {w:"uyển chuyển",m:"Chuyển động mềm mại, nhịp nhàng, đẹp mắt, giống như múa.",ex:"Điệu múa uyển chuyển như sóng nước.",wrong:"uyển chuyễn",tip:"Chữ cuối là “chuyểN”, không phải “chuyểNG”."},
 {w:"réo rắt",m:"Âm thanh cao, trong và ngân dài, nghe rất vui tai, như tiếng đàn hay tiếng chim hót.",ex:"Tiếng vi-ô-lông réo rắt vang lên.",wrong:"réo rắc",tip:"“Rắt” tận cùng bằng T, giống vần trong chữ “sắt”."},
 {w:"rạo rực",m:"Cảm giác nôn nao, háo hức trong lòng, giống như khi sắp được đi chơi.",ex:"Nghe nhạc xuân, lòng em rạo rực.",wrong:"dạo rực",tip:"“Rạo” viết bằng chữ R, đi cùng nghĩa với từ “rộn ràng”."},
 {w:"rù rì",m:"Âm thanh nhỏ và đều đều, cứ vang lên mãi, như tiếng ong bay.",ex:"Đàn ong bay rù rì quanh hàng giậu.",wrong:"gù gì",tip:"Cả hai chữ trong từ đều viết bằng R."},
 {w:"xào xạc",m:"Âm thanh lá cây cọ vào nhau khi có gió thổi qua.",ex:"Gió thổi, lá khô xào xạc.",wrong:"sào sạc",tip:"Viết bằng X (không phải S). Nhớ theo cặp “xào xạc, lá cây”."},
 {w:"thầm thì",m:"Nói rất khẽ, rất nhỏ, chỉ đủ để người bên cạnh nghe thấy.",ex:"Gió thầm thì với lá cây.",wrong:"thầm chì",tip:"Cả hai chữ trong từ đều viết bằng TH."},
 {w:"khoẻ khoắn",m:"Có sức khoẻ tốt, người nhanh nhẹn, tràn đầy năng lượng.",ex:"Dế mèn bước ra khoẻ khoắn.",wrong:"khoẻ khoắng",tip:"“Khoắn” không có chữ G ở cuối. Khác với “khoắng” là quậy nước."},
 {w:"trang nhã",m:"Đẹp một cách nhẹ nhàng, lịch sự, không loè loẹt.",ex:"Chiếc áo nâu trông thật trang nhã.",wrong:"chang nhã",tip:"“Trang” viết bằng TR, giống chữ “trang” trong “trang phục”."},
 {w:"nghiêm trang",m:"Có vẻ mặt nghiêm túc, đứng đắn, không đùa giỡn.",ex:"Thầy vàng anh đứng dậy vẻ nghiêm trang.",wrong:"nghiêm chang",tip:"“Trang” luôn viết TR khi tả vẻ mặt nghiêm túc."},
 {w:"hồi hộp",m:"Vừa lo vừa mong chờ một điều sắp xảy ra, giống như khi chờ mở quà.",ex:"Cả lớp hồi hộp chờ kết quả.",wrong:"hồi hợp",tip:"“Hộp” viết dấu nặng (.)."},
 {w:"mãn nguyện",m:"Cảm thấy hài lòng và vui vì mọi việc diễn ra tốt đẹp.",ex:"Thầy giáo mãn nguyện khi thấy học trò thành công.",wrong:"mãng nguyện",tip:"“Mãn” không có chữ G ở cuối."},
 {w:"hứng khởi",m:"Vui vẻ, phấn khích, tràn đầy năng lượng tích cực.",ex:"Gà trống hát với vẻ hứng khởi.",wrong:"hứng khỡi",tip:"“Khởi” viết dấu hỏi (?), giống chữ “khởi” trong “khởi đầu”."},
 {w:"độc đáo",m:"Có nét riêng, không giống ai khác, rất đặc biệt.",ex:"Mỗi bạn có phong cách độc đáo.",wrong:"độc đão",tip:"“Đáo” viết dấu sắc (´). Khác với “đảo” (dấu hỏi, nghĩa là hòn đảo)."},
 {w:"tiết tấu",m:"Nhịp điệu của một bài nhạc, nhanh hay chậm, mạnh hay nhẹ.",ex:"Tiết tấu bài hát rất vui nhộn.",wrong:"tiếc tấu",tip:"Viết là “tiết” chứ không phải “tiếc”. “Tiết” nói về nhịp điệu, còn “tiếc” là cảm giác buồn vì mất gì đó."},
 {w:"tác phẩm",m:"Một sản phẩm do mình sáng tạo ra, ví dụ một bài hát, bức tranh hay bài văn.",ex:"Ve sầu trình bày tác phẩm của mình.",wrong:"tát phẩm",tip:"“Tác” không có dấu nặng."},
 {w:"sáng chói",m:"Rất sáng và nổi bật, khiến ai cũng phải chú ý.",ex:"Gian phòng tràn ngập âm thanh sáng chói.",wrong:"sáng chóe",tip:"“Chói” tả ánh sáng mạnh. Khác với “chói tai” là tả âm thanh."},
 {w:"mênh mông",m:"Rộng lớn đến mức không nhìn thấy điểm kết thúc.",ex:"Bầu trời xanh mênh mông.",wrong:"mênh môn",tip:"“Mông” có chữ G ở cuối, dễ quên khi viết nhanh."},
 {w:"tha thướt",m:"Dáng vẻ mềm mại và nhẹ nhàng khi di chuyển, thường tả tà áo dài bay trong gió.",ex:"Trong tà áo dài tha thướt, hoạ mi bước ra.",wrong:"tha thược",tip:"“Thướt” có vần ƯƠT, không phải ƯỢC."}
];

const WARMUP = [
 {show:["Ve","sầu","biểu","diễn","với","vẽ","tự","tin."],wrongIdx:5,right:"vẻ",note:"“Vẻ” (dấu hỏi) nghĩa là dáng vẻ, biểu cảm trên khuôn mặt. Còn “vẽ” (dấu ngã) là hành động vẽ tranh, khác nghĩa hoàn toàn."},
 {show:["Gà","trống","kiêu","hảnh","ngẩng","đầu."],wrongIdx:3,right:"hãnh",note:"“Hãnh” trong từ “kiêu hãnh” viết dấu ngã (~), không viết dấu hỏi."},
 {show:["Dế","mèn","bước","ra","khoẻ","khoắng","và","trang","nhã."],wrongIdx:5,right:"khoắn",note:"“Khoắn” trong “khoẻ khoắn” không có chữ G ở cuối. Khác với “khoắng” là quậy nước."},
 {show:["Hoạ","mi","trông","thật","dịu","dàn."],wrongIdx:5,right:"dàng",note:"“Dàng” trong từ láy “dịu dàng” phải có chữ G ở cuối."},
 {show:["Gió","thổi,","lá","khô","sào","xạc."],wrongIdx:4,right:"xào",note:"“Xào” trong “xào xạc” viết bằng X, không viết bằng S."},
 {show:["Bầu","trời","xanh","mênh","môn."],wrongIdx:4,right:"mông",note:"“Mông” trong “mênh mông” phải có chữ G ở cuối."}
];

const STORY = [
 "Cuộn giấy cổ kể rằng: hôm ấy là ngày thi tốt nghiệp của các học trò thầy giáo vàng anh, người thầy mà công chúa Sơn Ca luôn kính trọng.",
 "Ve sầu được thầy mời trình bày <span class='wd' data-w='tác phẩm'>tác phẩm</span> trước tiên. Mặc áo măng tô trong suốt, đôi mắt nâu lấp lánh, đầy vẻ tự tin, ve sầu biểu diễn bản nhạc “Mùa hè”. Gian phòng tràn ngập âm thanh <span class='wd' data-w='sáng chói'>sáng chói</span>. Tiếng vi-ô-lông <span class='wd' data-w='réo rắt'>réo rắt</span>, tiếng cla-ri-nét trong sáng, xen-lô ấm áp. Bên hàng giậu, hoa mướp vàng và những cánh ong <span class='wd' data-w='rù rì'>rù rì</span>. Thầy giáo xúc động, cúi xuống ghi điểm.",
 "Sau ve sầu, gà trống <span class='wd' data-w='đĩnh đạc'>đĩnh đạc</span> bước lên, <span class='wd' data-w='kiêu hãnh'>kiêu hãnh</span> ngẩng đầu với cái mũ đỏ chói. Gà mở đầu khúc nhạc “Bình minh” bằng <span class='wd' data-w='tiết tấu'>tiết tấu</span> nhanh, khoẻ, đầy <span class='wd' data-w='hứng khởi'>hứng khởi</span>.",
 "Đến lượt dế mèn. Dế bước ra <span class='wd' data-w='khoẻ khoắn'>khoẻ khoắn</span> và <span class='wd' data-w='trang nhã'>trang nhã</span> trong chiếc áo nâu óng. Bản nhạc “Mùa thu” gợi hình ảnh những chiếc lá khô xoay tròn, rơi rơi trong nắng. Tiếng gió <span class='wd' data-w='xào xạc'>xào xạc</span> <span class='wd' data-w='thầm thì'>thầm thì</span> với lá. Đôi mắt thầy vàng anh nhoà đi.",
 "Trong <span class='wd' data-w='tha thướt'>tà áo dài tha thướt</span>, hoạ mi trông thật <span class='wd' data-w='dịu dàng'>dịu dàng</span>, <span class='wd' data-w='uyển chuyển'>uyển chuyển</span>. Bản nhạc “Mùa xuân” vang lên réo rắt, say đắm, rồi dần chuyển sang tiết tấu <span class='wd' data-w='rạo rực'>rạo rực</span>, tưng bừng. Cuộn giấy cổ nói: chính giọng hát này là thứ Ác Long Lạc Điệu sợ nhất.",
 "Thầy vàng anh đứng dậy, vẻ <span class='wd' data-w='nghiêm trang'>nghiêm trang</span>. — “Thầy rất vui vì sự thành công của các em. Các em đã tạo dựng cho mình một phong cách <span class='wd' data-w='độc đáo'>độc đáo</span>, không ai bắt chước ai.” Thầy nói, lòng đầy <span class='wd' data-w='mãn nguyện'>mãn nguyện</span>. <i>(Theo Nguyễn Phan Hách)</i>"
];

const QUIZ = [
 {q:"Các nhân vật ve sầu, gà trống, dế mèn, hoạ mi trong câu chuyện có điểm gì giống nhau?",
  opts:["Đều biết bay cao","Đều biểu diễn một bản nhạc mang phong cách riêng của mình","Đều sợ thầy giáo","Đều là loài chim"],ans:1},
 {q:"Vì sao thầy giáo vàng anh xúc động và mãn nguyện khi xem các học trò biểu diễn?",
  opts:["Vì các trò đạt điểm cao nhất lớp","Vì mỗi học trò đã tạo được phong cách biểu diễn độc đáo của riêng mình","Vì buổi thi kết thúc sớm","Vì thời tiết hôm đó rất đẹp"],ans:1},
 {q:"Bản nhạc “Mùa thu” của dế mèn gợi hình ảnh gì?",
  opts:["Hoa phượng đỏ rực","Mặt trời rực rỡ","Lá khô xoay tròn, rơi trong nắng","Giọt mưa xuân rơi trên má"],ans:2},
 {q:"Tác giả muốn nói với chúng ta điều gì qua câu chuyện “Thi nhạc”?",
  opts:["Nhiều loài vật có tiếng kêu, tiếng hót rất hay","Thế giới của các loài vật muôn màu, muôn vẻ","Mỗi người hãy tạo cho mình một nét đẹp riêng","Muốn hát hay, đàn giỏi phải tập luyện chăm chỉ"],ans:2}
];

const DICT = [
 {s:"Dế bước ra khoẻ khoắn."},
 {s:"Chiếc áo nâu rất trang nhã."},
 {s:"Hoạ mi thật dịu dàng."},
 {s:"Điệu múa uyển chuyển."},
 {s:"Thầy rất mãn nguyện."}
];

const HUNT = [
 {tokens:["Sau","ve sầu",",","gà trống","đĩnh đạc","bước lên",",","kiêu hãnh","ngẩng","đầu","với","cái","mũ","đỏ chói","."],
  nouns:["ve sầu","gà trống","đầu","mũ"]},
 {tokens:["Dế","bước ra","khoẻ khoắn","và","trang nhã","trong","chiếc","áo","nâu óng","."],
  nouns:["Dế","áo"]},
 {tokens:["Trong","tà áo dài","tha thướt",",","hoạ mi","trông","thật","dịu dàng",",","uyển chuyển","."],
  nouns:["tà áo dài","hoạ mi"]}
];

const MAP_STATIONS = [
 {id:1,ic:"🐛",name:"Cổng Yêu Tinh Chữ",sub:"Bắt lỗi nhanh"},
 {id:2,ic:"📜",name:"Cuộn Giấy Cổ",sub:"Đọc truyện Thi nhạc"},
 {id:3,ic:"🌉",name:"Cầu Thử Thách",sub:"Trả lời nhanh"},
 {id:4,ic:"🕳️",name:"Hang Yêu Tinh Chính Tả",sub:"Chính tả trọng tâm"},
 {id:5,ic:"🌿",name:"Vườn Phép Thuật",sub:"Từ vựng và ghép thẻ"},
 {id:6,ic:"🐊",name:"Đầm Lầy Danh Từ",sub:"Săn danh từ"},
 {id:7,ic:"🗼",name:"Tháp Phù Thuỷ",sub:"Viết câu thần chú"}
];

/* ================= STATE ================= */
let state = {
  heroName:"", heroAvatar:0,
  gems:0, heartsMax:5, hearts:5,
  totalQ: 18,
  correctCount:0,
  completed:{},
  mistakes:[]
};

/* ================= COMPANION (Chích Bông) ================= */
const COMPANION_HINTS = {
  warmup: [
   "Đọc từng từ thật chậm, chú ý dấu thanh (sắc, huyền, hỏi, ngã, nặng) nhé!",
   "Thử so sánh với từ “hãnh diện”, cùng một kiểu dấu ngã đó!",
   "Âm cuối “khoắn” không có G đâu, khác với từ “khoắng” nước nha!",
   "Từ láy “dịu dàng”, cả hai tiếng đều giữ nguyên, không mất chữ cuối đâu!",
   "“Xào xạc” luôn đi với X, tả tiếng lá cây đó!",
   "“Mênh mông”, chữ “mông” phải có G cuối nha!"
  ],
  quiz: [
   "Đọc lại đoạn ve sầu, gà trống, dế mèn, hoạ mi biểu diễn, họ có làm giống nhau không nào?",
   "Để ý câu nói của thầy vàng anh ở cuối chuyện xem thầy vui vì điều gì.",
   "Nhớ lại bản nhạc “Mùa thu” của dế mèn tả cảnh gì vào mùa thu nhé.",
   "Thông điệp thường nằm ở lời thầy giáo nói cuối câu chuyện đó!"
  ],
  dict:"Đọc thầm câu 2 lần, để ý các từ láy và dấu thanh trước khi viết nhé!",
  hunt:"Danh từ là từ chỉ người, con vật, đồ vật, thử hỏi “ai?” hoặc “cái gì?” trước mỗi từ xem sao!"
};
const STATION_GREETINGS = {
 1:"Yêu tinh giấu lỗi chính tả trong từng câu đó! Cần thì bấm mình để xin gợi ý nhé.",
 2:"Đọc kỹ cuộn giấy cổ nào, những từ gạch vàng là từ mới, bấm vào xem nghĩa nhé!",
 3:"Trả lời đúng để qua cầu an toàn nha, đừng vội vàng quá!",
 4:"Nhìn thật kỹ câu thần chú trước khi nó biến vào bóng tối nhé!",
 5:"Thu thập phép từ vựng rồi thử ghép thẻ trí nhớ xem sao!",
 6:"Tìm từ chỉ người, con vật, đồ vật trong đầm lầy nhé!",
 7:"Viết câu thần chú thật hay để mở cửa Tháp Lạc Điệu nào!"
};
let companionTimer = null;
function sayCompanion(text){
  const modal = document.getElementById('companionModal');
  const msg = document.getElementById('companionMsg');
  if(!modal||!msg) return;
  msg.innerHTML = text;
  modal.classList.add('show');
}
function closeCompanion(){
  document.getElementById('companionModal').classList.remove('show');
}
function companionTapped(){
  sayCompanion("Chào bạn! Bấm nút 💡 “Hỏi Chích Bông” ở mỗi câu hỏi để mình mách nước nhé. Cùng nhau giải cứu công chúa Sơn Ca nào! 🎶");
}
function hintWarmup(i){ sayCompanion(WARMUP[i].note || "Đọc kỹ từng từ và chú ý dấu thanh nhé!"); }
function hintQuiz(i){ sayCompanion(COMPANION_HINTS.quiz[i] || "Đọc lại đoạn văn liên quan để tìm câu trả lời nhé!"); }
function hintDict(){ sayCompanion(COMPANION_HINTS.dict); }
function hintHunt(){ sayCompanion(COMPANION_HINTS.hunt); }
function positionMapCompanion(){
  const mapWrap = document.getElementById('mapWrap');
  const comp = document.getElementById('mapCompanion');
  const hero = document.getElementById('mapHero');
  if(!mapWrap||!comp) return;
  const doneCount = Object.keys(state.completed).length;
  let targetEl;
  if(doneCount>=7){
    targetEl = document.getElementById('castleNode');
  } else {
    const nodes = document.querySelectorAll('.map-node');
    targetEl = nodes[doneCount] || nodes[nodes.length-1];
  }
  if(!targetEl) return;
  const wrapRect = mapWrap.getBoundingClientRect();
  const elRect = targetEl.getBoundingClientRect();
  const top = elRect.top - wrapRect.top + (elRect.height/2) - 16;
  comp.style.top = top + "px";
  if(hero) hero.style.top = (top-6) + "px";
}

/* ================= NAV ================= */
function go(id){
  closeCompanion();
  document.querySelectorAll('section.panel').forEach(s=>s.classList.remove('active'));
  document.getElementById(id.startsWith? id : id).classList.add('active');
  window.scrollTo({top:0,behavior:'smooth'});
}
function goStation(n){
  go('p'+n);
  if(n===4) renderDictation();
  if(STATION_GREETINGS[n]) setTimeout(()=>sayCompanion(STATION_GREETINGS[n]), 300);
}
function tryGo(n){
  if(n===8){
    if(Object.keys(state.completed).length>=7){ go('p8'); renderBoss(); }
    return;
  }
  goStation(n);
}

/* ================= TITLE / SETUP ================= */
function startAdventure(){
  Audio1.startMusic();
  go('pSetup');
  renderAvatarGrid();
}
function renderAvatarGrid(){
  const g = document.getElementById('avatarGrid');
  g.innerHTML = AVATARS.map((a,i)=>`
    <div class="avatar-opt ${i===state.heroAvatar?'picked':''}" id="av-${i}" onclick="pickAvatar(${i})">
      <div class="em">${a.em}</div><b>${a.name}</b><span>${a.desc}</span><span>Trang bị: ${a.gear}</span>
    </div>`).join('');
}
function pickAvatar(i){
  state.heroAvatar = i;
  document.querySelectorAll('.avatar-opt').forEach((el,idx)=>el.classList.toggle('picked',idx===i));
}
function confirmCharacter(){
  const nameVal = document.getElementById('heroNameInput').value.trim();
  state.heroName = nameVal || "Chiến Binh Nhí";
  document.getElementById('hud').style.display='block';
  document.getElementById('hudAvatar').textContent = AVATARS[state.heroAvatar].em;
  document.getElementById('hudName').innerHTML = state.heroName + "<small>"+AVATARS[state.heroAvatar].name+"</small>";
  const heroGearEl = document.querySelector('#mapHero .gearic');
  if(heroGearEl) heroGearEl.textContent = AVATARS[state.heroAvatar].gear;
  renderHearts();
  renderMap();
  go('pMap');
  document.getElementById('companionWrap').classList.add('show');
  setTimeout(()=>sayCompanion("Xin chào "+state.heroName+"! Mình là Chích Bông 🐦, trợ lý của công chúa Sơn Ca. Mình sẽ đi cùng bạn suốt hành trình, cần gợi ý thì cứ bấm vào mình nhé!"), 400);
}

/* ================= HUD ================= */
function renderHearts(){
  document.getElementById('hudHearts').innerHTML =
    Array.from({length:state.heartsMax}).map((_,i)=>`<span class="heart ${i<state.hearts?'':'lost'}">❤️</span>`).join('');
  document.getElementById('hudGems').textContent = state.gems;
}
function loseHeart(){
  if(state.hearts>1) state.hearts--;
  renderHearts();
  Audio1.heartLost();
}
function updateBoss(){
  const pct = Math.max(0, Math.round(100 - (state.correctCount/state.totalQ)*100));
  document.getElementById('bossFill').style.width = pct+"%";
  document.getElementById('bossPct').textContent = pct+"%";
  return pct;
}
function awardCorrect(){
  state.gems++; state.correctCount++;
  renderHearts(); updateBoss();
  Audio1.correct();
}
function awardWrong(){
  loseHeart();
  Audio1.wrong();
}

/* ================= MAP ================= */
function renderMap(){
  const wrap = document.getElementById('mapPath');
  const doneCount = Object.keys(state.completed).length;
  wrap.innerHTML = MAP_STATIONS.map(s=>{
    const done = !!state.completed[s.id];
    const locked = s.id>1 && !state.completed[s.id-1] && !done;
    const cls = done? 'done' : (locked? 'locked' : 'current');
    const status = done? '✅' : (locked? '🔒' : '▶');
    return `<div class="map-node ${cls}" onclick="${locked? '' : 'goStation('+s.id+')'}">
      <div class="map-ic">${s.ic}</div>
      <div class="map-txt"><b>${s.name}</b><span>${s.sub}</span></div>
      <div class="status">${status}</div>
    </div>`;
  }).join('');
  const castle = document.getElementById('castleNode');
  const castleStatus = document.getElementById('castleStatus');
  if(doneCount>=7){
    castle.classList.remove('locked');
    castleStatus.textContent = "⚔️ Sẵn sàng, bấm để bước vào!";
  } else {
    castle.classList.add('locked');
    castleStatus.textContent = `🔒 Hoàn thành ${doneCount}/7 vùng đất để mở`;
  }
  setTimeout(positionMapCompanion, 60);
}
function finishStation(n){
  state.completed[n] = true;
  renderMap();
  go('pMap');
  const left = 7 - Object.keys(state.completed).length;
  setTimeout(()=>sayCompanion(left>0
    ? `Giỏi quá! Còn ${left} vùng đất nữa là tới Tháp Lạc Điệu rồi!`
    : `Tuyệt vời! Bạn đã xong cả 7 vùng đất, Tháp Lạc Điệu đang mở ra kìa! 🏰`), 350);
}

/* ================= GLOSSARY ================= */
function openGloss(word){
  const v = VOCAB.find(x=>x.w===word);
  if(!v) return;
  document.getElementById('gWord').textContent = v.w;
  document.getElementById('gMean').textContent = v.m;
  document.getElementById('gEx').textContent = "Ví dụ: " + v.ex;
  document.getElementById('gTip').innerHTML = "🔔 <span><b>Hay viết sai:</b> “"+v.wrong+"”. <b>Ghi nhớ:</b> "+v.tip+"</span>";
  document.getElementById('glossPop').classList.add('show');
}
function closeGloss(){document.getElementById('glossPop').classList.remove('show');}
function vocabTipFor(word){const v=VOCAB.find(x=>x.w===word); return v? v.tip:"";}

/* ================= 1. WARM UP ================= */
let warmupDone = 0;
function renderWarmup(){
  warmupDone = 0;
  document.getElementById('w1next').disabled = true;
  const wrap = document.getElementById('warmupWrap');
  wrap.innerHTML = WARMUP.map((item,i)=>`
    <div class="card" id="warmup-${i}">
      <div>${item.show.map((w,wi)=>`<span class="tok" style="cursor:pointer;" onclick="pickWarmup(${i},${wi})" id="wtok-${i}-${wi}">${w}</span>`).join(' ')}</div>
      <button class="hintbtn" onclick="hintWarmup(${i})">💡 Hỏi Chích Bông</button>
      <div class="qfeedback" id="wfeed-${i}"></div>
    </div>`).join('');
}
function pickWarmup(i,wi){
  const item = WARMUP[i];
  const feed = document.getElementById('wfeed-'+i);
  if(feed.classList.contains('show')) return;
  const tokEl = document.getElementById(`wtok-${i}-${wi}`);
  const correct = wi===item.wrongIdx;
  tokEl.classList.add(correct?'right':'miss');
  document.getElementById(`wtok-${i}-${item.wrongIdx}`).classList.add('right');
  feed.classList.add('show', correct?'ok':'no');
  warmupDone++;
  if(warmupDone>=WARMUP.length) document.getElementById('w1next').disabled=false;
  if(correct){
    awardCorrect();
    feed.innerHTML = `✅ Phá phép thành công! Từ sai là "<b>${item.show[item.wrongIdx]}</b>", đúng là "<b>${item.right}</b>".`;
    sayCompanion(`Chuẩn luôn! "${item.show[item.wrongIdx]}" phải viết là "<b>${item.right}</b>". ${item.note}`);
  } else {
    awardWrong();
    feed.innerHTML = `❌ Chưa đúng. Từ sai là "<b>${item.show[item.wrongIdx]}</b>", đúng là "<b>${item.right}</b>".`;
    state.mistakes.push({type:"Bắt lỗi nhanh",detail:`"${item.show[item.wrongIdx]}" nên sửa thành "${item.right}"`,tip:item.note});
    sayCompanion(`Chưa đúng rồi! Từ sai là "${item.show[item.wrongIdx]}", viết đúng là "<b>${item.right}</b>". ${item.note}`);
  }
}

/* ================= 2. STORY ================= */
function renderStory(){
  const wrap = document.getElementById('storyWrap');
  wrap.innerHTML = STORY.map(p=>`<p>${p}</p>`).join('');
  wrap.querySelectorAll('.wd').forEach(el=> el.addEventListener('click', ()=>openGloss(el.dataset.w)));
}

/* ================= 3. QUIZ ================= */
let quizDone = 0;
function renderQuiz(){
  quizDone = 0;
  document.getElementById('w3next').disabled = true;
  const wrap = document.getElementById('quizWrap');
  wrap.innerHTML = QUIZ.map((q,i)=>`
    <div class="card qcard">
      <h4>${i+1}. ${q.q}</h4>
      ${q.opts.map((o,oi)=>`<button class="opt" id="qopt-${i}-${oi}" onclick="answerQuiz(${i},${oi})">${String.fromCharCode(65+oi)}. ${o}</button>`).join('')}
      <button class="hintbtn" onclick="hintQuiz(${i})">💡 Hỏi Chích Bông</button>
      <div class="qfeedback" id="qfeed-${i}"></div>
    </div>`).join('');
}
function answerQuiz(i,oi){
  const q = QUIZ[i];
  const feed = document.getElementById('qfeed-'+i);
  if(feed.classList.contains('show')) return;
  const correct = oi===q.ans;
  document.getElementById(`qopt-${i}-${oi}`).classList.add(correct?'correct':'wrong');
  if(!correct) document.getElementById(`qopt-${i}-${q.ans}`).classList.add('correct');
  feed.classList.add('show', correct?'ok':'no');
  feed.textContent = correct? "✅ Qua cầu an toàn!" : "❌ Suýt rơi xuống vực, đáp án đúng là " + String.fromCharCode(65+q.ans) + ".";
  quizDone++;
  if(quizDone>=QUIZ.length) document.getElementById('w3next').disabled=false;
  if(correct){awardCorrect(); sayCompanion("Chính xác! " + q.opts[q.ans] + " 🎉");}
  else{
    awardWrong();
    state.mistakes.push({type:"Đọc hiểu",detail:q.q,tip:"Đáp án đúng: "+q.opts[q.ans]});
    sayCompanion("Chưa đúng rồi, đáp án đúng là: <b>" + q.opts[q.ans] + "</b>. Đọc lại đoạn liên quan nhé!");
  }
}

/* ================= 4. DICTATION ================= */
let dictIndex = 0, dictDoneCount = 0, dictIntervalId = null;
function renderDictation(){
  dictIndex = 0; dictDoneCount = 0;
  document.getElementById('w4next').disabled = true;
  const wrap = document.getElementById('dictWrap');
  wrap.innerHTML = `<div id="dictStage-0"></div><div style="text-align:center;margin-top:10px;"><button class="btn" id="dictNextBtn" onclick="nextDict()" style="display:none;">Câu tiếp theo ▶</button></div>`;
  loadDictSentence();
}
function loadDictSentence(){
  const holder = document.getElementById('dictStage-0');
  document.getElementById('dictNextBtn').style.display = 'none';
  if(dictIndex>=DICT.length){
    holder.innerHTML = `<p style="text-align:center;color:var(--teal);font-weight:700;">🎉 Ánh sáng đã xua tan bóng tối trong hang!</p>`;
    document.getElementById('w4next').disabled = false;
    return;
  }
  const item = DICT[dictIndex];
  holder.innerHTML = `
    <p style="text-align:center;color:var(--ink-soft);font-size:.85rem;">Câu thần chú ${dictIndex+1}/${DICT.length}, nhìn kỹ, chữ sẽ ẩn vào bóng tối sau vài giây</p>
    <div class="dict-sentence" id="dsent">${item.s}</div>
    <div class="countdown" id="dcount">6</div>
    <div style="text-align:center;"><button class="hintbtn" onclick="hintDict()">💡 Hỏi Chích Bông</button></div>
  `;
  let t = 6;
  if(dictIntervalId) clearInterval(dictIntervalId);
  dictIntervalId = setInterval(()=>{
    t--;
    document.getElementById('dcount').textContent = t;
    if(t<=0){
      clearInterval(dictIntervalId);
      dictIntervalId = null;
      document.getElementById('dsent').style.visibility='hidden';
      document.getElementById('dcount').style.display='none';
      holder.insertAdjacentHTML('beforeend', `
        <textarea id="dinput" placeholder="Gõ lại câu thần chú em vừa đọc..."></textarea>
        <div style="text-align:center;margin-top:10px;"><button class="btn teal" onclick="checkDict(${dictIndex})">Kiểm tra phép ✓</button></div>
        <div id="dresult"></div>
      `);
    }
  },1000);
}
function normWords(s){return s.trim().split(/\s+/);}
function checkDict(i){
  const item = DICT[i];
  const typed = document.getElementById('dinput').value;
  const correctWords = normWords(item.s);
  const typedWords = normWords(typed);
  let html = `<div class="diff-line">`;
  let wrongList = [];
  correctWords.forEach((w,idx)=>{
    const tw = typedWords[idx] || "";
    const clean=(x)=>x.toLowerCase().replace(/[.,!?…]/g,'');
    if(clean(tw)===clean(w)){ html += `<span class="ok">${w}</span> `; }
    else { html += `<span class="bad">${w}</span> `; wrongList.push(w.replace(/[.,!?…]/g,'')); }
  });
  html += `</div>`;
  dictDoneCount++;
  if(wrongList.length===0){
    awardCorrect();
    html += `<p style="color:var(--teal);font-weight:700;margin-top:8px;">✅ Tuyệt vời, phép sáng đã hoàn thành!</p>`;
    sayCompanion("Viết đúng hết luôn! Bóng tối trong hang tan biến rồi ✨");
  } else {
    awardWrong();
    html += `<div class="memo">`;
    let firstTip = "";
    wrongList.forEach(w=>{
      const v = VOCAB.find(x=> w.toLowerCase().includes(x.w.split(' ').pop().toLowerCase()) || x.w.toLowerCase().includes(w.toLowerCase()));
      const tipTxt = v? v.tip : "Xem lại cách viết đúng của từ này và chép lại 2 lần cho nhớ.";
      if(!firstTip) firstTip = `"${w}", ${tipTxt}`;
      html += `<b>🔔 Ghi nhớ, "${w}"</b>${tipTxt}<br>`;
      state.mistakes.push({type:"Chính tả",detail:`Viết đúng: "${w}"`,tip: tipTxt});
    });
    html += `</div>`;
    sayCompanion("Có vài chữ viết chưa đúng nè: " + firstTip);
  }
  document.getElementById('dresult').innerHTML = html;
  document.getElementById('dictNextBtn').style.display = 'inline-block';
}
function nextDict(){dictIndex++; loadDictSentence();}

/* ================= 5. VOCAB ================= */
function renderVocabGrid(){
  const grid = document.getElementById('vocabGrid');
  grid.innerHTML = VOCAB.map((v)=>`
    <div class="flip-card" onclick="this.classList.toggle('open')">
      <div class="flip-inner">
        <div class="flip-face flip-front">${v.w}</div>
        <div class="flip-face flip-back"><b>${v.w}</b>${v.m}</div>
      </div>
    </div>`).join('');
}
let matchState = {cards:[], flipped:[], lock:false};
function newMatchGame(){
  const picks = [...VOCAB].sort(()=>Math.random()-0.5).slice(0,6);
  let cards = [];
  picks.forEach((v,i)=>{ cards.push({id:'w'+i,pairId:i,text:v.w}); cards.push({id:'m'+i,pairId:i,text:v.m}); });
  cards.sort(()=>Math.random()-0.5);
  matchState = {cards, flipped:[], lock:false};
  renderMatch();
}
function renderMatch(){
  const wrap = document.getElementById('matchWrap');
  wrap.innerHTML = matchState.cards.map(c=>`<div class="mcard" id="card-${c.id}" onclick="flipCard('${c.id}')">?</div>`).join('');
  document.getElementById('matchStatus').textContent = `Đã khoá: 0 / ${matchState.cards.length/2} phép`;
}
function flipCard(id){
  if(matchState.lock) return;
  const el = document.getElementById('card-'+id);
  if(el.classList.contains('flipped')||el.classList.contains('matched')) return;
  const card = matchState.cards.find(c=>c.id===id);
  el.classList.add('flipped'); el.textContent = card.text;
  matchState.flipped.push(card);
  if(matchState.flipped.length===2){
    matchState.lock = true;
    const [a,b] = matchState.flipped;
    setTimeout(()=>{
      if(a.pairId===b.pairId && a.id!==b.id){
        document.getElementById('card-'+a.id).classList.add('matched');
        document.getElementById('card-'+b.id).classList.add('matched');
        Audio1.correct(); state.gems++; renderHearts();
        const matched = matchState.cards.filter(c=>document.getElementById('card-'+c.id).classList.contains('matched')).length/2;
        document.getElementById('matchStatus').textContent = `Đã khoá: ${matched} / ${matchState.cards.length/2} phép` + (matched===matchState.cards.length/2? " 🎉 Xong ván này!":"");
      } else {
        Audio1.wrong();
        [a,b].forEach(c=>{
          const e = document.getElementById('card-'+c.id);
          e.classList.remove('flipped'); e.classList.add('shake'); e.textContent='?';
          setTimeout(()=>e.classList.remove('shake'),350);
        });
      }
      matchState.flipped = []; matchState.lock = false;
    },700);
  }
}

/* ================= 6. NOUN HUNT ================= */
let huntPicks = {}; let huntDone=0;
function renderHunt(){
  huntPicks = {}; huntDone = 0;
  document.getElementById('w6next').disabled = true;
  const wrap = document.getElementById('huntWrap');
  wrap.innerHTML = HUNT.map((h,hi)=>`
    <div class="card">
      <div class="hunt-sentence" id="hunt-${hi}">
        ${h.tokens.map((t,ti)=> /^[.,!?…]$/.test(t) ? `<span class="tok punct">${t}</span>` : `<span class="tok" onclick="pickNoun(${hi},${ti})" id="htok-${hi}-${ti}">${t}</span>`).join(' ')}
      </div>
      <button class="hintbtn" onclick="hintHunt()">💡 Hỏi Chích Bông</button><br>
      <button class="btn teal" onclick="checkHunt(${hi})" id="hcheck-${hi}" style="margin-top:8px;">Kiểm tra ✓</button>
      <div class="qfeedback" id="hfeed-${hi}"></div>
    </div>`).join('');
}
function pickNoun(hi,ti){
  const key = hi+'-'+ti;
  const el = document.getElementById(`htok-${hi}-${ti}`);
  if(el.classList.contains('right')||el.classList.contains('miss')) return;
  huntPicks[key] = !huntPicks[key];
  el.classList.toggle('picked');
}
function checkHunt(hi){
  const h = HUNT[hi];
  const feed = document.getElementById('hfeed-'+hi);
  if(feed.classList.contains('show')) return;
  let correctCount = 0, wrongPick = 0;
  h.tokens.forEach((t,ti)=>{
    if(/^[.,!?…]$/.test(t)) return;
    const key = hi+'-'+ti;
    const el = document.getElementById(`htok-${hi}-${ti}`);
    const isNoun = h.nouns.includes(t);
    const picked = !!huntPicks[key];
    if(isNoun){ el.classList.add(picked?'right':'miss'); if(picked) correctCount++; }
    else if(picked){ el.classList.add('miss'); wrongPick++; }
  });
  const perfect = correctCount===h.nouns.length && wrongPick===0;
  huntDone++;
  if(huntDone>=HUNT.length) document.getElementById('w6next').disabled=false;
  if(perfect){
    awardCorrect();
    feed.innerHTML = "✅ Đầm lầy sạch bóng! Đây đều là danh từ, từ chỉ người, con vật, đồ vật.";
    sayCompanion("Chuẩn không cần chỉnh! " + h.nouns.join(', ') + " đều là danh từ 🎯");
  } else {
    awardWrong();
    feed.innerHTML = `❌ Danh từ đúng trong câu này là: <b>${h.nouns.join(', ')}</b>. Danh từ là từ chỉ người, con vật, đồ vật, sự việc.`;
    state.mistakes.push({type:"Luyện từ và câu",detail:"Câu "+(hi+1)+", danh từ đúng: "+h.nouns.join(', '),tip:"Danh từ là từ chỉ người, con vật, đồ vật, hiện tượng, có thể đặt sau “cái”, “con”, “sự”."});
    sayCompanion("Chưa trúng hết rồi! Danh từ đúng là: <b>" + h.nouns.join(', ') + "</b>.");
  }
  feed.classList.add('show', perfect?'ok':'no');
  document.getElementById('hcheck-'+hi).disabled = true;
}

/* ================= 7. MINI WRITE ================= */
document.addEventListener('input', e=>{
  if(e.target.id==='miniWrite'){
    const words = e.target.value.trim().split(/\s+/).filter(Boolean).length;
    document.getElementById('wcount').textContent = words + " từ";
    document.getElementById('w7next').disabled = words < 8;
  }
});

/* ================= 8. BOSS / ENDING ================= */
function renderBoss(){
  const pct = updateBoss();
  const hero = document.getElementById('bossHero');
  const fightCard = document.getElementById('finalFightCard');
  if(pct<=0){
    Audio1.victory();
    hero.innerHTML = `
      <div class="victory-scene">
        <div class="em">👑</div>
        <h3>Chiến thắng! Ác Long Lạc Điệu đã bị đánh bại!</h3>
        <p>${state.heroName} đã giải cứu công chúa Sơn Ca. Khu rừng Thi Nhạc lại vang lên tiếng hát trong trẻo!</p>
      </div>`;
    fightCard.style.display = 'none';
  } else {
    hero.innerHTML = `
      <div class="em">🐉</div>
      <h3>Ác Long vẫn còn ${pct}% sức mạnh!</h3>
      <p>Trả lời đòn phép cuối bên dưới để hạ gục hoàn toàn và giải cứu công chúa Sơn Ca.</p>
    `;
    fightCard.style.display = 'block';
    renderFinalFight();
  }
  renderNotebook();
}
function renderFinalFight(){
  const pool = state.mistakes.length? state.mistakes : VOCAB.map(v=>({type:"Từ vựng",detail:v.w,tip:v.tip}));
  const picks = [...pool].sort(()=>Math.random()-0.5).slice(0,4);
  const wrap = document.getElementById('finalFightWrap');
  wrap.innerHTML = picks.map((m,i)=>`
    <div class="card">
      <p style="margin:0 0 8px;font-size:.9rem;"><b>[${m.type}]</b> ${m.detail}</p>
      <p style="margin:0 0 8px;color:var(--ink-soft);font-size:.85rem;">🔔 ${m.tip}</p>
      <button class="btn teal" onclick="finalHit(this)">⚔️ Đã hiểu, tung đòn phép!</button>
    </div>`).join('');
}
function finalHit(btn){
  btn.disabled = true; btn.textContent = "✅ Đòn phép đã trúng!";
  state.correctCount = Math.min(state.totalQ, state.correctCount+1);
  const pct = updateBoss();
  Audio1.correct();
  if(pct<=0){ setTimeout(renderBoss, 500); }
}
function renderNotebook(){
  const nb = document.getElementById('notebook');
  if(state.mistakes.length===0){
    nb.innerHTML = `<li class="empty-note">🎉 Không có lỗi nào được ghi lại, quá giỏi!</li>`;
  } else {
    nb.innerHTML = state.mistakes.map(m=>`<li><b>[${m.type}]</b> ${m.detail}<br><span style="color:var(--ink-soft);">🔔 ${m.tip}</span></li>`).join('');
  }
}

/* ================= RESTART ================= */
function restartAll(){
  state = {heroName:state.heroName, heroAvatar:state.heroAvatar, gems:0, heartsMax:5, hearts:5, totalQ:18, correctCount:0, completed:{}, mistakes:[]};
  renderHearts(); updateBoss();
  renderWarmup(); renderStory(); renderQuiz();
  renderVocabGrid(); newMatchGame(); renderHunt();
  document.getElementById('dictWrap').innerHTML = '';
  document.getElementById('miniWrite').value=''; document.getElementById('wcount').textContent='0 từ';
  document.getElementById('w7next').disabled = true;
  renderMap();
  go('pMap');
}

/* ================= INIT ================= */
window.addEventListener('resize', ()=>positionMapCompanion());
renderWarmup();
renderStory();
renderQuiz();
renderVocabGrid();
newMatchGame();
renderHunt();
</script>
</body>
</html>
