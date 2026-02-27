<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio - Tsiory Ny Antsa (fusion animée)</title>
    <!-- Google Fonts Montserrat -->
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        /* ===== MERGE COMPLET : STYLES ORIGINE + NOUVELLES ANIMATIONS ===== */
        /* (les deux blocs sont fusionnés, sans conflit, ordre optimisé) */

        /* ---------- RESET & GLOBAL (issu du second code + ajustements) ---------- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Montserrat', sans-serif;
        }

        body {
            background: #f4efe6;      /* second code : fond beige clair */
            color: #222;
            animation: fadeIn 1.5s ease-in-out;  /* global fade */
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to   { opacity: 1; }
        }

        /* BAR : du second code + couleurs adaptées */
        .bar {
            background: #1e1b4b;
            color: #fff;
            padding: 8px;
            text-align: center;
            font-size: 14px;
            letter-spacing: 2px;
            animation: slideDown 0.8s ease-out;
            text-transform: uppercase;
            border-top: 2px solid #3b44f6;
            border-bottom: 2px solid #3b44f6;
        }

        @keyframes slideDown {
            from { transform: translateY(-100%); opacity: 0; }
            to   { transform: translateY(0); opacity: 1; }
        }

        /* ---------- CONTAINER : GRID (second code) + largeur adaptée ---------- */
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 40px auto;
            display: grid;
            grid-template-columns: 40% 60%;
            gap: 40px;
            background: transparent;  /* pas de fond blanc, c'est le body qui gère */
        }

        /* animations des colonnes (second code) */
        .left {
            animation: slideInLeft 1s ease-out;
        }
        @keyframes slideInLeft {
            from { transform: translateX(-50px); opacity: 0; }
            to   { transform: translateX(0); opacity: 1; }
        }

        .right {
            animation: slideInRight 1s ease-out;
        }
        @keyframes slideInRight {
            from { transform: translateX(50px); opacity: 0; }
            to   { transform: translateX(0); opacity: 1; }
        }

        /* ---------- LEFT PANEL (panneau sombre, hérité du premier code mais adapté au fond clair) ---------- */
        .left {
            background: #1e1b4b;        /* fond indigo profond */
            color: #f0eefb;
            padding: 40px 30px;
            border-radius: 32px;
            box-shadow: 0 20px 30px rgba(0,0,0,0.2);
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        /* profile container */
        .profile-container {
            text-align: center;
            margin-bottom: 10px;
        }

        /* IMAGE : fusion des styles (popIn, hover, dimensions) */
        .left img {
            width: 250px;
            height: 250px;
            border-radius: 50%;
            object-fit: cover;
            border: 4px solid #4f5af7;
            box-shadow: 0 10px 25px rgba(0,0,0,0.5);
            animation: popIn 1.2s ease-out;
            transition: transform 0.5s ease, box-shadow 0.5s ease;
        }

        @keyframes popIn {
            0% { transform: scale(0.5); opacity: 0; }
            80% { transform: scale(1.1); }
            100% { transform: scale(1); opacity: 1; }
        }

        .left img:hover {
            transform: scale(1.05) rotate(5deg);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
        }

        /* profile name (animation letter bounce du premier code) */
        .profile-name {
            margin-top: 20px;
            font-size: 2em;
            font-weight: 900;
            color: white;
            position: relative;
            display: inline-block;
            padding: 10px 30px;
            animation: nameGlow 3s ease-in-out infinite;
            text-shadow: 0 0 8px #3b44f6;
        }

        @keyframes nameGlow {
            0%,100% { text-shadow: 0 0 10px #6f7cff, 0 0 20px #3b44f6; transform: scale(1); }
            50% { text-shadow: 0 0 20px #a5b0ff, 0 0 40px #4f5af7; transform: scale(1.03); }
        }

        .profile-name span {
            display: inline-block;
            animation: letterBounce 2s ease-in-out infinite;
        }
        @keyframes letterBounce {
            0%,100% { transform: translateY(0); }
            50% { transform: translateY(-6px); }
        }

        /* sections dans left */
        .left .section {
            margin-top: 0;  /* on utilise le gap du flex */
            animation: fadeInUp 0.8s ease-out;
            animation-fill-mode: both;
        }
        .left .section:nth-child(1) { animation-delay: 0.2s; }
        .left .section:nth-child(2) { animation-delay: 0.4s; }
        .left .section:nth-child(3) { animation-delay: 0.6s; }

        @keyframes fadeInUp {
            from { transform: translateY(30px); opacity: 0; }
            to   { transform: translateY(0); opacity: 1; }
        }

        .left .section h3 {
            color: #b9c1fe;          /* adapté au fond sombre */
            font-weight: 700;
            letter-spacing: 1px;
            font-size: 1.3rem;
            border-bottom: 2px dashed #4f5af7;
            padding-bottom: 8px;
            margin-bottom: 18px;
            display: inline-block;
            position: relative;
        }

        /* soulignement animé (second code) */
        .left .section h3::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 3px;
            background: #b9c1fe;    /* plus clair */
            transition: width 0.5s ease;
        }
        .left .section:hover h3::after {
            width: 100%;
        }

        /* contact */
        .contact p {
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: transform 0.3s ease, color 0.3s ease;
        }
        .contact p:hover {
            transform: translateX(10px);
            color: #b9c1fe;
        }

        /* skills & tags */
        .skills, .tags {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-top: 8px;
        }

        .skill-box {
            background: #2f2b70;
            padding: 8px 20px;
            border-radius: 40px;
            font-weight: 600;
            color: white;
            border: 1px solid #5d68f0;
            transition: all 0.3s ease;
            animation: skillPulse 2s infinite;   /* du second code */
        }

        @keyframes skillPulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .skill-box:hover {
            background: #3b44f6;
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 10px 20px rgba(59, 68, 246, 0.4);
            animation: none;
        }

        .tag {
            background: #2f2b70;
            padding: 6px 18px;
            border-radius: 30px;
            font-size: 0.9rem;
            font-weight: 500;
            border: 1px solid #7f8aff;
            transition: all 0.3s ease;
            animation: tagFloat 3s ease-in-out infinite;
        }

        @keyframes tagFloat {
            0% { transform: translateY(0); }
            50% { transform: translateY(-3px); }
            100% { transform: translateY(0); }
        }

        .tag:hover {
            background: #3b44f6;
            color: white;
            border-color: #3b44f6;
            transform: scale(1.1);
            animation: none;
        }

        /* ---------- RIGHT PANEL (blanc avec animations) ---------- */
        .right {
            background: white;
            padding: 40px 45px;
            border-radius: 32px;
            box-shadow: 0 20px 30px rgba(0,0,0,0.1);
        }

        .right .section {
            margin-bottom: 35px;
            animation: fadeInUp 0.8s ease-out;
            animation-fill-mode: both;
        }
        .right .section:nth-child(1) { animation-delay: 0.2s; }
        .right .section:nth-child(2) { animation-delay: 0.4s; }
        .right .section:nth-child(3) { animation-delay: 0.6s; }

        .right .section h3 {
            color: #1e1b4b;
            font-weight: 900;
            font-size: 1.8rem;
            border-left: 8px solid #3b44f6;
            padding-left: 20px;
            margin-bottom: 25px;
            position: relative;
            display: inline-block;
        }

        .right .section h3::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 3px;
            background: #3b44f6;
            transition: width 0.5s ease;
        }
        .right .section:hover h3::after {
            width: 100%;
        }

        .about h2 {
            color: #3b44f6;
            font-weight: 900;
            font-size: 1.8rem;
            border-left: 8px solid #1e1b4b;
            padding-left: 20px;
            margin-bottom: 20px;
            animation: slideInRight 1s ease-out;
        }

        .about p {
            background: #f0f3ff;
            padding: 20px 28px;
            border-radius: 24px;
            font-size: 1.2rem;
            line-height: 1.7;
            border: 1px solid #d0d6ff;
            transition: color 0.3s ease;
        }
        .about p:hover {
            color: #3b44f6;
        }

        .timeline {
            margin-bottom: 30px;
            padding: 15px;
            padding-left: 25px;
            border-left: 3px solid #3b44f6;
            position: relative;
            border-radius: 10px;
            transition: all 0.3s ease;
            animation: fadeInScale 0.8s ease-out;
            animation-fill-mode: both;
        }
        .timeline:nth-child(1) { animation-delay: 0.2s; }
        .timeline:nth-child(2) { animation-delay: 0.4s; }
        .timeline:nth-child(3) { animation-delay: 0.6s; }

        @keyframes fadeInScale {
            from { transform: scale(0.9); opacity: 0; }
            to   { transform: scale(1); opacity: 1; }
        }

        .timeline:hover {
            background: rgba(59, 68, 246, 0.1);
            transform: translateX(10px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .timeline h4 {
            font-size: 1.4rem;
            font-weight: 900;
            color: #1e1b4b;
        }

        .timeline small {
            color: #3b44f6;
            font-weight: 700;
            background: #e2e6ff;
            padding: 4px 12px;
            border-radius: 40px;
            display: inline-block;
            margin: 6px 0 8px;
            transition: color 0.3s ease;
        }
        .timeline:hover small {
            color: #1e1b4b;
        }

        .timeline p {
            font-size: 1rem;
            color: #2d2b55;
        }

        /* ---------- WELCOME LETTER (fusionné du premier code, ajusté) ---------- */
        .welcome-letter {
            background: linear-gradient(135deg, #141238 0%, #2f3af8 100%);
            color: white;
            padding: 40px 30px;
            text-align: center;
            margin: 30px auto 10px;
            border-radius: 40px;
            width: 95%;
            max-width: 1200px;
            box-shadow: 0 20px 35px rgba(20, 30, 100, 0.5);
            animation: welcomePop 1.4s cubic-bezier(0.21, 1.11, 0.33, 1.1);
            position: relative;
            overflow: hidden;
        }

        @keyframes welcomePop {
            0% { transform: scale(0.3) rotate(-6deg); opacity: 0; }
            50% { transform: scale(1.08) rotate(1.5deg); }
            100% { transform: scale(1) rotate(0); opacity: 1; }
        }

        .welcome-letter::before {
            content: '✉️';
            font-size: 90px;
            position: absolute;
            top: -20px;
            left: 5px;
            opacity: 0.15;
            transform: rotate(10deg);
            animation: float 4s infinite;
        }
        .welcome-letter::after {
            content: '💻';
            font-size: 100px;
            bottom: -30px;
            right: 10px;
            position: absolute;
            opacity: 0.15;
            transform: rotate(-10deg);
            animation: floatAlt 5s infinite;
        }

        @keyframes float {
            0% { transform: rotate(10deg) translateY(0); }
            50% { transform: rotate(10deg) translateY(-20px); }
            100% { transform: rotate(10deg) translateY(0); }
        }
        @keyframes floatAlt {
            0% { transform: rotate(-10deg) translateY(0); }
            50% { transform: rotate(-8deg) translateY(-25px); }
            100% { transform: rotate(-10deg) translateY(0); }
        }

        .welcome-letter h1 {
            font-size: 2.8rem;
            font-weight: 900;
            margin-bottom: 20px;
            text-shadow: 3px 3px 0 #1a1f60;
            animation: slideDown 0.6s 0.3s both;
        }

        .welcome-letter p {
            font-size: 1.2rem;
            max-width: 900px;
            margin: 15px auto;
            background: rgba(255, 255, 255, 0.05);
            padding: 12px 25px;
            border-radius: 60px;
            backdrop-filter: blur(3px);
        }

        .welcome-signature {
            font-size: 1.8rem;
            font-weight: 900;
            margin-top: 25px;
        }
        .welcome-signature span {
            display: inline-block;
            animation: wave 2s infinite;
        }
        @keyframes wave {
            0%,100% { transform: rotate(0); }
            25% { transform: rotate(18deg); }
            75% { transform: rotate(-10deg); }
        }

        /* ---------- RESPONSIVE (second code) ---------- */
        @media(max-width:900px) {
            .container {
                grid-template-columns: 1fr;
            }
            .left img {
                display: block;
                margin: 0 auto;
            }
            .left, .right {
                animation: fadeIn 1s ease-out;
            }
        }

        /* petit extra (optionnel) */
        .bar:last-of-type {
            margin-top: 20px;
        }
    </style>
</head>
<body>

    <!-- TOP BAR -->
    <div class="bar">PORTFOLIO • 2026 • ANDRIANANTENAINA Tsiory Ny Antsa • PORTFOLIO • 2026</div>

    <!-- WELCOME LETTER (premier code) -->
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
            <span>✨</span> Tsiory Ny Antsa <span>✨</span>
        </div>
    </div>

    <!-- MAIN CONTENT : LEFT / RIGHT (fusionné) -->
    <div class="container">
        <!-- LEFT PANEL (indigo, avec image et nom) -->
        <div class="left">
            <div class="profile-container">
                <!-- image SVG stylée (ou remplacer par vrai chemin) -->
                <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='400' height='400' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='45' fill='%233b44f6' /%3E%3Ccircle cx='35' cy='35' r='8' fill='%23FFF' /%3E%3Ccircle cx='65' cy='35' r='8' fill='%23FFF' /%3E%3Cpath d='M30 65 Q50 80, 70 65' stroke='%23FFF' stroke-width='5' fill='none' stroke-linecap='round' /%3E%3C/svg%3E"
                     alt="profile">
                <!-- nom animé -->
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
                <p>WHATSAPP ⚡ 0334127027</p>
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
                <p>🇲🇬 MALGACHE – Native</p>
                <p>🇫🇷 FRANCAIS</p>
            </div>

            <div class="section">
                <h3>INTERESTS</h3>
                <div class="tags">
                    <div class="tag">🎨 Design</div>
                    <div class="tag">🎵 Music</div>
                    <div class="tag">🎬 Cinema</div>
                    <div class="tag">🎮 Jeu video</div>
                </div>
            </div>
        </div>

        <!-- RIGHT PANEL (blanc, contenu) -->
        <div class="right">
            <div class="about">
                <h2>À PROPOS DE MOI</h2>
                <p>Je débute dans la création de sites web et dans le codage, et je suis en voie d'expansion dans ce domaine. Chaque jour est une nouvelle découverte !</p>
            </div>

            <div class="section">
                <h3>EDUCATION</h3>
                <div class="timeline">
                    <h4>EMIT Fianaratsoa</h4>
                    <small>2026 - Aujourd'hui</small>
                    <p>Formation en développement web & multimédia</p>
                </div>
            </div>

            <div class="section">
                <h3>EXPERIENCE</h3>
                <div class="timeline">
                    <h4>Création de sites web</h4>
                    <small>2026 - maintenant</small>
                    <p>Créateur et designer de sites web (projets personnels, portfolio, pages statiques)</p>
                </div>
                <div class="timeline">
                    <h4>Informatique de base</h4>
                    <small>2026 - maintenant</small>
                    <p>Expérience bureautique (Word, Excel, PowerPoint) – maîtrise des outils essentiels</p>
                </div>
            </div>

            <!-- petite signature discrète -->
            <div style="margin-top: 40px; font-style: italic; color: #a5a9d4; border-top: 1px dashed #cbd0ff; padding-top: 20px; text-align: right;">
                ✨ "coder, c'est créer sans limite" ✨
            </div>
        </div>
    </div>

    <!-- BOTTOM BAR -->
    <div class="bar">PORTFOLIO • 2026 • ANDRIANANTENAINA Tsiory Ny Antsa • PORTFOLIO • 2026</div>

</body>
</html>
