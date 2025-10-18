<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dr. José Gabriel Aguilera González - Especialista en Inteligencia Artificial</title>
    <meta name="description" content="Portafolio profesional del Dr. Gabriel Aguilera, Doctor en Sistemas Computacionales especializado en Inteligencia Artificial">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary-color: #3b82f6;
            --primary-dark: #1d4ed8;
            --secondary-color: #64748b;
            --background-dark: #0f172a;
            --sidebar-dark: #1e293b;
            --content-dark: #334155;
            --text-primary: #f8fafc;
            --text-secondary: #cbd5e1;
            --text-muted: #94a3b8;
            --accent-blue: #60a5fa;
            --border-color: #475569;
            --shadow-color: rgba(0, 0, 0, 0.3);
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            --border-radius: 12px;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background-color: var(--background-dark);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 20% 50%, rgba(59, 130, 246, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(59, 130, 246, 0.08) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(59, 130, 246, 0.06) 0%, transparent 50%);
            background-attachment: fixed;
        }

        /* Neural Network Background Pattern */
        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%233b82f6' fill-opacity='0.03'%3E%3Ccircle cx='30' cy='30' r='4'/%3E%3Cpath d='m30 26c2.2091 0 4 1.7909 4 4s-1.7909 4-4 4-4-1.7909-4-4 1.7909-4 4-4zm-15 15c1.1046 0 2 .8954 2 2s-.8954 2-2 2-2-.8954-2-2 .8954-2 2-2zm30 0c1.1046 0 2 .8954 2 2s-.8954 2-2 2-2-.8954-2-2 .8954-2 2-2zm-15-30c1.1046 0 2 .8954 2 2s-.8954 2-2 2-2-.8954-2-2 .8954-2 2-2z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
            z-index: -2;
        }

        /* SIDEBAR STYLES */
        .sidebar {
            position: fixed;
            left: 0;
            top: 0;
            width: 320px;
            height: 100vh;
            background: linear-gradient(180deg, var(--sidebar-dark) 0%, #0f172a 100%);
            border-right: 2px solid var(--border-color);
            box-shadow: 4px 0 24px var(--shadow-color);
            padding: 2rem 0;
            overflow-y: auto;
            z-index: 1000;
            transition: var(--transition);
        }

        .sidebar::-webkit-scrollbar {
            width: 4px;
        }

        .sidebar::-webkit-scrollbar-track {
            background: transparent;
        }

        .sidebar::-webkit-scrollbar-thumb {
            background: var(--primary-color);
            border-radius: 2px;
        }

        .profile-section {
            padding: 0 2rem 2rem;
            text-align: center;
            border-bottom: 1px solid var(--border-color);
            margin-bottom: 2rem;
        }

        .profile-photo {
            width: 140px;
            height: 140px;
            border-radius: 50%;
            border: 4px solid var(--primary-color);
            margin: 0 auto 1.5rem;
            box-shadow: 0 8px 32px rgba(59, 130, 246, 0.3);
            transition: var(--transition);
            object-fit: cover;
        }

        .profile-photo:hover {
            transform: scale(1.05);
            box-shadow: 0 12px 48px rgba(59, 130, 246, 0.4);
        }

        .profile-name {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: var(--text-primary);
        }

        .profile-title {
            font-size: 1rem;
            font-weight: 400;
            color: var(--accent-blue);
            margin-bottom: 0.5rem;
        }

        .profile-subtitle {
            font-size: 0.875rem;
            color: var(--text-muted);
            font-weight: 300;
        }

        .nav-menu {
            list-style: none;
            padding: 0 1rem;
        }

        .nav-item {
            margin-bottom: 0.5rem;
        }

        .nav-link {
            display: flex;
            align-items: center;
            padding: 1rem 1.5rem;
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
            color: var(--text-primary);
            transform: translateX(4px);
        }

        .nav-icon {
            font-size: 1.25rem;
            margin-right: 1rem;
            min-width: 24px;
        }

        /* MAIN CONTENT STYLES */
        .main-content {
            margin-left: 320px;
            min-height: 100vh;
            background: transparent;
            position: relative;
        }

        .content-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 3rem;
            position: relative;
        }

        .content-section {
            background: rgba(51, 65, 85, 0.4);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(71, 85, 105, 0.3);
            border-radius: var(--border-radius);
            padding: 3rem;
            margin-bottom: 2rem;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .content-section::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, var(--primary-color), var(--accent-blue));
        }

        .content-section:hover {
            transform: translateY(-4px);
            box-shadow: 0 12px 48px rgba(0, 0, 0, 0.3);
            border-color: rgba(96, 165, 250, 0.3);
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            color: var(--text-primary);
            position: relative;
            display: inline-block;
        }

        .section-title::after {
            content: "";
            position: absolute;
            bottom: -8px;
            left: 0;
            width: 60px;
            height: 3px;
            background: var(--primary-color);
            border-radius: 2px;
        }

        .section-text {
            font-size: 1.125rem;
            color: var(--text-secondary);
            margin-bottom: 1.5rem;
            line-height: 1.8;
        }

        .highlight-text {
            color: var(--accent-blue);
            font-weight: 500;
        }

        /* Research Areas Grid */
        .research-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .research-card {
            background: rgba(30, 41, 59, 0.6);
            padding: 2rem;
            border-radius: var(--border-radius);
            border: 1px solid var(--border-color);
            transition: var(--transition);
        }

        .research-card:hover {
            background: rgba(59, 130, 246, 0.1);
            border-color: var(--accent-blue);
            transform: translateY(-2px);
        }

        .research-card h3 {
            color: var(--accent-blue);
            margin-bottom: 1rem;
            font-size: 1.25rem;
            font-weight: 600;
        }

        /* Publications List */
        .publications-list {
            list-style: none;
            margin-top: 2rem;
        }

        .publication-item {
            background: rgba(30, 41, 59, 0.4);
            padding: 2rem;
            margin-bottom: 1.5rem;
            border-radius: var(--border-radius);
            border-left: 4px solid var(--primary-color);
            transition: var(--transition);
        }

        .publication-item:hover {
            background: rgba(30, 41, 59, 0.6);
            transform: translateX(4px);
        }

        .publication-title {
            font-size: 1.25rem;
            font-weight: 600;
            color: var(--text-primary);
            margin-bottom: 0.5rem;
        }

        .publication-authors {
            color: var(--accent-blue);
            font-weight: 500;
            margin-bottom: 0.5rem;
        }

        .publication-details {
            color: var(--text-muted);
            font-style: italic;
        }

        /* Contact Grid */
        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            background: rgba(30, 41, 59, 0.4);
            padding: 1.5rem;
            border-radius: var(--border-radius);
            transition: var(--transition);
            border: 1px solid transparent;
        }

        .contact-item:hover {
            background: rgba(59, 130, 246, 0.1);
            border-color: var(--accent-blue);
        }

        .contact-icon {
            font-size: 2rem;
            margin-right: 1rem;
            color: var(--primary-color);
            min-width: 40px;
        }

        .contact-info h4 {
            color: var(--text-primary);
            margin-bottom: 0.25rem;
            font-weight: 600;
        }

        .contact-info p {
            color: var(--text-secondary);
            margin: 0;
        }

        /* Mobile Menu Toggle */
        .mobile-toggle {
            display: none;
            position: fixed;
            top: 1rem;
            left: 1rem;
            z-index: 1001;
            background: var(--primary-color);
            color: var(--text-primary);
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            font-size: 1.5rem;
            cursor: pointer;
            box-shadow: 0 4px 16px rgba(59, 130, 246, 0.3);
            transition: var(--transition);
        }

        .mobile-toggle:hover {
            background: var(--primary-dark);
            transform: scale(1.05);
        }

        /* Responsive Design */
        @media (max-width: 1024px) {
            .content-container {
                padding: 2rem;
            }
            
            .content-section {
                padding: 2rem;
            }
        }

        @media (max-width: 768px) {
            .mobile-toggle {
                display: flex;
                align-items: center;
                justify-content: center;
            }

            .sidebar {
                transform: translateX(-100%);
                width: 100%;
                max-width: 320px;
            }

            .sidebar.active {
                transform: translateX(0);
            }

            .main-content {
                margin-left: 0;
            }

            .content-container {
                padding: 1rem;
            }

            .content-section {
                padding: 1.5rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .research-grid,
            .contact-grid {
                grid-template-columns: 1fr;
            }

            .profile-photo {
                width: 120px;
                height: 120px;
            }

            .profile-name {
                font-size: 1.25rem;
            }
        }

        /* Scroll behavior */
        html {
            scroll-behavior: smooth;
        }

        /* Custom scrollbar for webkit browsers */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: var(--background-dark);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--primary-color);
            border-radius: 4px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--primary-dark);
        }
    </style>
</head>
<body>
    <!-- Mobile Menu Toggle -->
    <button class="mobile-toggle" id="mobileToggle" aria-label="Toggle menu">
        ☰
    </button>

    <!-- Sidebar -->
    <nav class="sidebar" id="sidebar">
        <div class="profile-section">
        <img src="https://drive.google.com/uc?export=view&id=1CLFKgSMF8CJlpwOMSRQwVCFLxANtmY4l" alt="Dr. José Gabriel Aguilera González" class="profile-photo"
            <h1 class="profile-name">Dr. José Gabriel Aguilera González</h1>
            <p class="profile-title">Doctor en Sistemas Computacionales</p>
            <p class="profile-subtitle">Especialista en Inteligencia Artificial</p>
            <p class="profile-subtitle">Líder Académico e Impulsor de la Calidad en la Educación Superior</p>
            <p class="profile-subtitle">Gestor de Programas y Proyectos</p>
        </div>
        
        <ul class="nav-menu">
            <li class="nav-item">
                <a href="#acerca-de" class="nav-link active">
                    <span class="nav-icon">👤</span>
                    Acerca de
                </a>
            </li>
            <li class="nav-item">
                <a href="#investigacion" class="nav-link">
                    <span class="nav-icon">🔬</span>
                    Investigación
                </a>
            </li>
            <li class="nav-item">
                <a href="#publicaciones" class="nav-link">
                    <span class="nav-icon">📚</span>
                    Publicaciones
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
        <div class="content-container">
            <!-- Acerca de Section -->
            <section id="acerca-de" class="content-section">
                <h2 class="section-title">Acerca de</h2>
                <p class="section-text">
                    Soy <span class="highlight-text">Doctor en Sistemas Computacionales</span> con una especialización profunda en Inteligencia Artificial, Líder Académico e impulsor de educación superior de calidad; Gestor de Programas y Proyectos; Impulsor de Equipos de Alto Desempeño. Mi trabajo se enfoca en el avance del campo de la IA a través de investigación innovadora y aplicaciones prácticas que impacten positivamente en la sociedad; cuento con más de 7 años de experiencia en liderazgo del área académica de Instituciones de Educación Superior, con un amplio compromiso con educación de calidad; he gestionado e impulsado proyectos de investigación y equipamiento.
                </p>
                <p class="section-text">
                    Mi expertise en Inteligencia Artificial abarca <span class="highlight-text">aprendizaje profundo, redes neuronales, procesamiento de lenguaje natural, visión por computadora y sistemas inteligentes</span>. Tengo una pasión particular por desarrollar algoritmos eficientes y explicables que puedan ser implementados en entornos del mundo real.
                </p>
                <p class="section-text">
                    Como académico y investigador, estoy comprometido con la excelencia en la educación superior, la mentoría de nuevos investigadores y la colaboración interdisciplinaria para abordar los desafíos más complejos de nuestro tiempo mediante la inteligencia artificial.
                </p>
            </section>

            <!-- Investigación Section -->
            <section id="investigacion" class="content-section">
                <h2 class="section-title">Investigación</h2>
                <p class="section-text">
                    Mis líneas de investigación se centran en el desarrollo de <span class="highlight-text">Redes Neuronales Convolucionales de Aprendizaje Profundo</span>. Trabajo en la intersección entre la teoría computacional avanzada y sus aplicaciones prácticas en diversos dominios.
                </p>

                <div class="research-grid">
                    <div class="research-card">
                        <h3>🧠 Aprendizaje Profundo Adaptativo</h3>
                        <p>Desarrollo de arquitecturas de redes neuronales que se adaptan dinámicamente a nuevos dominios y tareas, con especial énfasis en la eficiencia computacional y la robustez.</p>
                    </div>
                    
                    <div class="research-card">
                        <h3>🔍 IA Explicable y Transparente</h3>
                        <p>Investigación en métodos para hacer que los sistemas de IA sean interpretables y transparentes, especialmente en aplicaciones críticas como salud y seguridad.</p>
                    </div>
                    
                    <div class="research-card">
                        <h3>🏥 IA Aplicada en Salud Digital</h3>
                        <p>Análisis de imágenes médicas y medicina personalizada usando técnicas avanzadas de ML.</p>
                    </div>
                </div>
            </section>

            <!-- Publicaciones Section -->
            <section id="publicaciones" class="content-section">
                <h2 class="section-title">Publicaciones</h2>
                <p class="section-text">
                    A continuación se presenta una selección de mis contribuciones más relevantes al campo de la Inteligencia Artificial y Sistemas Computacionales, publicadas en revistas y conferencias de alto impacto.
                </p>

                <ul class="publications-list">
                    <li class="publication-item">
                        <div class="publication-title">Adaptive Neural Architectures for Edge Computing in Healthcare Applications</div>
                        <div class="publication-authors">Dr. [Tu Nombre], Dr. Colaborador A., Dr. Colaborador B.</div>
                        <div class="publication-details">IEEE Transactions on Artificial Intelligence, Vol. 4, No. 3, pp. 245-260, 2023</div>
                    </li>
                    
                    <li class="publication-item">
                        <div class="publication-title">Explainable AI Framework for Medical Decision Support Systems</div>
                        <div class="publication-authors">Dr. [Tu Nombre], Dr. Colaborador C., Dr. Colaborador D.</div>
                        <div class="publication-details">Nature Machine Intelligence, Vol. 5, pp. 123-138, 2023</div>
                    </li>
                    
                    <li class="publication-item">
                        <div class="publication-title">Bias Mitigation Strategies in Large Language Models: A Comprehensive Survey</div>
                        <div class="publication-authors">Dr. [Tu Nombre], Dr. Colaborador E.</div>
                        <div class="publication-details">Journal of Machine Learning Research, Vol. 24, pp. 1-45, 2023</div>
                    </li>
                    
                    <li class="publication-item">
                        <div class="publication-title">Reinforcement Learning for Autonomous Medical Diagnosis: Challenges and Opportunities</div>
                        <div class="publication-authors">Dr. [Tu Nombre], Dr. Colaborador F., Dr. Colaborador G.</div>
                        <div class="publication-details">Proceedings of AAAI Conference on Artificial Intelligence, pp. 8756-8763, 2022</div>
                    </li>
                    
                    <li class="publication-item">
                        <div class="publication-title">Federated Learning in Healthcare: Privacy-Preserving Collaborative AI</div>
                        <div class="publication-authors">Dr. [Tu Nombre], Dr. Colaborador H.</div>
                        <div class="publication-details">ACM Computing Surveys, Vol. 55, No. 2, Article 37, 2022</div>
                    </li>
                </ul>
            </section>

            <!-- Contacto Section -->
            <section id="contacto" class="content-section">
                <h2 class="section-title">Contacto</h2>
                <p class="section-text">
                    Estoy abierto a colaboraciones en proyectos de investigación, consultoría académica, participación en conferencias y oportunidades de mentoría. No dudes en contactarme para discutir posibles colaboraciones o intercambio académico.
                </p>

                <div class="contact-grid">
                    <div class="contact-item">
                        <span class="contact-icon">📧</span>
                        <div class="contact-info">
                            <h4>Correo Electrónico</h4>
                            <a href="gabriel.ag@surguanajuato.tecnm.mx" target="_blank" rel="noopener">
                            Correo electrónico
                            <a>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <span class="contact-icon">🏛️</span>
                        <div class="contact-info">
                            <h4>Institución</h4>
                            <a href="surguanajuato.tecnm.mx" target="_blank" rel="noopener">
                            TecNM Sur de Guanajuato
                            <a>
                        </div>
                    </div>
                    
                    
                    <div class="contact-item">
                        <span class="contact-icon">🔗</span>
                        <div class="contact-info">
                            <h4>ORCID</h4>
                            <a href="https://orcid.org/0000-0002-4160-448X" target="_blank" rel="noopener">
                            ORCID: 0000-0002-4160-448X
                            </a>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <span class="contact-icon">💼</span>
                        <div class="contact-info">
                            <h4>LinkedIn Académico</h4>
                             <a href="www.linkedin.com/in/gabriel-aguilera-3969a1183" target="_blank" rel="noopener">
                            LinkedIn
                            </a>
                        </div>
                    </div>
                    
                    <div class="contact-item">
                        <span class="contact-icon">📍</span>
                        <div class="contact-info">
                            <h4>Ubicación</h4>
                            <p>Uriangato, Gto.<br>Oficina: 445 457 7468 + 106</p>
                        </div>
                    </div>
                </div>
            </section>
        </div>
    </main>

    <script>
        // Mobile menu toggle functionality
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
                
                // Get target section and scroll to it
                const targetId = link.getAttribute('href');
                const targetSection = document.querySelector(targetId);
                
                if (targetSection) {
                    const offsetTop = targetSection.offsetTop - 20;
                    window.scrollTo({
                        top: offsetTop,
                        behavior: 'smooth'
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
            rootMargin: '-20% 0px -60% 0px',
            threshold: 0.1
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

        // Add loading animation for better UX
        document.addEventListener('DOMContentLoaded', () => {
            document.body.style.opacity = '0';
            setTimeout(() => {
                document.body.style.transition = 'opacity 0.5s ease';
                document.body.style.opacity = '1';
            }, 100);
        });
    </script>
</body>
</html>
