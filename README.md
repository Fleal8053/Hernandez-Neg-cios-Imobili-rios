<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hernandez Negócios Imobiliários</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700&family=Playfair+Display:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --dark1: #1a1a1a;
            --dark2: #0d0d0a;
            --dark3: #0a0a0a;
            --gold1: #C9A84C;
            --gold2: #D4AF37;
        }
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Montserrat', sans-serif;
            color: white;
            background: linear-gradient(135deg, var(--dark3) 0%, var(--dark1) 100%);
            line-height: 1.6;
            overflow-x: hidden;
        }
        h1, h2, h3 {
            font-family: 'Playfair Display', serif;
        }
        a {
            text-decoration: none;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }
        /* Navbar */
        #navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            transition: all 0.3s ease;
        }
        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 70px;
        }
        .logo {
            color: var(--gold1);
            font-size: 1.5rem;
            font-weight: 700;
            font-family: 'Playfair Display', serif;
        }
        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
        }
        .nav-menu a {
            color: white;
            padding: 0.5rem 1rem;
            transition: color 0.3s;
            border-radius: 5px;
        }
        .nav-menu a:hover {
            color: var(--gold1);
            background: rgba(201, 168, 76, 0.1);
        }
        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
            gap: 4px;
        }
        .hamburger span {
            width: 25px;
            height: 3px;
            background: white;
            transition: 0.3s;
        }
        /* Hero */
        #hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            background: radial-gradient(circle at center, var(--dark1) 0%, var(--dark3) 100%);
            padding-top: 70px;
        }
        #hero .hero-content h1 {
            font-size: 4rem;
            color: var(--gold2);
            margin-bottom: 1rem;
        }
        #hero .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }
        .btn-wa {
            display: inline-block;
            background: var(--gold1);
            color: #000;
            padding: 1rem 2.5rem;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(201, 168, 76, 0.4);
        }
        .btn-wa:hover {
            background: var(--gold2);
            transform: scale(1.05) translateY(-2px);
        }
        /* Sections */
        section {
            padding: 100px 0;
        }
        section h2 {
            text-align: center;
            font-size: 3rem;
            color: var(--gold2);
            margin-bottom: 4rem;
        }
        /* Fade-in */
        .fade-in {
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s ease;
        }
        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
        /* Sobre Cards */
        .cards-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        .sobre-card {
            background: var(--dark1);
            padding: 3rem 2rem;
            border-radius: 15px;
            text-align: center;
            border: 1px solid transparent;
            transition: all 0.3s;
        }
        .sobre-card:hover {
            border-color: var(--gold1);
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(201, 168, 76, 0.3);
        }
        .sobre-card i {
            font-size: 4rem;
            color: var(--gold1);
            margin-bottom: 1.5rem;
        }
        .sobre-card h3 {
            color: var(--gold2);
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }
        /* Imóveis */
        .imoveis-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }
        .imovel-card {
            position: relative;
            background: var(--dark1);
            border-radius: 15px;
            overflow: hidden;
            border: 1px solid transparent;
            transition: all 0.4s;
        }
        .imovel-card:hover {
            border-color: var(--gold1);
            transform: translateY(-15px);
            box-shadow: 0 30px 60px rgba(201, 168, 76, 0.4);
        }
        .badge {
            position: absolute;
            top: 1rem;
            left: 1rem;
            background: var(--gold1);
            color: #000;
            padding: 0.5rem 1.2rem;
            border-radius: 25px;
            font-weight: 600;
            font-size: 0.9rem;
            z-index: 2;
        }
        .imovel-card img {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }
        .info {
            padding: 1.5rem;
        }
        .info h3 {
            margin-bottom: 0.5rem;
        }
        .info p {
            opacity: 0.8;
            margin-bottom: 1rem;
        }
        .price {
            font-size: 2rem;
            color: var(--gold2);
            font-weight: 700;
            margin: 1rem 0;
        }
        .btn-interesse {
            display: block;
            width: 100%;
            background: var(--gold1);
            color: #000;
            padding: 1rem;
            border-radius: 8px;
            font-weight: 600;
            text-align: center;
            transition: all 0.3s;
        }
        .btn-interesse:hover {
            background: var(--gold2);
        }
        /* Localização */
        #localizacao iframe {
            width: 100%;
            height: 450px;
            border-radius: 15px;
            border: 2px solid var(--gold1);
        }
        /* Contato */
        .contato-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: start;
        }
        #contactForm {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }
        #contactForm input,
        #contactForm textarea {
            background: var(--dark1);
            border: 1px solid var(--gold1);
            color: white;
            padding: 1rem;
            border-radius: 8px;
            font-family: inherit;
            font-size: 1rem;
        }
        #contactForm input::placeholder,
        #contactForm textarea::placeholder {
            color: rgba(255,255,255,0.6);
        }
        #contactForm button {
            background: var(--gold1);
            color: #000;
            border: none;
            padding: 1.2rem;
            border-radius: 8px;
            font-weight: 600;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s;
        }
        #contactForm button:hover {
            background: var(--gold2);
            transform: translateY(-2px);
        }
        .contato-info {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }
        .contato-info p {
            font-size: 1.3rem;
            display: flex;
            align-items: center;
            gap: 1rem;
        }
        .contato-info i {
            color: var(--gold1);
            width: 30px;
        }
        .contato-info a {
            color: var(--gold1);
        }
        /* Footer */
        footer {
            background: var(--dark1);
            padding: 2rem;
            text-align: center;
            border-top: 1px solid var(--gold1);
        }
        footer p {
            margin-bottom: 0.5rem;
        }
        footer a {
            color: var(--gold1);
        }
        /* Floating WA */
        .floating-wa {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            width: 60px;
            height: 60px;
            background: var(--gold1);
            color: #000;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.8rem;
            box-shadow: 0 10px 30px rgba(201, 168, 76, 0.5);
            animation: pulse 2s infinite;
            z-index: 1000;
            transition: all 0.3s;
        }
        .floating-wa:hover {
            transform: scale(1.1);
            background: var(--gold2);
        }
        @keyframes pulse {
            0% {
                box-shadow: 0 0 0 0 rgba(201, 168, 76, 0.7);
            }
            70% {
                box-shadow: 0 0 0 20px rgba(201, 168, 76, 0);
            }
            100% {
                box-shadow: 0 0 0 0 rgba(201, 168, 76, 0);
            }
        }
        /* Responsive */
        @media (max-width: 768px) {
            .hamburger {
                display: flex;
            }
            .nav-menu {
                position: fixed;
                left: -100%;
                top: 70px;
                flex-direction: column;
                width: 100%;
                background: var(--dark1);
                padding: 2rem 0;
                transition: left 0.3s;
            }
            .nav-menu.active {
                left: 0;
            }
            #hero .hero-content h1 {
                font-size: 2.5rem;
            }
            section h2 {
                font-size: 2.2rem;
            }
            .contato-container {
                grid-template-columns: 1fr;
                gap: 2rem;
            }
            .imoveis-grid {
                grid-template-columns: 1fr;
            }
        }
        html {
            scroll-behavior: smooth;
        }
    </style>
</head>
<body>
    <nav id="navbar">
        <div class="nav-container">
            <div class="logo">Hernandez Negócios Imobiliários</div>
            <ul class="nav-menu">
                <li><a href="#imoveis">Imóveis</a></li>
                <li><a href="#sobre">Sobre</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>
            <div class="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <section id="hero">
        <div class="hero-content container">
            <h1>ENCONTRE O IMÓVEL DOS SEUS SONHOS</h1>
            <p>Seu lar perfeito está aqui. Conte conosco para encontrar a casa ideal!</p>
            <a href="https://wa.me/554994229422?text=Ol%C3%A1%2C%20vim%20do%20site%20da%20Hernandez%20Neg%C3%B3cios%20Imobili%C3%A1rios%20e%20quero%20saber%20mais%20sobre%20os%20im%C3%B3veis." class="btn-wa" target="_blank">
                Fale pelo WhatsApp
            </a>
        </div>
    </section>

    <section id="sobre" class="fade-in">
        <div class="container">
            <h2>Sobre Nós</h2>
            <div class="cards-container">
                <div class="sobre-card">
                    <i class="fas fa-map-marker-alt"></i>
                    <h3>Localização Privilegiada</h3>
                    <p>Imóveis nos melhores bairros de Lages e região, com fácil acesso e infraestrutura completa.</p>
                </div>
                <div class="sobre-card">
                    <i class="fas fa-tag"></i>
                    <h3>Preço Justo</h3>
                    <p>Valores competitivos e negociações transparentes para você investir com segurança.</p>
                </div>
                <div class="sobre-card">
                    <i class="fas fa-users"></i>
                    <h3>Atendimento Personalizado</h3>
                    <p>Equipe dedicada para entender suas necessidades e encontrar o imóvel perfeito.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="imoveis" class="fade-in">
        <div class="container">
            <h2>Nossos Imóveis</h2>
            <div class="imoveis-grid">
                <div class="imovel-card">
                    <div class="badge">Casa 3 Quartos</div>
                    <img src="https://images.unsplash.com/photo-1600585154340-be6161a56a0c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Casa 3 Quartos">
                    <div class="info">
                        <h3>150m² - 3 Quartos - 2 Vagas</h3>
                        <p>Centro</p>
                        <div class="price">R$ 500.000</div>
                        <a href="https://wa.me/554994229422?text=Ol%C3%A1%2C%20tenho%20interesse%20na%20Casa%203%20Quartos%20-%20150m%C2%B2%20-%203%20Quartos%20-%202%20Vagas%20-%20R%24%20500.000%20-%20Centro" class="btn-interesse" target="_blank">Tenho Interesse</a>
                    </div>
                </div>
                <div class="imovel-card">
                    <div class="badge">Apartamento Vista Mar</div>
                    <img src="https://images.unsplash.com/photo-1570129477492-45c003edd2be?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80" alt="Apartamento Vista Mar">
                    <div class="info">
                        <h3>120m² - 2 Quartos - 1 Vaga</h3>
                        <p>Jardim Europa</p>
                        <div class="price">R$ 450.000</div>
                        <a href="https://wa.me/554994229422?text=Ol%C3%A1%2C%20tenho%20interesse%20no%20Apartamento%20Vista%20Mar%20-%20120m%C2%B2%20-%202%20Quartos%20-%201%20Vaga%20-%20R%24%20450.000%20-%20Jardim%20Europa" class="btn-interesse" target="_blank">Tenho Interesse</a>
                    </div>
                </div>
                <div class="imovel-card">
                    <div class="badge">Terreno Nobre</div>
                    <img src="https://images.unsplash.com/photo-1536623481567-12363e9d3985?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80" alt="Terreno Nobre">
                    <div class="info">
                        <h3>500m² - Arborizado</h3>
                        <p>Vila Nova</p>
                        <div class="price">R$ 300.000</div>
                        <a href="https://wa.me/554994229422?text=Ol%C3%A1%2C%20tenho%20interesse%20no%20Terreno%20Nobre%20-%20500m%C2%B2%20Arborizado%20-%20R%24%20300.000%20-%20Vila%20Nova" class="btn-interesse" target="_blank">Tenho Interesse</a>
                    </div>
                </div>
                <div class="imovel-card">
                    <div class="badge">Loja Comercial</div>
                    <img src="https://images.unsplash.com/photo-1564013799919-ab600027ffc6?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80" alt="Loja Comercial">
                    <div class="info">
                        <h3>200m² - Frente Comercial</h3>
                        <p>Centro</p>
                        <div class="price">R$ 650.000</div>
                        <a href="https://wa.me/554994229422?text=Ol%C3%A1%2C%20tenho%20interesse%20na%20Loja%20Comercial%20-%20200m%C2%B2%20-%20Frente%20Comercial%20-%20R%24%20650.000%20-%20Centro" class="btn-interesse" target="_blank">Tenho Interesse</a>
                    </div>
                </div>
                <div class="imovel-card">
                    <div class="badge">Cobertura Luxuosa</div>
                    <img src="https://images.unsplash.com/photo-1600585152563-6a09e8c92da4?ixlib=rb-4.0.3&auto=format&fit=crop&w=1470&q=80" alt="Cobertura Luxuosa">
                    <div class="info">
                        <h3>300m² - 4 Quartos - Piscina</h3>
                        <p>Alto da Cidade</p>
                        <div class="price">R$ 1.200.000</div>
                        <a href="https://wa.me/554994229422?text=Ol%C3%A1%2C%20tenho%20interesse%20na%20Cobertura%20Luxuosa%20-%20300m%C2%B2%20-%204%20Quartos%20-%20Piscina%20-%20R%24%201.200.000%20-%20Alto%20da%20Cidade" class="btn-interesse" target="_blank">Tenho Interesse</a>
                    </div>
                </div>
                <div class="imovel-card">
                    <div class="badge">Kitnet Compacta</div>
                    <img src="https://images.unsplash.com/photo-1578662996442-48f60103fc96?ixlib=rb-4.0.3&auto=format&fit=crop&w=687&q=80" alt="Kitnet Compacta">
                    <div class="info">
                        <h3>40m² - 1 Quarto</h3>
                        <p>Próximo ao Centro</p>
                        <div class="price">R$ 150.000</div>
                        <a href="https://wa.me/554994229422?text=Ol%C3%A1%2C%20tenho%20interesse%20na%20Kitnet%20Compacta%20-%2040m%C2%B2%20-%201%20Quarto%20-%20R%24%20150.000%20-%20Pr%C3%B3ximo%20ao%20Centro" class="btn-interesse" target="_blank">Tenho Interesse</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="localizacao" class="fade-in">
        <div class="container">
            <h2>Localização</h2>
            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3538.0742000000003!2d-50.327299385094!3d-27.815120982647!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x952736f9f5b5b5b5%3A0x1234567890abcdef!2sCentro%2C%20Lages%20-%20SC%2C%20Brasil!5e0!3m2!1spt-BR!2sbr!4v1720000000000!5m2!1spt-BR!2sbr" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div>
    </section>

    <section id="contato" class="fade-in">
        <div class="container">
            <h2>Contato</h2>
            <div class="contato-container">
                <form id="contactForm">
                    <input type="text" name="nome" placeholder="Seu Nome" required>
                    <input type="email" name="email" placeholder="Seu Email" required>
                    <input type="tel" name="telefone" placeholder="Seu Telefone">
                    <textarea name="mensagem" rows="5" placeholder="Sua Mensagem" required></textarea>
                    <button type="submit">Enviar Mensagem</button>
                </form>
                <div class="contato-info">
                    <p><i class="fab fa-whatsapp"></i> <a href="https://wa.me/554994229422" target="_blank">(54) 99422-9422</a></p>
                    <p><i class="fas fa-envelope"></i> <a href="mailto:fleal8053@gmail.com">fleal8053@gmail.com</a></p>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>© 2024 Hernandez Negócios Imobiliários. Todos os direitos reservados.</p>
            <p><i class="fab fa-whatsapp"></i> <a href="https://wa.me/554994229422" target="_blank">WhatsApp</a> | <i class="fas fa-envelope"></i> <a href="mailto:fleal8053@gmail.com">Email</a></p>
        </div>
    </footer>

    <a href="https://wa.me/554994229422" class="floating-wa" target="_blank">
        <i class="fab fa-whatsapp"></i>
    </a>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Navbar Toggle
            const hamburger = document.querySelector('.hamburger');
            const navMenu = document.querySelector('.nav-menu');

            hamburger.addEventListener('click', function() {
                navMenu.classList.toggle('active');
            });

            // Close menu on link click
            document.querySelectorAll('.nav-menu a').forEach(function(link) {
                link.addEventListener('click', function() {
                    navMenu.classList.remove('active');
                });
            });

            // Fade-in Animation
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };

            const observer = new IntersectionObserver(function(entries) {
                entries.forEach(function(entry) {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                    }
                });
            }, observerOptions);

            document.querySelectorAll('.fade-in').forEach(function(el) {
                observer.observe(el);
            });

            // Contact Form
            const form = document.getElementById('contactForm');
            form.addEventListener('submit', function(e) {
                e.preventDefault();
                const nome = form.nome.value;
                const email = form.email.value;
                const telefone = form.telefone.value;
                const mensagem = form.mensagem.value;
                const text = `Ol%C3%A1!%20Meu%20nome%20%C3%A9%20${encodeURIComponent(nome)},%20email:%20${encodeURIComponent(email)},%20telefone:%20${encodeURIComponent(telefone)}.%20Mensagem:%20${encodeURIComponent(mensagem)}`;
                window.open(`https://wa.me/554994229422?text=${text}`, '_blank');
                form.reset();
            });
        });
    </script>
</body>
</html>
