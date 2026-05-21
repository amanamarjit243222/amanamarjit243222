<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Aman Amarjit — GitHub Profile</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&display=swap" rel="stylesheet"/>
<style>
/* ─── RESET & BASE ─────────────────────────────────────────────────── */
*{margin:0;padding:0;box-sizing:border-box}
:root{
  --cyan:#00d4e8;
  --cyan2:#67e8f9;
  --cyan3:#a5f3fc;
  --dark:#060f1c;
  --mid:#001824;
  --deep:#000000;
  --card:#0a1628;
  --border:rgba(0,212,232,.25);
  --border2:rgba(0,212,232,.5);
  --text:#e0f7ff;
  --muted:#3d6e7e;
  --glow:rgba(0,212,232,.6);
}
html{scroll-behavior:smooth}
body{
  background:var(--deep);
  color:var(--text);
  font-family:'JetBrains Mono',monospace;
  overflow-x:hidden;
  line-height:1.6;
}

/* ─── SCROLLBAR ────────────────────────────────────────────────────── */
::-webkit-scrollbar{width:6px}
::-webkit-scrollbar-track{background:#000}
::-webkit-scrollbar-thumb{background:var(--cyan);border-radius:3px}

/* ─── SELECTION ────────────────────────────────────────────────────── */
::selection{background:rgba(0,212,232,.3);color:#fff}

/* ─── GLOBAL GRID BG ───────────────────────────────────────────────── */
body::before{
  content:'';
  position:fixed;inset:0;z-index:0;pointer-events:none;
  background-image:
    linear-gradient(rgba(0,212,232,.04) 1px,transparent 1px),
    linear-gradient(90deg,rgba(0,212,232,.04) 1px,transparent 1px);
  background-size:48px 48px;
  animation:gridDrift 30s linear infinite;
}
@keyframes gridDrift{0%{background-position:0 0}100%{background-position:48px 48px}}

/* ─── WRAPPER ──────────────────────────────────────────────────────── */
.page{position:relative;z-index:1;max-width:960px;margin:0 auto;padding:0 24px 80px}

/* ═══════════════════════════════════════════════════════════════════ */
/* HERO                                                               */
/* ═══════════════════════════════════════════════════════════════════ */
.hero{
  position:relative;overflow:hidden;
  background:linear-gradient(135deg,#000 0%,#001824 55%,#004d6b 100%);
  border:1px solid var(--border);
  border-radius:12px;
  margin:32px 0;
  min-height:340px;
}
.hero-scan{
  position:absolute;inset:0;pointer-events:none;
  background:repeating-linear-gradient(0deg,transparent,transparent 3px,rgba(0,212,232,.025) 3px,rgba(0,212,232,.025) 4px);
  animation:scanSlide 10s linear infinite;
}
@keyframes scanSlide{0%{transform:translateY(0)}100%{transform:translateY(48px)}}

.hero-flare{
  position:absolute;top:-80px;right:-80px;
  width:320px;height:320px;border-radius:50%;
  background:radial-gradient(circle,rgba(0,212,232,.15) 0%,transparent 65%);
  animation:flarePulse 5s ease-in-out infinite;
}
@keyframes flarePulse{0%,100%{opacity:.5;transform:scale(1)}50%{opacity:1;transform:scale(1.2)}}

.hero-flare2{
  position:absolute;bottom:-60px;left:-60px;
  width:220px;height:220px;border-radius:50%;
  background:radial-gradient(circle,rgba(0,77,107,.4) 0%,transparent 65%);
  animation:flarePulse 7s 1s ease-in-out infinite;
}

/* corners */
.corner{position:absolute;width:14px;height:14px}
.corner::before,.corner::after{content:'';position:absolute;background:var(--cyan)}
.corner.tl{top:14px;left:14px}
.corner.tl::before{top:0;left:0;width:2px;height:14px}
.corner.tl::after{top:0;left:0;width:14px;height:2px}
.corner.tr{top:14px;right:14px}
.corner.tr::before{top:0;right:0;width:2px;height:14px}
.corner.tr::after{top:0;right:0;width:14px;height:2px}
.corner.bl{bottom:14px;left:14px}
.corner.bl::before{bottom:0;left:0;width:2px;height:14px}
.corner.bl::after{bottom:0;left:0;width:14px;height:2px}
.corner.br{bottom:14px;right:14px}
.corner.br::before{bottom:0;right:0;width:2px;height:14px}
.corner.br::after{bottom:0;right:0;width:14px;height:2px}

/* 3D CUBE */
.cube-wrap{
  position:absolute;right:60px;top:50%;transform:translateY(-50%);
  width:140px;height:140px;perspective:400px;
}
.cube{
  width:100%;height:100%;
  transform-style:preserve-3d;
  animation:spinCube 10s linear infinite;
}
@keyframes spinCube{0%{transform:rotateX(22deg) rotateY(0)}100%{transform:rotateX(22deg) rotateY(360deg)}}

.face{
  position:absolute;width:140px;height:140px;
  border:1.5px solid rgba(0,212,232,.65);
  background:rgba(0,24,36,.5);
  display:flex;align-items:center;justify-content:center;
  font-size:13px;font-weight:700;letter-spacing:.12em;
  color:rgba(103,232,249,.75);
  backdrop-filter:blur(2px);
}
.face span{position:relative;z-index:1}
.face::before{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(0,212,232,.08),transparent);
}
.face.front {transform:translateZ(70px)}
.face.back  {transform:rotateY(180deg) translateZ(70px)}
.face.left  {transform:rotateY(-90deg) translateZ(70px)}
.face.right {transform:rotateY(90deg)  translateZ(70px)}
.face.top   {transform:rotateX(90deg)  translateZ(70px)}
.face.bottom{transform:rotateX(-90deg) translateZ(70px)}

.cube-glow{
  position:absolute;inset:-20px;
  background:radial-gradient(circle at center,rgba(0,212,232,.12),transparent 70%);
  animation:cubeGlow 3s ease-in-out infinite;
}
@keyframes cubeGlow{0%,100%{opacity:.6}50%{opacity:1}}

/* HERO CONTENT */
.hero-content{
  position:relative;z-index:2;
  padding:44px 240px 44px 44px;
  display:flex;flex-direction:column;gap:16px;
  min-height:340px;justify-content:center;
}
.hero-name{
  font-size:46px;font-weight:700;letter-spacing:.08em;
  color:#fff;line-height:1;
  text-shadow:0 0 40px rgba(0,212,232,.5),0 0 80px rgba(0,212,232,.15);
  animation:slideIn .8s ease both;
}
@keyframes slideIn{from{opacity:0;transform:translateX(-40px)}to{opacity:1;transform:none}}

.hero-roles{
  display:flex;align-items:center;gap:10px;flex-wrap:wrap;
  font-size:12px;letter-spacing:.12em;color:var(--cyan2);
  animation:fadeUp .8s .15s ease both;
}
.hero-roles .sep{color:rgba(103,232,249,.35)}

.typewriter-row{
  height:20px;overflow:hidden;
  animation:fadeUp .8s .3s ease both;
}
.typewriter{
  font-size:12px;color:var(--cyan);letter-spacing:.06em;
  white-space:nowrap;overflow:hidden;width:0;
  border-right:2px solid var(--cyan);
  animation:typeLine 3.5s steps(50,end) .8s forwards, blink .75s step-end infinite .8s;
}
@keyframes typeLine{to{width:100%}}
@keyframes blink{0%,100%{border-color:var(--cyan)}50%{border-color:transparent}}

.hero-tags{
  display:flex;gap:8px;flex-wrap:wrap;
  animation:fadeUp .8s .45s ease both;
}
.tag{
  font-size:10px;letter-spacing:.1em;padding:4px 12px;
  border:1px solid rgba(0,212,232,.4);
  border-radius:2px;color:var(--cyan2);
  background:rgba(0,30,50,.6);
  position:relative;overflow:hidden;
}
.tag::after{
  content:'';position:absolute;inset:0;
  background:linear-gradient(90deg,transparent,rgba(0,212,232,.12),transparent);
  transform:translateX(-100%);
  animation:shimmer 3.5s ease infinite;
}
.tag:nth-child(2)::after{animation-delay:.6s}
.tag:nth-child(3)::after{animation-delay:1.2s}
.tag:nth-child(4)::after{animation-delay:1.8s}
@keyframes shimmer{0%{transform:translateX(-100%)}60%,100%{transform:translateX(200%)}}

.hero-stats{
  display:flex;gap:12px;flex-wrap:wrap;
  animation:fadeUp .8s .6s ease both;
}
.hstat{
  display:flex;align-items:center;gap:10px;
  background:rgba(0,20,36,.7);border:1px solid var(--border);
  padding:6px 16px;border-radius:3px;
}
.hstat-label{font-size:10px;letter-spacing:.1em;color:var(--muted)}
.hstat-val{font-size:14px;font-weight:700;color:#fff}

.hero-status{
  display:flex;align-items:center;gap:8px;
  font-size:10px;letter-spacing:.08em;color:rgba(103,232,249,.6);
  animation:fadeUp .8s .75s ease both;
}
.live-dot{
  width:8px;height:8px;border-radius:50%;
  background:var(--cyan);box-shadow:0 0 8px var(--cyan);
  animation:livePulse 1.5s ease-in-out infinite;
}
@keyframes livePulse{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.4;transform:scale(.6)}}

@keyframes fadeUp{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:none}}

/* ═══════════════════════════════════════════════════════════════════ */
/* SECTION COMMON                                                     */
/* ═══════════════════════════════════════════════════════════════════ */
.section{margin:32px 0}
.section-title{
  display:flex;align-items:center;gap:12px;
  font-size:13px;font-weight:700;letter-spacing:.14em;
  color:var(--cyan2);margin-bottom:20px;
  text-transform:uppercase;
}
.section-title::before{
  content:'';display:block;width:3px;height:18px;
  background:var(--cyan);border-radius:2px;
  box-shadow:0 0 8px var(--cyan);
}
.section-title::after{
  content:'';flex:1;height:1px;
  background:linear-gradient(90deg,var(--border),transparent);
}

/* ═══════════════════════════════════════════════════════════════════ */
/* WHOAMI TERMINAL                                                    */
/* ═══════════════════════════════════════════════════════════════════ */
.terminal{
  background:#050e1a;
  border:1px solid var(--border);
  border-radius:10px;
  overflow:hidden;
  box-shadow:0 0 40px rgba(0,212,232,.06);
}
.term-bar{
  background:#0a1628;
  border-bottom:1px solid var(--border);
  padding:10px 16px;
  display:flex;align-items:center;gap:8px;
}
.term-dot{width:12px;height:12px;border-radius:50%}
.term-dot.r{background:#ff5f57}
.term-dot.y{background:#ffbd2e}
.term-dot.g{background:#28ca41}
.term-title{margin-left:auto;font-size:11px;color:var(--muted);letter-spacing:.06em;margin-right:auto}

.term-body{padding:24px 28px;font-size:12px;line-height:2}
.term-prompt{color:var(--cyan);font-weight:700}
.term-cmd{color:var(--cyan2)}
.term-key{color:var(--muted)}
.term-val{color:var(--text)}
.term-val.hi{color:var(--cyan2)}
.term-val.acc{color:var(--cyan)}
.term-block{margin:12px 0 16px 0}
.term-row{display:flex;gap:0}
.term-k{min-width:120px;color:var(--muted)}
.term-v{color:var(--text)}
.term-v .bracket{color:rgba(103,232,249,.4)}
.term-v .str{color:var(--cyan2)}
.term-cursor{
  display:inline-block;width:8px;height:14px;
  background:var(--cyan);margin-left:2px;vertical-align:middle;
  animation:cursorBlink 1s step-end infinite;
}
@keyframes cursorBlink{0%,100%{opacity:1}50%{opacity:0}}
.term-highlight{
  display:inline-block;padding:1px 6px;
  background:rgba(0,212,232,.12);border-radius:2px;
  color:var(--cyan);font-weight:700;
}

/* ═══════════════════════════════════════════════════════════════════ */
/* PROJECTS TABLE                                                     */
/* ═══════════════════════════════════════════════════════════════════ */
.projects-table{width:100%;border-collapse:collapse;font-size:12px}
.projects-table th{
  text-align:left;padding:10px 14px;
  font-size:10px;letter-spacing:.12em;color:var(--muted);
  border-bottom:1px solid var(--border);
  text-transform:uppercase;
}
.projects-table td{
  padding:14px 14px;
  border-bottom:1px solid rgba(0,212,232,.08);
  vertical-align:top;
}
.projects-table tr{transition:background .2s}
.projects-table tr:hover td{background:rgba(0,212,232,.04)}
.proj-num{color:var(--muted);font-size:10px;letter-spacing:.06em}
.proj-name{font-weight:700;color:var(--cyan2);letter-spacing:.04em;margin-bottom:4px}
.proj-desc{color:rgba(224,247,255,.55);font-size:11px;line-height:1.6}
.proj-stack{display:flex;flex-wrap:wrap;gap:4px;margin-top:8px}
.pill{
  font-size:9px;padding:2px 8px;letter-spacing:.08em;
  border:1px solid var(--border);border-radius:2px;
  color:rgba(103,232,249,.6);background:rgba(0,30,50,.5);
}
.proj-links{display:flex;gap:8px;white-space:nowrap}
.proj-links a{
  font-size:10px;color:var(--cyan);text-decoration:none;
  border:1px solid var(--border);padding:3px 10px;border-radius:2px;
  transition:all .2s;letter-spacing:.06em;
}
.proj-links a:hover{background:rgba(0,212,232,.1);border-color:var(--cyan2)}

/* table wrapper */
.table-wrap{
  background:#050e1a;
  border:1px solid var(--border);
  border-radius:10px;overflow:hidden;
}

/* ═══════════════════════════════════════════════════════════════════ */
/* TECH STACK                                                         */
/* ═══════════════════════════════════════════════════════════════════ */
.stack-grid{display:grid;gap:16px}
.stack-category{
  background:#050e1a;border:1px solid var(--border);
  border-radius:8px;padding:18px 20px;
}
.stack-cat-title{
  font-size:10px;letter-spacing:.14em;color:var(--muted);
  text-transform:uppercase;margin-bottom:12px;
}
.stack-items{display:flex;flex-wrap:wrap;gap:8px}
.stack-item{
  font-size:11px;letter-spacing:.06em;
  border:1px solid var(--border);border-radius:3px;
  padding:5px 12px;color:var(--cyan2);
  background:rgba(0,30,50,.5);
  position:relative;overflow:hidden;
  transition:all .25s;cursor:default;
}
.stack-item:hover{
  border-color:var(--cyan);
  background:rgba(0,212,232,.1);
  color:#fff;
  box-shadow:0 0 12px rgba(0,212,232,.2);
  transform:translateY(-2px);
}
.stack-item .dot-i{
  display:inline-block;width:5px;height:5px;border-radius:50%;
  background:var(--cyan);margin-right:6px;vertical-align:middle;
  opacity:.6;
}

/* ═══════════════════════════════════════════════════════════════════ */
/* STATS CARDS                                                        */
/* ═══════════════════════════════════════════════════════════════════ */
.stats-row{display:grid;grid-template-columns:1fr 1fr;gap:16px}
.stat-card{
  background:#050e1a;border:1px solid var(--border);
  border-radius:8px;padding:20px;
  position:relative;overflow:hidden;
}
.stat-card::before{
  content:'';position:absolute;top:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,transparent,var(--cyan),transparent);
  animation:scanTop 4s ease-in-out infinite;
}
@keyframes scanTop{0%,100%{opacity:0}50%{opacity:1}}
.stat-card-title{font-size:10px;letter-spacing:.12em;color:var(--muted);margin-bottom:12px;text-transform:uppercase}
.stat-img-placeholder{
  width:100%;background:#0a1628;border:1px solid var(--border);
  border-radius:4px;height:140px;
  display:flex;align-items:center;justify-content:center;
  font-size:10px;color:var(--muted);letter-spacing:.08em;
  flex-direction:column;gap:8px;
}
.stat-img-placeholder .icon{font-size:28px;opacity:.3}

/* ═══════════════════════════════════════════════════════════════════ */
/* MANIFESTO                                                          */
/* ═══════════════════════════════════════════════════════════════════ */
.manifesto{
  background:#050e1a;border:1px solid var(--border);
  border-radius:10px;padding:32px 36px;
  position:relative;overflow:hidden;
}
.manifesto::before{
  content:'';position:absolute;inset:0;
  background:
    radial-gradient(ellipse at 0% 100%,rgba(0,212,232,.06),transparent 50%),
    radial-gradient(ellipse at 100% 0%,rgba(0,77,107,.1),transparent 50%);
}
.manifesto-header{
  font-size:11px;letter-spacing:.2em;color:var(--muted);
  text-align:center;margin-bottom:24px;text-transform:uppercase;
}
.manifesto-items{list-style:none;display:flex;flex-direction:column;gap:14px;position:relative;z-index:1}
.manifesto-item{
  display:flex;align-items:baseline;gap:14px;
  font-size:12px;line-height:1.7;
  padding-bottom:14px;
  border-bottom:1px solid rgba(0,212,232,.07);
}
.manifesto-item:last-child{border-bottom:none;padding-bottom:0}
.man-num{
  font-size:10px;color:var(--cyan);font-weight:700;
  letter-spacing:.1em;min-width:24px;
}
.man-text{color:rgba(224,247,255,.75)}
.man-accent{color:var(--cyan2);font-weight:700}
.manifesto-sig{
  text-align:right;font-size:10px;color:var(--muted);
  margin-top:20px;letter-spacing:.08em;
}

/* ═══════════════════════════════════════════════════════════════════ */
/* CONNECT                                                            */
/* ═══════════════════════════════════════════════════════════════════ */
.connect-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:12px}
.connect-card{
  background:#050e1a;border:1px solid var(--border);
  border-radius:8px;padding:16px;
  text-decoration:none;color:var(--text);
  display:flex;flex-direction:column;align-items:center;gap:10px;
  transition:all .25s;position:relative;overflow:hidden;
}
.connect-card::after{
  content:'';position:absolute;bottom:0;left:0;right:0;height:2px;
  background:var(--cyan);transform:scaleX(0);transform-origin:left;
  transition:transform .3s ease;
}
.connect-card:hover{
  border-color:var(--cyan2);
  background:rgba(0,212,232,.06);
  transform:translateY(-4px);
  box-shadow:0 8px 24px rgba(0,212,232,.12);
}
.connect-card:hover::after{transform:scaleX(1)}
.connect-icon{font-size:22px;opacity:.7}
.connect-label{font-size:10px;letter-spacing:.1em;color:var(--muted);text-transform:uppercase}
.connect-val{font-size:11px;color:var(--cyan2);text-align:center}

/* ═══════════════════════════════════════════════════════════════════ */
/* FOOTER                                                             */
/* ═══════════════════════════════════════════════════════════════════ */
.footer{
  text-align:center;padding:32px 0 0;
  border-top:1px solid var(--border);
  font-size:10px;letter-spacing:.12em;color:var(--muted);
}
.footer span{color:var(--cyan)}

/* ─── RESPONSIVE ───────────────────────────────────────────────────── */
@media(max-width:680px){
  .cube-wrap{display:none}
  .hero-content{padding:32px 24px}
  .hero-name{font-size:30px}
  .stats-row{grid-template-columns:1fr}
  .connect-grid{grid-template-columns:repeat(2,1fr)}
}

/* ─── ENTRANCE ANIMATIONS ──────────────────────────────────────────── */
.reveal{
  opacity:0;transform:translateY(24px);
  transition:opacity .6s ease,transform .6s ease;
}
.reveal.visible{opacity:1;transform:none}

/* ─── NOW SECTION ──────────────────────────────────────────────────── */
.now-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
.now-item{
  background:#050e1a;border:1px solid var(--border);
  border-radius:8px;padding:16px 18px;
  display:flex;align-items:flex-start;gap:12px;
  font-size:12px;
}
.now-arrow{color:var(--cyan);font-size:14px;margin-top:2px}
.now-text{color:rgba(224,247,255,.65);line-height:1.6}

/* ─── HIGHLIGHTS ───────────────────────────────────────────────────── */
.highlights{display:flex;flex-direction:column;gap:10px}
.hl{
  background:#050e1a;border:1px solid var(--border);
  border-radius:8px;padding:14px 18px;
  display:flex;align-items:baseline;gap:12px;
  font-size:12px;
  transition:border-color .2s;
}
.hl:hover{border-color:rgba(0,212,232,.5)}
.hl-bullet{color:var(--cyan);font-size:16px;line-height:1}
.hl-text{color:rgba(224,247,255,.7);line-height:1.6}
.hl-text strong{color:var(--cyan2)}
</style>
</head>
<body>

<div class="page">

<!-- ═══════════════════════════════════════════════════════════════════ -->
<!-- HERO                                                               -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<div class="hero">
  <div class="hero-scan"></div>
  <div class="hero-flare"></div>
  <div class="hero-flare2"></div>
  <div class="corner tl"></div>
  <div class="corner tr"></div>
  <div class="corner bl"></div>
  <div class="corner br"></div>

  <!-- 3D CUBE -->
  <div class="cube-wrap">
    <div class="cube-glow"></div>
    <div class="cube">
      <div class="face front"><span>ML</span></div>
      <div class="face back"><span>NLP</span></div>
      <div class="face left"><span>SEC</span></div>
      <div class="face right"><span>AI</span></div>
      <div class="face top"><span>SYS</span></div>
      <div class="face bottom"><span>RTA</span></div>
    </div>
  </div>

  <div class="hero-content">
    <div class="hero-name">AMAN AMARJIT</div>

    <div class="hero-roles">
      <span>AI Engineer</span>
      <span class="sep">·</span>
      <span>Systems Builder</span>
      <span class="sep">·</span>
      <span>Security Researcher</span>
    </div>

    <div class="typewriter-row">
      <div class="typewriter">Architecting Autonomous Intelligent Systems</div>
    </div>

    <div class="hero-tags">
      <div class="tag">Security-First</div>
      <div class="tag">Biometric AI</div>
      <div class="tag">LLM Engineering</div>
      <div class="tag">Open to Collaborate</div>
    </div>

    <div class="hero-stats">
      <div class="hstat">
        <span class="hstat-label">PROFILE VIEWS</span>
        <span class="hstat-val">392</span>
      </div>
      <div class="hstat">
        <span class="hstat-label">FOLLOWERS</span>
        <span class="hstat-val">3</span>
      </div>
      <div class="hstat">
        <span class="hstat-label">LOCATION</span>
        <span class="hstat-val">Odisha, IN</span>
      </div>
    </div>

    <div class="hero-status">
      <div class="live-dot"></div>
      <span>ONLINE &nbsp;·&nbsp; Building at the intersection of AI &amp; Systems</span>
    </div>
  </div>
</div>


<!-- ═══════════════════════════════════════════════════════════════════ -->
<!-- WHOAMI                                                             -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<div class="section reveal">
  <div class="section-title">whoami</div>
  <div class="terminal">
    <div class="term-bar">
      <div class="term-dot r"></div>
      <div class="term-dot y"></div>
      <div class="term-dot g"></div>
      <div class="term-title">AAJ@systems — bash</div>
    </div>
    <div class="term-body">
      <div><span class="term-prompt">AAJ@systems</span><span class="term-cmd">:~$ whoami</span></div>
      <div class="term-block">
        <div class="term-row"><span class="term-k">Name</span><span class="term-v">» <span class="hi">Aman Amarjit</span></span></div>
        <div class="term-row"><span class="term-k">Alias</span><span class="term-v">» <span class="hi">AAJ</span> &nbsp;·&nbsp; <span class="hi">Reshape The Algorithm (RTA)</span></span></div>
        <div class="term-row"><span class="term-k">Location</span><span class="term-v">» Odisha, India</span></div>
        <div class="term-row"><span class="term-k">Status</span><span class="term-v">» <span class="term-highlight">[ ONLINE ]</span> &nbsp;Building at the intersection of AI &amp; systems</span></div>
      </div>
      <div><span class="term-prompt">AAJ@systems</span><span class="term-cmd">:~$ cat focus.json</span></div>
      <div class="term-block">
        <div class="term-v"><span class="bracket">{</span></div>
        <div class="term-v" style="padding-left:16px">"primary"   : <span class="bracket">[</span><span class="str">"Machine Learning"</span>, <span class="str">"LLM Engineering"</span>, <span class="str">"NLP Pipelines"</span><span class="bracket">]</span>,</div>
        <div class="term-v" style="padding-left:16px">"secondary" : <span class="bracket">[</span><span class="str">"Security Engineering"</span>, <span class="str">"Biometric AI"</span>, <span class="str">"Quant Systems"</span><span class="bracket">]</span>,</div>
        <div class="term-v" style="padding-left:16px">"frontier"  : <span class="bracket">[</span><span class="str">"Autonomous Agents"</span>, <span class="str">"Human-Machine Interfaces"</span>, <span class="str">"Robotics"</span><span class="bracket">]</span></div>
        <div class="term-v"><span class="bracket">}</span></div>
      </div>
      <div><span class="term-prompt">AAJ@systems</span><span class="term-cmd">:~$ _</span><div class="term-cursor"></div></div>
    </div>
  </div>
</div>


<!-- ═══════════════════════════════════════════════════════════════════ -->
<!-- NOW                                                                -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<div class="section reveal">
  <div class="section-title">now</div>
  <div class="now-grid">
    <div class="now-item"><div class="now-arrow">▸</div><div class="now-text">Building AI systems under the <strong style="color:var(--cyan2)">RTA</strong> brand</div></div>
    <div class="now-item"><div class="now-arrow">▸</div><div class="now-text">Exploring LLM fine-tuning &amp; autonomous agents</div></div>
    <div class="now-item"><div class="now-arrow">▸</div><div class="now-text">Open to AI/ML internships &amp; freelance work</div></div>
    <div class="now-item"><div class="now-arrow">▸</div><div class="now-text">Competing in hackathons &amp; coding contests</div></div>
  </div>
</div>


<!-- ═══════════════════════════════════════════════════════════════════ -->
<!-- HIGHLIGHTS                                                         -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<div class="section reveal">
  <div class="section-title">highlights</div>
  <div class="highlights">
    <div class="hl"><span class="hl-bullet">✦</span><div class="hl-text">Delivered a <strong>multi-engine crypto analytics platform</strong> for an international client (CA)</div></div>
    <div class="hl"><span class="hl-bullet">✦</span><div class="hl-text"><strong>2nd Place</strong> — Code Verse · HORIZON 2026, IGIT Sarang (Mar 2026)</div></div>
    <div class="hl"><span class="hl-bullet">✦</span><div class="hl-text">Freelance AI/ML engineer — clients across <strong>India &amp; Canada</strong></div></div>
    <div class="hl"><span class="hl-bullet">✦</span><div class="hl-text">Founder, <strong>Reshape The Algorithm (RTA)</strong> — AI engineering practice</div></div>
  </div>
</div>


<!-- ═══════════════════════════════════════════════════════════════════ -->
<!-- PROJECTS                                                           -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<div class="section reveal">
  <div class="section-title">projects</div>
  <div class="table-wrap">
    <table class="projects-table">
      <thead>
        <tr>
          <th style="width:36px">#</th>
          <th>Project</th>
          <th style="width:200px">Links</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td class="proj-num">01</td>
          <td>
            <div class="proj-name">CRYPTO REVERSAL BOT</div>
            <div class="proj-desc">Production-grade algorithmic trading system with 15 analytical engines, breakout detection, volatility filtering, and a React/TypeScript dashboard. Built for international client.</div>
            <div class="proj-stack">
              <span class="pill">Python</span><span class="pill">FastAPI</span><span class="pill">React</span><span class="pill">TypeScript</span><span class="pill">Vite</span>
            </div>
          </td>
          <td class="proj-links">—</td>
        </tr>
        <tr>
          <td class="proj-num">02</td>
          <td>
            <div class="proj-name">KNOWLEDGE SYNTHESIZER</div>
            <div class="proj-desc">NLP pipeline that transforms raw audio and text into live semantic knowledge graphs. Extracts entities, infers concept relationships, renders real-time graph topology.</div>
            <div class="proj-stack">
              <span class="pill">FastAPI</span><span class="pill">NLP</span><span class="pill">Graph Rendering</span><span class="pill">Python</span>
            </div>
          </td>
          <td class="proj-links">
            <a href="https://knowledge-synthesizer.netlify.app/" target="_blank">↗ Demo</a>
            <a href="https://github.com/Aman-Amarjit/Knowledge-Synthesizer" target="_blank">↗ Src</a>
          </td>
        </tr>
        <tr>
          <td class="proj-num">03</td>
          <td>
            <div class="proj-name">BIOMETRIC ENGINE</div>
            <div class="proj-desc">Face recognition running 100% client-side via TensorFlow.js. Zero biometric data ever leaves the browser. JWT sessions + IndexedDB encryption.</div>
            <div class="proj-stack">
              <span class="pill">TensorFlow.js</span><span class="pill">JWT</span><span class="pill">IndexedDB</span><span class="pill">Security</span>
            </div>
          </td>
          <td class="proj-links">
            <a href="https://identity-verification-system.netlify.app/" target="_blank">↗ Demo</a>
            <a href="https://github.com/Aman-Amarjit/Face-recognition" target="_blank">↗ Src</a>
          </td>
        </tr>
        <tr>
          <td class="proj-num">04</td>
          <td>
            <div class="proj-name">DISCORD AI PERSONA</div>
            <div class="proj-desc">Autonomous social agent with a dynamic mood-state engine, persistent user memory via entity extraction, and multi-key API failover. Deployed via Docker + PM2.</div>
            <div class="proj-stack">
              <span class="pill">Gemini API</span><span class="pill">Episodic Memory</span><span class="pill">Docker</span><span class="pill">PM2</span>
            </div>
          </td>
          <td class="proj-links">
            <a href="https://github.com/Aman-Amarjit/discord-ai" target="_blank">↗ Src</a>
          </td>
        </tr>
        <tr>
          <td class="proj-num">05</td>
          <td>
            <div class="proj-name">SOLAR SYSTEM — GESTURE UI</div>
            <div class="proj-desc">Full WebGL solar system controlled by real-time hand gesture recognition. No controllers, no clicks. MediaPipe fused with Three.js orbital physics at 30fps.</div>
            <div class="proj-stack">
              <span class="pill">Three.js</span><span class="pill">MediaPipe</span><span class="pill">WebGL</span><span class="pill">CV</span>
            </div>
          </td>
          <td class="proj-links">
            <a href="https://solarsystemwithhandgestures.netlify.app/" target="_blank">↗ Demo</a>
            <a href="https://github.com/Aman-Amarjit/solar-system-using-hand-gesture" target="_blank">↗ Src</a>
          </td>
        </tr>
        <tr>
          <td class="proj-num">06</td>
          <td>
            <div class="proj-name">RULE THE WORLD</div>
            <div class="proj-desc">Geopolitical &amp; macroeconomic strategy simulator on a custom modular JS engine — zero framework dependencies. Real-time diplomatic state machines, multi-variable economic modeling.</div>
            <div class="proj-stack">
              <span class="pill">Vanilla JS</span><span class="pill">Event-Driven</span><span class="pill">State Machines</span>
            </div>
          </td>
          <td class="proj-links">
            <a href="https://ruletheworldmadebyaaj.netlify.app/" target="_blank">↗ Demo</a>
            <a href="https://github.com/Aman-Amarjit/RULE-THE-WORLD" target="_blank">↗ Src</a>
          </td>
        </tr>
        <tr>
          <td class="proj-num">07</td>
          <td>
            <div class="proj-name">PERSONAL BUTLER (PANDA AI)</div>
            <div class="proj-desc">AI desktop agent with episodic memory, local RAG pipeline, and a cognitive emotion framework (OCC/PAD model). Voice-driven interaction via Whisper.</div>
            <div class="proj-stack">
              <span class="pill">Whisper</span><span class="pill">FastAPI</span><span class="pill">RAG</span><span class="pill">Python</span>
            </div>
          </td>
          <td class="proj-links">
            <a href="https://github.com/Aman-Amarjit/personal-butler" target="_blank">↗ Src</a>
          </td>
        </tr>
        <tr>
          <td class="proj-num">08</td>
          <td>
            <div class="proj-name">PLUMBER</div>
            <div class="proj-desc">Dual-interface Android service marketplace in Kotlin — real-time technician tracking, booking dashboard, and live status updates.</div>
            <div class="proj-stack">
              <span class="pill">Kotlin</span><span class="pill">Android</span><span class="pill">Firebase</span>
            </div>
          </td>
          <td class="proj-links">
            <a href="https://github.com/Aman-Amarjit/PLUMBER" target="_blank">↗ Src</a>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</div>


<!-- ═══════════════════════════════════════════════════════════════════ -->
<!-- TECH STACK                                                         -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<div class="section reveal">
  <div class="section-title">tech stack</div>
  <div class="stack-grid">
    <div class="stack-category">
      <div class="stack-cat-title">AI · ML · Computer Vision</div>
      <div class="stack-items">
        <div class="stack-item"><span class="dot-i"></span>Python</div>
        <div class="stack-item"><span class="dot-i"></span>TensorFlow</div>
        <div class="stack-item"><span class="dot-i"></span>PyTorch</div>
        <div class="stack-item"><span class="dot-i"></span>MediaPipe</div>
        <div class="stack-item"><span class="dot-i"></span>Whisper</div>
        <div class="stack-item"><span class="dot-i"></span>Gemini API</div>
      </div>
    </div>
    <div class="stack-category">
      <div class="stack-cat-title">Backend · Systems · Infrastructure</div>
      <div class="stack-items">
        <div class="stack-item"><span class="dot-i"></span>FastAPI</div>
        <div class="stack-item"><span class="dot-i"></span>Node.js</div>
        <div class="stack-item"><span class="dot-i"></span>Docker</div>
        <div class="stack-item"><span class="dot-i"></span>Nginx</div>
        <div class="stack-item"><span class="dot-i"></span>PM2</div>
        <div class="stack-item"><span class="dot-i"></span>Linux</div>
        <div class="stack-item"><span class="dot-i"></span>GitHub Actions</div>
      </div>
    </div>
    <div class="stack-category">
      <div class="stack-cat-title">Frontend · Interfaces</div>
      <div class="stack-items">
        <div class="stack-item"><span class="dot-i"></span>React</div>
        <div class="stack-item"><span class="dot-i"></span>TypeScript</div>
        <div class="stack-item"><span class="dot-i"></span>JavaScript</div>
        <div class="stack-item"><span class="dot-i"></span>Three.js</div>
        <div class="stack-item"><span class="dot-i"></span>Vite</div>
        <div class="stack-item"><span class="dot-i"></span>HTML/CSS</div>
      </div>
    </div>
    <div class="stack-category">
      <div class="stack-cat-title">Data · Storage · Platforms</div>
      <div class="stack-items">
        <div class="stack-item"><span class="dot-i"></span>Firebase</div>
        <div class="stack-item"><span class="dot-i"></span>PostgreSQL</div>
        <div class="stack-item"><span class="dot-i"></span>MongoDB</div>
        <div class="stack-item"><span class="dot-i"></span>IndexedDB</div>
        <div class="stack-item"><span class="dot-i"></span>Netlify</div>
        <div class="stack-item"><span class="dot-i"></span>Vercel</div>
        <div class="stack-item"><span class="dot-i"></span>Kotlin/Android</div>
      </div>
    </div>
  </div>
</div>


<!-- ═══════════════════════════════════════════════════════════════════ -->
<!-- MANIFESTO                                                          -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<div class="section reveal">
  <div class="section-title">engineering doctrine</div>
  <div class="manifesto">
    <div class="manifesto-header">T H E &nbsp; A A J &nbsp; M A N I F E S T O</div>
    <ul class="manifesto-items">
      <li class="manifesto-item">
        <span class="man-num">I</span>
        <span class="man-text"><span class="man-accent">Security</span> is not a feature — it is the foundation.</span>
      </li>
      <li class="manifesto-item">
        <span class="man-num">II</span>
        <span class="man-text">Every <span class="man-accent">abstraction</span> must earn its complexity.</span>
      </li>
      <li class="manifesto-item">
        <span class="man-num">III</span>
        <span class="man-text">Systems should <span class="man-accent">think</span>. Interfaces should <span class="man-accent">transcend</span>.</span>
      </li>
      <li class="manifesto-item">
        <span class="man-num">IV</span>
        <span class="man-text">Ship with <span class="man-accent">intent</span>. Refactor with <span class="man-accent">courage</span>.</span>
      </li>
      <li class="manifesto-item">
        <span class="man-num">V</span>
        <span class="man-text">The best code is the code that <span class="man-accent">doesn't need comments</span>.</span>
      </li>
    </ul>
    <div class="manifesto-sig">— Aman Amarjit &nbsp;·&nbsp; AAJ &nbsp;·&nbsp; RTA &nbsp;·&nbsp; 2025 —</div>
  </div>
</div>


<!-- ═══════════════════════════════════════════════════════════════════ -->
<!-- CONNECT                                                            -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<div class="section reveal">
  <div class="section-title">connect</div>
  <div class="connect-grid">
    <a href="https://www.linkedin.com/in/aman-amarjit-991016368/" target="_blank" class="connect-card">
      <div class="connect-icon">💼</div>
      <div class="connect-label">LinkedIn</div>
      <div class="connect-val">aman-amarjit</div>
    </a>
    <a href="https://aman-amarjit.onrender.com/" target="_blank" class="connect-card">
      <div class="connect-icon">🌐</div>
      <div class="connect-label">Portfolio</div>
      <div class="connect-val">aman-amarjit.onrender.com</div>
    </a>
    <a href="https://www.instagram.com/amanamarjit8/" target="_blank" class="connect-card">
      <div class="connect-icon">📷</div>
      <div class="connect-label">Instagram</div>
      <div class="connect-val">@amanamarjit8</div>
    </a>
    <a href="mailto:amanamarjit04@gmail.com" class="connect-card">
      <div class="connect-icon">✉️</div>
      <div class="connect-label">Email</div>
      <div class="connect-val">amanamarjit04@gmail.com</div>
    </a>
  </div>
</div>


<!-- ═══════════════════════════════════════════════════════════════════ -->
<!-- FOOTER                                                             -->
<!-- ═══════════════════════════════════════════════════════════════════ -->
<div class="footer">
  Built with <span>precision</span>. Deployed with <span>intent</span>.
  &nbsp;·&nbsp; Aman Amarjit &nbsp;·&nbsp; AAJ &nbsp;·&nbsp; RTA &nbsp;·&nbsp; 2025
</div>

</div><!-- /page -->

<script>
// Scroll reveal
const reveals = document.querySelectorAll('.reveal');
const io = new IntersectionObserver((entries)=>{
  entries.forEach(e=>{
    if(e.isIntersecting){e.target.classList.add('visible');io.unobserve(e.target)}
  });
},{threshold:.1});
reveals.forEach(r=>io.observe(r));

// Typewriter cycling
const lines = [
  'Architecting Autonomous Intelligent Systems',
  'Security-First | Biometric AI | NLP Pipelines',
  'Human-Machine Interface Engineering',
  'Full-Stack | Backend | Distributed AI',
  'Freelance AI Engineer · Open to Collaborate'
];
let idx = 0;
const tw = document.querySelector('.typewriter');
function cycle(){
  tw.style.animation = 'none';
  tw.textContent = lines[idx % lines.length];
  void tw.offsetWidth; // reflow
  tw.style.animation = 'typeLine 3.5s steps(50,end) forwards, blink .75s step-end infinite';
  idx++;
}
cycle();
setInterval(()=>{
  tw.style.opacity = '0';
  setTimeout(()=>{tw.style.opacity='1'; cycle();}, 400);
}, 5000);
</script>
</body>
</html>
