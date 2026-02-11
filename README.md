# noticias-uocra
noticias-actualidad-temas de interés
[index.html](https://github.com/user-attachments/files/25245617/index.html)
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CTA - Confederación de Trabajadores Argentinos | Noticias Sindicales</title>
    <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #1a1a2e;
            --secondary: #16213e;
            --accent: #e94560;
            --accent-dark: #c73e54;
            --gold: #ffd700;
            --text-light: #f5f5f5;
            --text-gray: #b8b8b8;
            --bg-dark: #0f0f1a;
            --card-bg: #1e1e2f;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-dark);
            color: var(--text-light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 20px rgba(0,0,0,0.3);
        }

        .header-top {
            background: var(--accent);
            padding: 0.5rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 0.85rem;
        }

        .header-top a {
            color: white;
            text-decoration: none;
            margin-left: 1.5rem;
            transition: opacity 0.3s;
        }

        .header-top a:hover {
            opacity: 0.8;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .logo-icon {
            width: 50px;
            height: 50px;
            background: var(--accent);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1.5rem;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .logo-text h1 {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 2rem;
            letter-spacing: 2px;
            color: var(--gold);
        }

        .logo-text span {
            font-size: 0.8rem;
            color: var(--text-gray);
            display: block;
            margin-top: -5px;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--text-light);
            text-decoration: none;
            font-weight: 500;
            position: relative;
            padding: 0.5rem 0;
            transition: color 0.3s;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent);
            transition: width 0.3s;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .nav-links a:hover {
            color: var(--accent);
        }

        /* Hero Slider */
        .hero-section {
            position: relative;
            height: 600px;
            overflow: hidden;
        }

        .slider-container {
            position: relative;
            height: 100%;
            width: 100%;
        }

        .slide {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0;
            transition: opacity 1s ease-in-out;
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: flex-end;
        }

        .slide.active {
            opacity: 1;
        }

        .slide::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(to top, rgba(15,15,26,0.95) 0%, rgba(15,15,26,0.4) 50%, transparent 100%);
        }

        .slide-content {
            position: relative;
            z-index: 2;
            padding: 3rem;
            max-width: 800px;
            transform: translateY(30px);
            opacity: 0;
            transition: all 0.8s ease 0.3s;
        }

        .slide.active .slide-content {
            transform: translateY(0);
            opacity: 1;
        }

        .category-tag {
            display: inline-block;
            background: var(--accent);
            color: white;
            padding: 0.3rem 1rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            text-transform: uppercase;
            margin-bottom: 1rem;
            letter-spacing: 1px;
        }

        .slide h2 {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 3.5rem;
            line-height: 1.1;
            margin-bottom: 1rem;
            color: white;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        .slide p {
            font-size: 1.2rem;
            color: var(--text-gray);
            margin-bottom: 1.5rem;
        }

        .btn-primary {
            display: inline-block;
            background: var(--accent);
            color: white;
            padding: 1rem 2rem;
            text-decoration: none;
            border-radius: 5px;
            font-weight: 600;
            transition: all 0.3s;
            border: 2px solid var(--accent);
        }

        .btn-primary:hover {
            background: transparent;
            transform: translateY(-2px);
            box-shadow: 0 5px 20px rgba(233, 69, 96, 0.4);
        }

        .slider-dots {
            position: absolute;
            bottom: 2rem;
            right: 3rem;
            display: flex;
            gap: 0.5rem;
            z-index: 10;
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: rgba(255,255,255,0.3);
            cursor: pointer;
            transition: all 0.3s;
        }

        .dot.active {
            background: var(--accent);
            transform: scale(1.2);
        }

        /* News Grid */
        .news-section {
            max-width: 1400px;
            margin: 4rem auto;
            padding: 0 2rem;
        }

        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            border-bottom: 2px solid var(--secondary);
            padding-bottom: 1rem;
        }

        .section-title {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 2.5rem;
            color: var(--gold);
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .section-title::before {
            content: '';
            width: 5px;
            height: 30px;
            background: var(--accent);
        }

        .view-all {
            color: var(--accent);
            text-decoration: none;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            transition: gap 0.3s;
        }

        .view-all:hover {
            gap: 1rem;
        }

        .news-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .news-card {
            background: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
            border: 1px solid rgba(255,255,255,0.05);
        }

        .news-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            border-color: var(--accent);
        }

        .news-image {
            width: 100%;
            height: 220px;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .news-card:hover .news-image {
            transform: scale(1.05);
        }

        .news-content {
            padding: 1.5rem;
        }

        .news-meta {
            display: flex;
            gap: 1rem;
            font-size: 0.85rem;
            color: var(--text-gray);
            margin-bottom: 0.5rem;
        }

        .news-meta span {
            display: flex;
            align-items: center;
            gap: 0.3rem;
        }

        .news-card h3 {
            font-size: 1.3rem;
            margin-bottom: 0.8rem;
            line-height: 1.3;
            color: white;
            transition: color 0.3s;
        }

        .news-card:hover h3 {
            color: var(--accent);
        }

        .news-excerpt {
            color: var(--text-gray);
            font-size: 0.95rem;
            line-height: 1.5;
        }

        /* Alliances Section */
        .alliances-section {
            background: linear-gradient(135deg, var(--secondary) 0%, var(--primary) 100%);
            padding: 4rem 2rem;
            margin-top: 4rem;
        }

        .alliances-container {
            max-width: 1400px;
            margin: 0 auto;
        }

        .alliances-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .alliance-card {
            background: rgba(255,255,255,0.03);
            border: 1px solid rgba(255,255,255,0.1);
            border-radius: 10px;
            padding: 2rem;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .alliance-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
            transition: left 0.5s;
        }

        .alliance-card:hover::before {
            left: 100%;
        }

        .alliance-card:hover {
            transform: translateY(-5px);
            border-color: var(--accent);
            background: rgba(255,255,255,0.05);
        }

        .alliance-logo {
            width: 60px;
            height: 60px;
            background: var(--accent);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }

        .alliance-card h4 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: var(--gold);
        }

        .alliance-card p {
            color: var(--text-gray);
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .alliance-link {
            color: var(--accent);
            text-decoration: none;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 0.9rem;
        }

        /* Footer */
        footer {
            background: var(--bg-dark);
            border-top: 1px solid var(--secondary);
            padding: 3rem 2rem 1rem;
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
        }

        .footer-section h4 {
            color: var(--gold);
            margin-bottom: 1.5rem;
            font-family: 'Bebas Neue', sans-serif;
            font-size: 1.5rem;
            letter-spacing: 1px;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 0.8rem;
        }

        .footer-section a {
            color: var(--text-gray);
            text-decoration: none;
            transition: color 0.3s;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .footer-section a:hover {
            color: var(--accent);
            padding-left: 5px;
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-icon {
            width: 40px;
            height: 40px;
            background: var(--secondary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
            cursor: pointer;
        }

        .social-icon:hover {
            background: var(--accent);
            transform: translateY(-3px);
        }

        .footer-bottom {
            max-width: 1400px;
            margin: 3rem auto 0;
            padding-top: 2rem;
            border-top: 1px solid var(--secondary);
            text-align: center;
            color: var(--text-gray);
            font-size: 0.9rem;
        }

        /* Mobile Menu */
        .menu-toggle {
            display: none;
            flex-direction: column;
            cursor: pointer;
            gap: 5px;
        }

        .menu-toggle span {
            width: 25px;
            height: 3px;
            background: white;
            transition: all 0.3s;
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .menu-toggle {
                display: flex;
            }
            
            .hero-section {
                height: 500px;
            }
            
            .slide h2 {
                font-size: 2rem;
            }
            
            .news-grid {
                grid-template-columns: 1fr;
            }
            
            .header-top {
                display: none;
            }
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

        .animate-in {
            animation: fadeInUp 0.6s ease forwards;
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <div class="header-top">
            <span>📞 Línea directa: 0800-999-9999 | ✉️ contacto@cta.org.ar</span>
            <div>
                <a href="#">Acceso Afiliados</a>
                <a href="#">Prensa</a>
                <a href="#">Contacto</a>
            </div>
        </div>
        <nav>
            <div class="logo">
                <div class="logo-icon">CTA</div>
                <div class="logo-text">
                    <h1>CTA</h1>
                    <span>Confederación de Trabajadores Argentinos</span>
                </div>
            </div>
            <ul class="nav-links">
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#noticias">Noticias</a></li>
                <li><a href="#institucional">Institucional</a></li>
                <li><a href="#derechos">Derechos Laborales</a></li>
                <li><a href="#capacitacion">Capacitación</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
            <div class="menu-toggle">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </nav>
    </header>

    <!-- Hero Slider -->
    <section class="hero-section" id="inicio">
        <div class="slider-container">
            <div class="slide active" style="background-image: url('https://images.unsplash.com/photo-1521737604893-d14cc237f11d?w=1200');">
                <div class="slide-content">
                    <span class="category-tag">Negociación Colectiva</span>
                    <h2>NUEVO ACUERDO SALARIAL PARA EL SECTOR CONSTRUCCIÓN</h2>
                    <p>Se firmó un aumento del 45% en tres cuotas para los trabajadores de la construcción, garantizando la paritaria más alta del año.</p>
                    <a href="#" class="btn-primary">Leer Noticia Completa →</a>
                </div>
            </div>
            <div class="slide" style="background-image: url('https://images.unsplash.com/photo-1577962917302-cd874c4e31d2?w=1200');">
                <div class="slide-content">
                    <span class="category-tag">Seguridad Laboral</span>
                    <h2>JORNADA DE CAPACITACIÓN EN PREVENCIÓN DE RIESGOS</h2>
                    <p>Más de 500 delegados participaron de la jornada sobre nuevas normativas de seguridad en altura y trabajos eléctricos.</p>
                    <a href="#" class="btn-primary">Ver Galería →</a>
                </div>
            </div>
            <div class="slide" style="background-image: url('https://images.unsplash.com/photo-1556761175-5973dc0f32e7?w=1200');">
                <div class="slide-content">
                    <span class="category-tag">Solidaridad</span>
                    <h2>CAMPAÑA DE AYUDA PARA TRABAJADORES AFECTADOS</h2>
                    <p>La organización lanza programa de asistencia integral para familias de trabajadores damnificados por las inundaciones.</p>
                    <a href="#" class="btn-primary">Sumate a la Campaña →</a>
                </div>
            </div>
        </div>
        <div class="slider-dots">
            <span class="dot active" onclick="currentSlide(0)"></span>
            <span class="dot" onclick="currentSlide(1)"></span>
            <span class="dot" onclick="currentSlide(2)"></span>
        </div>
    </section>

    <!-- News Grid -->
    <section class="news-section" id="noticias">
        <div class="section-header">
            <h2 class="section-title">ÚLTIMAS NOTICIAS</h2>
            <a href="#" class="view-all">Ver todas las noticias →</a>
        </div>
        
        <div class="news-grid">
            <article class="news-card">
                <img src="https://images.unsplash.com/photo-1541888946425-d81bb19240f5?w=600" alt="Obra pública" class="news-image">
                <div class="news-content">
                    <div class="news-meta">
                        <span>📅 12 Feb 2026</span>
                        <span>🏷️ Obras Públicas</span>
                    </div>
                    <h3>Reactivación de obras públicas generará 50.000 puestos de trabajo</h3>
                    <p class="news-excerpt">El gobierno anunció la reactivación de 120 obras paralizadas que generarán miles de puestos de trabajo registrados...</p>
                </div>
            </article>

            <article class="news-card">
                <img src="https://images.unsplash.com/photo-1517245386807-bb43f82c33c4?w=600" alt="Reunión sindical" class="news-image">
                <div class="news-content">
                    <div class="news-meta">
                        <span>📅 11 Feb 2026</span>
                        <span>🏷️ Gremial</span>
                    </div>
                    <h3>Encuentro Nacional de Delegados: fortaleciendo la representación</h3>
                    <p class="news-excerpt">Más de 2000 delegados de todo el país participaron del encuentro anual para debatir estrategias sindicales...</p>
                </div>
            </article>

            <article class="news-card">
                <img src="https://images.unsplash.com/photo-1450101499163-c8848c66ca85?w=600" alt="Derechos laborales" class="news-image">
                <div class="news-content">
                    <div class="news-meta">
                        <span>📅 10 Feb 2026</span>
                        <span>🏷️ Legal</span>
                    </div>
                    <h3>Nueva ley de ART: mayores coberturas para trabajadores</h3>
                    <p class="news-excerpt">Se sancionó la reforma integral de la Ley de Riesgos del Trabajo aumentando las indemnizaciones...</p>
                </div>
            </article>

            <article class="news-card">
                <img src="https://images.unsplash.com/photo-1551836022-d5d88e9218df?w=600" alt="Capacitación" class="news-image">
                <div class="news-content">
                    <div class="news-meta">
                        <span>📅 09 Feb 2026</span>
                        <span>🏷️ Capacitación</span>
                    </div>
                    <h3>Abren inscripciones para cursos de oficios gratuitos</h3>
                    <p class="news-excerpt">Electricidad, plomería, albañilería y más: 5000 vacantes disponibles para trabajadores y familiares...</p>
                </div>
            </article>

            <article class="news-card">
                <img src="https://images.unsplash.com/photo-1521791136064-7986c2920216?w=600" alt="Mujeres trabajadoras" class="news-image">
                <div class="news-content">
                    <div class="news-meta">
                        <span>📅 08 Feb 2026</span>
                        <span>🏷️ Diversidad</span>
                    </div>
                    <h3>Día de la Mujer Trabajadora: reconocimiento a la construcción</h3>
                    <p class="news-excerpt">Homenaje a las mujeres que desafían estereotipos en la industria de la construcción...</p>
                </div>
            </article>

            <article class="news-card">
                <img src="https://images.unsplash.com/photo-1507679799987-c73779587ccf?w=600" alt="Vivienda" class="news-image">
                <div class="news-content">
                    <div class="news-meta">
                        <span>📅 07 Feb 2026</span>
                        <span>🏷️ Vivienda</span>
                    </div>
                    <h3>Plan Pro.Cre.Ar: nuevos sorteos para trabajadores registrados</h3>
                    <p class="news-excerpt">El sindicato gestionó 1000 cupos prioritarios para afiliados con antigüedad en el gremio...</p>
                </div>
            </article>
        </div>
    </section>

    <!-- Alliances Section -->
    <section class="alliances-section" id="institucional">
        <div class="alliances-container">
            <div class="section-header" style="border-bottom-color: rgba(255,255,255,0.1);">
                <h2 class="section-title">ALIANZAS INTERNACIONALES</h2>
            </div>
            
            <div class="alliances-grid">
                <div class="alliance-card">
                    <div class="alliance-logo">OIT</div>
                    <h4>Organización Internacional del Trabajo</h4>
                    <p>Promueve la justicia social y los derechos humanos y laborales reconocidos a nivel internacional.</p>
                    <a href="https://www.ilo.org" target="_blank" class="alliance-link">Visitar sitio →</a>
                </div>

                <div class="alliance-card">
                    <div class="alliance-logo">CSA</div>
                    <h4>Confederación Sindical de las Américas</h4>
                    <p>Expresión sindical regional más importante del continente americano.</p>
                    <a href="https://www.csa-csi.org" target="_blank" class="alliance-link">Visitar sitio →</a>
                </div>

                <div class="alliance-card">
                    <div class="alliance-logo">CSI</div>
                    <h4>Confederación Sindical Internacional</h4>
                    <p>Promueve y defiende los derechos de los trabajadores impulsando cooperación internacional.</p>
                    <a href="https://www.ituc-csi.org" target="_blank" class="alliance-link">Visitar sitio →</a>
                </div>

                <div class="alliance-card">
                    <div class="alliance-logo">BWI</div>
                    <h4>Building and Wood Workers' International</h4>
                    <p>Desarrollo de sindicatos en industrias de construcción y madera a nivel mundial.</p>
                    <a href="https://www.bwint.org" target="_blank" class="alliance-link">Visitar sitio →</a>
                </div>

                <div class="alliance-card">
                    <div class="alliance-logo">IERIC</div>
                    <h4>Instituto de Estadística de la Construcción</h4>
                    <p>Dinamiza la operatividad y eficiencia del sector construcción mediante estadísticas.</p>
                    <a href="#" class="alliance-link">Visitar sitio →</a>
                </div>

                <div class="alliance-card">
                    <div class="alliance-logo">SEGIB</div>
                    <h4>Secretaría General Iberoamericana</h4>
                    <p>Promueve el bienestar económico y social de los países iberoamericanos.</p>
                    <a href="https://www.segib.org" target="_blank" class="alliance-link">Visitar sitio →</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contacto">
        <div class="footer-content">
            <div class="footer-section">
                <h4>INSTITUCIONAL</h4>
                <ul>
                    <li><a href="#">Historia del Gremio</a></li>
                    <li><a href="#">Autoridades</a></li>
                    <li><a href="#">Estatuto y Reglamento</a></li>
                    <li><a href="#">Sede Central</a></li>
                    <li><a href="#">Delegaciones</a></li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h4>SERVICIOS</h4>
                <ul>
                    <li><a href="#">Asesoramiento Legal</a></li>
                    <li><a href="#">Capacitación</a></li>
                    <li><a href="#">Obra Social</a></li>
                    <li><a href="#">Turismo y Recreación</a></li>
                    <li><a href="#">Créditos y Beneficios</a></li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h4>PRENSA</h4>
                <ul>
                    <li><a href="#">Comunicados Oficiales</a></li>
                    <li><a href="#">Galería de Fotos</a></li>
                    <li><a href="#">Videos Institucionales</a></li>
                    <li><a href="#">Revista del Trabajador</a></li>
                    <li><a href="#">Newsletter</a></li>
                </ul>
            </div>
            
            <div class="footer-section">
                <h4>CONTACTO</h4>
                <ul>
                    <li><a href="#">📍 Av. Corrientes 1234, CABA</a></li>
                    <li><a href="#">📞 011 4567-8900</a></li>
                    <li><a href="#">✉️ info@cta.org.ar</a></li>
                    <li><a href="#">🕐 Lunes a Viernes: 9-18hs</a></li>
                </ul>
                <div class="social-links">
                    <div class="social-icon">f</div>
                    <div class="social-icon">t</div>
                    <div class="social-icon">in</div>
                    <div class="social-icon">ig</div>
                    <div class="social-icon">yt</div>
                </div>
            </div>
        </div>
        
        <div class="footer-bottom">
            <p>© 2026 Confederación de Trabajadores Argentinos. Todos los derechos reservados. | <a href="#" style="color: var(--text-gray);">Política de Privacidad</a> | <a href="#" style="color: var(--text-gray);">Términos de Uso</a></p>
        </div>
    </footer>

    <script>
        // Slider functionality
        let currentIndex = 0;
        const slides = document.querySelectorAll('.slide');
        const dots = document.querySelectorAll('.dot');

        function showSlide(index) {
            slides.forEach((slide, i) => {
                slide.classList.remove('active');
                dots[i].classList.remove('active');
                if (i === index) {
                    slide.classList.add('active');
                    dots[i].classList.add('active');
                }
            });
        }

        function currentSlide(index) {
            currentIndex = index;
            showSlide(currentIndex);
        }

        function nextSlide() {
            currentIndex = (currentIndex + 1) % slides.length;
            showSlide(currentIndex);
        }

        // Auto-advance slider every 5 seconds
        setInterval(nextSlide, 5000);

        // Smooth scroll for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: "0px 0px -50px 0px"
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('animate-in');
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        // Observe news cards
        document.querySelectorAll('.news-card').forEach((card, index) => {
            card.style.opacity = '0';
            card.style.animationDelay = $;{'index * 0.1'}s;
            observer.observe(card);
        });

        // Observe alliance cards
        document.querySelectorAll('.alliance-card').forEach((card, index) => {
            card.style.opacity = '0';
            card.style.animationDelay = $;{index * 0.1}s;
            observer.observe(card);
        });
    </script>
</body>
</html>
