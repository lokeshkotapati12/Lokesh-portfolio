<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Kotapati Lokesh | Portfolio</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    :root {
      --bg: #0f172a;
      --bg-alt: #020617;
      --accent: #38bdf8;
      --accent-soft: rgba(56, 189, 248, 0.1);
      --text: #e5e7eb;
      --muted: #9ca3af;
      --card: #020617;
      --border: #1f2933;
      --radius: 14px;
      --shadow: 0 18px 45px rgba(0, 0, 0, 0.45);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI",
        sans-serif;
      background: radial-gradient(circle at top, #1d283a, #020617 50%, #020617);
      color: var(--text);
      line-height: 1.6;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    /* Layout */
    .page {
      min-height: 100vh;
      max-width: 1100px;
      margin: 0 auto;
      padding: 1.5rem 1.25rem 3rem;
      display: flex;
      flex-direction: column;
      gap: 2rem;
    }

    header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 1rem;
      position: sticky;
      top: 0;
      z-index: 10;
      padding: 0.75rem 1rem;
      margin: -0.75rem -1rem 0;
      backdrop-filter: blur(18px);
      background: linear-gradient(
        to bottom,
        rgba(15, 23, 42, 0.92),
        rgba(15, 23, 42, 0.7),
        transparent
      );
      border-bottom: 1px solid rgba(148, 163, 184, 0.25);
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }

    .avatar {
      width: 38px;
      height: 38px;
      border-radius: 50%;
      background: radial-gradient(circle at 30% 20%, #38bdf8, #0f172a);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 700;
      font-size: 1.05rem;
      border: 2px solid rgba(148, 163, 184, 0.4);
      box-shadow: 0 0 0 1px rgba(15, 23, 42, 0.9);
    }

    .brand-text {
      display: flex;
      flex-direction: column;
      gap: 0.08rem;
    }

    .brand-text strong {
      font-size: 0.95rem;
      letter-spacing: 0.04em;
      text-transform: uppercase;
    }

    .brand-text span {
      font-size: 0.8rem;
      color: var(--muted);
    }

    nav {
      display: flex;
      gap: 0.75rem;
      font-size: 0.85rem;
      flex-wrap: wrap;
      justify-content: flex-end;
    }

    nav a {
      padding: 0.4rem 0.8rem;
      border-radius: 999px;
      border: 1px solid transparent;
      color: var(--muted);
      transition: all 0.18s ease;
    }

    nav a:hover {
      border-color: rgba(148, 163, 184, 0.6);
      color: var(--text);
      background: rgba(15, 23, 42, 0.7);
    }

    /* Hero / Intro */
    .hero {
      display: grid;
      grid-template-columns: minmax(0, 2.1fr) minmax(0, 1.6fr);
      gap: 1.75rem;
      align-items: center;
    }

    .hero-main h1 {
      font-size: clamp(2.1rem, 3vw, 2.5rem);
      line-height: 1.2;
      margin-bottom: 0.6rem;
    }

    .gradient-text {
      background: linear-gradient(120deg, #38bdf8, #a855f7);
      -webkit-background-clip: text;
      color: transparent;
    }

    .hero-main h2 {
      font-size: 1rem;
      text-transform: uppercase;
      letter-spacing: 0.28em;
      color: var(--muted);
      margin-bottom: 0.8rem;
    }

    .hero-main p {
      color: #d1d5db;
      font-size: 0.96rem;
      max-width: 32rem;
      margin-bottom: 1.5rem;
    }

    .hero-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
      margin-bottom: 1.6rem;
    }

    .pill {
      font-size: 0.76rem;
      padding: 0.35rem 0.75rem;
      border-radius: 999px;
      background: rgba(15, 23, 42, 0.9);
      border: 1px solid rgba(148, 163, 184, 0.35);
      color: var(--muted);
      display: inline-flex;
      align-items: center;
      gap: 0.35rem;
    }

    .pill-dot {
      width: 7px;
      height: 7px;
      border-radius: 999px;
      background: #22c55e;
      box-shadow: 0 0 0 4px rgba(34, 197, 94, 0.25);
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem;
    }

    .btn {
      border-radius: 999px;
      padding: 0.6rem 1.2rem;
      border: 1px solid rgba(148, 163, 184, 0.6);
      font-size: 0.9rem;
      cursor: pointer;
      background: transparent;
      color: var(--text);
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      transition: all 0.18s ease;
    }

    .btn-primary {
      background: radial-gradient(circle at 0 0, #38bdf8, #0f172a);
      border-color: transparent;
      box-shadow: 0 18px 35px rgba(15, 23, 42, 0.9);
    }

    .btn-primary:hover {
      transform: translateY(-1px);
      box-shadow: 0 22px 45px rgba(15, 23, 42, 1);
    }

    .btn-outline:hover {
      background: rgba(15, 23, 42, 0.9);
    }

    .hero-sidecard {
      border-radius: var(--radius);
      padding: 1.3rem 1.2rem;
      background: radial-gradient(circle at top, #0b1120, #020617);
      border: 1px solid rgba(148, 163, 184, 0.45);
      box-shadow: var(--shadow);
      display: flex;
      flex-direction: column;
      gap: 0.7rem;
    }

    .hero-sidecard h3 {
      font-size: 0.95rem;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: var(--muted);
    }

    .hero-metadata {
      display: grid;
      grid-template-columns: 1.2fr 1.8fr;
      font-size: 0.82rem;
      gap: 0.4rem 1rem;
    }

    .hero-metadata div span {
      display: block;
    }

    .hero-metadata label {
      font-size: 0.78rem;
      text-transform: uppercase;
      letter-spacing: 0.14em;
      color: var(--muted);
      margin-bottom: 0.1rem;
    }

    .hero-metadata strong {
      color: #e5e7eb;
    }

    .hero-badges {
      display: flex;
      gap: 0.5rem;
      flex-wrap: wrap;
      margin-top: 0.3rem;
    }

    .hero-badges .pill {
      background: var(--accent-soft);
      border-color: rgba(56, 189, 248, 0.5);
      color: #e0f2fe;
    }

    /* Section shell */
    section {
      border-radius: var(--radius);
      background: radial-gradient(circle at top left, #020617, #020617);
      border: 1px solid rgba(15, 23, 42, 0.9);
      box-shadow: var(--shadow);
      padding: 1.4rem 1.35rem 1.5rem;
    }

    section + section {
      margin-top: 0.5rem;
    }

    .section-header {
      display: flex;
      align-items: baseline;
      justify-content: space-between;
      margin-bottom: 1rem;
      gap: 0.5rem;
      flex-wrap: wrap;
    }

    .section-header h2 {
      font-size: 1.05rem;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: var(--muted);
    }

    .section-header p {
      font-size: 0.82rem;
      color: var(--muted);
    }

    /* Skills */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 0.85rem;
      font-size: 0.88rem;
    }

    .skill-card {
      background: linear-gradient(
        145deg,
        rgba(15, 23, 42, 0.95),
        rgba(15, 23, 42, 0.9)
      );
      border-radius: 12px;
      border: 1px solid rgba(51, 65, 85, 0.9);
      padding: 0.75rem 0.8rem;
    }

    .skill-card h3 {
      font-size: 0.9rem;
      margin-bottom: 0.3rem;
    }

    .skill-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.35rem;
      margin-top: 0.2rem;
    }

    .skill-tags span {
      font-size: 0.78rem;
      padding: 0.25rem 0.6rem;
      border-radius: 999px;
      background: #020617;
      border: 1px solid rgba(55, 65, 81, 0.95);
      color: var(--muted);
    }

    /* Projects */
    .projects {
      display: grid;
      gap: 0.85rem;
    }

    .project-card {
      display: grid;
      grid-template-columns: minmax(0, 2.2fr) minmax(0, 1.4fr);
      gap: 0.8rem;
      padding: 0.9rem 0.95rem;
      border-radius: 12px;
      border: 1px solid rgba(55, 65, 81, 0.95);
      background: linear-gradient(
        140deg,
        rgba(15, 23, 42, 0.98),
        rgba(15, 23, 42, 0.92)
      );
    }

    .project-header {
      display: flex;
      justify-content: space-between;
      gap: 0.4rem;
      margin-bottom: 0.2rem;
    }

    .project-title {
      font-weight: 600;
      font-size: 0.95rem;
    }

    .tech-label {
      font-size: 0.75rem;
      padding: 0.2rem 0.6rem;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.5);
      color: var(--muted);
      white-space: nowrap;
      align-self: flex-start;
    }

    .project-body p {
      font-size: 0.85rem;
      color: #d1d5db;
      margin-bottom: 0.4rem;
    }

    .project-highlights {
      font-size: 0.8rem;
      color: var(--muted);
      padding-left: 1rem;
    }

    .project-highlights li {
      margin-bottom: 0.08rem;
    }

    .project-meta {
      font-size: 0.78rem;
      color: var(--muted);
      border-radius: 10px;
      padding: 0.7rem 0.7rem;
      background: radial-gradient(circle at 0 0, #0b1120, #020617);
      border: 1px dashed rgba(75, 85, 99, 0.9);
      display: flex;
      flex-direction: column;
      gap: 0.4rem;
    }

    .project-meta-row {
      display: flex;
      justify-content: space-between;
      gap: 0.5rem;
      flex-wrap: wrap;
    }

    .project-meta-row span {
      white-space: nowrap;
    }

    /* Contact */
    .contact-layout {
      display: grid;
      grid-template-columns: minmax(0, 1.7fr) minmax(0, 1.4fr);
      gap: 1rem;
    }

    form {
      display: grid;
      gap: 0.7rem;
      font-size: 0.86rem;
    }

    label {
      font-size: 0.78rem;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.16em;
      margin-bottom: 0.15rem;
      display: block;
    }

    input,
    textarea {
      width: 100%;
      border-radius: 10px;
      border: 1px solid rgba(55, 65, 81, 0.9);
      padding: 0.55rem 0.7rem;
      background: rgba(15, 23, 42, 0.95);
      color: var(--text);
      font: inherit;
      resize: vertical;
      min-height: 40px;
    }

    input:focus,
    textarea:focus {
      outline: none;
      border-color: var(--accent);
      box-shadow: 0 0 0 1px rgba(56, 189, 248, 0.6);
    }

    textarea {
      min-height: 110px;
    }

    .contact-info {
      font-size: 0.9rem;
      color: var(--muted);
      display: flex;
      flex-direction: column;
      gap: 0.6rem;
    }

    .contact-info h3 {
      font-size: 0.9rem;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      color: var(--muted);
      margin-bottom: 0.1rem;
    }

    .contact-line {
      display: flex;
      justify-content: space-between;
      gap: 0.5rem;
      flex-wrap: wrap;
    }

    .contact-info a {
      color: #e0f2fe;
      text-decoration: underline;
      text-decoration-style: dotted;
    }

    footer {
      margin-top: 1.5rem;
      font-size: 0.75rem;
      color: var(--muted);
      text-align: center;
      opacity: 0.9;
    }

    /* Responsive */
    @media (max-width: 800px) {
      .hero {
        grid-template-columns: minmax(0, 1fr);
      }

      .project-card {
        grid-template-columns: minmax(0, 1fr);
      }

      .contact-layout {
        grid-template-columns: minmax(0, 1fr);
      }

      header {
        flex-direction: column;
        align-items: flex-start;
      }

      nav {
        justify-content: flex-start;
      }
    }

    @media (max-width: 480px) {
      .page {
        padding-inline: 1rem;
      }

      section {
        padding-inline: 1rem;
      }

      header {
        padding-inline: 0.75rem;
      }
    }
  </style>
</head>
<body>
  <div class="page">
    <header>
      <div class="brand">
        <div class="avatar">KL</div>
        <div class="brand-text">
          <strong>Kotapati Lokesh</strong>
          <span>ECE | Python | Web Dev</span>
        </div>
      </div>
      <nav>
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
      </nav>
    </header>

    <!-- Hero / About -->
    <section id="about">
      <div class="hero">
        <div class="hero-main">
          <h2>Hyderabad • B.Tech ECE</h2>
          <h1>
            Hi, I'm <span class="gradient-text">Lokesh</span> — a
            dedicated Electronics & Communication Engineering student with
            a passion for building useful digital experiences.
          </h1>
          <p>
            I'm a motivated B.Tech student in Electronics and Communication
            Engineering, with a strong foundation in IoT and Embedded Systems
            and hands-on experience in web development. I enjoy turning ideas
            into working solutions using technologies like Python, C/C++,
            HTML, CSS, JavaScript and ARM-based systems, while collaborating in
            teams and solving real-world problems efficiently.
          </p>

          <div class="hero-tags">
            <div class="pill">
              <span class="pill-dot"></span> Open to full-time roles
            </div>
            <div class="pill">IoT & Embedded Enthusiast</div>
            <div class="pill">Front-End Development</div>
          </div>

          <div class="hero-actions">
            <a href="#contact" class="btn btn-primary">Contact Me</a>
            <a href="#projects" class="btn btn-outline">View Projects</a>
          </div>
        </div>

        <aside class="hero-sidecard">
          <h3>Snapshot</h3>
          <div class="hero-metadata">
            <div>
              <label>Current Degree</label>
              <strong>B.Tech, ECE</strong>
            </div>
            <div>
              <label>College</label>
              <strong>Malla Reddy College of Engineering</strong>
            </div>
            <div>
              <label>Location</label>
              <strong>Hyderabad, India</strong>
            </div>
            <div>
              <label>Contact</label>
              <strong>+91 93461 18394</strong>
            </div>
          </div>
          <div>
            <label>Strengths</label>
            <div class="hero-badges">
              <span class="pill">Problem-Solving</span>
              <span class="pill">Team Collaboration</span>
              <span class="pill">Communication</span>
              <span class="pill">Continuous Learning</span>
            </div>
          </div>
        </aside>
      </div>
    </section>

    <!-- Skills -->
    <section id="skills">
      <div class="section-header">
        <h2>Skills</h2>
        <p>Technologies and tools I have worked with.</p>
      </div>
      <div class="skills-grid">
        <div class="skill-card">
          <h3>Programming & Scripting</h3>
          <p>Writing clean, readable and efficient code for projects.</p>
          <div class="skill-tags">
            <span>Python</span>
            <span>C</span>
            <span>C++</span>
            <span>.NET</span>
          </div>
        </div>

        <div class="skill-card">
          <h3>Web Development</h3>
          <p>Building responsive and user-friendly web interfaces.</p>
          <div class="skill-tags">
            <span>HTML</span>
            <span>CSS</span>
            <span>JavaScript</span>
            <span>Bootstrap</span>
          </div>
        </div>

        <div class="skill-card">
          <h3>Embedded & IoT</h3>
          <p>Working with hardware, sensors and communication protocols.</p>
          <div class="skill-tags">
            <span>IoT Concepts</span>
            <span>Embedded Systems</span>
            <span>ARM Processors</span>
            <span>UART</span>
            <span>I²C</span>
          </div>
        </div>

        <div class="skill-card">
          <h3>Other Tools & Platforms</h3>
          <p>Using additional tools to support development and learning.</p>
          <div class="skill-tags">
            <span>SAP ABAP (Basics)</span>
            <span>Git / GitHub</span>
            <span>VS Code</span>
            <span>Linux (Basics)</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Projects -->
    <section id="projects">
      <div class="section-header">
        <h2>Projects</h2>
        <p>Some of the things I've built and worked on.</p>
      </div>

      <div class="projects">
        <!-- Project 1 -->
        <article class="project-card">
          <div class="project-body">
            <div class="project-header">
              <div class="project-title">Food Munch – Online Food Ordering Site</div>
              <div class="tech-label">HTML • CSS • JavaScript</div>
            </div>
            <p>
              A responsive website for exploring menus and placing online
              food orders, designed to give users a smooth and intuitive
              experience across devices.
            </p>
            <ul class="project-highlights">
              <li>Built front-end using semantic HTML, modern CSS and JavaScript.</li>
              <li>Designed user-friendly pages for browsing restaurants and dishes.</li>
              <li>Integrated basic back-end flows for ordering and payment steps.</li>
              <li>Focused on clear layout, easy navigation and performance.</li>
            </ul>
          </div>
          <aside class="project-meta">
            <div class="project-meta-row">
              <span><strong>Role:</strong> Solo Developer</span>
              <span><strong>Type:</strong> Full-stack Prototype</span>
            </div>
            <div class="project-meta-row">
              <span><strong>Focus:</strong> UX, front-end logic</span>
              <span><strong>Status:</strong> Completed</span>
            </div>
            <div>
              <em>Future improvements:</em> integrate real payment gateway, add live order tracking.
            </div>
          </aside>
        </article>

        <!-- Project 2 -->
        <article class="project-card">
          <div class="project-body">
            <div class="project-header">
              <div class="project-title">Interactive Real Estate Showcase</div>
              <div class="tech-label">HTML • CSS • JS • Bootstrap</div>
            </div>
            <p>
              A visually rich real estate website that lets users explore
              property listings interactively, with smooth navigation and
              clear presentation of key details.
            </p>
            <ul class="project-highlights">
              <li>Implemented dynamic section navigation using JavaScript.</li>
              <li>Created a responsive layout with Bootstrap and custom CSS.</li>
              <li>Used animations and hover effects to highlight key content.</li>
              <li>Showcased pricing, locations and booking options in a clean UI.</li>
            </ul>
          </div>
          <aside class="project-meta">
            <div class="project-meta-row">
              <span><strong>Role:</strong> Front-End Developer</span>
              <span><strong>Type:</strong> Web UI Project</span>
            </div>
            <div class="project-meta-row">
              <span><strong>Focus:</strong> Responsiveness, interactivity</span>
              <span><strong>Status:</strong> Completed</span>
            </div>
            <div>
              <em>Future improvements:</em> connect with real APIs for listings and maps.
            </div>
          </aside>
        </article>
      </div>
    </section>

    <!-- Contact -->
    <section id="contact">
      <div class="section-header">
        <h2>Contact</h2>
        <p>Have an opportunity or idea? Feel free to reach out.</p>
      </div>

      <div class="contact-layout">
        <form
          action="https://formspree.io/f/your-form-id"
          method="POST"
        >
          <!-- Replace the action URL above with your own form endpoint -->
         <div>
            <label for="name">Name</label>
            <input
              id="name"
              name="name"
              type="text"
              placeholder="Your name"
              required
            />
          </div>
          <div>
            <label for="email">Email</label>
            <input
              id="email"
              name="email"
              type="email"
              placeholder="you@example.com"
              required
            />
          </div>
          <div>
            <label for="subject">Subject</label>
            <input
              id="subject"
              name="subject"
              type="text"
              placeholder="What is this about?"
              required
            />
          </div>
          <div>
            <label for="message">Message</label>
            <textarea
              id="message"
              name="message"
              placeholder="Write your message here..."
              required
            ></textarea>
          </div>
          <button type="submit" class="btn btn-primary">
            Send Message
          </button>
        </form>

        <div class="contact-info">
          <h3>Direct Contact</h3>
          <div class="contact-line">
            <span>Email</span>
            <a href="mailto:lokeshkotapati4@gmail.com"
              >lokeshkotapati4@gmail.com</a
            >
          </div>
          <div class="contact-line">
            <span>Phone</span>
            <span>+91 93461 18394</span>
          </div>
          <div class="contact-line">
            <span>Location</span>
            <span>Hyderabad, Telangana, India</span>
          </div>
          <div>
            <h3 style="margin-top: 0.8rem;">What I'm looking for</h3>
            <p>
              I’m interested in opportunities related to software development,
              front-end engineering, IoT/embedded systems and related
              roles where I can learn, contribute and grow with the team.
            </p>
          </div>
        </div>
      </div>
    </section>

    <footer>
      © <span id="year"></span> Kotapati Lokesh. Built with HTML, CSS &amp; passion for learning.
    </footer>
  </div>

  <script>
    // Set current year in footer
    document.getElementById("year").textContent = new Date().getFullYear();
  </script>
</body>
</html>
