[index.html](https://github.com/user-attachments/files/33008380/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Space Rocks — FTC Team 15303</title>
<link rel="preload" href="/fonts/syne-latin.woff2" as="font" type="font/woff2" crossorigin>
<style>
@font-face{font-family:"Syne";font-style:normal;font-weight:400 800;font-display:swap;src:url(/fonts/syne-latin.woff2) format("woff2")}
:root{--bg:#fffafc;--panel:#ffe8f1;--ink:#2b1020;--pink:#e6007e;--rose:#ff4fa3;--blush:#ff9ccb;--berry:#b0125c;--mut:#8a5f74;--line:#f5c6da;--disp:"Helvetica Neue",Helvetica,Arial,system-ui,sans-serif;--body:system-ui,-apple-system,"Segoe UI",sans-serif}
*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth;scroll-padding-top:64px}
body{background:var(--bg);color:var(--ink);font:1rem/1.6 var(--body);overflow-x:hidden}
a{color:inherit}
:focus-visible{outline:2px solid var(--pink);outline-offset:3px}
.lbl{font:600 .72rem/1 var(--body);letter-spacing:.2em;text-transform:uppercase;color:var(--pink)}
.big{font:500 clamp(3rem,13vw,11rem)/.86 "Syne",var(--disp);letter-spacing:-.03em;}
.h2{font:300 clamp(2.4rem,8vw,6rem)/.9 var(--disp);letter-spacing:-.03em;}
.outline{color:transparent;-webkit-text-stroke:1.5px var(--ink)}
.wrap{max-width:1200px;margin:auto;padding:0 24px}
section{padding:110px 0 40px;position:relative}
.btn{display:inline-flex;gap:10px;align-items:center;padding:14px 26px;border:1px solid var(--ink);font:700 .8rem var(--body);letter-spacing:.14em;text-transform:uppercase;text-decoration:none;background:none;color:var(--ink);cursor:pointer;transition:.25s}
.btn span{transition:transform .25s}.btn:hover span{transform:translateX(6px)}
.btn:hover{background:var(--ink);color:var(--bg)}
.btn.hot{background:var(--pink);border-color:var(--pink);color:var(--bg)}
.ul{text-decoration:none;background:linear-gradient(currentColor,currentColor) 0 100%/0 1px no-repeat;transition:background-size .3s}.ul:hover{background-size:100% 1px}
/* nav */
header{position:fixed;inset:0 0 auto;z-index:70;mix-blend-mode:normal;background:linear-gradient(var(--bg),transparent)}
.nav{display:flex;justify-content:space-between;align-items:center;gap:12px;height:64px}
.nav .logo{white-space:nowrap;flex:none}
.nav>div{flex:none;white-space:nowrap}
.logo{font:600 1.1rem "Syne",var(--disp);letter-spacing:.08em;text-decoration:none}
.menu{display:flex;gap:26px;align-items:center;font-size:.78rem;letter-spacing:.14em;text-transform:uppercase}
.menu a{text-decoration:none;color:var(--mut)}.menu a:hover{color:var(--pink)}
#bg{display:block;flex:none;white-space:nowrap;background:none;border:1px solid var(--line);color:#fff;padding:6px 12px;cursor:pointer;font:700 .75rem var(--body);letter-spacing:.14em}
@media(max-width:860px){.menu{display:none;position:absolute;top:64px;left:0;right:0;flex-direction:column;align-items:flex-start;background:var(--bg);padding:24px;border-bottom:1px solid var(--line);gap:18px}.menu.open{display:flex}}
/* hero */
#hero{min-height:100vh;display:flex;flex-direction:column;justify-content:flex-end;padding:0 0 60px;overflow:hidden}
#orbit{position:absolute;inset:0;width:100%;height:100%;z-index:0}
#hero .wrap{position:relative;z-index:1;width:100%}
.meta{display:flex;gap:28px;flex-wrap:wrap;margin:26px 0}
.meta div{font-size:.78rem;letter-spacing:.14em;text-transform:uppercase;color:var(--mut)}.meta b{display:block;color:var(--ink)}
#hero .big{transition:transform .2s}
.grad{background:linear-gradient(90deg,var(--pink),var(--blush),var(--berry));-webkit-background-clip:text;background-clip:text;color:transparent}
.marq{overflow:hidden;background:var(--pink);padding:14px 0;margin-top:70px;white-space:nowrap}
.marq div{display:inline-block;animation:mq 30s linear infinite;font:300 1.6rem var(--disp);letter-spacing:.1em;color:#fff}
@keyframes mq{to{transform:translateX(-50%)}}
/* about */
.two{display:grid;grid-template-columns:1.1fr 1fr;gap:60px;align-items:start}
@media(max-width:860px){.two{grid-template-columns:1fr;gap:30px}}
.stats{display:flex;gap:40px;flex-wrap:wrap;margin-top:40px;border-top:1px solid var(--line);padding-top:24px}
.stat b{display:block;font:300 clamp(2.4rem,6vw,4rem)/1 var(--disp)}.stat span{font-size:.72rem;letter-spacing:.16em;color:var(--mut);text-transform:uppercase}
.fact{border-left:2px solid var(--pink);padding:2px 0 2px 18px;margin-bottom:22px;color:#5c3a4d}
.src{font-size:.7rem;color:var(--mut);margin-top:30px}.src a{color:var(--pink)}
/* process */
.strip{display:flex;gap:0;overflow-x:auto;scroll-snap-type:x mandatory;margin-top:40px;border-block:1px solid var(--line)}
.step{flex:0 0 min(78vw,340px);scroll-snap-align:start;padding:36px 28px 40px;border-right:1px solid var(--line);transition:background .3s}
.step:hover{background:var(--panel)}
.step i{font:300 4.5rem/1 var(--disp);font-style:normal;color:transparent;-webkit-text-stroke:1px var(--rose)}
.step h3{font:300 2.2rem/1 var(--disp);margin:10px 0}
.step p{color:var(--mut);font-size:.92rem}
/* seasons */
#seasons{background:var(--panel);transition:background .6s}
.years{display:flex;gap:6px;overflow-x:auto;margin:34px 0;padding-bottom:6px}
.yr{flex:0 0 auto;background:none;border:0;border-bottom:2px solid var(--line);color:var(--mut);font:300 1.6rem var(--disp);padding:6px 14px;cursor:pointer;transition:.25s}
.yr:hover{color:var(--ink)}.yr[aria-selected=true]{color:var(--pink);border-color:var(--pink);transform:translateY(-4px)}
.stage{display:grid;grid-template-columns:1fr 1fr;gap:50px;min-height:380px}
@media(max-width:860px){.stage{grid-template-columns:1fr}}
.stage .yrbig{font:300 clamp(5rem,20vw,14rem)/.8 var(--disp);color:transparent;-webkit-text-stroke:1.5px var(--blush);letter-spacing:-.05em}
.stage .game{font:300 clamp(2rem,6vw,4.5rem)/.9 var(--disp);margin-top:12px}
.swap{animation:swap .6s cubic-bezier(.2,.8,.2,1)}
@keyframes swap{from{opacity:0;transform:translateY(30px) skewY(2deg)}to{opacity:1;transform:none}}
dl{display:grid;gap:0}
dl div{display:grid;grid-template-columns:120px 1fr;gap:14px;padding:14px 0;border-bottom:1px solid var(--line)}
dt{font:600 .72rem var(--body);letter-spacing:.18em;text-transform:uppercase;color:var(--pink)}dd{color:#5c3a4d}
.ph{color:var(--mut);font-style:italic}
.act{border:1px solid var(--pink);padding:30px;margin-top:40px;display:grid;grid-template-columns:1fr 1fr;gap:10px 40px}
@media(max-width:700px){.act{grid-template-columns:1fr}}
.act .row{display:flex;justify-content:space-between;border-bottom:1px dashed var(--line);padding:10px 0;font-size:.85rem;letter-spacing:.12em;text-transform:uppercase}
.tag{color:var(--berry);font-weight:700}
/* timeline */
.tl{margin-top:36px;border-left:1px solid var(--line)}
.tl div{padding:0 0 28px 28px;position:relative}
.tl div::before{content:"";position:absolute;left:-5px;top:8px;width:9px;height:9px;background:var(--pink);border-radius:50%}
.tl div:first-child::before{background:var(--berry);box-shadow:0 0 14px var(--berry)}
.tl h3{font:300 1.7rem var(--disp);}.tl p{color:var(--mut);font-size:.9rem}
/* sponsors */
.sp{display:grid;grid-template-columns:140px 1fr;gap:20px;padding:22px 0;border-top:1px solid var(--line);align-items:center}
.sp em{font:300 1.1rem var(--disp);letter-spacing:.1em;font-style:normal}
.sp span{color:var(--mut)}.sp b{font:300 2rem var(--disp);}
.tiers{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;background:var(--line);border:1px solid var(--line)}
@media(max-width:1020px){.tiers{grid-template-columns:repeat(2,1fr)}}
@media(max-width:560px){.tiers{grid-template-columns:1fr}}
.tier{padding:26px;background:#fff;display:flex;flex-direction:column;gap:14px;min-width:0}
.tier header{display:flex;align-items:baseline;gap:10px;border-bottom:2px solid var(--tc,var(--pink));padding-bottom:10px}
.tier header{min-height:3.4rem;align-items:flex-end}
@media(max-width:560px){.tier header{min-height:0}}
.tier header em{font:500 1.3rem/1.15 var(--disp);font-style:normal;letter-spacing:.04em}
.tier header small{font:600 .8rem var(--body);letter-spacing:.12em;text-transform:uppercase;color:var(--ink)}
.tier .amt{font:500 clamp(2.4rem,5vw,3.4rem)/1 var(--disp);letter-spacing:-.03em;color:var(--tc,var(--pink))}
.tier p.who{margin-top:auto;font:300 1.4rem/1.2 var(--disp);color:var(--ink)}
.t-gold{--tc:#c9a227}.t-silver{--tc:#9aa3ad}.t-bronze{--tc:#b06f3c}.t-total{--tc:var(--pink)}
/* forms */
form{display:grid;gap:18px;max-width:560px}
label{font-size:.7rem;letter-spacing:.18em;text-transform:uppercase;color:var(--mut)}
input,select,textarea{width:100%;background:none;border:0;border-bottom:1px solid var(--line);color:var(--ink);font:inherit;padding:10px 0;border-radius:0}
select option{background:var(--panel)}
input:focus,select:focus,textarea:focus{outline:none;border-color:var(--pink)}
.msg{color:var(--pink);min-height:1.5em;font-size:.9rem}
footer{margin-top:100px;border-top:1px solid var(--line);padding:60px 0 30px;overflow:hidden}
footer .big{font-size:clamp(4rem,22vw,20rem)}
.fl{display:flex;gap:26px;flex-wrap:wrap;margin:30px 0;font-size:.8rem;letter-spacing:.14em;text-transform:uppercase}
.fine{color:var(--mut);font-size:.72rem;letter-spacing:.14em}

.two.top{align-items:start}
.roles{display:grid;grid-template-columns:repeat(auto-fill,minmax(210px,1fr));margin-top:30px;border-top:1px solid var(--line)}
.roles div{padding:22px 18px 26px 0;border-bottom:1px solid var(--line)}
.roles h3{font:300 1.7rem var(--disp);color:var(--pink)}.roles p{color:var(--mut);font-size:.9rem}
table{width:100%;border-collapse:collapse;margin-top:30px;font-size:.92rem}
th{text-align:left;font:600 .7rem var(--body);letter-spacing:.18em;text-transform:uppercase;color:var(--pink);padding:10px 12px 10px 0;border-bottom:2px solid var(--pink)}
td{padding:14px 12px 14px 0;border-bottom:1px solid var(--line);vertical-align:top;color:#5c3a4d}td:first-child{font-weight:700;color:var(--ink);white-space:nowrap}
.tw{overflow-x:auto}
.join{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:0;margin:30px 0;border:1px solid var(--line)}
.join div{padding:26px;border-right:1px solid var(--line);background:#fff}.join h3{font:300 1.6rem var(--disp);margin-bottom:8px}.join p{color:var(--mut);font-size:.9rem}
details{border-bottom:1px solid var(--line);padding:16px 0}summary{cursor:pointer;font-weight:700;list-style:none;display:flex;justify-content:space-between}summary::after{content:"+";color:var(--pink);font-size:1.4rem;line-height:1}details[open] summary::after{content:"–"}details p{color:#5c3a4d;margin-top:10px;max-width:640px}

#bg{display:block!important;font:500 .72rem var(--body);letter-spacing:.16em;text-transform:uppercase;padding:9px 18px;border:1px solid var(--ink);color:var(--ink);background:none;cursor:pointer}
@media(max-width:600px){.nav .dsk{padding:7px 12px!important;font-size:.7rem}.nav .logo{font-size:.95rem}}
#ov{position:fixed;inset:0;z-index:60;background:var(--pink);color:#fff;padding:96px 24px 28px;display:flex;flex-direction:column;justify-content:space-between;visibility:hidden;clip-path:circle(0 at 100% 0);transition:clip-path .7s cubic-bezier(.7,0,.2,1),visibility 0s .7s;overflow:auto}
#ov.open{visibility:visible;clip-path:circle(150% at 100% 0);transition:clip-path .7s cubic-bezier(.7,0,.2,1),visibility 0s}
#ov nav{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:0 30px}
#ov nav a{font:300 clamp(2rem,5.5vw,3.8rem)/1.2 var(--disp);letter-spacing:-.03em;text-decoration:none;transition:opacity .3s,transform .3s}
#ov nav:hover a,#ov nav:focus-within a{opacity:.4}#ov nav a:hover,#ov nav a:focus{opacity:1;transform:translateX(14px)}
#load{position:fixed;inset:0;z-index:200;background:var(--pink);color:#fff;display:flex;flex-direction:column;justify-content:flex-end;padding:28px;transition:transform .9s cubic-bezier(.7,0,.2,1)}
#load.done{transform:translateY(-100%)}#load b{font:300 clamp(6rem,26vw,20rem)/.8 var(--disp);letter-spacing:-.06em}
#prog{position:fixed;top:0;left:0;height:2px;width:0;background:var(--pink);z-index:80}
#bot{position:absolute;left:0;top:0;width:30px;height:40px;border:2px solid var(--pink);background:#fff;border-radius:6px;z-index:2;pointer-events:none;will-change:transform}
#bot::before,#bot::after{content:"";position:absolute;top:4px;bottom:4px;width:5px;background:var(--ink);border-radius:2px}#bot::before{left:-8px}#bot::after{right:-8px}
#bot b{position:absolute;top:-2px;left:6px;right:6px;height:4px;background:var(--pink)}
.pix{position:absolute;width:12px;height:12px;background:var(--pink);border-radius:2px;pointer-events:none;z-index:1;animation:pop 1.8s forwards}
@keyframes pop{0%{transform:translate(-50%,-50%) rotate(45deg) scale(0)}15%{transform:translate(-50%,-50%) rotate(45deg) scale(1.5)}30%{transform:translate(-50%,-50%) rotate(45deg) scale(1)}100%{transform:translate(-50%,-150%) rotate(45deg);opacity:0}}
.pts{position:absolute;z-index:3;pointer-events:none;font:700 1rem var(--body);color:var(--pink);transform:translate(-50%,-50%);animation:rise 1s forwards}.pts.miss{color:var(--mut);font-weight:500}
@keyframes rise{to{transform:translate(-50%,-220%);opacity:0}}
#troph{position:absolute;right:24px;top:108px;z-index:2;display:flex;gap:4px;flex-wrap:wrap;justify-content:flex-end;max-width:260px;font-size:1.1rem}
#troph span{position:relative}#troph small{position:absolute;bottom:-12px;left:50%;transform:translateX(-50%);font:600 .55rem var(--body);color:var(--mut)}
#toast{position:absolute;left:50%;top:90px;z-index:3;transform:translate(-50%,-20px);opacity:0;pointer-events:none;background:var(--ink);color:#fff;padding:10px 18px;font:600 .75rem var(--body);letter-spacing:.14em;text-transform:uppercase;transition:.4s}#toast.on{opacity:1;transform:translate(-50%,0)}
.score{position:absolute;right:24px;top:84px;z-index:2;font:500 .7rem var(--body);letter-spacing:.14em;text-transform:uppercase;color:var(--mut)}.score span{color:var(--pink);font-size:1rem}
.split2{display:flex;height:70vh;min-height:420px;border-block:1px solid var(--line)}
.split2 a{flex:1;display:flex;flex-direction:column;justify-content:flex-end;gap:6px;padding:30px;text-decoration:none;border-right:1px solid var(--line);transition:flex .7s cubic-bezier(.2,.8,.2,1),background .4s,color .4s}
.split2 a:last-child{border:0}.split2 a:hover,.split2 a:focus-visible{flex:2;background:var(--pink);color:#fff}
.split2 b{font:300 clamp(3rem,9vw,8rem)/.9 var(--disp);letter-spacing:-.05em}
@media(max-width:700px){.split2{flex-direction:column;height:auto}.split2 a{min-height:220px}}
.cubewrap{perspective:900px;height:340px;display:grid;place-items:center;cursor:grab;touch-action:pan-y;user-select:none}
.cube{width:200px;height:200px;position:relative;transform-style:preserve-3d}
.cube div{position:absolute;inset:0;border:1px solid var(--pink);background:rgba(255,250,252,.9);display:grid;place-items:center;text-align:center;padding:16px;font:400 1rem/1.3 var(--disp)}
.f1{transform:translateZ(100px)}.f2{transform:rotateY(90deg) translateZ(100px)}.f3{transform:rotateY(180deg) translateZ(100px)}.f4{transform:rotateY(-90deg) translateZ(100px)}.f5{transform:rotateX(90deg) translateZ(100px)}.f6{transform:rotateX(-90deg) translateZ(100px)}
@media(min-width:861px){#hz{width:100vw;margin-left:calc(50% - 50vw)}.hst{position:sticky;top:0;height:100vh;display:flex;align-items:center;overflow:hidden}.hst .strip{overflow:visible;scroll-snap-type:none;border:0;margin:0;padding:0 24px;will-change:transform}.step{flex:0 0 360px;min-height:340px;border:1px solid var(--line);margin-right:-1px}}
.w{display:inline-block;overflow:hidden;vertical-align:top;padding-bottom:.12em}.w>span{display:inline-block;transform:translateY(108%);transition:transform .9s cubic-bezier(.2,.8,.2,1)}.in .w>span{transform:none}
.h2 .grad{background:none;-webkit-background-clip:initial;color:inherit}.h2 .grad .w>span{background:linear-gradient(90deg,var(--pink),var(--rose),var(--berry));-webkit-background-clip:text;background-clip:text;color:transparent}
.roles:hover div{opacity:.4;transition:opacity .3s}.roles div:hover{opacity:1}
.yr[aria-selected=true]{font-weight:500}
#cur{display:none;place-items:center;font:600 .6rem var(--body);letter-spacing:.12em;text-transform:uppercase;color:#fff}
#cur.hov{width:46px;height:46px;background:rgba(230,0,126,.25)}#cur.lab{width:80px;height:80px;background:var(--pink)}
/* reveal + cursor */
.rv{opacity:0;transform:translateY(40px);transition:opacity .9s,transform .9s cubic-bezier(.2,.8,.2,1)}.rv.in{opacity:1;transform:none}
#cur{position:fixed;width:14px;height:14px;border-radius:50%;background:var(--pink);pointer-events:none;z-index:99;transform:translate(-50%,-50%);transition:width .2s,height .2s,background .2s;display:none}

@media(hover:hover) and (pointer:fine){#cur.on{display:grid}}
@media(prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important;scroll-behavior:auto!important}.rv{opacity:1;transform:none}}
</style>
</head>
<body>
<noscript><link rel="preload" href="/fonts/syne-latin.woff2" as="font" type="font/woff2" crossorigin>
<style>
@font-face{font-family:"Syne";font-style:normal;font-weight:400 800;font-display:swap;src:url(/fonts/syne-latin.woff2) format("woff2")}#load{display:none}</style></noscript>
<div id="load" aria-hidden="true"><p class="lbl" style="color:#fff;margin-bottom:12px">Loading Space Rocks</p><b id="ln">0</b></div>
<div id="prog" aria-hidden="true"></div>
<div id="cur" aria-hidden="true"></div>
<header><div class="wrap nav">
<a class="logo" href="#hero">SPACE ROCKS</a>
<div style="display:flex;gap:12px;align-items:center"><a class="btn hot dsk" style="padding:9px 18px" href="#contact">Connect <span>→</span></a><button id="bg" aria-expanded="false" aria-controls="ov">Menu</button></div></div></header>
<div id="ov" aria-label="Menu"><nav aria-label="Main">
<a href="#about" data-p="Who we are">About</a><a href="#ftc" data-p="What FIRST Tech Challenge is, and who is on a team">The program</a><a href="#spin" data-p="Drag to turn the build over">Spin the build</a><a href="#build" data-p="Build, test, fail, learn, iterate">Engineering</a><a href="#seasons" data-p="2018 to now">Seasons</a><a href="#record" data-p="Verified results with sources">Record</a><a href="#news" data-p="Stay in orbit">Newsletter</a><a href="#events" data-p="What is next">Events</a><a href="#sponsors" data-p="Powering the next generation">Sponsors</a><a href="#join" data-p="Students, parents, engineers, sponsors">Join</a><a href="#contact" data-p="Say hello">Contact</a>
</nav><div><p id="ovp" class="lbl" style="color:#fff;min-height:1em">Space Rocks · FTC 15303</p><p style="margin-top:14px"><a class="ul" style="color:#fff" href="https://sites.google.com/d/1IJrwvnLNJUbaQXfs8Zcpbo0CiUaQnzEQ/p/1g_2HXlOytMigezkTcSSX6GWBXslTyED1/edit" target="_blank" rel="noopener">Parent Hub ↗</a></p></div></div>

<main>
<section id="hero">
<canvas id="orbit" aria-hidden="true"></canvas>
<div id="bot" aria-hidden="true"><b></b></div>
<div class="score" aria-hidden="true">Aim for the planet · inner rings score more · <span id="sc">0</span></div>
<div id="troph" aria-label="Trophies earned"></div>
<div id="toast" role="status"></div>
<div class="wrap">
<p class="lbl">FTC Team 15303 · Arcadia, California</p>
<h1 class="big" id="hTitle">Space<br><span class="grad">Rocks</span></h1>
<div class="meta"><div>Rookie year<b>2018</b></div><div>Region<b>Los Angeles, CA</b></div><div>League<b>SoCal C1</b></div></div>
<p style="max-width:520px;color:#5c3a4d;margin-bottom:28px">Engineering the future of robotics in Southern California.</p>
<div style="display:flex;gap:14px;flex-wrap:wrap">
<a class="btn hot" href="#contact">Join / Contact Us <span>→</span></a>
<a class="btn" href="#sponsors">Support / Sponsor Us <span>→</span></a>
<a class="btn" href="https://sites.google.com/d/1IJrwvnLNJUbaQXfs8Zcpbo0CiUaQnzEQ/p/1g_2HXlOytMigezkTcSSX6GWBXslTyED1/edit" target="_blank" rel="noopener">Parent Hub <span>↗</span></a>
</div>
</div>
<div class="marq" aria-hidden="true"><div>FTC 15303 — SPACE ROCKS — ROBOTICS — ENGINEERING — SOUTHERN CALIFORNIA — FTC 15303 — SPACE ROCKS — ROBOTICS — ENGINEERING — SOUTHERN CALIFORNIA — </div></div>
</section>

<section id="about"><div class="wrap two">
<div class="rv"><p class="lbl">01 / Who we are</p>
<h2 class="h2" style="margin-top:14px">Who are<br><span class="outline">Space Rocks?</span></h2>
<div class="stats">
<div class="stat"><b data-n="15303">15303</b><span>FTC team</span></div>
<div class="stat"><b data-n="2018">2018</b><span>Rookie year</span></div>
<div class="stat"><b>10–5–0</b><span>Qual record, 2022 official events</span></div>
</div></div>
<div class="rv">
<div class="fact">A youth robotics team in Southern California, created in August 2018 as part of MajorStem.org.</div>
<div class="fact">Students build communication, collaboration, teamwork and leadership skills alongside engineering.</div>
<div class="fact">Supported by the Haas Foundation, Xin Wang and our community of families and alumni.</div>
<a class="btn" href="https://sites.google.com/d/1IJrwvnLNJUbaQXfs8Zcpbo0CiUaQnzEQ/p/1g_2HXlOytMigezkTcSSX6GWBXslTyED1/edit" target="_blank" rel="noopener">Our parent organization <span>↗</span></a>
<p class="src">Sources: <a href="https://robotics.majorstem.org/" target="_blank" rel="noopener">robotics.majorstem.org</a> · <a href="https://ftc-events.firstinspires.org/2022/team/15303" target="_blank" rel="noopener">FTC Events</a>. Add verified seasons, event and award counts as you confirm them.</p>
</div></div></section>

<section id="paths" style="padding-top:60px"><div class="split2">
<a href="#record" data-cur="Go"><small class="lbl" style="color:inherit">Results</small><b>On the field</b><span>Matches, events and the record.</span></a>
<a href="#join" data-cur="Go"><small class="lbl" style="color:inherit">People</small><b>Beyond the field</b><span>Mentors, sponsors and community.</span></a>
</div></section>

<section id="ftc"><div class="wrap">
<p class="lbl rv">02 / The program</p>
<h2 class="h2 rv" style="margin-top:14px">What is<br><span class="grad">FIRST Tech Challenge?</span></h2>
<div class="two top" style="margin-top:34px">
<p class="rv" style="color:#5c3a4d">FIRST Tech Challenge (FTC) is a nationwide robotics competition for middle and high school students (grades 7–12). Teams of up to 15 students design, build and program a robot to score points in a game that changes every season.</p>
<div class="rv"><div class="fact">Space Rocks competes in the California – Los Angeles region, in SoCal League C1.</div>
<div class="fact">Our robots use the REV Robotics kit plus parts we make in-house, and we design in CAD (OnShape).</div>
<div class="fact">Every season is a new game, a new robot and a new set of lessons.</div></div></div>
<h3 class="h2 rv" style="font-size:clamp(1.8rem,5vw,3.4rem);margin-top:70px">More than <span class="outline">a robot.</span></h3>
<div class="roles rv">
<div><h3>Engineers</h3><p>Design and build the mechanisms that make the robot work.</p></div>
<div><h3>Programmers</h3><p>Write the code for autonomous and driver-controlled play.</p></div>
<div><h3>Designers</h3><p>Model parts in CAD, 3D print them and shape how the team looks.</p></div>
<div><h3>Drivers</h3><p>Operate the robot in matches and practice until it is second nature.</p></div>
<div><h3>Strategists</h3><p>Scout, plan and decide how to score the most points.</p></div>
<div><h3>Outreach leaders</h3><p>Bring STEM to the community through workshops and events.</p></div>
<div><h3>Mentors</h3><p>Adults and professionals who guide, review and encourage.</p></div>
</div></div></section>

<section id="spin"><div class="wrap two">
<div class="rv"><p class="lbl">03 / Spin the build</p>
<h2 class="h2" style="margin-top:14px">Pick it up.<br><span class="grad">Turn it over.</span></h2>
<p style="margin-top:22px;color:#5c3a4d;max-width:420px">Drag the block to rotate it. Each face is something we use to build our robots.</p></div>
<div class="cubewrap" id="cw" data-cur="Drag" aria-label="Rotatable block listing our build materials"><div class="cube" id="cube">
<div class="f1">Mecanum drivetrain</div><div class="f2">REV motors and controllers</div><div class="f3">3D-printed and cut parts</div><div class="f4">REV extrusions</div><div class="f5">Designed in CAD (OnShape)</div><div class="f6 ph">Add your robot photo</div>
</div></div></div></section>

<section id="build"><div class="wrap">
<p class="lbl rv">04 / Engineering</p>
<h2 class="h2 rv" style="margin-top:14px">We don't just build.<br><span class="grad">We iterate.</span></h2>
<p class="rv" style="max-width:560px;margin-top:22px;color:#5c3a4d">Our robots use the REV Robotics kit plus parts we make in-house with 3D printing and cutting, so we can prototype fast. Drivetrains run mecanum wheels on REV motors, controllers and extrusions.</p>
<div id="hz"><div class="hst"><div class="strip" tabindex="0" aria-label="Engineering process, scroll horizontally">
<div class="step"><i>01</i><h3>Build</h3><p>Rapid prototypes from REV parts and in-house prints. <span class="ph">Add photo.</span></p></div>
<div class="step"><i>02</i><h3>Test</h3><p class="ph">Add a real test: what you measured.</p></div>
<div class="step"><i>03</i><h3>Fail</h3><p class="ph">Add a real failure and what broke.</p></div>
<div class="step"><i>04</i><h3>Learn</h3><p class="ph">What the failure taught you.</p></div>
<div class="step"><i>05</i><h3>Iterate</h3><p class="ph">Add before / after CAD (OnShape).</p></div>
<div class="step"><i>06</i><h3>Compete</h3><p class="ph">Link match results.</p></div>
<div class="step"><i>07</i><h3>Share</h3><p class="ph">Link outreach and mentoring.</p></div>
</div></div></div></div></section>

<section id="seasons"><div class="wrap">
<p class="lbl">05 / Season archive</p>
<h2 class="h2" style="margin-top:14px">Every season.<br><span class="outline">Every robot.</span></h2>
<div class="years" role="tablist" aria-label="Seasons" id="years"></div>
<div class="stage" id="stage" aria-live="polite"></div>
<div class="act">
<div class="lbl" style="grid-column:1/-1">Active season · 2026–2027 <span class="tag">● LIVE</span></div>
<div class="row"><span>Robot</span><span class="ph">set status</span></div>
<div class="row"><span>CAD</span><span class="ph">set status</span></div>
<div class="row"><span>Software</span><span class="ph">set status</span></div>
<div class="row"><span>Autonomous</span><span class="ph">set status</span></div>
<div class="row"><span>Driver practice</span><span class="ph">set status</span></div>
<div class="row"><span>Outreach</span><span class="ph">set status</span></div>
</div></div></section>

<section id="record"><div class="wrap">
<p class="lbl rv">06 / Competition record</p>
<h2 class="h2 rv" style="margin-top:14px">On the <span class="grad">field.</span></h2>
<div class="tw rv"><table><thead><tr><th>When</th><th>Event</th><th>Detail</th><th>Source</th></tr></thead><tbody>
<tr><td>Dec 3, 2022</td><td>SoCal FTC League C1 – Meet 1</td><td>La Cañada High School</td><td><a class="ul" href="https://ftc-events.firstinspires.org/2022/USCALAC1M1" target="_blank" rel="noopener">FTC Events</a></td></tr>
<tr><td>2022–23 season</td><td>4 official events</td><td>Qualification record 10–5–0</td><td><a class="ul" href="https://ftc-events.firstinspires.org/2022/team/15303" target="_blank" rel="noopener">FTC Events</a></td></tr>
<tr><td>2023–24 season</td><td>California SoCal FTC Championship</td><td>Listed participant</td><td><a class="ul" href="https://ftc-events.firstinspires.org/2023/USCALACMP1" target="_blank" rel="noopener">FTC Events</a></td></tr>
<tr><td>Feb 18, 2024</td><td>SoCal event, semifinal match SF1-1</td><td>Played in the semifinal round</td><td><a class="ul" href="https://www.ftcstats.org/2024/california_southern.html" target="_blank" rel="noopener">FTC Stats</a></td></tr>
<tr><td>Jan 4, 2025</td><td>SoCal FTC League C1 – Meet 3</td><td>La Cañada High School</td><td><a class="ul" href="https://ftc-events.firstinspires.org/2024/USCALAC1M3" target="_blank" rel="noopener">FTC Events</a></td></tr>
</tbody></table></div>
<p class="src">Awards and playoff results are not listed until verified. Add them in this table.</p>
</div></section>

<section id="news"><div class="wrap two">
<div class="rv"><p class="lbl">07 / Newsletter</p>
<h2 class="h2" style="margin-top:14px">Stay in<br><span class="grad">orbit.</span></h2>
<p style="margin:20px 0;color:#5c3a4d">Get the latest from Space Rocks.</p>
<form id="subF"><div><label for="se">Email</label><input id="se" name="email" type="email" required autocomplete="email"></div>
<div><button class="btn hot" type="submit">Subscribe <span>→</span></button></div><p class="msg" id="subM" role="status"></p></form></div>
<div class="rv"><p class="lbl">Archive</p><div class="tl" id="nl"></div></div>
</div></section>

<section id="events"><div class="wrap">
<p class="lbl rv">08 / Calendar</p>
<h2 class="h2 rv" style="margin-top:14px">Next up.</h2>
<div class="tl rv" id="ev"></div>
</div></section>

<section id="sponsors"><div class="wrap">
<p class="lbl rv">09 / Sponsors</p>
<h2 class="h2 rv" style="margin:14px 0 30px">Powering the<br><span class="outline">next generation.</span></h2>
<div class="tiers rv">
<div class="tier t-gold"><header><em>Gold Tier</em></header><b class="amt">$1,000+</b></div>
<div class="tier t-silver"><header><em>Silver Tier</em></header><b class="amt">$50+</b></div>
<div class="tier t-bronze"><header><em>Bronze Tier</em></header><b class="amt">$10+</b></div>
<div class="tier t-total"><header><em>Total Raised This Season</em></header><b class="amt">$3,000</b><p class="who">Funding parts, travel, and outreach</p></div>
</div>
<p class="rv" style="margin:26px 0;color:#5c3a4d;max-width:620px">Sponsors can receive logo placement on the robot, a pit banner, social media tags and a website feature.</p>
<a class="btn hot rv" href="#contact" data-role="Sponsor">Become a Space Rocks sponsor <span>→</span></a>
</div></section>

<section id="join"><div class="wrap">
<p class="lbl rv">10 / Get involved</p>
<h2 class="h2 rv" style="margin-top:14px">Build<br><span class="grad">with us.</span></h2>
<div class="join rv">
<div><h3>Students</h3><p>Grades 7–12 who want to build, code, design and compete. Tell us what you are curious about.</p></div>
<div><h3>Parents</h3><p>Follow the season, volunteer and cheer at meets. Subscribe to the newsletter.</p></div>
<div><h3>Engineers & mentors</h3><p>Share your expertise through mentoring or a design review of our robot.</p></div>
<div><h3>Sponsors</h3><p>Help fund parts, travel and outreach, and get visibility in return.</p></div>
</div>
<div class="rv" style="margin:0 0 40px"><a class="btn hot" href="https://forms.gle/jxZiQeuKrLDhTKDM6" target="_blank" rel="noopener">Space Rocks FTC 15303: Interest &amp; Application <span>→</span></a></div>
<div class="rv" style="max-width:760px">
<details><summary>Who can join?</summary><p>FIRST Tech Challenge is for students in grades 7–12 — no prior robotics experience required. We look for curious students interested in any part of the team: mechanical build, CAD and design, programming and AI, electronics and sensors, strategy and scouting, or outreach, business and media. Members commit to regular meetings during the season, work as part of a team, and help with community outreach. Fill out the <a class="ul" href="https://forms.gle/jxZiQeuKrLDhTKDM6" target="_blank" rel="noopener" style="color:var(--pink)">Interest &amp; Application form</a> to tell us about yourself and hear about current openings and tryouts.</p></details>
<details><summary>What is MajorStem.org?</summary><p>Our parent organization. Space Rocks was created in August 2018 as part of MajorStem.org. Visit the <a class="ul" href="https://sites.google.com/d/1IJrwvnLNJUbaQXfs8Zcpbo0CiUaQnzEQ/p/1g_2HXlOytMigezkTcSSX6GWBXslTyED1/edit" target="_blank" rel="noopener" style="color:var(--pink)">Parent Hub</a>.</p></details>
<details><summary>Who supports the team?</summary><p>Space Rocks is supported by a whole community: sponsors like the Haas Foundation and Xin Wang, individual donors, previous team alumni who come back to mentor, parents who volunteer their time, and local organizations, schools and community partners. We are always welcoming more sponsors and partners.</p></details>
<details><summary>How can an engineer or professional help?</summary><p>You do not have to be an engineer — we welcome professionals from every field connected to robotics. Mechanical and electrical engineers, CAD and design specialists, software developers, AI and computer-vision experts, sensors and controls specialists, machinists and fabricators, as well as people in outreach, marketing, business and media can all help. Mentor students, run a workshop, or review a design. Fill out the <a class="ul" href="https://forms.gle/jxZiQeuKrLDhTKDM6" target="_blank" rel="noopener" style="color:var(--pink)">Interest &amp; Application form</a> and tell us your specialty.</p></details>
</div></div></section>

<section id="contact"><div class="wrap two">
<div class="rv"><p class="lbl">11 / Contact</p>
<h2 class="h2" style="margin-top:14px">Let's build<br><span class="grad">something.</span></h2>
<p style="margin-top:22px;color:#5c3a4d">Students, parents, engineers, mentors, sponsors and neighbors are welcome.</p></div>
<form id="cF" class="rv">
<div><label for="cn">Name</label><input id="cn" name="name" required autocomplete="name"></div>
<div><label for="ce">Email</label><input id="ce" name="email" type="email" required autocomplete="email"></div>
<div><label for="cr">I am a</label><select id="cr" name="role" required><option value="" selected disabled hidden></option><option>Student</option><option>Parent</option><option>Engineer</option><option>Mentor</option><option>Sponsor</option><option>Community Member</option><option>Other</option></select></div>
<div><label for="cm">Message</label><textarea id="cm" name="message" rows="3" required></textarea></div>
<div><button class="btn hot" type="submit">Send <span>→</span></button></div><p class="msg" id="cM" role="status"></p>
</form></div></section>
</main>

<footer><div class="wrap">
<div class="big" aria-hidden="true">Space<br><span class="outline">Rocks</span></div>
<div class="fl">
<a class="ul" href="https://www.instagram.com/" target="_blank" rel="noopener">Instagram</a>
<a class="ul" href="https://www.youtube.com/" target="_blank" rel="noopener">YouTube</a>
<a class="ul" href="https://ftc-events.firstinspires.org/2022/team/15303" target="_blank" rel="noopener">FTC</a>
<a class="ul" href="https://sites.google.com/d/1IJrwvnLNJUbaQXfs8Zcpbo0CiUaQnzEQ/p/1g_2HXlOytMigezkTcSSX6GWBXslTyED1/edit" target="_blank" rel="noopener">Parent Organization</a>
<a class="ul" href="#contact">Contact</a></div>
<p class="fine">FTC TEAM 15303 · SPACE ROCKS · SOUTHERN CALIFORNIA</p>
<p class="fine" style="margin-top:8px">© FTC Team 15303 Space Rocks. All rights reserved.</p>
</div></footer>

<script>
/* ===== EDIT ME ===== */
const FORM_ENDPOINT=""; // e.g. a Formspree/Supabase function URL. Empty = forms don't send anything.
const SEASONS=[
{y:2018,g:"Rover Ruckus",d:{Team:"Founded August 2018 as part of MajorStem.org."}},
{y:2019,g:"Skystone",d:{}},
{y:2020,g:"Ultimate Goal",d:{Robot:"Mecanum drivetrain with a collect-store-shoot mechanism for rings."}},
{y:2021,g:"Freight Frenzy",d:{}},
{y:2022,g:"PowerPlay",d:{Competition:"4 official events, 10–5–0 qualification record. Opened at League C1 Meet 1, Dec 3, 2022 (FTC Events)."}},
{y:2023,g:"CenterStage",d:{Competition:"Listed at the SoCal FTC Championship; played a semifinal match on Feb 18, 2024 (FTC Events, FTC Stats)."}},
{y:2024,g:"Into The Deep",d:{Competition:"Competed at SoCal League C1 Meet 3, Jan 4, 2025 (FTC Events)."}},
{y:2025,g:"DECODE",d:{}},
{y:2026,g:"BIOBUZZ",d:{},active:true}
];
const FIELDS=["Robot","Engineering","Competition","Awards","Outreach","Media"];
const NEWS=[{t:"Newsletter archive",p:"Add your monthly editions here (title, date, link)."}];
const EVENTS=[
{t:"Next event",p:"Add date, place and public/private visibility."},
{t:"Weekly build & CAD sessions",p:"Add schedule."},
{t:"Outreach & STEM workshops",p:"Add dates."},
{t:"League meets, scrimmages, championship",p:"Add dates from the official FTC Events page."}
];
const reduce=matchMedia('(prefers-reduced-motion:reduce)').matches;
/* ===== loader, progress, menu ===== */
(()=>{const ld=document.getElementById('load'),n=document.getElementById('ln');
if(reduce){ld.remove()}else{document.body.style.overflow='hidden';let v=0;const t=setInterval(()=>{v+=Math.ceil(Math.random()*9);if(v>=100){v=100;clearInterval(t);setTimeout(()=>{ld.classList.add('done');document.body.style.overflow='';setTimeout(()=>ld.remove(),1000)},250)}n.textContent=v},70)}
const pg=document.getElementById('prog');addEventListener('scroll',()=>{pg.style.width=(scrollY/(document.documentElement.scrollHeight-innerHeight)*100)+'%'},{passive:true});
const ov=document.getElementById('ov'),bg=document.getElementById('bg'),ovp=document.getElementById('ovp');
function tg(o){ov.classList.toggle('open',o);bg.setAttribute('aria-expanded',o);bg.textContent=o?'Close':'Menu';document.body.style.overflow=o?'hidden':''}
bg.onclick=()=>tg(!ov.classList.contains('open'));
ov.querySelectorAll('nav a').forEach(a=>{a.addEventListener('click',()=>tg(false));a.onmouseenter=a.onfocus=()=>ovp.textContent=a.dataset.p||''});
addEventListener('keydown',e=>{if(e.key==='Escape')tg(false)})})();
/* ===== drive the robot (hero) ===== */
(()=>{const h=document.getElementById('hero'),b=document.getElementById('bot'),sc=document.getElementById('sc');let tx=innerWidth*.6,ty=innerHeight*.45,x=tx,y=ty,a=0,n=0;
const set=e=>{const p=e.touches?e.touches[0]:e,r=h.getBoundingClientRect();tx=p.clientX-r.left;ty=p.clientY-r.top};
h.addEventListener('pointermove',set);h.addEventListener('touchmove',set,{passive:true});
const tr=document.getElementById('troph'),to=document.getElementById('toast');let next=0,tt;
const RP=[25,10,5,3,2,1];window.orbitG={cx:innerWidth*.68,cy:innerHeight*.4,u:Math.min(innerWidth,innerHeight)};
const MS=[10,50,100,250,500,1000];const ms=i=>i<MS.length?MS[i]:MS[MS.length-1]*2**(i-MS.length+1);
const fx=(t,c)=>{const p=document.createElement('i');p.className='pts'+(c?' '+c:'');p.textContent=t;p.style.left=tx+'px';p.style.top=ty+'px';h.appendChild(p);setTimeout(()=>p.remove(),1000)};
h.addEventListener('click',e=>{if(e.target.closest('a,button'))return;set(e);const d=document.createElement('i');d.className='pix';d.style.left=tx+'px';d.style.top=ty+'px';h.appendChild(d);setTimeout(()=>d.remove(),1800);
const g=window.orbitG,dx=tx-g.cx,dy=ty-g.cy,c=Math.cos(.35),sn=Math.sin(.35),ex=dx*c-dy*sn,ey=dx*sn+dy*c,a1=g.u*.12,r=Math.hypot(ex/a1,ey/(a1*.4)),k=r<=.3?0:Math.ceil(r),p=k<RP.length?RP[k]:0;
if(p)g.hit={k,t:performance.now()};
if(!p){fx('Miss','miss');return}fx('+'+p+(k===0?' Bullseye!':''));n+=p;sc.textContent=n;
while(n>=ms(next)){const m=ms(next++),t=document.createElement('span');t.title=m+' points';t.innerHTML='🏆<small>'+m+'</small>';tr.appendChild(t);to.textContent='🏆 Trophy unlocked: '+m+' points';to.classList.add('on');clearTimeout(tt);tt=setTimeout(()=>to.classList.remove('on'),2200)}});
(function f(){const dx=tx-x,dy=ty-y;x+=dx*.08;y+=dy*.08;if(Math.hypot(dx,dy)>6)a=Math.atan2(dy,dx)*180/Math.PI+90;b.style.transform=`translate(${x}px,${y}px) translate(-50%,-50%) rotate(${a}deg)`;requestAnimationFrame(f)})()})();
/* ===== hero orbit canvas with cursor parallax ===== */
(()=>{const c=document.getElementById('orbit'),x=c.getContext('2d');let w,h,mx=0,my=0,t=0;
const pts=Array.from({length:70},()=>({a:Math.random()*6.28,r:.15+Math.random()*.6,s:(Math.random()-.5)*.002,z:Math.random()}));
function rs(){w=c.width=c.offsetWidth;h=c.height=c.offsetHeight}rs();addEventListener('resize',rs);
const mv=e=>{const p=e.touches?e.touches[0]:e;mx=(p.clientX/innerWidth-.5);my=(p.clientY/innerHeight-.5)};
addEventListener('pointermove',mv);addEventListener('touchmove',mv,{passive:true});
function f(){t++;x.clearRect(0,0,w,h);const cx=w*.68+mx*-40,cy=h*.4+my*-30,u=Math.min(w,h),G=window.orbitG||{},hk=G.hit&&performance.now()-G.hit.t<500?G.hit.k:-1;Object.assign(G,{cx,cy,u});window.orbitG=G;
x.strokeStyle='rgba(230,0,126,.2)';x.lineWidth=1;
const RL=[10,5,3,2,1];x.font='600 10px system-ui';x.textAlign='center';
for(let i=1;i<=5;i++){const hit=hk===i;x.lineWidth=hit?3:1;x.strokeStyle=hit?'rgba(230,0,126,.8)':'rgba(230,0,126,.2)';x.beginPath();x.ellipse(cx,cy,u*.12*i,u*.12*i*.4,-.35,0,6.28);x.stroke();
const ra=u*.12*i-u*.06,lx=cx+Math.cos(-.35)*ra,ly=cy+Math.sin(-.35)*ra;x.fillStyle='rgba(176,18,92,.55)';x.fillText(RL[i-1],lx,ly+3)}
x.lineWidth=1;x.textAlign='start';
x.strokeStyle='rgba(230,0,126,.07)';for(let i=0;i<w;i+=60){x.beginPath();x.moveTo(i+mx*10,0);x.lineTo(i+mx*10,h);x.stroke()}
pts.forEach(p=>{if(!reduce)p.a+=p.s;const rr=p.r*u,px=cx+Math.cos(p.a)*rr+mx*p.z*30,py=cy+Math.sin(p.a)*rr*.4+my*p.z*30;
x.fillStyle=p.z>.8?'#b0125c':p.z>.4?'#e6007e':'#ff7ab8';x.globalAlpha=.4+p.z*.5;x.fillRect(px,py,1+p.z*2,1+p.z*2)});x.globalAlpha=1;
x.fillStyle='#e6007e';x.beginPath();x.arc(cx,cy,hk===0?9:5,0,6.28);x.fill();if(hk===0){x.strokeStyle='rgba(230,0,126,.6)';x.beginPath();x.ellipse(cx,cy,u*.036,u*.0144,-.35,0,6.28);x.stroke()}
x.fillStyle='rgba(138,95,116,.9)';x.font='11px monospace';x.fillText('TEL  T+'+String(Math.floor(t/60)).padStart(4,'0')+'s  ORBIT 15303',20,h-100);
if(!reduce)requestAnimationFrame(f)}f()})();
/* ===== split headings ===== */
document.querySelectorAll('.h2').forEach(h=>{h.classList.add('rv');const w=document.createTreeWalker(h,NodeFilter.SHOW_TEXT),ns=[];while(w.nextNode())ns.push(w.currentNode);let k=0;
ns.forEach(n=>{const f=document.createDocumentFragment();n.textContent.split(/(\s+)/).forEach(t=>{if(!t.trim()){f.append(t);return}const s=document.createElement('span'),i=document.createElement('span');s.className='w';i.textContent=t;i.style.transitionDelay=(k++*70)+'ms';s.appendChild(i);f.append(s)});n.replaceWith(f)})});
/* ===== reveal + count-up ===== */
const io=new IntersectionObserver(es=>es.forEach(e=>{if(!e.isIntersecting)return;e.target.classList.add('in');
e.target.querySelectorAll('[data-n]').forEach(n=>{if(reduce)return;const to=+n.dataset.n,s=performance.now();
(function st(now){const k=Math.min((now-s)/1200,1);n.textContent=Math.round(to*(1-Math.pow(1-k,3)));if(k<1)requestAnimationFrame(st)})(s)});io.unobserve(e.target)}),{threshold:.2});
document.querySelectorAll('.rv').forEach(el=>io.observe(el));
/* ===== seasons ===== */
const yrs=document.getElementById('years'),stage=document.getElementById('stage');
SEASONS.forEach((s,i)=>{const b=document.createElement('button');b.className='yr';b.role='tab';b.textContent=s.y;b.onclick=()=>pick(i);b.onkeydown=e=>{if(e.key==='ArrowRight')pick(Math.min(i+1,SEASONS.length-1),1);if(e.key==='ArrowLeft')pick(Math.max(i-1,0),1)};yrs.appendChild(b)});
function pick(i,focus){const s=SEASONS[i];[...yrs.children].forEach((b,j)=>{b.setAttribute('aria-selected',i===j);b.tabIndex=i===j?0:-1});if(focus)yrs.children[i].focus();
document.getElementById('seasons').style.background=`hsl(${335+i*3},85%,${97-i}%)`;
stage.innerHTML=`<div class="swap"><div class="yrbig">${s.y}</div><div class="game">${s.g}</div>${s.active?'<p class="lbl tag" style="margin-top:14px">Active season</p>':''}${s.g==='BIOBUZZ'?'<p class="src">Game name as supplied by the team; confirm against FIRST.</p>':''}</div>
<dl class="swap">${FIELDS.map(f=>`<div><dt>${f}</dt><dd class="${s.d[f]?'':'ph'}">${s.d[f]||'Add Space Rocks info'}</dd></div>`).join('')}</dl>`}
pick(SEASONS.length-1);
/* ===== lists ===== */
const tl=(id,a)=>document.getElementById(id).innerHTML=a.map(n=>`<div><h3>${n.t}</h3><p>${n.p}</p></div>`).join('');
tl('nl',NEWS);tl('ev',EVENTS);
/* ===== forms (no fake storage) ===== */
function wire(id,mid,ok){document.getElementById(id).onsubmit=async e=>{e.preventDefault();const m=document.getElementById(mid),f=e.target;
if(!FORM_ENDPOINT){m.textContent='Form not connected yet: nothing was sent. Set FORM_ENDPOINT to enable.';return}
try{const r=await fetch(FORM_ENDPOINT,{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify({form:id,...Object.fromEntries(new FormData(f))})});
if(!r.ok)throw 0;m.textContent=ok;f.reset()}catch{m.textContent='Something went wrong. Please try again.'}}}
wire('subF','subM','You are in orbit. Thank you!');wire('cF','cM','Message sent. Thank you!');
document.querySelectorAll('[data-role]').forEach(a=>a.onclick=()=>{document.getElementById('cr').value='Sponsor'});
/* ===== pinned horizontal engineering strip ===== */
(()=>{const hz=document.getElementById('hz'),st=hz.querySelector('.strip'),on=()=>innerWidth>860&&!reduce;
function sz(){hz.style.height=on()?(st.scrollWidth-innerWidth+innerHeight+120)+'px':'';if(!on())st.style.transform=''}
function up(){if(!on())return;const r=hz.getBoundingClientRect(),m=st.scrollWidth-innerWidth+120,p=Math.min(Math.max(-r.top/(hz.offsetHeight-innerHeight),0),1);st.style.transform=`translateX(${-p*m}px)`}
sz();up();addEventListener('resize',()=>{sz();up()});addEventListener('scroll',up,{passive:true})})();
/* ===== spin the build ===== */
(()=>{const w=document.getElementById('cw'),c=document.getElementById('cube');let rx=-20,ry=30,d=false,lx=0,ly=0;
w.addEventListener('pointerdown',e=>{d=true;lx=e.clientX;ly=e.clientY;w.setPointerCapture(e.pointerId);w.style.cursor='grabbing'});
w.addEventListener('pointermove',e=>{if(!d)return;ry+=(e.clientX-lx)*.6;rx-=(e.clientY-ly)*.6;lx=e.clientX;ly=e.clientY});
const up=()=>{d=false;w.style.cursor='grab'};w.addEventListener('pointerup',up);w.addEventListener('pointercancel',up);
(function f(){if(!d&&!reduce)ry+=.25;c.style.transform=`rotateX(${rx}deg) rotateY(${ry}deg)`;requestAnimationFrame(f)})()})();
/* ===== magnetic buttons ===== */
if(matchMedia('(hover:hover) and (pointer:fine)').matches&&!reduce)document.querySelectorAll('.btn').forEach(b=>{b.addEventListener('pointermove',e=>{const r=b.getBoundingClientRect();b.style.transform=`translate(${(e.clientX-r.left-r.width/2)*.2}px,${(e.clientY-r.top-r.height/2)*.3}px)`});b.addEventListener('pointerleave',()=>b.style.transform='')});
document.querySelectorAll('.step').forEach(x=>x.dataset.cur='Scroll');document.querySelectorAll('.yr').forEach(x=>x.dataset.cur='Year');
/* ===== cursor ===== */
if(matchMedia('(hover:hover) and (pointer:fine)').matches&&!reduce){const c=document.getElementById('cur');c.classList.add('on');
addEventListener('pointermove',e=>{c.style.left=e.clientX+'px';c.style.top=e.clientY+'px';const t=e.target.closest('[data-cur]');c.textContent=t?t.dataset.cur:'';c.classList.toggle('lab',!!t);c.classList.toggle('hov',!t&&!!e.target.closest('a,button'))})}
</script>
</body>
</html>
