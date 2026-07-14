<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>Sarif Tachamo · Cyber Portfolio</title>
    <!-- Font Awesome for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css"/>
    <style>
        /* ── Reset & Base ── */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: #0b0e14;
            font-family: 'Inter', 'Segoe UI', system-ui, -apple-system, sans-serif;
            color: #d0d7e6;
            line-height: 1.6;
            padding: 2rem 1rem;
        }
        .container {
            max-width: 1100px;
            margin: 0 auto;
            background: #11161f;
            border-radius: 2.5rem;
            padding: 2.5rem 2rem;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.8);
            border: 1px solid rgba(0, 255, 65, 0.08);
        }

        /* ── Scrollbar ── */
        ::-webkit-scrollbar {
            width: 8px;
            background: #0b0e14;
        }
        ::-webkit-scrollbar-thumb {
            background: #00ff41;
            border-radius: 10px;
        }

        /* ── Typography ── */
        h1,
        h2,
        h3 {
            font-weight: 600;
            letter-spacing: -0.02em;
        }
        h1 {
            font-size: 2.6rem;
        }
        h2 {
            font-size: 1.9rem;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.6rem;
        }
        h2 i {
            color: #00ff41;
            font-size: 1.6rem;
        }
        a {
            color: #7ee8b0;
            text-decoration: none;
            transition: color 0.2s;
        }
        a:hover {
            color: #00ff41;
        }
        .highlight {
            color: #00ff41;
        }
        .muted {
            color: #8892a8;
        }

        /* ── Matrix Banner ── */
        .matrix-banner {
            background: #06080c;
            border-radius: 1.8rem;
            padding: 1.8rem 1.2rem;
            margin-bottom: 2.5rem;
            border: 1px solid rgba(0, 255, 65, 0.15);
            box-shadow: 0 0 40px rgba(0, 255, 65, 0.04);
            overflow: hidden;
            position: relative;
        }
        .matrix-banner pre {
            font-family: 'Fira Code', 'Courier New', monospace;
            font-size: 0.85rem;
            line-height: 1.5;
            color: #00ff41;
            text-shadow: 0 0 6px rgba(0, 255, 65, 0.3);
            white-space: pre-wrap;
            word-break: break-word;
            margin: 0;
            background: transparent;
            border: none;
            padding: 0;
        }
        .matrix-banner .glow {
            color: #33ff77;
            text-shadow: 0 0 12px #00ff41, 0 0 30px rgba(0, 255, 65, 0.15);
        }
        .matrix-banner .dim {
            color: #1a5a2a;
        }

        /* ── Hero / Typing ── */
        .hero {
            background: linear-gradient(145deg, #0e131e, #080b12);
            border-radius: 2rem;
            padding: 2.5rem 2rem;
            margin-bottom: 2.5rem;
            border: 1px solid rgba(0, 255, 65, 0.07);
            text-align: center;
        }
        .hero .typing-svg {
            max-width: 100%;
            height: auto;
            margin-bottom: 0.5rem;
        }
        .hero .tagline {
            font-size: 1.1rem;
            color: #8892a8;
            margin-top: 0.2rem;
        }
        .hero .badge-row {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 0.8rem;
            margin-top: 1.2rem;
        }
        .hero .badge-row a {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: rgba(0, 255, 65, 0.06);
            padding: 0.4rem 1.2rem;
            border-radius: 40px;
            border: 1px solid rgba(0, 255, 65, 0.12);
            font-size: 0.85rem;
            color: #b0c7d9;
            transition: 0.2s;
        }
        .hero .badge-row a:hover {
            background: rgba(0, 255, 65, 0.12);
            border-color: #00ff41;
            color: #fff;
        }
        .hero .badge-row a i {
            color: #00ff41;
        }

        /* ── Cards (About, Focus, Achievements, etc.) ── */
        .card-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
            margin: 1.8rem 0 2.5rem;
        }
        .card {
            background: #0e131e;
            border-radius: 1.6rem;
            padding: 1.8rem 1.6rem;
            border: 1px solid rgba(255, 255, 255, 0.04);
            transition: 0.25s ease;
            box-shadow: 0 8px 24px rgba(0, 0, 0, 0.3);
        }
        .card:hover {
            border-color: rgba(0, 255, 65, 0.20);
            transform: translateY(-3px);
            box-shadow: 0 12px 36px rgba(0, 0, 0, 0.5);
        }
        .card h3 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            display: flex;
            align-items: center;
            gap: 0.6rem;
        }
        .card h3 i {
            color: #00ff41;
            font-size: 1.3rem;
        }
        .card p,
        .card li {
            color: #b0c7d9;
            font-size: 0.95rem;
        }
        .card ul {
            list-style: none;
            padding: 0;
            margin: 0.6rem 0 0;
        }
        .card ul li {
            padding: 0.25rem 0 0.25rem 1.5rem;
            position: relative;
        }
        .card ul li::before {
            content: "▹";
            position: absolute;
            left: 0;
            color: #00ff41;
        }
        .card .badge-list {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 0.6rem;
        }
        .card .badge-list span {
            background: rgba(0, 255, 65, 0.07);
            padding: 0.2rem 0.9rem;
            border-radius: 30px;
            font-size: 0.75rem;
            border: 1px solid rgba(0, 255, 65, 0.08);
            color: #b0c7d9;
        }

        /* ── Tech Stack (organised) ── */
        .tech-section {
            background: #0e131e;
            border-radius: 1.8rem;
            padding: 2rem 1.8rem;
            margin: 2rem 0;
            border: 1px solid rgba(255, 255, 255, 0.04);
        }
        .tech-section h2 {
            margin-bottom: 1.2rem;
        }
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
            gap: 0.8rem;
        }
        .tech-grid .tech-item {
            background: rgba(0, 255, 65, 0.04);
            padding: 0.45rem 0.9rem;
            border-radius: 40px;
            font-size: 0.8rem;
            border: 1px solid rgba(0, 255, 65, 0.06);
            color: #b0c7d9;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            transition: 0.2s;
        }
        .tech-grid .tech-item i {
            color: #00ff41;
            font-size: 0.9rem;
        }
        .tech-grid .tech-item:hover {
            border-color: #00ff41;
            background: rgba(0, 255, 65, 0.08);
        }

        /* ── Project Cards ── */
        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 1.5rem;
            margin: 1.5rem 0 2rem;
        }
        .project-card {
            background: #0e131e;
            border-radius: 1.6rem;
            padding: 1.6rem 1.4rem;
            border: 1px solid rgba(255, 255, 255, 0.04);
            transition: 0.25s;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.25);
        }
        .project-card:hover {
            border-color: rgba(0, 255, 65, 0.20);
            transform: translateY(-4px);
        }
        .project-card h4 {
            font-size: 1.1rem;
            margin-bottom: 0.3rem;
            color: #e6edf5;
        }
        .project-card p {
            font-size: 0.9rem;
            color: #8892a8;
            margin-bottom: 0.8rem;
        }
        .project-card .tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.4rem;
        }
        .project-card .tags span {
            background: rgba(0, 255, 65, 0.06);
            padding: 0.15rem 0.7rem;
            border-radius: 30px;
            font-size: 0.7rem;
            border: 1px solid rgba(0, 255, 65, 0.06);
            color: #8892a8;
        }

        /* ── GitHub Stats ── */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
            margin: 1.8rem 0;
        }
        .stats-grid img {
            width: 100%;
            border-radius: 1.2rem;
            border: 1px solid rgba(255, 255, 255, 0.04);
            background: #0e131e;
        }

        /* ── Trophies & Contributions ── */
        .trophy-wrap,
        .graph-wrap {
            background: #0e131e;
            border-radius: 1.8rem;
            padding: 1.8rem 1.2rem;
            margin: 1.8rem 0;
            border: 1px solid rgba(255, 255, 255, 0.04);
            text-align: center;
        }
        .trophy-wrap img,
        .graph-wrap img {
            max-width: 100%;
            border-radius: 1rem;
        }

        /* ── Snake Animation ── */
        .snake-wrap {
            background: #0e131e;
            border-radius: 1.8rem;
            padding: 1.2rem;
            margin: 1.8rem 0;
            border: 1px solid rgba(255, 255, 255, 0.04);
            text-align: center;
        }
        .snake-wrap img {
            max-width: 100%;
            border-radius: 1rem;
        }

        /* ── Goals & Research ── */
        .two-col {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.5rem;
            margin: 1.5rem 0;
        }
        @media (max-width: 700px) {
            .two-col {
                grid-template-columns: 1fr;
            }
        }

        /* ── Social / Contact ── */
        .social-row {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.2rem;
            margin: 1.8rem 0 1.2rem;
        }
        .social-row a {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: rgba(0, 255, 65, 0.05);
            padding: 0.5rem 1.5rem;
            border-radius: 50px;
            border: 1px solid rgba(0, 255, 65, 0.08);
            font-size: 0.95rem;
            color: #b0c7d9;
            transition: 0.2s;
        }
        .social-row a:hover {
            background: rgba(0, 255, 65, 0.10);
            border-color: #00ff41;
            color: #fff;
        }
        .social-row a i {
            color: #00ff41;
            font-size: 1.2rem;
        }

        /* ── Visitor Counter ── */
        .visitor-wrap {
            text-align: center;
            margin: 1.5rem 0 1rem;
            font-size: 0.9rem;
            color: #8892a8;
        }
        .visitor-wrap img {
            vertical-align: middle;
        }

        /* ── Support ── */
        .support-row {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.2rem;
            margin: 1.2rem 0 0;
        }
        .support-row a {
            display: inline-flex;
            align-items: center;
            gap: 0.6rem;
            padding: 0.5rem 1.8rem;
            border-radius: 50px;
            font-weight: 500;
            font-size: 0.95rem;
            transition: 0.2s;
            border: 1px solid rgba(255, 255, 255, 0.06);
        }
        .support-row a.bmc {
            background: #ffdd00;
            color: #000;
        }
        .support-row a.bmc:hover {
            background: #ffe44d;
            transform: scale(1.02);
        }
        .support-row a.paypal {
            background: #00457c;
            color: #fff;
        }
        .support-row a.paypal:hover {
            background: #005a9c;
            transform: scale(1.02);
        }

        /* ── Divider ── */
        .divider {
            border: none;
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(0, 255, 65, 0.15), transparent);
            margin: 2rem 0;
        }

        /* ── Responsive ── */
        @media (max-width: 600px) {
            .container {
                padding: 1.2rem 1rem;
            }
            h1 {
                font-size: 1.8rem;
            }
            h2 {
                font-size: 1.4rem;
            }
            .hero {
                padding: 1.8rem 1rem;
            }
            .matrix-banner pre {
                font-size: 0.6rem;
            }
            .card-grid {
                grid-template-columns: 1fr;
            }
            .project-grid {
                grid-template-columns: 1fr;
            }
            .tech-grid {
                grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            }
        }
    </style>
</head>
<body>

    <div class="container">

        <!-- ════════════════════════════════════════ -->
        <!-- 🟢 ANIMATED MATRIX RAIN BANNER          -->
        <!-- ════════════════════════════════════════ -->
        <div class="matrix-banner">
            <pre>
                <span class="dim">01001000 01100101 01101100 01101100 01101111 00100000 01010111 01101111 01110010 01101100 01100100</span>
                <span class="glow">   ███████╗ █████╗ ██████╗ ██╗███████╗    ████████╗ █████╗  ██████╗██╗  ██╗ █████╗ ███╗   ███╗ ██████╗ </span>
                <span class="glow">   ██╔════╝██╔══██╗██╔══██╗██║██╔════╝    ╚══██╔══╝██╔══██╗██╔════╝██║  ██║██╔══██╗████╗ ████║██╔═══██╗</span>
                <span class="glow">   ███████╗███████║██████╔╝██║█████╗         ██║   ███████║██║     ███████║███████║██╔████╔██║██║   ██║</span>
                <span class="glow">   ╚════██║██╔══██║██╔══██╗██║██╔══╝         ██║   ██╔══██║██║     ██╔══██║██╔══██║██║╚██╔╝██║██║   ██║</span>
                <span class="glow">   ███████║██║  ██║██║  ██║██║██║            ██║   ██║  ██║╚██████╗██║  ██║██║  ██║██║ ╚═╝ ██║╚██████╔╝</span>
                <span class="glow">   ╚══════╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝╚═╝            ╚═╝   ╚═╝  ╚═╝ ╚═════╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝     ╚═╝ ╚═════╝ </span>
                <span class="dim">01110011 01100001 01110010 01101001 01100110 00101110 01110100 01100001 01100011 01101000 01100001 01101101 01101111</span>
                <span style="color:#1a5a2a;">▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄</span>
                <span class="dim">  01010011 01000001 01010010 01001001 01000110 00100000 01010100 01000001 01000011 01001000 01000001 01001101 01001111</span>
            </pre>
        </div>

        <!-- ════════════════════════════════════════ -->
        <!-- ⌨️ TYPING SVG ANIMATION + HERO          -->
        <!-- ════════════════════════════════════════ -->
        <div class="hero">
            <img
            class="typing-svg"
            src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=28&duration=3000&pause=800&color=00FF41&center=true&vCenter=true&width=700&lines=Sarif+Tachamo;Cybersecurity+%26+AI%2FML+Researcher;Computer+Engineering+Student;Building+Secure+Intelligent+Systems"
            alt="Typing SVG Animation"
            />
            <p class="tagline">
                <i class="fas fa-shield-halved" style="color:#00ff41;"></i>
                Computer Engineering · Cybersecurity Enthusiast &amp; Researcher · AI/ML
            </p>
            <div class="badge-row">
                <a href="https://discord.gg/55e4VebV"><i class="fab fa-discord"></i> Discord</a>
                <a href="https://linkedin.com/in/sarif-tachamo-06b9b9248"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
                <a href="mailto:sariftachamo.job@gmail.com"><i class="fas fa-envelope"></i> Email</a>
                <a href="#"><i class="fas fa-user-astronaut"></i> Portfolio</a>
            </div>
        </div>

        <hr class="divider" />

        <!-- ════════════════════════════════════════ -->
        <!-- 👋 ABOUT ME                            -->
        <!-- ════════════════════════════════════════ -->
        <h2><i class="fas fa-user-ninja"></i> About Me</h2>
        <div class="card-grid">
            <div class="card">
                <h3><i class="fas fa-graduation-cap"></i> Who I Am</h3>
                <p>
                    I'm <strong class="highlight">Sarif Tachamo</strong>, a Computer Engineering student
                    with a deep passion for <strong>Cybersecurity</strong>, <strong>AI/ML</strong>,
                    and building resilient digital infrastructure. I bridge the gap between
                    offensive security research and intelligent automation.
                </p>
            </div>
            <div class="card">
                <h3><i class="fas fa-bolt"></i> Current Focus</h3>
                <ul>
                    <li>🔐 Advanced persistent threat (APT) simulation</li>
                    <li>🤖 ML-based intrusion detection systems</li>
                    <li>☁️ Cloud security &amp; DevOps hardening</li>
                    <li>📚 Research: adversarial AI &amp; federated learning</li>
                </ul>
            </div>
            <div class="card">
                <h3><i class="fas fa-trophy"></i> Achievements &amp; Certifications</h3>
                <ul>
                    <li>🏅 CEH (Certified Ethical Hacker) — <em>in progress</em></li>
                    <li>🏆 Top 5% TryHackMe · 2025</li>
                    <li>📜 Google Cybersecurity Certificate</li>
                    <li>⚡ AWS Cloud Practitioner (foundational)</li>
                </ul>
                <div class="badge-list">
                    <span>#CEH</span>
                    <span>#TryHackMe</span>
                    <span>#AWS</span>
                    <span>#GoogleCybersecurity</span>
                </div>
            </div>
        </div>

        <hr class="divider" />

        <!-- ════════════════════════════════════════ -->
        <!-- 📂 FEATURED PROJECTS                    -->
        <!-- ════════════════════════════════════════ -->
        <h2><i class="fas fa-code-branch"></i> Featured Projects</h2>
        <div class="project-grid">
            <div class="project-card">
                <h4>🛡️ ThreatHive</h4>
                <p>AI-driven threat intelligence feed with real-time IoC correlation and ML-based risk scoring.</p>
                <div class="tags"><span>Python</span><span>Flask</span><span>ML</span><span>Elastic</span></div>
            </div>
            <div class="project-card">
                <h4>⚡ NetGuardian</h4>
                <p>Network anomaly detection using unsupervised learning on pcap data. Visualised with Grafana.</p>
                <div class="tags"><span>Python</span><span>Scikit-learn</span><span>Wireshark</span><span>Grafana</span></div>
            </div>
            <div class="project-card">
                <h4>🔐 CipherForge</h4>
                <p>Cryptographic toolkit with custom AES-256 implementation, hash cracking utilities &amp; steganography.</p>
                <div class="tags"><span>Python</span><span>Crypto</span><span>Bash</span><span>OpenCV</span></div>
            </div>
            <div class="project-card">
                <h4>🤖 AutoSecOps</h4>
                <p>Automated security pipeline: SAST, DAST, dependency scanning &amp; container hardening for CI/CD.</p>
                <div class="tags"><span>Docker</span><span>GitHub Actions</span><span>Trivy</span><span>OWASP</span></div>
            </div>
        </div>

        <hr class="divider" />

        <!-- ════════════════════════════════════════ -->
        <!-- 💻 TECH STACK (organised)              -->
        <!-- ════════════════════════════════════════ -->
        <div class="tech-section">
            <h2><i class="fas fa-layer-group"></i> Tech Stack</h2>
            <div class="tech-grid">
                <span class="tech-item"><i class="fab fa-js-square"></i> JavaScript</span>
                <span class="tech-item"><i class="fab fa-python"></i> Python</span>
                <span class="tech-item"><i class="fas fa-terminal"></i> Bash</span>
                <span class="tech-item"><i class="fab fa-php"></i> PHP</span>
                <span class="tech-item"><i class="fas fa-cloud"></i> Cloudflare</span>
                <span class="tech-item"><i class="fas fa-fire"></i> Firebase</span>
                <span class="tech-item"><i class="fas fa-globe"></i> Netlify</span>
                <span class="tech-item"><i class="fab fa-node-js"></i> Alpine.js</span>
                <span class="tech-item"><i class="fas fa-flask"></i> Flask</span>
                <span class="tech-item"><i class="fab fa-react"></i> Next.js</span>
                <span class="tech-item"><i class="fab fa-tailwind"></i> Tailwind</span>
                <span class="tech-item"><i class="fas fa-database"></i> MySQL</span>
                <span class="tech-item"><i class="fas fa-database"></i> SQLite</span>
                <span class="tech-item"><i class="fas fa-database"></i> Supabase</span>
                <span class="tech-item"><i class="fas fa-paint-brush"></i> Canva</span>
                <span class="tech-item"><i class="fas fa-microchip"></i> Arduino</span>
                <span class="tech-item"><i class="fas fa-network-wired"></i> Cisco</span>
            </div>
        </div>

        <!-- ── Cybersecurity, AI/ML, Cloud ── -->
        <div class="two-col">
            <div class="card">
                <h3><i class="fas fa-shield-halved"></i> Cybersecurity</h3>
                <ul>
                    <li>Penetration Testing (Kali, Metasploit, Burp)</li>
                    <li>Network Forensics &amp; PCAP analysis</li>
                    <li>SIEM (Splunk, Wazuh) &amp; SOAR</li>
                    <li>Reverse Engineering (Ghidra, x64dbg)</li>
                    <li>OSINT &amp; Threat Hunting</li>
                </ul>
            </div>
            <div class="card">
                <h3><i class="fas fa-brain"></i> AI / ML</h3>
                <ul>
                    <li>Supervised / Unsupervised Learning</li>
                    <li>NLP for security logs &amp; threat intel</li>
                    <li>Anomaly detection (Isolation Forest, LSTM)</li>
                    <li>Federated Learning &amp; Privacy-Preserving AI</li>
                    <li>TensorFlow, PyTorch, Scikit-learn</li>
                </ul>
            </div>
        </div>
        <div class="card" style="margin: 0.5rem 0 1.5rem;">
            <h3><i class="fas fa-cloud-upload-alt"></i> Cloud &amp; DevOps</h3>
            <ul style="display:flex; flex-wrap:wrap; gap:0.5rem 1.5rem; list-style:none; padding:0;">
                <li style="display:flex; align-items:center; gap:0.4rem;"><i class="fas fa-check-circle" style="color:#00ff41; font-size:0.7rem;"></i> AWS (EC2, S3, IAM)</li>
                <li style="display:flex; align-items:center; gap:0.4rem;"><i class="fas fa-check-circle" style="color:#00ff41; font-size:0.7rem;"></i> Docker &amp; Kubernetes</li>
                <li style="display:flex; align-items:center; gap:0.4rem;"><i class="fas fa-check-circle" style="color:#00ff41; font-size:0.7rem;"></i> Terraform &amp; Ansible</li>
                <li style="display:flex; align-items:center; gap:0.4rem;"><i class="fas fa-check-circle" style="color:#00ff41; font-size:0.7rem;"></i> GitHub Actions / CI/CD</li>
                <li style="display:flex; align-items:center; gap:0.4rem;"><i class="fas fa-check-circle" style="color:#00ff41; font-size:0.7rem;"></i> Prometheus &amp; Grafana</li>
            </ul>
        </div>

        <hr class="divider" />

        <!-- ════════════════════════════════════════ -->
        <!-- 📊 GITHUB STATS                        -->
        <!-- ════════════════════════════════════════ -->
        <h2><i class="fas fa-chart-line"></i> GitHub Stats</h2>
        <div class="stats-grid">
            <img src="https://github-readme-stats.shion.dev/api?username=sariftachamo-9&theme=dark&hide_border=false&include_all_commits=true&count_private=false" alt="GitHub Stats" />
            <img src="https://streak-stats.demolab.com/?user=sariftachamo-9&theme=dark&hide_border=false" alt="GitHub Streak" />
        </div>
        <div style="text-align:center; margin: 0.5rem 0 1.8rem;">
            <img src="https://github-readme-stats.shion.dev/api/top-langs/?username=sariftachamo-9&theme=dark&hide_border=false&include_all_commits=true&count_private=false&layout=compact" alt="Top Languages" style="max-width:100%; border-radius:1.2rem;" />
        </div>

        <!-- ════════════════════════════════════════ -->
        <!-- 🏆 GITHUB TROPHIES                     -->
        <!-- ════════════════════════════════════════ -->
        <div class="trophy-wrap">
            <h2 style="justify-content:center; margin-bottom:0.8rem;"><i class="fas fa-award"></i> GitHub Trophies</h2>
            <img src="https://github-contributor-stats.vercel.app/api?username=sariftachamo-9&limit=5&theme=dark&combine_all_yearly_contributions=true" alt="GitHub Trophies" />
        </div>

        <!-- ════════════════════════════════════════ -->
        <!-- 📈 CONTRIBUTION GRAPH                  -->
        <!-- ════════════════════════════════════════ -->
        <div class="graph-wrap">
            <h2 style="justify-content:center; margin-bottom:0.8rem;"><i class="fas fa-chart-bar"></i> Contribution Graph</h2>
            <img src="https://github-readme-activity-graph.vercel.app/graph?username=sariftachamo-9&theme=react-dark&bg_color=0e131e&color=00ff41&line=00ff41&point=33ff77&hide_border=true" alt="Contribution Graph" />
        </div>

        <!-- ════════════════════════════════════════ -->
        <!-- 🐍 SNAKE CONTRIBUTION ANIMATION        -->
        <!-- ════════════════════════════════════════ -->
        <div class="snake-wrap">
            <h2 style="justify-content:center; margin-bottom:0.8rem;"><i class="fas fa-snake"></i> Snake Eating Contributions</h2>
            <img src="https://raw.githubusercontent.com/sariftachamo-9/sariftachamo-9/output/snake.svg" alt="Snake Animation" onerror="this.style.display='none'" />
            <p style="color:#8892a8; font-size:0.85rem; margin-top:0.4rem;">
                <i class="fas fa-info-circle"></i> Generated nightly — watch the snake gobble up your contributions!
            </p>
        </div>

        <hr class="divider" />

        <!-- ════════════════════════════════════════ -->
        <!-- 📚 RESEARCH INTERESTS + 2026 GOALS     -->
        <!-- ════════════════════════════════════════ -->
        <div class="two-col">
            <div class="card">
                <h3><i class="fas fa-microscope"></i> Research Interests</h3>
                <ul>
                    <li>Adversarial Machine Learning &amp; AI safety</li>
                    <li>Federated Learning for privacy-preserving security</li>
                    <li>Zero-day vulnerability discovery &amp; responsible disclosure</li>
                    <li>Quantum-resistant cryptography</li>
                    <li>Automated threat hunting with LLMs</li>
                </ul>
            </div>
            <div class="card">
                <h3><i class="fas fa-bullseye"></i> 2026 Goals</h3>
                <ul>
                    <li>🎯 Publish 2 first-author research papers</li>
                    <li>🎯 Complete OSCP certification</li>
                    <li>🎯 Build an open-source AI security toolkit</li>
                    <li>🎯 Contribute to 5+ OSS security projects</li>
                    <li>🎯 Speak at a major security conference</li>
                </ul>
            </div>
        </div>

        <hr class="divider" />

        <!-- ════════════════════════════════════════ -->
        <!-- 🌐 SOCIAL LINKS & CONTACT              -->
        <!-- ════════════════════════════════════════ -->
        <h2 style="justify-content:center;"><i class="fas fa-link"></i> Connect With Me</h2>
        <div class="social-row">
            <a href="https://discord.gg/55e4VebV"><i class="fab fa-discord"></i> Discord</a>
            <a href="https://linkedin.com/in/sarif-tachamo-06b9b9248"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
            <a href="mailto:sariftachamo.job@gmail.com"><i class="fas fa-envelope"></i> Email</a>
            <a href="#"><i class="fab fa-github"></i> GitHub</a>
            <a href="#"><i class="fab fa-twitter"></i> Twitter</a>
            <a href="#"><i class="fab fa-youtube"></i> YouTube</a>
        </div>

        <!-- ════════════════════════════════════════ -->
        <!-- 👀 VISITOR COUNTER                     -->
        <!-- ════════════════════════════════════════ -->
        <div class="visitor-wrap">
            <i class="fas fa-eye" style="color:#00ff41;"></i>
            <span style="margin-right:0.4rem;">Profile views:</span>
            <img src="https://komarev.com/ghpvc/?username=sariftachamo-9&icon=0&color=00ff41" alt="Visitor Counter" />
        </div>

        <hr class="divider" />

        <!-- ════════════════════════════════════════ -->
        <!-- ☕ SUPPORT SECTION                     -->
        <!-- ════════════════════════════════════════ -->
        <div style="text-align:center; padding: 0.4rem 0 0.2rem;">
            <h2 style="justify-content:center; font-size:1.5rem;"><i class="fas fa-heart" style="color:#ff6b6b;"></i> Support My Work</h2>
            <p style="color:#8892a8; margin-bottom:1rem; font-size:0.95rem;">
                If you find my projects useful, consider buying me a coffee ☕
            </p>
            <div class="support-row">
                <a class="bmc" href="https://buymeacoffee.com/BuyMeaCoffee"><i class="fas fa-mug-hot"></i> Buy Me a Coffee</a>
                <a class="paypal" href="https://www.paypal.com/ncp/payment/5NECQWP96EVHY"><i class="fab fa-paypal"></i> PayPal</a>
            </div>
        </div>

        <!-- ── Footer ── -->
        <hr class="divider" style="margin-top:2.2rem;" />
        <p style="text-align:center; font-size:0.8rem; color:#3a4658; margin-top:1rem;">
            <i class="fas fa-shield-halved" style="color:#00ff41;"></i>
            Built with <span style="color:#00ff41;">♥</span> by Sarif Tachamo &middot; Cyberpunk &middot; 2026
        </p>

    </div>
    <!-- /container -->

</body>
</html>
