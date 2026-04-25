<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FC Consultadoria - Soluções Estratégicas para o Seu Negócio</title>
    <meta name="description" content="FC Consultadoria - Soluções estratégicas personalizadas para crescimento sustentável do seu negócio. Consultoria estratégica, gestão de equipas e transformação digital em Portugal.">
    <meta name="keywords" content="consultoria estratégica, consultoria Portugal, gestão equipas, transformação digital, consultoria Porto, estratégia empresarial">
    <link rel="canonical" href="https://fcconsultadoria.pt">
    
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- EmailJS -->
    <script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: #333;
        }

        /* Header */
        header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(20px);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            padding: 1rem 0;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a.active {
            color: #667eea;
        }

        .nav-links a.active::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .nav-links a:hover {
            color: #667eea;
        }

        .cta-button {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 0.8rem 2rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: transform 0.3s ease;
        }

        .cta-button:hover {
            transform: translateY(-2px);
        }

        /* Mobile Menu */
        .mobile-menu {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .mobile-menu span {
            width: 25px;
            height: 3px;
            background: #333;
            margin: 3px 0;
            transition: 0.3s;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 120px 2rem 80px;
            text-align: center;
            overflow: hidden;
        }

        .hero-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 5vw, 4rem);
            font-weight: 700;
            margin-bottom: 1.5rem;
            opacity: 0;
            animation: fadeInUp 1s ease forwards;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2.5rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            opacity: 0;
            animation: fadeInUp 1s ease 0.2s forwards;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            opacity: 0;
            animation: fadeInUp 1s ease 0.4s forwards;
        }

        .btn-primary {
            background: white;
            color: #667eea;
            padding: 1rem 2.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .btn-secondary {
            background: transparent;
            color: white;
            padding: 1rem 2.5rem;
            border: 2px solid white;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .btn-primary:hover, .btn-secondary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        /* Services Section */
        .services {
            padding: 100px 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 4rem;
            color: #333;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .service-card {
            background: white;
            padding: 2.5rem;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
            text-align: center;
            transition: all 0.3s ease;
            border-top: 4px solid transparent;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(0,0,0,0.15);
            border-top-color: #667eea;
        }

        .service-icon {
            font-size: 3rem;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1.5rem;
        }

        .service-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #333;
        }

        /* Testimonials Section */
        .testimonials {
            background: #f8f9ff;
            padding: 100px 2rem;
        }

        .testimonials-grid {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .testimonial-card {
            background: white;
            padding: 2.5rem;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
            text-align: center;
            position: relative;
        }

        .testimonial-card::before {
            content: '"';
            font-size: 4rem;
            color: #667eea;
            position: absolute;
            top: 20px;
            left: 30px;
            opacity: 0.3;
            font-family: serif;
        }

        .testimonial-text {
            font-style: italic;
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
        }

        .testimonial-author {
            font-weight: 600;
            color: #333;
        }

        /* Contact Section */
        .contact {
            padding: 100px 2rem;
        }

        .contact-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .contact-info h2 {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            color: #333;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
            gap: 1rem;
        }

        .contact-item i {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
        }

        .contact-form {
            background: white;
            padding: 2.5rem;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid #e1e5e9;
            border-radius: 12px;
            font-family: inherit;
            transition: border-color 0.3s ease;
            font-size: 1rem;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #667eea;
            box-shadow: 0 0 0 3px rgba(102, 126, 234, 0.1);
        }

        .submit-btn {
            width: 100%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 1rem;
            border: none;
            border-radius: 12px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.4);
        }

        .submit-btn:disabled {
            opacity: 0.7;
            cursor: not-allowed;
            transform: none;
        }

        /* Footer */
        footer {
            background: #1a1a2e;
            color: white;
            text-align: center;
            padding: 3rem 2rem 1.5rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            color: #667eea;
        }

        .footer-section a {
            color: #ccc;
            text-decoration: none;
            display: block;
            margin-bottom: 0.5rem;
            transition: color 0.3s ease;
        }

        .footer-section a:hover {
            color: #667eea;
        }

        .footer-bottom {
            border-top: 1px solid #333;
            padding-top: 1.5rem;
            opacity: 0.8;
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

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .nav-links.active {
                display: flex !important;
                position: fixed;
                top: 70px;
                left: 0;
                width: 100%;
                background: rgba(255,255,255,0.98);
                flex-direction: column;
                padding: 2rem;
                box-shadow: 0 10px 30px rgba(0,0,0,0.1);
                backdrop-filter: blur(20px);
            }

            .mobile-menu {
                display: flex;
            }

            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }

            .contact-content {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .services-grid,
            .testimonials-grid {
                grid-template-columns: 1fr;
            }

            .mobile-menu.open span:nth-child(1) { 
                transform: rotate(45deg) translate(5px, 5px); 
            }
            .mobile-menu.open span:nth-child(2) { 
                opacity: 0; 
            }
            .mobile-menu.open span:nth-child(3) { 
                transform: rotate(-45deg) translate(7px, -6px); 
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <div class="logo">FC Consultadoria</div>
            <ul class="nav-links">
                <li><a href="#home">Início</a></li>
                <li><a href="#services">Serviços</a></li>
                <li><a href="#testimonials">Testemunhos</a></li>
                <li><a href="#contact">Contacto</a></li>
            </ul>
            <a href="#contact" class="cta-button">Fale Connosco</a>
            <div class="mobile-menu">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Transformamos Negócios com Estratégia e Inovação</h1>
            <p>Soluções personalizadas de consultoria estratégica para impulsionar o crescimento sustentável do seu negócio.</p>
            <div class="hero-buttons">
                <a href="#contact" class="btn-primary">Começar Agora</a>
                <a href="#services" class="btn-secondary">Ver Serviços</a>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services">
        <h2 class="section-title">Os Nossos Serviços</h2>
        <div class="services-grid">
            <div class="service-card">
                <div class="service-icon">
                    <i class="fas fa-chart-line"></i>
                </div>
                <h3>Consultoria Estratégica</h3>
                <p>Desenvolvimento de planos estratégicos personalizados para maximizar resultados e crescimento sustentável.</p>
            </div>
            <div class="service-card">
                <div class="service-icon">
                    <i class="fas fa-users"></i>
                </div>
                <h3>Gestão de Equipas</h3>
                <p>Otimização de processos e desenvolvimento de liderança para equipes de alto desempenho.</p>
            </div>
            <div class="service-card">
                <div class="service-icon">
                    <i class="fas fa-lightbulb"></i>
                </div>
                <h3>Inovação & Transformação</h3>
                <p>Implementação de tecnologias e processos inovadores para transformação digital.</p>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section id="testimonials" class="testimonials">
        <h2 class="section-title">O que dizem os nossos clientes</h2>
        <div class="testimonials-grid">
            <div class="testimonial-card">
                <p class="testimonial-text">"A FC Consultadoria transformou completamente a nossa estratégia. Resultados incríveis em apenas 6 meses!"</p>
                <div class="testimonial-author">- João Silva, CEO TechNova</div>
            </div>
            <div class="testimonial-card">
                <p class="testimonial-text">"Profissionais excecionais. Ajudaram-nos a otimizar a nossa equipa e aumentar a produtividade em 40%."</p>
                <div class="testimonial-author">- Maria Santos, Diretora de RH, AgroIndústria</div>
            </div>
            <div class="testimonial-card">
                <p class="testimonial-text">"A transformação digital que implementaram está a dar frutos. Recomendo 100%!"</p>
                <div class="testimonial-author">- Pedro Costa, CTO, FinTech Solutions</div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="contact-content">
            <div class="contact-info">
                <h2>Fale Connosco</h2>
                <p>Precisa de consultoria especializada? Estamos aqui para ajudar.</p>
                
                <!-- 👇 ATUALIZE AQUI COM OS SEUS DADOS REAIS 👇 -->
                <div class="contact-item">
                    <i class="fas fa-map-marker-alt"></i>
                    <div>
                        <strong>Morada</strong><br>
                        Rua Exemplo, 123<br>
                        4000-000 Porto, Portugal
                    </div>
                </div>
                <div class="contact-item">
                    <i class="fas fa-phone"></i>
                  
