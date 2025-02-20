<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rohit Vyavahare - AI Engineer</title>
  <style>
    :root {
      --primary-color: #3CE0F7;
      --secondary-color: #0A2540;
      --accent-color: #8B5CF6;
      --background: #0f172a;
      --card-bg: rgba(15, 23, 42, 0.8);
      --text-color: #f1f5f9;
    }
    
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Fira Code', monospace;
    }
    
    body {
      background-color: var(--background);
      background-image: 
        radial-gradient(circle at 10% 20%, rgba(60, 224, 247, 0.1) 0%, transparent 20%),
        radial-gradient(circle at 90% 80%, rgba(139, 92, 246, 0.1) 0%, transparent 20%);
      color: var(--text-color);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 2rem;
      overflow-x: hidden;
    }
    
    .header {
      position: relative;
      width: 100%;
      max-width: 1000px;
      height: 150px;
      margin-bottom: 2rem;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
      border-radius: 12px;
      background: linear-gradient(135deg, #4F46E5, #06B6D4, #8B5CF6);
      animation: gradientShift 15s ease infinite;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
    }
    
    @keyframes gradientShift {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    
    .header h1 {
      font-size: 3.5rem;
      font-weight: 800;
      color: white;
      text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
      z-index: 2;
    }
    
    .typing-container {
      margin-top: 1rem;
      margin-bottom: 2rem;
      height: 50px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    
    .typing-text {
      font-size: 1.5rem;
      font-weight: 600;
      color: var(--primary-color);
      position: relative;
      overflow: hidden;
      white-space: nowrap;
      animation: typing 4s steps(30) infinite;
      border-right: 3px solid var(--primary-color);
      padding-right: 5px;
    }
    
    @keyframes typing {
      0%, 100% { width: 0 }
      50% { width: 435px }
    }
    
    .content-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 2rem;
      width: 100%;
      max-width: 1000px;
    }
    
    .card {
      background: var(--card-bg);
      border-radius: 16px;
      padding: 1.5rem;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
      border: 1px solid rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(10px);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    
    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
    }
    
    .code-block {
      background: rgba(0, 0, 0, 0.3);
      border-radius: 8px;
      padding: 1.5rem;
      width: 100%;
      margin-bottom: 1rem;
      color: var(--primary-color);
      font-family: 'Fira Code', monospace;
      line-height: 1.5;
      text-align: left;
      position: relative;
      overflow: hidden;
    }
    
    .code-block::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(60, 224, 247, 0.1), transparent);
      transform: translateX(-100%);
      animation: shimmer 3s infinite;
    }
    
    @keyframes shimmer {
      100% { transform: translateX(100%); }
    }
    
    .gif-container {
      width: 100%;
      height: 200px;
      border-radius: 8px;
      overflow: hidden;
      position: relative;
    }
    
    .gif-container img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: 8px;
      transition: transform 0.5s ease;
    }
    
    .card:hover .gif-container img {
      transform: scale(1.05);
    }
    
    /* Particle animation */
    .particles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: -1;
    }
    
    @media (max-width: 768px) {
      .content-grid {
        grid-template-columns: 1fr;
      }
      
      .header h1 {
        font-size: 2.5rem;
      }
      
      .typing-text {
        font-size: 1.2rem;
      }
    }
  </style>
</head>
<body>
  <!-- Particle background -->
  <div class="particles" id="particles-js"></div>
  
  <!-- Header with wave effect -->
  <div class="header">
    <h1>Rohit Vyavahare</h1>
  </div>
  
  <!-- Typing effect -->
  <div class="typing-container">
    <div class="typing-text" id="typing-text">AI Engineer</div>
  </div>
  
  <!-- Content grid -->
  <div class="content-grid">
    <div class="card">
      <pre class="code-block">model.compile(
  life = "Coding",
  passion = "AI",
  mission = "Innovation"
)</pre>
      <div class="gif-container">
        <img src="https://raw.githubusercontent.com/gist/patevs/b007a0e98fb216438d4cbf559fac4166/raw/88f20c9d749d756be63f22b09f3c4ac570bc5101/programming.gif" alt="Programming GIF"/>
      </div>
    </div>
    
    <div class="card">
      <pre class="code-block">while alive:
    eat()
    sleep()
    code()
    repeat()</pre>
      <div class="gif-container">
        <img src="https://raw.githubusercontent.com/TheDudeThatCode/TheDudeThatCode/master/Assets/Developer.gif" alt="Developer GIF"/>
      </div>
    </div>
  </div>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/particlesjs/2.2.3/particles.min.js"></script>
  <script>
    // Typing effect for multiple phrases
    const phrases = [
      "AI Engineer",
      "Machine Learning Specialist",
      "Deep Learning",
      "NLP Engineer",
      "LLM's",
      "Agents"
    ];
    
    let currentPhraseIndex = 0;
    const typingTextElement = document.getElementById('typing-text');
    
    function updateTypingText() {
      typingTextElement.textContent = phrases[currentPhraseIndex];
      currentPhraseIndex = (currentPhraseIndex + 1) % phrases.length;
    }
    
    // Initial text
    updateTypingText();
    // Update text every 4 seconds
    setInterval(updateTypingText, 4000);
    
    // Initialize particles
    window.addEventListener('DOMContentLoaded', () => {
      Particles.init({
        selector: '#particles-js',
        maxParticles: 100,
        color: ['#3CE0F7', '#8B5CF6', '#ffffff'],
        connectParticles: true,
        responsive: [
          {
            breakpoint: 768,
            options: {
              maxParticles: 50
            }
          }
        ]
      });
    });
  </script>
</body>
</html>
