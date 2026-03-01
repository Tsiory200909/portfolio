<!DOCTYPE html>
<html lang="fr">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes">
    <title>Portfolio · Tsiory Ny Antsa</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        /* (Gardez tout le style existant, il est parfait) */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Montserrat', sans-serif;
        }

        body {
            background: #f4efe6;
            color: #222;
            animation: fadeIn 1.2s ease;
            width: 100%;
            overflow-x: hidden;
        }

        /* ANIMATIONS */
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
                transform: translateX(-40px);
                opacity: 0;
            }

            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        @keyframes slideInRight {
            from {
                transform: translateX(40px);
                opacity: 0;
            }

            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        @keyframes skillPulse {
            0% {
                box-shadow: 0 0 0 0 rgba(59, 68, 246, 0.4);
            }

            50% {
                box-shadow: 0 0 0 10px rgba(59, 68, 246, 0);
            }
        }

        @keyframes tagFloat {

            0%,
            100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-4px);
            }
        }

        @keyframes welcomePop {
            0% {
                transform: scale(0.6) rotate(-3deg);
                opacity: 0;
            }

            100% {
                transform: scale(1) rotate(0);
                opacity: 1;
            }
        }

        @keyframes nameGlow {

            0%,
            100% {
                text-shadow: 0 0 8px rgba(59, 68, 246, 0.4);
                letter-spacing: 1px;
            }

            50% {
                text-shadow: 0 0 20px rgba(255, 215, 0, 0.6);
                letter-spacing: 3px;
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

        @keyframes letterBounce {

            0%,
            100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-5px);
            }
        }

        /* BAR */
        .bar {
            background: linear-gradient(90deg, #1e1b4b, #3b44f6, #1e1b4b);
            background-size: 200% 100%;
            color: #fff;
            padding: clamp(8px, 2vw, 14px);
            text-align: center;
            font-size: clamp(12px, 2.5vw, 16px);
            letter-spacing: 1.5px;
            animation: slideDown 0.7s, gradientFlow 4s infinite;
            font-weight: 700;
            text-transform: uppercase;
            border-bottom: 2px solid gold;
            border-top: 2px solid gold;
            white-space: nowrap;
            overflow-x: auto;
            scrollbar-width: none;
        }

        .bar::-webkit-scrollbar {
            display: none;
        }

        /* WELCOME LETTER */
        .welcome-letter {
            background: linear-gradient(135deg, #1e1b4b, #3b44f6, #1e1b4b);
            background-size: 200% 200%;
            color: white;
            padding: clamp(25px, 6vw, 50px) clamp(15px, 5vw, 30px);
            text-align: center;
            margin: 20px auto;
            border-radius: 30px;
            width: 95%;
            max-width: 1300px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.25);
            animation: welcomePop 1.2s, gradientFlow 6s infinite;
            border: 3px solid gold;
        }

        .welcome-letter h1 {
            font-size: clamp(1.8rem, 6vw, 3.5rem);
            font-weight: 900;
        }

        .welcome-letter p {
            font-size: clamp(0.9rem, 3vw, 1.2rem);
            background: rgba(255, 255, 255, 0.1);
            padding: clamp(8px, 2.5vw, 15px);
            border-radius: 18px;
        }

        .welcome-signature {
            font-size: clamp(1.5rem, 5vw, 2.3rem);
            text-shadow: 0 0 10px gold;
        }

        /* CONTAINER */
        .container {
            width: 95%;
            max-width: 1300px;
            margin: 30px auto;
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: clamp(15px, 3vw, 40px);
        }

        /* LEFT & RIGHT */
        .left,
        .right {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(12px);
            padding: clamp(15px, 3vw, 30px);
            border-radius: 28px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            border: 2px solid rgba(255, 255, 255, 0.6);
            width: 100%;
        }

        .left {
            animation: slideInLeft 0.9s;
        }

        .right {
            animation: slideInRight 0.9s;
        }

        /* ===== PHOTO DE PROFIL - VERSION CORRIGÉE ===== */
        .profile-container {
            text-align: center;
            margin-bottom: 10px;
        }

        .profile-image-wrapper {
            position: relative;
            width: min(280px, 65vw);
            height: min(280px, 65vw);
            margin: 0 auto;
            border-radius: 50%;
            overflow: hidden;
            border: 5px solid gold;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
            transition: 0.3s;
            background: linear-gradient(135deg, #1e1b4b, #3b44f6);
            /* fallback élégant */
        }

        .profile-image-wrapper:hover {
            transform: scale(1.03) rotate(2deg);
            border-color: #3b44f6;
        }

        .profile-image-wrapper img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        /* SOLUTION 1: Image hébergée sur un service fiable (ImgBB, PostImage, etc.) */
        /* J'utilise une image placeholder mais VOUS DEVEZ LA REMPLACER par votre vrai lien */

        /* NOM */
        .profile-name {
            margin-top: 20px;
            font-size: clamp(1.6rem, 5vw, 2.2rem);
            font-weight: 900;
            background: linear-gradient(90deg, #1e1b4b, #3b44f6, #1e1b4b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-size: 200% auto;
            animation: nameGlow 3s infinite;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 0 3px;
        }

        .profile-name span {
            display: inline-block;
            animation: letterBounce 2s infinite;
            animation-delay: calc(0.08s * var(--i));
        }

        /* SECTIONS */
        .section {
            margin: 35px 0 25px;
            padding: 18px 15px;
            border-radius: 20px;
            background: rgba(255, 255, 255, 0.4);
            backdrop-filter: blur(4px);
            transition: 0.25s;
        }

        .section:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.7);
            box-shadow: 0 12px 25px rgba(59, 68, 246, 0.15);
        }

        .section h3 {
            color: #1e1b4b;
            font-weight: 900;
            margin-bottom: 18px;
            font-size: clamp(1.2rem, 3.5vw, 1.5rem);
            border-left: 5px solid gold;
            padding-left: 12px;
        }

        /* CONTACT */
        .contact p {
            margin-bottom: 10px;
            padding: 8px 12px;
            border-radius: 40px;
            background: white;
            font-weight: 600;
            font-size: clamp(0.85rem, 2.5vw, 1rem);
            transition: 0.2s;
        }

        .contact p:hover {
            background: #3b44f6;
            color: white;
            transform: translateX(8px);
        }

        /* SKILLS */
        .skills {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
        }

        .skill-box {
            background: linear-gradient(145deg, #1e1b4b, #000);
            color: #fff;
            padding: 12px 22px;
            border-radius: 60px;
            font-weight: 700;
            font-size: clamp(0.9rem, 2.2vw, 1.1rem);
            animation: skillPulse 3s infinite;
            transition: 0.25s;
        }

        .skill-box:hover {
            background: #3b44f6;
            transform: scale(1.1) translateY(-5px);
            border: 2px solid gold;
            animation: none;
        }

        /* TAGS */
        .tags {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .tag {
            border: 2px solid #1e1b4b;
            padding: 8px 16px;
            border-radius: 40px;
            font-weight: 600;
            background: white;
            animation: tagFloat 4s infinite;
            font-size: clamp(0.8rem, 2.5vw, 0.95rem);
        }

        .tag:hover {
            background: linear-gradient(130deg, gold, #3b44f6);
            color: white;
            border-color: transparent;
            transform: scale(1.1) rotate(1deg);
            animation: none;
        }

        /* ABOUT */
        .about h2 {
            color: #1e1b4b;
            font-size: clamp(1.8rem, 5vw, 2.2rem);
            font-weight: 900;
            margin-bottom: 15px;
            position: relative;
            display: inline-block;
        }

        .about h2::after {
            content: '';
            display: block;
            width: 70px;
            height: 4px;
            background: gold;
            margin-top: 5px;
            transition: width 0.3s;
        }

        .about:hover h2::after {
            width: 100%;
        }

        .about p {
            background: rgba(255, 255, 255, 0.5);
            padding: 16px 18px;
            border-radius: 25px;
            font-size: clamp(0.95rem, 2.8vw, 1.1rem);
            line-height: 1.7;
        }

        /* TIMELINE */
        .timeline {
            margin: 25px 0;
            padding: 18px 20px;
            background: white;
            border-radius: 18px;
            border-left: 5px solid transparent;
            transition: 0.25s;
        }

        .timeline:hover {
            border-left-color: #3b44f6;
            transform: translateX(5px) scale(1.01);
            background: #faf8ff;
        }

        .timeline h4 {
            font-size: clamp(1.1rem, 3vw, 1.3rem);
            color: #1e1b4b;
        }

        .timeline small {
            background: #eef;
            padding: 4px 14px;
            border-radius: 30px;
            font-weight: 600;
            display: inline-block;
            margin: 6px 0;
        }

        /* RESPONSIVE */
        @media screen and (max-width: 850px) {
            .container {
                grid-template-columns: 1fr;
            }

            .profile-image-wrapper {
                width: min(250px, 50vw);
                height: min(250px, 50vw);
            }
        }

        @media screen and (max-width: 550px) {
            .welcome-letter h1 {
                font-size: 1.9rem;
            }
        }
    </style>
</head>

<body>
    <div class="bar">✨ PORTFOLIO • 2026 • ANDRIANANTENAINA Tsiory Ny Antsa • PORTFOLIO • 2026 ✨</div>

    <div class="welcome-letter">
        <h1>👋 Bienvenue sur mon Portfolio !</h1>
        <p>Bonjour et bienvenue dans mon univers créatif ! Passionné par le développement web et le design, je vous
            invite à découvrir mon parcours, mes compétences et mes réalisations.</p>
        <p>En tant que débutant, je suis constamment en quête d'apprentissage et d'amélioration. Ce portfolio reflète ma
            passion et ma détermination.</p>
        <div class="welcome-signature"><span>✨</span> Tsiory Ny Antsa <span>✨</span></div>
    </div>

    <div class="container">
        <!-- LEFT -->
        <div class="left">
            <div class="profile-container">
                <div class="profile-image-wrapper">
                    <!-- OPTION 1: Utilisez un hébergement d'images fiable (recommandé) -->
                    <img src="https://raw.githubusercontent.com/Tsiory200909/mon-portfolio/refs/heads/main/IMG_20260226_152915.jpg"
                        alt="Tsiory Ny Antsa"
                        onerror="this.onerror=null; this.src='https://via.placeholder.com/500x500/1e1b4b/gold?text=TNA';">

                    <!-- OPTION 2: Si vous avez l'URL directe d'une image (Google Drive, etc.) -->
                    <!-- Décommentez et remplacez par votre lien valide -->
                    <!-- <img src="VOTRE_LIEN_DIRECT_ICI" alt="Tsiory Ny Antsa"> -->
                </div>

                <div class="profile-name">
                    <span style="--i:1">T</span><span style="--i:2">s</span><span style="--i:3">i</span><span
                        style="--i:4">o</span><span style="--i:5">r</span><span style="--i:6">y</span><span
                        style="--i:7"> </span>
                    <span style="--i:8">N</span><span style="--i:9">y</span><span style="--i:10"> </span>
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
                <p>🇬🇧 ANGLAIS – Courant</p>
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
                    <p>Créateur et designer de sites web - Projets personnels</p>
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

    <script>
        // Solution supplémentaire : tentative de chargement avec différents formats
        (function () {
            const img = document.querySelector('.profile-image-wrapper img');

            // Si l'image ne charge pas après 3 secondes, essayer un lien alternatif
            setTimeout(() => {
                if (img && img.naturalWidth === 0) {
                    // Dernier recours : placeholder avec initiales
                    img.src = 'https://via.placeholder.com/500x500/1e1b4b/gold?text=TNA';
                    img.alt = 'Tsiory Ny Antsa';
                }
            }, 3000);
        })();
    </script>
</body>

</html>
