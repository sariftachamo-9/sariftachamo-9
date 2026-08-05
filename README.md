<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Sarif Tachamo · Cybersecurity Profile</title>
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
    <style>
        /* ── reset & base ── */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0b0e14;
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
            display: flex;
            justify-content: center;
            padding: 2rem 1rem;
            color: #e4e9f0;
        }

        .profile-card {
            max-width: 1100px;
            width: 100%;
            background: rgba(14, 19, 28, 0.75);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-radius: 2.5rem;
            padding: 2.5rem 2rem;
            border: 1px solid rgba(0, 255, 200, 0.12);
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.8), inset 0 1px 0 rgba(0, 255, 200, 0.06);
            transition: all 0.2s ease;
        }

        /* ── scrollbar ── */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #0f141c;
        }
        ::-webkit-scrollbar-thumb {
            background: #00d4b0;
            border-radius: 12px;
        }

        /* ── glassmorphism helpers ── */
        .glass-badge {
            display: inline-flex;
            align-items: center;
            gap: 0.4rem;
            background: rgba(0, 255, 200, 0.06);
            backdrop-filter: blur(4px);
            -webkit-backdrop-filter: blur(4px);
            border: 1px solid rgba(0, 255, 200, 0.10);
            border-radius: 40px;
            padding: 0.35rem 1rem;
            font-size: 0.85rem;
            font-weight: 500;
            color: #c8d6e5;
            transition: 0.2s;
            text-decoration: none;
        }
        .glass-badge:hover {
            background: rgba(0, 255, 200, 0.12);
            border-color: rgba(0, 255, 200, 0.30);
            transform: translateY(-2px);
            color: #fff;
        }
        .glass-badge i {
            font-size: 1rem;
            color: #00d4b0;
        }

        .glass-stats {
            background: rgba(0, 255, 200, 0.04);
            backdrop-filter: blur(6px);
            -webkit-backdrop-filter: blur(6px);
            border: 1px solid rgba(0, 255, 200, 0.08);
            border-radius: 1.5rem;
            padding: 1.25rem 1.5rem;
            transition: 0.25s ease;
        }
        .glass-stats:hover {
            border-color: rgba(0, 255, 200, 0.20);
            background: rgba(0, 255, 200, 0.07);
        }

        /* ── header ── */
        .header-wrap {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 1.5rem 2rem;
            margin-bottom: 2.5rem;
        }

        .avatar-gif {
            flex-shrink: 0;
            width: 110px;
            height: 110px;
            border-radius: 50%;
            border: 2px solid rgba(0, 255, 200, 0.30);
            box-shadow: 0 0 30px rgba(0, 255, 200, 0.08);
            overflow: hidden;
            background: #0f141c;
        }
        .avatar-gif img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .header-titles h1 {
            font-size: 2.2rem;
            font-weight: 700;
            background: linear-gradient(135deg, #e4e9f0 0%, #00d4b0 80%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -0.5px;
            line-height: 1.2;
        }
        .header-titles .sub {
            font-size: 1rem;
            color: #8b9bb5;
            margin-top: 0.2rem;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 0.4rem 1rem;
        }
        .header-titles .sub .flag {
            font-size: 1.3rem;
            line-height: 1;
        }
        .header-titles .sub .tag {
            background: rgba(0, 255, 200, 0.08);
            border-radius: 30px;
            padding: 0.1rem 0.9rem;
            font-size: 0.75rem;
            font-weight: 600;
            letter-spacing: 0.3px;
            color: #00d4b0;
            border: 1px solid rgba(0, 255, 200, 0.12);
            text-transform: uppercase;
        }

        .social-row {
            display: flex;
            flex-wrap: wrap;
            gap: 0.6rem 1.2rem;
            margin-top: 0.6rem;
        }
        .social-row a {
            color: #9aabc4;
            font-size: 1.1rem;
            transition: 0.2s;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 0.3rem;
        }
        .social-row a:hover {
            color: #00d4b0;
            transform: translateY(-2px);
        }

        /* ── section titles ── */
        .section-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin: 2rem 0 1rem 0;
            display: flex;
            align-items: center;
            gap: 0.6rem;
            color: #dce3ed;
            letter-spacing: -0.2px;
        }
        .section-title i {
            color: #00d4b0;
            font-size: 1.3rem;
        }
        .section-title .line {
            flex: 1;
            height: 1px;
            background: linear-gradient(90deg, rgba(0, 255, 200, 0.20), transparent);
        }

        /* ── tech grid ── */
        .tech-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 0.6rem 0.8rem;
            margin: 0.5rem 0 0.2rem;
        }
        .tech-grid .badge {
            display: inline-flex;
            align-items: center;
            gap: 0.4rem;
            background: rgba(255, 255, 255, 0.04);
            backdrop-filter: blur(4px);
            -webkit-backdrop-filter: blur(4px);
            border: 1px solid rgba(255, 255, 255, 0.06);
            border-radius: 30px;
            padding: 0.25rem 1rem 0.25rem 0.9rem;
            font-size: 0.78rem;
            font-weight: 500;
            color: #c4d0e0;
            transition: 0.2s;
        }
        .tech-grid .badge i {
            font-size: 0.9rem;
            color: #00d4b0;
        }
        .tech-grid .badge:hover {
            background: rgba(0, 255, 200, 0.06);
            border-color: rgba(0, 255, 200, 0.15);
            transform: translateY(-2px);
        }
        .tech-grid .badge .dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            display: inline-block;
            margin-right: 2px;
        }

        /* ── stats row ── */
        .stats-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
            margin: 1rem 0;
        }
        .stats-row .glass-stats {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 1rem 0.8rem;
        }
        .stats-row .glass-stats .num {
            font-size: 1.9rem;
            font-weight: 700;
            color: #00d4b0;
            letter-spacing: -0.5px;
        }
        .stats-row .glass-stats .label {
            font-size: 0.8rem;
            color: #8b9bb5;
            margin-top: 0.1rem;
        }
        .stats-row .glass-stats i {
            font-size: 1.4rem;
            color: #00d4b0;
            margin-bottom: 0.2rem;
            opacity: 0.7;
        }

        /* ── image cards (stats, lang, streak) ── */
        .img-card {
            background: rgba(0, 0, 0, 0.30);
            border-radius: 1.2rem;
            border: 1px solid rgba(0, 255, 200, 0.07);
            overflow: hidden;
            transition: 0.25s ease;
            width: 100%;
        }
        .img-card:hover {
            border-color: rgba(0, 255, 200, 0.15);
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.4);
        }
        .img-card img {
            display: block;
            width: 100%;
            height: auto;
            background: #0b0e14;
        }

        .two-col {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.2rem;
            margin: 1rem 0;
        }

        .full-width {
            margin: 1rem 0;
        }

        /* ── snake ── */
        .snake-wrap {
            border-radius: 1.2rem;
            overflow: hidden;
            background: #0b0e14;
            border: 1px solid rgba(0, 255, 200, 0.06);
            margin: 1rem 0;
        }
        .snake-wrap img {
            display: block;
            width: 100%;
            height: auto;
        }

        /* ── projects ── */
        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
            margin: 0.8rem 0 0.2rem;
        }
        .project-card {
            background: rgba(0, 255, 200, 0.03);
            backdrop-filter: blur(4px);
            -webkit-backdrop-filter: blur(4px);
            border: 1px solid rgba(0, 255, 200, 0.06);
            border-radius: 1.2rem;
            padding: 1.2rem 1.2rem 1rem;
            transition: 0.25s ease;
            text-decoration: none;
            color: #c8d6e5;
            display: flex;
            flex-direction: column;
        }
        .project-card:hover {
            border-color: rgba(0, 255, 200, 0.20);
            background: rgba(0, 255, 200, 0.06);
            transform: translateY(-4px);
            color: #fff;
        }
        .project-card .p-title {
            font-weight: 600;
            font-size: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        .project-card .p-title i {
            color: #00d4b0;
            font-size: 0.9rem;
        }
        .project-card .p-desc {
            font-size: 0.82rem;
            color: #8b9bb5;
            margin-top: 0.3rem;
            line-height: 1.4;
        }
        .project-card .p-tags {
            margin-top: 0.5rem;
            display: flex;
            flex-wrap: wrap;
            gap: 0.3rem;
        }
        .project-card .p-tags span {
            font-size: 0.6rem;
            background: rgba(0, 255, 200, 0.08);
            padding: 0.1rem 0.6rem;
            border-radius: 20px;
            border: 1px solid rgba(0, 255, 200, 0.06);
            color: #8b9bb5;
        }

        /* ── footer / donor ── */
        .donor-row {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 0.8rem 1.5rem;
            margin-top: 1.8rem;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(0, 255, 200, 0.06);
        }
        .donor-row a {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.3rem 1.2rem;
            border-radius: 40px;
            font-weight: 500;
            font-size: 0.9rem;
            text-decoration: none;
            transition: 0.2s;
            border: 1px solid rgba(0, 255, 200, 0.08);
            background: rgba(0, 255, 200, 0.04);
            color: #c8d6e5;
        }
        .donor-row a:hover {
            background: rgba(0, 255, 200, 0.10);
            border-color: rgba(0, 255, 200, 0.20);
            transform: translateY(-2px);
            color: #fff;
        }
        .donor-row a i {
            color: #00d4b0;
        }

        .visitor-badge {
            margin-left: auto;
            font-size: 0.8rem;
            color: #5f738f;
            display: flex;
            align-items: center;
            gap: 0.4rem;
        }
        .visitor-badge i {
            color: #00d4b0;
        }

        /* ── quote ── */
        .quote-box {
            margin: 1.8rem 0 0.5rem;
            padding: 1rem 1.5rem;
            border-radius: 1.5rem;
            background: rgba(0, 255, 200, 0.03);
            border: 1px solid rgba(0, 255, 200, 0.06);
            text-align: center;
            font-style: italic;
            color: #8b9bb5;
            font-size: 0.95rem;
        }
        .quote-box i {
            color: #00d4b0;
            margin: 0 0.3rem;
        }

        /* ── responsive ── */
        @media (max-width: 720px) {
            .profile-card {
                padding: 1.5rem 1rem;
            }
            .header-wrap {
                flex-direction: column;
                align-items: flex-start;
            }
            .avatar-gif {
                width: 80px;
                height: 80px;
            }
            .header-titles h1 {
                font-size: 1.6rem;
            }
            .stats-row {
                grid-template-columns: 1fr 1fr;
                gap: 0.6rem;
            }
            .two-col {
                grid-template-columns: 1fr;
                gap: 0.8rem;
            }
            .project-grid {
                grid-template-columns: 1fr;
            }
            .social-row {
                gap: 0.4rem 0.8rem;
            }
            .donor-row {
                flex-direction: column;
                align-items: stretch;
            }
            .visitor-badge {
                margin-left: 0;
                justify-content: center;
            }
        }

        @media (max-width: 480px) {
            .stats-row {
                grid-template-columns: 1fr 1fr;
                gap: 0.4rem;
            }
            .stats-row .glass-stats .num {
                font-size: 1.4rem;
            }
            .tech-grid .badge {
                font-size: 0.7rem;
                padding: 0.15rem 0.7rem 0.15rem 0.6rem;
            }
        }
    </style>
</head>
<body>

    <div class="profile-card">

        <!-- ═══ HEADER ═══ -->
        <div class="header-wrap">
            <div class="avatar-gif">
                <img src="https://media.giphy.com/media/ZVik7pBtu9dNS/giphy.gif" alt="hacker animation" />
            </div>
            <div class="header-titles">
                <h1>Sarif Tachamo</h1>
                <div class="sub">
                    <span class="flag">🇳🇵</span>
                    <span>Computer Engineering Student</span>
                    <span class="tag">Cybersecurity</span>
                    <span class="tag">AI/ML</span>
                </div>
                <div class="social-row">
                    <a href="https://discord.com/invite/55e4VebV" target="_blank">
                        <i class="fab fa-discord"></i> Discord
                    </a>
                    <a href="https://www.linkedin.com/in/sarif-tachamo-cybersec/" target="_blank">
                        <i class="fab fa-linkedin-in"></i> LinkedIn
                    </a>
                    <a href="mailto:sariftachamo.job@gmail.com" target="_blank">
                        <i class="fas fa-envelope"></i> Email
                    </a>
                </div>
            </div>
        </div>

        <!-- ═══ ABOUT ═══ -->
        <div class="section-title">
            <i class="fas fa-user-astronaut"></i> About Me
            <span class="line"></span>
        </div>
        <p style="color:#b8c7dd; line-height:1.7; font-size:0.98rem;">
            Hi 👋! I'm <strong style="color:#00d4b0;">Sarif Tachamo</strong> — a
            <strong>Computer Engineering Student</strong> from Nepal 🇳🇵 with a deep
            passion for <strong>Cybersecurity</strong> and <strong>AI/ML</strong>.
            I love breaking down complex systems, hunting vulnerabilities, and
            building intelligent solutions. Currently exploring the intersection of
            offensive security and machine learning.
        </p>

        <!-- ═══ TECH STACK ═══ -->
        <div class="section-title">
            <i class="fas fa-code"></i> Tech Stack
            <span class="line"></span>
        </div>
        <div class="tech-grid">
            <span class="badge"><i class="fab fa-html5"></i> HTML5</span>
            <span class="badge"><i class="fab fa-css3-alt"></i> CSS3</span>
            <span class="badge"><i class="fab fa-js"></i> JavaScript</span>
            <span class="badge"><i class="fab fa-php"></i> PHP</span>
            <span class="badge"><i class="fab fa-python"></i> Python</span>
            <span class="badge"><i class="fab fa-ts"></i> TypeScript</span>
            <span class="badge"><i class="fas fa-c"></i> C</span>
            <span class="badge"><i class="fas fa-c"></i> C++</span>
            <span class="badge"><i class="fas fa-terminal"></i> Bash</span>
            <span class="badge"><i class="fas fa-database"></i> MySQL</span>
            <span class="badge"><i class="fas fa-leaf"></i> MongoDB</span>
            <span class="badge"><i class="fas fa-fire"></i> Firebase</span>
            <span class="badge"><i class="fab fa-node-js"></i> Express.js</span>
            <span class="badge"><i class="fas fa-flask"></i> Flask</span>
            <span class="badge"><i class="fas fa-cube"></i> Bootstrap</span>
            <span class="badge"><i class="fas fa-robot"></i> Pandas</span>
            <span class="badge"><i class="fas fa-brain"></i> Keras</span>
            <span class="badge"><i class="fas fa-chart-line"></i> SciPy</span>
            <span class="badge"><i class="fas fa-cloud"></i> Cloudflare</span>
            <span class="badge"><i class="fas fa-database"></i> Supabase</span>
            <span class="badge"><i class="fas fa-paint-brush"></i> Canva</span>
        </div>

        <!-- ═══ STATS ROW ═══ -->
        <div class="section-title" style="margin-top:2.2rem;">
            <i class="fas fa-chart-simple"></i> GitHub Stats
            <span class="line"></span>
        </div>
        <div class="stats-row">
            <div class="glass-stats">
                <i class="fas fa-star"></i>
                <div class="num">42</div>
                <div class="label">Total Stars</div>
            </div>
            <div class="glass-stats">
                <i class="fas fa-code-commit"></i>
                <div class="num">128</div>
                <div class="label">Total Commits</div>
            </div>
            <div class="glass-stats">
                <i class="fas fa-fire"></i>
                <div class="num">87</div>
                <div class="label">Contributions</div>
            </div>
            <div class="glass-stats">
                <i class="fas fa-users"></i>
                <div class="num">17</div>
                <div class="label">Followers</div>
            </div>
            <div class="glass-stats" style="grid-column: span 2;">
                <i class="fas fa-trophy"></i>
                <div class="num">#1,234</div>
                <div class="label">Global Ranking</div>
            </div>
        </div>

        <!-- ═══ STATS IMAGES (2‑col) ═══ -->
        <div class="two-col">
            <div class="img-card">
                <img src="https://github-readme-stats.shion.dev/api?username=sariftachamo-9&theme=dark&hide_border=false&include_all_commits=false&count_private=true"
                alt="GitHub Stats" />
            </div>
            <div class="img-card">
                <img src="https://github-readme-stats.shion.dev/api/top-langs/?username=sariftachamo-9&theme=dark&hide_border=false&include_all_commits=false&count_private=true&layout=compact"
                alt="Top Languages" />
            </div>
        </div>

        <!-- ═══ STREAK (UPDATED: hides longest streak) ═══ -->
        <div class="img-card full-width">
            <img src="https://streak-stats.demolab.com/?user=sariftachamo-9&theme=dark&hide_border=false&hide_longest_streak=true"
            alt="GitHub Streak" />
        </div>

        <!-- ═══ ACTIVITY GRAPH ═══ -->
        <div class="section-title">
            <i class="fas fa-wave-square"></i> Contribution Graph
            <span class="line"></span>
        </div>
        <div class="img-card full-width">
            <img src="https://github-readme-activity-graph.vercel.app/graph?username=sariftachamo-9&theme=react-dark&hide_border=true&area=true&bg_color=0b0e14&color=00d4b0&line=00d4b0&point=00ffc8"
            alt="Activity Graph" />
        </div>

        <!-- ═══ SNAKE ═══ -->
        <div class="section-title">
            <i class="fas fa-snake"></i> Snake eating my contributions
            <span class="line"></span>
        </div>
        <div class="snake-wrap">
            <img src="https://raw.githubusercontent.com/sariftachamo-9/sariftachamo-9/output/snake.svg"
            alt="Snake animation" />
        </div>

        <!-- ═══ FEATURED PROJECTS ═══ -->
        <div class="section-title">
            <i class="fas fa-rocket"></i> Featured Projects
            <span class="line"></span>
        </div>
        <div class="project-grid">
            <a href="#" class="project-card">
                <div class="p-title"><i class="fas fa-shield-halved"></i> VulnScanner</div>
                <div class="p-desc">Automated vulnerability scanner for web apps using Python &amp; OWASP top 10.</div>
                <div class="p-tags"><span>Python</span><span>Security</span></div>
            </a>
            <a href="#" class="project-card">
                <div class="p-title"><i class="fas fa-brain"></i> PhishDetect</div>
                <div class="p-desc">ML-based phishing URL detector with 94% accuracy using TensorFlow.</div>
                <div class="p-tags"><span>TensorFlow</span><span>NLP</span></div>
            </a>
            <a href="#" class="project-card">
                <div class="p-title"><i class="fas fa-terminal"></i> CipherX</div>
                <div class="p-desc">Cross‑platform encryption tool with AES‑256 and CLI interface.</div>
                <div class="p-tags"><span>C++</span><span>Crypto</span></div>
            </a>
            <a href="#" class="project-card">
                <div class="p-title"><i class="fas fa-robot"></i> ThreatIntel</div>
                <div class="p-desc">Real‑time threat intelligence feed aggregator with alerting system.</div>
                <div class="p-tags"><span>Flask</span><span>APIs</span></div>
            </a>
        </div>

        <!-- ═══ QUOTE ═══ -->
        <div class="quote-box">
            <i class="fas fa-quote-left"></i>
            In the world of bits, the only constant is the battle between
            those who build and those who break.
            <i class="fas fa-quote-right"></i>
        </div>

        <!-- ═══ FOOTER / DONOR ═══ -->
        <div class="donor-row">
            <span style="color:#8b9bb5; font-size:0.9rem;">
                <i class="fas fa-heart" style="color:#00d4b0;"></i> Support my work
            </span>
            <a href="https://buymeacoffee.com/Thanks%20for%20you%20coffee" target="_blank">
                <i class="fas fa-mug-hot"></i> Buy Me a Coffee
            </a>
            <a href="https://www.paypal.com/ncp/payment/89GP4598VD79W" target="_blank">
                <i class="fab fa-paypal"></i> PayPal
            </a>
            <div class="visitor-badge">
                <i class="fas fa-eye"></i>
                <img src="https://komarev.com/ghpvc/?username=sariftachamo-9&icon=0&color=0"
                alt="visitor counter" style="height:20px; border-radius:4px;" />
            </div>
        </div>

        <!-- tiny footer note -->
        <div style="margin-top:1.2rem; text-align:center; font-size:0.7rem; color:#33445a; letter-spacing:0.3px; border-top:1px solid rgba(0,255,200,0.04); padding-top:0.8rem;">
            ⚡ built with <span style="color:#00d4b0;">&lt;/&gt;</span> — sariftachamo-9 · cybersecurity theme
        </div>

    </div>

</body>
</html>
