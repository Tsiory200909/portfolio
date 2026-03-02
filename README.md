<!DOCTYPE html>
<html lang="fr">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio - Design Bleu Animé</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            color: #fff;
            background: linear-gradient(135deg, #0a192f 0%, #1a3650 50%, #2a4a6e 100%);
            min-height: 100vh;
        }

        /* Navigation */
        nav {
            padding: 2rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            animation: slideDown 0.8s ease-out;
        }

        @keyframes slideDown {
            from {
                transform: translateY(-100%);
                opacity: 0;
            }

            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 300;
            letter-spacing: 2px;
            color: #fff;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.3);
            position: relative;
            overflow: hidden;
        }

        .logo::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: -100%;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, #fff, transparent);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% {
                left: -100%;
            }

            20% {
                left: 100%;
            }

            100% {
                left: 100%;
            }
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
        }

        .nav-links a {
            text-decoration: none;
            color: rgba(255, 255, 255, 0.8);
            font-weight: 400;
            font-size: 0.95rem;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a::before {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #64b5f6;
            transition: width 0.3s ease;
        }

        .nav-links a:hover {
            color: #fff;
            transform: translateY(-2px);
        }

        .nav-links a:hover::before {
            width: 100%;
        }

        /* Container principal */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 5%;
        }

        /* Section Hero */
        .hero {
            min-height: 80vh;
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 4rem;
            padding: 2rem 0;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero-content {
            flex: 1;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            font-weight: 300;
            line-height: 1.2;
            margin-bottom: 1.5rem;
            color: #fff;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {

            0%,
            100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-10px);
            }
        }

        .hero-content .highlight {
            font-weight: 500;
            color: #64b5f6;
            text-shadow: 0 0 15px rgba(100, 181, 246, 0.5);
            position: relative;
            display: inline-block;
        }

        .hero-content .highlight::after {
            content: '';
            position: absolute;
            width: 100%;
            height: 30%;
            bottom: 0;
            left: 0;
            background: rgba(100, 181, 246, 0.2);
            z-index: -1;
            transform: scaleX(0);
            transform-origin: right;
            animation: reveal 1s ease-out 1s forwards;
        }

        @keyframes reveal {
            to {
                transform: scaleX(1);
            }
        }

        .hero-content p {
            font-size: 1.1rem;
            color: rgba(255, 255, 255, 0.8);
            margin-bottom: 2rem;
            max-width: 500px;
            animation: slideInLeft 1s ease-out 0.6s both;
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

        .hero-image {
            flex: 1;
            display: flex;
            justify-content: center;
            animation: rotateIn 1s ease-out 0.9s both;
        }

        @keyframes rotateIn {
            from {
                opacity: 0;
                transform: rotate(-10deg) scale(0.9);
            }

            to {
                opacity: 1;
                transform: rotate(0) scale(1);
            }
        }

        .hero-image img {
            width: 100%;
            max-width: 400px;
            border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
            background: linear-gradient(135deg, #64b5f6, #1976d2);
            box-shadow: 0 20px 40px -15px rgba(0, 0, 0, 0.3),
                0 0 30px rgba(100, 181, 246, 0.3);
            transition: all 0.5s ease;
            animation: pulse 3s ease-in-out infinite;
        }

        @keyframes pulse {

            0%,
            100% {
                transform: scale(1);
            }

            50% {
                transform: scale(1.02);
            }
        }

        .hero-image img:hover {
            transform: scale(1.05) rotate(2deg);
            box-shadow: 0 30px 50px -15px rgba(0, 0, 0, 0.4),
                0 0 40px rgba(100, 181, 246, 0.5);
        }

        /* Boutons */
        .btn {
            display: inline-block;
            padding: 0.8rem 2rem;
            text-decoration: none;
            border-radius: 30px;
            font-weight: 400;
            transition: all 0.3s ease;
            margin-right: 1rem;
            position: relative;
            overflow: hidden;
            z-index: 1;
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
            z-index: -1;
        }

        .btn:hover::before {
            left: 100%;
        }

        .btn-primary {
            background-color: #1976d2;
            color: white;
            border: 1px solid #1976d2;
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {

            0%,
            100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-5px);
            }
        }

        .btn-primary:hover {
            background-color: #1565c0;
            transform: translateY(-2px) scale(1.05);
            box-shadow: 0 10px 20px -8px rgba(25, 118, 210, 0.5);
        }

        .btn-outline {
            border: 1px solid #64b5f6;
            color: #64b5f6;
            background: transparent;
        }

        .btn-outline:hover {
            background-color: #64b5f6;
            color: #0a192f;
            transform: translateY(-2px) scale(1.05);
            box-shadow: 0 10px 20px -8px rgba(100, 181, 246, 0.3);
        }

        /* Section À propos */
        .about {
            padding: 6rem 0;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 30px;
            margin: 2rem 0;
            animation: fadeInScale 1s ease-out;
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

        .section-title {
            font-size: 2.5rem;
            font-weight: 300;
            text-align: center;
            margin-bottom: 3rem;
            color: #fff;
            text-shadow: 0 0 10px rgba(100, 181, 246, 0.3);
            animation: glitch 5s infinite;
        }

        @keyframes glitch {

            0%,
            100% {
                transform: skew(0deg, 0deg);
            }

            95% {
                transform: skew(0deg, 0deg);
            }

            96% {
                transform: skew(5deg, 2deg);
            }

            97% {
                transform: skew(-5deg, -2deg);
            }

            98% {
                transform: skew(3deg, 1deg);
            }
        }

        .section-title span {
            font-weight: 500;
            color: #64b5f6;
        }

        .about-content {
            max-width: 800px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .about-text {
            font-size: 1.2rem;
            color: rgba(255, 255, 255, 0.9);
            margin-bottom: 3rem;
            text-align: center;
            line-height: 1.8;
        }

        .about-highlight {
            background: linear-gradient(135deg, #64b5f6, #1976d2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 600;
            font-size: 1.4rem;
            position: relative;
            display: inline-block;
        }

        .bio-section {
            margin: 3rem 0;
            animation: slideInRight 1s ease-out;
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

        .bio-section h3 {
            font-size: 1.5rem;
            font-weight: 400;
            color: #64b5f6;
            margin-bottom: 1.5rem;
            text-align: center;
            position: relative;
        }

        .bio-section h3::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 50px;
            height: 2px;
            background: linear-gradient(90deg, transparent, #64b5f6, transparent);
        }

        .bio-section p {
            color: rgba(255, 255, 255, 0.8);
            margin-bottom: 1.5rem;
            line-height: 1.8;
            text-align: center;
            font-size: 1.1rem;
        }

        .passions {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            justify-content: center;
            margin: 3rem 0;
        }

        .passion-tag {
            background: rgba(255, 255, 255, 0.1);
            padding: 0.8rem 1.5rem;
            border-radius: 30px;
            font-size: 1rem;
            color: #fff;
            transition: all 0.3s ease;
            border: 1px solid rgba(100, 181, 246, 0.3);
            backdrop-filter: blur(5px);
            animation: fadeInTags 0.5s ease-out forwards;
            opacity: 0;
        }

        .passion-tag:nth-child(1) {
            animation-delay: 0.1s;
        }

        .passion-tag:nth-child(2) {
            animation-delay: 0.2s;
        }

        .passion-tag:nth-child(3) {
            animation-delay: 0.3s;
        }

        .passion-tag:nth-child(4) {
            animation-delay: 0.4s;
        }

        .passion-tag:nth-child(5) {
            animation-delay: 0.5s;
        }

        .passion-tag:nth-child(6) {
            animation-delay: 0.6s;
        }

        .passion-tag:nth-child(7) {
            animation-delay: 0.7s;
        }

        .passion-tag:nth-child(8) {
            animation-delay: 0.8s;
        }

        @keyframes fadeInTags {
            from {
                opacity: 0;
                transform: translateY(20px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .passion-tag:hover {
            background: #64b5f6;
            color: #0a192f;
            transform: scale(1.05) rotate(2deg);
            box-shadow: 0 5px 15px rgba(100, 181, 246, 0.3);
            border-color: #64b5f6;
        }

        .quote {
            font-style: italic;
            font-size: 1.2rem;
            color: #64b5f6;
            text-align: center;
            margin: 3rem 0;
            padding: 2rem;
            border-top: 1px solid rgba(100, 181, 246, 0.3);
            border-bottom: 1px solid rgba(100, 181, 246, 0.3);
            position: relative;
            animation: glow 3s ease-in-out infinite;
        }

        @keyframes glow {

            0%,
            100% {
                text-shadow: 0 0 10px rgba(100, 181, 246, 0.3);
            }

            50% {
                text-shadow: 0 0 20px rgba(100, 181, 246, 0.6);
            }
        }

        .quote-author {
            display: block;
            margin-top: 1rem;
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.6);
            font-style: normal;
        }

        /* Section Compétences */
        .skills {
            padding: 4rem 0;
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(5px);
            border-radius: 30px;
            animation: fadeIn 1s ease-out;
        }

        .skills-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1rem;
            max-width: 600px;
            margin: 0 auto;
        }

        .skill-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 0.8rem 1.5rem;
            border-radius: 30px;
            font-size: 0.95rem;
            color: #fff;
            border: 1px solid rgba(100, 181, 246, 0.3);
            transition: all 0.3s ease;
            cursor: default;
            animation: float 3s ease-in-out infinite;
        }

        .skill-item:nth-child(odd) {
            animation-delay: 0.2s;
        }

        .skill-item:hover {
            transform: scale(1.1) translateY(-5px);
            background: #64b5f6;
            color: #0a192f;
            box-shadow: 0 10px 20px rgba(100, 181, 246, 0.3);
            border-color: #64b5f6;
        }

        /* Section Contact */
        .contact {
            padding: 6rem 0;
            background: linear-gradient(135deg, rgba(25, 118, 210, 0.1) 0%, rgba(100, 181, 246, 0.1) 100%);
            backdrop-filter: blur(10px);
            border-radius: 30px;
            margin: 2rem 0;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            max-width: 1000px;
            margin: 3rem auto;
        }

        .contact-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 2.5rem 2rem;
            border-radius: 20px;
            text-align: center;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(100, 181, 246, 0.2);
            transition: all 0.3s ease;
            animation: slideUp 0.5s ease-out forwards;
            opacity: 0;
            transform: translateY(30px);
        }

        .contact-card:nth-child(1) {
            animation-delay: 0.2s;
        }

        .contact-card:nth-child(2) {
            animation-delay: 0.4s;
        }

        .contact-card:nth-child(3) {
            animation-delay: 0.6s;
        }

        @keyframes slideUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .contact-card:hover {
            transform: translateY(-15px) scale(1.02);
            border-color: #64b5f6;
            box-shadow: 0 20px 30px rgba(0, 0, 0, 0.3),
                0 0 30px rgba(100, 181, 246, 0.2);
        }

        .contact-icon {
            font-size: 3rem;
            margin-bottom: 1.5rem;
            display: inline-block;
            background: rgba(255, 255, 255, 0.1);
            padding: 1rem;
            border-radius: 60px;
            line-height: 1;
            animation: rotate 10s linear infinite;
        }

        @keyframes rotate {
            from {
                transform: rotate(0deg);
            }

            to {
                transform: rotate(360deg);
            }
        }

        .contact-card h3 {
            font-size: 1.5rem;
            font-weight: 500;
            color: #64b5f6;
            margin-bottom: 1rem;
        }

        .contact-card p {
            color: rgba(255, 255, 255, 0.8);
            margin-bottom: 1.5rem;
            font-size: 1rem;
        }

        .contact-link {
            display: inline-block;
            padding: 0.8rem 2rem;
            background: transparent;
            color: #fff;
            text-decoration: none;
            border-radius: 30px;
            font-size: 0.95rem;
            transition: all 0.3s ease;
            border: 1px solid #64b5f6;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }

        .contact-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(100, 181, 246, 0.3), transparent);
            transition: left 0.5s ease;
            z-index: -1;
        }

        .contact-link:hover::before {
            left: 100%;
        }

        .contact-link:hover {
            background: #64b5f6;
            color: #0a192f;
            transform: scale(1.05);
            box-shadow: 0 0 20px rgba(100, 181, 246, 0.5);
        }

        .contact-info-supplementaire {
            text-align: center;
            margin-top: 3rem;
            padding: 2rem;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            border: 1px solid rgba(100, 181, 246, 0.2);
        }

        .disponibilite {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            color: #64b5f6;
            margin-top: 1rem;
        }

        .disponibilite span {
            display: inline-block;
            width: 12px;
            height: 12px;
            background: #64b5f6;
            border-radius: 50%;
            animation: pulse 2s infinite;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 3rem;
        }

        .social-links a {
            text-decoration: none;
            color: rgba(255, 255, 255, 0.8);
            font-size: 1.1rem;
            transition: all 0.3s ease;
            position: relative;
        }

        .social-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 1px;
            background: #64b5f6;
            transition: width 0.3s ease;
        }

        .social-links a:hover {
            color: #64b5f6;
            transform: translateY(-3px);
        }

        .social-links a:hover::after {
            width: 100%;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 2rem 0;
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.9rem;
            border-top: 1px solid rgba(100, 181, 246, 0.2);
        }

        /* Responsive */
        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                gap: 1rem;
                padding: 1rem 5%;
            }

            .hero {
                flex-direction: column;
                text-align: center;
                min-height: auto;
                gap: 2rem;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .hero-content p {
                margin-left: auto;
                margin-right: auto;
            }

            .nav-links {
                gap: 1.5rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .btn {
                display: block;
                margin: 1rem 0;
            }

            .btn-primary {
                margin-right: 0;
            }

            .about-content {
                padding: 0 1rem;
            }

            .contact-card {
                padding: 2rem 1rem;
            }
        }
    </style>
</head>

<body>
    <nav>
        <div class="logo">MON PORTFOLIO</div>
        <div class="nav-links">
            <a href="#about">À propos</a>
            <a href="#skills">Compétences</a>
            <a href="#contact">Contact</a>
        </div>
    </nav>

    <main>
        <!-- Section Héro -->
        <section class="hero container">
            <div class="hero-content">
                <h1>
                    <span class="highlight">Découvrez</span> qui je suis<br>
                    et ce qui me passionne
                </h1>
                <p>
                    Bienvenue dans mon univers créatif. Je suis développeur
                    et designer passionné par la création d'expériences
                    numériques uniques et significatives.
                </p>
                <a href="#about" class="btn btn-primary">En savoir plus</a>
                <a href="#contact" class="btn btn-outline">Me contacter</a>
            </div>
            <div class="hero-image">
                <img src="https://scontent.ftnr2-2.fna.fbcdn.net/v/t39.30808-1/645375205_122112962919211419_7326047931328132376_n.jpg?stp=c0.0.1080.1080a_dst-jpg_s200x200_tt6&_nc_cat=111&ccb=1-7&_nc_sid=e99d92&_nc_ohc=SUxVciJ8w2UQ7kNvwFxkrp9&_nc_oc=AdmrXVn9JoFYQix0AQKbakQS0YWu8lmL5dgo_bA_iEye2-L8rgofJIpeuNp2dY8jA0w&_nc_zt=24&_nc_ht=scontent.ftnr2-2.fna&_nc_gid=_RJpJU36yKS1WJblCLNpYA&_nc_ss=8&oh=00_Afygxt494KYAR9MgmNAJjEKwoTNy-w7OOZUUhV8mOHvl4g&oe=69AAD170"
                    alt="Profile placeholder">
            </div>
        </section>

        <!-- Section À propos de moi -->
        <section id="about" class="about container">
            <h2 class="section-title">
                <span>À propos</span> de moi
            </h2>

            <div class="about-content">
                <p class="about-text">
                    👋 Bonjour ! Je suis <span class="about-highlight">ANDRIANANTENAINA Tsiory Ny Antsa</span>,<br>
                    un développeur créatif de site web.
                </p>

                <div class="bio-section">
                    <h3>Ma philosophie</h3>
                    <p>
                        Je suis passionné par la création de solutions innovantes qui résolvent
                        des problèmes concrets. J'aime particulièrement travailler sur des projets
                        qui ont un impact positif et qui améliorent le quotidien des utilisateurs.
                        Mon approche allie créativité, technicité et une attention particulière aux détails.
                    </p>
                </div>

                <div class="bio-section">
                    <h3>Mes passions</h3>
                    <div class="passions">
                        <span class="passion-tag">🎸 Guitare</span>
                        <span class="passion-tag">📚 Lecture</span>
                        <span class="passion-tag">📸 Photographie</span>
                    </div>
                </div>

                <div class="quote">
                    "Le design n'est pas seulement ce à quoi cela ressemble,
                    mais comment cela fonctionne."
                    <span class="quote-author">— Steve Jobs</span>
                </div>
            </div>
        </section>

        <!-- Section Compétences -->
        <section id="skills" class="skills container">
            <h2 class="section-title">
                <span>Compétences</span> & technologies
            </h2>
            <div class="skills-container">
                <span class="skill-item">HTML5/CSS3</span>
                <span class="skill-item">JavaScript</span>
            </div>
        </section>

        <!-- Section Contact -->
        <section id="contact" class="contact container">
            <h2 class="section-title">
                <span>Me</span> contacter
            </h2>
            <p style="text-align: center; max-width: 600px; margin: 0 auto 2rem auto; color: rgba(255,255,255,0.8);">
                N'hésitez pas à me contacter via le moyen qui vous convient le mieux.
            </p>

            <div class="contact-grid">
                <!-- Carte WhatsApp -->
                <div class="contact-card">
                    <div class="contact-icon">📱</div>
                    <h3>WhatsApp</h3>
                    <p>Réponse rapide<br>via messagerie instantanée</p>
                    <a href="https://wa.me/385907180" class="contact-link" target="_blank">
                        Envoyer un message
                    </a>
                </div>

                <!-- Carte Téléphone -->
                <div class="contact-card">
                    <div class="contact-icon">📞</div>
                    <h3>Téléphone</h3>
                    <p>Appelez-moi pour<br>échanger directement</p>
                    <a href="tel:+261385907180" class="contact-link">
                        +261 38 59 071 80
                    </a>
                </div>

                <!-- Carte Email -->
                <div class="contact-card">
                    <div class="contact-icon">✉️</div>
                    <h3>Email</h3>
                    <p>Pour les demandes<br>détaillées et projets</p>
                    <a href="mailto:contact@andrianantenainatsiorynyantsa.fr" class="contact-link">
                        contact@andrianantenainatsiorynyantsa.fr
                    </a>
                </div>
            </div>

            <!-- Informations supplémentaires -->
            <div class="contact-info-supplementaire">
                <div class="disponibilite">
                    <span></span>
                    Disponible pour vos projets
                </div>
                <p style="margin-top: 1rem; color: rgba(255,255,255,0.8); font-size: 0.95rem;">
                    Horaires de réponse habituels : <br>
                    Lundi - Vendredi : 9h - 19h
                </p>
            </div>

            <div class="social-links">
                <a href="#">GitHub</a>
                <a href="#">LinkedIn</a>
                <a href="#">Twitter</a>
                <a href="#">Instagram</a>
            </div>
        </section>
    </main>

    <footer>
        <p>© 2026 ANDRIANANTENAINA Tsiory Ny Antsa</p>
    </footer>
</body>

</html>
