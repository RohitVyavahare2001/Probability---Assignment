<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #0d1117;
      font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
    }
    
    .profile-container {
      overflow: hidden;
      position: relative;
    }
    
    .hero-section {
      position: relative;
      height: 250px;
      overflow: hidden;
      background: linear-gradient(125deg, #0d0d4b, #1a1add, #3CE0F7);
      background-size: 300% 300%;
      animation: gradientShift 15s ease infinite;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    
    @keyframes gradientShift {
      0% { background-position: 0% 50% }
      50% { background-position: 100% 50% }
      100% { background-position: 0% 50% }
    }
    
    .hero-overlay {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="none" stroke="rgba(255,255,255,0.1)" stroke-width="0.5"/></svg>');
      animation: moveGrid 20s linear infinite;
      opacity: 0.4;
    }
    
    @keyframes moveGrid {
      0% { background-position: 0 0; }
      100% { background-position: 100px 100px; }
    }
    
    .name-container {
      position: relative;
      z-index: 2;
      text-align: center;
    }
    
    .name-title {
      font-size: 52px;
      color: white;
      font-weight: 800;
      margin: 0;
      text-shadow: 0 0 15px rgba(60, 224, 247, 0.8);
      letter-spacing: 1px;
      position: relative;
      display: inline-block;
    }
    
    .name-title::after {
      content: '';
      position: absolute;
      bottom: -10px;
      left: 0;
      width: 100%;
      height: 3px;
      background: linear-gradient(90deg, transparent, #3CE0F7, transparent);
    }
    
    .particles {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
    }
    
    .particle {
      position: absolute;
      width: 3px;
      height: 3px;
      background-color: rgba(255, 255, 255, 0.7);
      border-radius: 50%;
      animation: particleFloat 8s infinite linear;
    }
    
    @keyframes particleFloat {
      0% {
        transform: translateY(0) translateX(0);
        opacity: 0;
      }
      10% {
        opacity: 1;
      }
      90% {
        opacity: 1;
      }
      100% {
        transform: translateY(-200px) translateX(100px);
        opacity: 0;
      }
    }
    
    .specialty-container {
      text-align: center;
      padding: 20px 0;
      background-color: rgba(13, 17, 23, 0.95);
      position: relative;
      z-index: 2;
      border-bottom: 1px solid rgba(60, 224, 247, 0.3);
    }
    
    .content-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px;
      padding: 20px;
      max-width: 1200px;
      margin: 0 auto;
    }
    
    .card {
      background: linear-gradient(145deg, rgba(18, 18, 29, 0.9), rgba(25, 25, 39, 0.9));
      border-radius: 12px;
      overflow: hidden;
      transition: transform 0.3s, box-shadow 0.3s;
      position: relative;
      border: 1px solid rgba(60, 224, 247, 0.2);
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
    }
    
    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 25px rgba(60, 224, 247, 0.25);
    }
    
    .card-header {
      background: rgba(20, 20, 35, 0.95);
      padding: 15px;
      border-bottom: 1px solid rgba(60, 224, 247, 0.2);
      display: flex;
      align-items: center;
      gap: 10px;
    }
    
    .card-header h3 {
      margin: 0;
      color: #3CE0F7;
      font-size: 20px;
      font-weight: 600;
    }
    
    .card-icon {
      width: 28px;
      height: 28px;
      display: flex;
      align-items: center;
      justify-content: center;
      background: rgba(60, 224, 247, 0.2);
      border-radius: 8px;
      color: #3CE0F7;
    }
    
    .card-content {
      padding: 20px;
    }
    
    .code-block {
      background: rgba(10, 10, 15, 0.8);
      border-radius: 8px;
      padding: 15px;
      margin-bottom: 15px;
      position: relative;
      overflow: hidden;
    }
    
    .code-block::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 4px;
      height: 100%;
      background: linear-gradient(180deg, #3CE0F7, #1a1add);
    }
    
    pre {
      margin: 0;
      color: #e6e6e6;
      font-family: 'Fira Code', Consolas, monospace;
      font-size: 14px;
      line-height: 1.5;
      overflow-x: auto;
    }
    
    .keyword { color: #ff79c6; }
    .string { color: #f1fa8c; }
    .comment { color: #6272a4; }
    .function { color: #50fa7b; }
    .variable { color: #8be9fd; }
    
    .gif-container {
      margin-top: 15px;
      border-radius: 8px;
      overflow: hidden;
      position: relative;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
      border: 1px solid rgba(60, 224, 247, 0.3);
    }
    
    .gif-container img {
      width: 100%;
      height: 180px;
      object-fit: cover;
      display: block;
    }
    
    .gif-overlay {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(45deg, rgba(26, 26, 221, 0.3), rgba(60, 224, 247, 0.3));
      opacity: 0.5;
    }
    
    .tech-stack {
      padding: 30px 20px;
      text-align: center;
      max-width: 1200px;
      margin: 0 auto;
    }
    
    .tech-stack h2 {
      color: #3CE0F7;
      font-size: 24px;
      margin: 0 0 25px 0;
      position: relative;
      display: inline-block;
    }
    
    .tech-stack h2::after {
      content: '';
      position: absolute;
      bottom: -10px;
      left: 25%;
      width: 50%;
      height: 2px;
      background: linear-gradient(90deg, transparent, #3CE0F7, transparent);
    }
    
    .badge-container {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      justify-content: center;
      margin-top: 20px;
    }
    
    .tech-badge {
      padding: 8px 16px;
      border-radius: 30px;
      font-size: 14px;
      font-weight: 500;
      background: rgba(20, 20, 35, 0.9);
      color: white;
      border: 1px solid rgba(60, 224, 247, 0.3);
      display: flex;
      align-items: center;
      gap: 8px;
      transition: all 0.2s;
    }
    
    .tech-badge:hover {
      transform: translateY(-3px);
      box-shadow: 0 5px 10px rgba(60, 224, 247, 0.2);
      background: rgba(30, 30, 50, 0.9);
    }
    
    .badge-icon {
      width: 18px;
      height: 18px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    
    .stats-section {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 15px;
      max-width: 1200px;
      margin: 0 auto 40px auto;
      padding: 0 20px;
    }
    
    .stat-card {
      background: rgba(20, 20, 35, 0.8);
      border-radius: 10px;
      padding: 20px;
      text-align: center;
      border: 1px solid rgba(60, 224, 247, 0.15);
      transition: transform 0.3s;
    }
    
    .stat-card:hover {
      transform: translateY(-5px);
      background: rgba(25, 25, 45, 0.9);
    }
    
    .stat-value {
      font-size: 32px;
      font-weight: 700;
      color: #3CE0F7;
      margin: 0 0 10px 0;
    }
    
    .stat-label {
      font-size: 14px;
      color: #a0a0a0;
      margin: 0;
    }
    
    .footer {
      padding: 40px 0 0 0;
      position: relative;
      overflow: hidden;
    }
    
    .footer-wave {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 120px;
      background: url('data:image/svg+xml;utf8,<svg viewBox="0 0 1200 120" xmlns="http://www.w3.org/2000/svg"><path d="M0 0v46.29c47.79 22.2 103.59 32.17 158 28 70.36-5.37 136.33-33.31 206.8-37.5 73.84-4.36 147.54 16.88 218.2 35.26 69.27 18.17 138.3 24.42 209.4 13.08 36.15-5.76 72.02-17.84 107.88-32.15 36.18-14.48 72.19-33.31 108-33.31V0H0z" fill="%231a1add" opacity="0.3"/><path d="M0 0v15.81c13 21.11 27.64 41.05 47.69 56.24C99.41 111.27 165 111 224.58 91.58c31.15-10.15 60.09-26.07 89.67-39.8 40.92-19 84.73-46 130.83-49.67 36.26-2.85 70.9 9.42 98.6 31.56 31.77 25.39 62.32 62 103.63 73 40.44 10.79 81.35-6.69 119.13-24.28s75.16-39 116.92-43.05c59.73-5.85 113.28 22.88 168.9 38.84 30.2 8.66 59 6.17 87.09-7.5 22.43-10.89 48-26.93 60.65-49.24V0H0z" fill="%233CE0F7" opacity="0.2"/><path d="M0 0v5.63C149.93 59 314.09 71.32 475.83 42.57c43-7.64 84.23-20.12 127.61-26.46 59-8.63 112.48 12.24 165.56 35.4C827.93 77.22 886 95.24 951.2 90c86.53-7 172.46-45.71 248.8-84.81V0H0z" fill="%231a1add" opacity="0.2"/></svg>');
      background-size: cover;
    }
  </style>
</head>
<body>
  <div class="profile-container">
    <!-- Hero Section with Dynamic Background -->
    <div class="hero-section">
      <div class="hero-overlay"></div>
      <div class="particles">
        <!-- Created dynamically with JS -->
      </div>
      <div class="name-container">
        <h1 class="name-title">Rohit Vyavahare</h1>
      </div>
    </div>
    
    <!-- Specialty Typing Animation -->
    <div class="specialty-container">
      <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=24&duration=3000&pause=1000&color=3CE0F7&center=true&vCenter=true&random=false&width=500&lines=AI+Engineer;Machine+Learning+Specialist;Deep+Learning+Expert;NLP+Engineer;LLM+Architect;Intelligent+Agents+Developer" />
    </div>
    
    <!-- Main Content Grid -->
    <div class="content-grid">
      <!-- AI Philosophy Card -->
      <div class="card">
        <div class="card-header">
          <div class="card-icon">🧠</div>
          <h3>AI Philosophy</h3>
        </div>
        <div class="card-content">
          <div class="code-block">
            <pre><span class="variable">model</span>.<span class="function">compile</span>(
  <span class="variable">life</span> = <span class="string">"Coding"</span>,
  <span class="variable">passion</span> = <span class="string">"AI"</span>,
  <span class="variable">mission</span> = <span class="string">"Innovation"</span>
)</pre>
          </div>
          <div class="gif-container">
            <div class="gif-overlay"></div>
            <img src="https://raw.githubusercontent.com/gist/patevs/b007a0e98fb216438d4cbf559fac4166/raw/88f20c9d749d756be63f22b09f3c4ac570bc5101/programming.gif" alt="Programming Animation" />
          </div>
        </div>
      </div>
      
      <!-- Daily Routine Card -->
      <div class="card">
        <div class="card-header">
          <div class="card-icon">⏱️</div>
          <h3>Daily Routine</h3>
        </div>
        <div class="card-content">
          <div class="code-block">
            <pre><span class="keyword">while</span> <span class="variable">alive</span>:
    <span class="function">eat</span>()
    <span class="function">sleep</span>()
    <span class="function">code</span>()
    <span class="function">repeat</span>()  <span class="comment"># Infinite loop of excellence</span></pre>
          </div>
          <div class="gif-container">
            <div class="gif-overlay"></div>
            <img src="https://raw.githubusercontent.com/TheDudeThatCode/TheDudeThatCode/master/Assets/Developer.gif" alt="Developer Animation" />
          </div>
        </div>
      </div>
    </div>
    
    <!-- Project Stats Section -->
    <div class="stats-section">
      <div class="stat-card">
        <div class="stat-value">500+</div>
        <p class="stat-label">AI Models Trained</p>
      </div>
      <div class="stat-card">
        <div class="stat-value">15+</div>
        <p class="stat-label">Research Publications</p>
      </div>
      <div class="stat-card">
        <div class="stat-value">98.7%</div>
        <p class="stat-label">Model Accuracy</p>
      </div>
    </div>
    
    <!-- Tech Stack Section -->
    <div class="tech-stack">
      <h2>Tech Expertise</h2>
      <div class="badge-container">
        <div class="tech-badge">
          <div class="badge-icon">🐍</div>
          Python
        </div>
        <div class="tech-badge">
          <div class="badge-icon">🧠</div>
          TensorFlow
        </div>
        <div class="tech-badge">
          <div class="badge-icon">🔥</div>
          PyTorch
        </div>
        <div class="tech-badge">
          <div class="badge-icon">🤖</div>
          Transformer Models
        </div>
        <div class="tech-badge">
          <div class="badge-icon">🔍</div>
          NLP
        </div>
        <div class="tech-badge">
          <div class="badge-icon">📊</div>
          Data Science
        </div>
        <div class="tech-badge">
          <div class="badge-icon">🔄</div>
          MLOps
        </div>
        <div class="tech-badge">
          <div class="badge-icon">🧪</div>
          Reinforcement Learning
        </div>
        <div class="tech-badge">
          <div class="badge-icon">🔎</div>
          Computer Vision
        </div>
        <div class="tech-badge">
          <div class="badge-icon">🌐</div>
          LangChain
        </div>
      </div>
    </div>
    
    <!-- Footer with Wave Effect -->
    <div class="footer">
      <div class="footer-wave"></div>
    </div>
  </div>

  <script>
    // Create particle effects
    document.addEventListener('DOMContentLoaded', function() {
      const particlesContainer = document.querySelector('.particles');
      const particleCount = 40;
      
      for (let i = 0; i < particleCount; i++) {
        const particle = document.createElement('div');
        particle.classList.add('particle');
        
        // Random positioning
        const size = Math.random() * 3 + 1;
        particle.style.width = `${size}px`;
        particle.style.height = `${size}px`;
        particle.style.left = `${Math.random() * 100}%`;
        particle.style.top = `${Math.random() * 100}%`;
        
        // Random animation delay
        particle.style.animationDelay = `${Math.random() * 8}s`;
        particle.style.opacity = Math.random() * 0.5 + 0.3;
        
        particlesContainer.appendChild(particle);
      }
    });
  </script>
</body>
</html>
