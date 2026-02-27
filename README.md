![IMG_20260226_152915](https://github.com/user-attachments/assets/202a9ae1-5631-4475-b062-8e181f947d83)<!DOCTYPE html>
<html lang="fr">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio - Tsiory Ny Antsa</title>

    <link rel="stylesheet" href="style.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="./css Tsiory.css">
    <style>
        /* Animation pour la lettre de bienvenue */
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

        .welcome-letter h1 {
            font-size: 3em;
            font-weight: 900;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            animation: slideInDown 0.8s ease-out 0.5s both;
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

        /* Style pour le nom sous l'image */
        .profile-container {
            text-align: center;
            margin-bottom: 20px;
        }

        .profile-name {
            margin-top: 20px;
            font-size: 2em;
            font-weight: 900;
            color: #1e1b4b;
            position: relative;
            display: inline-block;
            padding: 10px 30px;
            animation: nameGlow 3s ease-in-out infinite;
        }

        @keyframes nameGlow {

            0%,
            100% {
                text-shadow: 0 0 10px rgba(59, 68, 246, 0.3);
                transform: scale(1);
            }

            50% {
                text-shadow: 0 0 20px rgba(59, 68, 246, 0.7);
                transform: scale(1.05);
            }
        }

        .profile-name::before {
            position: absolute;
            left: -10px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 1.2em;
            animation: starSpin 4s linear infinite;
        }

        .profile-name::after {
            position: absolute;
            right: -10px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 1.2em;
            animation: starSpin 4s linear infinite reverse;
        }

        @keyframes starSpin {
            from {
                transform: translateY(-50%) rotate(0deg);
            }

            to {
                transform: translateY(-50%) rotate(360deg);
            }
        }

        .profile-name span {
            display: inline-block;
            animation: letterBounce 2s ease-in-out infinite;
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

        /* Style pour les titres corrigés */
        .about h2 {
            color: #3b44f6;
            font-weight: 900;
            margin-bottom: 15px;
            font-size: 1.5em;
        }

        .timeline h4 {
            font-weight: 700;
            margin: 0;
        }

        /* Correction des balises fermantes */
        .about h2 {
            color: #3b44f6;
            font-weight: 900;
            margin-bottom: 15px;
        }

        .timeline p {
            margin-top: 5px;
        }
    </style>
</head>

<body>

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

    <div class="container">

        <!-- LEFT -->
        <div class="left">
            <div class="profile-container">
               <img src="IMG_20260226_152915.jpg"
          " alt="Photo de profil" class="profile-image" id="profileImage">
                    style="border-radius: 50%; object-fit: cover;">

                <!-- NOM AJOUTÉ SOUS L'IMAGE -->
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

        <!-- RIGHT -->
        <div class="right">

            <div class="about">
                <h2>A PROPOS DE MOI</h2>
                <p>je fait que debuter dans la creation des site web et dans le codage et en voie d'expention
                    dans ce domaine</p>
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
                    <small>2026-now</small>
                    <p>createur et designeur de site web</p>
                </div>

                <div class="timeline">
                    <h4>informatique de base</h4>
                    <small>2026 - Now</small>
                    <p>experience bureautique (word,exel,power point)</p>
                </div>

            </div>

        </div>

    </div>

    <div class="bar">PORTFOLIO • 2026 • ANDRIANANTENAINA Tsiory Ny Antsa • PORTFOLIO • 2026</div>

</body>

</html>
  

