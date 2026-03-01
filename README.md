<!DOCTYPE html>
<html lang="fr">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio - Tsiory Ny Antsa</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700;900&display=swap" rel="stylesheet">

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Montserrat', sans-serif;
        }

        body {
            background: #f4efe6;
            color: #222;
            animation: fadeIn 1.5s ease-in-out;
            overflow-x: hidden;
        }

        /* Animations globales */
        @keyframes fadeIn {
            from {
                opacity: 0;
            }

            to {
                opacity: 1;
            }
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

        @keyframes slideInLeft {
            from {
                transform: translateX(-50px);
                opacity: 0;
            }

            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        @keyframes slideInRight {
            from {
                transform: translateX(50px);
                opacity: 0;
            }

            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        @keyframes popIn {
            0% {
                transform: scale(0.5);
                opacity: 0;
            }

            80% {
                transform: scale(1.1);
            }

            100% {
                transform: scale(1);
                opacity: 1;
            }
        }

        @keyframes fadeInUp {
            from {
                transform: translateY(30px);
                opacity: 0;
            }

            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        @keyframes skillPulse {
            0% {
                transform: scale(1);
                box-shadow: 0 0 0 0 rgba(59, 68, 246, 0.4);
            }

            50% {
                transform: scale(1.05);
                box-shadow: 0 0 0 10px rgba(59, 68, 246, 0);
            }

            100% {
                transform: scale(1);
                box-shadow: 0 0 0 0 rgba(59, 68, 246, 0);
            }
        }

        @keyframes tagFloat {

            0%,
            100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-5px);
            }
        }

        @keyframes welcomePop {
            0% {
                transform: scale(0.5) rotate(-5deg);
                opacity: 0;
            }

            50% {
                transform: scale(1.1) rotate(2deg);
            }

            100% {
                transform: scale(1) rotate(0);
                opacity: 1;
            }
        }

        @keyframes floatEmoji {
            0% {
                transform: rotate(15deg) translateY(0);
            }

            50% {
                transform: rotate(15deg) translateY(-20px);
            }

            100% {
                transform: rotate(15deg) translateY(0);
            }
        }

        @keyframes slideInDown {
            from {
                transform: translateY(-50px);
                opacity: 0;
            }

            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        @keyframes wave {

            0%,
            100% {
                transform: rotate(0);
            }

            25% {
                transform: rotate(15deg);
            }

            75% {
                transform: rotate(-15deg);
            }
        }

        @keyframes nameGlow {

            0%,
            100% {
                text-shadow: 0 0 10px rgba(59, 68, 246, 0.3);
                letter-spacing: 2px;
            }

            50% {
                text-shadow: 0 0 20px rgba(59, 68, 246, 0.7);
                letter-spacing: 4px;
            }
        }

        @keyframes starSpin {
            from {
                transform: translateY(-50%) rotate(0deg);
            }

            to {
                transform: translateY(-50%) rotate(360deg);
            }
        }

        @keyframes letterBounce {

            0%,
            100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-5px);
            }
        }

        @keyframes gradientFlow {
            0% {
                background-position: 0% 50%;
            }

            50% {
                background-position: 100% 50%;
            }

            100% {
                background-position: 0% 50%;
            }
        }

        @keyframes borderPulse {

            0%,
            100% {
                border-color: #3b44f6;
            }

            50% {
                border-color: #ff6b6b;
            }
        }

        /* Barre de navigation */
        .bar {
            background: linear-gradient(90deg, #1e1b4b, #3b44f6, #1e1b4b);
            background-size: 200% 100%;
            color: #fff;
            padding: 12px;
            text-align: center;
            font-size: 14px;
            letter-spacing: 2px;
            animation: slideDown 0.8s ease-out, gradientFlow 3s ease infinite;
            font-weight: 700;
            text-transform: uppercase;
            border-bottom: 2px solid gold;
        }

        /* Lettre de bienvenue */
        .welcome-letter {
            background: linear-gradient(135deg, #1e1b4b 0%, #3b44f6 50%, #1e1b4b 100%);
            background-size: 200% 200%;
            color: white;
            padding: 50px 20px;
            text-align: center;
            margin: 30px auto;
            border-radius: 30px;
            width: 90%;
            max-width: 1200px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            animation: welcomePop 1.5s ease-out, gradientFlow 5s ease infinite;
            position: relative;
            overflow: hidden;
            border: 3px solid gold;
        }

        .welcome-letter::before {
            content: '✉️';
            font-size: 80px;
            position: absolute;
            top: -20px;
            left: -20px;
            opacity: 0.1;
            transform: rotate(15deg);
            animation: floatEmoji 3s ease-in-out infinite;
        }

        .welcome-letter::after {
            content: '💻';
            font-size: 90px;
            position: absolute;
            bottom: -30px;
            right: -30px;
            opacity: 0.1;
            transform: rotate(-15deg);
            animation: floatEmoji 4s ease-in-out infinite reverse;
        }

        .welcome-letter h1 {
            font-size: 3.5em;
            font-weight: 900;
            margin-bottom: 20px;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.3);
            animation: slideInDown 0.8s ease-out 0.5s both;
            position: relative;
            display: inline-block;
        }

        .welcome-letter h1::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, transparent, gold, transparent);
            animation: borderPulse 2s infinite;
        }

        .welcome-letter p {
            font-size: 1.2em;
            line-height: 1.8;
            max-width: 800px;
            margin: 0 auto 20px;
            animation: fadeInUp 0.8s ease-out 0.8s both;
            background: rgba(255, 255, 255, 0.1);
            padding: 15px;
            border-radius: 15px;
            backdrop-filter: blur(5px);
        }

        .welcome-letter p:hover {
            transform: scale(1.02);
            transition: transform 0.3s ease;
            background: rgba(255, 255, 255, 0.2);
        }

        .welcome-signature {
            font-size: 2em;
            font-style: italic;
            margin-top: 40px;
            animation: fadeIn 1s ease-out 1.2s both;
            font-weight: 700;
            text-shadow: 0 0 15px gold;
        }

        .welcome-signature span {
            display: inline-block;
            animation: wave 2s ease-in-out infinite;
            filter: drop-shadow(0 0 5px gold);
        }

        /* Container principal */
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 50px auto;
            display: grid;
            grid-template-columns: 40% 60%;
            gap: 40px;
            position: relative;
        }

        /* Sidebar gauche */
        .left {
            animation: slideInLeft 1s ease-out;
            background: rgba(255, 255, 255, 0.7);
            padding: 30px;
            border-radius: 30px;
            backdrop-filter: blur(10px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            border: 2px solid rgba(255, 255, 255, 0.5);
        }

        .profile-container {
            text-align: center;
            margin-bottom: 20px;
            position: relative;
        }

        .profile-container::before {
            content: '';
            position: absolute;
            top: -10px;
            left: -10px;
            right: -10px;
            bottom: -10px;
            border: 3px solid transparent;
            border-radius: 50%;
            background: linear-gradient(90deg, #1e1b4b, #3b44f6, #1e1b4b) border-box;
            -webkit-mask: linear-gradient(#fff 0 0) padding-box, linear-gradient(#fff 0 0);
            mask: linear-gradient(#fff 0 0) padding-box, linear-gradient(#fff 0 0);
            -webkit-mask-composite: xor;
            mask-composite: exclude;
            animation: starSpin 4s linear infinite;
        }

        /* CORRECTION: Gestion améliorée de l'image */
        .profile-image-wrapper {
            position: relative;
            width: 280px;
            height: 280px;
            margin: 0 auto;
            border-radius: 50%;
            overflow: hidden;
            border: 5px solid gold;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            transition: all 0.5s ease;
        }

        .profile-image-wrapper:hover {
            transform: scale(1.05) rotate(5deg);
            border-color: #3b44f6;
            box-shadow: 0 20px 40px rgba(59, 68, 246, 0.4);
        }

        .profile-image-wrapper img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
            transition: all 0.5s ease;
        }

        /* Fallback élégant si l'image ne charge pas */
        .profile-image-wrapper img.error {
            opacity: 0;
        }

        .profile-image-wrapper .image-fallback {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #1e1b4b, #3b44f6);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            color: gold;
            border-radius: 50%;
            opacity: 0;
            transition: opacity 0.3s ease;
            pointer-events: none;
        }

        .profile-image-wrapper img.error+.image-fallback {
            opacity: 1;
        }

        .profile-name {
            margin-top: 25px;
            font-size: 2.2em;
            font-weight: 900;
            color: #1e1b4b;
            position: relative;
            display: inline-block;
            padding: 10px 40px;
            animation: nameGlow 3s ease-in-out infinite;
            background: linear-gradient(90deg, #1e1b4b, #3b44f6, #1e1b4b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-size: 200% auto;
        }

        .profile-name::before {
            content: '⭐';
            position: absolute;
            left: -5px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 1.5em;
            animation: starSpin 3s linear infinite;
        }

        .profile-name::after {
            content: '⭐';
            position: absolute;
            right: -5px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 1.5em;
            animation: starSpin 3s linear infinite reverse;
        }

        .profile-name span {
            display: inline-block;
            animation: letterBounce 2s ease-in-out infinite;
            animation-delay: calc(0.1s * var(--i));
        }

        /* Sections communes */
        .section {
            margin-top: 35px;
            animation: fadeInUp 0.8s ease-out;
            animation-fill-mode: both;
            padding: 20px;
            border-radius: 20px;
            background: rgba(255, 255, 255, 0.5);
            backdrop-filter: blur(5px);
            transition: all 0.3s ease;
        }

        .section:nth-child(1) {
            animation-delay: 0.2s;
        }

        .section:nth-child(2) {
            animation-delay: 0.4s;
        }

        .section:nth-child(3) {
            animation-delay: 0.6s;
        }

        .section:nth-child(4) {
            animation-delay: 0.8s;
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(59, 68, 246, 0.2);
            background: rgba(255, 255, 255, 0.8);
        }

        .section h3 {
            color: #3b44f6;
            font-weight: 900;
            margin-bottom: 20px;
            position: relative;
            display: inline-block;
            font-size: 1.5em;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .section h3::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 0;
            width: 0;
            height: 4px;
            background: linear-gradient(90deg, #3b44f6, gold);
            transition: width 0.5s ease;
            border-radius: 2px;
        }

        .section:hover h3::after {
            width: 100%;
        }

        /* Contact */
        .contact p {
            margin-bottom: 12px;
            transition: all 0.3s ease;
            padding: 8px 15px;
            border-radius: 10px;
            font-weight: 500;
        }

        .contact p:hover {
            transform: translateX(15px);
            background: linear-gradient(90deg, #3b44f6 0%, transparent 100%);
            color: white;
            box-shadow: 0 5px 15px rgba(59, 68, 246, 0.3);
        }

        /* Skills */
        .skills {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        .skill-box {
            background: linear-gradient(135deg, #000, #1e1b4b);
            color: #fff;
            padding: 15px 25px;
            border-radius: 50px;
            font-weight: 700;
            transition: all 0.4s ease;
            animation: skillPulse 3s infinite;
            border: 2px solid transparent;
            font-size: 1.1em;
            letter-spacing: 1px;
        }

        .skill-box:hover {
            background: linear-gradient(135deg, #3b44f6, gold);
            transform: translateY(-8px) scale(1.1);
            box-shadow: 0 15px 30px rgba(59, 68, 246, 0.4);
            animation: none;
            border-color: white;
        }

        /* Languages */
        .section p {
            font-size: 1.1em;
            padding: 8px 0;
            transition: all 0.3s ease;
        }

        .section p:hover {
            transform: scale(1.05);
            color: #3b44f6;
            font-weight: 700;
        }

        /* Tags */
        .tags {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .tag {
            border: 2px solid #1e1b4b;
            padding: 8px 18px;
            border-radius: 30px;
            font-size: 14px;
            transition: all 0.3s ease;
            animation: tagFloat 4s ease-in-out infinite;
            font-weight: 600;
            background: white;
        }

        .tag:hover {
            background: linear-gradient(135deg, #3b44f6, gold);
            color: white;
            border-color: transparent;
            transform: scale(1.15) rotate(2deg);
            animation: none;
            box-shadow: 0 10px 20px rgba(59, 68, 246, 0.3);
        }

        /* Partie droite */
        .right {
            animation: slideInRight 1s ease-out;
            background: rgba(255, 255, 255, 0.7);
            padding: 30px;
            border-radius: 30px;
            backdrop-filter: blur(10px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
            border: 2px solid rgba(255, 255, 255, 0.5);
        }

        .about h2 {
            color: #3b44f6;
            font-weight: 900;
            margin-bottom: 20px;
            animation: slideInRight 1s ease-out;
            font-size: 2em;
            position: relative;
            display: inline-block;
        }

        .about h2::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 0;
            width: 60px;
            height: 4px;
            background: linear-gradient(90deg, #3b44f6, gold);
            border-radius: 2px;
            transition: width 0.3s ease;
        }

        .about:hover h2::after {
            width: 100%;
        }

        .about p {
            line-height: 1.8;
            margin-bottom: 30px;
            transition: all 0.3s ease;
            font-size: 1.1em;
            padding: 15px;
            border-radius: 15px;
            background: rgba(255, 255, 255, 0.5);
        }

        .about p:hover {
            color: #1e1b4b;
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(59, 68, 246, 0.2);
            background: rgba(255, 255, 255, 0.9);
        }

        /* Timeline */
        .timeline {
            margin-bottom: 25px;
            padding: 20px;
            border-radius: 15px;
            transition: all 0.4s ease;
            animation: fadeInUp 0.8s ease-out;
            animation-fill-mode: both;
            background: rgba(255, 255, 255, 0.5);
            border-left: 4px solid transparent;
        }

        .timeline:nth-child(1) {
            animation-delay: 0.2s;
        }

        .timeline:nth-child(2) {
            animation-delay: 0.4s;
        }

        .timeline:nth-child(3) {
            animation-delay: 0.6s;
        }

        .timeline:hover {
            background: linear-gradient(90deg, rgba(59, 68, 246, 0.1), rgba(255, 215, 0, 0.1));
            transform: translateX(15px) scale(1.02);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
            border-left: 4px solid #3b44f6;
        }

        .timeline h4 {
            font-weight: 900;
            margin: 0 0 5px 0;
            font-size: 1.3em;
            color: #1e1b4b;
        }

        .timeline small {
            color: #666;
            transition: all 0.3s ease;
            font-weight: 600;
            display: inline-block;
            padding: 3px 10px;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 20px;
        }

        .timeline:hover small {
            color: #fff;
            background: #3b44f6;
            transform: scale(1.05);
        }

        .timeline p {
            margin-top: 10px;
            font-style: italic;
        }

        /* Responsive */
        @media(max-width:900px) {
            .container {
                grid-template-columns: 1fr;
                gap: 20px;
            }

            .profile-image-wrapper {
                width: 250px;
                height: 250px;
            }

            .left,
            .right {
                animation: fadeIn 1s ease-out;
                padding: 20px;
            }

            .welcome-letter h1 {
                font-size: 2.5em;
            }
        }
    </style>
</head>

<body>
    <div class="bar">✨ PORTFOLIO • 2026 • ANDRIANANTENAINA Tsiory Ny Antsa • PORTFOLIO • 2026 ✨</div>

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
            <span>✨</span> Tsiory Ny Antsa <span>✨</span>
        </div>
    </div>

    <div class="container">
        <!-- LEFT -->
        <div class="left">
            <div class="profile-container">
                <div class="profile-image-wrapper">
                    <img src="https://scontent.ftnr2-2.fna.fbcdn.net/v/t39.30808-6/645751332_122112903753211419_5620609322743338792_n.jpg?_nc_cat=107&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=N_hr6gbaj04Q7kNvwGPZw3r&_nc_oc=AdnzD8scRuebFW-ks8X9NZj60aE1fCz4rjUB0UAb26iL6r8shn_PsV1sEUpmloB51A4&_nc_zt=23&_nc_ht=scontent.ftnr2-2.fna&_nc_gid=65jiCVUPFzZ5MX-FVklNGw&_nc_ss=8&oh=00_Aft1pAUdpapyPz79IlZTRdfKzhwYzMlr1jDpMxZSuHOAYg&oe=69AA5AB9"
                        alt="Photo de profil Tsiory Ny Antsa"
                        onerror="this.classList.add('error'); this.src='data:https://scontent.ftnr2-2.fna.fbcdn.net/v/t39.30808-6/645751332_122112903753211419_5620609322743338792_n.jpg?_nc_cat=107&ccb=1-7&_nc_sid=1d70fc&_nc_ohc=N_hr6gbaj04Q7kNvwGPZw3r&_nc_oc=AdnzD8scRuebFW-ks8X9NZj60aE1fCz4rjUB0UAb26iL6r8shn_PsV1sEUpmloB51A4&_nc_zt=23&_nc_ht=scontent.ftnr2-2.fna&_nc_gid=65jiCVUPFzZ5MX-FVklNGw&_nc_ss=8&oh=00_Aft1pAUdpapyPz79IlZTRdfKzhwYzMlr1jDpMxZSuHOAYg&oe=69AA5AB9">
                    <div class="image-fallback">📸</div>
                </div>

                <!-- NOM SOUS L'IMAGE -->
                <div class="profile-name">
                    <span style="--i:1">T</span><span style="--i:2">s</span><span style="--i:3">i</span><span
                        style="--i:4">o</span><span style="--i:5">r</span><span style="--i:6">y</span><span
                        style="--i:7">&nbsp;</span>
                    <span style="--i:8">N</span><span style="--i:9">y</span><span style="--i:10">&nbsp;</span>
                    <span style="--i:11">A</span><span style="--i:12">n</span><span style="--i:13">t</span><span
                        style="--i:14">s</span><span style="--i:15">a</span>
                </div>
            </div>

            <div class="section contact">
                <h3>📱 CONTACT</h3>
                <p>📞 0385907180 - 0334127027</p>
                <p>🎂 26 Septembre 2009</p>
                <p>📧 andrianantenainatsiorynyantsa@gmail.com</p>
                <p>💬 WHATSAPP: 0334127027</p>
            </div>

            <div class="section">
                <h3>💻 TECHNICAL SKILLS</h3>
                <div class="skills">
                    <div class="skill-box">CSS</div>
                    <div class="skill-box">HTML</div>
                    <div class="skill-box">EXCEL</div>
                    <div class="skill-box">WORD</div>
                </div>
            </div>

            <div class="section">
                <h3>🗣️ LANGUAGES</h3>
                <p>🇲🇬 MALAGASY – Langue maternelle</p>
                <p>🇫🇷 FRANÇAIS – Courant</p>
                <p>ANGLAIS - Courant</p>
            </div>

            <div class="section">
                <h3>🎯 INTERESTS</h3>
                <div class="tags">
                    <div class="tag">🎨 Design</div>
                    <div class="tag">🎵 Musique</div>
                    <div class="tag">🎬 Cinéma</div>
                    <div class="tag">🎮 Jeux vidéo</div>
                </div>
            </div>
        </div>

        <!-- RIGHT -->
        <div class="right">
            <div class="about">
                <h2>À PROPOS DE MOI</h2>
                <p>✨ Je débute dans la création de sites web et dans le codage, et je suis en voie d'expansion dans ce
                    domaine passionnant. Chaque jour est une nouvelle opportunité d'apprendre et de créer !</p>
            </div>

            <div class="section">
                <h3>🎓 EDUCATION</h3>
                <div class="timeline">
                    <h4>EMIT Fianarantsoa</h4>
                    <small>2026 - Présent</small>
                    <p>Études en informatique et développement web</p>
                </div>
            </div>

            <div class="section">
                <h3>💼 EXPERIENCE</h3>
                <div class="timeline">
                    <h4>Création de sites web</h4>
                    <small>2026 - Présent</small>
                    <p>Créateur et designer de sites web - Développement de projets personnels</p>
                </div>

                <div class="timeline">
                    <h4>Informatique de base</h4>
                    <small>2026 - Présent</small>
                    <p>Maîtrise des outils bureautiques (Word, Excel, PowerPoint)</p>
                </div>
            </div>
        </div>
    </div>

    <div class="bar">✨ PORTFOLIO • 2026 • ANDRIANANTENAINA Tsiory Ny Antsa • PORTFOLIO • 2026 ✨</div>
</body>

</html>
