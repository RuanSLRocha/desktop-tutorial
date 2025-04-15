<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SaleSync - Inteligência para suas vendas</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-blue: #2563eb;
            --secondary-blue: #3b82f6;
            --primary-purple: #7e22ce;
            --secondary-purple: #a855f7;
            --primary-orange: #ea580c;
            --secondary-orange: #f97316;
            --light-gray: #f3f4f6;
            --dark-gray: #4b5563;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary-blue), var(--primary-purple));
            color: white;
            padding: 1rem;
            position: fixed;
            width: 100%;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
        }
        
        .logo span {
            color: var(--secondary-orange);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav li {
            margin-left: 2rem;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        nav a:hover {
            color: var(--secondary-orange);
        }
        
        .btn {
            background-color: var(--primary-orange);
            color: white;
            padding: 0.6rem 1.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 500;
            display: inline-block;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background-color: var(--secondary-orange);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(242, 97, 0, 0.2);
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #f8fafc, #e0e7ff);
            padding: 180px 0 100px;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: -50px;
            right: -50px;
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--secondary-purple), var(--primary-blue));
            opacity: 0.1;
        }
        
        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 40px;
        }
        
        .hero-text {
            flex: 1;
        }
        
        .hero-image {
            flex: 1;
            position: relative;
        }
        
        .hero-title {
            font-size: 3rem;
            margin-bottom: 1.5rem;
            line-height: 1.2;
            color: var(--dark-gray);
        }
        
        .hero-title span {
            color: var(--primary-purple);
        }
        
        .hero-subtitle {
            font-size: 1.25rem;
            margin-bottom: 2rem;
            color: var(--dark-gray);
        }
        
        .dashboard-img {
            width: 100%;
            max-width: 600px;
            border-radius: 10px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            border: 5px solid white;
        }
        
        /* Features Section */
        .features {
            padding: 100px 0;
            background: white;
        }
        
        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--primary-blue);
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .feature-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            padding: 30px;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1);
        }
        
        .feature-icon {
            width: 80px;
            height: 80px;
            margin-bottom: 20px;
            background: linear-gradient(135deg, var(--secondary-blue), var(--primary-purple));
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 20px;
        }
        
        .feature-icon svg {
            width: 40px;
            height: 40px;
            fill: white;
        }
        
        .feature-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--primary-blue);
        }
        
        .feature-description {
            color: var(--dark-gray);
            flex-grow: 1;
        }
        
        /* How It Works Section */
        .how-it-works {
            padding: 100px 0;
            background: linear-gradient(135deg, #f8fafc, #e0e7ff);
            position: relative;
        }
        
        .steps-container {
            display: flex;
            flex-direction: column;
            gap: 60px;
            position: relative;
            padding: 30px 0;
        }
        
        .step {
            display: flex;
            align-items: center;
            gap: 40px;
        }
        
        .step-reversed {
            flex-direction: row-reverse;
        }
        
        .step-number {
            background: linear-gradient(135deg, var(--primary-blue), var(--primary-purple));
            color: white;
            width: 80px;
            height: 80px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            font-weight: 700;
            border-radius: 50%;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        
        .step-content {
            flex: 1;
        }
        
        .step-title {
            font-size: 1.8rem;
            margin-bottom: 15px;
            color: var(--primary-purple);
        }
        
        .step-description {
            color: var(--dark-gray);
        }
        
        .step-image {
            flex: 1;
        }
        
        .step-image img {
            width: 100%;
            max-width: 500px;
            border-radius: 10px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            border: 5px solid white;
        }
        
        /* Contact Form Section */
        .contact {
            padding: 100px 0;
            background: white;
        }
        
        .form-container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            border-radius: 15px;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.1);
            padding: 50px;
        }
        
        .form-title {
            text-align: center;
            margin-bottom: 40px;
        }
        
        .form-title h2 {
            font-size: 2.2rem;
            color: var(--primary-blue);
            margin-bottom: 15px;
        }
        
        .form-title p {
            color: var(--dark-gray);
        }
        
        .input-group {
            margin-bottom: 25px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--dark-gray);
        }
        
        input, textarea {
            width: 100%;
            padding: 15px;
            border-radius: 8px;
            border: 1px solid #ddd;
            font-family: 'Poppins', sans-serif;
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        
        input:focus, textarea:focus {
            border-color: var(--primary-purple);
            box-shadow: 0 0 0 3px rgba(126, 34, 206, 0.1);
            outline: none;
        }
        
        .btn-submit {
            width: 100%;
            padding: 15px;
            font-size: 1.1rem;
            background: linear-gradient(135deg, var(--primary-blue), var(--primary-purple));
        }
        
        .btn-submit:hover {
            background: linear-gradient(135deg, var(--secondary-blue), var(--secondary-purple));
        }
        
        .success-message {
            background-color: #dcfce7;
            color: #166534;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
            text-align: center;
            display: none;
        }
        
        /* Footer */
        footer {
            background: var(--primary-blue);
            color: white;
            padding: 50px 0 20px;
        }
        
        .footer-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-logo {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 15px;
        }
        
        .footer-logo span {
            color: var(--secondary-orange);
        }
        
        .footer-info {
            max-width: 350px;
        }
        
        .footer-links h3 {
            margin-bottom: 20px;
            font-size: 1.3rem;
        }
        
        .footer-links ul {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 10px;
        }
        
        .footer-links a {
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .footer-links a:hover {
            color: var(--secondary-orange);
        }
        
        .copyright {
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        /* Responsive Design */
        @media (max-width: 992px) {
            .hero-content {
                flex-direction: column;
                text-align: center;
            }
            
            .hero-image {
                margin-top: 40px;
            }
            
            .step {
                flex-direction: column;
                text-align: center;
            }
            
            .step-reversed {
                flex-direction: column;
            }
            
            .step-number {
                margin: 0 auto 20px;
            }
        }
        
        @media (max-width: 768px) {
            nav {
                display: none; /* Simplificado para este exemplo */
            }
            
            .hero-title {
                font-size: 2.5rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
            
            .form-container {
                padding: 30px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">Sales<span>Sync</span></div>
                <nav>
                    <ul>
                        <li><a href="#features">Recursos</a></li>
                        <li><a href="#how-it-works">Como Funciona</a></li>
                        <li><a href="#contact">Contato</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>
    
    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1 class="hero-title">Potencialize suas vendas com <span>SaleSync</span></h1>
                    <p class="hero-subtitle">Sistema inteligente de análise de notas fiscais para identificar padrões de venda e oportunidades de negócio.</p>
                    <a href="#contact" class="btn">Solicitar Demonstração</a>
                </div>
                <div class="hero-image">
                    <img src="https://via.placeholder.com/600x400/3b82f6/FFFFFF?text=Dashboard+SaleSync" alt="Dashboard SaleSync" class="dashboard-img">
                </div>
            </div>
        </div>
    </section>
    
    <!-- Features Section -->
    <section class="features" id="features">
        <div class="container">
            <h2 class="section-title">Recursos Poderosos</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                            <path d="M12 4.5C7 4.5 2.73 7.61 1 12c1.73 4.39 6 7.5 11 7.5s9.27-3.11 11-7.5c-1.73-4.39-6-7.5-11-7.5zM12 17c-2.76 0-5-2.24-5-5s2.24-5 5-5 5 2.24 5 5-2.24 5-5 5zm0-8c-1.66 0-3 1.34-3 3s1.34 3 3 3 3-1.34 3-3-1.34-3-3-3z"/>
                        </svg>
                    </div>
                    <h3 class="feature-title">Análise de Padrões</h3>
                    <p class="feature-description">Identifique padrões de compra dos seus clientes através da análise inteligente de notas fiscais.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                            <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-5h2v5zm4 0h-2v-7h2v7zm4 0h-2V7h2v10z"/>
                        </svg>
                    </div>
                    <h3 class="feature-title">Gráficos Intuitivos</h3>
                    <p class="feature-description">Visualize dados e métricas importantes através de gráficos intuitivos e painéis personalizáveis.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                            <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm-5 14H4v-4h11v4zm0-5H4V9h11v4zm5 5h-4V9h4v9z"/>
                        </svg>
                    </div>
                    <h3 class="feature-title">Notificações Inteligentes</h3>
                    <p class="feature-description">Receba alertas automáticos sobre oportunidades de venda e ações recomendadas.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                            <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm1 15h-2v-6h2v6zm0-8h-2V7h2v2z"/>
                        </svg>
                    </div>
                    <h3 class="feature-title">Previsão de Recompra</h3>
                    <p class="feature-description">Antecipe as necessidades de seus clientes com previsões precisas de recompra.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                            <path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/>
                        </svg>
                    </div>
                    <h3 class="feature-title">Perfil de Cliente</h3>
                    <p class="feature-description">Crie perfis detalhados de clientes com histórico de compras e preferências.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                            <path d="M22 10V6c0-1.1-.9-2-2-2H4c-1.1 0-1.99.9-1.99 2v4c1.1 0 1.99.9 1.99 2s-.89 2-2 2v4c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2v-4c-1.1 0-2-.9-2-2s.9-2 2-2zm-2-1.46c-1.19.69-2 1.99-2 3.46s.81 2.77 2 3.46V18H4v-2.54c1.19-.69 2-1.99 2-3.46 0-1.48-.8-2.77-1.99-3.46L4 6h16v2.54z M11 15h2v2h-2zm0-6h2v2h-2z"/>
                        </svg>
                    </div>
                    <h3 class="feature-title">Multiplatforma</h3>
                    <p class="feature-description">Acesse o sistema via web ou dispositivos móveis, em qualquer lugar e a qualquer momento.</p>
                </div>
            </div>
        </div>
    </section>
    
    <!-- How It Works Section -->
    <section class="how-it-works" id="how-it-works">
        <div class="container">
            <h2 class="section-title">Como Funciona</h2>
            <div class="steps-container">
                <div class="step">
                    <div class="step-number">1</div>
                    <div class="step-content">
                        <h3 class="step-title">Integração de Dados</h3>
                        <p class="step-description">Importamos suas notas fiscais e dados de vendas para o sistema SaleSync. Nossa equipe cuida de toda a configuração inicial do sistema.</p>
                    </div>
                    <div class="step-image">
                        <img src="https://via.placeholder.com/500x300/a855f7/FFFFFF?text=Integração+de+Dados" alt="Integração de Dados">
                    </div>
                </div>
                
                <div class="step step-reversed">
                    <div class="step-number">2</div>
                    <div class="step-content">
                        <h3 class="step-title">Análise Inteligente</h3>
                        <p class="step-description">Nossa IA analisa seus dados, identificando padrões de compra, frequência, sazonalidade e oportunidades de venda cruzada ou recompra.</p>
                    </div>
                    <div class="step-image">
                        <img src="https://via.placeholder.com/500x300/2563eb/FFFFFF?text=Análise+Inteligente" alt="Análise Inteligente">
                    </div>
                </div>
                
                <div class="step">
                    <div class="step-number">3</div>
                    <div class="step-content">
                        <h3 class="step-title">Ações Recomendadas</h3>
                        <p class="step-description">O sistema gera notificações e recomendações de ações para sua equipe de vendas, aumentando as chances de conversão e melhorando o relacionamento com o cliente.</p>
                    </div>
                    <div class="step-image">
                        <img src="https://via.placeholder.com/500x300/f97316/FFFFFF?text=Ações+Recomendadas" alt="Ações Recomendadas">
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Contact Form Section -->
    <section class="contact" id="contact">
        <div class="container">
            <div class="form-container">
                <div class="form-title">
                    <h2>Solicite uma Demonstração</h2>
                    <p>Preencha o formulário abaixo para conhecer o SaleSync em ação e descobrir como podemos ajudar sua empresa a vender mais.</p>
                </div>
                
                <div id="success-message" class="success-message">
                    <p>Obrigado pelo seu interesse! Em breve nossa equipe entrará em contato.</p>
                </div>
                
                <form id="contact-form">
                    <div class="input-group">
                        <label for="name">Nome Completo</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    
                    <div class="input-group">
                        <label for="email">E-mail</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    
                    <div class="input-group">
                        <label for="phone">Telefone</label>
                        <input type="tel" id="phone" name="phone" required>
                    </div>
                    
                    <div class="input-group">
                        <label for="company">Empresa</label>
                        <input type="text" id="company" name="company" required>
                    </div>
                    
                    <button type="submit" class="btn btn-submit">Solicitar Demonstração</button>
                </form>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-info">
                    <div class="footer-logo">Sales<span>Sync</span></div>
                    <p>Transformando dados em oportunidades de vendas através de análise inteligente e acionável.</p>
                </div>
                
                <div class="footer-links">
                    <h3>Links Rápidos</h3>
                    <ul>
                        <li><a href="#features">Recursos</a></li>
                        <li><a href="#how-it-works">Como Funciona</a></li>
                        <li><a href="#contact">Contato</a></li>
                    </ul>
                </div>
                
                <div class="footer-links">
                    <h3>Contato</h3>
                    <ul>
                        <li><a href="mailto:info@salessync.com.br">info@salessync.com.br</a></li>
                        <li><a href="tel:+551140028922">+55 11 4002-8922</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; <span id="current-year">2025</span> SaleSync. Todos os direitos reservados.</p>
            </div>
        </div>
    </footer>

    <script>
        // Atualizar o ano atual no footer
        document.getElementById('current-year').textContent = new Date().getFullYear();
        
        // Manipulação do formulário
        document.getElementById('contact-form').addEventListener('submit', function(event) {
            event.preventDefault();
            
            // Aqui você poderia adicionar código para enviar os dados para um serviço externo
            // como Formspree, Netlify Forms, ou outro serviço de formulários
            
            // Exibir mensagem de sucesso
            document.getElementById('success-message').style.display = 'block';
            
            // Limpar o formulário
            this.reset();
            
            // Rolar para a mensagem de sucesso
            document.getElementById('success-message').scrollIntoView({behavior: "smooth"});
        });
    </script>
</body>
</html>