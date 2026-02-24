<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Raghav Shukla · Applied AI · Computer Vision</title>
    <!-- Professional fonts: Inter + Fira Code (clean, modern, technical) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600&family=Inter:opsz,wght@14..32,400;14..32,600;14..32,700&display=swap" rel="stylesheet">
    <!-- Font Awesome 6 (free) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #f8fafc;  /* light neutral background – professional but we will keep main container dark to match github theme */
            font-family: 'Inter', sans-serif;
            display: flex;
            justify-content: center;
            padding: 2rem 1.5rem;
            line-height: 1.5;
            color: #e2e8f0;
            background-color: #0b1120;  /* deep navy background, easy on eyes, professional */
        }

        .container {
            max-width: 1200px;
            width: 100%;
        }

        /* ========== PROFESSIONAL COLOR PALETTE ========== 
           background: #0b1120 (deep slate)
           surface: #1e293b (dark blue-gray)
           accent: #3b82f6 (clean blue, not overly flashy)
           secondary accent: #8b5cf6 (subtle purple)
           text: #e2e8f0 / #94a3b8
           border: #334155
        */

        /* header - clean, minimal, with subtle accent */
        .profile-header {
            background: #1e293b;
            border-radius: 32px;
            padding: 3rem 2rem 2.5rem;
            margin-bottom: 2.5rem;
            border: 1px solid #334155;
            box-shadow: 0 20px 35px -10px rgba(0,0,0,0.6);
            text-align: center;
        }

        .name {
            font-size: clamp(3rem, 8vw, 4.5rem);
            font-weight: 700;
            letter-spacing: -0.02em;
            color: #f1f5f9;
            line-height: 1.1;
            margin-bottom: 0.5rem;
        }

        .badge-row {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 0.8rem 1.8rem;
            font-size: 1.2rem;
            color: #94a3b8;
        }

        .badge-row span {
            background: #0f172a;
            padding: 0.3rem 1.4rem;
            border-radius: 40px;
            border: 1px solid #3b82f6;
            color: #cbd5e1;
            font-weight: 500;
        }

        /* social links - professional, rectangular minimal */
        .social-links {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.5rem 2rem;
            margin: 2rem 0 1rem;
        }

        .social-item {
            background: #1e293b;
            padding: 0.6rem 1.8rem;
            border-radius: 40px;
            border: 1px solid #334155;
            color: #cbd5e1;
            text-decoration: none;
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            transition: 0.15s;
            font-size: 1.1rem;
        }

        .social-item:hover {
            border-color: #3b82f6;
            background: #2d3a4f;
            color: white;
        }

        .social-item i {
            color: #3b82f6;
            font-size: 1.3rem;
        }

        /* status / tagline — clean, no overused gimmicks */
        .status-line {
            background: #0f172a;
            border-radius: 60px;
            padding: 1rem 2rem;
            margin: 2.5rem 0;
            border: 1px solid #3b82f6;
            text-align: center;
            font-size: 1.2rem;
            color: #94a3b8;
            font-weight: 400;
            border-left: 6px solid #8b5cf6;
        }

        .status-line strong {
            color: #f1f5f9;
            font-weight: 600;
        }

        /* section titles — professional, understated */
        .section-title {
            display: flex;
            align-items: center;
            gap: 12px;
            margin: 3rem 0 1.5rem;
            border-bottom: 2px solid #334155;
            padding-bottom: 0.6rem;
        }

        .section-title h2 {
            font-size: 2rem;
            font-weight: 600;
            color: #e2e8f0;
            letter-spacing: -0.01em;
        }

        .section-title i {
            font-size: 2rem;
            color: #3b82f6;
        }

        /* quote / philosophy — professional and sharp */
        .philosophy {
            background: #1e293b;
            border-radius: 32px;
            padding: 2rem;
            border: 1px solid #334155;
            font-size: 1.2rem;
            color: #cbd5e1;
            box-shadow: inset 0 2px 8px rgba(0,0,0,0.3);
            margin: 2.5rem 0;
            border-left: 8px solid #8b5cf6;
        }

        .philosophy i {
            color: #3b82f6;
            margin-right: 10px;
        }

        /* skills grid — clean, techy, but professional */
        .skills-panel {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 16px;
            background: #1e293b;
            padding: 2rem;
            border-radius: 48px;
            border: 1px solid #334155;
        }

        .skill-tag {
            background: #0f172a;
            padding: 0.5rem 1.5rem;
            border-radius: 40px;
            border: 1px solid #3b82f6;
            color: #cbd5e1;
            font-size: 1.1rem;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            transition: 0.1s;
        }

        .skill-tag i {
            color: #8b5cf6;
        }

        /* project cards — clean, consistent, professional */
        .project-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            justify-content: center;
        }

        .project-card {
            flex: 1 1 340px;
            background: #1e293b;
            border-radius: 32px;
            padding: 2rem;
            border: 1px solid #334155;
            transition: 0.2s;
            box-shadow: 0 12px 30px -12px #00000080;
        }

        .project-card:hover {
            border-color: #3b82f6;
            box-shadow: 0 25px 35px -16px #3b82f660;
            background: #263445;
        }

        .project-icon {
            font-size: 2.8rem;
            color: #3b82f6;
            margin-bottom: 0.8rem;
        }

        .project-title {
            font-size: 1.9rem;
            font-weight: 600;
            color: #f1f5f9;
            margin-bottom: 0.3rem;
        }

        .project-desc {
            color: #94a3b8;
            margin: 1rem 0 1.6rem;
            line-height: 1.5;
        }

        .project-link {
            background: transparent;
            border: 2px solid #3b82f6;
            border-radius: 40px;
            padding: 0.5rem 1.6rem;
            display: inline-block;
            color: #e2e8f0;
            text-decoration: none;
            font-weight: 600;
            transition: 0.15s;
        }

        .project-link:hover {
            background: #3b82f6;
            color: #0b1120;
            border-color: #8b5cf6;
        }

        /* achievements — clean chips */
        .achievement-wall {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 16px;
            background: #1e293b;
            padding: 1.8rem;
            border-radius: 60px;
            border: 1px solid #334155;
            margin: 2.5rem 0;
        }

        .achieve-item {
            background: #0f172a;
            padding: 0.5rem 1.8rem;
            border-radius: 40px;
            border: 1px solid #8b5cf6;
            color: #cbd5e1;
            font-weight: 500;
            font-size: 1rem;
        }

        .achieve-item i {
            color: #fbbf24;  /* gold */
            margin-right: 10px;
        }

        /* stats row — clean images, no distortion */
        .stats-row {
            display: flex;
            flex-wrap: wrap;
            gap: 1.8rem;
            justify-content: center;
            margin: 3rem 0;
        }

        .stat-card {
            background: #1e293b;
            border-radius: 32px;
            border: 1px solid #334155;
            padding: 1rem;
            flex: 1 1 300px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .stat-card img {
            max-width: 100%;
            border-radius: 24px;
            border: 1px solid #3b82f6;
        }

        /* footer — minimal */
        .footer {
            background: #1e293b;
            border-radius: 40px 40px 24px 24px;
            padding: 2.5rem 2rem;
            margin-top: 4rem;
            border: 1px solid #334155;
            text-align: center;
        }

        .footer-main {
            font-size: 2.4rem;
            font-weight: 600;
            color: #f1f5f9;
            letter-spacing: -0.5px;
        }

        .footer-sub {
            color: #94a3b8;
            margin: 1.2rem 0 0.8rem;
        }

        hr {
            border: 1px solid #334155;
            width: 40%;
            margin: 1.8rem auto;
        }

        /* utilities */
        .text-accent {
            color: #3b82f6;
        }

        @media (max-width: 600px) {
            .name { font-size: 2.8rem; }
            .badge-row span { font-size: 1rem; }
        }

    </style>
</head>
<body>
    <div class="container">

        <!-- HEADER – professional & sharp -->
        <div class="profile-header">
            <div class="name">Raghav Shukla</div>
            <div class="badge-row">
                <span>Applied AI</span>
                <span>Computer Vision</span>
                <span>Edge Privacy</span>
            </div>
        </div>

        <!-- SOCIAL / CONTACT (clean, professional) -->
        <div class="social-links">
            <a href="https://github.com/PyRaghaw" class="social-item"><i class="fab fa-github"></i> GitHub</a>
            <a href="https://linkedin.com/in/raghaw-shukla-a49727326" class="social-item"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
            <a href="mailto:sraghaw911@gmail.com" class="social-item"><i class="fas fa-envelope"></i> Email</a>
            <a href="https://raghawshukla.dev" class="social-item"><i class="fas fa-globe"></i> Portfolio</a>
        </div>

        <!-- CURRENT FOCUS / PROFESSIONAL TAGLINE (replaces over-the-top typing) -->
        <div class="status-line">
            <i class="fas fa-microchip text-accent"></i> <strong>Current focus:</strong> Offline-first vision systems · Privacy-preserving AI · Low-latency edge inference
        </div>

        <!-- CORE PHILOSOPHY (professional, less dramatic) -->
        <div class="philosophy">
            <i class="fas fa-quote-left"></i> 
            I architect computer vision systems that operate at the edge — combining model efficiency with absolute data privacy. 
            My work emphasizes real-time performance without cloud dependency.
            <i class="fas fa-quote-right"></i>
        </div>

        <!-- TECH STACK – clean representation -->
        <div class="section-title">
            <i class="fas fa-code"></i>
            <h2>Technical stack</h2>
        </div>
        <div class="skills-panel">
            <span class="skill-tag"><i class="fab fa-python"></i> Python</span>
            <span class="skill-tag"><i class="fas fa-eye"></i> OpenCV</span>
            <span class="skill-tag"><i class="fas fa-brain"></i> PyTorch</span>
            <span class="skill-tag"><i class="fas fa-bolt"></i> FastAPI</span>
            <span class="skill-tag"><i class="fas fa-flask"></i> Flask</span>
            <span class="skill-tag"><i class="fab fa-git-alt"></i> Git</span>
            <span class="skill-tag"><i class="fab fa-docker"></i> Docker</span>
            <span class="skill-tag"><i class="fas fa-database"></i> MongoDB</span>
            <span class="skill-tag"><i class="fab fa-react"></i> React</span>
            <span class="skill-tag"><i class="fab fa-linux"></i> Linux</span>
            <span class="skill-tag"><i class="fas fa-cube"></i> TensorFlow</span>
            <span class="skill-tag"><i class="fas fa-paint-brush"></i> Tailwind</span>
            <span class="skill-tag"><i class="fas fa-database"></i> PostgreSQL</span>
        </div>

        <!-- PROJECTS – professional, descriptive -->
        <div class="section-title">
            <i class="fas fa-folder-open"></i>
            <h2>Key projects</h2>
        </div>

        <div class="project-grid">
            <!-- GESTURE OS -->
            <div class="project-card">
                <div class="project-icon"><i class="fas fa-hand-peace"></i></div>
                <div class="project-title">Gesture Control System</div>
                <div class="project-desc">
                    Real-time hand gesture recognition for touchless interaction. Pure on-device inference (<50ms latency). 
                    Built with OpenCV and MediaPipe, deployed on edge devices.
                </div>
                <a href="https://github.com/PyRaghaw/Gesture-Control-System" class="project-link">Repository →</a>
            </div>
            <!-- MAILMIND -->
            <div class="project-card">
                <div class="project-icon"><i class="fas fa-envelope-open-text"></i></div>
                <div class="project-title">MailMind</div>
                <div class="project-desc">
                    Privacy-first email intent classifier. All processing in-memory; no data persisted. 
                    Uses transformer models with ONNX runtime for fast, zero-trace analysis.
                </div>
                <a href="https://github.com/PyRaghaw/MailMind" class="project-link">Repository →</a>
            </div>
        </div>

        <!-- ACHIEVEMENTS / RECOGNITION (professional tone) -->
        <div class="section-title">
            <i class="fas fa-award"></i>
            <h2>Recognitions</h2>
        </div>
        <div class="achievement-wall">
            <span class="achieve-item"><i class="fas fa-trophy"></i> SIH 2024 · National Finalist</span>
            <span class="achieve-item"><i class="fas fa-trophy"></i> KuRook Shetra 2.0</span>
            <span class="achieve-item"><i class="fas fa-trophy"></i> QuizON · Winner</span>
            <span class="achieve-item"><i class="fas fa-trophy"></i> Syntaxical 2.0</span>
            <span class="achieve-item"><i class="fas fa-trophy"></i> TechFiesta 25</span>
            <span class="achieve-item"><i class="fas fa-trophy"></i> MCKVIE Hackathon 2K25</span>
        </div>

        <!-- STATS – clean github stats -->
        <div class="section-title">
            <i class="fas fa-chart-bar"></i>
            <h2>GitHub activity</h2>
        </div>
        <div class="stats-row">
            <div class="stat-card">
                <img src="https://github-readme-stats.vercel.app/api?username=PyRaghaw&show_icons=true&theme=radical&hide_border=true&bg_color=1e293b&title_color=3b82f6&icon_color=8b5cf6&text_color=cbd5e1" alt="github stats">
            </div>
            <div class="stat-card">
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=PyRaghaw&theme=radical&hide_border=true&background=1e293b&ring=3b82f6&fire=8b5cf6&dates=94a3b8" alt="streak">
            </div>
        </div>

        <!-- PROFESSIONAL FOOTER -->
        <div class="footer">
            <div class="footer-main">Raghav Shukla</div>
            <div class="footer-sub">Applied AI · Computer Vision · Edge privacy</div>
            <hr>
            <div style="color: #94a3b8; font-size: 0.95rem;">
                <i class="fas fa-code"></i> Built with clean architecture · Offline-first mindset
            </div>
            <div style="margin-top: 1.5rem; font-size: 0.9rem; color: #3b82f6;">
                <i class="fas fa-shield-alt"></i> Privacy by design · Low latency · Sovereign intelligence
            </div>
        </div>

    </div> <!-- end container -->
</body>
</html>
