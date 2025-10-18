<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dr. Gabriel Aguilera - AI Specialist</title>
    <meta name="description" content="Professional portfolio of Dr. Gabriel Aguielra, Doctor in Computer Systems specializing in Artificial Intelligence.">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #3b82f6;
            --primary-dark: #1d4ed8;
            --background-dark: #1e1e2e;
            --sidebar-dark: #27273a;
            --text-primary: #f1f5f9;
            --text-secondary: #cbd5e1;
            --accent-color: #60a5fa;
            --border-radius: 8px;
            --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
            --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
            --transition: all 0.3s ease;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            color: var(--text-primary);
            background-color: var(--background-dark);
            background-image: url('data:image/svg+xml;utf8,<svg width="100" height="100" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg"><path d="M30,40 H70 V60 H30 V40 Z M40,30 V70 M60,30 V70 M30,30 L70,70 M30,70 L70,30" stroke="%233b82f6" stroke-width="1" stroke-opacity="0.1" fill="none"/></svg>');
            background-size: 200px 200px;
            overflow-x: hidden;
        }

        /* Sidebar Styles */
        .sidebar {
            position: fixed;
            left: 0;
            top: 0;
            width: 300px;
            height: 100vh;
            background-color: var(--sidebar-dark);
            padding: 2rem 1.5rem;
            box-shadow: var(--shadow-lg);
            z-index: 1000;
            transition: var(--transition);
            overflow-y: auto;
        }

        .profile-header {
            text-align: center;
            margin-bottom: 2rem;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            padding-bottom: 1.5rem;
        }

        .profile-photo {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            margin: 0 auto 1rem;
            border: 4px solid var(--primary-color);
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .profile-photo:hover {
            transform: scale(1.03);
            box-shadow: var(--shadow-lg);
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
            color: var(--text-secondary);
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
            padding: 0.75rem 1rem;
            color: var(--text-secondary);
            text-decoration: none;
            border-radius: var(--border-radius);
            transition: var(--transition);
            font-weight: 500;
            position: relative;
        }

        .nav-link:hover,
        .nav-link.active {
            background-color: rgba(255, 255, 255, 0.1);
            color: var(--accent-color);
            transform: translateX(3px);
        }

        .nav-icon {
            margin-right: 0.75rem;
            font-size: 1.2rem;
        }

        /* Main Content */
        .main-content {
            margin-left: 300px;
            min-height: 100vh;
            transition: var(--transition);
            padding: 2rem;
        }

        /* Content Sections */
        .content-section {
            background-color: rgba(39, 39, 58, 0.7);
            padding: 2rem;
            margin-bottom: 2rem;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            transition: var(--transition);
            backdrop-filter: blur(10px);
        }

        .content-section:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-lg);
        }

        .section-title {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            color: var(--text-primary);
            position: relative;
            padding-bottom: 0.5rem;
        }

        .section-title::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 50px;
            height: 3px;
            background: var(--primary-color);
        }

        .section-text {
            font-size: 1.1rem;
            color: var(--text-secondary);
            margin-bottom: 1rem;
        }

        /* Publications List */
        .publications-list {
            list-style: none;
            margin-top: 1.5rem;
        }

        .publication-item {
            margin-bottom: 1.5rem;
            padding-left: 1.5rem;
            position: relative;
            border-left: 2px solid var(--primary-color);
        }

        .publication-item::before {
            content: "•";
            position: absolute;
            left: -0.75rem;
            color: var(--primary-color);
            font-size: 1.5rem;
        }

        .publication-title {
            font-weight: 600;
            color: var(--text-primary);
            margin-bottom: 0.3rem;
        }

        .publication-details {
            font-size: 0.95rem;
            color: var(--text-secondary);
            font-style: italic;
        }

        /* Contact Info */
        .contact-info {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1.5rem;
            margin-top: 1.5rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            padding: 1rem;
            background: rgba(255, 255, 255, 0.05);
            border-radius: var(--border-radius);
            transition: var(--transition);
        }

        .contact-item:hover {
            background: rgba(255, 255, 255, 0.1);
        }

        .contact-icon {
            margin-right: 1rem;
            font-size: 1.5rem;
            color: var(--primary-color);
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
                padding: 1rem;
            }

            .section-title {
                font-size: 1.75rem;
            }

            .content-section {
                padding: 1.5rem;
            }
        }

        /* Scroll behavior */
        html {
            scroll-behavior: smooth;
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
        <div class="profile-header">
            <img src="https://placehold.co/400x400/3b82f6/ffffff?text=Profile" alt="Profile Photo" class="profile-photo">
            <h1 class="profile-name">Dr. [Your Name]</h1>
            <p class="profile-title">Doctor in Computer Systems (AI Specialist)</p>
        </div>
        
        <ul class="nav-menu">
            <li class="nav-item">
                <a href="#about" class="nav-link active">
                    <span class="nav-icon">👤</span>
                    About
                </a>
            </li>
            <li class="nav-item">
                <a href="#research" class="nav-link">
                    <span class="nav-icon">🔬</span>
                    Research
                </a>
            </li>
            <li class="nav-item">
                <a href="#publications" class="nav-link">
                    <span class="nav-icon">📚</span>
                    Publications
                </a>
            </li>
            <li class="nav-item">
                <a href="#contact" class="nav-link">
                    <span class="nav-icon">📧</span>
                    Contact
                </a>
            </li>
        </ul>
    </nav>

    <!-- Main Content -->
    <main class="main-content">
        <!-- About Section -->
        <section id="about" class="content-section">
            <h2 class="section-title">About</h2>
            <p class="section-text">
                I am a Doctor in Computer Systems with a specialization in Artificial Intelligence. My work focuses on advancing the field of AI through innovative research and practical applications. With a strong background in computer science and machine learning, I strive to develop solutions that address complex challenges in technology and society.
            </p>
            <p class="section-text">
                My expertise includes deep learning, neural networks, natural language processing, and computer vision. I am passionate about contributing to the academic community through teaching, mentoring, and collaborative projects.
            </p>
        </section>

        <!-- Research Section -->
        <section id="research" class="content-section">
            <h2 class="section-title">Research</h2>
            <p class="section-text">
                My research interests lie at the intersection of Artificial Intelligence and real-world problem-solving. I am currently exploring the following areas:
            </p>
            <ul class="section-text">
                <li>Development of efficient deep learning models for resource-constrained environments.</li>
                <li>Applications of computer vision in healthcare and diagnostics.</li>
                <li>Advancements in reinforcement learning for autonomous systems.</li>
            </ul>
            <p class="section-text">
                My ongoing projects aim to bridge the gap between theoretical AI research and practical implementation, with a focus on scalability and societal impact.
            </p>
        </section>

        <!-- Publications Section -->
        <section id="publications" class="content-section">
            <h2 class="section-title">Publications</h2>
            <p class="section-text">
                Below is a selection of my key publications in the field of Artificial Intelligence and Computer Systems.
            </p>
            <ul class="publications-list">
                <li class="publication-item">
                    <div class="publication-title">"Efficient Neural Architectures for Edge Devices"</div>
                    <div class="publication-details">Dr. [Your Name], et al. | Journal of Machine Learning Research | 2023</div>
                </li>
                <li class="publication-item">
                    <div class="publication-title">"Bias Mitigation Strategies in Deep Learning Models"</div>
                    <div class="publication-details">Dr. [Your Name], et al. | IEEE Transactions on AI | 2022</div>
                </li>
                <li class="publication-item">
                    <div class="publication-title">"Computer Vision Applications in Medical Imaging"</div>
                    <div class="publication-details">Dr. [Your Name], et al. | International Conference on AI in Healthcare | 2021</div>
                </li>
                <li class="publication-item">
                    <div class="publication-title">"Reinforcement Learning for Autonomous Navigation"</div>
                    <div class="publication-details">Dr. [Your Name], et al. | Robotics and AI Journal | 2020</div>
                </li>
            </ul>
        </section>

        <!-- Contact Section -->
        <section id="contact" class="content-section">
            <h2 class="section-title">Contact</h2>
            <p class="section-text">
                I am open to collaboration on research projects, speaking engagements, and academic consultations. Please feel free to reach out through the following channels:
            </p>
            <div class="contact-info">
                <div class="contact-item">
                    <span class="contact-icon">📧</span>
                    <div>
                        <strong>Email:</strong> [your.email@example.com]
                    </div>
                </div>
                <div class="contact-item">
                    <span class="contact-icon">🏛️</span>
                    <div>
                        <strong>Institution:</strong> [Your University/Organization]
                    </div>
                </div>
                <div class="contact-item">
                    <span class="contact-icon">🔗</span>
                    <div>
                        <strong>LinkedIn:</strong> linkedin.com/in/[your-profile]
                    </div>
                </div>
                <div class="contact-item">
                    <span class="contact-icon">📖</span>
                    <div>
                        <strong>ResearchGate:</strong> researchgate.net/profile/[your-profile]
                    </div>
                </div>
            </div>
        </section>
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
    </script>
</body>
</html>
