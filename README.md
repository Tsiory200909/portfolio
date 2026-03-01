<style>
    body {
        background: #f4efe6;
        color: #222;
        animation: fadeIn 1.2s ease;
        width: 100%;
        overflow-x: hidden;
    }

    /* ANIMATIONS */
    @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    @keyframes slideDown { from { transform: translateY(-100%); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
    @keyframes slideInLeft { from { transform: translateX(-40px); opacity: 0; } to { transform: translateX(0); opacity: 1; } }
    @keyframes slideInRight { from { transform: translateX(40px); opacity: 0; } to { transform: translateX(0); opacity: 1; } }
    @keyframes skillPulse { 0% { box-shadow: 0 0 0 0 rgba(59, 68, 246, 0.4); } 50% { box-shadow: 0 0 0 10px rgba(59, 68, 246, 0); } }
    @keyframes tagFloat { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-4px); } }
    @keyframes welcomePop { 0% { transform: scale(0.6) rotate(-3deg); opacity: 0; } 100% { transform: scale(1) rotate(0); opacity: 1; } }
    @keyframes nameGlow { 0%,100% { text-shadow: 0 0 8px rgba(59,68,246,0.4); letter-spacing: 1px; } 50% { text-shadow: 0 0 20px rgba(255,215,0,0.6); letter-spacing: 3px; } }
    @keyframes gradientFlow { 0% { background-position: 0% 50%; } 50% { background-position: 100% 50%; } 100% { background-position: 0% 50%; } }
    @keyframes letterBounce { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-5px); } }

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
    .bar::-webkit-scrollbar { display: none; }

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
        box-shadow: 0 15px 35px rgba(0,0,0,0.25);
        animation: welcomePop 1.2s, gradientFlow 6s infinite;
        border: 3px solid gold;
    }
    .welcome-letter h1 { font-size: clamp(1.8rem, 6vw, 3.5rem); font-weight: 900; }
    .welcome-letter p { font-size: clamp(0.9rem, 3vw, 1.2rem); background: rgba(255,255,255,0.1); padding: clamp(8px, 2.5vw, 15px); border-radius: 18px; }
    .welcome-signature { font-size: clamp(1.5rem, 5vw, 2.3rem); text-shadow: 0 0 10px gold; }

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
    .left, .right {
        background: rgba(255,255,255,0.7);
        backdrop-filter: blur(12px);
        padding: clamp(15px, 3vw, 30px);
        border-radius: 28px;
        box-shadow: 0 10px 30px rgba(0,0,0,0.08);
        border: 2px solid rgba(255,255,255,0.6);
        width: 100%;
    }
    .left { animation: slideInLeft 0.9s; }
    .right { animation: slideInRight 0.9s; }

    /* ===== PHOTO DE PROFIL - AVEC LIEN EN LIGNE VALIDE ===== */
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
        box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        transition: 0.3s;
        background: linear-gradient(135deg, #1e1b4b, #3b44f6);
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
        background: rgba(255,255,255,0.4);
        backdrop-filter: blur(4px);
        transition: 0.25s;
    }
    .section:hover {
        transform: translateY(-5px);
        background: rgba(255,255,255,0.7);
        box-shadow: 0 12px 25px rgba(59,68,246,0.15);
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
    .about:hover h2::after { width: 100%; }
    .about p {
        background: rgba(255,255,255,0.5);
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
    .timeline h4 { font-size: clamp(1.1rem, 3vw, 1.3rem); color: #1e1b4b; }
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
        .container { grid-template-columns: 1fr; }
        .profile-image-wrapper { width: min(250px, 50vw); height: min(250px, 50vw); }
    }
    @media screen and (max-width: 550px) {
        .welcome-letter h1 { font-size: 1.9rem; }
    }
</style>

<!-- BARRE ANNONCE -->
<div class="bar">
    🚀 PORTFOLIO OFFICIEL - MISE À JOUR 2026 ⚡ TOUJOURS EN LIGNE ✨
</div>

<!-- LETTRE DE BIENVENUE -->
<div class="welcome-letter">
    <h1>✨ BIENVENUE DANS MON UNIVERS ✨</h1>
    <p>🎯 Créatif • Développeur • Innovateur 🎯</p>
    <div class="welcome-signature">⬇️ DÉCOUVREZ MON PARCOURS ⬇️</div>
</div>

<!-- CONTENEUR PRINCIPAL -->
<div class="container">
    <!-- COLONNE GAUCHE (PHOTO + INFOS) -->
    <div class="left">
        <div class="profile-container">
            <div class="profile-image-wrapper">
                <!-- VOTRE PHOTO - LIEN DIRECT DEPUIS IMGBB -->
                <img src="https://i.ibb.co/qCk2k8k/photo-profil.jpg" alt="Photo de profil">
            </div>
            <div class="profile-name">
                <span style="--i:1;">V</span>
                <span style="--i:2;">O</span>
                <span style="--i:3;">T</span>
                <span style="--i:4;">R</span>
                <span style="--i:5;">E</span>
                <span style="--i:6;">&nbsp;</span>
                <span style="--i:7;">N</span>
                <span style="--i:8;">O</span>
                <span style="--i:9;">M</span>
            </div>
        </div>

        <!-- SECTION CONTACT -->
        <div class="section contact">
            <h3>📬 CONTACT</h3>
            <p>📧 email@professionnel.com</p>
            <p>📱 +33 6 12 34 56 78</p>
            <p>📍 Paris, France</p>
            <p>🔗 linkedin.com/in/votrenom</p>
            <p>🐙 github.com/votrenom</p>
        </div>

        <!-- SECTION COMPÉTENCES -->
        <div class="section">
            <h3>⚡ COMPÉTENCES</h3>
            <div class="skills">
                <span class="skill-box">HTML/CSS</span>
                <span class="skill-box">JavaScript</span>
                <span class="skill-box">React</span>
                <span class="skill-box">Python</span>
                <span class="skill-box">UI/UX</span>
                <span class="skill-box">SEO</span>
            </div>
        </div>

        <!-- SECTION CENTRES D'INTÉRÊT -->
        <div class="section">
            <h3>🎯 CENTRES D'INTÉRÊT</h3>
            <div class="tags">
                <span class="tag">💻 Tech</span>
                <span class="tag">🎨 Design</span>
                <span class="tag">📸 Photo</span>
                <span class="tag">✈️ Voyages</span>
                <span class="tag">🎮 Gaming</span>
                <span class="tag">📚 Lecture</span>
            </div>
        </div>
    </div>

    <!-- COLONNE DROITE (PARCOURS) -->
    <div class="right">
        <div class="about">
            <h2>👨‍💻 À PROPOS</h2>
            <p>Étudiant passionné par le développement web et le design, je crée des expériences numériques uniques. Mon objectif : allier créativité et performance pour donner vie à des projets innovants. 🚀</p>
        </div>

        <!-- SECTION EXPÉRIENCES -->
        <div class="section">
            <h3>💼 EXPÉRIENCES</h3>
            <div class="timeline">
                <h4>🚀 Développeur Front-End · Startup XYZ</h4>
                <small>2025 - Présent</small>
                <p>Création d'interfaces responsives · Optimisation des performances · Collaboration en équipe agile</p>
            </div>
            <div class="timeline">
                <h4>🎨 Designer UI/UX · Agence Créative</h4>
                <small>2024 - 2025</small>
                <p>Conception de maquettes · Tests utilisateurs · Amélioration de l'expérience client</p>
            </div>
        </div>

        <!-- SECTION FORMATION -->
        <div class="section">
            <h3>🎓 FORMATION</h3>
            <div class="timeline">
                <h4>📚 Master Développement Web · Université Paris</h4>
                <small>2024 - 2026</small>
                <p>Spécialisation en applications modernes et frameworks JavaScript</p>
            </div>
            <div class="timeline">
                <h4>📐 Bachelor Design Numérique · École de Design</h4>
                <small>2021 - 2024</small>
                <p>Formation aux fondamentaux du design et de l'ergonomie</p>
            </div>
        </div>

        <!-- SECTION PROJETS -->
        <div class="section">
            <h3>🔨 PROJETS RÉCENTS</h3>
            <div class="timeline">
                <h4>📱 Application Mobile Santé</h4>
                <p>Développement React Native · Interface intuitive · Suivi des objectifs</p>
            </div>
            <div class="timeline">
                <h4>🛒 E-commerce Éco-responsable</h4>
                <p>Site vitrine avec panier · Filtres dynamiques · Paiement sécurisé</p>
            </div>
        </div>
    </div>
</div>
