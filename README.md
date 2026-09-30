<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Hemanth Pindi | Portfolio</title>
<style>
  :root{--bg:#0b0b1a;--card:rgba(255,255,255,.06);--cyan:#00f5ff;--purple:#a78bfa;--gold:#f7b93e;--text:#e8e8f5;--muted:#9a9ab8}
  *{margin:0;padding:0;box-sizing:border-box}
  html{scroll-behavior:smooth}
  body{font-family:'Segoe UI',Arial,sans-serif;background:var(--bg);color:var(--text);overflow-x:hidden;line-height:1.6}

  /* animated background */
  .bg{position:fixed;top:0;left:0;width:100%;height:100%;z-index:-1;overflow:hidden}
  .orb{position:absolute;border-radius:50%;filter:blur(90px);opacity:.45;animation:float 14s ease-in-out infinite}
  .o1{width:420px;height:420px;background:#302b63;top:-100px;left:-100px}
  .o2{width:360px;height:360px;background:#00b4c8;bottom:-80px;right:-60px;animation-delay:-5s}
  .o3{width:300px;height:300px;background:#7c3aed;top:40%;left:55%;animation-delay:-9s}
  @keyframes float{0%,100%{transform:translate(0,0) scale(1)}50%{transform:translate(60px,-50px) scale(1.15)}}

  /* navbar */
  nav{position:sticky;top:0;display:flex;justify-content:center;gap:28px;padding:16px;background:rgba(11,11,26,.85);z-index:10;border-bottom:1px solid rgba(255,255,255,.08)}
  nav a{color:var(--muted);text-decoration:none;transition:color .3s}
  nav a:hover{color:var(--cyan)}

  section{max-width:1000px;margin:auto;padding:80px 24px}

  /* hero */
  .hero{min-height:88vh;display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center}
  .avatar{width:150px;height:150px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:3.6rem;font-weight:800;color:#fff;
    background:linear-gradient(135deg,var(--cyan),var(--purple));position:relative;animation:pop 1s ease both}
  .avatar::before{content:"";position:absolute;top:-8px;left:-8px;right:-8px;bottom:-8px;border-radius:50%;border:2px dashed var(--cyan);animation:spin 12s linear infinite}
  .avatar::after{content:"";position:absolute;top:-18px;left:-18px;right:-18px;bottom:-18px;border-radius:50%;border:2px solid transparent;border-top-color:var(--gold);animation:spin 5s linear infinite reverse}
  @keyframes spin{to{transform:rotate(360deg)}}
  @keyframes pop{from{transform:scale(0);opacity:0}to{transform:scale(1);opacity:1}}

  h1{font-size:clamp(2.4rem,7vw,4.4rem);margin-top:36px;
    background:linear-gradient(90deg,#00f5ff,#a78bfa,#f7b93e,#00f5ff);background-size:300% 100%;
    -webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent;color:transparent;
    animation:shine 6s linear infinite}
  @keyframes shine{to{background-position:300% 0}}

  .typing{display:inline-block;margin-top:10px;font-family:'Courier New',monospace;font-size:1.3rem;color:var(--cyan);
    white-space:nowrap;overflow:hidden;border-right:3px solid var(--cyan);width:0;
    animation:type 3s steps(28) .8s forwards,blink .7s step-end infinite}
  @keyframes type{to{width:28ch}}
  @keyframes blink{50%{border-color:transparent}}

  @keyframes fadeUp{from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:none}}
  .sub{margin-top:16px;color:var(--muted);animation:fadeUp 1s 1s ease both}
  .btns{margin-top:32px;display:flex;gap:16px;flex-wrap:wrap;justify-content:center;animation:fadeUp 1s 1.3s ease both}
  .btn{display:inline-block;padding:12px 28px;border-radius:50px;text-decoration:none;font-weight:600;transition:.3s}
  .btn.primary{background:linear-gradient(90deg,var(--cyan),var(--purple));color:#0b0b1a;animation:glow 2.5s ease-in-out infinite}
  @keyframes glow{50%{box-shadow:0 0 28px rgba(0,245,255,.6)}}
  .btn.ghost{border:1px solid var(--cyan);color:var(--cyan)}
  .btn:hover{transform:translateY(-4px)}
  .btn.ghost:hover{background:var(--cyan);color:#0b0b1a}

  /* headings and cards */
  h2{font-size:2rem;margin-bottom:36px;text-align:center}
  h2 span{color:var(--cyan)}
  .card{background:var(--card);border:1px solid rgba(255,255,255,.1);border-radius:20px;padding:28px;transition:.4s}
  .card:hover{transform:translateY(-8px);border-color:var(--cyan);box-shadow:0 12px 40px rgba(0,245,255,.15)}
  .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:24px}
  .card h3{color:var(--gold);margin-bottom:8px}
  .card p{color:var(--muted);font-size:.95rem}
  .num{display:inline-block;font-size:1.6rem;font-weight:800;color:var(--cyan);margin-bottom:8px;animation:bob 3s ease-in-out infinite}
  @keyframes bob{50%{transform:translateY(-8px)}}

  /* skill bars */
  .skill{margin-bottom:22px}
  .top{display:flex;justify-content:space-between;margin-bottom:6px;font-size:.95rem}
  .bar{height:10px;background:rgba(255,255,255,.1);border-radius:10px;overflow:hidden}
  .fill{height:100%;border-radius:10px;background:linear-gradient(90deg,var(--cyan),var(--purple));width:0;position:relative;overflow:hidden;animation:grow 2s ease forwards .5s}
  .fill::after{content:"";position:absolute;top:0;left:0;width:100%;height:100%;background:linear-gradient(90deg,transparent,rgba(255,255,255,.5),transparent);transform:translateX(-100%);animation:sweep 2.2s ease-in-out infinite}
  .w80{--w:80%}.w70{--w:70%}.w65{--w:65%}.w60{--w:60%}
  @keyframes grow{to{width:var(--w)}}
  @keyframes sweep{to{transform:translateX(100%)}}

  /* tags */
  .tags{display:flex;flex-wrap:wrap;gap:12px;justify-content:center;margin-top:24px}
  .tag{padding:8px 18px;border-radius:30px;background:var(--card);border:1px solid rgba(255,255,255,.12);font-size:.9rem;transition:.3s}
  .tag:hover{background:var(--purple);color:#0b0b1a;transform:scale(1.1) rotate(-3deg)}

  /* timeline */
  .timeline{border-left:2px solid var(--cyan);padding-left:28px;position:relative}
  .timeline .card::before{content:"";position:absolute;left:-37px;top:30px;width:16px;height:16px;border-radius:50%;background:var(--cyan);animation:pulse 2s infinite}
  .timeline .card{position:relative}
  @keyframes pulse{0%{box-shadow:0 0 0 0 rgba(0,245,255,.6)}100%{box-shadow:0 0 0 16px rgba(0,245,255,0)}}

  /* contact */
  .contact{text-align:center}
  .links{display:flex;gap:16px;justify-content:center;flex-wrap:wrap;margin-top:20px}
  footer{text-align:center;padding:30px;color:var(--muted);font-size:.85rem;border-top:1px solid rgba(255,255,255,.08)}

  @media (prefers-reduced-motion:reduce){
    *{animation:none!important}
    .fill{width:var(--w)}
    .typing{width:auto;border:0}
  }
</style>
</head>
<body>

<div class="bg">
  <div class="orb o1"></div>
  <div class="orb o2"></div>
  <div class="orb o3"></div>
</div>

<nav>
  <a href="#home">Home</a>
  <a href="#about">About</a>
  <a href="#skills">Skills</a>
  <a href="#education">Education</a>
  <a href="#contact">Contact</a>
</nav>

<section class="hero" id="home">
  <div class="avatar">HP</div>
  <h1>Hemanth Pindi</h1>
  <div class="typing">Computer Engineering Student</div>
  <p class="sub">Learning. Building. Growing.</p>
  <div class="btns">
    <a class="btn primary" href="#contact">Get in touch</a>
    <a class="btn ghost" href="https://www.linkedin.com/in/hemanthpindi-08758134b">LinkedIn</a>
  </div>
</section>

<section id="about">
  <h2>About <span>Me</span></h2>
  <div class="grid">
    <div class="card"><div class="num">01</div><h3>Education</h3><p>Pursuing a diploma in Computer Engineering at Sri Vasavi Engineering College.</p></div>
    <div class="card"><div class="num">02</div><h3>Location</h3><p>West Godavari, Andhra Pradesh, India.</p></div>
    <div class="card"><div class="num">03</div><h3>Goal</h3><p>To grow into a skilled developer by building real projects and learning every day.</p></div>
  </div>
</section>

<section id="skills">
  <h2>My <span>Skills</span></h2>
  <div class="card">
    <!-- Change the names and the percentages to match your real level -->
    <div class="skill"><div class="top"><span>HTML &amp; CSS</span><span>80%</span></div><div class="bar"><div class="fill w80"></div></div></div>
    <div class="skill"><div class="top"><span>Programming Basics</span><span>70%</span></div><div class="bar"><div class="fill w70"></div></div></div>
    <div class="skill"><div class="top"><span>Problem Solving</span><span>65%</span></div><div class="bar"><div class="fill w65"></div></div></div>
    <div class="skill"><div class="top"><span>Git &amp; GitHub</span><span>60%</span></div><div class="bar"><div class="fill w60"></div></div></div>
  </div>
  <div class="tags">
    <span class="tag">HTML</span><span class="tag">CSS</span><span class="tag">JavaScript</span>
    <span class="tag">Python</span><span class="tag">C</span><span class="tag">Git</span>
  </div>
</section>

<section id="education">
  <h2>My <span>Journey</span></h2>
  <div class="timeline">
    <div class="card">
      <h3>Sri Vasavi Engineering College</h3>
      <p>Diploma in Computer Engineering (currently pursuing)</p>
    </div>
  </div>
</section>

<section class="contact" id="contact">
  <h2>Let's <span>Connect</span></h2>
  <p style="color:#9a9ab8">Open to learning, collaborating and new opportunities.</p>
  <div class="links">
    <a class="btn primary" href="mailto:hemanthpindi02@gmail.com">Email Me</a>
    <a class="btn ghost" href="https://www.linkedin.com/in/hemanthpindi-08758134b">LinkedIn</a>
    <a class="btn ghost" href="https://github.com/YOUR_GITHUB_USERNAME">GitHub</a>
  </div>
</section>

<footer>&copy; 2026 Hemanth Pindi &middot; Built with HTML &amp; CSS</footer>

</body>
</html>
