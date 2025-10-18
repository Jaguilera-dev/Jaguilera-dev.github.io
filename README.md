<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Portfolio - GitHub Pages</title>
    <meta name="description" content="Portfolio profesional - Desarrollador Web">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #6366f1;
            --primary-dark: #4f46e5;
            --secondary-color: #f8fafc;
            --text-primary: #1e293b;
            --text-secondary: #64748b;
            --white: #ffffff;
            --gray-100: #f1f5f9;
            --gray-200: #e2e8f0;
            --gray-800: #1e293b;
            --shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
            --shadow-lg: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
            --border-radius: 12px;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            color: var(--text-primary);
            background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
            overflow-x: hidden;
        }

        /* Sidebar Styles */
        .sidebar {
            position: fixed;
            left: 0;
            top: 0;
            width: 280px;
            height: 100vh;
            background: linear-gradient(180deg, var(--white) 0%, var(--gray-100) 100%);
            padding: 2rem;
            box-shadow: var(--shadow-lg);
            z-index: 1000;
            transition: var(--transition);
        }

        .logo {
            display: flex;
            align-items: center;
            margin-bottom: 2rem;
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary-color);
        }

        .logo::before {
            content: "⚡";
            margin-right: 0.5rem;
            font-size: 1.8rem;
        }

        .nav-menu {
            list-style: none;
        }

        .nav-item {
            margin-bottom: 0.5rem;
        }

        .nav-link {
            display: flex;
            align-items: center;
            padding: 1rem;
            color: var(--text-secondary);
            text-decoration: none;
            border-radius: var(--border-radius);
            transition: var(--transition);
            font-weight: 500;
            position: relative;
            overflow: hidden;
        }

        .nav-link::before {
            content: "";
            position: absolute;
            left: 0;
            top: 0;
            width: 0;
            height: 100%;
            background: linear-gradient(90deg, var(--primary-color), var(--primary-dark));
            transition: var(--transition);
            z-index: -1;
        }

        .nav-link:hover::before,
        .nav-link.active::before {
            width: 100%;
        }

        .nav-link:hover,
        .nav-link.active {
            color: var(--white);
            transform: translateX(5px);
        }

        .nav-icon {
            margin-right: 0.75rem;
            font-size: 1.2rem;
        }

        /* Main Content */
        .main-content {
            margin-left: 280px;
            min-height: 100vh;
            transition: var(--transition);
        }

        /* Profile Section */
        .profile-section {
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--primary-dark) 100%);
            padding: 4rem 2rem;
            text-align: center;
            color: var(--white);
            position: relative;
            overflow: hidden;
        }

        .profile-section::before {
            content: "";
            position: absolute;
            top: -50%;
            right: -50%;
            width: 100%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .profile-photo {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            margin: 0 auto 2rem;
            border: 6px solid var(--white);
            box-shadow: var(--shadow-lg);
            transition: var(--transition);
            position: relative;
            z-index: 1;
        }

        .profile-photo:hover {
            transform: scale(1.05) rotate(5deg);
            box-shadow: 0 30px 60px -12px rgba(0, 0, 0, 0.5);
        }

        .profile-title {
            font-size: 3rem;
            font-weight: 800;
            margin-bottom: 1rem;
            position: relative;
            z-index: 1;
        }

        .profile-subtitle {
            font-size: 1.5rem;
            font-weight: 300;
            opacity: 0.9;
            position: relative;
            z-index: 1;
        }

        /* Content Area */
        .content-area {
            padding: 3rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .content-section {
            background: var(--white);
            padding: 3rem;
            margin-bottom: 2rem;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .content-section:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            color: var(--text-primary);
            position: relative;
        }

        .section-title::after {
            content: "";
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 60px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary-color), var(--primary-dark));
            border-radius: 2px;
        }

        .section-text {
            font-size: 1.1rem;
            color: var(--text-secondary);
            line-height: 1.8;
            margin-bottom: 1.5rem;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .skill-card {
            padding: 1.5rem;
            background: var(--gray-100);
            border-radius: var(--border-radius);
            text-align: center;
            transition: var(--transition);
        }

        .skill-card:hover {
            background: var(--primary-color);
            color: var(--white);
            transform: translateY(-3px);
        }

        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            padding: 1rem;
            background: var(--gray-100);
            border-radius: var(--border-radius);
            transition: var(--transition);
        }

        .contact-item:hover {
            background: var(--primary-color);
            color: var(--white);
        }

        .contact-icon {
            margin-right: 1rem;
            font-size: 1.5rem;
            color: var(--primary-color);
        }

        .contact-item:hover .contact-icon {
            color: var(--white);
        }

        /* Mobile Menu Toggle */
        .mobile-toggle {
            display: none;
            position: fixed;
            top: 1rem;
            left: 1rem;
            z-index: 1001;
            background: var(--primary-color);
            color: var(--white);
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            font-size: 1.5rem;
            cursor: pointer;
            box-shadow: var(--shadow);
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .mobile-toggle {
                display: block;
            }

            .sidebar {
                transform: translateX(-100%);
                width: 100%;
                max-width: 300px;
            }

            .sidebar.active {
                transform: translateX(0);
            }

            .main-content {
                margin-left: 0;
            }

            .profile-title {
                font-size: 2rem;
            }

            .profile-subtitle {
                font-size: 1.2rem;
            }

            .profile-photo {
                width: 150px;
                height: 150px;
            }

            .content-area {
                padding: 1.5rem;
            }

            .content-section {
                padding: 2rem;
            }

            .section-title {
                font-size: 2rem;
            }
        }

        /* Scroll behavior */
        html {
            scroll-behavior: smooth;
        }

        /* Loading animation for images */
        .profile-photo {
            background: linear-gradient(135deg, var(--gray-200) 0%, var(--gray-100) 100%);
        }
    </style>
</head>
<body>
    <!-- Mobile Menu Toggle -->
    <button class="mobile-toggle" id="mobileToggle">
        ☰
    </button>

    <!-- Sidebar Navigation -->
    <nav class="sidebar" id="sidebar">
        <div class="logo">
            Mi Portfolio
        </div>
        
        <ul class="nav-menu">
            <li class="nav-item">
                <a href="#home" class="nav-link active">
                    <span class="nav-icon">🏠</span>
                    Home
                </a>
            </li>
            <li class="nav-item">
                <a href="#sobre-mi" class="nav-link">
                    <span class="nav-icon">👤</span>
                    Sobre mí
                </a>
            </li>
            <li class="nav-item">
                <a href="#proyectos" class="nav-link">
                    <span class="nav-icon">💼</span>
                    Proyectos
                </a>
            </li>
            <li class="nav-item">
                <a href="#contacto" class="nav-link">
                    <span class="nav-icon">📧</span>
                    Contacto
                </a>
            </li>
        </ul>
    </nav>

    <!-- Main Content -->
    <main class="main-content">
        <!-- Profile Section -->
        <section id="home" class="profile-section">
            <img src="https://placehold.co/400x400/6366f1/ffffff?text=Tu+Foto" alt="Foto de perfil" class="profile-photo">
            <h1 class="profile-title">Tu Nombre</h1>
            <p class="profile-subtitle">Desarrollador Web Full Stack</p>
        </section>

        <!-- Content Area -->
        <div class="content-area">
            <!-- Sobre mí Section -->
            <section id="sobre-mi" class="content-section">
                <h2 class="section-title">Sobre mí</h2>
                <p class="section-text">
                    ¡Hola! Soy un desarrollador web apasionado con experiencia en crear aplicaciones web modernas y atractivas. 
                    Me especializo en tecnologías front-end y back-end, siempre buscando aprender nuevas herramientas y metodologías 
                    para crear mejores experiencias de usuario.
                </p>
                <p class="section-text">
                    Mi enfoque se centra en escribir código limpio, mantenible y escalable. Disfruto trabajando en equipo y 
                    colaborando en proyectos desafiantes que me permitan crecer profesionalmente.
                </p>

                <div class="skills-grid">
                    <div class="skill-card">
                        <h3>Frontend</h3>
                        <p>HTML, CSS, JavaScript, React, Vue.js</p>
                    </div>
                    <div class="skill-card">
                        <h3>Backend</h3>
                        <p>Node.js, Python, PHP, Bases de datos</p>
                    </div>
                    <div class="skill-card">
                        <h3>Herramientas</h3>
                        <p>Git, Docker, VS Code, Figma</p>
                    </div>
                    <div class="skill-card">
                        <h3>Metodologías</h3>
                        <p>Agile, Scrum, TDD, Clean Code</p>
                    </div>
                </div>
            </section>

            <!-- Proyectos Section -->
            <section id="proyectos" class="content-section">
                <h2 class="section-title">Proyectos</h2>
                <p class="section-text">
                    Aquí puedes encontrar algunos de mis proyectos más destacados. Cada uno representa un desafío diferente 
                    y me ha permitido aprender y aplicar nuevas tecnologías y conceptos.
                </p>

                <div class="skills-grid">
                    <div class="skill-card">
                        <h3>Proyecto 1</h3>
                        <p>Aplicación web desarrollada con React y Node.js. Incluye autenticación, base de datos y API REST.</p>
                    </div>
                    <div class="skill-card">
                        <h3>Proyecto 2</h3>
                        <p>E-commerce completo con carrito de compras, pasarela de pagos y panel de administración.</p>
                    </div>
                    <div class="skill-card">
                        <h3>Proyecto 3</h3>
                        <p>Dashboard analítico con visualización de datos en tiempo real usando D3.js y WebSockets.</p>
                    </div>
                </div>
            </section>

            <!-- Contacto Section -->
            <section id="contacto" class="content-section">
                <h2 class="section-title">Contacto</h2>
                <p class="section-text">
                    ¿Tienes algún proyecto en mente o quieres colaborar? No dudes en contactarme. 
                    Estoy siempre abierto a nuevas oportunidades y desafíos.
                </p>

                <div class="contact-info">
                    <div class="contact-item">
                        <span class="contact-icon">📧</span>
                        <div>
                            <strong>Email</strong><br>
                            tu.email@ejemplo.com
                        </div>
                    </div>
                    <div class="contact-item">
                        <span class="contact-icon">🐙</span>
                        <div>
                            <strong>GitHub</strong><br>
                            github.com/tu-usuario
                        </div>
                    </div>
                    <div class="contact-item">
                        <span class="contact-icon">💼</span>
                        <div>
                            <strong>LinkedIn</strong><br>
                            linkedin.com/in/tu-perfil
                        </div>
                    </div>
                    <div class="contact-item">
                        <span class="contact-icon">🌐</span>
                        <div>
                            <strong>Portfolio</strong><br>
                            tu-dominio.com
                        </div>
                    </div>
                </div>
            </section>
        </div>
    </main>

    <script>
        // Mobile menu toggle
        const mobileToggle = document.getElementById('mobileToggle');
        const sidebar = document.getElementById('sidebar');
        
        mobileToggle.addEventListener('click', () => {
            sidebar.classList.toggle('active');
            mobileToggle.textContent = sidebar.classList.contains('active') ? '✕' : '☰';
        });

        // Close sidebar when clicking outside on mobile
        document.addEventListener('click', (e) => {
            if (window.innerWidth <= 768) {
                if (!sidebar.contains(e.target) && !mobileToggle.contains(e.target)) {
                    sidebar.classList.remove('active');
                    mobileToggle.textContent = '☰';
                }
            }
        });

        // Smooth scrolling and active nav links
        const navLinks = document.querySelectorAll('.nav-link');
        
        navLinks.forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                
                // Remove active class from all links
                navLinks.forEach(l => l.classList.remove('active'));
                
                // Add active class to clicked link
                link.classList.add('active');
                
                // Get target section
                const targetId = link.getAttribute('href');
                const targetSection = document.querySelector(targetId);
                
                if (targetSection) {
                    targetSection.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
                
                // Close mobile menu
                if (window.innerWidth <= 768) {
                    sidebar.classList.remove('active');
                    mobileToggle.textContent = '☰';
                }
            });
        });

        // Intersection Observer for active nav links
        const sections = document.querySelectorAll('section[id]');
        
        const observerOptions = {
            root: null,
            rootMargin: '-50% 0px -50% 0px',
            threshold: 0
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const id = entry.target.getAttribute('id');
                    navLinks.forEach(link => {
                        link.classList.remove('active');
                        if (link.getAttribute('href') === `#${id}`) {
                            link.classList.add('active');
                        }
                    });
                }
            });
        }, observerOptions);
        
        sections.forEach(section => {
            observer.observe(section);
        });

        // Add loading effect to profile photo
        const profilePhoto = document.querySelector('.profile-photo');
        profilePhoto.addEventListener('load', () => {
            profilePhoto.style.opacity = '1';
        });
    </script>
</body>
</html>
