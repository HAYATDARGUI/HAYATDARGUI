<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hayat Dargui - Full Stack Developer</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0f0f0f 0%, #1a1a1a 50%, #0d4d0d 100%);
            color: #e0e0e0;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            text-align: center;
            padding: 60px 0;
            background: rgba(0, 20, 0, 0.3);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            margin-bottom: 40px;
            box-shadow: 0 8px 32px rgba(64, 160, 64, 0.1);
            border: 1px solid rgba(64, 160, 64, 0.2);
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(64, 160, 64, 0.1), transparent);
            animation: shimmer 3s infinite;
            transform: rotate(45deg);
        }

        @keyframes shimmer {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 5px solid rgba(64, 160, 64, 0.5);
            margin: 0 auto 20px;
            background: url('https://cdn.dribbble.com/users/4055494/screenshots/15215756/media/d2b66c4ca0192aa26d103448b3d1518b.gif') center/cover;
            box-shadow: 0 0 30px rgba(64, 160, 64, 0.3);
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .wave {
            display: inline-block;
            animation: wave 2s infinite;
            transform-origin: 70% 70%;
            font-size: 2rem;
        }

        @keyframes wave {
            0%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(-20deg); }
            75% { transform: rotate(20deg); }
        }

        h1 {
            font-size: 3rem;
            color: #40a040;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.8);
            position: relative;
            z-index: 1;
        }

        .subtitle {
            font-size: 1.3rem;
            color: rgba(255, 255, 255, 0.9);
            margin-bottom: 30px;
            position: relative;
            z-index: 1;
        }

        .badge-42 {
            margin: 20px 0;
            position: relative;
            z-index: 1;
        }

        .badge-42 img {
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            transition: transform 0.3s ease;
        }

        .badge-42 img:hover {
            transform: scale(1.05);
        }

        .stats {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 30px;
            position: relative;
            z-index: 1;
        }

        .stat-item {
            background: rgba(0, 20, 0, 0.4);
            padding: 15px 25px;
            border-radius: 15px;
            text-align: center;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(64, 160, 64, 0.3);
        }

        .stat-number {
            font-size: 1.5rem;
            font-weight: bold;
            color: #40a040;
        }

        .stat-label {
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.8);
        }

        .section {
            background: linear-gradient(145deg, #1a1a1a, #0f0f0f);
            padding: 40px;
            margin-bottom: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            border: 1px solid rgba(64, 160, 64, 0.1);
            position: relative;
            overflow: hidden;
        }

        .section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #40a040, #50b050, #45a545, #3a8a3a);
        }

        .section h2 {
            font-size: 2rem;
            color: #40a040;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .section h2 i {
            color: #50b050;
        }

        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            align-items: center;
        }

        .about-text {
            font-size: 1.1rem;
            color: #e0e0e0;
        }

        .about-img {
            text-align: center;
        }

        .about-img img {
            max-width: 100%;
            border-radius: 15px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
        }

        .skill-item {
            background: linear-gradient(135deg, #1a1a1a 0%, #0f0f0f 100%);
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 2px solid rgba(64, 160, 64, 0.2);
        }

        .skill-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(64, 160, 64, 0.2);
            border-color: #40a040;
        }

        .skill-item img {
            width: 50px;
            height: 50px;
            margin-bottom: 10px;
        }

        .skill-item h3 {
            color: #40a040;
            font-size: 1rem;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .contact-item {
            background: linear-gradient(135deg, #2a4a2a 0%, #1a3a1a 100%);
            color: white;
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s ease;
            text-decoration: none;
            border: 1px solid rgba(64, 160, 64, 0.3);
        }

        .contact-item:hover {
            transform: translateY(-5px);
            text-decoration: none;
            color: white;
            box-shadow: 0 10px 25px rgba(64, 160, 64, 0.3);
        }

        .contact-item i {
            font-size: 2rem;
            margin-bottom: 10px;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }

        .social-link {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #2a4a2a 0%, #1a3a1a 100%);
            color: #40a040;
            border-radius: 50%;
            text-decoration: none;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 2px solid rgba(64, 160, 64, 0.3);
        }

        .social-link:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(64, 160, 64, 0.4);
            color: #40a040;
            text-decoration: none;
            border-color: #40a040;
        }

        .social-link i {
            font-size: 1.2rem;
        }

        .footer {
            text-align: center;
            padding: 40px 20px;
            color: white;
            background: rgba(0, 20, 0, 0.3);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            margin-top: 40px;
            border: 1px solid rgba(64, 160, 64, 0.2);
        }

        @media (max-width: 768px) {
            .container {
                padding: 10px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .about-grid {
                grid-template-columns: 1fr;
            }
            
            .stats {
                flex-direction: column;
                align-items: center;
            }
            
            .section {
                padding: 20px;
            }
        }

        .typing-effect {
            border-right: 3px solid #40a040;
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 50% { border-color: #40a040; }
            51%, 100% { border-color: transparent; }
        }
    </style>
</head>
<body>
    <div class="container">
        <header class="header">
            <div class="profile-img"></div>
            <h1>Hi <span class="wave">👋</span>, I'm Hayat Dargui</h1>
          <div align="center">

        [![hdargui's 42 stats](https://badge.mediaplus.ma/greenbinary/hdargui)](https://github.com/oakoudad/badge42)

        </div>
            <p class="subtitle">A passionate <span class="typing-effect" id="typing-text">Full-Stack Developer</span> from Morocco</p>
            
            <div class="badge-42">
                <a href="https://github.com/oakoudad/badge42" target="_blank">
                    <img src="https://badge.mediaplus.ma/greenbinary/hdargui" alt="hdargui's 42 stats">
                </a>
            </div>
            
            <div class="stats">
                <div class="stat-item">
                    <div class="stat-number" id="profile-views">0</div>
                    <div class="stat-label">Profile Views</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">2+</div>
                    <div class="stat-label">Years Experience</div>
                </div>
                <div class="stat-item">
                    <div class="stat-number">10+</div>
                    <div class="stat-label">Projects</div>
                </div>
            </div>
        </header>

        <section class="section">
            <h2><i class="fas fa-user"></i> About Me</h2>
            <div class="about-grid">
                <div class="about-text">
                    <p>Welcome to my digital space! I'm a passionate full-stack web developer from Morocco, currently expanding my expertise in React and Laravel. I love creating innovative solutions and bringing ideas to life through code.</p>
                    <br>
                    <p>🌱 Currently mastering <strong>React</strong> and <strong>Laravel</strong></p>
                    <p>💡 Always eager to learn new technologies</p>
                    <p>🚀 Focused on building scalable web applications</p>
                    <p>🎯 Goal-oriented and detail-focused developer</p>
                </div>
                <div class="about-img">
                    <img src="https://cdn.dribbble.com/users/4055494/screenshots/15215756/media/d2b66c4ca0192aa26d103448b3d1518b.gif" alt="Coding Animation">
                </div>
            </div>
        </section>

        <section class="section">
            <h2><i class="fas fa-code"></i> Skills & Technologies</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="HTML5">
                    <h3>HTML5</h3>
                </div>
                <div class="skill-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="CSS3">
                    <h3>CSS3</h3>
                </div>
                <div class="skill-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg" alt="React">
                    <h3>React</h3>
                </div>
                <div class="skill-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/php/php-original.svg" alt="PHP">
                    <h3>PHP</h3>
                </div>
                <div class="skill-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="Python">
                    <h3>Python</h3>
                </div>
                <div class="skill-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="Java">
                    <h3>Java</h3>
                </div>
                <div class="skill-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="MySQL">
                    <h3>MySQL</h3>
                </div>
                <div class="skill-item">
                    <img src="https://www.vectorlogo.zone/logos/appwriteio/appwriteio-icon.svg" alt="Appwrite">
                    <h3>Appwrite</h3>
                </div>
                <div class="skill-item">
                    <img src="https://www.chartjs.org/media/logo-title.svg" alt="Chart.js">
                    <h3>Chart.js</h3>
                </div>
            </div>
        </section>

        <section class="section">
            <h2><i class="fas fa-envelope"></i> Get In Touch</h2>
            <div class="contact-grid">
                <a href="mailto:hayatdargui72@gmail.com" class="contact-item">
                    <i class="fas fa-envelope"></i>
                    <h3>Email</h3>
                    <p>hayatdargui72@gmail.com</p>
                </a>
                <a href="https://twitter.com/hayatdargui" target="_blank" class="contact-item">
                    <i class="fab fa-twitter"></i>
                    <h3>Twitter</h3>
                    <p>@hayatdargui</p>
                </a>
                <a href="https://instagram.com/_hayat_dk_" target="_blank" class="contact-item">
                    <i class="fab fa-instagram"></i>
                    <h3>Instagram</h3>
                    <p>@_hayat_dk_</p>
                </a>
            </div>
            
            <div class="social-links">
                <a href="https://twitter.com/hayatdargui" target="_blank" class="social-link">
                    <i class="fab fa-twitter"></i>
                </a>
                <a href="https://instagram.com/_hayat_dk_" target="_blank" class="social-link">
                    <i class="fab fa-instagram"></i>
                </a>
                <a href="https://github.com/hayatdargui" target="_blank" class="social-link">
                    <i class="fab fa-github"></i>
                </a>
                <a href="https://linkedin.com/in/hayatdargui" target="_blank" class="social-link">
                    <i class="fab fa-linkedin"></i>
                </a>
            </div>
        </section>

        <footer class="footer">
            <p>&copy; 2025 Hayat Dargui. Crafted with ❤️ and lots of ☕</p>
            <p>Made with passion in Morocco 🇲🇦</p>
        </footer>
    </div>

    <script>
        // Typing effect
        const typingText = document.getElementById('typing-text');
        const phrases = ['Full-Stack Developer', 'React Enthusiast', 'Laravel Developer', 'Problem Solver'];
        let phraseIndex = 0;
        let charIndex = 0;
        let isDeleting = false;

        function typeEffect() {
            const currentPhrase = phrases[phraseIndex];
            
            if (isDeleting) {
                typingText.textContent = currentPhrase.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingText.textContent = currentPhrase.substring(0, charIndex + 1);
                charIndex++;
            }

            if (!isDeleting && charIndex === currentPhrase.length) {
                setTimeout(() => isDeleting = true, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                phraseIndex = (phraseIndex + 1) % phrases.length;
            }

            const typingSpeed = isDeleting ? 50 : 100;
            setTimeout(typeEffect, typingSpeed);
        }

        // Profile views counter animation
        function animateCounter() {
            const counter = document.getElementById('profile-views');
            const target = Math.floor(Math.random() * 1000) + 500; // Random number between 500-1500
            let current = 0;
            const increment = target / 100;
            
            const timer = setInterval(() => {
                current += increment;
                if (current >= target) {
                    counter.textContent = Math.floor(target);
                    clearInterval(timer);
                } else {
                    counter.textContent = Math.floor(current);
                }
            }, 20);
        }

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Initialize animations
        document.addEventListener('DOMContentLoaded', () => {
            typeEffect();
            setTimeout(animateCounter, 1000);
            
            // Add animation classes to sections
            document.querySelectorAll('.section').forEach((section, index) => {
                section.style.opacity = '0';
                section.style.transform = 'translateY(50px)';
                section.style.transition = `opacity 0.6s ease ${index * 0.1}s, transform 0.6s ease ${index * 0.1}s`;
                observer.observe(section);
            });
        });

        // Smooth scrolling for internal links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>
</body>
</html>
