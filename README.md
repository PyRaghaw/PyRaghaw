<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RAGHAW SHUKLA · NEURAL EDGE FORGER</title>
    <!-- Google Fonts: Orbitron + JetBrains Mono for a technical edge -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;800&family=Orbitron:wght@400;700;900&display=swap" rel="stylesheet">
    <!-- Font Awesome 6 (free) for crisp icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #0d1117;
            background-image: radial-gradient(circle at 20% 30%, #1a0033 0%, #0d1117 90%);
            font-family: 'JetBrains Mono', monospace;
            color: #e0b0ff;
            display: flex;
            justify-content: center;
            padding: 2rem 1rem;
            line-height: 1.6;
        }

        .matrix-container {
            max-width: 1100px;
            width: 100%;
        }

        /* NEON GLOW + CYBER LAYERS */
        .glow-text {
            text-shadow: 0 0 8px #ff00ff, 0 0 20px #ff00ff80;
        }

        .neon-border {
            border: 1px solid #ff00ff;
            box-shadow: 0 0 15px #ff00ff, inset 0 0 10px #ff00ff40;
        }

        /* HEADER BANNER (capsule-render simulation) */
        .venom-header {
            background: linear-gradient(145deg, #0a0016 0%, #220033 100%);
            padding: 3rem 1rem 2.5rem;
            border-radius: 80px 80px 30px 30px;
            text-align: center;
            border: 1px solid #ff44cc;
            box-shadow: 0 0 40px #ff00cc60, inset 0 0 20px #ff00aa20;
            margin-bottom: 2.5rem;
            position: relative;
            overflow: hidden;
        }

        .venom-header::before {
            content: "";
            position: absolute;
            top: -50%;
            left: -20%;
            width: 140%;
            height: 200%;
            background: repeating-linear-gradient(45deg, transparent, transparent 20px, #ff00ff10 20px, #ff00ff15 40px);
            pointer-events: none;
            rotate: 10deg;
        }

        .main-title {
            font-family: 'Orbitron', sans-serif;
            font-size: clamp(3.2rem, 15vw, 5.6rem);
            font-weight: 900;
            color: #ff00ff;
            letter-spacing: 6px;
            animation: flicker 4s infinite;
            margin-bottom: 0.2rem;
        }

        .subtitle {
            font-size: 1.4rem;
            color: #ff88cc;
            letter-spacing: 3px;
            font-weight: 400;
            background: #0d1117aa;
            display: inline-block;
            padding: 0.2rem 2rem;
            border-radius: 40px;
            backdrop-filter: blur(3px);
            border: 1px dashed #ff44aa;
        }

        @keyframes flicker {
            0% { text-shadow: 0 0 5px #ff00ff, 0 0 20px #ff00ff; }
            25% { text-shadow: 0 0 8px #ff66ff, 0 0 30px #ff44ff; }
            50% { text-shadow: 0 0 5px #ff00cc, 0 0 15px #ff00aa; }
            75% { text-shadow: 0 0 10px #ff88ff, 0 0 40px #ff22ff; }
            100% { text-shadow: 0 0 5px #ff00ff, 0 0 20px #ff00ff; }
        }

        /* badge row */
        .badge-chain {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.2rem;
            margin: 2rem 0 1.2rem;
        }

        .neural-badge {
            background: #00000040;
            border: 1px solid #ff00ff;
            border-radius: 40px;
            padding: 0.5rem 1.5rem;
            font-weight: 600;
            color: #ffb6ff;
            backdrop-filter: blur(4px);
            transition: 0.2s;
            font-size: 1rem;
            box-shadow: 0 0 12px #ff00ff60;
        }

        .neural-badge i {
            color: #ff00ff;
            margin-right: 8px;
        }

        .neural-badge:hover {
            background: #ff00ff20;
            box-shadow: 0 0 24px #ff00ff;
            color: white;
        }

        /* typing quote */
        .typing-quote {
            background: #10001c;
            padding: 1.6rem 2rem;
            border-radius: 40px;
            margin: 2rem 0;
            border-left: 6px solid #ff00ff;
            font-size: 1.3rem;
            box-shadow: 0 0 35px #ff00aa40;
            font-family: 'Orbitron', monospace;
            font-weight: 500;
            text-align: center;
            color: #f0c0ff;
        }

        .typing-quote i {
            color: #ff00ff;
            margin: 0 10px;
        }

        /* section headers */
        .section-title {
            font-family: 'Orbitron', sans-serif;
            font-size: 2.2rem;
            font-weight: 800;
            margin: 2.5rem 0 1.8rem;
            display: flex;
            align-items: center;
            gap: 12px;
            border-bottom: 2px solid #ff44aa;
            padding-bottom: 8px;
            letter-spacing: 2px;
        }

        .section-title i {
            color: #ff00ff;
            font-size: 2.4rem;
        }

        /* skill grid */
        .skill-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 16px;
            background: #0a0018;
            padding: 2rem;
            border-radius: 60px;
            border: 1px solid #ff44aa;
            box-shadow: inset 0 0 30px #150022, 0 0 30px #ff00aa30;
        }

        .skill-icon {
            background: #11001c;
            padding: 10px 18px;
            border-radius: 40px;
            border: 1px solid #ff66cc;
            color: #ffb3ff;
            font-size: 1.5rem;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            transition: 0.15s;
            box-shadow: 0 0 8px #ff00ff;
        }

        .skill-icon span {
            font-size: 1rem;
            font-weight: 600;
        }

        .skill-icon:hover {
            transform: scale(1.08);
            background: #ff00ff20;
            border-color: white;
            box-shadow: 0 0 22px #ff88ff;
        }

        /* project cards */
        .project-row {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            justify-content: center;
            margin: 2rem 0;
        }

        .project-card {
            flex: 1 1 300px;
            background: #0e001b;
            border-radius: 40px;
            padding: 1.8rem 1.5rem 2rem;
            border: 1px solid #ff44bb;
            box-shadow: 0 0 35px #ff00aa50, inset 0 0 10px #ff00aa20;
            transition: 0.2s;
            backdrop-filter: blur(3px);
            display: flex;
            flex-direction: column;
        }

        .project-card:hover {
            border-color: #ffaaff;
            box-shadow: 0 0 55px #ff66ff;
            transform: translateY(-6px);
        }

        .project-img {
            width: 100%;
            height: 180px;
            background: #220033;
            border-radius: 30px;
            border: 2px solid #ff44aa;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            color: #ff44aa;
            margin-bottom: 1.2rem;
            background-image: linear-gradient(145deg, #2a0040, #100020);
            box-shadow: inset 0 0 30px #000;
        }

        .project-img i {
            filter: drop-shadow(0 0 10px #ff00ff);
        }

        .project-title {
            font-family: 'Orbitron', sans-serif;
            font-size: 1.8rem;
            font-weight: 700;
            color: #ffaaff;
        }

        .project-desc {
            font-size: 0.95rem;
            color: #ccaaff;
            margin: 10px 0 15px;
            flex-grow: 1;
        }

        .project-link {
            font-size: 1rem;
            background: transparent;
            border: 1px solid #ff44aa;
            border-radius: 30px;
            padding: 8px 18px;
            display: inline-block;
            width: fit-content;
            color: #ffc0ff;
            text-decoration: none;
            transition: 0.1s;
        }

        .project-link:hover {
            background: #ff00ff;
            color: black;
            font-weight: bold;
            box-shadow: 0 0 30px #ffaaff;
        }

        /* trophies */
        .trophy-cluster {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 14px;
            background: #0d0018;
            padding: 1.5rem;
            border-radius: 70px;
            border: 1px dashed #ff44aa;
            margin: 2rem 0;
        }

        .trophy-item {
            background: #1a002b;
            padding: 0.6rem 1.4rem;
            border-radius: 40px;
            font-weight: 600;
            border: 1px solid #ff66cc;
            color: #ffb8ff;
            font-size: 0.9rem;
            box-shadow: 0 0 6px #ff00ff;
        }

        .trophy-item i {
            color: #ff99ff;
            margin-right: 8px;
        }

        /* stats row */
        .stats-row {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
            margin: 30px 0;
        }

        .stat-card {
            background: #0b0015;
            border-radius: 30px;
            border: 1px solid #ff44aa;
            padding: 1.2rem;
            flex: 1 1 300px;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0 0 30px #ff00aa30;
        }

        .stat-card img {
            max-width: 100%;
            border-radius: 20px;
            border: 1px solid #ff88cc;
        }

        /* footer */
        .neural-footer {
            text-align: center;
            margin-top: 4rem;
            padding: 2rem 1rem;
            border-top: 2px solid #ff44aa;
            font-size: 0.9rem;
            color: #bb88ff;
            letter-spacing: 2px;
            position: relative;
        }

        .neural-footer sub {
            color: #ff55aa;
            font-size: 1rem;
        }

        /* glitch / line effect */
        .glitch-patch {
            background: #ff00ff10;
            height: 2px;
            width: 100%;
            margin: 20px 0;
            box-shadow: 0 0 18px #ff00ff;
        }

        /* responsive */
        @media (max-width: 600px) {
            .main-title { font-size: 3.2rem; letter-spacing: 2px; }
            .subtitle { font-size: 1rem; }
        }
    </style>
</head>
<body>
    <div class="matrix-container">

        <!-- VENOM HEADER (capsule style) -->
        <div class="venom-header">
            <div class="main-title">RAGHAW SHUKLA</div>
            <div class="subtitle">
                <i class="fas fa-microchip"></i> NEURAL EDGE FORGER · OFFLINE VISION ARCHITECT <i class="fas fa-eye"></i>
            </div>
            <!-- invisible extra text to match original vibe -->
            <div style="margin-top: 1rem; font-size: 0.9rem; opacity: 0.8; letter-spacing: 3px;">
                <i class="fas fa-shield-halved"></i> PRIVACY SHIELD · ZERO-CLOOD EXECUTION <i class="fas fa-shield-halved"></i>
            </div>
        </div>

        <!-- BADGE ROW (github, linkedin, mail, portfolio) -->
        <div class="badge-chain">
            <a href="https://github.com/PyRaghaw" style="text-decoration: none;"><span class="neural-badge"><i class="fab fa-github"></i> GITHUB</span></a>
            <a href="https://linkedin.com/in/raghaw-shukla-a49727326" style="text-decoration: none;"><span class="neural-badge"><i class="fab fa-linkedin-in"></i> LINKEDIN</span></a>
            <a href="mailto:sraghaw911@gmail.com" style="text-decoration: none;"><span class="neural-badge"><i class="fas fa-envelope"></i> EMAIL</span></a>
            <a href="https://raghawshukla.dev" style="text-decoration: none;"><span class="neural-badge"><i class="fas fa-globe"></i> PORTFOLIO</span></a>
        </div>

        <!-- TYPING SVG SIMULATION (custom animated quote) -->
        <div class="typing-quote">
            <i class="fas fa-bolt"></i> NEURAL CORE BOOTING... EDGE INTELLIGENCE ACTIVATED · PRIVACY SHIELD DEPLOYED <i class="fas fa-bolt"></i><br>
            <span style="font-size: 0.9rem; color: #ff80bf;">VISION SYSTEMS ONLINE · ZERO-CLOUD EXECUTION ENGAGED</span>
        </div>

        <!-- NEURAL PROTOCOL LINE -->
        <div style="display: flex; justify-content: center; gap: 2rem; flex-wrap: wrap; background: #1a0033; border-radius: 60px; padding: 1rem; border: 1px solid #ff00ff80;">
            <code style="color: #ffaaff;"><i class="fas fa-skull"></i> NEURAL PROTOCOL: Forge sovereign minds on the edge</code>
            <code style="color: #ffaaff;"><i class="fas fa-crown"></i> PRIMARY DOMAIN: Computer Vision + Absolute Privacy</code>
        </div>

        <!-- PHILOSOPHY BLOCK -->
        <div style="margin: 3rem 0; padding: 2rem; background: linear-gradient(145deg,#0f001b,#1e0033); border-radius: 50px; box-shadow: 0 0 40px #ff00aa40;">
            <p style="font-size: 1.5rem; font-style: italic; text-align: center; font-weight: 500;">
                <i class="fas fa-quote-left" style="color: #ff44aa;"></i> 
                Clouds are prisons for data. I build neural fortresses—<br>where models evolve in silence, latency vanishes,<br>and intelligence claims its freedom in raw silicon darkness.
                <i class="fas fa-quote-right" style="color: #ff44aa;"></i>
            </p>
        </div>

        <!-- NEURAL FORGE (SKILLS) -->
        <div class="section-title">
            <i class="fas fa-bolt"></i> NEURAL FORGE <i class="fas fa-code"></i>
        </div>
        <div class="skill-grid">
            <span class="skill-icon"><i class="fab fa-python"></i><span>python</span></span>
            <span class="skill-icon"><i class="fas fa-eye"></i><span>opencv</span></span>
            <span class="skill-icon"><i class="fas fa-brain"></i><span>pytorch</span></span>
            <span class="skill-icon"><i class="fas fa-rocket"></i><span>fastapi</span></span>
            <span class="skill-icon"><i class="fas fa-flask"></i><span>flask</span></span>
            <span class="skill-icon"><i class="fab fa-git-alt"></i><span>git</span></span>
            <span class="skill-icon"><i class="fab fa-docker"></i><span>docker</span></span>
            <span class="skill-icon"><i class="fas fa-database"></i><span>mongodb</span></span>
            <span class="skill-icon"><i class="fab fa-react"></i><span>react</span></span>
            <span class="skill-icon"><i class="fab fa-linux"></i><span>linux</span></span>
            <span class="skill-icon"><i class="fas fa-cube"></i><span>tensorflow</span></span>
            <span class="skill-icon"><i class="fas fa-paint-brush"></i><span>tailwind</span></span>
            <span class="skill-icon"><i class="fas fa-database"></i><span>postgres</span></span>
        </div>

        <!-- DEPLOYED ENTITIES (PROJECTS) -->
        <div class="section-title">
            <i class="fas fa-cubes"></i> NEURAL MATRIX [DEPLOYED ENTITIES]
        </div>

        <div class="project-row">
            <!-- GESTURE OS -->
            <div class="project-card">
                <div class="project-img"><i class="fas fa-hand-peace fa-4x"></i></div>
                <div class="project-title">🧬 GESTURE OS</div>
                <div class="project-desc"><strong>Quantum Hand Interface</strong> — <50ms edge CV OS. Gestures command reality. No cloud, pure local neural sovereignty.</div>
                <a href="https://github.com/PyRaghaw/Gesture-Control-System" class="project-link"><i class="fas fa-arrow-right"></i> → ENTER MATRIX</a>
            </div>
            <!-- MAILMIND -->
            <div class="project-card">
                <div class="project-img"><i class="fas fa-envelope-open-text fa-4x"></i></div>
                <div class="project-title">🕳️ MAILMIND</div>
                <div class="project-desc"><strong>Zero-Trace Neural Scan</strong> — In-memory privacy vault. Data dies after insight. Engineered oblivion for intelligence.</div>
                <a href="https://github.com/PyRaghaw/MailMind" class="project-link"><i class="fas fa-arrow-right"></i> → ENTER MATRIX</a>
            </div>
        </div>

        <!-- EVENT HORIZON: TROPHIES -->
        <div class="section-title">
            <i class="fas fa-trophy"></i> EVENT HORIZON [NEURAL TROPHIES]
        </div>

        <div class="trophy-cluster">
            <span class="trophy-item"><i class="fas fa-medal"></i> SIH 2024 National Forge</span>
            <span class="trophy-item"><i class="fas fa-medal"></i> KuRook Shetra 2.0 Strategic</span>
            <span class="trophy-item"><i class="fas fa-medal"></i> QuizON Knowledge Burst</span>
            <span class="trophy-item"><i class="fas fa-medal"></i> Syntaxical 2.0 Tech Vortex</span>
            <span class="trophy-item"><i class="fas fa-medal"></i> TechFiesta 25 Innovation</span>
            <span class="trophy-item"><i class="fas fa-medal"></i> MCKVIE Hackathon 2K25 AI</span>
        </div>

        <!-- QUANTUM METRICS (stats) -->
        <div class="section-title">
            <i class="fas fa-chart-line"></i> QUANTUM METRICS
        </div>

        <div class="stats-row">
            <div class="stat-card">
                <img src="https://github-readme-stats.vercel.app/api?username=PyRaghaw&show_icons=true&theme=radical&hide_border=true&bg_color=0d1117&title_color=ff00ff&icon_color=ff00ff&text_color=ff69b4" alt="github stats">
            </div>
            <div class="stat-card">
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=PyRaghaw&theme=radical&hide_border=true&background=0d1117&ring=ff00ff&fire=ff00ff&dates=ff69b4" alt="streak stats">
            </div>
        </div>

        <!-- CAPSULE FOOTER (venom style) -->
        <div style="margin: 4rem 0 2rem; background: #0d1117; border-radius: 100px 100px 30px 30px; padding: 2rem 1rem; text-align: center; border: 1px solid #ff00ff; box-shadow: 0 0 50px #ff00aa;">
            <div style="font-size: 2.5rem; font-weight: 900; color: #ff00ff; letter-spacing: 3px; animation: flicker 3s infinite;">NEURAL LINK STABLE</div>
            <div style="margin-top: 20px; color: #ff88cc; font-size: 0.9rem;">
                <i class="fas fa-code"></i> // CORE FORGED — RAGHAW SHUKLA // EDGE NEURONS FIRING //
            </div>
            <div style="margin-top: 8px; color: #b86eff;">
                <sub>PRIVACY SHIELD · OFFLINE INFERENCE · EDGE SOVEREIGNTY</sub>
            </div>
        </div>

        <!-- tiny glitch line -->
        <div class="glitch-patch"></div>
        <p style="text-align: center; color: #cc88ff;">⚡ neural edge — zero cloud, full silence ⚡</p>
    </div>
</body>
</html>
