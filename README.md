<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio - Tsiory Ny Antsa</title>
    <!-- Google Fonts Montserrat -->
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        /* ===== RESET & BASE ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Montserrat', sans-serif;
        }

        body {
            background: #f4efe6;
            color: #222;
            /* Fade In global */
            animation: fadeIn 1.5s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* ===== BARRE (SLIDE DOWN) ===== */
        .bar {
            background: #1e1b4b;
            color: #fff;
            padding: 8px;
            text-align: center;
            font-size: 14px;
            letter-spacing: 2px;
            animation: slideDown 0.8s ease-out;
        }

        @keyframes slideDown {
            from { transform: translateY(-100%); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        /* ===== CONTENEUR PRINCIPAL ===== */
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 40px auto;
            display: grid;
            grid-template-columns: 40% 60%;
            gap: 40px;
        }

        /* ===== ANIMATIONS LATÉRALES ===== */
        .left {
            animation: slideInLeft 1s ease-out;
        }

        @keyframes slideInLeft {
            from { transform: translateX(-50px); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }

        .right {
            animation: slideInRight 1s ease-out;
        }

        @keyframes slideInRight {
            from { transform: translateX(50px); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }

        /* ===== SECTION GAUCHE : PHOTO & NOM ===== */
        .profile-container {
            text-align: center;
            margin-bottom: 20px;
            position: relative;
            display: inline-block;
            width: 100%;
        }

        /* IMAGE avec animations multiples */
        .profile-img {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            object-fit: cover;
            border: 4px solid #3b44f6;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            
            /* Animation d'entrée */
            animation: popInRotate 1.2s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            
            /* Transition pour le hover */
            transition: all 0.5s ease;
            
            /* Effet de brillance */
            position: relative;
            z-index: 2;
        }

        /* Animation d'entrée combinée */
        @keyframes popInRotate {
            0% {
                transform: scale(0) rotate(-180deg);
                opacity: 0;
                filter: blur(10px);
            }
            50% {
                transform: scale(1.2) rotate(10deg);
                filter: blur(0);
            }
            80% {
                transform: scale(0.95) rotate(-2deg);
            }
            100% {
                transform: scale(1) rotate(0);
                opacity: 1;
            }
        }

        /* Hover animations sur l'image */
        .profile-img:hover {
            transform: scale(1.08) rotate(5deg);
            border-color: #ff6b6b;
            box-shadow: 0 20px 40px rgba(59, 68, 246, 0.5);
            filter: brightness(1.1) contrast(1.1);
        }

        /* Animation supplémentaire : pulse subtil sur l'image */
        .profile-img {
            animation: popInRotate 1.2s, softPulse 3s infinite 1.5s;
        }

        @keyframes softPulse {
            0%, 100% {
                box-shadow: 0 10px 30px rgba(59, 68, 246, 0.2);
            }
            50% {
                box-shadow: 0 15px 40px rgba(59, 68, 246, 0.5);
            }
        }

        /* Effet de scintillement autour de l'image */
        .profile-container::after {
            content: '';
            position: absolute;
            top: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 330px;
            height: 330px;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(59,68,246,0.4) 0%, transparent 70%);
            opacity: 0;
            animation: glowPulse 3s infinite;
            pointer-events: none;
            z-index: 1;
        }

        @keyframes glowPulse {
            0%, 100% { opacity: 0; transform: translateX(-50%) scale(1); }
            50% { opacity: 1; transform: translateX(-50%) scale(1.1); }
        }

        /* Effet de rotation d'anneau autour de l'image */
        .profile-container::before {
            content: '';
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            width: 340px;
            height: 340px;
            border-radius: 50%;
            border: 2px dashed rgba(59, 68, 246, 0.3);
            animation: rotateRing 10s linear infinite;
            pointer-events: none;
            z-index: 1;
        }

        @keyframes rotateRing {
            from { transform: translateX(-50%) rotate(0deg); }
            to { transform: translateX(-50%) rotate(360deg); }
        }

        /* NOM sous l'image (animé) */
        .profile-name {
            margin-top: 30px;
            font-size: 2em;
            font-weight: 900;
            color: #1e1b4b;
            position: relative;
            display: inline-block;
            padding: 10px 30px;
            animation: nameGlow 3s ease-in-out infinite;
            z-index: 3;
        }

        @keyframes nameGlow {
            0%, 100% { text-shadow: 0 0 10px rgba(59, 68, 246, 0.3); transform: scale(1); }
            50% { text-shadow: 0 0 20px rgba(59, 68, 246, 0.7); transform: scale(1.05); }
        }

        .profile-name::before {
            content: "✨";
            position: absolute;
            left: -10px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 1.2em;
            animation: starSpin 4s linear infinite;
        }

        .profile-name::after {
            content: "✨";
            position: absolute;
            right: -10px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 1.2em;
            animation: starSpin 4s linear infinite reverse;
        }

        @keyframes starSpin {
            from { transform: translateY(-50%) rotate(0deg); }
            to { transform: translateY(-50%) rotate(360deg); }
        }

        .profile-name span {
            display: inline-block;
            animation: letterBounce 2s ease-in-out infinite;
        }

        @keyframes letterBounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-5px); }
        }

        /* Animation pour chaque lettre avec délai */
        .profile-name span:nth-child(1) { animation-delay: 0.1s; }
        .profile-name span:nth-child(2) { animation-delay: 0.2s; }
        .profile-name span:nth-child(3) { animation-delay: 0.3s; }
        .profile-name span:nth-child(4) { animation-delay: 0.4s; }
        .profile-name span:nth-child(5) { animation-delay: 0.5s; }
        .profile-name span:nth-child(6) { animation-delay: 0.6s; }
        .profile-name span:nth-child(7) { animation-delay: 0.7s; }
        .profile-name span:nth-child(8) { animation-delay: 0.8s; }
        .profile-name span:nth-child(9) { animation-delay: 0.9s; }
        .profile-name span:nth-child(10) { animation-delay: 1s; }
        .profile-name span:nth-child(11) { animation-delay: 1.1s; }
        .profile-name span:nth-child(12) { animation-delay: 1.2s; }
        .profile-name span:nth-child(13) { animation-delay: 1.3s; }

        /* ===== SECTIONS COMMUNES ===== */
        .section {
            margin-top: 30px;
            animation: fadeInUp 0.8s ease-out;
            animation-fill-mode: both;
            transition: all 0.3s ease;
        }

        .section:nth-child(1) { animation-delay: 0.2s; }
        .section:nth-child(2) { animation-delay: 0.4s; }
        .section:nth-child(3) { animation-delay: 0.6s; }
        .section:nth-child(4) { animation-delay: 0.8s; }

        @keyframes fadeInUp {
            from { transform: translateY(30px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .section:hover {
            transform: translateY(-5px);
        }

        .section h3 {
            color: #3b44f6;
            font-weight: 900;
            margin-bottom: 15px;
            position: relative;
            display: inline-block;
        }

        /* Ligne animée sous les titres */
        .section h3::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 3px;
            background: #3b44f6;
            transition: width 0.5s ease;
        }

        .section:hover h3::after {
            width: 100%;
        }

        /* ===== CONTACT ===== */
        .contact p {
            margin-bottom: 8px;
            transition: transform 0.3s ease, color 0.3s ease;
            animation: slideInRight 0.5s ease-out;
            animation-fill-mode: both;
        }

        .contact p:nth-child(1) { animation-delay: 0.1s; }
        .contact p:nth-child(2) { animation-delay: 0.2s; }
        .contact p:nth-child(3) { animation-delay: 0.3s; }
        .contact p:nth-child(4) { animation-delay: 0.4s; }

        .contact p:hover {
            transform: translateX(10px);
            color: #3b44f6;
        }

        /* ===== SKILLS (TECHNICAL) ===== */
        .skills {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        .skill-box {
            background: #000;
            color: #fff;
            padding: 15px;
            border-radius: 15px;
            font-weight: 700;
            transition: all 0.3s ease;
            animation: skillPulse 2s infinite;
            position: relative;
            overflow: hidden;
        }

        @keyframes skillPulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .skill-box::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.3), transparent);
            transform: rotate(45deg);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% { transform: translateX(-100%) rotate(45deg); }
            20% { transform: translateX(100%) rotate(45deg); }
            100% { transform: translateX(100%) rotate(45deg); }
        }

        .skill-box:hover {
            background: #3b44f6;
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 10px 20px rgba(59, 68, 246, 0.4);
            animation: none;
        }

        /* ===== LANGUAGES & TAGS ===== */
        .tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .tag {
            border: 1px solid #333;
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 14px;
            transition: all 0.3s ease;
            animation: tagFloat 3s ease-in-out infinite;
            position: relative;
            overflow: hidden;
        }

        @keyframes tagFloat {
            0% { transform: translateY(0); }
            50% { transform: translateY(-3px); }
            100% { transform: translateY(0); }
        }

        .tag::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(59,68,246,0.2), transparent);
            transition: left 0.5s ease;
        }

        .tag:hover::before {
            left: 100%;
        }

        .tag:hover {
            background: #3b44f6;
            color: white;
            border-color: #3b44f6;
            transform: scale(1.1);
            animation: none;
        }

        /* ===== RIGHT: ABOUT, EDUCATION, EXPERIENCE ===== */
        .about h2 {
            color: #3b44f6;
            font-weight: 900;
            margin-bottom: 15px;
            animation: slideInRight 1s ease-out;
            position: relative;
            display: inline-block;
        }

        .about h2::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 3px;
            background: #3b44f6;
            transition: width 0.5s ease;
        }

        .about:hover h2::after {
            width: 100%;
        }

        .about p {
            line-height: 1.6;
            margin-bottom: 30px;
            transition: color 0.3s ease, transform 0.3s ease;
            animation: fadeInUp 0.8s ease-out 0.3s both;
        }

        .about p:hover {
            color: #3b44f6;
            transform: translateX(10px);
        }

        .timeline {
            margin-bottom: 25px;
            padding: 15px;
            border-radius: 10px;
            transition: all 0.3s ease;
            animation: fadeInScale 0.8s ease-out;
            animation-fill-mode: both;
            position: relative;
            overflow: hidden;
        }

        .timeline:nth-child(1) { animation-delay: 0.2s; }
        .timeline:nth-child(2) { animation-delay: 0.4s; }
        .timeline:nth-child(3) { animation-delay: 0.6s; }

        @keyframes fadeInScale {
            from { transform: scale(0.9); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        .timeline::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 0;
            background: #3b44f6;
            transition: height 0.3s ease;
        }

        .timeline:hover::before {
            height: 100%;
        }

        .timeline:hover {
            background: rgba(59, 68, 246, 0.1);
            transform: translateX(10px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .timeline h4 {
            font-weight: 700;
            margin: 0;
        }

        .timeline small {
            color: #555;
            transition: color 0.3s ease;
        }

        .timeline:hover small {
            color: #3b44f6;
        }

        .timeline p {
            margin-top: 5px;
        }

        /* ===== LETTRE DE BIENVENUE ===== */
        .welcome-letter {
            background: linear-gradient(135deg, #1e1b4b 0%, #3b44f6 100%);
            color: white;
            padding: 40px 20px;
            text-align: center;
            margin: 20px auto;
            border-radius: 20px;
            width: 90%;
            max-width: 1200px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            animation: welcomePop 1.5s ease-out;
            position: relative;
            overflow: hidden;
        }

        @keyframes welcomePop {
            0% { transform: scale(0.5) rotate(-5deg); opacity: 0; }
            50% { transform: scale(1.1) rotate(2deg); }
            100% { transform: scale(1) rotate(0); opacity: 1; }
        }

        .welcome-letter::before {
            content: '✉️';
            font-size: 50px;
            position: absolute;
            top: -20px;
            left: -20px;
            opacity: 0.1;
            transform: rotate(15deg);
            animation: float 3s ease-in-out infinite;
        }

        .welcome-letter::after {
            content: '💻';
            font-size: 60px;
            position: absolute;
            bottom: -20px;
            right: -20px;
            opacity: 0.1;
            transform: rotate(-15deg);
            animation: float 4s ease-in-out infinite reverse;
        }

        @keyframes float {
            0% { transform: rotate(15deg) translateY(0); }
            50% { transform: rotate(15deg) translateY(-20px); }
            100% { transform: rotate(15deg) translateY(0); }
        }

        .welcome-letter h1 {
            font-size: 3em;
            font-weight: 900;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            animation: slideInDown 0.8s ease-out 0.5s both;
        }

        @keyframes slideInDown {
            from { transform: translateY(-50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .welcome-letter p {
            font-size: 1.2em;
            line-height: 1.8;
            max-width: 800px;
            margin: 0 auto 20px;
            animation: fadeInUp 0.8s ease-out 0.8s both;
        }

        .welcome-signature {
            font-size: 1.5em;
            font-style: italic;
            margin-top: 30px;
            animation: fadeIn 1s ease-out 1.2s both;
        }

        .welcome-signature span {
            display: inline-block;
            animation: wave 2s ease-in-out infinite;
        }

        @keyframes wave {
            0%, 100% { transform: rotate(0); }
            25% { transform: rotate(15deg); }
            75% { transform: rotate(-15deg); }
        }

        /* ===== RESPONSIVE ===== */
        @media(max-width:900px) {
            .container {
                grid-template-columns: 1fr;
            }
            .profile-img {
                display: block;
                margin: 0 auto;
            }
            .left, .right {
                animation: fadeIn 1s ease-out;
            }
        }
    </style>
</head>
<body>

    <!-- Barre supérieure -->
    <div class="bar">PORTFOLIO • 2026 • ANDRIANANTENAINA Tsiory Ny Antsa • PORTFOLIO • 2026</div>

    <!-- LETTRE DE BIENVENUE -->
    <div class="welcome-letter">
        <h1>👋 Bienvenue sur mon Portfolio !</h1>
        <p>
            Bonjour et bienvenue dans mon univers créatif ! Je suis ravi de vous accueillir sur mon portfolio.
            Passionné par le développement web et le design, je vous invite à découvrir mon parcours, mes compétences
            et mes réalisations. Chaque ligne de code raconte une histoire, chaque design exprime une émotion.
        </p>
        <p>
            En tant que débutant dans le monde fascinant du développement web, je suis constamment en quête
            d'apprentissage et d'amélioration. Ce portfolio est le reflet de ma passion et de ma détermination
            à créer des expériences numériques uniques.
        </p>
        <div class="welcome-signature">
            <span></span> Tsiory Ny Antsa <span></span>
        </div>
    </div>

    <!-- Contenu principal -->
    <div class="container">

        <!-- COLONNE GAUCHE -->
        <div class="left">
            <div class="profile-container">
                <!-- IMAGE avec classe spécifique pour animations -->
                <img src="IMG_20260226_152915.jpg"                                                                                                      alt="profile" 
                     class="profile-img"
                     height="300" 
                     width="300">
                
                <!-- Nom animé -->
                <div class="profile-name">
                    <span>T</span><span>s</span><span>i</span><span>o</span><span>r</span><span>y</span>&nbsp;
                    <span>N</span><span>y</span>&nbsp;
                    <span>A</span><span>n</span><span>t</span><span>s</span><span>a</span>
                </div>
            </div>

            <div class="section contact">
                <h3>CONTACT</h3>
                <p>0385907180 - 0334127027</p>
                <p>26 - 09 - 2009</p>
                <p>andrianantenainatsiorynyantsa@gmail.com</p>
                <p>WHATSAPP ==> 0334127027</p>
            </div>

            <div class="section">
                <h3>TECHNICAL SKILLS</h3>
                <div class="skills">
                    <div class="skill-box">CSS</div>
                    <div class="skill-box">HTML</div>
                    <div class="skill-box">EXCEL</div>
                    <div class="skill-box">WORD</div>
                </div>
            </div>

            <div class="section">
                <h3>LANGUAGES</h3>
                <p>MALGACHE – Native</p>
                <p>FRANCAIS</p>
            </div>

            <div class="section">
                <h3>INTERESTS</h3>
                <div class="tags">
                    <div class="tag">Design</div>
                    <div class="tag">Music</div>
                    <div class="tag">Cinema</div>
                    <div class="tag">Jeu video</div>
                </div>
            </div>
        </div>

        <!-- COLONNE DROITE -->
        <div class="right">
            <div class="about">
                <h2>A PROPOS DE MOI</h2>
                <p>je fait que debuter dans la creation des site web et dans le codage et en voie d'expention dans ce domaine</p>
            </div>

            <div class="section">
                <h3>EDUCATION</h3>
                <div class="timeline">
                    <h4>EMIT Fianaratsoa</h4>
                    <small>2026 - Now</small>
                </div>
            </div>

            <div class="section">
                <h3>EXPERIENCE</h3>
                <div class="timeline">
                    <h4>creation de code de site web</h4>
                    <small>2026 - now</small>
                    <p>createur et designeur de site web</p>
                </div>
                <div class="timeline">
                    <h4>informatique de base</h4>
                    <small>2026 - Now</small>
                    <p>experience bureautique (word, excel, power point)</p>
                </div>
            </div>
        </div>

    </div>

    <!-- Barre inférieure -->
    <div class="bar">PORTFOLIO • 2026 • ANDRIANANTENAINA Tsiory Ny Antsa • PORTFOLIO • 2026</div>

</body>
</html>
