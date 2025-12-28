<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Raj Vekariya - Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a0a2e 50%, #0a0a0a 100%);
            color: #e0e0e0;
            overflow-x: hidden;
            position: relative;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            opacity: 0.3;
        }

        .particle {
            position: absolute;
            background: #6A5ACD;
            border-radius: 50%;
            animation: float 20s infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) translateX(0); }
            25% { transform: translateY(-100px) translateX(50px); }
            50% { transform: translateY(-50px) translateX(100px); }
            75% { transform: translateY(-150px) translateX(-50px); }
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        /* Header Section */
        .header {
            text-align: center;
            padding: 60px 20px;
            position: relative;
            overflow: hidden;
        }

        .header h1 {
            font-size: 3.5em;
            background: linear-gradient(45deg, #6A5ACD, #9A8FEE, #6A5ACD);
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradient 3s ease infinite;
            margin-bottom: 20px;
            text-shadow: 0 0 30px rgba(106, 90, 205, 0.5);
        }

        @keyframes gradient {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .typing-text {
            font-size: 1.3em;
            color: #6A5ACD;
            min-height: 50px;
            font-weight: 500;
            margin: 20px 0;
        }

        .cursor {
            animation: blink 0.7s infinite;
        }

        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }

        /* Profile Summary Box */
        .summary-box {
            background: rgba(106, 90, 205, 0.1);
            border: 2px solid #6A5ACD;
            border-radius: 15px;
            padding: 30px;
            margin: 40px 0;
            position: relative;
            overflow: hidden;
            animation: pulse-border 2s ease-in-out infinite;
        }

        @keyframes pulse-border {
            0%, 100% { box-shadow: 0 0 20px rgba(106, 90, 205, 0.5); }
            50% { box-shadow: 0 0 40px rgba(106, 90, 205, 0.8); }
        }

        .summary-box::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(106, 90, 205, 0.1), transparent);
            animation: rotate 4s linear infinite;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .summary-content {
            position: relative;
            z-index: 1;
        }

        /* Coding GIF */
        .coding-gif {
            float: right;
            margin: 0 0 20px 20px;
            border-radius: 15px;
            box-shadow: 0 10px 40px rgba(106, 90, 205, 0.3);
            animation: float-image 3s ease-in-out infinite;
        }

        @keyframes float-image {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        /* Section Title */
        .section-title {
            font-size: 2.5em;
            color: #6A5ACD;
            text-align: center;
            margin: 60px 0 40px;
            position: relative;
            display: inline-block;
            width: 100%;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, transparent, #6A5ACD, transparent);
            animation: expand 2s ease-in-out infinite;
        }

        @keyframes expand {
            0%, 100% { width: 100px; }
            50% { width: 200px; }
        }

        /* Cards */
        .cards-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        .card {
            background: rgba(26, 10, 46, 0.6);
            border: 1px solid #6A5ACD;
            border-radius: 15px;
            padding: 30px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(106, 90, 205, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .card:hover::before {
            left: 100%;
        }

        .card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 15px 50px rgba(106, 90, 205, 0.4);
            border-color: #9A8FEE;
        }

        .card h3 {
            color: #9A8FEE;
            margin-bottom: 20px;
            font-size: 1.5em;
        }

        .card ul {
            list-style: none;
        }

        .card li {
            padding: 10px 0;
            border-bottom: 1px solid rgba(106, 90, 205, 0.2);
            position: relative;
            padding-left: 25px;
        }

        .card li::before {
            content: '▸';
            position: absolute;
            left: 0;
            color: #6A5ACD;
            font-size: 1.2em;
            animation: pulse 1.5s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }

        /* Tech Stack */
        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            margin: 40px 0;
        }

        .tech-icon {
            width: 70px;
            height: 70px;
            background: rgba(106, 90, 205, 0.2);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2em;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            animation: icon-float 3s ease-in-out infinite;
        }

        .tech-icon:nth-child(even) {
            animation-delay: 0.5s;
        }

        @keyframes icon-float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-10px) rotate(5deg); }
        }

        .tech-icon:hover {
            transform: scale(1.2) rotate(10deg);
            background: rgba(106, 90, 205, 0.4);
            border-color: #6A5ACD;
            box-shadow: 0 10px 30px rgba(106, 90, 205, 0.5);
        }

        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin: 60px 0;
        }

        .social-btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 15px 30px;
            background: linear-gradient(45deg, #6A5ACD, #9A8FEE);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .social-btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            transform: translate(-50%, -50%);
            transition: width 0.5s ease, height 0.5s ease;
        }

        .social-btn:hover::before {
            width: 300px;
            height: 300px;
        }

        .social-btn:hover {
            transform: scale(1.1);
            box-shadow: 0 10px 40px rgba(106, 90, 205, 0.6);
        }

        .social-btn span {
            position: relative;
            z-index: 1;
        }

        /* Stats Grid */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }

        .stat-box {
            background: rgba(26, 10, 46, 0.6);
            border: 2px solid #6A5ACD;
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat-box:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 40px rgba(106, 90, 205, 0.5);
        }

        .stat-number {
            font-size: 3em;
            color: #6A5ACD;
            font-weight: bold;
            display: block;
            margin-bottom: 10px;
        }

        .stat-label {
            color: #9A8FEE;
            font-size: 1.1em;
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 60px 20px;
            margin-top: 80px;
        }

        .footer-animation {
            max-width: 500px;
            margin: 0 auto 30px;
            animation: glow 2s ease-in-out infinite;
        }

        @keyframes glow {
            0%, 100% { filter: drop-shadow(0 0 10px rgba(106, 90, 205, 0.5)); }
            50% { filter: drop-shadow(0 0 30px rgba(106, 90, 205, 0.8)); }
        }

        .footer h3 {
            font-size: 2em;
            color: #6A5ACD;
            margin-top: 20px;
        }

        /* Profile Views Badge */
        .profile-badge {
            display: inline-block;
            margin: 20px 0;
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header h1 { font-size: 2em; }
            .typing-text { font-size: 1em; }
            .coding-gif { float: none; margin: 20px auto; display: block; }
            .section-title { font-size: 1.8em; }
        }

        /* Loading Animation */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .fade-in {
            animation: fadeIn 1s ease forwards;
        }
    </style>
</head>
<body>
    <!-- Animated Background -->
    <div class="bg-animation" id="particles"></div>

    <div class="container">
        <!-- Header Section -->
        <div class="header fade-in">
            <h1>Hi 👋, I'm Raj Vekariya</h1>
            <div class="typing-text" id="typing"></div>
            <div class="profile-badge">
                <img src="https://komarev.com/ghpvc/?username=rajpatel-7&label=Profile%20Views&color=6A5ACD&style=flat" alt="Profile Views">
            </div>
        </div>

        <!-- Summary Box -->
        <div class="summary-box fade-in">
            <img src="https://cdn.dribbble.com/users/1162077/screenshots/3848914/programmer.gif" 
                 alt="Coding" width="420" class="coding-gif">
            <div class="summary-content">
                <p style="font-size: 1.2em; line-height: 1.8;">
                    💼 I design intelligent systems, build scalable APIs, and develop data-driven applications.<br><br>
                    🎯 Actively seeking opportunities in <strong>Machine Learning, .NET Backend & Software Engineering</strong>
                </p>
            </div>
        </div>

        <!-- Professional Summary -->
        <h2 class="section-title fade-in">🎯 Professional Summary</h2>
        <div class="cards-container fade-in">
            <div class="card">
                <h3>💻 Core Expertise</h3>
                <ul>
                    <li>Software Developer with strong foundations in <strong>Data Structures & Algorithms</strong></li>
                    <li>Hands-on experience with <strong>Machine Learning & Deep Learning workflows</strong></li>
                    <li>Skilled in <strong>Model Training, Feature Engineering & Evaluation</strong></li>
                </ul>
            </div>
            <div class="card">
                <h3>🚀 Technical Focus</h3>
                <ul>
                    <li>Backend developer using <strong>Advanced .NET, REST APIs & Databases</strong></li>
                    <li>Passionate about <strong>Data, Automation & Scalable Systems</strong></li>
                    <li>Growth mindset — learning industry-grade tools & architectures</li>
                </ul>
            </div>
        </div>

        <!-- ML & Deep Learning -->
        <h2 class="section-title fade-in">🤖 ML & Deep Learning Focus</h2>
        <div class="cards-container fade-in">
            <div class="card">
                <h3>🧠 Machine Learning</h3>
                <ul>
                    <li>Supervised & Unsupervised Learning</li>
                    <li>Feature Engineering & Data Preprocessing</li>
                    <li>Model Evaluation (Accuracy, Precision, Recall, F1)</li>
                </ul>
            </div>
            <div class="card">
                <h3>📊 Algorithms & Tools</h3>
                <ul>
                    <li>Logistic Regression, Tree-Based Models</li>
                    <li>Python for ML Pipelines</li>
                    <li>Data Visualization & Analysis</li>
                </ul>
            </div>
        </div>

        <!-- .NET & Backend -->
        <h2 class="section-title fade-in">💻 Advanced .NET & Backend Skills</h2>
        <div class="cards-container fade-in">
            <div class="card">
                <h3>⚙️ Backend Development</h3>
                <ul>
                    <li>ASP.NET Core Web API</li>
                    <li>Authentication & Validation</li>
                    <li>Clean Architecture & Layered Design</li>
                </ul>
            </div>
            <div class="card">
                <h3>🗄️ Database & API</h3>
                <ul>
                    <li>SQL Server / MySQL / MongoDB</li>
                    <li>RESTful API Development</li>
                    <li>Entity Framework Core</li>
                </ul>
            </div>
            <div class="card">
                <h3>🏗️ Architecture</h3>
                <ul>
                    <li>Scalable Backend Design</li>
                    <li>Microservices Patterns</li>
                    <li>Performance Optimization</li>
                </ul>
            </div>
        </div>

        <!-- Tech Stack -->
        <h2 class="section-title fade-in">🛠️ Tech Stack</h2>
        <div class="tech-stack fade-in">
            <div class="tech-icon" title="C">C</div>
            <div class="tech-icon" title="C#">C#</div>
            <div class="tech-icon" title=".NET">.NET</div>
            <div class="tech-icon" title="Python">🐍</div>
            <div class="tech-icon" title="Java">☕</div>
            <div class="tech-icon" title="JavaScript">JS</div>
            <div class="tech-icon" title="HTML5">HTML</div>
            <div class="tech-icon" title="CSS3">CSS</div>
            <div class="tech-icon" title="React">⚛️</div>
            <div class="tech-icon" title="Node.js">Node</div>
            <div class="tech-icon" title="MySQL">SQL</div>
            <div class="tech-icon" title="MongoDB">🍃</div>
            <div class="tech-icon" title="Postman">📮</div>
        </div>

        <!-- Stats -->
        <h2 class="section-title fade-in">📊 Quick Stats</h2>
        <div class="stats-grid fade-in">
            <div class="stat-box">
                <span class="stat-number" data-target="5">0</span>
                <span class="stat-label">Years Experience</span>
            </div>
            <div class="stat-box">
                <span class="stat-number" data-target="50">0</span>
                <span class="stat-label">Projects Completed</span>
            </div>
            <div class="stat-box">
                <span class="stat-number" data-target="15">0</span>
                <span class="stat-label">Technologies</span>
            </div>
            <div class="stat-box">
                <span class="stat-number" data-target="100">0</span>
                <span class="stat-label">Commits This Month</span>
            </div>
        </div>

        <!-- Social Links -->
        <h2 class="section-title fade-in">🌐 Connect With Me</h2>
        <div class="social-links fade-in">
            <a href="https://www.linkedin.com/in/raj-vekariya-49147a357/" target="_blank" class="social-btn">
                <span>💼 LinkedIn</span>
            </a>
            <a href="https://www.instagram.com/rajvekariya__7" target="_blank" class="social-btn">
                <span>📸 Instagram</span>
            </a>
        </div>

        <!-- Footer -->
        <div class="footer fade-in">
            <img src="https://github.com/Anmol-Baranwal/Cool-GIFs-For-GitHub/assets/74038190/d48893bd-0757-481c-8d7e-ba3e163feae7" 
                 width="500" class="footer-animation" alt="Footer Animation">
            <h3>⚡ Building Intelligent Systems with Code & Data ⚡</h3>
        </div>
    </div>

    <script>
        // Typing Animation
        const texts = [
            "Software Developer | ML & Deep Learning Enthusiast",
            "Advanced .NET | Flutter | Backend Developer",
            "Turning Data Into Intelligent Solutions",
            "Building Scalable, Production-Ready Applications"
        ];
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typing');

        function type() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }

            typingElement.innerHTML += '<span class="cursor">|</span>';

            let typeSpeed = isDeleting ? 30 : 100;

            if (!isDeleting && charIndex === currentText.length) {
                typeSpeed = 2000;
                isDeleting = true;
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
                typeSpeed = 500;
            }

            setTimeout(type, typeSpeed);
        }

        type();

        // Particle Background
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 50; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.width = Math.random() * 5 + 2 + 'px';
            particle.style.height = particle.style.width;
            particle.style.left = Math.random() * 100 + '%';
            particle.style.top = Math.random() * 100 + '%';
            particle.style.animationDelay = Math.random() * 20 + 's';
            particle.style.animationDuration = Math.random() * 20 + 10 + 's';
            particlesContainer.appendChild(particle);
        }

        // Counter Animation
        function animateCounter(element) {
            const target = parseInt(element.getAttribute('data-target'));
            let current = 0;
            const increment = target / 50;
            const timer = setInterval(() => {
                current += increment;
                if (current >= target) {
                    element.textContent = target + '+';
                    clearInterval(timer);
                } else {
                    element.textContent = Math.floor(current);
                }
            }, 30);
        }

        // Intersection Observer for animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    if (entry.target.classList.contains('stat-number')) {
                        animateCounter(entry.target);
                    }
                }
            });
        }, { threshold: 0.5 });

        document.querySelectorAll('.stat-number').forEach(stat => {
            observer.observe(stat);
        });

        // Fade in animation on scroll
        const fadeElements = document.querySelectorAll('.fade-in');
        const fadeObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, { threshold: 0.1 });

        fadeElements.forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'opacity 1s ease, transform 1s ease';
            fadeObserver.observe(el);
        });
    </script>
</body>
</html>
