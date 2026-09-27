<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="Modern GitHub developer portfolio" />
  <title>Developer Portfolio | GitHub</title>
  <style>
    :root {
      --bg: #09090b;
      --panel: #111114;
      --panel-2: #18181b;
      --border: #27272a;
      --text: #fafafa;
      --muted: #a1a1aa;
      --accent: #60a5fa;
      --accent-2: #a78bfa;
      --green: #4ade80;
      --shadow: 0 20px 60px rgba(0,0,0,.35);
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont,
        "Segoe UI", sans-serif;
      background:
        radial-gradient(circle at 15% 10%, rgba(96,165,250,.12), transparent 28%),
        radial-gradient(circle at 85% 20%, rgba(167,139,250,.10), transparent 25%),
        var(--bg);
      color: var(--text);
      line-height: 1.6;
    }

    a { color: inherit; text-decoration: none; }

    .container {
      width: min(1120px, calc(100% - 40px));
      margin: auto;
    }

    nav {
      position: sticky;
      top: 0;
      z-index: 20;
      backdrop-filter: blur(18px);
      background: rgba(9,9,11,.72);
      border-bottom: 1px solid rgba(39,39,42,.7);
    }

    .nav-inner {
      height: 70px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .brand {
      font-weight: 800;
      letter-spacing: -.04em;
      font-size: 1.1rem;
    }

    .brand span { color: var(--accent); }

    .nav-links {
      display: flex;
      gap: 24px;
      color: var(--muted);
      font-size: .9rem;
    }

    .nav-links a:hover { color: var(--text); }

    .hero {
      min-height: 720px;
      display: grid;
      place-items: center;
      padding: 90px 0 70px;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.35fr .65fr;
      gap: 70px;
      align-items: center;
    }

    .eyebrow {
      display: inline-flex;
      gap: 8px;
      align-items: center;
      padding: 7px 12px;
      border: 1px solid var(--border);
      border-radius: 999px;
      color: var(--muted);
      background: rgba(255,255,255,.025);
      font-size: .82rem;
      margin-bottom: 22px;
    }

    .dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: var(--green);
      box-shadow: 0 0 14px rgba(74,222,128,.8);
    }

    h1 {
      font-size: clamp(3rem, 7vw, 6.5rem);
      line-height: .95;
      letter-spacing: -.075em;
      max-width: 850px;
    }

    .gradient {
      background: linear-gradient(90deg, var(--accent), var(--accent-2));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .hero-copy {
      margin-top: 28px;
      max-width: 680px;
      color: var(--muted);
      font-size: 1.12rem;
    }

    .buttons {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
      margin-top: 32px;
    }

    .btn {
      padding: 12px 18px;
      border-radius: 10px;
      border: 1px solid var(--border);
      background: var(--panel);
      font-weight: 700;
      transition: .2s ease;
    }

    .btn:hover {
      transform: translateY(-2px);
      border-color: #3f3f46;
    }

    .btn.primary {
      background: var(--text);
      color: #09090b;
      border-color: var(--text);
    }

    .profile-card {
      padding: 26px;
      border: 1px solid var(--border);
      border-radius: 24px;
      background: linear-gradient(145deg, rgba(255,255,255,.07), rgba(255,255,255,.02));
      box-shadow: var(--shadow);
    }

    .avatar {
      width: 130px;
      height: 130px;
      border-radius: 50%;
      margin: 0 auto 22px;
      display: grid;
      place-items: center;
      font-size: 3rem;
      font-weight: 900;
      background: linear-gradient(135deg, var(--accent), var(--accent-2));
      color: white;
      border: 5px solid rgba(255,255,255,.08);
    }

    .profile-card h2 {
      text-align: center;
      font-size: 1.35rem;
    }

    .profile-card p {
      text-align: center;
      color: var(--muted);
      font-size: .9rem;
      margin-top: 4px;
    }

    .stats {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      margin-top: 25px;
      border-top: 1px solid var(--border);
      padding-top: 20px;
      gap: 10px;
    }

    .stat { text-align: center; }
    .stat strong { display: block; font-size: 1.25rem; }
    .stat span { color: var(--muted); font-size: .72rem; }

    section { padding: 100px 0; }

    .section-label {
      color: var(--accent);
      font-size: .8rem;
      font-weight: 800;
      text-transform: uppercase;
      letter-spacing: .14em;
      margin-bottom: 12px;
    }

    .section-title {
      font-size: clamp(2rem, 4vw, 3.4rem);
      letter-spacing: -.055em;
      margin-bottom: 45px;
    }

    .about {
      max-width: 800px;
      color: var(--muted);
      font-size: 1.05rem;
    }

    .skills {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 30px;
    }

    .skill {
      padding: 9px 14px;
      border: 1px solid var(--border);
      background: var(--panel);
      border-radius: 999px;
      font-size: .86rem;
    }

    .projects {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 18px;
    }

    .project {
      position: relative;
      overflow: hidden;
      padding: 28px;
      min-height: 260px;
      border: 1px solid var(--border);
      border-radius: 20px;
      background: var(--panel);
      transition: .25s ease;
    }

    .project:hover {
      transform: translateY(-5px);
      border-color: #3f3f46;
      box-shadow: var(--shadow);
    }

    .project-number {
      color: #52525b;
      font-size: .8rem;
      font-weight: 800;
    }

    .project h3 {
      font-size: 1.45rem;
      margin: 35px 0 10px;
      letter-spacing: -.035em;
    }

    .project p { color: var(--muted); }

    .tech {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
      margin-top: 22px;
    }

    .tech span {
      font-size: .72rem;
      color: var(--muted);
      border: 1px solid var(--border);
      padding: 5px 8px;
      border-radius: 6px;
    }

    .github {
      margin-top: 20px;
      color: var(--accent);
      font-size: .85rem;
      font-weight: 700;
    }

    .contact {
      border: 1px solid var(--border);
      border-radius: 25px;
      padding: 55px;
      background:
        radial-gradient(circle at 100% 0%, rgba(96,165,250,.14), transparent 35%),
        var(--panel);
      text-align: center;
    }

    .contact p {
      color: var(--muted);
      max-width: 650px;
      margin: 0 auto;
    }

    footer {
      border-top: 1px solid var(--border);
      padding: 30px 0;
      color: var(--muted);
      font-size: .82rem;
      text-align: center;
    }

    @media (max-width: 800px) {
      .nav-links { display: none; }
      .hero-grid { grid-template-columns: 1fr; gap: 45px; }
      .hero { min-height: auto; padding-top: 70px; }
      .projects { grid-template-columns: 1fr; }
      .contact { padding: 35px 20px; }
    }
  </style>
</head>

<body>
  <nav>
    <div class="container nav-inner">
      <a class="brand" href="#">dev<span>.</span>portfolio</a>
      <div class="nav-links">
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
      </div>
    </div>
  </nav>

  <main>
    <section class="hero">
      <div class="container hero-grid">
        <div>
          <div class="eyebrow">
            <span class="dot"></span>
            Available for opportunities
          </div>

          <h1>
            Java Full-Stack
            <span class="gradient">Developer.</span>
          </h1>

          <p class="hero-copy">
            I build scalable applications, clean APIs, modern web experiences,
            and AI-powered developer tools using Java, Spring Boot, React,
            TypeScript, Node.js and SQL.
          </p>

          <div class="buttons">
            <a class="btn primary" href="https://github.com/YOUR_USERNAME" target="_blank">
              View GitHub →
            </a>
            <a class="btn" href="#projects">Explore Projects</a>
          </div>
        </div>

        <div class="profile-card">
          <!-- Replace "SB" with your initials or replace the div with your GitHub avatar -->
          <div class="avatar">SB</div>
          <h2>Your Name</h2>
          <p>Software Engineer · Chennai, India</p>

          <div class="stats">
            <div class="stat">
              <strong>Java</strong>
              <span>Backend</span>
            </div>
            <div class="stat">
              <strong>React</strong>
              <span>Frontend</span>
            </div>
            <div class="stat">
              <strong>AI</strong>
              <span>Projects</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="about">
      <div class="container">
        <div class="section-label">01 — About</div>
        <h2 class="section-title">Building things that solve real problems.</h2>

        <p class="about">
          I'm a developer focused on full-stack engineering and backend development.
          I enjoy turning ideas into production-ready applications, working with
          APIs and databases, and exploring AI-assisted development and cloud
          infrastructure.
        </p>
      </div>
    </section>

    <section id="skills">
      <div class="container">
        <div class="section-label">02 — Tech Stack</div>
        <h2 class="section-title">Tools I work with.</h2>

        <div class="skills">
          <span class="skill">Java</span>
          <span class="skill">Spring Boot</span>
          <span class="skill">Hibernate</span>
          <span class="skill">JPA</span>
          <span class="skill">React</span>
          <span class="skill">TypeScript</span>
          <span class="skill">Node.js</span>
          <span class="skill">Next.js</span>
          <span class="skill">JavaScript</span>
          <span class="skill">SQL</span>
          <span class="skill">PostgreSQL</span>
          <span class="skill">MySQL</span>
          <span class="skill">Docker</span>
          <span class="skill">Git</span>
          <span class="skill">GitHub</span>
          <span class="skill">AI / LLM</span>
          <span class="skill">REST APIs</span>
          <span class="skill">Tailwind CSS</span>
        </div>
      </div>
    </section>

    <section id="projects">
      <div class="container">
        <div class="section-label">03 — Featured Projects</div>
        <h2 class="section-title">Things I've built.</h2>

        <div class="projects">
          <article class="project">
            <div class="project-number">PROJECT / 01</div>
            <h3>Farmers' E-Market</h3>
            <p>
              A digital marketplace connecting farmers with local buyers,
              including product listings, price updates, buyer identification,
              chat and order processing.
            </p>
            <div class="tech">
              <span>React</span>
              <span>TypeScript</span>
              <span>Supabase</span>
              <span>PostgreSQL</span>
            </div>
            <a class="github" href="https://github.com/YOUR_USERNAME" target="_blank">
              View repository →
            </a>
          </article>

          <article class="project">
            <div class="project-number">PROJECT / 02</div>
            <h3>AI Infrastructure Copilot</h3>
            <p>
              An AI-powered infrastructure workspace that converts natural
              language into Terraform infrastructure code and helps developers
              review and ship cloud changes.
            </p>
            <div class="tech">
              <span>Next.js</span>
              <span>AI SDK</span>
              <span>Terraform</span>
              <span>TypeScript</span>
            </div>
            <a class="github" href="https://github.com/YOUR_USERNAME" target="_blank">
              View repository →
            </a>
          </article>

          <article class="project">
            <div class="project-number">PROJECT / 03</div>
            <h3>Meeting Scheduler</h3>
            <p>
              A full-stack scheduling platform with authentication, resource
              management, PostgreSQL persistence and smart scheduling workflows.
            </p>
            <div class="tech">
              <span>Next.js</span>
              <span>Drizzle ORM</span>
              <span>PostgreSQL</span>
              <span>OAuth</span>
            </div>
            <a class="github" href="https://github.com/YOUR_USERNAME" target="_blank">
              View repository →
            </a>
          </article>

          <article class="project">
            <div class="project-number">PROJECT / 04</div>
            <h3>AI Developer Assistant</h3>
            <p>
              An AI chatbot exploring RAG, agents, MCP and database-backed
              conversations with streaming responses and structured data.
            </p>
            <div class="tech">
              <span>Next.js</span>
              <span>AI SDK</span>
              <span>Drizzle</span>
              <span>PostgreSQL</span>
            </div>
            <a class="github" href="https://github.com/YOUR_USERNAME" target="_blank">
              View repository →
            </a>
          </article>
        </div>
      </div>
    </section>

    <section id="contact">
      <div class="container">
        <div class="contact">
          <div class="section-label">04 — Let's Connect</div>
          <h2 class="section-title">Have an interesting project?</h2>
          <p>
            I'm interested in software engineering opportunities, backend
            development, full-stack applications and AI-powered products.
          </p>

          <div class="buttons" style="justify-content:center;">
            <a class="btn primary" href="mailto:YOUR_EMAIL@example.com">Email Me</a>
            <a class="btn" href="https://www.linkedin.com/in/YOUR_USERNAME/" target="_blank">
              LinkedIn
            </a>
            <a class="btn" href="https://github.com/YOUR_USERNAME" target="_blank">
              GitHub
            </a>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    © 2026 Your Name · Built with HTML & CSS
  </footer>
</body>
</html>
