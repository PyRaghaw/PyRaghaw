<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Raghaw Shukla - Interactive Dev & AI Portfolio</title>

<!-- TailwindCSS CDN -->
<script src="https://cdn.tailwindcss.com"></script>

<!-- Three.js CDN -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

<!-- FontAwesome CDN -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />

<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;700&family=Plus+Jakarta+Sans:wght@300;400;600;700;800;900&family=Orbitron:wght@700;900&display=swap" rel="stylesheet" />

<style>
  @layer components {
    /* Custom hover & glow effects */
    .btn-glow {
      box-shadow: 0 0 15px #00d9ff;
      transition: all 0.3s ease;
    }
    .btn-glow:hover {
      box-shadow: 0 0 30px #00d9ff;
      transform: scale(1.05);
    }
  }

  /* Visual vibes - neon/glow customizations */
  body { font-family: 'Plus Jakarta Sans', sans-serif; background: #0d0d0d; overflow-x: hidden; }
  /* Custom scrollbar for more neon-tech vibe */
  ::-webkit-scrollbar { width: 8px; }
  ::-webkit-scrollbar-track { background: #0d0d0d; }
  ::-webkit-scrollbar-thumb { background: linear-gradient(180deg, #6366f1, #8b5cf6); border-radius: 4px; }

  /* Neon accent text */
  .text-neon { background: linear-gradient(135deg, #6366f1, #8b5cf6); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }

  /* Neon glow button */
  .neon-btn {
    @apply px-6 py-3 rounded-xl font-bold transition-transform transition-shadow duration-300;
    background: linear-gradient(135deg, #00d9ff, #7b2ff7);
    box-shadow: 0 0 20px #00d9ff;
  }
  .neon-btn:hover { transform: scale(1.05); box-shadow: 0 0 40px #00d9ff; }

  /* Custom sections & cards */
  .card-glass {
    background: rgba(20, 20, 25, 0.8);
    border: 2px solid rgba(99, 102, 241, 0.3);
    backdrop-filter: blur(12px);
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  }
  .card-glass:hover { border-color: #6366f1; transform: translateY(-8px); box-shadow: 0 20px 60px rgba(99, 102, 241, 0.3); }

  /* Responsive Effects & Animations */
  .fade-in { opacity: 0; transform: translateY(40px); transition: all 0.8s ease; }
  .fade-in.visible { opacity: 1; transform: translateY(0); }

  /* Skill tree nodes */
  .skill-node {
    aspect-ratio: 1/1; border-radius: 50%; background: radial-gradient(circle, #6366f1, #8b5cf6, #00d9ff); border: 2px solid #00d9ff; display:flex; align-items:center; justify-content:center; font-size: 1.5rem; font-weight: bold; cursor:pointer; transition: all 0.3s ease;
  }
  .skill-node:hover { box-shadow: 0 0 20px #00d9ff; transform: scale(1.1); }

  /* Neon glow */
  .glow { box-shadow: 0 0 20px #00d9ff; }

</style>
</head>
<body>

<!-- 3D Canvas for Background -->
<canvas id="backgroundCanvas" class="fixed inset-0 z-0"></canvas>

<!-- Navbar -->
<nav class="fixed top-0 w-full backdrop-blur-lg bg-black/40 border-b border-white/20 z-50 px-6 py-4 flex justify-between items-center">
  <div class="text-2xl font-semibold text-neon font-mono cursor-pointer">Raghaw.dev</div>
  <ul class="hidden md:flex space-x-8 text-gray-300 font-medium font-mono">
    <li><a href="#about" class="hover:text-neon transition">About</a></li>
    <li><a href="#skills" class="hover:text-neon transition">Skills</a></li>
    <li><a href="#projects" class="hover:text-neon transition">Projects</a></li>
    <li><a href="#achievement" class="hover:text-neon transition">Achievements</a></li>
    <li><a href="#contact" class="hover:text-neon transition">Contact</a></li>
  </ul>
  <div class="md:hidden">
    <button id="menuBtn" class="text-neon text-2xl"><i class="fas fa-bars"></i></button>
  </div>
</nav>

<!-- Mobile Menu -->
<div id="mobileMenu" class="hidden md:hidden absolute top-16 inset-x-0 bg-black/80 backdrop-blur-lg border-t border-white/20 px-6 py-4 z-40 space-y-4 rounded-b-lg text-gray-300 font-mono">
  <a href="#about" class="block hover:text-neon transition" onclick="toggleMenu()">About</a>
  <a href="#skills" class="block hover:text-neon transition" onclick="toggleMenu()">Skills</a>
  <a href="#projects" class="block hover:text-neon transition" onclick="toggleMenu()">Projects</a>
  <a href="#achievement" class="block hover:text-neon transition" onclick="toggleMenu()">Achievements</a>
  <a href="#contact" class="block hover:text-neon transition" onclick="toggleMenu()">Contact</a>
</div>

<!-- Hero & Intro -->
<section class="min-h-screen flex flex-col justify-center items-center px-6 pt-24 pb-12 relative z-10" id="hero">
  <div class="text-center max-w-3xl fade-in">
    <h1 class="text-5xl md:text-7xl font-extrabold font-mono mb-4"><span class="text-neon">Innovate</span> & <span class="text-neon">Create</span></h1>
    <p class="text-gray-300 mb-6 text-lg">Building AI-powered, interactive, and gamified developer experiences. Explore my neural universe!</p>
    <div class="space-x-4 flex justify-center mb-10">
      <a href="#projects" class="neon-btn">Explore Projects</a>
      <button onclick="triggerDemo()" class="neon-btn bg-gradient-to-br from-cyan-500 to-purple-600">Demo Mode</button>
    </div>
  </div>
  <!-- Neural Network Animation -->
  <div class="w-full max-w-5xl h-96 relative" id="neuralNetViz"></div>
</section>

<!-- AI Avatar & Chat -->
<div id="aiAvatar" class="fixed bottom-10 right-10 w-20 h-20 rounded-full bg-gradient-to-tr from-cyan-400 to-purple-600 shadow-xl cursor-pointer z-50 glow flex items-center justify-center text-3xl text-white hover:scale-105 transition-transform" title="AI Assistant"></div>

<div id="aiChatBox" class="hidden fixed bottom-36 right-10 w-80 max-w-xs p-4 bg-gray-900 border border-white/20 rounded-xl backdrop-blur-lg z-50 shadow-lg hover:shadow-xl transition-shadow duration-300 overflow-y-auto" style="max-height:300px;">
  <div class="text-neon font-mono mb-2">AI Assistant</div>
  <div id="aiChatMsg" class="text-gray-300 text-sm min-h-[80px]">Click the avatar for insights and fun insights about my projects & skills!</div>
</div>

<!-- Main Sections -->
<!-- About / Mission -->
<section id="about" class="py-20 px-6 fade-in">
  <h2 class="text-3xl md:text-4xl font-bold mb-4 text-center"><span class="text-neon font-mono">// 01</span> About Me</h2>
  <p class="max-w-3xl mx-auto text-gray-300 text-center mb-8">I am Raghaw, a passionate AI engineer & developer building the future. Focused on privacy, education, and writing impactful code. Dive into my journey through the neural universe!</p>
  <div class="max-w-4xl mx-auto flex flex-col md:flex-row gap-6 items-center justify-center">
    <div class="w-48 h-48 bg-gradient-to-tr from-cyan-400 to-purple-600 rounded-full shadow-2xl animate-floating"></div>
    <div class="flex-1 text-center md:text-left">
      <h3 class="text-xl font-semibold mb-4 text-neon">My Creator's Philosophy</h3>
      <ul class="list-disc list-inside space-y-2 text-gray-300 text-sm">
        <li>Build privacy-respecting, scalable systems</li>
        <li>Make AI accessible & fun for all</li>
        <li>Constantly learn and innovate</li>
        <li>Share knowledge & grow together</li>
      </ul>
    </div>
  </div>
</section>

<!-- Skills: Interactive Skill Tree -->
<section id="skills" class="py-20 px-6 bg-gray-900/50 backdrop-blur-lg" style="border-radius:20px;">
<h2 class="text-3xl md:text-4xl font-bold mb-8 text-center"><span class="text-neon font-mono">// 02</span> My Skill Tree</h2>
<div class="grid md:grid-cols-3 gap-6 max-w-6xl mx-auto">
  <div class="bg-gray-800 p-4 rounded-xl shadow-xl hover:scale-105 transform transition-all cursor-pointer" onclick="unlockSkill('Backend')">
    <div class="text-3xl mb-2 text-neon"><i class="fas fa-server"></i></div>
    <div class="font-semibold text-center mb-2">Backend & APIs</div>
    <div class="text-sm text-center text-gray-400">Python, Flask, FastAPI, REST</div>
  </div>
  <div class="bg-gray-800 p-4 rounded-xl shadow-xl hover:scale-105 transform transition-all cursor-pointer" onclick="unlockSkill('AI/ML')">
    <div class="text-3xl mb-2 text-neon"><i class="fas fa-robot"></i></div>
    <div class="font-semibold text-center mb-2">AI & ML</div>
    <div class="text-sm text-center text-gray-400">TensorFlow, OpenCV, LLMs</div>
  </div>
  <div class="bg-gray-800 p-4 rounded-xl shadow-xl hover:scale-105 transform transition-all cursor-pointer" onclick="unlockSkill('Data')">
    <div class="text-3xl mb-2 text-neon"><i class="fas fa-database"></i></div>
    <div class="font-semibold text-center mb-2">Data & Storage</div>
    <div class="text-sm text-center text-gray-400">PostgreSQL, Redis, VDB</div>
  </div>
  <div class="bg-gray-800 p-4 rounded-xl shadow-xl hover:scale-105 transform transition-all cursor-pointer" onclick="unlockSkill('DevOps')">
    <div class="text-3xl mb-2 text-neon"><i class="fas fa-tools"></i></div>
    <div class="font-semibold text-center mb-2">DevOps</div>
    <div class="text-sm text-center text-gray-400">Docker, Git, CI/CD</div>
  </div>
  <div class="bg-gray-800 p-4 rounded-xl shadow-xl hover:scale-105 transform transition-all cursor-pointer" onclick="unlockSkill('Problem Solving')">
    <div class="text-3xl mb-2 text-neon"><i class="fas fa-brain"></i></div>
    <div class="font-semibold text-center mb-2">Problem Solving</div>
    <div class="text-sm text-center text-gray-400">Algorithmic Thinking</div>
  </div>
  <div class="bg-gray-800 p-4 rounded-xl shadow-xl hover:scale-105 transform transition-all cursor-pointer" onclick="unlockSkill('Full Stack')">
    <div class="text-3xl mb-2 text-neon"><i class="fas fa-layer-group"></i></div>
    <div class="font-semibold text-center mb-2">Full Stack</div>
    <div class="text-sm text-center text-gray-400">FastAPI + React</div>
  </div>
</div>
<div class="mt-8 text-center text-gray-400 text-sm">Hover over & click to unlock abilities & badges!</div>
</section>

<!-- Neural Network Live Visual -->
<section id="neural" class="py-20 px-6 bg-gray-900/50 backdrop-blur-lg rounded-3xl" style="margin-top:60px;">
<h2 class="text-3xl md:text-4xl font-bold mb-8 text-center"><span class="text-neon font-mono">// 03</span> Neural Network Flow</h2>
<div class="w-full h-[500px]" id="nnContainer"></div>
</section>

<!-- Projects Showcase -->
<section id="projects" class="py-20 px-6 max-w-7xl mx-auto">
<h2 class="text-3xl md:text-4xl font-bold mb-8 text-center"><span class="text-neon font-mono">// 04</span> My Projects</h2>
<div class="grid md:grid-cols-3 gap-8">

<!-- Project Card -->
<div class="bg-gray-800 bg-opacity-60 rounded-xl p-6 shadow-xl hover:scale-105 transform transition-all border-4 border-transparent hover:border-neon">
<h3 class="text-xl font-bold mb-4">ScholarConnect</h3>
<p class="text-gray-300 mb-4">Multilingual AI platform helping Indian students find scholarships with OCR and NLP.</p>
<ul class="text-gray-400 mb-4 list-disc list-inside">
<li>OCR Document Parsing</li>
<li>Language Support</li>
<li>Intelligent Matching</li>
</ul>
<a class="text-neon font-semibold hover:underline" href="https://github.com/PyRaghaw/Scholar-Connect" target="_blank">Repo & Details</a>
</div>

<!-- Repeat for other projects -->
<div class="bg-gray-800 bg-opacity-60 rounded-xl p-6 shadow-xl hover:scale-105 transform transition-all border-4 border-transparent hover:border-neon">
<h3 class="text-xl font-bold mb-4">AI Timetable</h3>
<p class="text-gray-300 mb-4">ML-powered adaptive scheduling for smarter time management.</p>
<ul class="text-gray-400 mb-4 list-disc list-inside">
<li>Personalized Schedules</li>
<li>Pattern Analysis</li>
<li>Analytics</li>
</ul>
<a class="text-neon font-semibold hover:underline" href="https://github.com/PyRaghaw/AI-Timetable" target="_blank">Repo & Details</a>
</div>

<div class="bg-gray-800 bg-opacity-60 rounded-xl p-6 shadow-xl hover:scale-105 transform transition-all border-4 border-transparent hover:border-neon">
<h3 class="text-xl font-bold mb-4">MailMind Pro</h3>
<p class="text-gray-300 mb-4">Privacy-first email assistant with auto-summaries and in-memory processing.</p>
<ul class="text-gray-400 mb-4 list-disc list-inside">
<li>Auto Summarization</li>
<li>Zero Storage</li>
<li>Secure API</li>
</ul>
<a class="text-neon font-semibold hover:underline" href="https://github.com/PyRaghaw/MailMind" target="_blank">Repo & Details</a>
</div>

</div>
</section>

<!-- Achievements & Badges -->
<section id="achievement" class="py-20 bg-gray-900/50 backdrop-blur-lg rounded-3xl my-16 px-6">
<h2 class="text-3xl md:text-4xl font-semibold mb-8 text-center"><i class="fas fa-trophy text-neon"></i> Achievements</h2>
<div id="badgesContainer" class="flex flex-wrap justify-center gap-4"></div>
</section>

<!-- Contact & Connect -->
<section id="contact" class="py-20 px-6 max-w-7xl mx-auto text-center">
<h2 class="text-3xl md:text-4xl font-bold mb-8"><i class="fas fa-user-shield text-neon"></i> Let's Collaborate</h2>
<div class="grid md:grid-cols-4 gap-6 max-w-4xl mx-auto mb-8">
  <a href="https://github.com/PyRaghaw" target="_blank" class="p-6 bg-gray-800 rounded-xl hover:scale-105 transform transition-all flex flex-col items-center border-2 border-transparent hover:border-neon">
    <i class="fab fa-github text-4xl mb-3"></i>
    <div class="text-gray-400 mb-1">@PyRaghaw</div>
  </a>
  <a href="https://linkedin.com/in/raghaw-shukla-a49727326/" target="_blank" class="p-6 bg-gray-800 rounded-xl hover:scale-105 transform transition-all flex flex-col items-center border-2 border-transparent hover:border-neon">
    <i class="fab fa-linkedin text-4xl mb-3"></i>
    <div class="text-gray-400 mb-1">Connect</div>
  </a>
  <a href="mailto:sraghaw911@gmail.com" class="p-6 bg-gray-800 rounded-xl hover:scale-105 transform transition-all flex flex-col items-center border-2 border-transparent hover:border-neon">
    <i class="fas fa-envelope text-4xl mb-3"></i>
    <div class="text-gray-400 mb-1">Email</div>
  </a>
  <div class="p-6 bg-gray-800 rounded-xl flex flex-col items-center border-2 border-transparent cursor-not-allowed">
    <i class="fas fa-map-marker-alt text-4xl mb-3"></i>
    <div class="text-gray-400 mb-1">Kolkata, India</div>
  </div>
</div>
<!-- Footer -->
<div class="mt-12 text-gray-500 text-sm font-mono">© 2025 Raghaw Shukla - All rights reserved. Built with ❤️ & AI.</div>
</section>

<!-- Scripts for interactions & visualization -->
<script>
// Mobile menu toggle
const menuBtn = document.getElementById('menuBtn');
const mobileMenu = document.getElementById('mobileMenu');
menuBtn.onclick = () => {
  mobileMenu.classList.toggle('hidden');
};

// Animate on scroll
const els = document.querySelectorAll('.fade-in');
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
    }
  });
}, { threshold: 0.1 });
els.forEach(el => observer.observe(el));

// Toggle AI chat
function toggleAI() {
  document.getElementById('aiChatBox').classList.toggle('hidden');
  if (!document.getElementById('aiChatBox').classList.contains('hidden')) {
    document.getElementById('aiChatMsg').textContent = "Hi! Ask me anything about my projects, skills, or just say hello!";
  }
}
document.getElementById('aiAvatar').onclick = toggleAI;

// Show achievement badge
function addBadge(text) {
  const container = document.getElementById('badgesContainer');
  const badge = document.createElement('div');
  badge.className = 'bg-gradient-to-br from-cyan-400 to-purple-600 px-4 py-2 rounded-full shadow-lg text-white font-semibold flex items-center space-x-2';
  badge.innerHTML = `<i class="fas fa-star"></i> <span>${text}</span>`;
  container.appendChild(badge);
}

// Trigger demo (simulate interaction)
function triggerDemo() {
  addBadge('Demo Initiated');
  alert('Demo mode activated! Explore my skills and projects.');
}

// Neural network live visualization
function initNeuralViz() {
  const container = document.getElementById('neuralNetViz');
  const scene = new THREE.Scene();
  const camera = new THREE.PerspectiveCamera(75, container.offsetWidth / container.offsetHeight, 0.1, 200);
  const renderer = new THREE.WebGLRenderer({ antialias:true, alpha:true });
  renderer.setSize(container.offsetWidth, container.offsetHeight);
  container.appendChild(renderer.domElement);
  camera.position.z=30;

  const nodes = [];
  const nodeCount=20;
  for (let i=0;i<nodeCount;i++) {
    const nodeGeom = new THREE.SphereGeometry(0.7,16,16);
    const nodeMat = new THREE.MeshStandardMaterial({ color:0x00e5ff, roughness:0.4 });
    const sphere = new THREE.Mesh(nodeGeom, nodeMat);
    sphere.position.set((Math.random()-0.5)*40, (Math.random()-0.5)*40, (Math.random()-0.5)*40);
    scene.add(sphere);
    nodes.push(sphere);
  }

  const lines = [];
  for (let i=0;i<nodeCount*2;i++) {
    const geo = new THREE.BufferGeometry().setFromPoints([new THREE.Vector3(), new THREE.Vector3()]);
    const mat = new THREE.LineBasicMaterial({ color:'#00e5ff', opacity:0.2, transparent:true });
    const line = new THREE.Line(geo, mat);
    scene.add(line);
    lines.push({ line, from: nodes[Math.floor(Math.random()*nodes.length)], to: nodes[Math.floor(Math.random()*nodes.length)] });
  }

  function animate() {
    requestAnimationFrame(animate);
    nodes.forEach((n,i) => {
      n.rotation.x+=0.005;
      n.rotation.y+=0.005;
    });
    lines.forEach(l => {
      l.from.position.x += (Math.random()-0.5)*0.02;
      l.to.position.x += (Math.random()-0.5)*0.02;
      l.line.geometry.setFromPoints([l.from.position, l.to.position]);
    });
    renderer.render(scene, camera);
  }
  animate();

  window.addEventListener('resize', () => {
    camera.aspect = container.offsetWidth / container.offsetHeight;
    camera.updateProjectionMatrix();
    renderer.setSize(container.offsetWidth, container.offsetHeight);
  });
}
initNeuralViz();
</script>
</body>
</html>
