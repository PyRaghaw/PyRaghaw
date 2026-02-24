<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Raghaw Shukla · Applied AI · Computer Vision</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;600&family=Inter:opsz,wght@14..32,400;14..32,600;14..32,700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #0b1120;
            font-family: 'Inter', sans-serif;
            display: flex;
            justify-content: center;
            padding: 2rem 1.5rem;
            line-height: 1.5;
            color: #e2e8f0;
        }

        .container {
            max-width: 1200px;
            width: 100%;
        }

        .profile-header {
            background: #1e293b;
            border-radius: 32px;
            padding: 3rem 2rem 2.5rem;
            margin-bottom: 2.5rem;
            border: 1px solid #334155;
            box-shadow: 0 20px 35px -10px rgba(0, 0, 0, 0.6);
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

        .philosophy {
            background: #1e293b;
            border-radius: 32px;
            padding: 2rem;
            border: 1px solid #334155;
            font-size: 1.2rem;
            color: #cbd5e1;
            box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.3);
            margin: 2.5rem 0;
            border-left: 8px solid #8b5cf6;
        }

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
        }

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
        }

        .footer {
            background: #1e293b;
            border-radius: 40px 40px 24px 24px;
            padding: 2.5rem 2rem;
            margin-top: 4rem;
            border: 1px solid #334155;
            text-align: center;
        }

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
        <div class="profile-header">
            <div class="name">Raghaw Shukla</div>
            <div class="badge-row">
                <span>Applied AI</span>
                <span>Computer Vision</span>
                <span>Edge Privacy</span>
            </div>
        </div>

        <div class="social-links">
            <a href="https://github.com/PyRaghaw" class="social-item"><i class="fab fa-github"></i> GitHub</a>
            <a href="https://linkedin.com/in/raghaw-shukla-a49727326" class="social-item"><i class="fab fa-linkedin-in"></i> LinkedIn</a>
            <a href="mailto:sraghaw911@gmail.com" class="social-item"><i class="fas fa-envelope"></i> Email</a>
            <a href="https://raghawshukla.dev" class="social-item"><i class="fas fa-globe"></i> Portfolio</a>
        </div>

        <div class="status-line">
            <i class="fas fa-microchip text-accent"></i> 
            <strong>Current focus:</strong> Offline-first vision systems · Privacy-preserving AI · Low-latency edge inference
        </div>

        <div class="philosophy">
            <i class="fas fa-quote-left"></i> 
            I architect computer vision systems that operate at the edge — combining model efficiency with absolute data privacy.
            <i class="fas fa-quote-right"></i>
        </div>

        <div class="section-title">
            <i class="fas fa-code"></i>
            <h2>Technical stack</h2>
        </div>
        <div class="skills-panel">
            <span class="skill-tag"><i class="fab fa-python"></i> Python</span>
            <span class="skill-tag"><i class="fas fa-eye"></i> OpenCV</span>
            <span class="skill-tag"><i class="fas fa-brain"></i> PyTorch</span>
            <span class="skill-tag"><i class="fas fa-bolt"></i> FastAPI</span>
            <span class="skill-tag"><i class="fab fa-docker"></i> Docker</span>
            <span class="skill-tag"><i class="fab fa-react"></i> React</span>
        </div>

        <div class="section-title">
            <i class="fas fa-folder-open"></i>
            <h2>Key projects</h2>
        </div>
        <div class="project-grid">
            <div class="project-card">
                <div class="project-icon"><i class="fas fa-hand-peace"></i></div>
                <div class="project-title">Gesture Control</div>
                <div class="project-desc">Real-time hand gesture recognition (<50ms latency). Built with OpenCV and MediaPipe.</div>
                <a href="https://github.com/PyRaghaw/Gesture-Control-System" class="project-link">Repository →</a>
            </div>
            <div class="project-card">
                <div class="project-icon"><i class="fas fa-envelope-open-text"></i></div>
                <div class="project-title">MailMind</div>
                <div class="project-desc">Privacy-first email intent classifier using ONNX runtime for zero-trace analysis.</div>
                <a href="https://github.com/PyRaghaw/MailMind" class="project-link">Repository →</a>
            </div>
        </div>

        <div class="section-title">
            <i class="fas fa-award"></i>
            <h2>Recognitions</h2>
        </div>
        <div class="achievement-wall">
            <span class="achieve-item"><i class="fas fa-trophy"></i> SIH 2024 · National Finalist</span>
            <span class="achieve-item"><i class="fas fa-trophy"></i> TechFiesta 25</span>
        </div>

        <div class="stats-row">
            <div class="stat-card">
                <img src="https://github-readme-stats.vercel.app/api?username=PyRaghaw&show_icons=true&theme=radical&hide_border=true&bg_color=1e293b&title_color=3b82f6&icon_color=8b5cf6&text_color=cbd5e1" alt="github stats">
            </div>
        </div>

        <div class="footer">
            <div class="footer-main">Raghaw Shukla</div>
            <div style="color: #94a3b8; margin-top: 1rem;">Built with Offline-first mindset</div>
        </div>
    </div>
</body>
</html>
