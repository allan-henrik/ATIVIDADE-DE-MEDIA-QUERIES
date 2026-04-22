<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>NexusPlay | A Arena dos Deuses</title>
    <style>
        /* RESET e ESTILOS GLOBAIS - LARGURA FIXA NÃO RESPONSIVA */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0a0c12;
            font-family: 'Segoe UI', 'Orbitron', 'Poppins', 'Arial', sans-serif;
            line-height: 1.4;
            color: #eef5ff;
            width: 100%;
            overflow-x: auto; /* permite scroll horizontal se necessário, mas layout fixo */
        }

        /* CONTAINER PRINCIPAL COM LARGURA FIXA - NÃO RESPONSIVA */
        .fixed-container {
            width: 1280px;
            margin: 0 auto;
            background-color: #0a0c12;
            box-shadow: 0 0 40px rgba(0,0,0,0.5);
        }

        /* ========== HEADER ========== */
        .main-header {
            background: linear-gradient(135deg, #0f0f1a 0%, #1a1a2f 100%);
            border-bottom: 3px solid #ff3366;
            padding: 0 40px;
            height: 90px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo-area h1 {
            font-family: 'Orbitron', monospace;
            font-size: 32px;
            letter-spacing: 3px;
            background: linear-gradient(135deg, #ff3366, #ffaa44);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            text-shadow: 0 0 8px rgba(255,51,102,0.3);
        }

        .logo-area p {
            font-size: 12px;
            color: #9aa2bf;
            letter-spacing: 1px;
        }

        .nav-links {
            display: flex;
            gap: 32px;
        }

        .nav-links a {
            color: #eef5ff;
            text-decoration: none;
            font-weight: 600;
            font-size: 18px;
            transition: 0.2s;
            padding: 8px 0;
            border-bottom: 2px solid transparent;
        }

        .nav-links a:hover {
            color: #ff6670;
            border-bottom-color: #ff3366;
        }

        /* ========== HERO SECTION ========== */
        .hero {
            background: radial-gradient(circle at 20% 30%, #19212b, #03050b);
            padding: 70px 40px 80px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid #2a2e3f;
        }

        .hero-text {
            max-width: 550px;
        }

        .hero-text .badge {
            background: #ff3366;
            display: inline-block;
            padding: 6px 18px;
            font-size: 14px;
            font-weight: bold;
            border-radius: 30px;
            letter-spacing: 1px;
            margin-bottom: 20px;
            box-shadow: 0 2px 12px rgba(255,51,102,0.4);
        }

        .hero-text h2 {
            font-size: 54px;
            font-weight: 800;
            line-height: 1.2;
            margin-bottom: 20px;
        }

        .hero-text h2 span {
            color: #ffaa44;
            text-shadow: 0 0 6px #ffaa44;
        }

        .hero-text p {
            font-size: 18px;
            color: #bdc3e0;
            margin-bottom: 32px;
            line-height: 1.5;
        }

        .btn-group {
            display: flex;
            gap: 20px;
        }

        .btn-primary {
            background: #ff3366;
            border: none;
            padding: 14px 32px;
            font-size: 18px;
            font-weight: bold;
            color: white;
            cursor: pointer;
            border-radius: 60px;
            transition: 0.2s;
            font-family: inherit;
            box-shadow: 0 6px 0 #a01e42;
        }

        .btn-primary:hover {
            background: #ff5577;
            transform: translateY(-2px);
            box-shadow: 0 8px 0 #a01e42;
        }

        .btn-secondary {
            background: transparent;
            border: 2px solid #ffaa44;
            padding: 12px 30px;
            font-size: 18px;
            font-weight: bold;
            color: #ffdd99;
            cursor: pointer;
            border-radius: 60px;
            transition: 0.2s;
        }

        .btn-secondary:hover {
            background: rgba(255,170,68,0.1);
            border-color: #ffcc66;
            color: #fff0c0;
        }

        .hero-image img {
            width: 480px;
            filter: drop-shadow(0 10px 20px rgba(0,0,0,0.6));
        }

        /* ========== JOGOS EM DESTAQUE ========== */
        .featured {
            padding: 70px 40px 60px 40px;
            background: #0f111a;
        }

        .section-title {
            font-size: 38px;
            text-align: center;
            margin-bottom: 50px;
            font-weight: 700;
            letter-spacing: -0.5px;
        }

        .section-title span {
            color: #ffaa44;
            border-bottom: 4px solid #ff3366;
            padding-bottom: 6px;
        }

        .games-grid {
            display: flex;
            gap: 28px;
            justify-content: center;
        }

        .game-card {
            background: #181c28;
            width: 280px;
            border-radius: 20px;
            overflow: hidden;
            transition: 0.2s linear;
            border: 1px solid #2a2f3f;
        }

        .game-card:hover {
            transform: translateY(-8px);
            border-color: #ff6680;
            box-shadow: 0 12px 26px rgba(0,0,0,0.5);
        }

        .game-img {
            height: 170px;
            background-size: cover;
            background-position: center;
        }

        .game-info {
            padding: 20px 18px 24px;
        }

        .game-info h3 {
            font-size: 24px;
            margin-bottom: 8px;
        }

        .game-info p {
            color: #9fa9c9;
            font-size: 14px;
            margin-bottom: 20px;
        }

        .game-tag {
            display: inline-block;
            background: #ff336620;
            color: #ff7799;
            padding: 4px 12px;
            border-radius: 40px;
            font-size: 12px;
            font-weight: bold;
        }

        /* ========== BANNER PROMO ========== */
        .promo-banner {
            background: linear-gradient(90deg, #1a1c2c, #221f32);
            margin: 0 40px 40px 40px;
            border-radius: 28px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 20px 40px;
            border-left: 8px solid #ffaa44;
        }

        .promo-text h4 {
            font-size: 28px;
            font-weight: 700;
        }

        .promo-text p {
            font-size: 16px;
            color: #cdd4f0;
        }

        .promo-btn {
            background: #ffaa44;
            color: #1e1b2c;
            border: none;
            font-weight: bold;
            padding: 12px 32px;
            border-radius: 40px;
            font-size: 18px;
            cursor: pointer;
            transition: 0.2s;
        }

        .promo-btn:hover {
            background: #ffcc66;
            transform: scale(0.98);
        }

        /* ========== MELHORES JOGADORES ========== */
        .rank-section {
            padding: 30px 40px 70px 40px;
            background: #0c0e16;
        }

        .rank-header {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
            margin-bottom: 30px;
        }

        .rank-header h3 {
            font-size: 32px;
        }

        .rank-header a {
            color: #ffaa66;
            text-decoration: none;
            font-weight: 500;
        }

        .rank-table {
            width: 100%;
            border-collapse: collapse;
            background: #10131e;
            border-radius: 24px;
            overflow: hidden;
        }

        .rank-table th, .rank-table td {
            padding: 18px 20px;
            text-align: left;
            border-bottom: 1px solid #22273a;
        }

        .rank-table th {
            background: #1e2337;
            color: #ffcc99;
            font-weight: 700;
            font-size: 16px;
        }

        .rank-table tr:last-child td {
            border-bottom: none;
        }

        .rank-number {
            font-weight: bold;
            font-size: 20px;
            width: 60px;
            color: #ffaa55;
        }

        .player-name {
            font-weight: 600;
        }

        .player-score {
            font-family: monospace;
            font-size: 18px;
            font-weight: bold;
            color: #66ffcc;
        }

        /* ========== NEWSLETTER ========== */
        .newsletter {
            background: #131725;
            margin: 20px 40px 50px 40px;
            border-radius: 40px;
            padding: 48px 60px;
            text-align: center;
            box-shadow: inset 0 0 0 1px #2a2f42, 0 10px 20px rgba(0,0,0,0.3);
        }

        .newsletter h3 {
            font-size: 32px;
            margin-bottom: 12px;
        }

        .newsletter p {
            color: #aeb9db;
            margin-bottom: 28px;
        }

        .form-group {
            display: flex;
            justify-content: center;
            gap: 12px;
        }

        .form-group input {
            background: #0b0e18;
            border: 1px solid #373e5a;
            padding: 14px 20px;
            width: 320px;
            border-radius: 60px;
            font-size: 16px;
            color: white;
            outline: none;
        }

        .form-group input:focus {
            border-color: #ff6680;
        }

        .form-group button {
            background: #ff3366;
            border: none;
            padding: 0 28px;
            border-radius: 60px;
            font-weight: bold;
            font-size: 16px;
            color: white;
            cursor: pointer;
            transition: 0.2s;
        }

        .form-group button:hover {
            background: #ff5b85;
        }

        /* ========== FOOTER ========== */
        .main-footer {
            background: #07090f;
            padding: 40px 40px 30px 40px;
            border-top: 1px solid #252a3c;
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
        }

        .footer-col {
            width: 240px;
        }

        .footer-col h4 {
            font-size: 20px;
            margin-bottom: 20px;
            color: #ffaa66;
        }

        .footer-col ul {
            list-style: none;
        }

        .footer-col li {
            margin-bottom: 12px;
        }

        .footer-col a {
            color: #a0a8ca;
            text-decoration: none;
            transition: 0.2s;
        }

        .footer-col a:hover {
            color: #ff6680;
        }

        .copyright {
            text-align: center;
            padding: 24px 0 20px;
            background: #030409;
            color: #6c7295;
            font-size: 13px;
            border-top: 1px solid #1a1e2c;
            width: 100%;
        }

        /* elementos extras fixos */
        hr {
            display: none;
        }

        /* largura fixa pra evitar qualquer comportamento responsivo */
        img, iframe, video {
            max-width: none;
        }

        .hero-image img {
            width: 480px;
            height: auto;
        }
    </style>
</head>
<body>
<div class="fixed-container">
    <!-- CABEÇALHO -->
    <header class="main-header">
        <div class="logo-area">
            <h1>⚡ NEXUSPLAY</h1>
            <p>REINO DOS JOGADORES</p>
        </div>
        <div class="nav-links">
            <a href="#">INÍCIO</a>
            <a href="#">JOGOS</a>
            <a href="#">RANKING</a>
            <a href="#">COMUNIDADE</a>
            <a href="#">LOJA</a>
        </div>
    </header>

    <!-- HERO PRINCIPAL -->
    <section class="hero">
        <div class="hero-text">
            <div class="badge">🔥 NOVO MUNDO ABERTO</div>
            <h2>DOMINE A <span>ARENA</span> <br> DOS DEUSES</h2>
            <p>Entre no jogo de ação definitivo. Batalhas épicas, gráficos de última geração e uma comunidade que cresce a cada segundo. Derrote seus inimigos e suba no ranking global agora!</p>
            <div class="btn-group">
                <button class="btn-primary">JOGAR AGORA</button>
                <button class="btn-secondary">ASSISTIR TRAILER</button>
            </div>
        </div>
        <div class="hero-image">
            <img src="https://placehold.co/480x400/1f1a2e/ff6680?text=GUERREIRO+DRAGON&font=montserrat&quot; alt="Personagem Jogo">
        </div>
    </section>

    <!-- JOGOS EM DESTAQUE (CARDS) -->
    <section class="featured">
        <div class="section-title"><span>⚔️ JOGOS EM DESTAQUE ⚔️</span></div>
        <div class="games-grid">
            <div class="game-card">
                <div class="game-img" style="background-image: url('https://placehold.co/280x170/2a1e3c/dd5588?text=Shadow+Legends');"></div&gt;
                <div class="game-info">
                    <h3>Shadow Legends</h3>
                    <p>RPG sombrio com combates táticos e heróis lendários.</p>
                    <span class="game-tag">MMORPG</span>
                </div>
            </div>
            <div class="game-card">
                <div class="game-img" style="background-image: url('https://placehold.co/280x170/1f2c2e/44ffaa?text=Cyber+Strike');"></div&gt;
                <div class="game-info">
                    <h3>Cyber Strike</h3>
                    <p>FPS futurista, alta velocidade e rivalidades intensas.</p>
                    <span class="game-tag">FPS</span>
                </div>
            </div>
            <div class="game-card">
                <div class="game-img" style="background-image: url('https://placehold.co/280x170/261f2a/f0aa44?text=Dragonspire');"></div&gt;
                <div class="game-info">
                    <h3>Dragonspire</h3>
                    <p>Domine dragões e reconstrua reinos em mundo aberto.</p>
                    <span class="game-tag">AÇÃO</span>
                </div>
            </div>
            <div class="game-card">
                <div class="game-img" style="background-image: url('https://placehold.co/280x170/141e30/66ccff?text=Racing+Xtreme');"></div&gt;
                <div class="game-info">
                    <h3>Racing Xtreme</h3>
                    <p>Corridas radicais com nitro infinito e pistas impossíveis.</p>
                    <span class="game-tag">CORRIDA</span>
                </div>
            </div>
        </div>
    </section>

    <!-- BANNER PROMOCIONAL -->
    <div class="promo-banner">
        <div class="promo-text">
            <h4>🏆 PROMOÇÃO DE LANÇAMENTO 🏆</h4>
            <p>Até 50% de desconto em skins lendárias + bônus de 1000 moedas para novos guerreiros!</p>
        </div>
        <button class="promo-btn">RESGATAR OFERTA</button>
    </div>

    <!-- RANKING DOS MELHORES JOGADORES -->
    <section class="rank-section">
        <div class="rank-header">
            <h3>🏅 LENDA DOS JOGADORES 🏅</h3>
            <a href="#">VER RANKING COMPLETO →</a>
        </div>
        <table class="rank-table">
            <thead>
                <tr><th>#</th><th>JOGADOR</th><th>PONTOS</th><th>CLASSE</th></tr>
            </thead>
            <tbody>
                <tr><td class="rank-number">1</td><td class="player-name">⚡ Kaelen_SV</td><td class="player-score">12,450</td><td>Mago Rubro</td></tr>
                <tr><td class="rank-number">2</td><td class="player-name">🔥 Nyx_Furia</td><td class="player-score">11,870</td><td>Assassina Sombria</td></tr>
                <tr><td class="rank-number">3</td><td class="player-name">🛡️ Thorin_Stone</td><td class="player-score">10,990</td><td>Paladino Colossal</td></tr>
                <tr><td class="rank-number">4</td><td class="player-name">🎯 MirageX</td><td class="player-score">9,540</td><td>Arqueiro Fatal</td></tr>
                <tr><td class="rank-number">5</td><td class="player-name">🌀 Vex_Core</td><td class="player-score">8,210</td><td>Mestre das Runas</td></tr>
            </tbody>
        </table>
    </section>

    <!-- NEWSLETTER E COMUNIDADE -->
    <div class="newsletter">
        <h3>📢 Entre na Irmandade dos Jogadores</h3>
        <p>Receba códigos secretos, novidades e convites para torneios semanais.</p>
        <div class="form-group">
            <input type="email" placeholder="Seu melhor e-mail gamer">
            <button>INSCREVER-SE</button>
        </div>
    </div>

    <!-- FOOTER COM INFORMAÇÕES -->
    <footer class="main-footer">
        <div class="footer-col">
            <h4>NEXUSPLAY</h4>
            <ul>
                <li><a href="#">Sobre nós</a></li>
                <li><a href="#">Carreiras</a></li>
                <li><a href="#">Imprensa</a></li>
                <li><a href="#">Termos de serviço</a></li>
            </ul>
        </div>
        <div class="footer-col">
            <h4>JOGOS</h4>
            <ul>
                <li><a href="#">Todos os jogos</a></li>
                <li><a href="#">Novidades</a></li>
                <li><a href="#">Próximos lançamentos</a></li>
                <li><a href="#">Jogos gratuitos</a></li>
            </ul>
        </div>
        <div class="footer-col">
            <h4>SUPORTE</h4>
            <ul>
                <li><a href="#">Central de ajuda</a></li>
                <li><a href="#">Comunidade</a></li>
                <li><a href="#">Status dos servidores</a></li>
                <li><a href="#">Reportar bug</a></li>
            </ul>
        </div>
        <div class="footer-col">
            <h4>SOCIAL</h4>
            <ul>
                <li><a href="#">Discord</a></li>
                <li><a href="#">Twitter/X</a></li>
                <li><a href="#">Twitch</a></li>
                <li><a href="#">Youtube</a></li>
            </ul>
        </div>
    </footer>
    <div class="copyright">
        © 2025 NEXUSPLAY — Todos os direitos reservados. Arena dos Deuses é uma marca registrada. Prepare-se para batalhar!
    </div>
</div>

<!-- PEQUENO SCRIPT PARA SIMULAR INTERAÇÃO (NÃO RESPONSIVO, APENAS ALERTAS) -->
<script>
    (function() {
        // ações simples para dar vida aos botões, sem alterar layout responsivo
        const btnJogar = document.querySelector('.btn-primary');
        const btnTrailer = document.querySelector('.btn-secondary');
        const btnPromo = document.querySelector('.promo-btn');
        const btnNews = document.querySelector('.form-group button');
        const emailInput = document.querySelector('.form-group input');

        if(btnJogar) {
            btnJogar.addEventListener('click', () => {
                alert("⚡ Modo batalha iniciado! Prepare-se para a arena (demo interativa).");
            });
        }
        if(btnTrailer) {
            btnTrailer.addEventListener('click', () => {
                alert("🎬 Trailer épico em breve! Acompanhe as redes da NexusPlay.");
            });
        }
        if(btnPromo) {
            btnPromo.addEventListener('click', () => {
                alert("🎁 Código promocional aplicado! Use DRAGON50 na loja para ganhar 50% OFF.");
            });
        }
        if(btnNews) {
            btnNews.addEventListener('click', () => {
                let email = emailInput ? emailInput.value.trim() : "";
                if(email === "" || !email.includes("@")) {
                    alert("📧 Por favor, insira um e-mail válido para receber as novidades!");
                } else {
                    alert(`✅ Obrigado, guerreiro! Enviamos um código de boas-vindas para ${email}`);
                    emailInput.value = "";
                }
            });
        }

        // qualquer clique nos links de navegação simula navegação (apenas demonstração)
        const navLinks = document.querySelectorAll('.nav-links a');
        navLinks.forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                alert(`🚀 Navegando para: ${link.innerText} (versão estática da landing)`);
            });
        });
        const rankLink = document.querySelector('.rank-header a');
        if(rankLink) {
            rankLink.addEventListener('click', (e) => {
                e.preventDefault();
                alert("🏆 Ranking completo disponível em breve. Fique ligado!");
            });
        }
        const footerLinks = document.querySelectorAll('.footer-col a');
        footerLinks.forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                alert(`🔗 Seção "${link.innerText}" - Em desenvolvimento, mas a NexusPlay agradece seu interesse!`);
            });
        });
    })();
</script>
</body>
</html>
