<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gabriel Aguilera, PhD</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --rimary-color: #4A90E2;
            --primary-dark: #357ABD;
            --secondary-color: #6C757D;
            --accent-color: #17A2B8;
            --text-primary: #2C3E50;
            --text-secondary: #6C757D;
            --bg-light: #F8F9FA;
            --bg-white: #FFFFFF;
            --shadow-sm: 0 2px 4px rgba(0, 0, 0, 0.05);
            --shadow-md: 0 4px 15px rgba(0, 0, 0, 0.1);
            --shadow-lg: 0 10px 30px rgba(0, 0, 0, 0.15);
            --border-radius: 12px;
            --transition: all 0.3s ease;
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: var(--text-primary);
            scroll-behavior: smooth;
        }

        /* Header */
        .header {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
            box-shadow: var(--shadow-sm);
            transition: var(--transition);
        }

        .header.scrolled {
            background: rgba(255, 255, 255, 0.98);
            box-shadow: var(--shadow-md);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
            text-decoration: none;
            transition: var(--transition);
        }

        .logo:hover {
            color: var(--primary-dark);
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-link {
            text-decoration: none;
            color: var(--text-primary);
            font-weight: 500;
            position: relative;
            transition: var(--transition);
        }

        .nav-link:hover {
            color: var(--primary-color);
        }

        .nav-link::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary-color);
            transition: width 0.3s ease;
        }

        .nav-link:hover::after {
            width: 100%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--text-primary);
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--bg-light) 0%, #E3F2FD 100%);
            padding: 8rem 0 4rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1000 100" fill="%23ffffff" opacity="0.1"><polygon points="1000,100 1000,0 0,0 0,100"/></svg>');
            background-size: cover;
        }

        .profile-img {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            object-fit: cover;
            border: 6px solid var(--bg-white);
            box-shadow: var(--shadow-lg);
            margin-bottom: 2rem;
            transition: var(--transition);
        }

        .profile-img:hover {
            transform: scale(1.05);
        }

        .hero h1 {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero .subtitle {
            font-size: 1.5rem;
            color: var(--text-secondary);
            margin-bottom: 1.5rem;
            font-weight: 400;
        }

        .hero .description {
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto 2rem;
            color: var(--text-secondary);
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 1rem 2rem;
            border-radius: var(--border-radius);
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            border: 2px solid transparent;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .btn-primary {
            background: var(--primary-color);
            color: white;
        }

        .btn-primary:hover {
            background: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: var(--shadow-md);
        }

        .btn-outline {
            background: transparent;
            color: var(--primary-color);
            border-color: var(--primary-color);
        }

        .btn-outline:hover {
            background: var(--primary-color);
            color: white;
            transform: translateY(-2px);
        }

        /* Section Styles */
        .section {
            padding: 5rem 0;
        }

        .section:nth-child(even) {
            background: var(--bg-light);
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--text-primary);
        }

        .section-subtitle {
            text-align: center;
            font-size: 1.1rem;
            color: var(--text-secondary);
            max-width: 600px;
            margin: 0 auto 3rem;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 4rem;
            align-items: center;
        }

        .about-img {
            width: 100%;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow-md);
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
        }

        .about-text p {
            margin-bottom: 1.5rem;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .skill-item {
            background: var(--bg-white);
            padding: 2rem;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow-sm);
            transition: var(--transition);
        }

        .skill-item:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-md);
        }

        .skill-header {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1rem;
        }

        .skill-icon {
            font-size: 2rem;
            color: var(--primary-color);
        }

        .skill-name {
            font-size: 1.2rem;
            font-weight: 600;
        }

        .progress-bar {
            width: 100%;
            height: 8px;
            background: var(--bg-light);
            border-radius: 4px;
            overflow: hidden;
            margin-top: 0.5rem;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary-color), var(--accent-color));
            border-radius: 4px;
            transition: width 2s ease-in-out;
            width: 0;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: var(--bg-white);
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--shadow-sm);
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-lg);
        }

        .project-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 1rem;
            color: var(--text-primary);
        }

        .project-description {
            color: var(--text-secondary);
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .tech-tag {
            background: var(--bg-light);
            color: var(--primary-color);
            padding: 0.25rem 0.75rem;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 500;
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        .project-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.5rem 1rem;
            background: var(--primary-color);
            color: white;
            text-decoration: none;
            border-radius: 6px;
            font-weight: 500;
            transition: var(--transition);
        }

        .project-link:hover {
            background: var(--primary-dark);
        }

        .project-link.secondary {
            background: var(--text-secondary);
        }

        .project-link.secondary:hover {
            background: var(--text-primary);
        }

        /* Experience Section */
        .timeline {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 2px;
            background: var(--primary-color);
            transform: translateX(-50%);
        }

        .timeline-item {
            margin-bottom: 3rem;
            position: relative;
        }

        .timeline-content {
            background: var(--bg-white);
            padding: 2rem;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow-sm);
            width: calc(50% - 2rem);
            position: relative;
        }

        .timeline-item:nth-child(odd) .timeline-content {
            margin-left: auto;
        }

        .timeline-content::before {
            content: '';
            position: absolute;
            top: 2rem;
            width: 0;
            height: 0;
            border: 10px solid transparent;
        }

        .timeline-item:nth-child(odd) .timeline-content::before {
            left: -20px;
            border-right-color: var(--bg-white);
        }

        .timeline-item:nth-child(even) .timeline-content::before {
            right: -20px;
            border-left-color: var(--bg-white);
        }

        .timeline-marker {
            position: absolute;
            left: 50%;
            top: 2rem;
            width: 16px;
            height: 16px;
            background: var(--primary-color);
            border: 4px solid var(--bg-white);
            border-radius: 50%;
            transform: translateX(-50%);
            z-index: 10;
        }

        .timeline-date {
            color: var(--primary-color);
            font-weight: 600;
            margin-bottom: 0.5rem;
        }

        .timeline-title {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
        }

        .timeline-company {
            color: var(--text-secondary);
            font-weight: 500;
            margin-bottom: 1rem;
        }

        /* Contact Section */
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
        }

        .contact-form {
            background: var(--bg-white);
            padding: 2rem;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow-sm);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: var(--text-primary);
        }

        .form-input {
            width: 100%;
            padding: 0.75rem;
            border: 2px solid var(--bg-light);
            border-radius: 6px;
            font-size: 1rem;
            transition: var(--transition);
        }

        .form-input:focus {
            outline: none;
            border-color: var(--primary-color);
        }

        .form-textarea {
            resize: vertical;
            min-height: 120px;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1.5rem;
            background: var(--bg-white);
            border-radius: var(--border-radius);
            box-shadow: var(--shadow-sm);
        }

        .contact-icon {
            font-size: 1.5rem;
            color: var(--primary-color);
            width: 50px;
            text-align: center;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            justify-content: center;
            margin-top: 2rem;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background: var(--primary-color);
            color: white;
            border-radius: 50%;
            text-decoration: none;
            transition: var(--transition);
        }

        .social-link:hover {
            background: var(--primary-dark);
            transform: translateY(-3px);
        }

        /* Footer */
        .footer {
            background: var(--text-primary);
            color: white;
            text-align: center;
            padding: 2rem 0;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .container {
                padding: 0 1rem;
            }

            .nav-menu {
                display: none;
            }

            .mobile-menu-btn {
                display: block;
            }

            .hero {
                padding: 6rem 0 3rem;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero .subtitle {
                font-size: 1.2rem;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }

            .about-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .timeline::before {
                left: 2rem;
            }

            .timeline-content {
                width: calc(100% - 4rem);
                margin-left: 4rem !important;
            }

            .timeline-content::before {
                left: -20px !important;
                border-right-color: var(--bg-white) !important;
                border-left-color: transparent !important;
            }

            .timeline-marker {
                left: 2rem;
                transform: translateX(-50%);
            }

            .contact-content {
                grid-template-columns: 1fr;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Animation Classes */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Progress Bar Animation */
        .progress-fill.animate {
            animation: progressAnimation 2s ease-in-out forwards;
        }

        @keyframes progressAnimation {
            from {
                width: 0;
            }
            to {
                width: var(--progress-width);
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header" id="header">
        <div class="container">
            <div class="header-content">
                <a href="#home" class="logo">Gabriel Aguilera, PhD</a>
                <nav>
                    <ul class="nav-menu">
                        <li><a href="#home" class="nav-link">Inicio</a></li>
                        <li><a href="#about" class="nav-link">Acerca de</a></li>
                        <li><a href="#skills" class="nav-link">Habilidades</a></li>
                        <li><a href="#projects" class="nav-link">Proyectos</a></li>
                        <li><a href="#experience" class="nav-link">Experiencia</a></li>
                        <li><a href="#contact" class="nav-link">Contacto</a></li>
                    </ul>
                </nav>
                <button class="mobile-menu-btn">
                    <i class="fas fa-bars"></i>
                </button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="fade-in">
                <img src="https://placehold.co/400x400/4A90E2/ffffff?text=Tu+Foto" alt="Tu Nombre" class="profile-img">
                <h1>Dr. José Gabriel Aguilera González</h1>
                <p class="subtitle">Doctor en Sistemas Computacionales</p>
                <p class="description">
                    Soy Ingeniero en Comunicaciones y Electrónica, con Maestría en Ingeniería Eléctrica y Doctorado en Sistemas Computacionales.
                    Especializado en Inteligencia Artificial, desarrollando proyectos con Redes Neuronales Artificiales, Redes Neuronales Concolucionales de Aprendizaje Profundo, Desarrollo Electrónico.
                    Cuento con amplia experiencia en el sector educativo, en la gesti{on y organización de equipos de alto desempeño; comprometido con la excelencia educativa de las instituciones en las que me desarrollo, pero también con la mejora contínua de la Educación Superior del País.
                    
                </p>
                <div class="cta-buttons">
                    <a href="#projects" class="btn btn-primary">
                        <i class="fas fa-eye"></i>
                        Ver Proyectos
                    </a>
                    <a href="#contact" class="btn btn-outline">
                        <i class="fas fa-paper-plane"></i>
                        Contactar
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="section" id="about">
        <div class="container">
            <div class="fade-in">
                <h2 class="section-title">Acerca de Mí</h2>
                <p class="section-subtitle">Conoce más sobre mi trayectoria y pasión por el desarrollo</p>
                
                <div class="about-content">
                    <img src="https://placehold.co/500x600/E3F2FD/4A90E2?text=Desarrollando" alt="Trabajando" class="about-img">
                    <div class="about-text">
                        <p>
                            Con más de 5 años de experiencia en desarrollo web, he tenido la oportunidad de trabajar 
                            en una amplia variedad de proyectos, desde aplicaciones web empresariales hasta 
                            plataformas e-commerce de alto tráfico.
                        </p>
                        <p>
                            Mi enfoque se centra en escribir código limpio, escalable y mantenible, siempre 
                            buscando las mejores prácticas y tecnologías emergentes. Me apasiona resolver 
                            problemas complejos y transformar ideas en soluciones digitales efectivas.
                        </p>
                        <p>
                            Cuando no estoy programando, disfruto aprendiendo nuevas tecnologías, contribuyendo 
                            a proyectos de código abierto y compartiendo conocimientos con la comunidad de desarrolladores.
                        </p>
                        <a href="#contact" class="btn btn-primary">
                            <i class="fas fa-download"></i>
                            Descargar CV
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section class="section" id="skills">
        <div class="container">
            <div class="fade-in">
                <h2 class="section-title">Habilidades Técnicas</h2>
                <p class="section-subtitle">Tecnologías y herramientas que domino</p>
                
                <div class="skills-grid">
                    <div class="skill-item">
                        <div class="skill-header">
                            <i class="fab fa-js-square skill-icon"></i>
                            <span class="skill-name">JavaScript</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill" data-width="90%"></div>
                        </div>
                    </div>

                    <div class="skill-item">
                        <div class="skill-header">
                            <i class="fab fa-react skill-icon"></i>
                            <span class="skill-name">React</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill" data-width="85%"></div>
                        </div>
                    </div>

                    <div class="skill-item">
                        <div class="skill-header">
                            <i class="fab fa-node-js skill-icon"></i>
                            <span class="skill-name">Node.js</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill" data-width="80%"></div>
                        </div>
                    </div>

                    <div class="skill-item">
                        <div class="skill-header">
                            <i class="fab fa-python skill-icon"></i>
                            <span class="skill-name">Python</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill" data-width="75%"></div>
                        </div>
                    </div>

                    <div class="skill-item">
                        <div class="skill-header">
                            <i class="fas fa-database skill-icon"></i>
                            <span class="skill-name">MongoDB</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill" data-width="85%"></div>
                        </div>
                    </div>

                    <div class="skill-item">
                        <div class="skill-header">
                            <i class="fab fa-aws skill-icon"></i>
                            <span class="skill-name">AWS</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill" data-width="70%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="section" id="projects">
        <div class="container">
            <div class="fade-in">
                <h2 class="section-title">Mis Proyectos</h2>
                <p class="section-subtitle">Una selección de mis trabajos más destacados</p>
                
                <div class="projects-grid">
                    <div class="project-card">
                        <img src="https://placehold.co/400x200/4A90E2/ffffff?text=E-commerce+App" alt="E-commerce App" class="project-img">
                        <div class="project-content">
                            <h3 class="project-title">Tienda Online Moderna</h3>
                            <p class="project-description">
                                Aplicación de comercio electrónico completa con carrito de compras, 
                                sistema de pagos y panel de administración.
                            </p>
                            <div class="project-tech">
                                <span class="tech-tag">React</span>
                                <span class="tech-tag">Node.js</span>
                                <span class="tech-tag">MongoDB</span>
                                <span class="tech-tag">Stripe</span>
                            </div>
                            <div class="project-links">
                                <a href="#" class="project-link">
                                    <i class="fab fa-github"></i>
                                    Código
                                </a>
                                <a href="#" class="project-link secondary">
                                    <i class="fas fa-external-link-alt"></i>
                                    Demo
                                </a>
                            </div>
                        </div>
                    </div>

                    <div class="project-card">
                        <img src="https://placehold.co/400x200/17A2B8/ffffff?text=Task+Manager" alt="Task Manager" class="project-img">
                        <div class="project-content">
                            <h3 class="project-title">Gestor de Tareas</h3>
                            <p class="project-description">
                                Aplicación web para gestión de proyectos con funcionalidades de 
                                colaboración en tiempo real y seguimiento de progreso.
                            </p>
                            <div class="project-tech">
                                <span class="tech-tag">Vue.js</span>
                                <span class="tech-tag">Express</span>
                                <span class="tech-tag">Socket.io</span>
                                <span class="tech-tag">PostgreSQL</span>
                            </div>
                            <div class="project-links">
                                <a href="#" class="project-link">
                                    <i class="fab fa-github"></i>
                                    Código
                                </a>
                                <a href="#" class="project-link secondary">
                                    <i class="fas fa-external-link-alt"></i>
                                    Demo
                                </a>
                            </div>
                        </div>
                    </div>

                    <div class="project-card">
                        <img src="https://placehold.co/400x200/6C757D/ffffff?text=Weather+App" alt="Weather App" class="project-img">
                        <div class="project-content">
                            <h3 class="project-title">App del Clima</h3>
                            <p class="project-description">
                                Aplicación móvil híbrida que muestra pronósticos meteorológicos 
                                con geolocalización y notificaciones push.
                            </p>
                            <div class="project-tech">
                                <span class="tech-tag">React Native</span>
                                <span class="tech-tag">Firebase</span>
                                <span class="tech-tag">OpenWeather API</span>
                                <span class="tech-tag">Redux</span>
                            </div>
                            <div class="project-links">
                                <a href="#" class="project-link">
                                    <i class="fab fa-github"></i>
                                    Código
                                </a>
                                <a href="#" class="project-link secondary">
                                    <i class="fas fa-external-link-alt"></i>
                                    Demo
                                </a>
