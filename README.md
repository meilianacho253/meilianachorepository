# meilianachopage
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Meiliana Choiriyah | Educator & EdTech Specialist</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet" />
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --ink:      #1c1c2e;
      --mid:      #44445a;
      --muted:    #888899;
      --gold:     #b8873a;
      --gold-lt:  #e8c882;
      --gold-bg:  #fdf5e6;
      --teal:     #2a7c6e;
      --teal-lt:  #d4ece8;
      --bg:       #f7f5f0;
      --white:    #ffffff;
      --rule:     #e0dbd0;
      --serif:    'Cormorant Garamond', Georgia, serif;
      --sans:     'Outfit', system-ui, sans-serif;
      --nav-h:    64px;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: var(--sans);
      background: var(--bg);
      color: var(--ink);
      font-size: 15px;
      line-height: 1.7;
    }

    /* ══ NAV ══ */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      height: var(--nav-h);
      background: rgba(247,245,240,.92);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--rule);
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 6vw;
    }
    .nav-brand {
      font-family: var(--serif);
      font-size: 1.3rem;
      font-weight: 600;
      color: var(--ink);
      text-decoration: none;
    }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a {
      font-size: 13.5px;
      font-weight: 500;
      color: var(--mid);
      text-decoration: none;
      letter-spacing: .04em;
      text-transform: uppercase;
      transition: color .2s;
    }
    .nav-links a:hover { color: var(--gold); }
    .hamburger { display: none; flex-direction: column; gap: 5px; cursor: pointer; background: none; border: none; padding: 4px; }
    .hamburger span { display: block; width: 22px; height: 2px; background: var(--ink); border-radius: 2px; transition: .3s; }

    /* ══ HERO ══ */
    #hero {
      min-height: 100vh;
      display: flex; align-items: center;
      padding: calc(var(--nav-h) + 4rem) 6vw 5rem;
      position: relative;
      overflow: hidden;
    }
    .hero-bg {
      position: absolute; inset: 0; z-index: 0;
      background:
        radial-gradient(ellipse 60% 50% at 80% 50%, #e8c88240 0%, transparent 70%),
        radial-gradient(ellipse 50% 60% at 10% 80%, #d4ece840 0%, transparent 60%);
    }
    .hero-content { position: relative; z-index: 1; max-width: 700px; }
    .hero-tag {
      display: inline-flex; align-items: center; gap: .5rem;
      font-size: 12px; font-weight: 600; letter-spacing: .1em; text-transform: uppercase;
      color: var(--gold); border: 1px solid var(--gold-lt);
      padding: .3rem .9rem; border-radius: 20px; background: var(--gold-bg);
      margin-bottom: 1.5rem;
    }
    .hero-tag::before { content: ''; display: block; width: 6px; height: 6px; border-radius: 50%; background: var(--gold); }
    .hero-name {
      font-family: var(--serif);
      font-size: clamp(2.8rem, 6vw, 5rem);
      font-weight: 600;
      line-height: 1.08;
      color: var(--ink);
      margin-bottom: .5rem;
    }
    .hero-name em { font-style: italic; color: var(--gold); }
    .hero-sub {
      font-size: 1.1rem;
      color: var(--mid);
      margin-bottom: 2rem;
      max-width: 520px;
    }
    .hero-cta-row { display: flex; flex-wrap: wrap; gap: 1rem; align-items: center; }
    .btn {
      display: inline-block;
      padding: .7rem 1.8rem;
      border-radius: 4px;
      font-size: 14px; font-weight: 500; letter-spacing: .04em;
      text-decoration: none; transition: .2s;
    }
    .btn-primary {
      background: var(--gold); color: #fff;
    }
    .btn-primary:hover { background: #a07530; }
    .btn-outline {
      border: 1.5px solid var(--gold); color: var(--gold); background: transparent;
    }
    .btn-outline:hover { background: var(--gold-bg); }
    .hero-stats {
      display: flex; gap: 2.5rem; margin-top: 3.5rem;
      padding-top: 2.5rem; border-top: 1px solid var(--rule);
    }
    .stat-num {
      font-family: var(--serif); font-size: 2rem; font-weight: 600; color: var(--ink); line-height: 1;
    }
    .stat-label { font-size: 12px; color: var(--muted); text-transform: uppercase; letter-spacing: .06em; margin-top: .2rem; }

    /* ══ SECTIONS ══ */
    section { padding: 6rem 6vw; }
    section:nth-child(even) { background: var(--white); }

    .section-label {
      font-size: 11.5px; font-weight: 600; letter-spacing: .14em; text-transform: uppercase;
      color: var(--gold); margin-bottom: .6rem;
    }
    .section-title {
      font-family: var(--serif);
      font-size: clamp(1.8rem, 3.5vw, 2.8rem);
      font-weight: 600; line-height: 1.15; color: var(--ink); margin-bottom: .8rem;
    }
    .section-intro { font-size: 15px; color: var(--mid); max-width: 540px; margin-bottom: 3rem; }
    .divider { width: 48px; height: 3px; background: var(--gold); border-radius: 2px; margin-bottom: 2.5rem; }

    /* ══ ABOUT ══ */
    .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: start; }
    .about-text p { color: var(--mid); margin-bottom: 1rem; font-size: 15px; }
    .about-text p:last-child { margin-bottom: 0; }
    .about-sidebar { display: flex; flex-direction: column; gap: 1.5rem; }
    .info-card {
      background: var(--bg); border: 1px solid var(--rule); border-radius: 8px; padding: 1.2rem 1.5rem;
    }
    .info-card-title { font-size: 11px; font-weight: 600; letter-spacing: .1em; text-transform: uppercase; color: var(--muted); margin-bottom: .8rem; }
    .info-item { display: flex; align-items: flex-start; gap: .7rem; margin-bottom: .5rem; font-size: 14px; color: var(--mid); }
    .info-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--gold); margin-top: .55rem; flex-shrink: 0; }

    /* ══ EXPERIENCE ══ */
    .exp-list { display: flex; flex-direction: column; gap: 0; }
    .exp-item {
      display: grid; grid-template-columns: 180px 1fr;
      gap: 0 2.5rem;
      padding: 2rem 0;
      border-bottom: 1px solid var(--rule);
      position: relative;
    }
    .exp-item:first-child { padding-top: 0; }
    .exp-item:last-child { border-bottom: none; }
    .exp-meta { padding-top: .1rem; }
    .exp-date {
      font-size: 12px; font-weight: 600; color: var(--gold); letter-spacing: .06em;
      text-transform: uppercase; margin-bottom: .3rem;
    }
    .exp-org { font-size: 13px; color: var(--muted); line-height: 1.4; }
    .exp-role {
      font-family: var(--serif); font-size: 1.25rem; font-weight: 600; color: var(--ink);
      margin-bottom: .6rem; line-height: 1.2;
    }
    .exp-bullets { list-style: none; padding: 0; }
    .exp-bullets li {
      padding-left: 1.2rem; position: relative;
      font-size: 13.5px; color: var(--mid); margin-bottom: .35rem; line-height: 1.6;
    }
    .exp-bullets li::before {
      content: '▸'; position: absolute; left: 0;
      color: var(--gold); font-size: 10px; top: .3rem;
    }

    /* ══ SKILLS ══ */
    .skills-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 1.5rem; }
    .skill-card {
      background: var(--bg); border: 1px solid var(--rule); border-radius: 10px;
      padding: 1.5rem; transition: border-color .2s, box-shadow .2s;
    }
    .skill-card:hover { border-color: var(--gold-lt); box-shadow: 0 4px 20px rgba(184,135,58,.1); }
    .skill-icon {
      width: 40px; height: 40px; border-radius: 8px;
      background: var(--gold-bg); display: flex; align-items: center; justify-content: center;
      font-size: 18px; margin-bottom: 1rem;
    }
    .skill-card-title { font-weight: 600; font-size: 14.5px; color: var(--ink); margin-bottom: .5rem; }
    .skill-card-desc { font-size: 13px; color: var(--muted); line-height: 1.6; }
    .tag-list { display: flex; flex-wrap: wrap; gap: .4rem; margin-top: .8rem; }
    .tag {
      font-size: 11.5px; padding: .2rem .65rem;
      border-radius: 3px; background: var(--white); border: 1px solid var(--rule);
      color: var(--mid);
    }
    .tag.gold { background: var(--gold-bg); border-color: var(--gold-lt); color: #7a5520; }
    .tag.teal { background: var(--teal-lt); border-color: #a2d4cc; color: var(--teal); }

    /* ══ PROJECTS / AWARDS ══ */
    .award-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; }
    .award-card {
      background: var(--white); border: 1px solid var(--rule); border-radius: 10px;
      padding: 1.5rem; border-top: 3px solid var(--gold);
      transition: box-shadow .2s;
    }
    .award-card:hover { box-shadow: 0 8px 30px rgba(0,0,0,.08); }
    .award-badge {
      display: inline-block; font-size: 11px; font-weight: 600; letter-spacing: .08em;
      text-transform: uppercase; padding: .2rem .7rem; border-radius: 3px;
      background: var(--gold-bg); color: var(--gold); margin-bottom: .8rem;
    }
    .award-title { font-weight: 600; font-size: 14px; color: var(--ink); margin-bottom: .5rem; line-height: 1.4; }
    .award-desc { font-size: 13px; color: var(--muted); line-height: 1.6; }

    /* ══ HONORS ══ */
    .honor-list { display: flex; flex-direction: column; gap: .8rem; max-width: 700px; }
    .honor-item {
      display: flex; align-items: flex-start; gap: 1rem;
      padding: 1rem 1.2rem; background: var(--white);
      border: 1px solid var(--rule); border-radius: 8px;
      transition: border-color .2s;
    }
    .honor-item:hover { border-color: var(--gold-lt); }
    .honor-icon {
      width: 36px; height: 36px; border-radius: 50%;
      background: var(--gold-bg); display: flex; align-items: center; justify-content: center;
      font-size: 16px; flex-shrink: 0;
    }
    .honor-text { font-size: 14px; color: var(--mid); line-height: 1.55; }

    /* ══ CONTACT ══ */
    #contact {
      background: var(--ink);
      color: #fff;
    }
    #contact .section-label { color: var(--gold-lt); }
    #contact .section-title { color: #fff; }
    #contact .section-intro { color: #9999aa; }
    .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: start; }
    .contact-link {
      display: flex; align-items: center; gap: .8rem;
      color: #bbbbc8; text-decoration: none; font-size: 14.5px;
      padding: 1rem; border: 1px solid #ffffff18; border-radius: 8px;
      transition: border-color .2s, color .2s; margin-bottom: .8rem;
    }
    .contact-link:hover { border-color: var(--gold); color: var(--gold-lt); }
    .contact-link-icon {
      width: 36px; height: 36px; border-radius: 8px;
      background: #ffffff12; display: flex; align-items: center; justify-content: center;
      font-size: 16px; flex-shrink: 0;
    }
    .contact-note { font-size: 13px; color: #666677; margin-top: 2rem; }

    /* ══ FOOTER ══ */
    footer {
      background: #131320; color: #44445a;
      text-align: center; padding: 1.5rem;
      font-size: 13px;
    }
    footer a { color: var(--gold); text-decoration: none; }

    /* ══ RESPONSIVE ══ */
    @media (max-width: 768px) {
      .nav-links { display: none; flex-direction: column; position: fixed; top: var(--nav-h); left: 0; right: 0; background: var(--bg); padding: 1.5rem 6vw; border-bottom: 1px solid var(--rule); gap: 1.2rem; }
      .nav-links.open { display: flex; }
      .hamburger { display: flex; }
      .about-grid { grid-template-columns: 1fr; gap: 2rem; }
      .exp-item { grid-template-columns: 1fr; gap: .5rem; }
      .contact-grid { grid-template-columns: 1fr; }
      .hero-stats { gap: 1.5rem; flex-wrap: wrap; }
    }

    /* ══ ANIMATIONS ══ */
    .fade-in { opacity: 0; transform: translateY(24px); transition: opacity .6s ease, transform .6s ease; }
    .fade-in.visible { opacity: 1; transform: none; }
  </style>
</head>
<body>

<!-- ══ NAV ══ -->
<nav>
  <a class="nav-brand" href="#hero">Meiliana C.</a>
  <ul class="nav-links" id="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <button class="hamburger" id="hamburger" aria-label="Toggle menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- ══ HERO ══ -->
<section id="hero">
  <div class="hero-bg"></div>
  <div class="hero-content">
    <div class="hero-tag">Open to Opportunities</div>
    <h1 class="hero-name">Meiliana<br><em>Choiriyah</em></h1>
    <p class="hero-sub">International Educator &amp; Academic Training Specialist — bridging science, pedagogy, and EdTech across 8+ years in international school settings.</p>
    <div class="hero-cta-row">
      <a href="#experience" class="btn btn-primary">View Experience</a>
      <a href="#contact" class="btn btn-outline">Get in Touch</a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="stat-num">8+</div>
        <div class="stat-label">Years Teaching</div>
      </div>
      <div>
        <div class="stat-num">4</div>
        <div class="stat-label">Curricula Taught</div>
      </div>
      <div>
        <div class="stat-num">4×</div>
        <div class="stat-label">STEM Award Wins</div>
      </div>
      <div>
        <div class="stat-num">2</div>
        <div class="stat-label">Degrees</div>
      </div>
    </div>
  </div>
</section>

<!-- ══ ABOUT ══ -->
<section id="about">
  <div class="fade-in">
    <div class="section-label">About Me</div>
    <h2 class="section-title">Educator, Researcher,<br>EdTech Enthusiast</h2>
    <div class="divider"></div>
  </div>
  <div class="about-grid fade-in">
    <div class="about-text">
      <p>I am an International Science and Biology educator with over eight years of experience teaching Upper Primary through High School students under globally recognised curricula — Cambridge IGCSE, AS/A Level, Pearson Edexcel, and the IB MYP Programme.</p>
      <p>My passion lies at the intersection of rigorous science education and innovative pedagogy. I have led research clubs, guided award-winning STEM projects, and managed educational laboratories in some of Indonesia's top international schools.</p>
      <p>Since December 2025, I have been building my career as an <strong>Academic and Training Specialist</strong> at Beeducation Adventures in Malaysia, where I create multimedia-rich educational content, conduct product training, and support EdTech adoption across industries.</p>
      <p>I hold degrees in Biology and Biology Education, and have been recognised as an AFS Global STEM Educator Scholar.</p>
    </div>
    <div class="about-sidebar">
      <div class="info-card">
        <div class="info-card-title">Current Role</div>
        <div class="info-item"><div class="info-dot"></div><div>Academic &amp; Training Specialist<br><span style="font-size:12px;color:#aaa">Beeducation Adventures, Malaysia</span></div></div>
      </div>
      <div class="info-card">
        <div class="info-card-title">Education</div>
        <div class="info-item"><div class="info-dot"></div><div>B.Sc. Biology — IPB University<br><span style="font-size:12px;color:#aaa">GPA 3.37 / 4.00</span></div></div>
        <div class="info-item"><div class="info-dot"></div><div>B.Ed. Biology Education — UT<br><span style="font-size:12px;color:#aaa">GPA 3.58 / 4.00</span></div></div>
      </div>
      <div class="info-card">
        <div class="info-card-title">Contact</div>
        <div class="info-item"><div class="info-dot"></div><div><a href="mailto:meilianacho11@gmail.com" style="color:var(--gold);text-decoration:none">meilianacho11@gmail.com</a></div></div>
        <div class="info-item"><div class="info-dot"></div><div><a href="https://linkedin.com/in/meiliana-choiriyah" style="color:var(--gold);text-decoration:none" target="_blank">LinkedIn Profile</a></div></div>
      </div>
    </div>
  </div>
</section>

<!-- ══ EXPERIENCE ══ -->
<section id="experience">
  <div class="fade-in">
    <div class="section-label">Career Journey</div>
    <h2 class="section-title">Professional Experience</h2>
    <div class="divider"></div>
  </div>
  <div class="exp-list">

    <div class="exp-item fade-in">
      <div class="exp-meta">
        <div class="exp-date">Dec 2025 – Now</div>
        <div class="exp-org">Beeducation Adventures Sdn Bhd<br>Malaysia</div>
      </div>
      <div>
        <div class="exp-role">Academic &amp; Training Specialist</div>
        <ul class="exp-bullets">
          <li>Research and apply latest trends in education technology and EdTech solutions.</li>
          <li>Create multimedia-rich educational content based on tech-pedagogical frameworks.</li>
          <li>Develop creative templates tailored to specific industries; serve as knowledge resource.</li>
          <li>Write academic-focused articles for blog and broadcasting channels.</li>
          <li>Conduct platform onboarding and product training sessions.</li>
          <li>Support Sales &amp; Marketing at conferences and education fairs.</li>
        </ul>
      </div>
    </div>

    <div class="exp-item fade-in">
      <div class="exp-meta">
        <div class="exp-date">Aug – Nov 2025</div>
        <div class="exp-org">Sekolah Victory Plus</div>
      </div>
      <div>
        <div class="exp-role">IB MYP Biology Teacher</div>
        <ul class="exp-bullets">
          <li>Delivered MYP Biology lessons aligned with IB Programme for Year 5 students.</li>
          <li>Designed unit plans and created formative/summative assessments.</li>
          <li>Managed class content and discussion through ManageBac.</li>
        </ul>
      </div>
    </div>

    <div class="exp-item fade-in">
      <div class="exp-meta">
        <div class="exp-date">Jan – Jul 2025</div>
        <div class="exp-org">Pelangi School Bali</div>
      </div>
      <div>
        <div class="exp-role">Upper Primary &amp; Lower Secondary Science Teacher</div>
        <ul class="exp-bullets">
          <li>Taught Science under the IMYC and Pearson Edexcel iLS frameworks.</li>
          <li>Provided ESL and Mathematics tutoring for non-native foreign students.</li>
        </ul>
      </div>
    </div>

    <div class="exp-item fade-in">
      <div class="exp-meta">
        <div class="exp-date">Jul 2019 – Jun 2024</div>
        <div class="exp-org">BINUS SCHOOL Bekasi</div>
      </div>
      <div>
        <div class="exp-role">Biology Lab. Associate Teacher &amp; Research Club Head</div>
        <ul class="exp-bullets">
          <li>Taught Grades 7–12 in lab activities under IGCSE and AS/A Level Cambridge.</li>
          <li>Trained students on STEM projects via Project-Based Learning.</li>
          <li>Led Research Club across Science, Mathematics, and Humanities departments.</li>
          <li>Prepared students for the National Biology Olympiad and ICAS.</li>
          <li>Managed lab equipment, safety, procurement, and vendor communications.</li>
        </ul>
      </div>
    </div>

    <div class="exp-item fade-in">
      <div class="exp-meta">
        <div class="exp-date">Jul 2018 – Jun 2019</div>
        <div class="exp-org">SPK Sekolah Pelita Bangsa</div>
      </div>
      <div>
        <div class="exp-role">Shadow Teacher for Special Needs</div>
        <ul class="exp-bullets">
          <li>Assisted a special needs student in building independence and learning confidence.</li>
          <li>Collaborated with teachers and parents to monitor and support student progress.</li>
        </ul>
      </div>
    </div>

  </div>
</section>

<!-- ══ SKILLS ══ -->
<section id="skills">
  <div class="fade-in">
    <div class="section-label">Expertise</div>
    <h2 class="section-title">Skills &amp; Competencies</h2>
    <div class="divider"></div>
  </div>
  <div class="skills-grid fade-in">

    <div class="skill-card">
      <div class="skill-icon">📚</div>
      <div class="skill-card-title">International Curricula</div>
      <div class="skill-card-desc">5+ years delivering lessons under globally recognised frameworks.</div>
      <div class="tag-list">
        <span class="tag gold">Cambridge IGCSE</span>
        <span class="tag gold">AS/A Level</span>
        <span class="tag gold">IB MYP</span>
        <span class="tag">Pearson Edexcel</span>
        <span class="tag">IMYC</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon">🔬</div>
      <div class="skill-card-title">Laboratory Management</div>
      <div class="skill-card-desc">4+ years running educational labs with certified quality standards.</div>
      <div class="tag-list">
        <span class="tag gold">ISO 17025:2017</span>
        <span class="tag gold">Good Lab Practice</span>
        <span class="tag">Lab Safety</span>
        <span class="tag">Procurement</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon">💻</div>
      <div class="skill-card-title">EdTech &amp; LMS</div>
      <div class="skill-card-desc">Experienced in leading education management platforms.</div>
      <div class="tag-list">
        <span class="tag teal">ManageBac+</span>
        <span class="tag teal">BeEd World</span>
        <span class="tag">Content Creation</span>
        <span class="tag">Product Training</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon">🚀</div>
      <div class="skill-card-title">STEM &amp; Research</div>
      <div class="skill-card-desc">Supervised multiple award-winning national and international research projects.</div>
      <div class="tag-list">
        <span class="tag gold">Project-Based Learning</span>
        <span class="tag">STEM Supervision</span>
        <span class="tag">Scientific Writing</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon">✍️</div>
      <div class="skill-card-title">Academic Writing</div>
      <div class="skill-card-desc">Published academic posters and presented at international conferences.</div>
      <div class="tag-list">
        <span class="tag">Blog Writing</span>
        <span class="tag">Conference Presentation</span>
        <span class="tag">Scientific Posters</span>
      </div>
    </div>

    <div class="skill-card">
      <div class="skill-icon">🌏</div>
      <div class="skill-card-title">Languages &amp; Inclusion</div>
      <div class="skill-card-desc">ESL tutoring and experience supporting students with special needs.</div>
      <div class="tag-list">
        <span class="tag">English (Proficient)</span>
        <span class="tag">Bahasa Indonesia</span>
        <span class="tag">Special Needs Support</span>
      </div>
    </div>

  </div>
</section>

<!-- ══ PROJECTS ══ -->
<section id="projects">
  <div class="fade-in">
    <div class="section-label">Student Work &amp; Recognition</div>
    <h2 class="section-title">STEM Projects Supervised</h2>
    <p class="section-intro">Award-winning research projects guided under Project-Based Learning at BINUS SCHOOL Bekasi.</p>
    <div class="divider"></div>
  </div>
  <div class="award-grid fade-in">

    <div class="award-card">
      <div class="award-badge">🥇 1st Place · SYRA 2020</div>
      <div class="award-title">Double Protection PPE — Chitosan &amp; Herbal Essential Oil</div>
      <div class="award-desc">Antiviral agent through reverse specification technique. STEM Young Research Awards competition winner.</div>
    </div>

    <div class="award-card">
      <div class="award-badge">🥈 2nd Place · SYRA 2021</div>
      <div class="award-title">Green Tea Chitosan Biofilm Solution</div>
      <div class="award-desc">Antiviral and antibacterial packaging protection using natural biofilm-forming properties.</div>
    </div>

    <div class="award-card">
      <div class="award-badge">🥇 1st Place · SYRA 2022</div>
      <div class="award-title">Nebulizer with Air Pollution Filter</div>
      <div class="award-desc">Cellulose from paper waste and Metal-Oxide materials via xerogel and Sol-Gel process.</div>
    </div>

    <div class="award-card">
      <div class="award-badge">🏆 SEAMEO STEM-ED Bangkok</div>
      <div class="award-title">Nebulizer Air Filter from Tissue &amp; Coffee Waste</div>
      <div class="award-desc">International award at STEM Fair &amp; Expo 2023 in Bangkok, Thailand for trapping specific air-pollutant gases.</div>
    </div>

  </div>

  <!-- Honors -->
  <div style="margin-top: 4rem;">
    <div class="section-label" style="margin-bottom:.6rem">Personal Honors</div>
    <h3 style="font-family:var(--serif);font-size:1.6rem;font-weight:600;margin-bottom:1.5rem;">Awards &amp; Scholarships</h3>
    <div class="honor-list fade-in">
      <div class="honor-item">
        <div class="honor-icon">🥇</div>
        <div class="honor-text">1st Place, Business Plan — National Competition "Agrifest 2016", Hasanuddin University, Makassar</div>
      </div>
      <div class="honor-item">
        <div class="honor-icon">🏅</div>
        <div class="honor-text">Top-20 Finalist, Animal Science National Competition, Brawijaya University</div>
      </div>
      <div class="honor-item">
        <div class="honor-icon">🎓</div>
        <div class="honor-text">PPA Scholarship Awardee — Ministry of Research &amp; Technology, Republic of Indonesia</div>
      </div>
      <div class="honor-item">
        <div class="honor-icon">✈️</div>
        <div class="honor-text">AFS Global STEM Educator Scholarship Recipient — AFS Intercultural Programs</div>
      </div>
      <div class="honor-item">
        <div class="honor-icon">📄</div>
        <div class="honor-text">Presenter, International Conference on Mathematics and Science Education 2022 (STEM track)</div>
      </div>
    </div>
  </div>
</section>

<!-- ══ CONTACT ══ -->
<section id="contact">
  <div class="fade-in">
    <div class="section-label">Say Hello</div>
    <h2 class="section-title">Get in Touch</h2>
    <p class="section-intro">I am open to new opportunities in education, EdTech, and curriculum development. Feel free to reach out!</p>
    <div class="divider" style="background:var(--gold)"></div>
  </div>
  <div class="contact-grid fade-in">
    <div>
      <a href="mailto:meilianacho11@gmail.com" class="contact-link">
        <div class="contact-link-icon">📧</div>
        <div>
          <div style="font-size:12px;color:#666;margin-bottom:2px;text-transform:uppercase;letter-spacing:.06em">Email</div>
          meilianacho11@gmail.com
        </div>
      </a>
      <a href="https://linkedin.com/in/meiliana-choiriyah" target="_blank" class="contact-link">
        <div class="contact-link-icon">💼</div>
        <div>
          <div style="font-size:12px;color:#666;margin-bottom:2px;text-transform:uppercase;letter-spacing:.06em">LinkedIn</div>
          linkedin.com/meiliana choiriyah
        </div>
      </a>
      <p class="contact-note">Based in Malaysia · Open to remote and international roles</p>
    </div>
    <div style="color:#9999aa;font-size:14px;line-height:1.8;">
      <p style="font-family:var(--serif);font-size:1.4rem;color:#fff;margin-bottom:1rem;">"Education is not the filling of a pail, but the lighting of a fire."</p>
      <p>With a background spanning laboratory science, international curricula, STEM mentorship, and EdTech content creation, I bring a multidisciplinary perspective to every role.</p>
      <p style="margin-top:1rem;">Currently at Beeducation Adventures in Malaysia, I'm helping shape how educators and industries engage with technology-driven learning.</p>
    </div>
  </div>
</section>

<!-- ══ FOOTER ══ -->
<footer>
  <p>© 2026 Meiliana Choiriyah · Built with ❤️ and hosted on <a href="https://pages.github.com" target="_blank">GitHub Pages</a></p>
</footer>

<script>
  const hamburger = document.getElementById('hamburger');
  const navLinks  = document.getElementById('nav-links');
  hamburger.addEventListener('click', () => navLinks.classList.toggle('open'));
  navLinks.querySelectorAll('a').forEach(a => a.addEventListener('click', () => navLinks.classList.remove('open')));

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
  }, { threshold: 0.12 });
  document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));
</script>
</body>
</html>
