<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Buddhike Kuruppu - Cloud Engineer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #ffffff;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Hero Section */
        .hero {
            text-align: center;
            padding: 60px 0;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 20px;
            margin-bottom: 40px;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
        }

        .profile-image {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid rgba(255, 255, 255, 0.3);
            margin-bottom: 20px;
            animation: float 3s ease-in-out infinite;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            margin: 0 auto 20px;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 3s ease-in-out infinite;
        }

        @keyframes gradientShift {
            0%, 100% { filter: hue-rotate(0deg); }
            50% { filter: hue-rotate(90deg); }
        }

        .hero h2 {
            font-size: 1.5rem;
            margin-bottom: 20px;
            opacity: 0.9;
        }

        .profile-views {
            display: inline-block;
            background: rgba(255, 255, 255, 0.2);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.9rem;
            backdrop-filter: blur(10px);
        }

        /* About Section */
        .about {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            margin-bottom: 40px;
        }

        .about-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 15px;
            padding: 30px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .about-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .about-item {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            padding: 10px;
            border-radius: 10px;
            transition: background 0.3s ease;
        }

        .about-item:hover {
            background: rgba(255, 255, 255, 0.1);
        }

        .about-item span {
            font-size: 1.5rem;
            margin-right: 15px;
            width: 30px;
        }

        /* Skills Section */
        .skills {
            margin-bottom: 40px;
        }

        .skills h3 {
            text-align: center;
            font-size: 2rem;
            margin-bottom: 30px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .skill-item {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .skill-item:hover {
            transform: scale(1.1);
            background: rgba(255, 255, 255, 0.2);
        }

        .skill-icon {
            font-size: 2.5rem;
            margin-bottom: 10px;
            display: block;
        }

        .skill-name {
            font-size: 0.8rem;
            font-weight: 600;
        }

        /* Social Links */
        .social {
            text-align: center;
            margin-bottom: 40px;
        }

        .social h3 {
            font-size: 2rem;
            margin-bottom: 20px;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 60px;
            height: 60px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 50%;
            text-decoration: none;
            color: white;
            font-size: 1.5rem;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            transform: scale(1.2);
            background: rgba(255, 255, 255, 0.3);
        }

        /* Stats Section */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(20px);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: transform 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
        }

        .stat-card img {
            border-radius: 10px;
            width: 100%;
            height: auto;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2rem;
            }
            
            .about {
                grid-template-columns: 1fr;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(60px, 1fr));
            }
            
            .container {
                padding: 10px;
            }
        }

        /* Floating Animation */
        .floating {
            animation: floating 2s ease-in-out infinite;
        }

        @keyframes floating {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        /* Pulse Animation */
        .pulse {
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { opacity: 1; }
            50% { opacity: 0.7; }
            100% { opacity: 1; }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Hero Section -->
        <div class="hero">
            <div class="hero-content">
                <div class="profile-image">🤖</div>
                <h1>Hi 👋, I'm Buddhike Kuruppu</h1>
                <h2>Energetic Cloud Engineer (DevOps Specialist)</h2>
                <p style="margin-bottom: 20px;">📍 Melbourne, Australia</p>
                <div class="profile-views pulse">
                    👀 Profile Views: 1,234+
                </div>
            </div>
        </div>

        <!-- About Section -->
        <div class="about">
            <div class="about-card floating">
                <h3 style="margin-bottom: 20px; text-align: center;">🚀 What I'm Up To</h3>
                <div class="about-item">
                    <span>🔭</span>
                    <div>
                        <strong>Currently Working On:</strong><br>
                        Cloud DevOps and Migration projects
                    </div>
                </div>
                <div class="about-item">
                    <span>💬</span>
                    <div>
                        <strong>Ask Me About:</strong><br>
                        Cisco Networking, Azure DevOps, Automation, Linux Administration, Azure
                    </div>
                </div>
                <div class="about-item">
                    <span>⚡</span>
                    <div>
                        <strong>Fun Fact:</strong><br>
                        I love watching and giving reviews on movies 😜
                    </div>
                </div>
            </div>
            
            <div class="about-card floating" style="animation-delay: 0.5s;">
                <h3 style="margin-bottom: 20px; text-align: center;">📫 Let's Connect</h3>
                <div class="about-item">
                    <span>📧</span>
                    <div>
                        <strong>Email:</strong><br>
                        <a href="mailto:buddhikakuruppu@hotmail.com" style="color: #4ecdc4;">buddhikakuruppu@hotmail.com</a>
                    </div>
                </div>
                <div class="about-item">
                    <span>📄</span>
                    <div>
                        <strong>Resume:</strong><br>
                        <a href="https://drive.google.com/file/d/17nXPtZjazTTXU7CIrw2qLeHd1bmOndXe/view?usp=sharing" style="color: #4ecdc4;" target="_blank">View My Experience</a>
                    </div>
                </div>
                <div class="about-item">
                    <span>🏆</span>
                    <div>
                        <strong>Achievements:</strong><br>
                        Cloud & DevOps Expert
                    </div>
                </div>
            </div>
        </div>

        <!-- Skills Section -->
        <div class="skills">
            <h3>🛠️ Technologies & Tools</h3>
            <div class="skills-grid">
                <div class="skill-item">
                    <span class="skill-icon">☁️</span>
                    <div class="skill-name">AWS</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🌐</span>
                    <div class="skill-name">Azure</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🐳</span>
                    <div class="skill-name">Docker</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🐍</span>
                    <div class="skill-name">Python</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🐧</span>
                    <div class="skill-name">Linux</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">📊</span>
                    <div class="skill-name">MySQL</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">⚙️</span>
                    <div class="skill-name">Git</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">💻</span>
                    <div class="skill-name">JavaScript</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🔧</span>
                    <div class="skill-name">Bash</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🎨</span>
                    <div class="skill-name">CSS</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🌐</span>
                    <div class="skill-name">HTML</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🔌</span>
                    <div class="skill-name">Arduino</div>
                </div>
            </div>
        </div>

        <!-- Social Links -->
        <div class="social">
            <h3>🤝 Connect With Me</h3>
            <div class="social-links">
                <a href="https://linkedin.com/in/buddhika-kuruppu" target="_blank" class="social-link">
                    💼
                </a>
                <a href="https://instagram.com/buddhika.kuruppu" target="_blank" class="social-link">
                    📸
                </a>
                <a href="mailto:buddhikakuruppu@hotmail.com" class="social-link">
                    📧
                </a>
            </div>
        </div>

        <!-- GitHub Stats -->
        <div class="stats">
            <div class="stat-card">
                <h4 style="margin-bottom: 15px;">📊 GitHub Stats</h4>
                <img src="https://github-readme-stats.vercel.app/api?username=buddhika-kuruppu&theme=radical&show_icons=true&locale=en&hide_border=true&bg_color=00000000" alt="GitHub Stats" />
            </div>
            <div class="stat-card">
                <h4 style="margin-bottom: 15px;">🔥 Streak Stats</h4>
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=buddhika-kuruppu&theme=radical&hide_border=true&background=00000000" alt="Streak Stats" />
            </div>
            <div class="stat-card">
                <h4 style="margin-bottom: 15px;">💻 Top Languages</h4>
                <img src="https://github-readme-stats.vercel.app/api/top-langs?username=buddhika-kuruppu&theme=radical&show_icons=true&locale=en&layout=compact&hide_border=true&bg_color=00000000" alt="Top Languages" />
            </div>
        </div>
    </div>

    <script>
        // Add interactive animations
        document.addEventListener('DOMContentLoaded', function() {
            // Skill items hover effect
            const skillItems = document.querySelectorAll('.skill-item');
            skillItems.forEach(item => {
                item.addEventListener('mouseenter', function() {
                    this.style.transform = 'scale(1.1) rotate(5deg)';
                });
                item.addEventListener('mouseleave', function() {
                    this.style.transform = 'scale(1) rotate(0deg)';
                });
            });

            // Add parallax effect to hero section
            window.addEventListener('scroll', function() {
                const scrolled = window.pageYOffset;
                const hero = document.querySelector('.hero');
                if (hero) {
                    hero.style.transform = `translateY(${scrolled * 0.5}px)`;
                }
            });

            // Add typing effect to title
            const title = document.querySelector('.hero h1');
            if (title) {
                const text = title.textContent;
                title.textContent = '';
                let i = 0;
                const typeWriter = () => {
                    if (i < text.length) {
                        title.textContent += text.charAt(i);
                        i++;
                        setTimeout(typeWriter, 100);
                    }
                };
                setTimeout(typeWriter, 1000);
            }
        });
    </script>
</body>
</html>
