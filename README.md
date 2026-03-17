<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>Surya Pratap Singh</title>
<meta name="description" content="CS undergrad @ AKTU — building ML systems, AI agents & deep RL environments."/>
<meta property="og:title" content="Surya Pratap Singh"/>
<meta property="og:description" content="Software Dev · ML · AI Systems · AKTU 2024–2028"/>
<meta property="og:type" content="website"/>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=VT323&family=Share+Tech+Mono&family=Syne:wght@400;700;800&display=swap" rel="stylesheet"/>
<style>
:root {
  --g:    #00ff41;
  --gd:   #00cc33;
  --gdd:  #007722;
  --gddd: #003311;
  --gx:   #aaffcc;
  --bg:   #000500;
  --bg2:  #020a04;
  --line: rgba(0,255,65,0.12);
}
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--gd);font-family:'Share Tech Mono',monospace;overflow-x:hidden;cursor:none}
::-webkit-scrollbar{width:4px}
::-webkit-scrollbar-track{background:#000}
::-webkit-scrollbar-thumb{background:var(--gddd)}
#cur-dot{position:fixed;width:8px;height:8px;background:var(--g);border-radius:50%;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);box-shadow:0 0 8px var(--g),0 0 20px #00ff4166;transition:width .1s,height .1s}
#cur-ring{position:fixed;width:28px;height:28px;border:1px solid #00ff4155;border-radius:50%;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);transition:all .12s ease}
#rain{position:fixed;top:0;left:0;width:100%;height:100%;z-index:0;pointer-events:none;opacity:.5}
#glow-cv{position:fixed;top:0;left:0;width:100%;height:100%;z-index:1;pointer-events:none}
.scanlines{position:fixed;inset:0;z-index:2;pointer-events:none;background:repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,255,65,.015) 2px,rgba(0,255,65,.015) 4px)}
.grid-bg{position:fixed;inset:0;z-index:0;pointer-events:none;background-image:linear-gradient(var(--line) 1px,transparent 1px),linear-gradient(90deg,var(--line) 1px,transparent 1px);background-size:60px 60px;mask-image:radial-gradient(ellipse 80% 80% at 50% 50%,black 40%,transparent 100%)}
#page{position:relative;z-index:3;min-height:100vh}

/* HERO */
#hero{min-height:100vh;display:flex;flex-direction:column;justify-content:center;padding:clamp(24px,5vw,80px) clamp(20px,6vw,100px);position:relative}
.hero-topbar{position:absolute;top:clamp(20px,3vw,36px);left:clamp(20px,6vw,100px);right:clamp(20px,6vw,100px);display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:10px}
.hero-topbar-left{font-size:11px;color:var(--gddd);letter-spacing:3px}
.hero-topbar-left span{color:var(--gd)}
.nav-links{display:flex;gap:24px}
.nav-links a{font-size:11px;color:var(--gddd);letter-spacing:2px;text-decoration:none;transition:color .2s;position:relative}
.nav-links a::after{content:'';position:absolute;bottom:-3px;left:0;width:0;height:1px;background:var(--g);transition:width .25s}
.nav-links a:hover{color:var(--g)}
.nav-links a:hover::after{width:100%}
.hero-inner{max-width:1100px;display:grid;grid-template-columns:1fr auto;gap:40px;align-items:end}
.sys-tag{font-size:11px;color:var(--gddd);letter-spacing:4px;margin-bottom:18px;display:flex;align-items:center;gap:10px}
.sys-tag::before{content:'';width:24px;height:1px;background:var(--gddd)}
.name-display{margin-bottom:16px;line-height:.88}
.n1{font-family:'VT323',monospace;font-size:clamp(56px,11vw,110px);color:var(--g);letter-spacing:5px;text-shadow:0 0 30px #00ff4155,0 0 60px #00ff4122;display:block;animation:fadeUp .8s ease both}
.n2{font-family:'VT323',monospace;font-size:clamp(56px,11vw,110px);color:var(--gd);letter-spacing:5px;text-shadow:0 0 15px #00cc3344;display:block;animation:fadeUp .8s .1s ease both}
.n3{font-family:'VT323',monospace;font-size:clamp(56px,11vw,110px);color:var(--gdd);letter-spacing:5px;display:block;animation:fadeUp .8s .2s ease both}
@keyframes fadeUp{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:translateY(0)}}
.hero-role{font-family:'Syne',sans-serif;font-size:clamp(13px,2vw,17px);font-weight:400;color:var(--gddd);letter-spacing:4px;text-transform:uppercase;margin-bottom:6px;animation:fadeUp .8s .3s ease both}
.hero-uni{font-size:11px;color:#003311;letter-spacing:3px;animation:fadeUp .8s .4s ease both}
.hero-uni span{color:var(--gddd)}
.hero-desc{font-family:'Share Tech Mono',monospace;font-size:13px;color:#005519;line-height:1.7;max-width:520px;margin:22px 0 28px;animation:fadeUp .8s .5s ease both}
.hero-desc em{color:var(--gd);font-style:normal}
.hero-btns{display:flex;gap:12px;flex-wrap:wrap;animation:fadeUp .8s .6s ease both}
.btn{font-family:'Share Tech Mono',monospace;font-size:11px;letter-spacing:2px;padding:10px 22px;text-decoration:none;cursor:pointer;border:none;clip-path:polygon(8px 0%,100% 0%,calc(100% - 8px) 100%,0% 100%);transition:all .2s}
.btn-primary{background:var(--g);color:#000}
.btn-primary:hover{background:var(--gx)}
.btn-outline{background:transparent;border:1px solid var(--gddd);color:var(--gddd)}
.btn-outline:hover{border-color:var(--g);color:var(--g);background:#00ff4108}
.hero-terminal{background:#020f05;border:1px solid var(--gddd);padding:20px;min-width:220px;animation:fadeUp .8s .4s ease both}
.term-bar{display:flex;gap:6px;margin-bottom:14px;align-items:center}
.term-dot{width:8px;height:8px;border-radius:50%}
.td1{background:#ff5f57}.td2{background:#febc2e}.td3{background:#28c840}
.term-line{font-size:11px;line-height:1.9;color:var(--gddd)}
.term-line .cmd{color:var(--gd)}.term-line .val{color:var(--g)}.term-line .dim{color:#003311}
.blink{animation:blink 1s step-end infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
.hero-bottombar{position:absolute;bottom:clamp(20px,3vw,36px);left:clamp(20px,6vw,100px);right:clamp(20px,6vw,100px);display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:10px}
.socials{display:flex;gap:20px}
.socials a{font-size:11px;color:#003311;letter-spacing:2px;text-decoration:none;transition:color .2s}
.socials a:hover{color:var(--g)}
.scroll-hint{font-size:10px;color:#002208;letter-spacing:3px;display:flex;align-items:center;gap:8px;animation:scrollPulse 2s ease infinite}
.scroll-hint::before{content:'';width:1px;height:20px;background:linear-gradient(transparent,var(--gddd));animation:scrollLine 2s ease infinite}
@keyframes scrollPulse{0%,100%{opacity:.4}50%{opacity:1}}
@keyframes scrollLine{0%{height:0}100%{height:20px}}

/* SECTIONS */
section{padding:clamp(60px,8vh,120px) clamp(20px,6vw,100px);max-width:1200px;margin:0 auto}
.sec-label{font-size:10px;color:var(--gddd);letter-spacing:5px;display:flex;align-items:center;gap:12px;margin-bottom:40px;text-transform:uppercase}
.sec-label::after{content:'';flex:1;height:1px;background:linear-gradient(90deg,var(--gddd),transparent)}
.sec-label .num{color:#003311}

/* STATS */
.stats-row{display:grid;grid-template-columns:repeat(auto-fill,minmax(140px,1fr));gap:1px;border:1px solid var(--gddd);background:var(--gddd);margin:0 clamp(20px,6vw,100px) clamp(40px,5vh,80px)}
.stat-card{background:var(--bg2);padding:24px 20px;text-align:center}
.stat-num{font-family:'VT323',monospace;font-size:40px;color:var(--g);text-shadow:0 0 15px #00ff4144;line-height:1}
.stat-lbl{font-size:9px;color:#003311;letter-spacing:3px;margin-top:4px}

/* PROJECTS */
.projects-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:1px;border:1px solid var(--gddd);background:var(--gddd)}
.proj-card{background:var(--bg2);padding:28px 24px;position:relative;overflow:hidden;transition:background .25s;cursor:pointer}
.proj-card::before{content:'';position:absolute;top:0;left:0;width:100%;height:2px;background:transparent;transition:background .25s}
.proj-card:hover{background:#020f05}
.proj-card:hover::before{background:var(--g)}
.proj-tag{font-size:9px;color:#003311;letter-spacing:3px;margin-bottom:12px;display:flex;gap:8px;align-items:center}
.proj-tag .status{border:1px solid var(--gddd);padding:1px 7px;color:var(--gdd);font-size:9px;letter-spacing:1px}
.proj-tag .status.live{border-color:var(--g);color:var(--g)}
.proj-name{font-family:'VT323',monospace;font-size:22px;color:var(--gd);letter-spacing:2px;margin-bottom:10px;transition:color .2s}
.proj-card:hover .proj-name{color:var(--g)}
.proj-desc{font-size:11px;color:#005519;line-height:1.7;margin-bottom:16px}
.proj-stack{display:flex;flex-wrap:wrap;gap:5px}
.tag{font-size:9px;letter-spacing:1px;padding:2px 8px;border:1px solid #002208;color:#003d11;clip-path:polygon(3px 0%,100% 0%,calc(100% - 3px) 100%,0% 100%)}
.proj-arrow{position:absolute;bottom:20px;right:20px;font-size:18px;color:var(--gddd);transition:color .2s,transform .2s}
.proj-card:hover .proj-arrow{color:var(--g);transform:translate(3px,-3px)}

/* SKILLS */
.skills-wrap{display:grid;grid-template-columns:repeat(auto-fill,minmax(110px,1fr));gap:6px}
.skill-item{border:1px solid var(--gddd);padding:14px 10px;text-align:center;font-family:'VT323',monospace;font-size:16px;letter-spacing:1px;color:#005519;transition:all .2s;clip-path:polygon(4px 0%,100% 0%,calc(100% - 4px) 100%,0% 100%);position:relative}
.skill-item::before{content:attr(data-level);position:absolute;bottom:3px;right:6px;font-size:8px;color:#002208}
.skill-item:hover{border-color:var(--g);color:var(--g);background:#00ff4108;text-shadow:0 0 10px var(--g)}

/* TIMELINE */
.timeline{position:relative;padding-left:28px}
.timeline::before{content:'';position:absolute;left:7px;top:6px;width:1px;bottom:0;background:linear-gradient(var(--gddd),transparent)}
.t-item{position:relative;margin-bottom:32px}
.t-item::before{content:'';position:absolute;left:-24px;top:5px;width:8px;height:8px;background:var(--gddd);clip-path:polygon(50% 0%,100% 50%,50% 100%,0% 50%)}
.t-item.active::before{background:var(--g);box-shadow:0 0 6px var(--g);animation:tpulse 1.5s infinite}
@keyframes tpulse{0%,100%{opacity:1}50%{opacity:.3}}
.t-meta{font-size:10px;color:#003311;letter-spacing:2px;margin-bottom:4px}
.t-title{font-family:'VT323',monospace;font-size:20px;color:var(--gd);letter-spacing:1px;margin-bottom:4px}
.t-desc{font-size:11px;color:#005519;line-height:1.65}

/* CONTACT */
#contact{text-align:center;border-top:1px solid var(--gddd);padding:clamp(60px,8vh,100px) clamp(20px,6vw,100px);max-width:100%}
.contact-head{font-family:'VT323',monospace;font-size:clamp(36px,7vw,72px);color:var(--gdd);letter-spacing:4px;margin-bottom:12px}
.contact-sub{font-size:12px;color:#005519;letter-spacing:2px;margin-bottom:36px}
.contact-links{display:flex;justify-content:center;gap:12px;flex-wrap:wrap}
.contact-link{font-family:'Share Tech Mono',monospace;font-size:11px;letter-spacing:2px;padding:10px 24px;border:1px solid var(--gddd);color:var(--gdd);text-decoration:none;clip-path:polygon(8px 0%,100% 0%,calc(100% - 8px) 100%,0% 100%);transition:all .2s}
.contact-link:hover{border-color:var(--g);color:var(--g);background:#00ff4108}

/* FOOTER */
footer{border-top:1px solid #001a07;padding:20px clamp(20px,6vw,100px);display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:10px;font-size:10px;color:#002208;letter-spacing:2px}
footer a{color:#003311;text-decoration:none}
footer a:hover{color:var(--g)}

/* REVEAL */
.reveal{opacity:0;transform:translateY(30px);transition:opacity .7s ease,transform .7s ease}
.reveal.visible{opacity:1;transform:translateY(0)}

@media(max-width:768px){
  .hero-inner{grid-template-columns:1fr}
  .hero-terminal{display:none}
  .hero-topbar{position:relative;top:auto;left:auto;right:auto;margin-bottom:40px}
  .hero-bottombar{position:relative;bottom:auto;margin-top:40px}
  #hero{min-height:auto;padding-top:100px}
}
</style>
</head>
<body>

<div id="cur-dot"></div>
<div id="cur-ring"></div>
<canvas id="rain"></canvas>
<canvas id="glow-cv"></canvas>
<div class="grid-bg"></div>
<div class="scanlines"></div>

<div id="page">

<section id="hero">
  <div class="hero-topbar">
    <div class="hero-topbar-left">SYS.BOOT &nbsp;<span>OK</span> &nbsp;// Surya97141</div>
    <nav class="nav-links">
      <a href="#projects">projects</a>
      <a href="#skills">stack</a>
      <a href="#timeline">log</a>
      <a href="#contact">contact</a>
    </nav>
  </div>

  <div class="hero-inner">
    <div class="hero-left">
      <div class="sys-tag">[ IDENTITY NODE ]<span class="blink">_</span></div>
      <div class="name-display">
        <span class="n1">SURYA</span>
        <span class="n2">PRATAP</span>
        <span class="n3">SINGH</span>
      </div>
      <div class="hero-role">Software Dev &nbsp;·&nbsp; ML &nbsp;·&nbsp; AI Systems</div>
      <div class="hero-uni">AKTU &nbsp;<span>B.Tech CSE — Data Science</span> &nbsp;· 2024–2028</div>
      <p class="hero-desc">
        CS undergrad building at the intersection of <em>software development</em>,
        <em>machine learning</em>, and <em>autonomous AI systems</em>.
        Clean, modular code — and ML that works outside notebooks.
      </p>
      <div class="hero-btns">
        <a class="btn btn-primary" href="#projects">view projects</a>
        <a class="btn btn-outline" href="https://github.com/Surya97141" target="_blank">github profile</a>
        <a class="btn btn-outline" href="mailto:pratap742006@gmail.com">get in touch</a>
      </div>
    </div>

    <div class="hero-terminal">
      <div class="term-bar">
        <div class="term-dot td1"></div>
        <div class="term-dot td2"></div>
        <div class="term-dot td3"></div>
      </div>
      <div class="term-line"><span class="dim">$</span> <span class="cmd">whoami</span></div>
      <div class="term-line"><span class="val">surya_pratap_singh</span></div>
      <div class="term-line">&nbsp;</div>
      <div class="term-line"><span class="dim">$</span> <span class="cmd">cat status.txt</span></div>
      <div class="term-line"><span class="val">open_to_work: true</span></div>
      <div class="term-line"><span class="val">target: SWE | ML | AI</span></div>
      <div class="term-line">&nbsp;</div>
      <div class="term-line"><span class="dim">$</span> <span class="cmd">ls projects/</span></div>
      <div class="term-line"><span class="val">MAIRA/</span></div>
      <div class="term-line"><span class="val">DRL-Combat/</span></div>
      <div class="term-line"><span class="val">SentinelAI/</span></div>
      <div class="term-line"><span class="val">+2 more</span></div>
      <div class="term-line">&nbsp;</div>
      <div class="term-line"><span class="dim">$</span> <span class="blink">_</span></div>
    </div>
  </div>

  <div class="hero-bottombar">
    <div class="socials">
      <a href="https://github.com/Surya97141" target="_blank">github</a>
      <a href="https://linkedin.com/in/surya-singh-b575591b5" target="_blank">linkedin</a>
      <a href="mailto:pratap742006@gmail.com">email</a>
    </div>
    <div class="scroll-hint">scroll</div>
  </div>
</section>

<div class="stats-row reveal">
  <div class="stat-card"><div class="stat-num">05</div><div class="stat-lbl">PROJECTS</div></div>
  <div class="stat-card"><div class="stat-num">02</div><div class="stat-lbl">ACTIVE BUILDS</div></div>
  <div class="stat-card"><div class="stat-num">02</div><div class="stat-lbl">HACKATHONS</div></div>
  <div class="stat-card"><div class="stat-num">15+</div><div class="stat-lbl">TECHNOLOGIES</div></div>
  <div class="stat-card"><div class="stat-num">646</div><div class="stat-lbl">COMMITS / YEAR</div></div>
</div>

<section id="projects">
  <div class="sec-label"><span class="num">01</span> project.log</div>
  <div class="projects-grid">

    <div class="proj-card reveal" onclick="window.open('https://github.com/Surya97141/MAIRA','_blank')">
      <div class="proj-tag"><span class="status live">BUILDING</span> NODE_01</div>
      <div class="proj-name">MAIRA</div>
      <p class="proj-desc">ML Research Automation Agent — scans codebases and surfaces missing experiments: ablation studies, baseline gaps, hyperparameter sweeps researchers forget to run.</p>
      <div class="proj-stack">
        <span class="tag">Python</span><span class="tag">NLP</span><span class="tag">Static Analysis</span><span class="tag">OOP</span><span class="tag">Git</span>
      </div>
      <div class="proj-arrow">↗</div>
    </div>

    <div class="proj-card reveal" onclick="window.open('https://github.com/Surya97141/DRL-Aerial-Combat','_blank')">
      <div class="proj-tag"><span class="status live">BUILDING</span> NODE_02</div>
      <div class="proj-name">DRL AERIAL COMBAT</div>
      <p class="proj-desc">Custom OpenAI Gym-compatible RL environment for autonomous multi-agent aerial combat. PPO with reward shaping, tracking policy convergence and sample efficiency.</p>
      <div class="proj-stack">
        <span class="tag">Python</span><span class="tag">OpenAI Gym</span><span class="tag">PPO</span><span class="tag">Deep RL</span><span class="tag">Multi-Agent</span>
      </div>
      <div class="proj-arrow">↗</div>
    </div>

    <div class="proj-card reveal">
      <div class="proj-tag"><span class="status">SHIPPED</span> NODE_03</div>
      <div class="proj-name">SENTINELAI</div>
      <p class="proj-desc">Real-time misinformation detection. TF-IDF + cosine similarity + HuggingFace zero-shot classification. Sub-second inference. Shipped at Galgotias Creator Hackathon.</p>
      <div class="proj-stack">
        <span class="tag">HuggingFace</span><span class="tag">REST API</span><span class="tag">Streamlit</span><span class="tag">TF-IDF</span>
      </div>
      <div class="proj-arrow">↗</div>
    </div>

    <div class="proj-card reveal">
      <div class="proj-tag"><span class="status">SHIPPED</span> NODE_04</div>
      <div class="proj-name">MENTAL HEALTH PREDICTOR</div>
      <p class="proj-desc">End-to-end supervised ML pipeline — SMOTE + feature encoding + missing-value imputation. Benchmarked LR / RF / GBM on F1, ROC-AUC, precision, recall.</p>
      <div class="proj-stack">
        <span class="tag">scikit-learn</span><span class="tag">SMOTE</span><span class="tag">Pandas</span><span class="tag">NumPy</span>
      </div>
      <div class="proj-arrow">↗</div>
    </div>

    <div class="proj-card reveal">
      <div class="proj-tag"><span class="status">SHIPPED</span> NODE_05 · SIH</div>
      <div class="proj-name">FLOOD PREDICTION</div>
      <p class="proj-desc">Disaster risk prediction for Smart India Hackathon. Scalable ETL on environmental sensor datasets with real-time Streamlit geospatial visualization dashboard.</p>
      <div class="proj-stack">
        <span class="tag">scikit-learn</span><span class="tag">Streamlit</span><span class="tag">ETL</span><span class="tag">Agile</span>
      </div>
      <div class="proj-arrow">↗</div>
    </div>

    <div class="proj-card reveal" style="display:flex;align-items:center;justify-content:center;min-height:180px;">
      <div style="text-align:center">
        <div style="font-family:'VT323',monospace;font-size:28px;color:var(--gdd);margin-bottom:8px">MORE INCOMING</div>
        <div style="font-size:10px;color:#003311;letter-spacing:2px">always building<span class="blink">_</span></div>
      </div>
    </div>

  </div>
</section>

<section id="skills">
  <div class="sec-label"><span class="num">02</span> stack.loaded</div>
  <div class="skills-wrap">
    <div class="skill-item" data-level="██████">Python</div>
    <div class="skill-item" data-level="████░░">C++</div>
    <div class="skill-item" data-level="███░░░">Java</div>
    <div class="skill-item" data-level="████░░">PyTorch</div>
    <div class="skill-item" data-level="███░░░">TensorFlow</div>
    <div class="skill-item" data-level="█████░">scikit-learn</div>
    <div class="skill-item" data-level="██████">NumPy</div>
    <div class="skill-item" data-level="██████">Pandas</div>
    <div class="skill-item" data-level="████░░">FastAPI</div>
    <div class="skill-item" data-level="████░░">HuggingFace</div>
    <div class="skill-item" data-level="█████░">Streamlit</div>
    <div class="skill-item" data-level="███░░░">Gradio</div>
    <div class="skill-item" data-level="██████">Git</div>
    <div class="skill-item" data-level="████░░">Linux</div>
    <div class="skill-item" data-level="███░░░">OpenAI Gym</div>
    <div class="skill-item" data-level="████░░">Matplotlib</div>
  </div>
</section>

<section id="timeline">
  <div class="sec-label"><span class="num">03</span> mission.log</div>
  <div class="timeline">
    <div class="t-item active reveal">
      <div class="t-meta">2025 — PRESENT · ACTIVE</div>
      <div class="t-title">MAIRA — ML Research Automation Agent</div>
      <p class="t-desc">Building an AI agent that audits ML research codebases and surfaces missing experiments. Rule-based NLP + LLM-assisted workflow automation.</p>
    </div>
    <div class="t-item active reveal">
      <div class="t-meta">2025 — PRESENT · ACTIVE</div>
      <div class="t-title">DRL Aerial Combat Simulation</div>
      <p class="t-desc">Custom OpenAI Gym multi-agent RL environment for autonomous aerial combat. PPO with reward shaping, clean decoupled architecture.</p>
    </div>
    <div class="t-item reveal">
      <div class="t-meta">2025 · SHIPPED</div>
      <div class="t-title">Galgotias Creator Hackathon</div>
      <p class="t-desc">Built SentinelAI — real-time fake news detection system with end-to-end NLP pipeline under hackathon time pressure.</p>
    </div>
    <div class="t-item reveal">
      <div class="t-meta">2024 · SHIPPED</div>
      <div class="t-title">Smart India Hackathon (SIH)</div>
      <p class="t-desc">Flood prediction & geospatial visualization system. Scalable ETL pipeline on environmental sensor data with real-time Streamlit dashboard.</p>
    </div>
    <div class="t-item reveal">
      <div class="t-meta">2024 · CERTIFIED</div>
      <div class="t-title">IIT Hyderabad — Neural Intelligence & CNNs</div>
      <p class="t-desc">Workshop on deep learning architectures, convolutional neural networks and neural intelligence systems.</p>
    </div>
    <div class="t-item reveal">
      <div class="t-meta">2024 · CERTIFIED</div>
      <div class="t-title">Kaggle — Intro to Machine Learning</div>
      <p class="t-desc">Completed Kaggle's foundational ML course covering decision trees, model validation, random forests, XGBoost.</p>
    </div>
    <div class="t-item reveal">
      <div class="t-meta">2024 · ENROLLED</div>
      <div class="t-title">B.Tech CSE — Data Science @ AKTU</div>
      <p class="t-desc">Started undergraduate journey in Computer Science Engineering with specialisation in Data Science (2024–2028).</p>
    </div>
  </div>
</section>

<section id="contact">
  <div class="contact-head reveal">LET'S BUILD</div>
  <p class="contact-sub reveal">open to SWE · ML · AI agent internships &amp; collaborations</p>
  <div class="contact-links reveal">
    <a class="contact-link" href="mailto:pratap742006@gmail.com">pratap742006@gmail.com</a>
    <a class="contact-link" href="https://linkedin.com/in/surya-singh-b575591b5" target="_blank">LinkedIn</a>
    <a class="contact-link" href="https://github.com/Surya97141" target="_blank">GitHub</a>
  </div>
</section>

<footer>
  <span>// Surya Pratap Singh — AKTU 2024–2028</span>
  <span>build things that work. then make them work better.</span>
  <span><a href="https://github.com/Surya97141" target="_blank">Surya97141</a></span>
</footer>

</div>

<script>
const rainCv = document.getElementById('rain');
const glowCv = document.getElementById('glow-cv');
const rCtx   = rainCv.getContext('2d');
const gCtx   = glowCv.getContext('2d');
const curDot = document.getElementById('cur-dot');
const curRing= document.getElementById('cur-ring');

let W, H, mx = -999, my = -999;
const CHARS = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789@#$%&*<>{}[]アイウエオカキクケコサシスセソ';
const COL_W = 18;
let cols = [], drops = [];

function resize() {
  W = rainCv.width  = glowCv.width  = window.innerWidth;
  H = rainCv.height = glowCv.height = document.documentElement.scrollHeight;
  initRain();
}

function initRain() {
  const n = Math.ceil(W / COL_W);
  cols  = Array.from({length:n}, (_,i) => i * COL_W + 9);
  drops = cols.map(() => Math.random() * -80);
}

function drawRain() {
  rCtx.fillStyle = 'rgba(0,5,0,0.1)';
  rCtx.fillRect(0, 0, W, H);
  rCtx.font = '13px Share Tech Mono';
  for (let i = 0; i < cols.length; i++) {
    const y = drops[i] * COL_W;
    rCtx.fillStyle = '#33aa55';
    rCtx.fillText(CHARS[Math.floor(Math.random() * CHARS.length)], cols[i]-6, y);
    for (let t = 1; t < 12; t++) {
      const ty = y - t * COL_W;
      if (ty < 0) continue;
      const b = Math.floor((1 - t/12) * 90);
      rCtx.fillStyle = `rgb(0,${b},${Math.floor(b*.15)})`;
      rCtx.fillText(CHARS[Math.floor(Math.random() * CHARS.length)], cols[i]-6, ty);
    }
    drops[i]++;
    if (drops[i] * COL_W > H + COL_W * 20) drops[i] = Math.random() * -80;
  }
}

const GLOW_R = 100, INNER_R = 32;
function drawGlow() {
  gCtx.clearRect(0, 0, W, H);
  if (mx < 0) return;
  const sy = my + window.scrollY;
  const halo = gCtx.createRadialGradient(mx, sy, 0, mx, sy, GLOW_R);
  halo.addColorStop(0,   'rgba(0,255,65,0.15)');
  halo.addColorStop(0.4, 'rgba(0,255,65,0.07)');
  halo.addColorStop(1,   'rgba(0,255,65,0)');
  gCtx.fillStyle = halo;
  gCtx.beginPath(); gCtx.arc(mx, sy, GLOW_R, 0, Math.PI*2); gCtx.fill();
  const mkLine = (x0,y0,x1,y1) => {
    const g = gCtx.createLinearGradient(x0,y0,x1,y1);
    g.addColorStop(0,'rgba(0,255,65,0)');g.addColorStop(.5,'rgba(0,255,65,0.45)');g.addColorStop(1,'rgba(0,255,65,0)');
    gCtx.strokeStyle=g;gCtx.lineWidth=1;
    gCtx.beginPath();gCtx.moveTo(x0,y0);gCtx.lineTo(x1,y1);gCtx.stroke();
  };
  mkLine(mx-55,sy,mx+55,sy); mkLine(mx,sy-55,mx,sy+55);
  const core = gCtx.createRadialGradient(mx,sy,0,mx,sy,INNER_R);
  core.addColorStop(0,'rgba(150,255,180,0.2)');core.addColorStop(1,'rgba(0,255,65,0)');
  gCtx.fillStyle=core;gCtx.beginPath();gCtx.arc(mx,sy,INNER_R,0,Math.PI*2);gCtx.fill();
}

document.addEventListener('mousemove', e => {
  mx=e.clientX; my=e.clientY;
  curDot.style.left=mx+'px'; curDot.style.top=my+'px';
  curRing.style.left=mx+'px'; curRing.style.top=my+'px';
});
document.addEventListener('mouseleave', () => { mx=-999; });

/* Scroll reveal */
const revEls = document.querySelectorAll('.reveal');
const io = new IntersectionObserver(entries => {
  entries.forEach(e => { if(e.isIntersecting){ e.target.classList.add('visible'); io.unobserve(e.target); } });
}, {threshold:0.12});
revEls.forEach(el => io.observe(el));

/* Loop */
let frame=0;
function loop(){
  requestAnimationFrame(loop);
  if(++frame%2===0) drawRain();
  drawGlow();
}

resize();
window.addEventListener('resize', resize);
loop();
</script>
</body>
</html>
