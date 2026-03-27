#idearq-web
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IDEARQ | Arquitetura e Design de Alto Padrão</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=Outfit:wght@400;700&family=Playfair+Display:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #367588; /* Azul Petróleo */
            --accent: #FF8C00;  /* Laranja Segurança */
            --bg-light: #f4f7f6; /* Fundo esverdeado limpo */
            --text-dark: #1a2a2e;
            --text-muted: #5a6a6e;
            --white: #ffffff;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-light);
            color: var(--text-dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        h1, h2, h3 {
            font-family: 'Outfit', sans-serif;
            font-weight: 700;
        }

        a {
            text-decoration: none;
            color: inherit;
            transition: var(--transition);
        }

        ul {
            list-style: none;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }

        .btn {
            display: inline-block;
            padding: 14px 28px;
            border-radius: 6px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            text-align: center;
            border: none;
        }

        .btn-primary {
            background-color: var(--accent);
            color: var(--white);
        }

        .btn-primary:hover {
            background-color: #e67e00;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 140, 0, 0.3);
        }

        .btn-whatsapp {
            background-color: transparent;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 8px;
            border: 1px solid var(--primary);
        }

        .btn-whatsapp:hover {
            background-color: var(--primary);
            color: var(--white);
            transform: translateY(-2px);
        }

        /* Header */
        header {
            background-color: var(--white);
            padding: 20px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 20px;
            font-weight: 800;
            color: var(--accent);
            letter-spacing: 1px;
        }

        .nav-links {
            display: none;
        }

        .mobile-menu-btn {
            display: block;
            font-size: 24px;
            cursor: pointer;
            color: var(--primary);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(26, 42, 46, 0.6), rgba(26, 42, 46, 0.6)), 
                        url('https://images.unsplash.com/photo-1600585154340-be6161a56a0c?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80') center/cover no-repeat;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--white);
            padding-top: 80px;
        }

        .hero-content h1 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            max-width: 900px;
            line-height: 1.2;
        }

        .hero-content p {
            font-size: 1.2rem;
            margin-bottom: 30px;
            opacity: 0.95;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            font-weight: 300;
        }

        /* Form Section */
        .form-section {
            background-color: var(--bg-light);
            padding: 80px 0;
        }

        .form-container {
            width: 100%;
            max-width: 800px;
            margin: 0 auto;
            background: var(--white);
            padding: 20px;
            border-radius: 15px;
            box-shadow: var(--shadow);
        }

        .form-container iframe {
            width: 100%;
            height: 800px;
            border: none;
            border-radius: 10px;
        }

        /* About Section */
        .about-section {
            background-color: #fffaf5;
            padding: 100px 0;
            text-align: center;
        }

        .about-content {
            max-width: 900px;
            margin: 0 auto;
        }

        .about-content h2 {
            font-family: 'Playfair Display', serif;
            font-size: 2.2rem;
            color: var(--primary);
            margin-bottom: 30px;
            font-weight: 400;
            font-style: italic;
        }

        .about-text {
            font-family: 'Playfair Display', serif;
            font-size: 1.15rem;
            color: var(--text-muted);
            line-height: 1.8;
            text-align: justify;
            font-weight: 400;
        }

        .about-text p {
            margin-bottom: 25px;
        }

        .about-text strong {
            color: var(--primary);
            font-weight: 700;
        }

        /* Services Section */
        section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h2 {
            font-size: 2rem;
            color: var(--primary);
            margin-bottom: 10px;
        }

        .section-title .underline {
            width: 60px;
            height: 4px;
            background-color: var(--accent);
            margin: 0 auto;
        }

        .services-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 25px;
        }

        .service-card {
            background-color: var(--white);
            padding: 30px;
            border-radius: 12px;
            box-shadow: var(--shadow);
            transition: var(--transition);
            text-align: center;
        }

        .service-card:hover {
            transform: translateY(-8px);
        }

        .service-card i {
            font-size: 36px;
            color: var(--accent);
            margin-bottom: 15px;
            display: block;
        }

        .service-card h3 {
            margin-bottom: 10px;
            color: var(--primary);
            font-size: 1.2rem;
        }

        /* Gallery */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .gallery-item {
            height: 350px;
            border-radius: 8px;
            overflow: hidden;
            position: relative;
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .gallery-item:hover img {
            transform: scale(1.05);
        }

        /* Portfolio Management */
        .portfolio-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 50px;
        }

        .portfolio-header .section-title {
            margin-bottom: 0;
            text-align: left;
        }

        .portfolio-header .section-title .underline {
            margin: 0;
        }

        .btn-add-project {
            background-color: var(--primary);
            color: var(--white);
            font-size: 0.9rem;
            padding: 10px 20px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .btn-add-project:hover {
            background-color: var(--text-dark);
        }

        /* Modal Styles */
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.6);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 3000;
            backdrop-filter: blur(5px);
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background-color: var(--white);
            padding: 40px;
            border-radius: 12px;
            width: 90%;
            max-width: 500px;
            box-shadow: var(--shadow);
            position: relative;
        }

        .modal-content h3 {
            color: var(--primary);
            margin-bottom: 20px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            font-size: 0.9rem;
        }

        .form-group input {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 6px;
            font-family: inherit;
        }

        .modal-footer {
            display: flex;
            justify-content: flex-end;
            gap: 15px;
            margin-top: 30px;
        }

        .btn-cancel {
            background-color: #eee;
            color: var(--text-dark);
        }

        .project-card-overlay {
            position: absolute;
            top: 10px;
            right: 10px;
            z-index: 10;
            display: none;
        }

        .gallery-item:hover .project-card-overlay {
            display: block;
        }

        .btn-delete-project {
            background-color: rgba(255, 0, 0, 0.7);
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 0.7rem;
        }

        /* Footer */
        footer {
            background-color: #1a2a2e;
            color: var(--white);
            padding: 60px 0 20px;
        }

        .footer-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-logo {
            font-size: 24px;
            font-weight: 800;
            margin-bottom: 15px;
            display: block;
            letter-spacing: 1px;
        }

        .footer-info p {
            font-size: 1rem;
            opacity: 0.9;
            line-height: 1.5;
        }

        .footer-links h4 {
            margin-bottom: 20px;
            color: var(--accent);
            text-transform: uppercase;
            font-size: 0.9rem;
            letter-spacing: 1px;
        }

        .footer-links li {
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .footer-links .emoji {
            font-size: 1.4rem;
        }

        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
            font-size: 0.85rem;
            opacity: 0.6;
        }

        /* Responsive */
        @media (min-width: 768px) {
            .nav-links {
                display: flex;
                gap: 30px;
                align-items: center;
            }

            .mobile-menu-btn {
                display: none;
            }

            .hero-content h1 {
                font-size: 3.5rem;
            }

            .services-grid {
                grid-template-columns: repeat(5, 1fr);
            }

            .footer-grid {
                grid-template-columns: 2fr 1fr 1.5fr;
            }
        }

        /* Mobile Menu Overlay */
        .mobile-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: var(--primary);
            z-index: 2000;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            transform: translateX(100%);
            transition: transform 0.4s cubic-bezier(0.77,0.2,0.05,1.0);
        }

        .mobile-overlay.active {
            transform: translateX(0);
        }

        .mobile-overlay .close-btn {
            position: absolute;
            top: 30px;
            right: 30px;
            font-size: 30px;
            color: var(--white);
            cursor: pointer;
        }

        .mobile-overlay a {
            font-size: 1.5rem;
            color: var(--white);
            margin: 15px 0;
            font-weight: 600;
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <div class="container">
            <nav>
                <a href="#" class="logo">IDEARQ Arquitetura e Design</a>
                <ul class="nav-links">
                    <li><a href="#inicio">Início</a></li>
                    <li><a href="#sobre">Sobre</a></li>
                    <li><a href="#servicos">Serviços</a></li>
                    <li><a href="#projetos">Projetos</a></li>
                    <li><a href="#contato">Contato</a></li>
                    <li><a href="#contato" class="btn btn-whatsapp">WhatsApp</a></li>
                </ul>
                <div class="mobile-menu-btn" id="openMenu">☰</div>
            </nav>
        </div>
    </header>

    <!-- Mobile Menu Overlay -->
    <div class="mobile-overlay" id="mobileOverlay">
        <div class="close-btn" id="closeMenu">&times;</div>
        <a href="#" class="logo" style="color: var(--accent); margin-bottom: 30px;">IDEARQ Arquitetura e Design</a>
        <a href="#inicio" class="mobile-link">Início</a>
        <a href="#sobre" class="mobile-link">Sobre</a>
        <a href="#servicos" class="mobile-link">Serviços</a>
        <a href="#projetos" class="mobile-link">Projetos</a>
        <a href="#contato" class="mobile-link">Contato</a>
        <a href="#contato" class="btn btn-whatsapp" style="margin-top: 20px;">WhatsApp</a>
    </div>

    <!-- Hero Section -->
    <section class="hero" id="inicio">
        <div class="container hero-content">
            <h1>Transformamos as suas ideias em realidade</h1>
            <p>Desde 2013 com projetos de alto padrão com foco em oferecer o melhor em ambientação. Prezamos o conceito de morar bem.</p>
            <a href="#agendamento" class="btn btn-primary">Agende uma consultoria on-line</a>
        </div>
    </section>

    <!-- About Section -->
    <section id="sobre" class="about-section">
        <div class="container about-content">
            <h2>Idearq Arquitetura: Transformando Ideias em Espaços com Propósito</h2>
            <div class="about-text">
                <p>Bem-vindo à <strong>IDEARQ Arquitetura & Design</strong>, um escritório dedicado a unir estética, funcionalidade e inovação em cada projeto. Acreditamos que a arquitetura vai além do desenho, ela é a materialização de sonhos e a otimização de experiências no espaço urbano e privado.</p>
                <p>À frente do escritório, os sócios <strong>Isac Pontes</strong> e <strong>Pedro Brasiliano</strong> combinam visões complementares para entregar soluções de excelência.</p>
                <p><strong>Isac Pontes</strong> traz um olhar atento ao detalhe e à viabilidade técnica, garantindo que cada conceito seja executado com precisão e sofisticação.</p>
                <p><strong>Pedro Brasiliano</strong> foca na integração harmoniosa entre design moderno e as necessidades reais de quem habita ou utiliza o espaço, sempre priorizando a identidade do cliente.</p>
                <p>Na IDEARQ, nosso compromisso é com a transparência e a qualidade. Seja em projetos residenciais, comerciais ou corporativos, nossa missão é converter complexidade em elegância, entregando resultados que elevam o padrão de vida e de negócios dos nossos clientes.</p>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="servicos">
        <div class="container">
            <div class="section-title">
                <h2>Nossos Serviços</h2>
                <div class="underline"></div>
            </div>
            <div class="services-grid">
                <div class="service-card">
                    <i>📐</i>
                    <h3>Projeto</h3>
                    <p>Arquitetura autoral e funcional.</p>
                </div>
                <div class="service-card">
                    <i>🏗️</i>
                    <h3>Construção</h3>
                    <p>Execução com rigor técnico.</p>
                </div>
                <div class="service-card">
                    <i>🛠️</i>
                    <h3>Reformas</h3>
                    <p>Renovação completa de espaços.</p>
                </div>
                <div class="service-card">
                    <i>🌿</i>
                    <h3>Paisagismo</h3>
                    <p>Integração com a natureza.</p>
                </div>
                <div class="service-card">
                    <i>🛋️</i>
                    <h3>Design de Interiores</h3>
                    <p>Ambientação e sofisticação.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section id="projetos">
        <div class="container">
            <div class="portfolio-header">
                <div class="section-title">
                    <h2>Portfólio</h2>
                    <div class="underline"></div>
                </div>
                <button class="btn btn-add-project" id="openAddModal">
                    <span>+</span> Adicionar Projeto
                </button>
            </div>
            <div class="gallery-grid" id="portfolioGrid">
                <!-- Projetos serão carregados aqui via JS -->
            </div>
        </div>
    </section>

    <!-- Add Project Modal -->
    <div class="modal" id="addProjectModal">
        <div class="modal-content">
            <h3>Novo Projeto</h3>
            <form id="addProjectForm">
                <div class="form-group">
                    <label for="projectTitle">Título do Projeto</label>
                    <input type="text" id="projectTitle" placeholder="Ex: Casa Contemporânea" required>
                </div>
                <div class="form-group">
                    <label for="projectImage">URL da Imagem</label>
                    <input type="url" id="projectImage" placeholder="https://images.unsplash.com/..." required>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-cancel" id="closeAddModal">Cancelar</button>
                    <button type="submit" class="btn btn-primary">Salvar Projeto</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Form Section -->
    <section id="agendamento" class="form-section">
        <div class="container">
            <div class="section-title">
                <h2>Agende sua Consultoria</h2>
                <div class="underline"></div>
            </div>
            <div class="form-container">
                <iframe src="https://docs.google.com/forms/d/e/1FAIpQLSedCiDpnDJLEN6UN34AYZkiZEW92YKLfA8W9LUro8XFlHNSVg/viewform?embedded=true" frameborder="0" marginheight="0" marginwidth="0">Carregando…</iframe>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contato">
        <div class="container">
            <div class="footer-grid">
                <div class="footer-info">
                    <span class="footer-logo">IDEARQ Arquitetura e Design</span>
                    <p>Especialistas em transformar ideias em realidade com elegância e sofisticação. Nosso maior projeto é alcançar sua satisfação.</p>
                </div>
                <div class="footer-links">
                    <h4>Navegação</h4>
                    <ul>
                        <li><a href="#inicio">Início</a></li>
                        <li><a href="#servicos">Serviços</a></li>
                        <li><a href="#projetos">Portfólio</a></li>
                    </ul>
                </div>
                <div class="footer-links">
                    <h4>Contato</h4>
                    <ul>
                        <li><span class="emoji">📍</span> Av. T2, 2554, St. Bueno</li>
                        <li><span class="emoji">📞</span> (62) 3251-2122</li>
                        <li><span class="emoji">📧</span> idearprojetosgyn@gmail.com</li>
                        <li><span class="emoji">💬</span> <strong>WhatsApp:</strong></li>
                        <li style="margin-left: 30px;"><a href="https://wa.me/5562998450957" target="_blank">Isac Freitas: (62) 99845-0957</a></li>
                        <li style="margin-left: 30px;"><a href="https://wa.me/5562999532411" target="_blank">Pedro Brasiliano: (62) 99953-2411</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>IDEARQ Arquitetura. Todos os direitos reservados.</p>
            </div>
        </div>
    </footer>

    <script>
        // Mobile Menu Logic
        const openMenu = document.getElementById('openMenu');
        const closeMenu = document.getElementById('closeMenu');
        const mobileOverlay = document.getElementById('mobileOverlay');
        const mobileLinks = document.querySelectorAll('.mobile-link');

        openMenu.addEventListener('click', () => {
            mobileOverlay.classList.add('active');
            document.body.style.overflow = 'hidden';
        });

        const hideMenu = () => {
            mobileOverlay.classList.remove('active');
            document.body.style.overflow = 'auto';
        };

        closeMenu.addEventListener('click', hideMenu);
        mobileLinks.forEach(link => link.addEventListener('click', hideMenu));

        // Smooth Scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });

        // Header Scroll Effect
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 50) {
                header.style.padding = '10px 0';
                header.style.backgroundColor = 'rgba(255, 255, 255, 0.98)';
            } else {
                header.style.padding = '20px 0';
                header.style.backgroundColor = 'var(--white)';
            }
        });

        // Portfolio Logic
        const portfolioGrid = document.getElementById('portfolioGrid');
        const addProjectModal = document.getElementById('addProjectModal');
        const openAddModal = document.getElementById('openAddModal');
        const closeAddModal = document.getElementById('closeAddModal');
        const addProjectForm = document.getElementById('addProjectForm');

        const defaultProjects = [
            { id: 1, title: 'Projeto 1', image: 'https://images.unsplash.com/photo-1618221195710-dd6b41faaea6?auto=format&fit=crop&w=600&q=80' },
            { id: 2, title: 'Projeto 2', image: 'https://images.unsplash.com/photo-1613977257363-707ba9348227?auto=format&fit=crop&w=600&q=80' },
            { id: 3, title: 'Projeto 3', image: 'https://images.unsplash.com/photo-1600607687940-47a04b629733?auto=format&fit=crop&w=600&q=80' },
            { id: 4, title: 'Projeto 4', image: 'https://images.unsplash.com/photo-1600210492486-724fe5c67fb0?auto=format&fit=crop&w=600&q=80' }
        ];

        let projects = JSON.parse(localStorage.getItem('idearq_projects')) || defaultProjects;

        const renderProjects = () => {
            portfolioGrid.innerHTML = '';
            projects.forEach(project => {
                const item = document.createElement('div');
                item.className = 'gallery-item';
                item.innerHTML = `
                    <div class="project-card-overlay">
                        <button class="btn-delete-project" onclick="deleteProject(${project.id})">Excluir</button>
                    </div>
                    <img src="${project.image}" alt="${project.title}" loading="lazy">
                `;
                portfolioGrid.appendChild(item);
            });
        };

        const saveProjects = () => {
            localStorage.setItem('idearq_projects', JSON.stringify(projects));
        };

        window.deleteProject = (id) => {
            if (confirm('Deseja realmente excluir este projeto?')) {
                projects = projects.filter(p => p.id !== id);
                saveProjects();
                renderProjects();
            }
        };

        openAddModal.addEventListener('click', () => addProjectModal.classList.add('active'));
        closeAddModal.addEventListener('click', () => addProjectModal.classList.remove('active'));

        addProjectForm.addEventListener('submit', (e) => {
            e.preventDefault();
            const newProject = {
                id: Date.now(),
                title: document.getElementById('projectTitle').value,
                image: document.getElementById('projectImage').value
            };
            projects.push(newProject);
            saveProjects();
            renderProjects();
            addProjectForm.reset();
            addProjectModal.classList.remove('active');
        });

        renderProjects();
    </script>
</body>
</html>

