<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Full-Stack Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a1a 100%);
            color: #ffffff;
            line-height: 1.6;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        .header {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50px;
            left: 50%;
            transform: translateX(-50%);
            width: 200px;
            height: 4px;
            background: linear-gradient(90deg, transparent, #00ff88, transparent);
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.4; }
            50% { opacity: 1; }
        }

        .title {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, #ffffff 0%, #00ff88 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: slideInDown 1s ease-out;
        }

        @keyframes slideInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .subtitle {
            font-size: 1.2rem;
            color: #cccccc;
            margin-bottom: 2rem;
            animation: fadeIn 1.5s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .tech-category {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(0, 255, 136, 0.2);
            border-radius: 15px;
            padding: 2rem;
            transition: all 0.3s ease;
            animation: slideInUp 1s ease-out;
            animation-fill-mode: both;
            backdrop-filter: blur(10px);
        }

        .tech-category:nth-child(1) { animation-delay: 0.2s; }
        .tech-category:nth-child(2) { animation-delay: 0.4s; }
        .tech-category:nth-child(3) { animation-delay: 0.6s; }
        .tech-category:nth-child(4) { animation-delay: 0.8s; }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .tech-category:hover {
            transform: translateY(-5px);
            border-color: #00ff88;
            box-shadow: 0 10px 30px rgba(0, 255, 136, 0.2);
        }

        .category-title {
            font-size: 1.4rem;
            font-weight: 600;
            color: #00ff88;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .category-icon {
            width: 24px;
            height: 24px;
            animation: rotate 4s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .tech-list {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem;
        }

        .tech-item {
            background: rgba(0, 255, 136, 0.1);
            border: 1px solid rgba(0, 255, 136, 0.3);
            padding: 0.5rem 1rem;
            border-radius: 25px;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .tech-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 255, 136, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .tech-item:hover::before {
            left: 100%;
        }

        .tech-item:hover {
            background: rgba(0, 255, 136, 0.2);
            transform: scale(1.05);
            border-color: #00ff88;
        }

        .experience-section {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(0, 255, 136, 0.2);
            border-radius: 15px;
            padding: 2.5rem;
            margin-bottom: 2rem;
            backdrop-filter: blur(10px);
            animation: fadeInScale 1.2s ease-out;
        }

        @keyframes fadeInScale {
            from {
                opacity: 0;
                transform: scale(0.95);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .experience-title {
            font-size: 2rem;
            color: #00ff88;
            margin-bottom: 2rem;
            text-align: center;
            position: relative;
        }

        .experience-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 2px;
            background: linear-gradient(90deg, transparent, #00ff88, transparent);
        }

        .job-title {
            font-size: 1.3rem;
            font-weight: 600;
            color: #ffffff;
            margin-bottom: 0.5rem;
        }

        .company-info {
            color: #00ff88;
            font-size: 1rem;
            margin-bottom: 1.5rem;
        }

        .achievements {
            list-style: none;
        }

        .achievements li {
            margin-bottom: 1rem;
            padding-left: 2rem;
            position: relative;
            color: #cccccc;
            line-height: 1.6;
        }

        .achievements li::before {
            content: '▶';
            position: absolute;
            left: 0;
            color: #00ff88;
            font-size: 0.8rem;
            animation: blink 2s ease-in-out infinite;
        }

        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0.3; }
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-top: 3rem;
        }

        .stat-item {
            text-align: center;
            background: rgba(0, 255, 136, 0.1);
            border: 1px solid rgba(0, 255, 136, 0.3);
            border-radius: 15px;
            padding: 1.5rem;
            transition: all 0.3s ease;
        }

        .stat-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 255, 136, 0.2);
        }

        .stat-number {
            font-size: 2rem;
            font-weight: 700;
            color: #00ff88;
            display: block;
        }

        .stat-label {
            color: #cccccc;
            font-size: 0.9rem;
        }

        .floating-particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: #00ff88;
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% {
                opacity: 0;
                transform: translateY(100vh) translateX(0);
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-10px) translateX(10px);
            }
        }

        @media (max-width: 768px) {
            .title {
                font-size: 2.5rem;
            }
            
            .tech-grid {
                grid-template-columns: 1fr;
            }
            
            .container {
                padding: 1rem;
            }
        }
    </style>
</head>
<body>
    <div class="floating-particles" id="particles"></div>
    
    <div class="container">
        <header class="header">
            <h1 class="title">Full-Stack Developer</h1>
            <p class="subtitle">Criando soluções digitais inovadoras com tecnologias modernas</p>
        </header>

        <div class="tech-grid">
            <div class="tech-category">
                <h3 class="category-title">
                    <svg class="category-icon" viewBox="0 0 24 24" fill="#00ff88">
                        <path d="M12 2L2 7v10c0 5.55 3.84 9.739 9 11 5.16-1.261 9-5.45 9-11V7l-10-5z"/>
                    </svg>
                    Front-End
                </h3>
                <div class="tech-list">
                    <span class="tech-item">HTML5</span>
                    <span class="tech-item">CSS3</span>
                    <span class="tech-item">JavaScript</span>
                    <span class="tech-item">TypeScript</span>
                    <span class="tech-item">React.js</span>
                    <span class="tech-item">Next.js</span>
                    <span class="tech-item">Tailwind CSS</span>
                    <span class="tech-item">Framer Motion</span>
                </div>
            </div>

            <div class="tech-category">
                <h3 class="category-title">
                    <svg class="category-icon" viewBox="0 0 24 24" fill="#00ff88">
                        <path d="M4 6h16v2H4zm0 5h16v2H4zm0 5h16v2H4z"/>
                    </svg>
                    Back-End
                </h3>
                <div class="tech-list">
                    <span class="tech-item">Node.js</span>
                    <span class="tech-item">Express.js</span>
                    <span class="tech-item">API RESTful</span>
                    <span class="tech-item">Webhooks</span>
                    <span class="tech-item">OAuth2</span>
                </div>
            </div>

            <div class="tech-category">
                <h3 class="category-title">
                    <svg class="category-icon" viewBox="0 0 24 24" fill="#00ff88">
                        <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                    </svg>
                    Database & Estado
                </h3>
                <div class="tech-list">
                    <span class="tech-item">MongoDB</span>
                    <span class="tech-item">MySQL</span>
                    <span class="tech-item">IndexedDB</span>
                    <span class="tech-item">React Hooks</span>
                    <span class="tech-item">Zustand</span>
                </div>
            </div>

            <div class="tech-category">
                <h3 class="category-title">
                    <svg class="category-icon" viewBox="0 0 24 24" fill="#00ff88">
                        <path d="M22.46 6c-.77.35-1.6.58-2.46.69.88-.53 1.56-1.37 1.88-2.38-.83.5-1.75.85-2.72 1.05C18.37 4.5 17.26 4 16 4c-2.35 0-4.27 1.92-4.27 4.29 0 .34.04.67.11.98C8.28 9.09 5.11 7.38 3 4.79c-.37.63-.58 1.37-.58 2.15 0 1.49.75 2.81 1.91 3.56-.71 0-1.37-.2-1.95-.5v.03c0 2.08 1.48 3.82 3.44 4.21a4.22 4.22 0 0 1-1.93.07 4.28 4.28 0 0 0 4 2.98 8.521 8.521 0 0 1-5.33 1.84c-.34 0-.68-.02-1.02-.06C3.44 20.29 5.7 21 8.12 21 16 21 20.33 14.46 20.33 8.79c0-.19 0-.37-.01-.56.84-.6 1.56-1.36 2.14-2.23z"/>
                    </svg>
                    Dev Tools & Cloud
                </h3>
                <div class="tech-list">
                    <span class="tech-item">Git</span>
                    <span class="tech-item">GitHub</span>
                    <span class="tech-item">Docker</span>
                    <span class="tech-item">Google Cloud</span>
                    <span class="tech-item">Insomnia</span>
                    <span class="tech-item">Swagger</span>
                </div>
            </div>
        </div>

        <div class="experience-section">
            <h2 class="experience-title">Experiência Atual</h2>
            
            <div class="job-title">Desenvolvedor Full-Stack</div>
            <div class="company-info">waTools • Agosto 2024 - Presente • Minas Gerais, Brasil</div>
            
            <ul class="achievements">
                <li>Desenvolvimento de sistema de checkout de alta demanda acessado por milhares de usuários diariamente</li>
                <li>Integração de webhooks com Asaas para automação de processos de cobrança</li>
                <li>Criação de APIs REST de alta performance em Node.js/TypeScript</li>
                <li>Desenvolvimento de interfaces responsivas com React.js, Next.js e Tailwind CSS</li>
                <li>Otimização de performance: migração do Context API para Zustand resultou em +50% de melhoria</li>
                <li>Arquitetura de bancos de dados escaláveis com MongoDB</li>
                <li>Integração completa com Google Cloud Platform, OAuth2 e APIs do Google</li>
                <li>Sistema de filtragem de webhooks e roteamento de mensagens</li>
            </ul>
        </div>

        <div class="stats">
            <div class="stat-item">
                <span class="stat-number">+50%</span>
                <span class="stat-label">Melhoria Performance</span>
            </div>
            <div class="stat-item">
                <span class="stat-number">1000s</span>
                <span class="stat-label">Usuários Diários</span>
            </div>
            <div class="stat-item">
                <span class="stat-number">100%</span>
                <span class="stat-label">APIs Escaláveis</span>
            </div>
            <div class="stat-item">
                <span class="stat-number">24/7</span>
                <span class="stat-label">Sistemas Ativos</span>
            </div>
        </div>
    </div>

    <script>
        // Criar partículas flutuantes
        function createParticles() {
            const particleContainer = document.getElementById('particles');
            const numParticles = 50;

            for (let i = 0; i < numParticles; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 3 + 4) + 's';
                particleContainer.appendChild(particle);
            }
        }

        // Animação de digitação para o título
        function typeWriter(element, text, speed = 100) {
            let i = 0;
            element.innerHTML = '';
            function type() {
                if (i < text.length) {
                    element.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, speed);
                }
            }
            type();
        }

        // Inicializar animações
        document.addEventListener('DOMContentLoaded', function() {
            createParticles();
            
            // Animação de hover para tech items
            const techItems = document.querySelectorAll('.tech-item');
            techItems.forEach(item => {
                item.addEventListener('mouseenter', function() {
                    this.style.transform = 'scale(1.05) rotateZ(2deg)';
                });
                
                item.addEventListener('mouseleave', function() {
                    this.style.transform = 'scale(1) rotateZ(0deg)';
                });
            });

            // Scroll reveal para elementos
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };

            const observer = new IntersectionObserver(function(entries) {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, observerOptions);

            // Observar elementos para animação de scroll
            document.querySelectorAll('.tech-category, .experience-section, .stat-item').forEach(el => {
                observer.observe(el);
            });
        });

        // Efeito paralaxe suave
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const particles = document.querySelectorAll('.particle');
            
            particles.forEach((particle, index) => {
                const speed = (index % 3 + 1) * 0.5;
                particle.style.transform = `translateY(${scrolled * speed}px)`;
            });
        });
    </script>
</body>
</html>
