<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Animated CSS Bicycle with Tech Stack</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    html, body {
      width: 100%;
      height: 100%;
      font-family: 'Courier New', monospace;
    }
    body {
      background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%);
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
      position: relative;
    }
    
    /* Animated Background Tech Text */
    .tech-background {
      position: absolute;
      width: 100%;
      height: 100%;
      overflow: hidden;
      opacity: 0.1;
    }
    
    .tech-text {
      position: absolute;
      color: #fff;
      font-size: 18px;
      font-weight: bold;
      white-space: nowrap;
      animation: scrollTech 15s linear infinite;
    }
    
    .tech-text:nth-child(1) { top: 10%; animation-delay: 0s; }
    .tech-text:nth-child(2) { top: 25%; animation-delay: -3s; }
    .tech-text:nth-child(3) { top: 40%; animation-delay: -6s; }
    .tech-text:nth-child(4) { top: 55%; animation-delay: -9s; }
    .tech-text:nth-child(5) { top: 70%; animation-delay: -12s; }
    .tech-text:nth-child(6) { top: 85%; animation-delay: -15s; }
    
    @keyframes scrollTech {
      0% { transform: translateX(100vw); }
      100% { transform: translateX(-100%); }
    }
    
    /* Main Title */
    .title {
      position: absolute;
      top: 80px;
      width: 100%;
      text-align: center;
      color: #fff;
      font-size: 36px;
      font-weight: bold;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
      z-index: 10;
    }
    
    .subtitle {
      position: absolute;
      top: 130px;
      width: 100%;
      text-align: center;
      color: #ffd700;
      font-size: 18px;
      font-weight: bold;
      text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
      z-index: 10;
    }

    .bicycle-container {
      position: relative;
      width: 350px;
      height: 300px;
      overflow: visible;
      animation: move 12s linear infinite;
      z-index: 5;
    }
    
    /* Wheels */
    .wheel {
      position: absolute;
      bottom: 0;
      width: 120px;
      height: 120px;
      border: 8px solid #ff1744;
      border-radius: 50%;
      box-shadow: 0 10px 15px -12px rgba(0,0,0,0.8);
      animation: spin 2s linear infinite;
      background: rgba(255, 23, 68, 0.1);
    }
    
    .wheel::after {
      content: "";
      position: absolute;
      top: 50%;
      left: 50%;
      width: 20px;
      height: 20px;
      background: #ff1744;
      border-radius: 50%;
      transform: translate(-50%, -50%);
      box-shadow: 0 0 10px #ff1744;
    }
    
    /* Spokes */
    .wheel::before {
      content: "";
      position: absolute;
      top: 50%;
      left: 50%;
      width: 100px;
      height: 2px;
      background: #ff1744;
      transform: translate(-50%, -50%);
      box-shadow: 
        0 0 0 0 #ff1744,
        0 0 0 0 #ff1744 45deg,
        0 0 0 0 #ff1744 90deg,
        0 0 0 0 #ff1744 135deg;
    }
    
    .wheel.left {
      left: 0;
    }
    .wheel.right {
      right: 0;
    }
    
    /* Frame */
    .frame {
      position: absolute;
      top: 40px;
      left: 60px;
      width: 230px;
      height: 160px;
    }
    .frame svg {
      width: 100%;
      height: 100%;
    }
    svg line {
      stroke: #ff1744;
      stroke-width: 6;
      stroke-linecap: round;
      filter: drop-shadow(0 0 5px #ff1744);
    }
    svg rect {
      fill: #ff1744;
      stroke: none;
      filter: drop-shadow(0 0 5px #ff1744);
    }
    
    /* Tech Stack Labels */
    .tech-label {
      position: absolute;
      color: #ffd700;
      font-size: 14px;
      font-weight: bold;
      text-shadow: 1px 1px 2px rgba(0,0,0,0.8);
      animation: pulse 2s ease-in-out infinite;
    }
    
    .frontend-label {
      top: 20px;
      left: 50px;
    }
    
    .middleware-label {
      top: 80px;
      right: 20px;
    }
    
    .backend-label {
      bottom: 40px;
      left: 30px;
    }
    
    @keyframes pulse {
      0%, 100% { opacity: 0.7; transform: scale(1); }
      50% { opacity: 1; transform: scale(1.1); }
    }
    
    /* Animations */
    @keyframes spin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }
    @keyframes move {
      0% { transform: translateX(-400px); }
      100% { transform: translateX(calc(100vw + 400px)); }
    }
    
    /* Particles */
    .particle {
      position: absolute;
      width: 4px;
      height: 4px;
      background: #ffd700;
      border-radius: 50%;
      animation: particle 8s linear infinite;
    }
    
    @keyframes particle {
      0% { 
        transform: translateX(0) translateY(0);
        opacity: 1;
      }
      100% { 
        transform: translateX(-200px) translateY(-100px);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <!-- Background Tech Text -->
  <div class="tech-background">
    <div class="tech-text">Frontend: React.js • Vue.js • Angular • HTML5 • CSS3 • JavaScript • TypeScript • Bootstrap • Tailwind</div>
    <div class="tech-text">Middleware: Node.js • Express.js • REST APIs • GraphQL • Socket.io • JWT • OAuth • Redis</div>
    <div class="tech-text">Backend: Python • Django • Flask • FastAPI • PostgreSQL • MongoDB • MySQL • SQLite</div>
    <div class="tech-text">DevOps: Docker • Kubernetes • AWS • Azure • Git • CI/CD • Jenkins • Nginx</div>
    <div class="tech-text">ML/AI: TensorFlow • PyTorch • Scikit-learn • Pandas • NumPy • OpenCV • NLP • Deep Learning</div>
    <div class="tech-text">Mobile: React Native • Flutter • Ionic • Progressive Web Apps • Responsive Design</div>
  </div>
  
  <!-- Main Title -->
  <div class="title">HTML + CSS Bike</div>
  <div class="subtitle">Full Stack Development Journey</div>
  
  <!-- Bicycle Animation -->
  <div class="bicycle-container">
    <!-- Tech Stack Labels -->
    <div class="tech-label frontend-label">Frontend</div>
    <div class="tech-label middleware-label">Middleware</div>
    <div class="tech-label backend-label">Backend</div>
    
    <!-- Wheels -->
    <div class="wheel left"></div>
    <div class="wheel right"></div>
    
    <!-- Frame -->
    <div class="frame">
      <svg viewBox="0 0 300 200">
        <!-- Main frame triangle -->
        <line x1="60" y1="140" x2="150" y2="60" />
        <line x1="150" y1="60" x2="240" y2="140" />
        <line x1="60" y1="140" x2="240" y2="140" />
        
        <!-- Seat post -->
        <line x1="150" y1="60" x2="150" y2="100" />
        
        <!-- Handle post -->
        <line x1="240" y1="140" x2="240" y2="70" />
        <line x1="240" y1="70" x2="270" y2="50" />
        
        <!-- Seat -->
        <rect x="135" y="45" width="30" height="8" rx="4" />
        
        <!-- Handlebars -->
        <rect x="260" y="45" width="25" height="6" rx="3" />
        
        <!-- Chain area -->
        <circle cx="150" cy="140" r="15" fill="none" stroke="#ff1744" stroke-width="3"/>
        
        <!-- Pedals -->
        <rect x="145" y="150" width="10" height="4" rx="2" />
      </svg>
    </div>
    
    <!-- Particle effects -->
    <div class="particle" style="bottom: 60px; left: 60px; animation-delay: 0s;"></div>
    <div class="particle" style="bottom: 60px; right: 60px; animation-delay: 0.5s;"></div>
    <div class="particle" style="bottom: 60px; left: 160px; animation-delay: 1s;"></div>
  </div>
  
  <script>
    // Add more dynamic particles
    function createParticle() {
      const particle = document.createElement('div');
      particle.className = 'particle';
      particle.style.left = Math.random() * window.innerWidth + 'px';
      particle.style.top = Math.random() * window.innerHeight + 'px';
      particle.style.animationDuration = (Math.random() * 5 + 3) + 's';
      document.body.appendChild(particle);
      
      setTimeout(() => {
        particle.remove();
      }, 8000);
    }
    
    setInterval(createParticle, 1000);
  </script>
</body>
</html>



---

## 🚀 About Me

🎓 **B.Tech in Computer Science** from **Siddhartha Institute of Engineering and Technology** (CGPA: 8.1/10.0)

💼 **Python Developer & ML Enthusiast**

🔥 **Core Interests:**
- 🤖 Machine Learning
- 🌐 Web Development
- 🧩 Problem Solving

🚀 **Current Focus:** Building innovative solutions with Python & Machine Learning

🏏 **Fun Fact:** Cricket player who codes between matches - because strategy works both on field and in code!

---

## 💻 Tech Stack & Tools

<div align="center">

### 🔥 Languages & Frameworks
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

### 🗄️ Databases & Cloud
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

### 🛠️ Development Tools
![VS Code](https://img.shields.io/badge/VS_Code-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

### 🤖 ML/AI Tools
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Scikit Learn](https://img.shields.io/badge/Scikit_Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)

</div>



## 🏆 Achievements & Certifications

<div align="center">

| 🏅 Certification | 🏢 Organization | 📅 Status |
|:----------------:|:---------------:|:---------:|
| 🐍 **Python Programming** | Aavanto | ✅ Certified |
| 📊 **SQL Database** | IBM | ✅ Certified |
| 🤖 **Machine Learning** | Slash Mark | ✅ Certified |

</div>



## 🤝 Let's Connect & Collaborate!

<div align="center">
  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/praveen-kumar-87277021a)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:praveenyadavp999@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/praveen-kumar58)

</div>

---

<div align="center">
  
### 💭 Random Dev Quote
![](https://quotes-github-readme.vercel.app/api?type=horizontal&theme=tokyonight)

### 🏏 When I'm not coding...
```
if not coding:
    play_cricket() 
    # Because every developer needs a sport that involves strategy! 🏏
```

---

<img src="https://raw.githubusercontent.com/platane/platane/output/github-contribution-grid-snake-dark.svg" alt="Snake animation" />

**⭐ From [Mekala Praveen Kumar](https://github.com/praveen-kumar58) - Let's build something amazing together!**

</div>
