<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HARDIANTO.EXE // Mekatronika Engineer</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;700;900&family=Rajdhani:wght@300;400;500;600;700&family=Share+Tech+Mono&display=swap');

:root {
  --f-display: 'Orbitron', 'Trebuchet MS', 'Impact', sans-serif;
  --f-body:    'Rajdhani', 'Arial Narrow', 'Calibri', Arial, sans-serif;
  --f-mono:    'Share Tech Mono', 'Consolas', 'Lucida Console', 'Courier New', monospace;
  --yellow: #FCE300;
  --cyan:   #00F5FF;
  --pink:   #FF003C;
  --darker: #050508;
  --panel:  rgba(8,8,18,0.92);
  --border: rgba(252,227,0,0.25);
  --glow-y: 0 0 8px #FCE300, 0 0 24px rgba(252,227,0,0.35);
  --glow-c: 0 0 8px #00F5FF, 0 0 24px rgba(0,245,255,0.35);
  --nav-h:  64px;
}
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{background:var(--darker);color:#ddd;font-family:var(--f-body);overflow-x:hidden;cursor:none;min-height:100vh;}
body::after{content:'';position:fixed;inset:0;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,0,0,0.032) 2px,rgba(0,0,0,0.032) 4px);pointer-events:none;z-index:900;}

/* ═══ NAVBAR ═══ */
nav{position:fixed;top:0;left:0;right:0;height:var(--nav-h);z-index:800;display:flex;align-items:center;justify-content:space-between;padding:0 48px;background:rgba(3,3,8,0.97);backdrop-filter:blur(20px) saturate(1.5);border-bottom:1px solid rgba(252,227,0,0.12);box-shadow:0 1px 40px rgba(0,0,0,0.7),0 0 0 0.5px rgba(252,227,0,0.06);transition:background 0.3s;}
.nav-logo{display:flex;align-items:center;gap:12px;text-decoration:none;flex-shrink:0;}
.nav-logo-icon{width:36px;height:36px;border:1.5px solid var(--yellow);display:flex;align-items:center;justify-content:center;font-family:var(--f-display);font-size:0.58rem;font-weight:900;color:var(--yellow);box-shadow:var(--glow-y),inset 0 0 10px rgba(252,227,0,0.08);clip-path:polygon(7px 0%,100% 0%,calc(100% - 7px) 100%,0% 100%);transition:all 0.3s;letter-spacing:0;}
.nav-logo:hover .nav-logo-icon{background:rgba(252,227,0,0.1);}
.nav-logo-text{font-family:var(--f-display);font-weight:900;font-size:0.82rem;color:var(--yellow);text-shadow:var(--glow-y);letter-spacing:3px;text-transform:uppercase;line-height:1;display:block;}
.nav-logo-sub{font-family:var(--f-mono);font-size:0.5rem;color:#555;letter-spacing:2px;display:block;margin-top:3px;}
.nav-links{display:flex;align-items:center;gap:2px;list-style:none;}
.nav-links a{font-family:var(--f-display);font-size:0.56rem;font-weight:600;color:#5a5a72;text-decoration:none;letter-spacing:2.5px;text-transform:uppercase;padding:8px 14px;position:relative;transition:color 0.25s;white-space:nowrap;}
.nav-links a::after{content:'';position:absolute;bottom:4px;left:14px;right:14px;height:1px;background:var(--yellow);box-shadow:var(--glow-y);transform:scaleX(0);transition:transform 0.28s cubic-bezier(0.23,1,0.32,1);}
.nav-links a:hover,.nav-links a.active{color:var(--yellow);text-shadow:0 0 10px rgba(252,227,0,0.45);}
.nav-links a:hover::after,.nav-links a.active::after{transform:scaleX(1);}
.nav-cta{font-family:var(--f-display);font-size:0.54rem;font-weight:700;letter-spacing:2.5px;color:#000;background:var(--yellow);padding:9px 22px;text-decoration:none;text-transform:uppercase;clip-path:polygon(8px 0%,100% 0%,calc(100% - 8px) 100%,0% 100%);transition:all 0.25s;flex-shrink:0;margin-left:16px;cursor:none;}
.nav-cta:hover{background:#fff;box-shadow:var(--glow-y);}

/* ═══ CURSOR ═══ */
.cursor{position:fixed;width:10px;height:10px;background:var(--yellow);border-radius:50%;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);box-shadow:var(--glow-y);transition:transform 0.1s;}
.cursor-ring{position:fixed;width:30px;height:30px;border:1px solid var(--cyan);border-radius:50%;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);transition:border-color 0.2s;box-shadow:var(--glow-c);}

/* ═══ HERO ═══ */
#hero{min-height:100vh;display:flex;align-items:center;position:relative;padding:calc(var(--nav-h) + 60px) 60px 80px;overflow:hidden;}
.hero-bg{position:absolute;inset:0;background:radial-gradient(ellipse 70% 80% at 78% 55%,rgba(0,245,255,0.055) 0%,transparent 65%),radial-gradient(ellipse 50% 70% at 18% 30%,rgba(255,0,60,0.065) 0%,transparent 65%),linear-gradient(160deg,#040408 0%,#0A0A1C 100%);}
.hero-grid{position:absolute;inset:0;background-image:linear-gradient(rgba(252,227,0,0.045) 1px,transparent 1px),linear-gradient(90deg,rgba(252,227,0,0.045) 1px,transparent 1px);background-size:58px 58px;transform:perspective(700px) rotateX(14deg);transform-origin:50% 100%;pointer-events:none;}
.hero-content{position:relative;z-index:2;max-width:660px;}
.hero-eyebrow{font-family:var(--f-mono);font-size:0.7rem;color:var(--cyan);letter-spacing:4px;text-transform:uppercase;margin-bottom:22px;opacity:0;animation:fadeUp 0.6s 0.1s ease forwards;}
.hero-eyebrow::before{content:'[ ';color:var(--yellow);}
.hero-eyebrow::after{content:' ]';color:var(--yellow);}
.hero-name{font-family:var(--f-display);font-weight:900;font-size:clamp(2.6rem,6.5vw,5rem);line-height:0.94;color:var(--yellow);text-shadow:var(--glow-y);letter-spacing:1px;text-transform:uppercase;opacity:0;animation:fadeUp 0.6s 0.2s ease forwards;}
.glitch{position:relative;display:inline-block;}
.glitch::before,.glitch::after{content:attr(data-text);position:absolute;top:0;left:0;width:100%;height:100%;}
.glitch::before{color:var(--cyan);clip-path:polygon(0 22%,100% 22%,100% 42%,0 42%);animation:glitch1 5s infinite;}
.glitch::after{color:var(--pink);clip-path:polygon(0 62%,100% 62%,100% 78%,0 78%);animation:glitch2 5s infinite;}
.hero-subtitle{font-family:var(--f-body);font-size:clamp(0.9rem,2vw,1.3rem);font-weight:300;color:#aaa;letter-spacing:5px;text-transform:uppercase;margin:18px 0 26px;opacity:0;animation:fadeUp 0.6s 0.3s ease forwards;}
.hero-subtitle span{color:var(--cyan);font-weight:600;}
.hero-desc{font-family:var(--f-mono);font-size:0.78rem;color:#666;line-height:1.95;max-width:520px;margin-bottom:40px;opacity:0;animation:fadeUp 0.6s 0.4s ease forwards;}
.hero-desc .hl{color:var(--yellow);}
.hero-btns{display:flex;gap:14px;flex-wrap:wrap;opacity:0;animation:fadeUp 0.6s 0.5s ease forwards;}
.hero-side{position:absolute;right:72px;top:50%;transform:translateY(-50%);z-index:2;opacity:0;animation:fadeUp 0.8s 0.55s ease forwards;}
.avatar-wrap{width:250px;height:290px;position:relative;}
.avatar-border{position:absolute;inset:0;background:linear-gradient(135deg,var(--yellow),var(--cyan),var(--pink),var(--yellow));background-size:300% 300%;clip-path:polygon(20px 0%,100% 0%,100% calc(100% - 20px),calc(100% - 20px) 100%,0% 100%,0% 20px);animation:borderSpin 4s linear infinite;}
.avatar-inner{position:absolute;inset:2px;background:linear-gradient(150deg,#0e0e1c,#060610);clip-path:polygon(20px 0%,100% 0%,100% calc(100% - 20px),calc(100% - 20px) 100%,0% 100%,0% 20px);display:flex;flex-direction:column;align-items:center;justify-content:center;gap:6px;}
.avatar-letters{font-family:var(--f-display);font-size:3.6rem;font-weight:900;color:var(--yellow);text-shadow:var(--glow-y);letter-spacing:-2px;}
.avatar-sub{font-family:var(--f-mono);font-size:0.52rem;color:var(--cyan);letter-spacing:3px;text-transform:uppercase;opacity:0.7;}
.avatar-hint{position:absolute;bottom:-22px;left:0;right:0;text-align:center;font-family:var(--f-mono);font-size:0.48rem;color:#2a2a3a;letter-spacing:3px;}
.scroll-ind{position:absolute;bottom:32px;left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:8px;animation:bounce 2.2s infinite;}
.scroll-ind span{font-family:var(--f-mono);font-size:0.56rem;color:#3a3a4a;letter-spacing:3px;}
.scroll-arrow{width:1px;height:34px;background:linear-gradient(180deg,transparent,var(--yellow));}

/* ═══ BTN ═══ */
.btn{font-family:var(--f-display);font-size:0.62rem;font-weight:700;letter-spacing:2.5px;text-transform:uppercase;padding:12px 28px;border:none;cursor:none;text-decoration:none;transition:all 0.28s;display:inline-block;}
.btn-primary{background:var(--yellow);color:#000;clip-path:polygon(10px 0%,100% 0%,calc(100% - 10px) 100%,0% 100%);}
.btn-primary:hover{background:#fff;box-shadow:var(--glow-y);transform:scale(1.04);}
.btn-secondary{background:transparent;color:var(--cyan);border:1px solid var(--cyan);clip-path:polygon(10px 0%,100% 0%,calc(100% - 10px) 100%,0% 100%);}
.btn-secondary:hover{background:rgba(0,245,255,0.08);box-shadow:var(--glow-c);transform:scale(1.04);}

/* ═══ SECTION COMMON ═══ */
section{padding:100px 60px;position:relative;}
.section-header{display:flex;align-items:center;gap:18px;margin-bottom:56px;}
.section-num{font-family:var(--f-mono);font-size:0.65rem;color:var(--pink);letter-spacing:3px;white-space:nowrap;flex-shrink:0;}
.section-title{font-family:var(--f-display);font-size:clamp(1.3rem,3vw,2rem);font-weight:900;color:var(--yellow);text-shadow:var(--glow-y);letter-spacing:5px;text-transform:uppercase;}
.section-line{flex:1;height:1px;max-width:260px;background:linear-gradient(90deg,var(--yellow),transparent);}

/* ═══ ABOUT ═══ */
#about{background:linear-gradient(180deg,var(--darker),rgba(8,8,20,0.5));}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:56px;align-items:center;}
.about-text p{font-family:var(--f-mono);font-size:0.8rem;line-height:1.95;color:#777;margin-bottom:18px;}
.about-text p .hl{color:var(--yellow);}
.about-text p .hl2{color:var(--cyan);}
.stat-grid{display:grid;grid-template-columns:1fr 1fr;gap:16px;}
.stat-card{border:1px solid var(--border);padding:22px 18px;background:var(--panel);clip-path:polygon(10px 0%,100% 0%,100% calc(100% - 10px),calc(100% - 10px) 100%,0% 100%,0% 10px);transition:all 0.3s;position:relative;}
.stat-card::before{content:'';position:absolute;top:0;left:0;width:3px;height:100%;background:var(--yellow);}
.stat-card:hover{border-color:var(--yellow);box-shadow:var(--glow-y);transform:translateY(-4px);}
.stat-num{font-family:var(--f-display);font-size:1.8rem;font-weight:900;color:var(--yellow);}
.stat-label{font-family:var(--f-mono);font-size:0.6rem;color:#444;letter-spacing:2px;text-transform:uppercase;margin-top:4px;}

/* ═══ SKILLS ═══ */
#skills{background:var(--darker);}
.skills-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:22px;}
.skill-category{border:1px solid rgba(0,245,255,0.18);padding:28px;background:var(--panel);clip-path:polygon(14px 0%,100% 0%,100% calc(100% - 14px),calc(100% - 14px) 100%,0% 100%,0% 14px);transition:all 0.3s;}
.skill-category:hover{border-color:var(--cyan);box-shadow:0 0 28px rgba(0,245,255,0.1);transform:translateY(-5px);}
.skill-cat-title{font-family:var(--f-display);font-size:0.62rem;font-weight:700;color:var(--cyan);letter-spacing:3px;text-transform:uppercase;margin-bottom:22px;display:flex;align-items:center;gap:10px;}
.skill-cat-title::before{content:'';display:inline-block;width:7px;height:7px;background:var(--cyan);box-shadow:var(--glow-c);}
.skill-item{margin-bottom:15px;}
.skill-name{display:flex;justify-content:space-between;font-family:var(--f-body);font-size:0.9rem;font-weight:600;color:#ccc;margin-bottom:6px;}
.skill-pct{color:var(--yellow);font-family:var(--f-mono);}
.skill-bar{height:2px;background:rgba(255,255,255,0.06);overflow:hidden;}
.skill-fill{height:100%;width:0%;background:linear-gradient(90deg,var(--cyan),var(--yellow));transition:width 1.3s cubic-bezier(0.23,1,0.32,1);box-shadow:0 0 6px var(--cyan);}

/* ═══ PROJECTS ═══ */
#projects{background:linear-gradient(180deg,var(--darker),rgba(4,4,10,0.7));}
.projects-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(400px,1fr));gap:26px;}
.project-card{border:1px solid rgba(252,227,0,0.1);background:var(--panel);clip-path:polygon(20px 0%,100% 0%,100% calc(100% - 20px),calc(100% - 20px) 100%,0% 100%,0% 20px);overflow:hidden;transition:all 0.38s;cursor:none;}
.project-card:hover{border-color:var(--yellow);box-shadow:var(--glow-y);transform:translateY(-8px);}
.project-img{height:195px;position:relative;overflow:hidden;display:flex;align-items:center;justify-content:center;}
.project-img-bg{position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-size:5.5rem;transition:transform 0.4s;}
.project-card:hover .project-img-bg{transform:scale(1.1);}
.bg1{background:linear-gradient(135deg,#0c1840,#001268,#0A0A1a);}
.bg2{background:linear-gradient(135deg,#1e0035,#0d0022,#0A0A1a);}
.project-overlay{position:absolute;inset:0;background:rgba(252,227,0,0.06);display:flex;align-items:center;justify-content:center;font-family:var(--f-mono);font-size:0.7rem;color:var(--yellow);letter-spacing:3px;opacity:0;transition:opacity 0.38s;}
.project-card:hover .project-overlay{opacity:1;}
.project-badge{position:absolute;top:12px;right:12px;font-family:var(--f-display);font-size:0.52rem;font-weight:700;padding:4px 12px;letter-spacing:2px;clip-path:polygon(6px 0%,100% 0%,calc(100% - 6px) 100%,0% 100%);}
.badge-pbl{background:var(--yellow);color:#000;}
.badge-magang{background:var(--cyan);color:#000;}
.project-body{padding:24px;}
.project-tags{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:12px;}
.tag{font-family:var(--f-mono);font-size:0.58rem;padding:3px 10px;border:1px solid var(--cyan);color:var(--cyan);letter-spacing:2px;text-transform:uppercase;clip-path:polygon(5px 0%,100% 0%,calc(100% - 5px) 100%,0% 100%);}
.project-title{font-family:var(--f-display);font-size:0.9rem;font-weight:700;color:var(--yellow);margin-bottom:11px;letter-spacing:1px;}
.project-desc{font-family:var(--f-mono);font-size:0.75rem;color:#666;line-height:1.85;}
.project-footer{display:flex;justify-content:space-between;align-items:center;padding:13px 24px;border-top:1px solid rgba(255,255,255,0.04);}
.proj-tag{font-family:var(--f-mono);font-size:0.6rem;letter-spacing:2px;}
.proj-done{color:#00e87a;}
.proj-event{color:var(--cyan);}

/* ═══ TIMELINE (shared) ═══ */
.timeline{position:relative;padding-left:44px;}
.timeline::before{content:'';position:absolute;left:0;top:0;bottom:0;width:1px;background:linear-gradient(180deg,var(--yellow),var(--cyan),transparent);}
.timeline-item{position:relative;margin-bottom:34px;padding:28px;border:1px solid var(--border);background:var(--panel);clip-path:polygon(14px 0%,100% 0%,100% calc(100% - 14px),calc(100% - 14px) 100%,0% 100%,0% 14px);transition:all 0.3s;}
.timeline-item:hover{border-color:var(--yellow);box-shadow:var(--glow-y);}
.timeline-item::before{content:'';position:absolute;left:-50px;top:26px;width:12px;height:12px;background:var(--yellow);box-shadow:var(--glow-y);clip-path:polygon(50% 0%,100% 50%,50% 100%,0% 50%);}
.tl-date{font-family:var(--f-mono);font-size:0.62rem;color:var(--pink);letter-spacing:2.5px;margin-bottom:7px;}
.tl-role{font-family:var(--f-display);font-size:0.9rem;font-weight:700;color:var(--yellow);margin-bottom:4px;}
.tl-company{font-family:var(--f-body);font-size:0.95rem;font-weight:500;color:var(--cyan);margin-bottom:14px;letter-spacing:1px;}
.tl-desc{font-family:var(--f-mono);font-size:0.74rem;color:#666;line-height:1.9;}
.tl-desc .hl{color:var(--yellow);}
.tl-list{margin-top:10px;padding-left:0;list-style:none;}
.tl-list li{padding:3px 0;padding-left:18px;position:relative;font-family:var(--f-mono);font-size:0.73rem;color:#666;line-height:1.7;}
.tl-list li::before{content:'▸';position:absolute;left:0;color:var(--cyan);}

/* ═══ EXPERIENCE ═══ */
#experience{background:var(--darker);}

/* ═══ EDUCATION ═══ */
#education{background:linear-gradient(180deg,var(--darker),rgba(4,4,14,0.7));}
#education .timeline-item::before{background:var(--cyan);box-shadow:var(--glow-c);}
#education .timeline-item:hover{border-color:var(--cyan);box-shadow:var(--glow-c);}
.edu-badge{display:inline-block;font-family:var(--f-display);font-size:0.52rem;font-weight:700;padding:4px 12px;margin-bottom:12px;color:#000;background:var(--cyan);clip-path:polygon(6px 0%,100% 0%,calc(100% - 6px) 100%,0% 100%);letter-spacing:2px;}
.edu-ipk{display:inline-flex;align-items:center;gap:10px;margin-bottom:14px;}
.edu-ipk-val{font-family:var(--f-display);font-size:1.6rem;font-weight:900;color:var(--yellow);text-shadow:var(--glow-y);}
.edu-ipk-label{font-family:var(--f-mono);font-size:0.6rem;color:#555;letter-spacing:2px;text-transform:uppercase;line-height:1.5;}

/* ═══ CONTACT ═══ */
#contact{background:linear-gradient(180deg,var(--darker),#030306);text-align:center;}
.contact-intro{font-family:var(--f-mono);font-size:0.78rem;color:#555;letter-spacing:2px;line-height:1.9;margin:0 auto 50px;max-width:480px;}
.contact-intro .hl{color:var(--cyan);}
.contact-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:18px;max-width:820px;margin:0 auto 48px;}
.contact-card{border:1px solid var(--border);padding:26px 18px;background:var(--panel);clip-path:polygon(12px 0%,100% 0%,100% calc(100% - 12px),calc(100% - 12px) 100%,0% 100%,0% 12px);transition:all 0.3s;text-decoration:none;display:block;}
.contact-card:hover{border-color:var(--cyan);box-shadow:var(--glow-c);transform:translateY(-5px);}
.cc-icon{font-size:1.7rem;margin-bottom:10px;}
.cc-label{font-family:var(--f-display);font-size:0.56rem;color:var(--cyan);letter-spacing:3px;text-transform:uppercase;margin-bottom:6px;}
.cc-val{font-family:var(--f-mono);font-size:0.75rem;color:#bbb;word-break:break-all;}

/* ═══ FOOTER ═══ */
footer{border-top:1px solid rgba(252,227,0,0.1);padding:20px 60px;display:flex;justify-content:space-between;align-items:center;background:#030305;}
footer p{font-family:var(--f-mono);font-size:0.6rem;color:#2e2e3a;letter-spacing:2px;}
footer span{color:var(--yellow);}

/* ═══ REVEAL ═══ */
.reveal{opacity:0;transform:translateY(32px);transition:opacity 0.75s ease,transform 0.75s cubic-bezier(0.23,1,0.32,1);}
.reveal.visible{opacity:1;transform:translateY(0);}
.d1{transition-delay:0.1s;}.d2{transition-delay:0.2s;}.d3{transition-delay:0.3s;}

/* ═══ ANIMATIONS ═══ */
@keyframes fadeUp{from{opacity:0;transform:translateY(26px);}to{opacity:1;transform:translateY(0);}}
@keyframes glitch1{0%,87%,100%{transform:translate(0);opacity:0;}89%{transform:translate(-3px,1px);opacity:0.7;}92%{transform:translate(3px,-1px);opacity:0.7;}95%{transform:translate(-1px,0);opacity:0.4;}}
@keyframes glitch2{0%,83%,100%{transform:translate(0);opacity:0;}85%{transform:translate(3px,-2px);opacity:0.6;}88%{transform:translate(-3px,2px);opacity:0.6;}91%{transform:translate(2px,1px);opacity:0.3;}}
@keyframes borderSpin{0%{background-position:0% 0%;}50%{background-position:100% 100%;}100%{background-position:0% 0%;}}
@keyframes bounce{0%,100%{transform:translateX(-50%) translateY(0);}50%{transform:translateX(-50%) translateY(9px);}}
@keyframes blink{0%,100%{opacity:1;}50%{opacity:0;}}
.blink{animation:blink 1s infinite;}

/* ═══ RESPONSIVE ═══ */
@media(max-width:960px){
  nav{padding:0 24px;}
  .nav-links,.nav-cta{display:none;}
  section{padding:80px 24px;}
  #hero{padding:calc(var(--nav-h) + 40px) 24px 80px;}
  .hero-side{position:relative;right:auto;top:auto;transform:none;margin-top:48px;}
  .about-grid{grid-template-columns:1fr;gap:40px;}
  .projects-grid{grid-template-columns:1fr;}
  footer{flex-direction:column;gap:8px;text-align:center;padding:20px 24px;}
}
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- ════════════ NAVBAR ════════════ -->
<nav id="navbar">
  <a href="#hero" class="nav-logo">
    <div class="nav-logo-icon">HPP</div>
    <div>
      <span class="nav-logo-text">Hardianto.exe</span>
      <span class="nav-logo-sub">Mekatronika Engineer</span>
    </div>
  </a>

  <ul class="nav-links" id="navLinks">
    <li><a href="#about">Tentang</a></li>
    <li><a href="#skills">Keahlian</a></li>
    <li><a href="#projects">Proyek</a></li>
    <li><a href="#experience">Pengalaman</a></li>
    <li><a href="#education">Pendidikan</a></li>
    <li><a href="#contact">Kontak</a></li>
  </ul>

  <a href="mailto:hardiantoputra789@gmail.com" class="nav-cta">◈ Hubungi</a>
</nav>

<!-- ════════════ HERO ════════════ -->
<section id="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid" id="heroGrid"></div>
  <div class="hero-content">
    <div class="hero-eyebrow">Mahasiswa Mekatronika // Inovator Sistem Otomasi</div>
    <h1 class="hero-name">
      <span class="glitch" data-text="HARDIANTO">HARDIANTO</span><br>
      <span class="glitch" data-text="PUTRA">PUTRA</span><br>
      <span class="glitch" data-text="PRATAMA">PRATAMA</span>
    </h1>
    <p class="hero-subtitle"><span>Teknologi Rekayasa</span> Mekatronika</p>
    <p class="hero-desc">
      &gt; Membangun sistem cerdas di persimpangan mekanika,<br>
      &gt; elektronika, dan kecerdasan buatan.<br>
      &gt; Dari <span class="hl">RFID Smart Locker</span> hingga mesin <span class="hl">FillFlow</span> —<br>
      &gt; inovasi nyata yang berdampak.<span class="blink">_</span>
    </p>
    <div class="hero-btns">
      <a href="#projects" class="btn btn-primary">▶ Lihat Proyek</a>
      <a href="#contact" class="btn btn-secondary">◈ Hubungi Saya</a>
    </div>
  </div>
  <div class="hero-side">
    <div class="avatar-wrap">
      <div class="avatar-border"></div>
      <div class="avatar-inner">
        <div class="avatar-letters">HPP</div>
        <div class="avatar-sub">Mekatronika</div>
      </div>
    </div>
    <div class="avatar-hint">[ Tambahkan foto kamu di sini ]</div>
  </div>
  <div class="scroll-ind"><span>SCROLL</span><div class="scroll-arrow"></div></div>
</section>

<!-- ════════════ ABOUT ════════════ -->
<section id="about">
  <div class="section-header reveal">
    <span class="section-num">01 //</span>
    <h2 class="section-title">Tentang Saya</h2>
    <div class="section-line"></div>
  </div>
  <div class="about-grid">
    <div class="about-text reveal">
      <p>Halo! Saya <span class="hl">Hardianto Putra Pratama</span>, mahasiswa D4 Teknologi Rekayasa Mekatronika di Politeknik Negeri Jember dengan IPK <span class="hl">3.83</span>.</p>
      <p>Passion saya ada pada perancangan sistem otomasi dan robotika. Percaya bahwa inovasi terbaik lahir dari kolaborasi — memadukan <span class="hl2">hardware, software, dan kreativitas</span> untuk solusi nyata.</p>
      <p>Dari <span class="hl">Smart Locker</span> berbasis RFID, mesin <span class="hl">FillFlow</span> otomatis, hingga magang di <span class="hl">PT PLN (Persero)</span> — saya terus menghadirkan karya yang fungsional dan berdampak.</p>
    </div>
    <div class="stat-grid">
      <div class="stat-card reveal d1"><div class="stat-num">3.83</div><div class="stat-label">IPK Saat Ini</div></div>
      <div class="stat-card reveal d2"><div class="stat-num">2+</div><div class="stat-label">Proyek Nyata</div></div>
      <div class="stat-card reveal d1"><div class="stat-num">3+</div><div class="stat-label">Pengalaman</div></div>
      <div class="stat-card reveal d2"><div class="stat-num">∞</div><div class="stat-label">Semangat Belajar</div></div>
    </div>
  </div>
</section>

<!-- ════════════ SKILLS ════════════ -->
<section id="skills">
  <div class="section-header reveal">
    <span class="section-num">02 //</span>
    <h2 class="section-title">Keahlian</h2>
    <div class="section-line"></div>
  </div>
  <div class="skills-grid">
    <div class="skill-category reveal">
      <div class="skill-cat-title">Hardware &amp; Elektronika</div>
      <div class="skill-item"><div class="skill-name"><span>RFID &amp; Sistem Sensor</span><span class="skill-pct">85%</span></div><div class="skill-bar"><div class="skill-fill" data-w="85"></div></div></div>
      <div class="skill-item"><div class="skill-name"><span>Mikrokontroler Arduino/ESP32</span><span class="skill-pct">83%</span></div><div class="skill-bar"><div class="skill-fill" data-w="83"></div></div></div>
      <div class="skill-item"><div class="skill-name"><span>Desain PCB</span><span class="skill-pct">75%</span></div><div class="skill-bar"><div class="skill-fill" data-w="75"></div></div></div>
      <div class="skill-item"><div class="skill-name"><span>Sistem Konveyor &amp; Aktuator</span><span class="skill-pct">80%</span></div><div class="skill-bar"><div class="skill-fill" data-w="80"></div></div></div>
    </div>
    <div class="skill-category reveal d1">
      <div class="skill-cat-title">Pemrograman</div>
      <div class="skill-item"><div class="skill-name"><span>C / C++ (Embedded)</span><span class="skill-pct">82%</span></div><div class="skill-bar"><div class="skill-fill" data-w="82"></div></div></div>
      <div class="skill-item"><div class="skill-name"><span>Python</span><span class="skill-pct">75%</span></div><div class="skill-bar"><div class="skill-fill" data-w="75"></div></div></div>
      <div class="skill-item"><div class="skill-name"><span>Pengembangan Aplikasi Mobile</span><span class="skill-pct">70%</span></div><div class="skill-bar"><div class="skill-fill" data-w="70"></div></div></div>
      <div class="skill-item"><div class="skill-name"><span>MATLAB / Simulink</span><span class="skill-pct">68%</span></div><div class="skill-bar"><div class="skill-fill" data-w="68"></div></div></div>
    </div>
    <div class="skill-category reveal d2">
      <div class="skill-cat-title">Mekanik &amp; Otomasi</div>
      <div class="skill-item"><div class="skill-name"><span>Rancang Bangun Mesin</span><span class="skill-pct">82%</span></div><div class="skill-bar"><div class="skill-fill" data-w="82"></div></div></div>
      <div class="skill-item"><div class="skill-name"><span>CAD 3D / SolidWorks</span><span class="skill-pct">78%</span></div><div class="skill-bar"><div class="skill-fill" data-w="78"></div></div></div>
      <div class="skill-item"><div class="skill-name"><span>Sistem Otomasi Industri</span><span class="skill-pct">77%</span></div><div class="skill-bar"><div class="skill-fill" data-w="77"></div></div></div>
      <div class="skill-item"><div class="skill-name"><span>Dokumentasi Teknis</span><span class="skill-pct">88%</span></div><div class="skill-bar"><div class="skill-fill" data-w="88"></div></div></div>
    </div>
  </div>
</section>

<!-- ════════════ PROJECTS ════════════ -->
<section id="projects">
  <div class="section-header reveal">
    <span class="section-num">03 //</span>
    <h2 class="section-title">Proyek</h2>
    <div class="section-line"></div>
  </div>
  <div class="projects-grid">
    <div class="project-card reveal">
      <div class="project-img">
        <div class="project-img-bg bg1">🔐</div>
        <div class="project-overlay">▶ LIHAT DETAIL</div>
        <div class="project-badge badge-pbl">PBL PROJECT</div>
      </div>
      <div class="project-body">
        <div class="project-tags"><span class="tag">RFID</span><span class="tag">IoT</span><span class="tag">Mobile App</span><span class="tag">Keamanan</span></div>
        <div class="project-title">▸ Smart Locker — Sistem Loker Cerdas</div>
        <div class="project-desc">Loker pintar berbasis RFID yang memungkinkan akses menggunakan kartu/tag atau aplikasi seluler yang dikembangkan sendiri. Dirancang meningkatkan keamanan penyimpanan di kampus dan tempat umum.<br><br>Dibangun bersama tim Project Based Learning (PBL) dengan bimbingan dosen. Sistem terintegrasi penuh antara hardware RFID, mikrokontroler, dan aplikasi mobile.</div>
      </div>
      <div class="project-footer">
        <span class="proj-tag proj-done">◉ Selesai &amp; Berfungsi</span>
        <span class="proj-tag" style="color:var(--yellow);">★ Tim PBL</span>
      </div>
    </div>
    <div class="project-card reveal d1">
      <div class="project-img">
        <div class="project-img-bg bg2">🏭</div>
        <div class="project-overlay">▶ LIHAT DETAIL</div>
        <div class="project-badge badge-magang">MAGANG WMK</div>
      </div>
      <div class="project-body">
        <div class="project-tags"><span class="tag">Arduino</span><span class="tag">Konveyor</span><span class="tag">Otomasi</span><span class="tag">Industri</span></div>
        <div class="project-title">▸ FillFlow — Mesin Pengisi Cairan Otomatis</div>
        <div class="project-desc">Mesin pengisian dan penyegelan botol otomatis berbasis konveyor dan Arduino, dikembangkan selama Magang Wirausaha Merdeka di Bengkel Sinar Alam Jember.<br><br>Mencakup rancang bangun mesin, integrasi sistem otomasi, pengujian kinerja, dokumentasi teknis, dan dipresentasikan di pameran kewirausahaan bersama tim 10 orang.</div>
      </div>
      <div class="project-footer">
        <span class="proj-tag proj-done">◉ Dipamerkan</span>
        <span class="proj-tag proj-event">★ Wirausaha Merdeka 2024</span>
      </div>
    </div>
  </div>
</section>

<!-- ════════════ EXPERIENCE ════════════ -->
<section id="experience">
  <div class="section-header reveal">
    <span class="section-num">04 //</span>
    <h2 class="section-title">Pengalaman</h2>
    <div class="section-line"></div>
  </div>
  <div class="timeline">
    <div class="timeline-item reveal">
      <div class="tl-date">// Okt 2024 — Des 2024 · 3 Bulan &nbsp;|&nbsp; Bengkel Sinar Alam, Jember</div>
      <div class="tl-role">Magang Wirausaha Merdeka — Pengembangan Produk FillFlow</div>
      <div class="tl-company">Bengkel Sinar Alam · Magang · Di Lokasi</div>
      <div class="tl-desc">
        Mengembangkan <span class="hl">FillFlow</span> — mesin pengisi dan penyegel botol otomatis berbasis konveyor dan Arduino dalam program Wirausaha Merdeka.
        <ul class="tl-list">
          <li>Merancang dan membangun mesin FillFlow menggunakan teknologi mekatronika berbasis Arduino</li>
          <li>Mengintegrasikan sistem otomatisasi pengisian dan penyegelan cairan secara otomatis</li>
          <li>Melakukan pengujian dan evaluasi kinerja mesin secara menyeluruh</li>
          <li>Menyiapkan dokumentasi teknis dan presentasi produk untuk pameran kewirausahaan</li>
          <li>Berkolaborasi dengan pemilik bengkel dan mentor dalam pengembangan ide bisnis</li>
        </ul>
      </div>
    </div>
    <div class="timeline-item reveal d1">
      <div class="tl-date">// Sep 2024 — Des 2024 · 4 Bulan &nbsp;|&nbsp; Jember, Jawa Timur</div>
      <div class="tl-role">Peserta Wirausaha Merdeka 2024</div>
      <div class="tl-company">Politeknik Negeri Jember · Purnawaktu · Di Lokasi</div>
      <div class="tl-desc">
        Berpartisipasi penuh dalam program <span class="hl">Wirausaha Merdeka 2024</span> sebagai anggota tim pengembangan prototipe FillFlow.
        <ul class="tl-list">
          <li>Melakukan pemrograman dan debugging sensor serta aktuator agar berfungsi dengan benar</li>
          <li>Prototipe FillFlow berhasil beroperasi sukses pada pameran Wirausaha Merdeka</li>
          <li>Bekerja dalam tim 10 anggota di bidang desain, perakitan, dan pengujian</li>
        </ul>
      </div>
    </div>
    <div class="timeline-item reveal d2">
      <div class="tl-date">// Sep 2021 — Mar 2022 · 7 Bulan &nbsp;|&nbsp; Jember, Jawa Timur</div>
      <div class="tl-role">Asisten Teknis &amp; Administrasi</div>
      <div class="tl-company">PT PLN (Persero) · Magang · Di Lokasi</div>
      <div class="tl-desc">
        Magang di <span class="hl">PT PLN (Persero)</span> Jember — verifikasi data pelanggan, inspeksi meter listrik tiga fase, dan administrasi teknis.
        <ul class="tl-list">
          <li>Memverifikasi dan mencocokkan data pelanggan dengan Nomor Induk Kependudukan (NIK) di sistem PLN</li>
          <li>Memastikan akurasi data dan memperbaiki ketidaksesuaian dalam basis data pelanggan</li>
          <li>Melakukan inspeksi meter listrik tiga fase untuk memastikan pencatatan daya yang akurat</li>
          <li>Menghitung tingkat kesalahan pengukuran dan melaporkan temuan untuk perbaikan lebih lanjut</li>
          <li>Menjalankan tugas administratif: pencatatan data, penyusunan laporan resmi, dan dokumentasi</li>
        </ul>
      </div>
    </div>
    <div class="timeline-item reveal">
      <div class="tl-date">// Project Based Learning (PBL)</div>
      <div class="tl-role">Pengembang — Sistem Smart Locker</div>
      <div class="tl-company">Program PBL Kampus · Tim Kolaborasi</div>
      <div class="tl-desc">
        Bersama tim PBL, merancang dan membangun <span class="hl">Smart Locker</span> — loker pintar berbasis RFID dan aplikasi mobile untuk keamanan penyimpanan di kampus.
        <ul class="tl-list">
          <li>Mengembangkan sistem keamanan berbasis RFID dengan kartu/tag akses otomatis</li>
          <li>Mengintegrasikan aplikasi seluler untuk kontrol loker secara nirkabel</li>
          <li>Berkolaborasi dalam tim lintas disiplin dengan bimbingan langsung dari dosen</li>
          <li>Menghadirkan solusi inovatif yang berdampak nyata di lingkungan kampus</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- ════════════ EDUCATION ════════════ -->
<section id="education">
  <div class="section-header reveal">
    <span class="section-num">05 //</span>
    <h2 class="section-title">Pendidikan</h2>
    <div class="section-line"></div>
  </div>
  <div class="timeline">
    <div class="timeline-item reveal">
      <div class="tl-date">// Agu 2023 — Sekarang</div>
      <div class="tl-role">D4 — Teknologi Rekayasa Mekatronika</div>
      <div class="tl-company">Politeknik Negeri Jember (POLIJE)</div>
      <div class="tl-desc">
        <div class="edu-badge">Aktif — Semester 2</div><br>
        <div class="edu-ipk">
          <div class="edu-ipk-val">3.83</div>
          <div class="edu-ipk-label">Indeks Prestasi<br>Kumulatif</div>
        </div>
        Menempuh pendidikan di Fakultas Teknik, mempelajari integrasi sistem mekanik, elektronik, dan kendali untuk menciptakan solusi teknologi inovatif.
        <ul class="tl-list">
          <li>Mempelajari sistem mekatronika: integrasi mekanik, elektronika, dan sistem kendali</li>
          <li>Aktif dalam kegiatan praktikum berbasis proyek (Project Based Learning)</li>
          <li>Meraih IPK <span class="hl">3.83</span> sebagai bukti komitmen akademis yang tinggi</li>
        </ul>
      </div>
    </div>
    <div class="timeline-item reveal d1">
      <div class="tl-date">// 2020 — 2023</div>
      <div class="tl-role">Rekayasa Perangkat Lunak (RPL)</div>
      <div class="tl-company">SMKN 03 Jember</div>
      <div class="tl-desc">
        Lulusan SMKN 3 Jember jurusan Rekayasa Perangkat Lunak. Tiga tahun mendalami bahasa pemrograman dan konsep pengembangan perangkat lunak sebagai fondasi karier teknologi.
        <ul class="tl-list">
          <li>Menguasai berbagai bahasa pemrograman dan konsep pengembangan aplikasi</li>
          <li>Merancang, membangun, dan menguji aplikasi yang efisien dan inovatif</li>
          <li>Aktif terlibat dalam proyek tim dan individu yang menuntut kreativitas teknis</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- ════════════ CONTACT ════════════ -->
<section id="contact">
  <div class="section-header reveal" style="justify-content:center;flex-direction:column;align-items:center;gap:10px;">
    <span class="section-num">06 //</span>
    <h2 class="section-title">Hubungi Saya</h2>
  </div>
  <p class="contact-intro reveal">
    &gt; Punya proyek menarik atau ingin berkolaborasi?<br>
    &gt; Saya terbuka untuk diskusi dan peluang baru.<br>
    &gt; Mari <span class="hl">terhubung</span> dan ciptakan sesuatu yang luar biasa!
  </p>
  <div class="contact-grid reveal">
    <a href="mailto:hardiantoputra789@gmail.com" class="contact-card">
      <div class="cc-icon">📧</div><div class="cc-label">Email</div>
      <div class="cc-val">hardiantoputra789@gmail.com</div>
    </a>
    <a href="https://www.linkedin.com/in/hardianto-putra-pratama-6b0075273" target="_blank" class="contact-card">
      <div class="cc-icon">💼</div><div class="cc-label">LinkedIn</div>
      <div class="cc-val">Hardianto Putra Pratama</div>
    </a>
    <a href="https://wa.me/6285651140067" target="_blank" class="contact-card">
      <div class="cc-icon">📱</div><div class="cc-label">WhatsApp</div>
      <div class="cc-val">+62 856-5114-0067</div>
    </a>
  </div>
  <div class="reveal" style="text-align:center;">
    <a href="mailto:hardiantoputra789@gmail.com" class="btn btn-primary">◈ Kirim Pesan</a>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <p>// <span>HARDIANTO PUTRA PRATAMA</span> &copy; 2025</p>
  <p>POLITEKNIK NEGERI JEMBER · TEKNOLOGI REKAYASA <span>MEKATRONIKA</span></p>
</footer>

<script>
/* CURSOR */
const cursor=document.getElementById('cursor'),ring=document.getElementById('cursorRing');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;cursor.style.left=mx+'px';cursor.style.top=my+'px';});
(function l(){rx+=(mx-rx)*.13;ry+=(my-ry)*.13;ring.style.left=rx+'px';ring.style.top=ry+'px';requestAnimationFrame(l);})();
document.querySelectorAll('a,button,.project-card,.stat-card,.contact-card,.skill-category,.timeline-item').forEach(el=>{
  el.addEventListener('mouseenter',()=>{cursor.style.transform='translate(-50%,-50%) scale(2.2)';ring.style.transform='translate(-50%,-50%) scale(1.6)';ring.style.borderColor='var(--yellow)';});
  el.addEventListener('mouseleave',()=>{cursor.style.transform='translate(-50%,-50%) scale(1)';ring.style.transform='translate(-50%,-50%) scale(1)';ring.style.borderColor='var(--cyan)';});
});

/* REVEAL */
const ro=new IntersectionObserver(e=>e.forEach(x=>{if(x.isIntersecting){x.target.classList.add('visible');ro.unobserve(x.target);}}),{threshold:0.1});
document.querySelectorAll('.reveal').forEach(el=>ro.observe(el));

/* SKILL BARS */
const so=new IntersectionObserver(e=>e.forEach(x=>{if(x.isIntersecting){setTimeout(()=>x.target.querySelectorAll('.skill-fill').forEach(f=>f.style.width=f.dataset.w+'%'),350);so.unobserve(x.target);}}),{threshold:0.3});
document.querySelectorAll('.skill-category').forEach(el=>so.observe(el));

/* PARALLAX */
document.addEventListener('mousemove',e=>{
  const g=document.getElementById('heroGrid');if(!g)return;
  const x=(e.clientX/innerWidth-.5)*14,y=(e.clientY/innerHeight-.5)*7;
  g.style.transform=`perspective(700px) rotateX(${14+y}deg) rotateY(${x*.3}deg)`;
});

/* ACTIVE NAV */
const secs=document.querySelectorAll('section[id]');
window.addEventListener('scroll',()=>{
  const sy=window.scrollY+80;
  secs.forEach(s=>{
    const t=s.offsetTop,b=t+s.offsetHeight;
    const lk=document.querySelector(`.nav-links a[href="#${s.id}"]`);
    if(lk)lk.classList.toggle('active',sy>=t&&sy<b);
  });
  document.getElementById('navbar').style.background=window.scrollY>10?'rgba(2,2,6,0.99)':'rgba(3,3,8,0.97)';
});

/* GLITCH */
(function g(){
  document.querySelectorAll('.glitch').forEach(el=>{if(Math.random()>.65){el.style.filter='hue-rotate(55deg) brightness(1.4)';setTimeout(()=>el.style.filter='',70+Math.random()*100);}});
  setTimeout(g,2800+Math.random()*3500);
})();
</script>
</body>
</html>
