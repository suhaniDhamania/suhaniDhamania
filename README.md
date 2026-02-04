<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Suhani Dhamania - Full Stack Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #6366f1;
            --secondary: #38bdf8;
            --accent: #0ea5e9;
            --success: #10b981;
            --dark: #0f172a;
            --dark-light: #1e293b;
            --text: #e2e8f0;
            --text-light: #94a3b8;
        }

        body {
            background: linear-gradient(135deg, var(--dark) 0%, var(--dark-light) 100%);
            color: var(--text);
            line-height: 1.6;
            overflow-x: hidden;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        .header {
            position: relative;
            padding: 40px 0;
            text-align: center;
            overflow: hidden;
        }

        .animated-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .gradient-dot {
            position: absolute;
            border-radius: 50%;
            opacity: 0.3;
            animation: float 6s ease-in-out infinite;
        }

        .dot-1 {
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, var(--primary) 0%, transparent 70%);
            top: -150px;
            left: -100px;
        }

        .dot-2 {
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, var(--secondary) 0%, transparent 70%);
            bottom: -50px;
            right: -50px;
            animation-delay: 2s;
        }

        .profile-img {
            width: 160px;
            height: 160px;
            border-radius: 50%;
            border: 4px solid var(--primary);
            box-shadow: 0 0 30px rgba(99, 102, 241, 0.5);
            margin: 0 auto 20px;
            animation: pulse 2s infinite;
            overflow: hidden;
        }

        .profile-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .name {
            font-size: 3rem;
            margin-bottom: 10px;
            background: linear-gradient(90deg, var(--primary), var(--secondary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-size: 200% 200%;
            animation: gradientShift 3s ease infinite;
        }

        .tagline {
            display: inline-block;
            padding: 8px 20px;
            background: rgba(99, 102, 241, 0.1);
            border: 2px solid var(--primary);
            border-radius: 25px;
            margin: 10px 0;
            color: var(--secondary);
            font-weight: bold;
            animation: borderPulse 2s infinite;
        }

        /* Typing Animation */
        .typing-container {
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 30px 0;
        }

        .typing-text {
            font-size: 1.5rem;
            color: var(--secondary);
            border-right: 3px solid var(--secondary);
            padding-right: 5px;
            white-space: nowrap;
            overflow: hidden;
            animation: typing 3.5s steps(40, end), blink 0.75s step-end infinite;
        }

        /* Stats Section */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 40px 0;
        }

        .stat-card {
            background: rgba(15, 23, 42, 0.7);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            border-top: 4px solid var(--primary);
            transition: transform 0.3s;
        }

        .stat-card:hover {
            transform: translateY(-10px);
        }

        .stat-card i {
            font-size: 2.5rem;
            color: var(--secondary);
            margin-bottom: 15px;
        }

        .stat-card h3 {
            font-size: 2rem;
            color: var(--accent);
            margin-bottom: 10px;
        }

        /* Tech Stack */
        .tech-stack {
            margin: 50px 0;
        }

        .tech-category {
            margin-bottom: 40px;
        }

        .tech-category h3 {
            color: var(--secondary);
            margin-bottom: 20px;
            font-size: 1.5rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .tech-icons {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
        }

        .tech-icon {
            background: rgba(30, 41, 59, 0.8);
            padding: 15px;
            border-radius: 10px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            width: 100px;
            height: 100px;
            transition: all 0.3s;
        }

        .tech-icon:hover {
            background: rgba(99, 102, 241, 0.2);
            transform: scale(1.1);
        }

        .tech-icon i {
            font-size: 2rem;
            margin-bottom: 10px;
            color: var(--secondary);
        }

        /* Projects */
        .projects {
            margin: 50px 0;
        }

        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(99, 102, 241, 0.1), rgba(56, 189, 248, 0.1));
            border-radius: 15px;
            padding: 25px;
            border-left: 4px solid var(--primary);
            transition: transform 0.3s;
        }

        .project-card:hover {
            transform: translateY(-5px);
        }

        .project-card h4 {
            color: var(--secondary);
            font-size: 1.3rem;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin: 15px 0;
        }

        .tag {
            background: rgba(99, 102, 241, 0.2);
            color: var(--secondary);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.9rem;
        }

        /* Charts */
        .charts {
            margin: 50px 0;
        }

        .chart-container {
            background: rgba(15, 23, 42, 0.7);
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 30px;
        }

        /* Contact */
        .contact {
            margin: 50px 0;
            text-align: center;
        }

        .contact-buttons {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin: 30px 0;
        }

        .contact-btn {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 15px 30px;
            background: linear-gradient(45deg, var(--primary), var(--accent));
            color: white;
            border-radius: 10px;
            text-decoration: none;
            font-weight: bold;
            transition: transform 0.3s;
        }

        .contact-btn:hover {
            transform: translateY(-5px);
        }

        .linkedin {
            background: linear-gradient(45deg, #0A66C2, #004182);
        }

        .github {
            background: linear-gradient(45deg, #181717, #333333);
        }

        .email {
            background: linear-gradient(45deg, #EA4335, #D14836);
        }

        /* Footer */
        .footer {
            background: linear-gradient(45deg, var(--dark), var(--dark-light));
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            margin-top: 50px;
        }

        .wave {
            width: 100%;
            height: 120px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            mask-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none"><path d="M321.39,56.44c58-10.79,114.16-30.13,172-41.86,82.39-16.72,168.19-17.73,250.45-.39C823.78,31,906.67,72,985.66,92.83c70.05,18.48,146.53,26.09,214.34,3V0H0V27.35A600.21,600.21,0,0,0,321.39,56.44Z"></path></svg>');
            mask-size: cover;
            animation: wave 10s linear infinite;
        }

        /* Animations */
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        @keyframes pulse {
            0% { box-shadow: 0 0 30px rgba(99, 102, 241, 0.5); }
            50% { box-shadow: 0 0 50px rgba(99, 102, 241, 0.8); }
            100% { box-shadow: 0 0 30px rgba(99, 102, 241, 0.5); }
        }

        @keyframes borderPulse {
            0% { border-color: var(--primary); }
            50% { border-color: var(--secondary); }
            100% { border-color: var(--primary); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }

        @keyframes blink {
            from, to { border-color: transparent }
            50% { border-color: var(--secondary); }
        }

        @keyframes wave {
            0% { transform: translateX(0); }
            100% { transform: translateX(-50%); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .name {
                font-size: 2rem;
            }
            
            .project-grid {
                grid-template-columns: 1fr;
            }
            
            .tech-icons {
                justify-content: center;
            }
            
            .contact-buttons {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="animated-bg">
                <div class="gradient-dot dot-1"></div>
                <div class="gradient-dot dot-2"></div>
            </div>
            
            <div class="profile-img">
                <img src="https://github.com/suhaniDhamania.png" alt="Suhani Dhamania">
            </div>
            
            <h1 class="name">Suhani Dhamania</h1>
            <div class="tagline">🚀 Full Stack Developer</div>
            
            <div class="typing-container">
                <div class="typing-text" id="typing-text">Building Scalable Web Applications...</div>
            </div>
        </header>

        <!-- Stats Section -->
        <section class="stats">
            <div class="stat-card">
                <i class="fas fa-code"></i>
                <h3 id="projectCount">15+</h3>
                <p>Projects Completed</p>
            </div>
            <div class="stat-card">
                <i class="fas fa-clock"></i>
                <h3 id="codingHours">1000+</h3>
                <p>Coding Hours</p>
            </div>
            <div class="stat-card">
                <i class="fas fa-star"></i>
                <h3 id="githubStars">50+</h3>
                <p>GitHub Stars</p>
            </div>
            <div class="stat-card">
                <i class="fas fa-users"></i>
                <h3 id="collaborations">10+</h3>
                <p>Collaborations</p>
            </div>
        </section>

        <!-- Tech Stack Section -->
        <section class="tech-stack">
            <h2 style="text-align: center; margin-bottom: 40px; color: var(--secondary);">🛠️ Tech Stack</h2>
            
            <div class="tech-category">
                <h3><i class="fas fa-paint-brush"></i> Frontend</h3>
                <div class="tech-icons">
                    <div class="tech-icon">
                        <i class="fab fa-react"></i>
                        <span>React</span>
                    </div>
                    <div class="tech-icon">
                        <i class="fab fa-js"></i>
                        <span>JavaScript</span>
                    </div>
                    <div class="tech-icon">
                        <i class="fab fa-html5"></i>
                        <span>HTML5</span>
                    </div>
                    <div class="tech-icon">
                        <i class="fab fa-css3-alt"></i>
                        <span>CSS3</span>
                    </div>
                    <div class="tech-icon">
                        <i class="fab fa-bootstrap"></i>
                        <span>Bootstrap</span>
                    </div>
                </div>
            </div>

            <div class="tech-category">
                <h3><i class="fas fa-server"></i> Backend</h3>
                <div class="tech-icons">
                    <div class="tech-icon">
                        <i class="fab fa-node-js"></i>
                        <span>Node.js</span>
                    </div>
                    <div class="tech-icon">
                        <i class="fas fa-bolt"></i>
                        <span>Express</span>
                    </div>
                    <div class="tech-icon">
                        <i class="fas fa-database"></i>
                        <span>MongoDB</span>
                    </div>
                    <div class="tech-icon">
                        <i class="fas fa-database"></i>
                        <span>PostgreSQL</span>
                    </div>
                </div>
            </div>

            <div class="tech-category">
                <h3><i class="fas fa-tools"></i> Tools & Others</h3>
                <div class="tech-icons">
                    <div class="tech-icon">
                        <i class="fab fa-git-alt"></i>
                        <span>Git</span>
                    </div>
                    <div class="tech-icon">
                        <i class="fab fa-github"></i>
                        <span>GitHub</span>
                    </div>
                    <div class="tech-icon">
                        <i class="fas fa-rocket"></i>
                        <span>Vite</span>
                    </div>
                    <div class="tech-icon">
                        <i class="fas fa-code"></i>
                        <span>VS Code</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section class="projects">
            <h2 style="text-align: center; margin-bottom: 40px; color: var(--secondary);">🚀 Featured Projects</h2>
            
            <div class="project-grid">
                <div class="project-card">
                    <h4><i class="fas fa-hospital"></i> Smilesync - PACS Integration</h4>
                    <p>Advanced DICOM medical imaging platform with real-time processing and secure access.</p>
                    <div class="project-tags">
                        <span class="tag">React</span>
                        <span class="tag">Node.js</span>
                        <span class="tag">MongoDB</span>
                        <span class="tag">WebSockets</span>
                    </div>
                    <p style="margin-top: 15px; color: var(--success);">
                        <i class="fas fa-check-circle"></i> Live & Active
                    </p>
                </div>

                <div class="project-card">
                    <h4><i class="fas fa-utensils"></i> Food Delivery System</h4>
                    <p>Full-stack food delivery platform with real-time order tracking and payment integration.</p>
                    <div class="project-tags">
                        <span class="tag">MERN Stack</span>
                        <span class="tag">JWT Auth</span>
                        <span class="tag">REST API</span>
                        <span class="tag">Stripe</span>
                    </div>
                </div>

                <div class="project-card">
                    <h4><i class="fas fa-chart-line"></i> Zerodha Trading Clone</h4>
                    <p>Stock trading simulation dashboard with real-time market data and chart visualization.</p>
                    <div class="project-tags">
                        <span class="tag">Chart.js</span>
                        <span class="tag">WebSocket</span>
                        <span class="tag">React</span>
                        <span class="tag">Node.js</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Skills Chart -->
        <section class="charts">
            <h2 style="text-align: center; margin-bottom: 40px; color: var(--secondary);">📊 Skills Proficiency</h2>
            
            <div class="chart-container">
                <canvas id="skillsChart"></canvas>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="contact">
            <h2 style="text-align: center; margin-bottom: 40px; color: var(--secondary);">🌐 Connect With Me</h2>
            
            <div class="contact-buttons">
                <a href="https://portfolio-app-726d.onrender.com" class="contact-btn" target="_blank">
                    <i class="fas fa-globe"></i> Portfolio
                </a>
                <a href="https://www.linkedin.com/in/suhanidhamania" class="contact-btn linkedin" target="_blank">
                    <i class="fab fa-linkedin"></i> LinkedIn
                </a>
                <a href="https://github.com/suhaniDhamania" class="contact-btn github" target="_blank">
                    <i class="fab fa-github"></i> GitHub
                </a>
                <a href="mailto:suhanidhamania157@gmail.com" class="contact-btn email">
                    <i class="fas fa-envelope"></i> Email
                </a>
            </div>
            
            <div style="margin-top: 30px; color: var(--text-light);">
                <p><i class="fas fa-clock"></i> <strong>Best Time to Connect:</strong> Monday - Friday, 10 AM - 7 PM IST</p>
            </div>
        </section>

        <!-- Footer -->
        <footer class="footer">
            <div class="wave"></div>
            
            <h3 style="color: var(--secondary); margin: 30px 0 20px;">✨ Thanks for Visiting!</h3>
            
            <p style="color: var(--text-light); max-width: 800px; margin: 0 auto 20px;">
                "Code is like humor. When you have to explain it, it's bad." – Cory House
            </p>
            
            <div style="color: var(--text-light); margin-top: 20px;">
                <p><i class="fas fa-map-marker-alt"></i> <strong>Location:</strong> Uttar Pradesh, India</p>
                <p><i class="fas fa-bullseye"></i> <strong>Status:</strong> Open to new opportunities & collaborations</p>
                <p><i class="fas fa-rocket"></i> <strong>Next Goal:</strong> Contribute to open-source projects</p>
            </div>
            
            <div style="margin-top: 40px; padding-top: 20px; border-top: 1px solid rgba(255, 255, 255, 0.1);">
                <p style="color: var(--text-light); font-size: 0.9rem;">
                    <i class="far fa-copyright"></i> 2024 Suhani Dhamania | Made with <i class="fas fa-heart" style="color: #ff4757;"></i>
                </p>
            </div>
        </footer>
    </div>

    <script>
        // Typing animation text
        const typingTexts = [
            "Building Scalable Web Applications...",
            "MERN Stack Developer...",
            "PACS Integration Specialist...",
            "Open Source Contributor...",
            "Always Learning New Tech..."
        ];
        
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        
        function typeEffect() {
            const currentText = typingTexts[textIndex];
            
            if (isDeleting) {
                charIndex--;
            } else {
                charIndex++;
            }
            
            document.getElementById('typing-text').textContent = currentText.substring(0, charIndex);
            
            if (!isDeleting && charIndex === currentText.length) {
                setTimeout(() => isDeleting = true, 1500);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % typingTexts.length;
            }
            
            const speed = isDeleting ? 50 : 100;
            setTimeout(typeEffect, speed);
        }
        
        // Initialize typing effect
        setTimeout(typeEffect, 1000);
        
        // Animated counters
        function animateCounter(elementId, target, duration = 2000) {
            const element = document.getElementById(elementId);
            const start = 0;
            const increment = target / (duration / 16);
            let current = start;
            
            const timer = setInterval(() => {
                current += increment;
                if (current >= target) {
                    element.textContent = target + '+';
                    clearInterval(timer);
                } else {
                    element.textContent = Math.floor(current) + '+';
                }
            }, 16);
        }
        
        // Start counters when in view
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    animateCounter('projectCount', 15);
                    animateCounter('codingHours', 1000);
                    animateCounter('githubStars', 50);
                    animateCounter('collaborations', 10);
                }
            });
        }, { threshold: 0.5 });
        
        observer.observe(document.querySelector('.stats'));
        
        // Skills Chart
        const skillsChart = new Chart(document.getElementById('skillsChart').getContext('2d'), {
            type: 'radar',
            data: {
                labels: ['React', 'Node.js', 'MongoDB', 'Express', 'JavaScript', 'HTML/CSS', 'Git/GitHub'],
                datasets: [{
                    label: 'Proficiency Level',
                    data: [90, 85, 80, 75, 95, 90, 85],
                    backgroundColor: 'rgba(56, 189, 248, 0.2)',
                    borderColor: 'rgba(56, 189, 248, 1)',
                    borderWidth: 2,
                    pointBackgroundColor: 'rgba(99, 102, 241, 1)',
                    pointBorderColor: '#fff',
                    pointBorderWidth: 2,
                    pointRadius: 4
                }]
            },
            options: {
                scales: {
                    r: {
                        angleLines: {
                            color: 'rgba(255, 255, 255, 0.1)'
                        },
                        grid: {
                            color: 'rgba(255, 255, 255, 0.1)'
                        },
                        pointLabels: {
                            color: 'rgba(255, 255, 255, 0.8)'
                        },
                        ticks: {
                            display: false,
                            max: 100
                        }
                    }
                },
                plugins: {
                    legend: {
                        labels: {
                            color: 'rgba(255, 255, 255, 0.8)'
                        }
                    }
                }
            }
        });
        
        // Add hover effects to tech icons
        document.querySelectorAll('.tech-icon').forEach(icon => {
            icon.addEventListener('mouseenter', function() {
                const text = this.querySelector('span').textContent;
                console.log(`Hovering over: ${text}`);
            });
        });
        
        // Add click effects to project cards
        document.querySelectorAll('.project-card').forEach(card => {
            card.addEventListener('click', function() {
                const title = this.querySelector('h4').textContent;
                alert(`Opening details for: ${title}`);
            });
        });
        
        // Add scroll animation
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const rate = scrolled * -0.5;
            document.querySelector('.dot-1').style.transform = `translateY(${rate * 0.1}px)`;
            document.querySelector('.dot-2').style.transform = `translateY(${rate * 0.05}px)`;
        });
        
        // Theme toggle (optional)
        function toggleTheme() {
            document.body.classList.toggle('light-theme');
            const isLight = document.body.classList.contains('light-theme');
            document.body.style.backgroundColor = isLight ? '#f8fafc' : '#0f172a';
            document.body.style.color = isLight ? '#1e293b' : '#e2e8f0';
        }
        
        // You can add a theme toggle button in the future
        console.log('Portfolio loaded successfully!');
    </script>
</body>
</html>
