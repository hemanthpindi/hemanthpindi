<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description"
        content="Hemanth Pindi - Computer Engineering Student Portfolio">
  <meta name="author" content="Hemanth Pindi">

  <title>Hemanth Pindi | Portfolio</title>

  <style>
    :root {
      --bg: #070711;
      --bg2: #0d0d20;
      --card: rgba(255,255,255,0.06);
      --card-hover: rgba(255,255,255,0.10);

      --cyan: #00f5ff;
      --purple: #a78bfa;
      --gold: #f7b93e;

      --text: #f2f2ff;
      --muted: #a2a2bd;

      --border: rgba(255,255,255,0.10);

      --transition: 0.35s ease;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: "Segoe UI", system-ui, sans-serif;
      background:
        radial-gradient(circle at top left, #151537 0%, transparent 35%),
        radial-gradient(circle at bottom right, #101d36 0%, transparent 35%),
        var(--bg);

      color: var(--text);
      line-height: 1.6;
      overflow-x: hidden;
    }

    a {
      color: inherit;
    }

    /* =========================
       ANIMATED BACKGROUND
    ========================= */

    .background {
      position: fixed;
      inset: 0;
      z-index: -10;
      overflow: hidden;
    }

    .orb {
      position: absolute;
      border-radius: 50%;
      filter: blur(100px);
      opacity: 0.35;
      animation: float 15s ease-in-out infinite;
    }

    .orb1 {
      width: 420px;
      height: 420px;
      background: #302b63;
      top: -120px;
      left: -120px;
    }

    .orb2 {
      width: 380px;
      height: 380px;
      background: #00a8c6;
      right: -120px;
      bottom: -100px;
      animation-delay: -5s;
    }

    .orb3 {
      width: 300px;
      height: 300px;
      background: #6d28d9;
      left: 50%;
      top: 45%;
      animation-delay: -9s;
    }

    @keyframes float {
      0%, 100% {
        transform: translate(0,0) scale(1);
      }

      50% {
        transform: translate(50px,-40px) scale(1.15);
      }
    }

    /* =========================
       NAVBAR
    ========================= */

    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;

      display: flex;
      justify-content: center;
      align-items: center;
      gap: 30px;

      padding: 17px 20px;

      background: rgba(7,7,17,0.70);
      backdrop-filter: blur(14px);

      border-bottom: 1px solid var(--border);

      z-index: 1000;
    }

    nav a {
      position: relative;

      color: var(--muted);
      text-decoration: none;

      font-size: 0.95rem;
      font-weight: 500;

      transition: var(--transition);
    }

    nav a::after {
      content: "";

      position: absolute;
      left: 0;
      bottom: -7px;

      width: 0;
      height: 2px;

      background: var(--cyan);

      transition: var(--transition);
    }

    nav a:hover {
      color: var(--cyan);
    }

    nav a:hover::after {
      width: 100%;
    }

    /* =========================
       COMMON
    ========================= */

    section {
      width: min(1100px, 92%);
      margin: auto;
      padding: 100px 0;
    }

    .section-title {
      text-align: center;
      margin-bottom: 55px;
    }

    .section-title h2 {
      font-size: clamp(2rem, 5vw, 2.8rem);
      margin-bottom: 10px;
    }

    .section-title h2 span {
      color: var(--cyan);
    }

    .section-title p {
      color: var(--muted);
      max-width: 600px;
      margin: auto;
    }

    .card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 22px;

      padding: 28px;

      backdrop-filter: blur(12px);

      transition: var(--transition);
    }

    .card:hover {
      transform: translateY(-8px);
      background: var(--card-hover);
      border-color: rgba(0,245,255,0.45);

      box-shadow:
        0 15px 50px rgba(0,245,255,0.10);
    }

    /* =========================
       HERO
    ========================= */

    .hero {
      min-height: 100vh;

      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;

      text-align: center;

      padding-top: 120px;
    }

    .avatar {
      width: 155px;
      height: 155px;

      display: grid;
      place-items: center;

      border-radius: 50%;

      font-size: 3.5rem;
      font-weight: 800;

      color: white;

      background:
        linear-gradient(
          135deg,
          var(--cyan),
          var(--purple)
        );

      position: relative;

      animation: pop 1s ease;
    }

    .avatar::before {
      content: "";

      position: absolute;
      inset: -9px;

      border-radius: 50%;

      border: 2px dashed var(--cyan);

      animation: spin 12s linear infinite;
    }

    .avatar::after {
      content: "";

      position: absolute;
      inset: -19px;

      border-radius: 50%;

      border: 2px solid transparent;
      border-top-color: var(--gold);

      animation: spin 5s linear infinite reverse;
    }

    @keyframes spin {
      to {
        transform: rotate(360deg);
      }
    }

    @keyframes pop {
      from {
        transform: scale(0);
        opacity: 0;
      }

      to {
        transform: scale(1);
        opacity: 1;
      }
    }

    .hero h1 {
      margin-top: 40px;

      font-size: clamp(2.6rem, 8vw, 5rem);

      background:
        linear-gradient(
          90deg,
          var(--cyan),
          var(--purple),
          var(--gold),
          var(--cyan)
        );

      background-size: 300% 100%;

      -webkit-background-clip: text;
      background-clip: text;

      color: transparent;

      animation:
        shine 6s linear infinite,
        fadeUp 1s 0.3s ease both;
    }

    @keyframes shine {
      to {
        background-position: 300% 0;
      }
    }

    .typing {
      margin-top: 12px;

      color: var(--cyan);

      font-family: "Courier New", monospace;

      font-size: clamp(1rem, 3vw, 1.4rem);

      border-right: 3px solid var(--cyan);

      white-space: nowrap;
      overflow: hidden;

      width: 0;

      animation:
        type 4s steps(29) 0.8s forwards,
        blink 0.7s step-end infinite;
    }

    @keyframes type {
      to {
        width: 29ch;
      }
    }

    @keyframes blink {
      50% {
        border-color: transparent;
      }
    }

    .hero-description {
      margin-top: 18px;

      max-width: 650px;

      color: var(--muted);

      animation: fadeUp 1s 1s ease both;
    }

    @keyframes fadeUp {
      from {
        opacity: 0;
        transform: translateY(25px);
      }

      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* =========================
       BUTTONS
    ========================= */

    .buttons {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;

      gap: 15px;

      margin-top: 30px;

      animation: fadeUp 1s 1.3s ease both;
    }

    .btn {
      display: inline-block;

      padding: 12px 27px;

      border-radius: 50px;

      text-decoration: none;

      font-weight: 600;

      transition: var(--transition);
    }

    .btn-primary {
      color: #050510;

      background:
        linear-gradient(
          90deg,
          var(--cyan),
          var(--purple)
        );

      box-shadow: 0 0 0 transparent;
    }

    .btn-primary:hover {
      transform: translateY(-4px);

      box-shadow:
        0 10px 30px rgba(0,245,255,0.30);
    }

    .btn-outline {
      border: 1px solid var(--cyan);

      color: var(--cyan);
    }

    .btn-outline:hover {
      color: #050510;
      background: var(--cyan);

      transform: translateY(-4px);
    }

    /* =========================
       ABOUT
    ========================= */

    .about-grid {
      display: grid;

      grid-template-columns:
        repeat(auto-fit, minmax(240px, 1fr));

      gap: 24px;
    }

    .about-card .number {
      color: var(--cyan);

      font-size: 1.7rem;
      font-weight: 800;

      margin-bottom: 10px;
    }

    .about-card h3 {
      color: var(--gold);

      margin-bottom: 8px;
    }

    .about-card p {
      color: var(--muted);
    }

    /* =========================
       SKILLS
    ========================= */

    .skills-container {
      display: grid;

      grid-template-columns:
        repeat(auto-fit, minmax(300px, 1fr));

      gap: 30px;
    }

    .skill {
      margin-bottom: 22px;
    }

    .skill-header {
      display: flex;
      justify-content: space-between;

      margin-bottom: 7px;

      font-size: 0.95rem;
    }

    .skill-header span:last-child {
      color: var(--cyan);
    }

    .progress {
      height: 10px;

      background: rgba(255,255,255,0.08);

      border-radius: 20px;

      overflow: hidden;
    }

    .progress span {
      display: block;

      height: 100%;

      width: var(--width);

      border-radius: 20px;

      background:
        linear-gradient(
          90deg,
          var(--cyan),
          var(--purple)
        );

      animation: progress 1.5s ease;
    }

    @keyframes progress {
      from {
        width: 0;
      }

      to {
        width: var(--width);
      }
    }

    .tags {
      display: flex;

      flex-wrap: wrap;

      gap: 12px;

      margin-top: 30px;
    }

    .tag {
      padding: 8px 17px;

      border-radius: 30px;

      color: var(--text);

      background: rgba(255,255,255,0.05);

      border: 1px solid var(--border);

      transition: var(--transition);
    }

    .tag:hover {
      color: #050510;

      background: var(--cyan);

      transform: translateY(-4px);
    }

    /* =========================
       PROJECTS
    ========================= */

    .projects-grid {
      display: grid;

      grid-template-columns:
        repeat(auto-fit, minmax(280px, 1fr));

      gap: 25px;
    }

    .project-icon {
      width: 55px;
      height: 55px;

      display: grid;
      place-items: center;

      border-radius: 15px;

      font-size: 1.5rem;
      font-weight: 800;

      color: #050510;

      background:
        linear-gradient(
          135deg,
          var(--cyan),
          var(--purple)
        );

      margin-bottom: 18px;
    }

    .project h3 {
      color: var(--gold);

      margin-bottom: 10px;
    }

    .project p {
      color: var(--muted);

      font-size: 0.95rem;

      margin-bottom: 18px;
    }

    .project-tech {
      display: flex;
      flex-wrap: wrap;

      gap: 8px;
    }

    .project-tech span {
      padding: 5px 10px;

      font-size: 0.78rem;

      border-radius: 15px;

      color: var(--cyan);

      border: 1px solid rgba(0,245,255,0.25);
    }

    /* =========================
       EDUCATION
    ========================= */

    .timeline {
      position: relative;

      max-width: 800px;

      margin: auto;

      border-left: 2px solid var(--cyan);

      padding-left: 30px;
    }

    .timeline-item {
      position: relative;

      margin-bottom: 25px;
    }

    .timeline-item:last-child {
      margin-bottom: 0;
    }

    .timeline-item::before {
      content: "";

      position: absolute;

      left: -40px;
      top: 22px;

      width: 16px;
      height: 16px;

      border-radius: 50%;

      background: var(--cyan);

      box-shadow:
        0 0 18px rgba(0,245,255,0.8);
    }

    .timeline-item h3 {
      color: var(--gold);

      margin-bottom: 5px;
    }

    .timeline-item p {
      color: var(--muted);
    }

    /* =========================
       CONTACT
    ========================= */

    .contact-box {
      text-align: center;

      max-width: 750px;

      margin: auto;
    }

    .contact-box p {
      color: var(--muted);

      margin-bottom: 25px;
    }

    .contact-links {
      display: flex;

      flex-wrap: wrap;

      justify-content: center;

      gap: 15px;
    }

    /* =========================
       FOOTER
    ========================= */

    footer {
      text-align: center;

      padding: 30px 20px;

      color: var(--muted);

      font-size: 0.9rem;

      border-top: 1px solid var(--border);
    }

    footer span {
      color: var(--cyan);
    }

    /* =========================
       MOBILE
    ========================= */

    @media (max-width: 700px) {

      nav {
        gap: 15px;

        overflow-x: auto;

        justify-content: flex-start;

        white-space: nowrap;
      }

      nav a {
        font-size: 0.85rem;
      }

      section {
        padding: 75px 0;
      }

      .hero {
        padding-top: 130px;
      }

      .avatar {
        width: 125px;
        height: 125px;

        font-size: 2.8rem;
      }

      .typing {
        font-size: 0.9rem;
      }

      .hero-description {
        font-size: 0.9rem;
      }

      .skills-container {
        grid-template-columns: 1fr;
      }

      .timeline {
        padding-left: 22px;
      }

      .timeline-item::before {
        left: -32px;
      }
    }

    @media (prefers-reduced-motion: reduce) {

      *,
      *::before,
      *::after {
        animation: none !important;

        scroll-behavior: auto !important;
      }

      .typing {
        width: auto;
        border: none;
      }
    }
  </style>
</head>

<body>

  <!-- =========================
       BACKGROUND
  ========================== -->

  <div class="background">
    <div class="orb orb1"></div>
    <div class="orb orb2"></div>
    <div class="orb orb3"></div>
  </div>


  <!-- =========================
       NAVIGATION
  ========================== -->

  <nav>
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="#education">Education</a>
    <a href="#contact">Contact</a>
  </nav>


  <!-- =========================
       HERO
  ========================== -->

  <section class="hero" id="home">

    <div class="avatar">
      HP
    </div>

    <h1>
      Hemanth Pindi
    </h1>

    <div class="typing">
      Computer Engineering Student
    </div>

    <p class="hero-description">
      Passionate about programming, web development and problem solving.
      Learning new technologies, building projects and improving every day.
    </p>

    <div class="buttons">

      <a
        href="#projects"
        class="btn btn-primary">
        View My Projects
      </a>

      <a
        href="#contact"
        class="btn btn-outline">
        Contact Me
      </a>

      <a
        href="https://www.linkedin.com/in/hemanthpindi-08758134b"
        target="_blank"
        rel="noopener noreferrer"
        class="btn btn-outline">
        LinkedIn
      </a>

    </div>

  </section>


  <!-- =========================
       ABOUT
  ========================== -->

  <section id="about">

    <div class="section-title">

      <h2>
        About <span>Me</span>
      </h2>

      <p>
        A little about my education, interests and career goals.
      </p>

    </div>


    <div class="about-grid">

      <div class="card about-card">

        <div class="number">
          01
        </div>

        <h3>
          Education
        </h3>

        <p>
          Pursuing a Diploma in Computer Engineering at
          Sri Vasavi Engineering College.
        </p>

      </div>


      <div class="card about-card">

        <div class="number">
          02
        </div>

        <h3>
          Interests
        </h3>

        <p>
          Interested in programming, web development,
          software development and solving coding problems.
        </p>

      </div>


      <div class="card about-card">

        <div class="number">
          03
        </div>

        <h3>
          Goal
        </h3>

        <p>
          To become a skilled developer by building
          practical projects and continuously learning.
        </p>

      </div>

    </div>

  </section>


  <!-- =========================
       SKILLS
  ========================== -->

  <section id="skills">

    <div class="section-title">

      <h2>
        My <span>Skills</span>
      </h2>

      <p>
        Technologies and areas I am currently learning and working with.
      </p>

    </div>


    <div class="skills-container">

      <div class="card">

        <div class="skill">

          <div class="skill-header">
            <span>HTML & CSS</span>
            <span>80%</span>
          </div>

          <div class="progress">
            <span style="--width:80%"></span>
          </div>

        </div>


        <div class="skill">

          <div class="skill-header">
            <span>Java</span>
            <span>70%</span>
          </div>

          <div class="progress">
            <span style="--width:70%"></span>
          </div>

        </div>


        <div class="skill">

          <div class="skill-header">
            <span>Python</span>
            <span>65%</span>
          </div>

          <div class="progress">
            <span style="--width:65%"></span>
          </div>

        </div>


        <div class="skill">

          <div class="skill-header">
            <span>C Programming</span>
            <span>65%</span>
          </div>

          <div class="progress">
            <span style="--width:65%"></span>
          </div>

        </div>

      </div>


      <div class="card">

        <h3 style="color:var(--gold);margin-bottom:18px;">
          Technologies
        </h3>

        <div class="tags">

          <span class="tag">HTML</span>
          <span class="tag">CSS</span>
          <span class="tag">JavaScript</span>
          <span class="tag">Java</span>
          <span class="tag">Python</span>
          <span class="tag">C</span>
          <span class="tag">MySQL</span>
          <span class="tag">DBMS</span>
          <span class="tag">Git</span>
          <span class="tag">GitHub</span>
          <span class="tag">Problem Solving</span>

        </div>

      </div>

    </div>

  </section>


  <!-- =========================
       PROJECTS
  ========================== -->

  <section id="projects">

    <div class="section-title">

      <h2>
        My <span>Projects</span>
      </h2>

      <p>
        Some of the projects I have worked on while learning and developing my skills.
      </p>

    </div>


    <div class="projects-grid">


      <!-- PROJECT 1 -->

      <div class="card project">

        <div class="project-icon">
          🍲
        </div>

        <h3>
          Flavour Hub
        </h3>

        <p>
          A recipe recommendation website where users can search
          recipes by name or available ingredients, explore categories,
          create accounts and share their own recipes.
        </p>

        <div class="project-tech">

          <span>HTML</span>
          <span>CSS</span>
          <span>JavaScript</span>
          <span>PHP</span>
          <span>MySQL</span>

        </div>

      </div>


      <!-- PROJECT 2 -->

      <div class="card project">

        <div class="project-icon">
          💻
        </div>

        <h3>
          Smart Code Review System
        </h3>

        <p>
          A learning-oriented project designed to analyze source code,
          identify possible issues and provide useful suggestions
          to help students understand and improve their code.
        </p>

        <div class="project-tech">

          <span>React</span>
          <span>JavaScript</span>
          <span>Python</span>
          <span>Flask</span>

        </div>

      </div>


      <!-- PROJECT 3 -->

      <div class="card project">

        <div class="project-icon">
          🚦
        </div>

        <h3>
          Smart Transportation
        </h3>

        <p>
          A transportation-focused project concept that works with
          traffic-related information to support better understanding
          of urban mobility and transportation data.
        </p>

        <div class="project-tech">

          <span>Web</span>
          <span>JavaScript</span>
          <span>Data</span>

        </div>

      </div>


    </div>

  </section>


  <!-- =========================
       EDUCATION
  ========================== -->

  <section id="education">

    <div class="section-title">

      <h2>
        My <span>Journey</span>
      </h2>

      <p>
        My educational journey and current learning path.
      </p>

    </div>


    <div class="timeline">

      <div class="timeline-item card">

        <h3>
          Sri Vasavi Engineering College
        </h3>

        <p>
          Diploma in Computer Engineering
        </p>

        <p>
          Currently pursuing
        </p>

      </div>


      <div class="timeline-item card">

        <h3>
          Computer Science & Programming
        </h3>

        <p>
          Developing skills in Java, Python, C, web development,
          databases and problem solving.
        </p>

      </div>

    </div>

  </section>


  <!-- =========================
       CONTACT
  ========================== -->

  <section id="contact">

    <div class="section-title">

      <h2>
        Let's <span>Connect</span>
      </h2>

      <p>
        Open to learning, collaboration, projects and new opportunities.
      </p>

    </div>


    <div class="card contact-box">

      <p>
        Feel free to connect with me through email, LinkedIn or GitHub.
      </p>


      <div class="contact-links">

        <a
          href="mailto:hemanthpindi02@gmail.com"
          class="btn btn-primary">
          📧 Email Me
        </a>


        <a
          href="https://www.linkedin.com/in/hemanthpindi-08758134b"
          target="_blank"
          rel="noopener noreferrer"
          class="btn btn-outline">
          LinkedIn
        </a>


        <!-- Replace YOUR_GITHUB_USERNAME with your real username -->

        <a
          href="https://github.com/YOUR_GITHUB_USERNAME"
          target="_blank"
          rel="noopener noreferrer"
          class="btn btn-outline">
          GitHub
        </a>

      </div>

    </div>

  </section>


  <!-- =========================
       FOOTER
  ========================== -->

  <footer>

    © 2026
    <span>Hemanth Pindi</span>
    · Built with HTML & CSS

  </footer>


</body>
</html>
