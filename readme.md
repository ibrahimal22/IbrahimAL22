<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ibrahim Aloui | AI Engineer & Full Stack Developer</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #667eea;
            --secondary: #764ba2;
            --accent: #f093fb;
            --dark: #0f0f23;
            --light: #ffffff;
            --gray: #8892b0;
            --highlight: #64ffda;
            --success: #00d4aa;
            --warning: #ffd700;
            --danger: #ff6b6b;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--dark);
            color: var(--light);
            overflow-x: hidden;
            line-height: 1.6;
        }

        /* Animated Background */
        .animated-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(45deg, #667eea, #764ba2, #f093fb, #f5576c);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
        }

        .animated-bg::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--dark);
            opacity: 0.95;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Floating Particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: var(--highlight);
            border-radius: 50%;
            animation: float 20s infinite linear;
            opacity: 0.7;
        }

        @keyframes float {
            0% {
                transform: translateY(100vh) translateX(0px);
                opacity: 0;
            }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% {
                transform: translateY(-100px) translateX(100px);
                opacity: 0;
            }
        }

        /* Scroll Progress Bar */
        .scroll-progress {
            position: fixed;
            top: 0;
            left: 0;
            width: 0%;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            z-index: 1000;
            transition: width 0.1s ease;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 999;
            display: flex;
            gap: 10px;
        }

        .nav-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            cursor: pointer;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .nav-dot.active {
            background: var(--highlight);
            transform: scale(1.5);
            box-shadow: 0 0 20px var(--highlight);
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
        }

        .hero-content {
            animation: fadeInUp 1s ease 0.5s both;
        }

        .hero h1 {
            font-size: clamp(3rem, 8vw, 8rem);
            font-weight: 900;
            background: linear-gradient(135deg, var(--highlight), var(--accent));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 20px;
            line-height: 1.1;
        }

        .hero .subtitle {
            font-size: clamp(1.2rem, 3vw, 2rem);
            color: var(--gray);
            margin-bottom: 30px;
            opacity: 0;
            animation: fadeInUp 1s ease 1s both;
        }

        .typing-animation {
            font-size: clamp(1rem, 2.5vw, 1.5rem);
            color: var(--highlight);
            margin-bottom: 40px;
            min-height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            opacity: 0;
            animation: fadeInUp 1s ease 1.5s both;
        }

        .btn {
            padding: 15px 35px;
            border: none;
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.3);
        }

        .btn-outline {
            background: rgba(255, 255, 255, 0.1);
            color: var(--light);
            border: 2px solid var(--highlight);
            backdrop-filter: blur(10px);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .btn:hover::before {
            left: 100%;
        }

        /* Sections */
        .section {
            padding: 100px 0;
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.6s ease;
        }

        .section.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .section-title {
            font-size: clamp(2.5rem, 5vw, 4rem);
            font-weight: 800;
            text-align: center;
            margin-bottom: 60px;
            background: linear-gradient(135deg, var(--light), var(--gray));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* About Section */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            margin-top: 60px;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: var(--gray);
        }

        .about-stats {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 30px;
            margin-top: 40px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 30px;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: transform 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-10px);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 800;
            color: var(--highlight);
            display: block;
        }

        .stat-label {
            color: var(--gray);
            margin-top: 10px;
        }

        .about-image {
            position: relative;
        }

        .floating-card {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 40px;
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            animation: float-card 6s ease-in-out infinite;
        }

        @keyframes float-card {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(1deg); }
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            margin-top: 60px;
        }

        .skill-category {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 40px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .skill-category::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
        }

        .skill-category:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .skill-category h3 {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: var(--highlight);
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .skill-tag {
            background: rgba(100, 255, 218, 0.1);
            color: var(--highlight);
            padding: 8px 16px;
            border-radius: 25px;
            font-size: 0.9rem;
            border: 1px solid rgba(100, 255, 218, 0.3);
            transition: all 0.3s ease;
        }

        .skill-tag:hover {
            background: rgba(100, 255, 218, 0.2);
            transform: scale(1.05);
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 40px;
            margin-top: 60px;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            overflow: hidden;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.5s ease;
            position: relative;
            cursor: pointer;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1), rgba(240, 147, 251, 0.1));
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .project-card:hover::before {
            opacity: 1;
        }

        .project-card:hover {
            transform: translateY(-20px) scale(1.02);
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.4);
        }

        .project-image {
            height: 200px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
        }

        .project-content {
            padding: 30px;
        }

        .project-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 15px;
            color: var(--light);
        }

        .project-description {
            color: var(--gray);
            margin-bottom: 20px;
            font-size: 0.95rem;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 20px;
        }

        .tech-tag {
            background: rgba(102, 126, 234, 0.2);
            color: var(--primary);
            padding: 4px 12px;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: 500;
        }

        .project-links {
            display: flex;
            gap: 15px;
        }

        .project-link {
            color: var(--highlight);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .project-link:hover {
            transform: translateX(5px);
        }

        /* Contact Section */
        .contact-content {
            text-align: center;
            max-width: 600px;
            margin: 0 auto;
        }

        .contact-text {
            font-size: 1.2rem;
            color: var(--gray);
            margin-bottom: 40px;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin-top: 40px;
        }

        .contact-link {
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--light);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            padding: 15px 25px;
            border-radius: 50px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .contact-link:hover {
            transform: translateY(-5px);
            background: rgba(100, 255, 218, 0.1);
            color: var(--highlight);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .about-grid {
                grid-template-columns: 1fr;
                gap: 40px;
            }

            .about-stats {
                grid-template-columns: 1fr;
                gap: 20px;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .contact-links {
                flex-direction: column;
                align-items: center;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }

            nav {
                top: 10px;
                right: 10px;
            }
        }

        /* Loading Animation */
        .loading-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: var(--dark);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 9999;
            transition: opacity 0.5s ease;
        }

        .loader {
            width: 50px;
            height: 50px;
            border: 3px solid rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            border-top-color: var(--highlight);
            animation: spin 1s ease-in-out infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        .loading-screen.fade-out {
            opacity: 0;
            pointer-events: none;
        }

        /* Glitch Effect */
        .glitch {
            position: relative;
        }

        .glitch::before,
        .glitch::after {
            content: attr(data-text);
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }

        .glitch::before {
            animation: glitch-1 2s infinite;
            color: #ff0040;
            z-index: -1;
        }

        .glitch::after {
            animation: glitch-2 2s infinite;
            color: #00ff40;
            z-index: -2;
        }

        @keyframes glitch-1 {
            0%, 14%, 15%, 49%, 50%, 99%, 100% {
                transform: translate(0);
            }
            15%, 49% {
                transform: translate(-2px, -1px);
            }
        }

        @keyframes glitch-2 {
            0%, 20%, 21%, 62%, 63%, 99%, 100% {
                transform: translate(0);
            }
            21%, 62% {
                transform: translate(2px, 1px);
            }
        }
    </style>
</head>
<body>
    <div class="loading-screen" id="loadingScreen">
        <div class="loader"></div>
    </div>

    <div class="scroll-progress" id="scrollProgress"></div>
    <div class="animated-bg"></div>
    <div class="particles" id="particles"></div>

    <nav>
        <div class="nav-dot active" data-section="hero"></div>
        <div class="nav-dot" data-section="about"></div>
        <div class="nav-dot" data-section="skills"></div>
        <div class="nav-dot" data-section="projects"></div>
        <div class="nav-dot" data-section="contact"></div>
    </nav>

    <section class="hero" id="hero">
        <div class="hero-content">
            <h1 class="glitch" data-text="Ibrahim Aloui">Ibrahim Aloui</h1>
            <p class="subtitle">AI Engineer & Full Stack Developer</p>
            <div class="typing-animation" id="typingText"></div>
            <div class="cta-buttons">
                <a href="#projects" class="btn btn-primary">
                    <i class="fas fa-rocket"></i>
                    View My Work
                </a>
                <a href="#contact" class="btn btn-outline">
                    <i class="fas fa-envelope"></i>
                    Get In Touch
                </a>
            </div>
        </div>
    </section>

    <section class="section" id="about">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-grid">
                <div class="about-text">
                    <p>Senior AI Engineer with 5+ years of experience delivering enterprise-grade solutions. I specialize in machine learning, full-stack development, and scalable cloud architecture, transforming complex business challenges into intelligent, innovative solutions.</p>
                    
                    <p>My passion lies in pushing the boundaries of what's possible with AI and creating systems that not only solve today's problems but anticipate tomorrow's opportunities.</p>

                    <div class="about-stats">
                        <div class="stat-card">
                            <span class="stat-number">50+</span>
                            <div class="stat-label">Projects Delivered</div>
                        </div>
                        <div class="stat-card">
                            <span class="stat-number">100%</span>
                            <div class="stat-label">Client Satisfaction</div>
                        </div>
                        <div class="stat-card">
                            <span class="stat-number">5+</span>
                            <div class="stat-label">Years Experience</div>
                        </div>
                        <div class="stat-card">
                            <span class="stat-number">99.9%</span>
                            <div class="stat-label">System Uptime</div>
                        </div>
                    </div>
                </div>
                <div class="about-image">
                    <div class="floating-card">
                        <h3 style="color: var(--highlight); margin-bottom: 20px;">🎯 Current Focus</h3>
                        <ul style="list-style: none; space: 15px;">
                            <li>🤖 Advanced AI/ML Engineering</li>
                            <li>☁️ Cloud Architecture & DevOps</li>
                            <li>🌐 Full Stack Development</li>
                            <li>🔗 Blockchain & Web3</li>
                            <li>🏠 IoT & Smart Systems</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="section" id="skills">
        <div class="container">
            <h2 class="section-title">Technical Expertise</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3><i class="fas fa-brain"></i> AI & Machine Learning</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">Python</span>
                        <span class="skill-tag">TensorFlow</span>
                        <span class="skill-tag">PyTorch</span>
                        <span class="skill-tag">Scikit-Learn</span>
                        <span class="skill-tag">OpenCV</span>
                        <span class="skill-tag">Pandas</span>
                        <span class="skill-tag">NumPy</span>
                        <span class="skill-tag">MLOps</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3><i class="fas fa-code"></i> Full Stack Development</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">Django</span>
                        <span class="skill-tag">React</span>
                        <span class="skill-tag">JavaScript</span>
                        <span class="skill-tag">TypeScript</span>
                        <span class="skill-tag">Node.js</span>
                        <span class="skill-tag">Next.js</span>
                        <span class="skill-tag">FastAPI</span>
                        <span class="skill-tag">GraphQL</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3><i class="fas fa-cloud"></i> DevOps & Cloud</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">Docker</span>
                        <span class="skill-tag">Kubernetes</span>
                        <span class="skill-tag">Azure</span>
                        <span class="skill-tag">AWS</span>
                        <span class="skill-tag">Terraform</span>
                        <span class="skill-tag">GitHub Actions</span>
                        <span class="skill-tag">GitLab CI</span>
                        <span class="skill-tag">Monitoring</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3><i class="fas fa-mobile-alt"></i> Mobile & IoT</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">Flutter</span>
                        <span class="skill-tag">React Native</span>
                        <span class="skill-tag">Dart</span>
                        <span class="skill-tag">Firebase</span>
                        <span class="skill-tag">Raspberry Pi</span>
                        <span class="skill-tag">Arduino</span>
                        <span class="skill-tag">ESP32</span>
                        <span class="skill-tag">MQTT</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3><i class="fas fa-link"></i> Blockchain & Web3</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">Blockchain</span>
                        <span class="skill-tag">Solidity</span>
                        <span class="skill-tag">Web3.js</span>
                        <span class="skill-tag">Ethereum</span>
                        <span class="skill-tag">Smart Contracts</span>
                        <span class="skill-tag">DeFi</span>
                        <span class="skill-tag">NFTs</span>
                        <span class="skill-tag">Crypto</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h3><i class="fas fa-database"></i> Databases</h3>
                    <div class="skill-tags">
                        <span class="skill-tag">PostgreSQL</span>
                        <span class="skill-tag">MongoDB</span>
                        <span class="skill-tag">Redis</span>
                        <span class="skill-tag">Elasticsearch</span>
                        <span class="skill-tag">MySQL</span>
                        <span class="skill-tag">SQLite</span>
                        <span class="skill-tag">InfluxDB</span>
                        <span class="skill-tag">Neo4j</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="section" id="projects">
        <div class="container">
            <h2 class="section-title">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-robot"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Intelligent Document Processing Platform</h3>
                        <p class="project-description">Enterprise-grade document analysis and automation system using advanced RAG implementation with 85% reduction in processing time and 94% accuracy.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Django</span>
                            <span class="tech-tag">LangChain</span>
                            <span class="tech-tag">ChromaDB</span>
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">Kubernetes</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">
                                <i class="fas fa-external-link-alt"></i>
                                Live Demo
                            </a>
                            <a href="#" class="project-link">
                                <i class="fab fa-github"></i>
                                Source Code
                            </a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-thermometer-half"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Enterprise Climate Management</h3>
                        <p class="project-description">AI-driven HVAC optimization for commercial buildings achieving 35% energy reduction and 99.5% system uptime across 50+ buildings.</p>
                        <div class="project-tech">
                            <span class="tech-tag">TensorFlow</span>
                            <span class="tech-tag">ESP32</span>
                            <span class="tech-tag">Django</span>
                            <span class="tech-tag">Grafana</span>
                            <span class="tech-tag">LoRaWAN</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">
                                <i class="fas fa-external-link-alt"></i>
                                Case Study
                            </a>
                            <a href="#" class="project-link">
                                <i class="fas fa-chart-line"></i>
                                Analytics
                            </a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-industry"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Industrial IoT Analytics Platform</h3>
                        <p class="project-description">Predictive maintenance system with 60% reduction in unplanned downtime, monitoring 1000+ sensors with real-time anomaly detection.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Apache Spark</span>
                            <span class="tech-tag">Kafka</span>
                            <span class="tech-tag">MLflow</span>
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">Kubernetes</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">
                                <i class="fas fa-external-link-alt"></i>
                                Platform
                            </a>
                            <a href="#" class="project-link">
                                <i class="fas fa-download"></i>
                                Whitepaper
                            </a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-stethoscope"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Healthcare AI Diagnostics</h3>
                        <p class="project-description">Medical image analysis system with 96% diagnostic accuracy, reducing preliminary diagnosis time by 75% for hospital networks.</p>
                        <div class="project-tech">
                            <span class="tech-tag">PyTorch</span>
                            <span class="tech-tag">OpenCV</span>
                            <span class="tech-tag">DICOM</span>
                            <span class="tech-tag">FastAPI</span>
                            <span class="tech-tag">HIPAA</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">
                                <i class="fas fa-shield-alt"></i>
                                Secure Demo
                            </a>
                            <a href="#" class="project-link">
                                <i class="fas fa-file-medical"></i>
                                Research
                            </a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-coins"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Fintech AI Fraud Detection</h3>
                        <p class="project-description">Real-time fraud detection system for European bank with 94% reduction in false positives and sub-100ms transaction analysis.</p>
                        <div class="project-tech">
                            <span class="tech-tag">TensorFlow Serving</span>
                            <span class="tech-tag">Apache Kafka</span>
                            <span class="tech-tag">PostgreSQL</span>
                            <span class="tech-tag">Redis</span>
                            <span class="tech-tag">Microservices</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">
                                <i class="fas fa-lock"></i>
                                Secure Access
                            </a>
                            <a href="#" class="project-link">
                                <i class="fas fa-chart-bar"></i>
                                Performance
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="section" id="contact">
        <div class="container">
            <h2 class="section-title">Let's Build Something Amazing</h2>
            <div class="contact-content">
                <p class="contact-text">
                    Ready to transform your business with cutting-edge AI solutions? I'm available for strategic consulting, 
                    full-stack development, and innovative project partnerships. Let's discuss how we can bring your vision to life.
                </p>
                
                <div class="contact-links">
                    <a href="mailto:ibrahimaloui433@gmail.com" class="contact-link">
                        <i class="fas fa-envelope"></i>
                        Email Me
                    </a>
                    <a href="https://www.linkedin.com/in/ibrahim-aloui-4a9186226/" class="contact-link" target="_blank">
                        <i class="fab fa-linkedin"></i>
                        LinkedIn
                    </a>
                    <a href="https://github.com/IbrahimAL22" class="contact-link" target="_blank">
                        <i class="fab fa-github"></i>
                        GitHub
                    </a>
                    <a href="https://huggingface.co/IbrahimAL24" class="contact-link" target="_blank">
                        <i class="fas fa-robot"></i>
                        HuggingFace
                    </a>
                </div>

                <div style="margin-top: 60px; padding: 30px; background: rgba(100, 255, 218, 0.1); border-radius: 20px; border: 1px solid rgba(100, 255, 218, 0.3);">
                    <h3 style="color: var(--highlight); margin-bottom: 20px;">🚀 Current Availability</h3>
                    <p style="color: var(--gray); margin-bottom: 15px;">✅ Available for new projects and consulting opportunities</p>
                    <p style="color: var(--gray); margin-bottom: 15px;">⚡ Response time: Within 12 hours</p>
                    <p style="color: var(--gray);">🌍 Working with global clients across multiple timezones</p>
                </div>
            </div>
        </div>
    </section>

    <footer style="padding: 40px 0; text-align: center; border-top: 1px solid rgba(255, 255, 255, 0.1); margin-top: 100px;">
        <div class="container">
            <p style="color: var(--gray); margin-bottom: 20px;">
                "Engineering intelligence, delivering excellence, transforming possibilities into reality."
            </p>
            <div style="display: flex; justify-content: center; gap: 20px; flex-wrap: wrap; margin-bottom: 20px;">
                <span style="color: var(--highlight);">🇹🇳 Based in Tunisia</span>
                <span style="color: var(--highlight);">🌍 Serving Global Clients</span>
                <span style="color: var(--highlight);">🚀 Available for Strategic Projects</span>
            </div>
            <p style="color: var(--gray); font-size: 0.9rem;">
                © 2025 Ibrahim Aloui | Senior AI Engineer & Technical Consultant
            </p>
        </div>
    </footer>

    <script>
        // Loading Screen
        window.addEventListener('load', () => {
            setTimeout(() => {
                document.getElementById('loadingScreen').classList.add('fade-out');
            }, 1000);
        });

        // Typing Animation
        const typingTexts = [
            "🚀 Transforming Ideas into Intelligent Solutions",
            "💡 Building Tomorrow's Technology Today", 
            "⚡ Available for Strategic Projects & Consulting",
            "🤖 Pioneering AI Innovation & Excellence",
            "🌟 Creating Impactful Digital Experiences"
        ];
        
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        
        function typeText() {
            const currentText = typingTexts[textIndex];
            const typingElement = document.getElementById('typingText');
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }
            
            let typingSpeed = isDeleting ? 50 : 100;
            
            if (!isDeleting && charIndex === currentText.length) {
                typingSpeed = 2000;
                isDeleting = true;
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % typingTexts.length;
                typingSpeed = 500;
            }
            
            setTimeout(typeText, typingSpeed);
        }
        
        setTimeout(typeText, 2000);

        // Floating Particles
        function createParticle() {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + 'vw';
            particle.style.animationDuration = (Math.random() * 20 + 10) + 's';
            particle.style.animationDelay = Math.random() * 5 + 's';
            document.getElementById('particles').appendChild(particle);
            
            setTimeout(() => {
                particle.remove();
            }, 25000);
        }
        
        setInterval(createParticle, 300);

        // Scroll Progress
        window.addEventListener('scroll', () => {
            const winScroll = document.body.scrollTop || document.documentElement.scrollTop;
            const height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
            const scrolled = (winScroll / height) * 100;
            document.getElementById('scrollProgress').style.width = scrolled + '%';
        });

        // Intersection Observer for Sections
        const sections = document.querySelectorAll('.section');
        const navDots = document.querySelectorAll('.nav-dot');
        
        const observerOptions = {
            threshold: 0.3,
            rootMargin: '-20% 0px -20% 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                    
                    // Update navigation
                    const sectionId = entry.target.id;
                    navDots.forEach(dot => {
                        dot.classList.remove('active');
                        if (dot.dataset.section === sectionId) {
                            dot.classList.add('active');
                        }
                    });
                }
            });
        }, observerOptions);
        
        sections.forEach(section => {
            observer.observe(section);
        });

        // Navigation Dots Click
        navDots.forEach(dot => {
            dot.addEventListener('click', () => {
                const sectionId = dot.dataset.section;
                const section = document.getElementById(sectionId);
                section.scrollIntoView({ behavior: 'smooth' });
            });
        });

        // Smooth Scrolling for Links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });

        // Project Card Hover Effects
        const projectCards = document.querySelectorAll('.project-card');
        projectCards.forEach(card => {
            card.addEventListener('mouseenter', () => {
                card.style.transform = 'translateY(-20px) scale(1.02)';
            });
            
            card.addEventListener('mouseleave', () => {
                card.style.transform = 'translateY(0) scale(1)';
            });
        });

        // Skill Tags Animation
        const skillTags = document.querySelectorAll('.skill-tag');
        skillTags.forEach((tag, index) => {
            tag.style.animationDelay = `${index * 0.1}s`;
            tag.addEventListener('mouseenter', () => {
                tag.style.transform = 'scale(1.1) rotate(5deg)';
            });
            tag.addEventListener('mouseleave', () => {
                tag.style.transform = 'scale(1) rotate(0deg)';
            });
        });

        // Stats Animation
        function animateStats() {
            const statNumbers = document.querySelectorAll('.stat-number');
            statNumbers.forEach(stat => {
                const finalValue = stat.textContent;
                const isPercentage = finalValue.includes('%');
                const numericValue = parseInt(finalValue.replace(/[^\d]/g, ''));
                let currentValue = 0;
                const increment = numericValue / 50;
                
                const timer = setInterval(() => {
                    currentValue += increment;
                    if (currentValue >= numericValue) {
                        stat.textContent = finalValue;
                        clearInterval(timer);
                    } else {
                        stat.textContent = Math.floor(currentValue) + (isPercentage ? '%' : '+');
                    }
                }, 50);
            });
        }

        // Trigger stats animation when about section is visible
        const aboutSection = document.getElementById('about');
        const statsObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    animateStats();
                    statsObserver.unobserve(entry.target);
                }
            });
        }, { threshold: 0.5 });
        
        statsObserver.observe(aboutSection);

        // Enhanced Cursor Effect
        const cursor = document.createElement('div');
        cursor.style.cssText = `
            position: fixed;
            width: 20px;
            height: 20px;
            background: rgba(100, 255, 218, 0.8);
            border-radius: 50%;
            pointer-events: none;
            z-index: 9999;
            transform: translate(-50%, -50%);
            transition: transform 0.1s ease;
            mix-blend-mode: difference;
        `;
        document.body.appendChild(cursor);

        document.addEventListener('mousemove', (e) => {
            cursor.style.left = e.clientX + 'px';
            cursor.style.top = e.clientY + 'px';
        });

        // Add hover effects for interactive elements
        const interactiveElements = document.querySelectorAll('a, button, .project-card, .skill-tag, .nav-dot');
        interactiveElements.forEach(el => {
            el.addEventListener('mouseenter', () => {
                cursor.style.transform = 'translate(-50%, -50%) scale(2)';
                cursor.style.background = 'rgba(240, 147, 251, 0.8)';
            });
            el.addEventListener('mouseleave', () => {
                cursor.style.transform = 'translate(-50%, -50%) scale(1)';
                cursor.style.background = 'rgba(100, 255, 218, 0.8)';
            });
        });

        // Parallax Effect for Hero Section
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero-content');
            if (hero) {
                hero.style.transform = `translateY(${scrolled * 0.5}px)`;
            }
        });

        // Dynamic Background Color Change
        window.addEventListener('scroll', () => {
            const scrollPercent = window.pageYOffset / (document.documentElement.scrollHeight - window.innerHeight);
            const hue = scrollPercent * 360;
            document.documentElement.style.setProperty('--primary', `hsl(${hue}, 70%, 60%)`);
        });

        console.log('🚀 Ibrahim Aloui Portfolio Loaded Successfully!');
        console.log('💡 Built with cutting-edge web technologies');
        console.log('⚡ Ready to create amazing things together!');
    </script>
</body>
</html>-link-alt"></i>
                                Live Demo
                            </a>
                            <a href="#" class="project-link">
                                <i class="fab fa-github"></i>
                                Source Code
                            </a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-car"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">AI-Powered Smart Parking Ecosystem</h3>
                        <p class="project-description">Complete parking management solution with AI vision, blockchain payments, and 99.2% accuracy in space detection deployed in 15+ facilities.</p>
                        <div class="project-tech">
                            <span class="tech-tag">YOLOv8</span>
                            <span class="tech-tag">Solidity</span>
                            <span class="tech-tag">FastAPI</span>
                            <span class="tech-tag">Raspberry Pi</span>
                            <span class="tech-tag">Ethereum</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">
                                <i class="fas fa-external
