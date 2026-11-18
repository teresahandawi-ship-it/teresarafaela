<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Teresa Rafaela — Portfolio</title>
<style>
  :root {
    --cream: #f6f1e7;
    --beige: #ece3d2;
    --sand: #e2d5bd;
    --card: #fdfaf3;
    --ink: #3b332a;
    --muted: #7d7264;
    --accent: #a9845b;
    --accent-deep: #8a6a45;
    --terracotta: #b3704f;
  }
  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }
  body {
    font-family: Georgia, 'Times New Roman', serif;
    background: var(--cream);
    color: var(--ink);
    line-height: 1.75;
  }

  /* ---------- Nav ---------- */
  nav {
    position: fixed; top: 0; width: 100%;
    background: rgba(246,241,231,.9);
    backdrop-filter: blur(8px);
    border-bottom: 1px solid var(--sand);
    display: flex; justify-content: space-between; align-items: center;
    padding: 16px 6vw; z-index: 100;
  }
  nav .logo { font-weight: bold; font-size: 1.15rem; color: var(--accent-deep); letter-spacing: 1px; }
  nav ul { display: flex; gap: 30px; list-style: none; }
  nav a { text-decoration: none; color: var(--ink); font-size: .95rem; transition: color .2s; }
  nav a:hover { color: var(--terracotta); }

  /* ---------- Hero ---------- */
  header {
    min-height: 100vh;
    display: flex; flex-direction: column; justify-content: center;
    padding: 0 8vw;
    background:
      radial-gradient(ellipse at 85% 15%, rgba(169,132,91,.14), transparent 55%),
      radial-gradient(ellipse at 10% 90%, rgba(179,112,79,.12), transparent 50%),
      var(--cream);
  }
  .hello { color: var(--terracotta); letter-spacing: 4px; text-transform: uppercase; font-size: .85rem; }
  h1 { font-size: clamp(2.8rem, 7vw, 5rem); line-height: 1.1; margin: 16px 0 22px; font-weight: normal; }
  h1 em { font-style: italic; color: var(--accent-deep); }
  .tagline { max-width: 580px; color: var(--muted); font-size: 1.15rem; }
  .btn {
    display: inline-block; margin-top: 38px; padding: 14px 36px;
    background: var(--accent-deep); color: #fdfaf3; text-decoration: none;
    border-radius: 40px; font-size: .98rem; transition: .25s;
  }
  .btn:hover { background: var(--terracotta); transform: translateY(-2px); }
  .btn.ghost { background: transparent; color: var(--accent-deep); border: 1.5px solid var(--accent-deep); margin-left: 12px; }
  .btn.ghost:hover { background: var(--accent-deep); color: #fdfaf3; }

  /* ---------- Sections ---------- */
  section { padding: 100px 8vw; }
  h2 { font-size: 2.1rem; font-weight: normal; margin-bottom: 6px; }
  h2 em { font-style: italic; color: var(--accent-deep); }
  .sub { color: var(--muted); margin-bottom: 46px; }
  .accent-line { width: 60px; height: 4px; background: var(--accent); border-radius: 2px; margin-bottom: 18px; }

  /* About */
  #about { background: var(--beige); }
  .about-grid { display: grid; grid-template-columns: 1.3fr 1fr; gap: 48px; align-items: start; }
  .fact-box { background: var(--card); border: 1px solid var(--sand); border-radius: 16px; padding: 30px; box-shadow: 0 8px 30px rgba(59,51,42,.07); }
  .fact-box h3 { color: var(--accent-deep); margin-bottom: 16px; font-size: 1.05rem; letter-spacing: 1px; text-transform: uppercase; }
  .fact-box li { margin: 10px 0 10px 20px; list-style: none; }
  .fact-box li::before { content: "—"; color: var(--terracotta); margin-right: 8px; }

  /* Projects */
  .cards { display: grid; grid-template-columns: repeat(auto-fit, minmax(270px, 1fr)); gap: 28px; }
  .card {
    background: var(--card); border: 1px solid var(--sand); border-radius: 16px; overflow: hidden;
    box-shadow: 0 8px 30px rgba(59,51,42,.07); transition: .25s;
  }
  .card:hover { transform: translateY(-6px); box-shadow: 0 14px 40px rgba(59,51,42,.12); }
  .card .thumb { height: 150px; display: flex; align-items: center; justify-content: center; font-size: 2.8rem; }
  .card .body { padding: 24px; }
  .card h3 { margin-bottom: 8px; font-size: 1.15rem; }
  .card p { color: var(--muted); font-size: .95rem; }
  .card .link { display: inline-block; margin-top: 14px; color: var(--terracotta); font-size: .9rem; text-decoration: none; }
  .card .link:hover { text-decoration: underline; }
  .tags { margin-top: 14px; }
  .tags span {
    display: inline-block; background: var(--beige); color: var(--accent-deep);
    font-size: .78rem; padding: 4px 12px; border-radius: 20px; margin: 3px 4px 0 0;
  }

  /* Skills */
  #skills { background: var(--beige); }
  .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 40px; }
  .skill { margin-bottom: 22px; }
  .skill .bar { background: #d9cbb2; border-radius: 10px; height: 12px; overflow: hidden; }
  .skill .fill { background: linear-gradient(90deg, var(--accent), var(--terracotta)); height: 100%; border-radius: 10px; }
  .skill .label { display: flex; justify-content: space-between; font-size: .95rem; margin-bottom: 6px; }

  /* Contact */
  #contact { text-align: center; background: var(--sand); }
  #contact .accent-line { margin: 0 auto 18px; }
  #contact .btn { margin: 8px; }
  footer { text-align: center; padding: 30px; color: var(--muted); font-size: .85rem; background: var(--sand); }

  @media (max-width: 720px) {
    .about-grid { grid-template-columns: 1fr; }
    nav ul { gap: 16px; }
    .btn.ghost { margin-left: 0; margin-top: 12px; }
  }
</style>
<base target="_blank">
</head>
<body>

<nav>
  <div class="logo">Teresa Rafaela</div>
  <ul>
    <li><a href="#about">About</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<header>
  <p class="hello">Hello, I'm</p>
  <h1>Teresa Rafaela —<br><em>data with a marketing instinct.</em></h1>
  <p class="tagline">Marketing Analytics & Information Management major at City University of Hong Kong, originally from Indonesia. I like turning raw numbers into stories people actually want to hear.</p>
  <a class="btn" href="#projects">See my work</a>
  <a class="btn ghost" href="mailto:teresahandawi@gmail.com">Say hello</a>
</header>

<section id="about">
  <div class="accent-line"></div>
  <h2>About <em>Me</em></h2>
  <p class="sub">Indonesia → Hong Kong, via data.</p>
  <div class="about-grid">
    <div>
      <p>I'm a Marketing Analytics and Information Management student at CityUHK. My sweet spot is the overlap: the analytical side of business — databases, SQL, and data modeling — mixed with the human side of marketing — understanding why people buy, click, and stay.</p>
      <br>
      <p>Right now I'm deepening my technical foundations (database design, advanced SQL) while keeping one eye on how analytics drives real marketing decisions. I'm looking for internships where I can do both.</p>
    </div>
    <div class="fact-box">
      <h3>Quick Facts</h3>
      <ul>
        <li>📍 Hong Kong · from Indonesia 🇮🇩</li>
        <li>🎓 Marketing Analytics & Information Management, CityUHK</li>
        <li>🗄️ Currently diving into: database design & advanced SQL</li>
        <li>💼 Open to: internships in analytics & marketing</li>
      </ul>
    </div>
  </div>
</section>

<section id="projects">
  <div class="accent-line"></div>
  <h2>Selected <em>Projects</em></h2>
  <p class="sub">A few things I've built. (Two of these are drafts — swap in your real projects anytime.)</p>
  <div class="cards">
    <div class="card">
      <div class="thumb" style="background:#e9dcc4;">🪑</div>
      <div class="body">
        <h3>Pine Valley Furniture Database</h3>
        <p>Designed a full relational database for a furniture company: ER modeling, EER extensions, normalization, and advanced SQL queries in Oracle LiveSQL. The project that made databases click for me.</p>
        <div class="tags"><span>SQL</span><span>ER / EER Modeling</span><span>Oracle LiveSQL</span></div>
      </div>
    </div>
    <div class="card">
      <div class="thumb" style="background:#efe6d2;">📈</div>
      <div class="body">
        <h3>Marketing Campaign Analysis</h3>
        <p>Replace me with a real project — e.g. a campaign performance dashboard, A/B test analysis, or a market research study you did for class. One or two sentences: what you analyzed and what you found.</p>
        <div class="tags"><span>Excel</span><span>Data Visualization</span><span>Marketing</span></div>
      </div>
    </div>
    <div class="card">
      <div class="thumb" style="background:#e4d8c0;">🧭</div>
      <div class="body">
        <h3>Your Next Project</h3>
        <p>Replace me too — maybe a Python data-cleaning script, a Tableau/Power BI dashboard, or a group consulting project. Coursework counts if you made it your own.</p>
        <div class="tags"><span>Python</span><span>Tableau / Power BI</span></div>
      </div>
    </div>
  </div>
</section>

<section id="skills">
  <div class="accent-line"></div>
  <h2>Skills & <em>Tools</em></h2>
  <p class="sub">What I work with. Adjust the bars to match you.</p>
  <div class="skills-grid">
    <div>
      <div class="skill">
        <div class="label"><span>SQL & Databases</span><span>85%</span></div>
        <div class="bar"><div class="fill" style="width:85%;"></div></div>
      </div>
      <div class="skill">
        <div class="label"><span>Data Modeling (ER / EER)</span><span>80%</span></div>
        <div class="bar"><div class="fill" style="width:80%;"></div></div>
      </div>
      <div class="skill">
        <div class="label"><span>Excel & Data Analysis</span><span>85%</span></div>
        <div class="bar"><div class="fill" style="width:85%;"></div></div>
      </div>
    </div>
    <div>
      <div class="skill">
        <div class="label"><span>Marketing Analytics</span><span>75%</span></div>
        <div class="bar"><div class="fill" style="width:75%;"></div></div>
      </div>
      <div class="skill">
        <div class="label"><span>Python</span><span>60%</span></div>
        <div class="bar"><div class="fill" style="width:60%;"></div></div>
      </div>
      <div class="skill">
        <div class="label"><span>Presentation & Storytelling</span><span>90%</span></div>
        <div class="bar"><div class="fill" style="width:90%;"></div></div>
      </div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="accent-line"></div>
  <h2>Let's <em>Connect</em></h2>
  <p class="sub" style="margin-bottom:32px;">Open to internships, projects, and a good coffee chat.</p>
  <a class="btn" href="mailto:teresahandawi@gmail.com">teresahandawi@gmail.com</a>
  <a class="btn ghost" href="https://www.linkedin.com/in/YOUR-LINKEDIN" target="_blank">LinkedIn</a>
  <a class="btn ghost" href="https://github.com/YOUR-USERNAME" target="_blank">GitHub</a>
</section>

<footer>© 2026 Teresa Rafaela · Hong Kong</footer>

</body>
</html>
