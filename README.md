
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Santhosh Kumar's personal portfolio website">
    <title>Santhosh Kumar | Portfolio</title>

    <style>
        /* THEME COLORS */
        :root {
            --bg: #f7f7f5;
            --surface: #ffffff;
            --text: #202020;
            --muted: #666666;
            --accent: #ff6b35;
            --border: #e5e5e5;
            --nav: rgba(255, 255, 255, 0.94);
            --shadow: 0 8px 28px rgba(0, 0, 0, 0.06);
        }

        body.dark-theme {
            --bg: #101116;
            --surface: #1b1d25;
            --text: #f5f5f5;
            --muted: #b0b0bc;
            --accent: #ff895e;
            --border: #343640;
            --nav: rgba(16, 17, 22, 0.95);
            --shadow: 0 8px 28px rgba(0, 0, 0, 0.2);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
            scroll-padding-top: 85px;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            background: var(--bg);
            color: var(--text);
            line-height: 1.6;
            transition: background 0.3s, color 0.3s;
        }

        a {
            color: inherit;
            text-decoration: none;
        }

        button {
            font: inherit;
        }

        .container {
            width: min(1100px, 90%);
            margin: auto;
        }

        /* NAVIGATION */
        header {
            position: sticky;
            top: 0;
            z-index: 100;
            background: var(--nav);
            backdrop-filter: blur(12px);
            border-bottom: 1px solid var(--border);
        }

        nav {
            min-height: 75px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 20px;
        }

        .logo {
            font-size: 23px;
            font-weight: 800;
            white-space: nowrap;
        }

        .logo span {
            color: var(--accent);
        }

        .nav-right {
            display: flex;
            align-items: center;
            gap: 22px;
        }

        .nav-links {
            display: flex;
            align-items: center;
            gap: 20px;
            list-style: none;
        }

        .nav-links a {
            color: var(--muted);
            font-size: 14px;
            font-weight: 600;
        }

        .nav-links a:hover {
            color: var(--accent);
        }

        .theme-toggle {
            padding: 10px 14px;
            background: var(--surface);
            color: var(--text);
            border: 1px solid var(--border);
            border-radius: 30px;
            cursor: pointer;
            white-space: nowrap;
            font-size: 13px;
            font-weight: 700;
        }

        .theme-toggle:hover {
            border-color: var(--accent);
        }

        /* HERO */
        .hero {
            min-height: 75vh;
            display: flex;
            align-items: center;
            padding: 75px 0;
        }

        .hero-content {
            max-width: 760px;
        }

        .eyebrow {
            display: inline-block;
            color: var(--accent);
            background: var(--surface);
            border: 1px solid var(--border);
            padding: 7px 14px;
            border-radius: 30px;
            font-size: 13px;
            font-weight: 700;
            margin-bottom: 24px;
        }

        h1 {
            font-size: clamp(38px, 7vw, 76px);
            line-height: 1.08;
            letter-spacing: -2px;
            margin-bottom: 22px;
        }

        h1 span {
            color: var(--accent);
        }

        .hero p {
            max-width: 620px;
            color: var(--muted);
            font-size: 17px;
            margin-bottom: 30px;
        }

        .buttons {
            display: flex;
            flex-wrap: wrap;
            gap: 14px;
        }

        .btn {
            display: inline-block;
            padding: 13px 22px;
            border-radius: 8px;
            font-weight: 700;
            border: 1px solid var(--accent);
            transition: transform 0.2s, opacity 0.2s;
        }

        .btn:hover {
            transform: translateY(-3px);
        }

        .btn-primary {
            background: var(--accent);
            color: #ffffff;
        }

        .btn-secondary {
            color: var(--text);
            background: var(--surface);
        }

        /* COMMON SECTIONS */
        section {
            padding: 75px 0;
        }

        .section-heading {
            margin-bottom: 35px;
        }

        .section-heading .small-title {
            color: var(--accent);
            text-transform: uppercase;
            font-size: 12px;
            font-weight: 800;
            letter-spacing: 2px;
        }

        .section-heading h2 {
            font-size: clamp(28px, 4vw, 42px);
            margin-top: 8px;
        }

        .section-heading p {
            color: var(--muted);
            margin-top: 10px;
        }

        /* ABOUT */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 25px;
        }

        .card {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 28px;
            box-shadow: var(--shadow);
        }

        .card h3 {
            margin-bottom: 12px;
        }

        .card p {
            color: var(--muted);
        }

        .education-card {
            border-left: 4px solid var(--accent);
        }

        /* SKILLS */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 16px;
        }

        .skill {
            background: var(--surface);
            border: 1px solid var(--border);
            padding: 23px 12px;
            border-radius: 12px;
            text-align: center;
            font-weight: 700;
            transition: transform 0.2s, border-color 0.2s;
        }

        .skill:hover {
            transform: translateY(-5px);
            border-color: var(--accent);
        }

        .skill span {
            display: block;
            font-size: 28px;
            margin-bottom: 8px;
        }

        /* PROJECTS */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }

        .project-card {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 14px;
            padding: 25px;
            box-shadow: var(--shadow);
            display: flex;
            flex-direction: column;
            align-items: flex-start;
        }

        .project-number {
            color: var(--accent);
            font-weight: 800;
            font-size: 14px;
            margin-bottom: 18px;
        }

        .project-card h3 {
            margin-bottom: 12px;
        }

        .project-card p {
            color: var(--muted);
            font-size: 14px;
            margin-bottom: 20px;
            flex-grow: 1;
        }

        .project-link {
            color: var(--accent);
            font-size: 14px;
            font-weight: 800;
        }

        /* EDUCATION */
        .education-list {
            display: grid;
            gap: 16px;
        }

        .education-item {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 12px;
            padding: 22px;
        }

        .education-item h3 {
            margin-bottom: 5px;
        }

        .education-item p {
            color: var(--muted);
        }

        /* CONTACT */
        .contact-card {
            background: var(--surface);
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 35px;
            box-shadow: var(--shadow);
        }

        .contact-list {
            display: grid;
            gap: 18px;
            margin-top: 25px;
        }

        .contact-item {
            overflow-wrap: anywhere;
        }

        .contact-item strong {
            display: block;
            margin-bottom: 3px;
        }

        .contact-item a,
        .contact-item span {
            color: var(--muted);
        }

        .contact-item a:hover {
            color: var(--accent);
        }

        /* FOOTER */
        footer {
            padding: 25px 0;
            text-align: center;
            border-top: 1px solid var(--border);
            color: var(--muted);
            font-size: 13px;
        }

        /* MOBILE RESPONSIVENESS */
        @media (max-width: 850px) {
            nav {
                padding: 14px 0;
                align-items: flex-start;
                flex-direction: column;
            }

            .nav-right {
                width: 100%;
                justify-content: space-between;
                gap: 10px;
                flex-wrap: wrap;
            }

            .nav-links {
                flex-wrap: wrap;
                gap: 12px;
            }

            .projects-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .skills-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 560px) {
            .hero {
                min-height: auto;
                padding: 65px 0;
            }

            h1 {
                letter-spacing: -1px;
            }

            .hero p {
                font-size: 15px;
            }

            section {
                padding: 55px 0;
            }

            .about-grid,
            .projects-grid {
                grid-template-columns: 1fr;
            }

            .nav-right {
                align-items: flex-start;
            }

            .nav-links {
                max-width: 270px;
            }

            .theme-toggle {
                font-size: 12px;
                padding: 9px 10px;
            }

            .contact-card {
                padding: 23px;
            }
        }
    </style>
</head>

<body>
    <!-- NAVIGATION -->
    <header>
        <nav class="container">
            <a href="#home" class="logo">Santhosh<span>.</span></a>

            <div class="nav-right">
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#education">Education</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>

                <button
                    id="themeToggle"
                    class="theme-toggle"
                    type="button"
                    aria-label="Switch to dark theme"
                    aria-pressed="false">
                    🌙 Dark Mode
                </button>
            </div>
        </nav>
    </header>

    <main>
        <!-- HOME -->
        <section class="hero container" id="home">
            <div class="hero-content">
                <span class="eyebrow">WELCOME TO MY PORTFOLIO</span>

                <h1>
                    Hi, I'm <span>Santhosh Kumar.</span>
                </h1>

                <p>
                    I am a BCA student interested in web development,
                    programming, and building useful digital projects.
                    I enjoy learning new technologies and improving my skills.
                </p>

                <div class="buttons">
                    <a href="#projects" class="btn btn-primary">
                        View My Projects
                    </a>

                    <a href="#contact" class="btn btn-secondary">
                        Contact Me
                    </a>
                </div>
            </div>
        </section>

        <!-- ABOUT -->
        <section id="about">
            <div class="container">
                <div class="section-heading">
                    <span class="small-title">ABOUT ME</span>
                    <h2>Get to Know Me</h2>
                    <p>A little information about me and my interests.</p>
                </div>

                <div class="about-grid">
                    <div class="card">
                        <h3>Who I Am</h3>
                        <p>
                            My name is Santhosh Kumar. I am a Bachelor of
                            Computer Applications (BCA) student who is
                            interested in technology, coding, and web design.
                            My goal is to develop my technical knowledge
                            by working on practical projects.
                        </p>
                    </div>

                    <div class="card education-card">
                        <h3>My Goal</h3>
                        <p>
                            I want to improve my programming skills, create
                            responsive websites, learn modern development
                            tools, and build projects that solve real problems.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- SKILLS -->
        <section id="skills">
            <div class="container">
                <div class="section-heading">
                    <span class="small-title">MY SKILLS</span>
                    <h2>Technologies I Learn</h2>
                    <p>Technical skills I am developing.</p>
                </div>

                <div class="skills-grid">
                    <div class="skill">
                        <span>🌐</span>
                        HTML
                    </div>

                    <div class="skill">
                        <span>🎨</span>
                        CSS
                    </div>

                    <div class="skill">
                        <span>⚡</span>
                        JavaScript
                    </div>

                    <div class="skill">
                        <span>🐍</span>
                        Python
                    </div>

                    <div class="skill">
                        <span>🗄️</span>
                        SQL
                    </div>

                    <div class="skill">
                        <span>⚙️</span>
                        Node.js
                    </div>

                    <div class="skill">
                        <span>🔧</span>
                        Git
                    </div>

                    <div class="skill">
                        <span>💻</span>
                        Responsive Design
                    </div>
                </div>
            </div>
        </section>

        <!-- PROJECTS -->
        <section id="projects">
            <div class="container">
                <div class="section-heading">
                    <span class="small-title">MY WORK</span>
                    <h2>Featured Projects</h2>
                    <p>Some projects you can showcase in your portfolio.</p>
                </div>

                <div class="projects-grid">
                    <article class="project-card">
                        <span class="project-number">PROJECT 01</span>
                        <h3>Personal Portfolio</h3>
                        <p>
                            A responsive personal website built using
                            HTML, CSS, and JavaScript to showcase my
                            profile, skills, and projects.
                        </p>
                        <a class="project-link" href="#home">
                            Explore Portfolio →
                        </a>
                    </article>

                    <article class="project-card">
                        <span class="project-number">PROJECT 02</span>
                        <h3>Task Manager API</h3>
                        <p>
                            A task management project that demonstrates
                            how to create, view, and manage tasks through
                            REST API endpoints.
                        </p>
                        <a class="project-link"
                           href="https://github.com/santhu2413"
                           target="_blank"
                           rel="noopener noreferrer">
                            View GitHub →
                        </a>
                    </article>

                    <article class="project-card">
                        <span class="project-number">PROJECT 03</span>
                        <h3>Online Store API</h3>
                        <p>
                            A sample online store project for managing
                            products with create, read, update, and
                            delete operations.
                        </p>
                        <a class="project-link"
                           href="https://github.com/santhu2413"
                           target="_blank"
                           rel="noopener noreferrer">
                            View GitHub →
                        </a>
                    </article>
                </div>
            </div>
        </section>

        <!-- EDUCATION -->
        <section id="education">
            <div class="container">
                <div class="section-heading">
                    <span class="small-title">EDUCATION</span>
                    <h2>My Learning Journey</h2>
                </div>

                <div class="education-list">
                    <div class="education-item">
                        <h3>Bachelor of Computer Applications (BCA)</h3>
                        <p>SVR First Grade College</p>
                        <p>Bangalore University</p>
                        <p>Currently pursuing</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- CONTACT -->
        <section id="contact">
            <div class="container">
                <div class="section-heading">
                    <span class="small-title">GET IN TOUCH</span>
                    <h2>Contact Me</h2>
                    <p>Feel free to contact me for projects and opportunities.</p>
                </div>

                <div class="contact-card">
                    <h3>Let's Connect!</h3>

                    <div class="contact-list">
                        <div class="contact-item">
                            <strong>📧 Email</strong>
                            <a href="mailto:lakshmanalakshmana394@gmail.com">
                                lakshmanalakshmana394@gmail.com
                            </a>
                        </div>

                        <div class="contact-item">
                            <strong>📱 Phone</strong>
                            <a href="tel:7338011946">
                                7338011946
                            </a>
                        </div>

                        <div class="contact-item">
                            <strong>💻 GitHub</strong>
                            <a href="https://github.com/santhu2413"
                               target="_blank"
                               rel="noopener noreferrer">
                                github.com/santhu2413
                            </a>
                        </div>
                    </div>

                    <div class="buttons" style="margin-top: 28px;">
                        <a class="btn btn-primary"
                           href="mailto:lakshmanalakshmana394@gmail.com">
                            Send Me an Email
                        </a>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- FOOTER -->
    <footer>
        <div class="container">
            <p>
                © <span id="year"></span> Santhosh Kumar.
                Built with HTML, CSS and JavaScript.
            </p>
        </div>
    </footer>

    <script>
        // DARK AND LIGHT THEME
        const themeToggle = document.getElementById("themeToggle");

        // Load the saved theme
        let savedTheme = "light";

        try {
            savedTheme = localStorage.getItem("portfolioTheme") || "light";
        } catch (error) {
            // The website still works if storage is unavailable.
        }

        if (savedTheme === "dark") {
            document.body.classList.add("dark-theme");
        }

        // Update button text and accessibility information
        function updateThemeButton() {
            const isDark = document.body.classList.contains("dark-theme");

            themeToggle.textContent = isDark
                ? "☀️ Light Mode"
                : "🌙 Dark Mode";

            themeToggle.setAttribute(
                "aria-label",
                isDark ? "Switch to light theme" : "Switch to dark theme"
            );

            themeToggle.setAttribute("aria-pressed", String(isDark));
        }

        // Switch themes when clicked
        themeToggle.addEventListener("click", function () {
            document.body.classList.toggle("dark-theme");

            const isDark = document.body.classList.contains("dark-theme");

            try {
                localStorage.setItem(
                    "portfolioTheme",
                    isDark ? "dark" : "light"
                );
            } catch (error) {
                // Theme switching still works for the current page.
            }

            updateThemeButton();
        });

        // Set the initial theme button
        updateThemeButton();

        // Automatically update the footer year
        document.getElementById("year").textContent =
            new Date().getFullYear();
    </script>
</body>
</html>
