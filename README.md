<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hamburguer do LC - O Melhor Hambúrguer da Cidade</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&family=Merriweather:wght@700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Roboto', sans-serif;
            background: linear-gradient(45deg, #8B0000, #ada310);
            color: #fff;
            line-height: 1.8;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
        }

        header {
            background-color: #d1cbcb;
            padding: 20px;
            text-align: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        header nav a {
            margin: 0 30px;
            text-decoration: none;
            color: #9c1414;
            font-weight: bold;
            font-size: 20px;
            transition: color 0.3s;
        }

        header nav a:hover {
            color: #6d0e0e;
        }

        section {
            padding: 80px 20px;
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }

        h1 {
            color: #000000;
            margin-bottom: 30px;
            font-size: 60px;
            font-family: 'Merriweather', serif;
            font-weight: bold;
        }

        h2 {
            color: #f1c40f;
            margin: 40px 0 20px;
            font-size: 36px;
            font-family: 'Merriweather', serif;
        }

        #home {
            background: linear-gradient(45deg, #ff7b00, #bead14);
            color: #fff;
            padding: 100px 20px;
            text-align: center;
            position: relative;
            z-index: 1;
        }

        #home h1 {
            font-size: 72px;
        }

        #home img {
            width: 80%;
            max-width: 500px;
            margin-top: 20px;
            border-radius: 20px;
            box-shadow: 0 8px 16px rgba(64, 32, 32, 0.4);
            transition: transform 0.3s ease;

/* Para telas menores */
@media (max-width: 768px) {
    #home img {
        width: 90%;
        max-width: 400px;
    }
}

@media (max-width: 480px) {
    #home img {
        width: 95%;
        max-width: 300px;
    }
}
        }

        #home img:hover {
            transform: scale(1.05);
        }

        .button {
            background-color: #800f0f;
            color: #c6c4c4;
            padding: 14px 30px;
            border: none;
            cursor: pointer;
            font-weight: bold;
            border-radius: 10px;
            transition: background-color 0.3s ease;
            font-size: 18px;
            margin-top: 20px;
        }

        .button:hover {
            background-color: #8b1212;
            transform: translateY(-2px);
        }

        .menu {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .menu div {
            background-color: #444;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.4);
            transition: transform 0.3s ease-in-out;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .menu div:hover {
            transform: translateY(-10px);
        }

        .menu img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 10px;
            transition: transform 0.3s ease;
        }

        .menu img:hover {
            transform: scale(1.05);
        }

        .menu h3 {
            color: #dbd7d7;
            margin-top: 10px;
            font-size: 24px;
            font-family: 'Merriweather', serif;
        }

        .menu p {
            color: #ddd;
            margin-top: 5px;
            font-size: 16px;
            font-family: 'Roboto', sans-serif;
            flex-grow: 1;
        }

        .menu .preco {
            font-size: 20px;
            font-weight: bold;
            margin: 10px 0;
            color: #f1c40f;
        }

        .adicionar-carrinho {
            background-color: #f1c40f;
            color: #333;
            border: none;
            padding: 10px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            transition: background-color 0.3s;
            margin-top: 10px;
        }

        .adicionar-carrinho:hover {
            background-color: #d4ac0d;
        }

        #pedido, #cadastro {
            margin-top: 30px;
            background-color: rgba(0, 0, 0, 0.7);
            padding: 40px;
            border-radius: 15px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .form-pedido, .form-cadastro {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .form-pedido input, .form-pedido button, 
        .form-cadastro input, .form-cadastro button {
            padding: 12px;
            font-size: 18px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }

        .form-pedido input, .form-cadastro input {
            background-color: #f9f9f9;
            color: #333;
        }

        .form-pedido button, .form-cadastro button {
            background-color: #800f0f;
            color: #fff;
            cursor: pointer;
            border: none;
            transition: background-color 0.3s;
        }

        .form-pedido button:hover, .form-cadastro button:hover {
            background-color: #a30606;
        }

        footer {
            background-color: #0f0d0d;
            color: #ffffff;
            text-align: center;
            padding: 40px;
            font-family: 'Roboto', sans-serif;
            margin-top: auto;
        }

        footer p {
            font-size: 16px;
        }

        footer .social-links {
            margin-top: 30px;
        }

        footer .social-links a {
            margin: 0 15px;
            text-decoration: none;
            color: #f1c40f;
            font-size: 28px;
            transition: color 0.3s ease;
        }

        footer .social-links a:hover {
            color: #b8b8b8;
        }

        #contato {
            margin-top: 40px;
        }

        .contact-info {
            font-size: 20px;
            margin-top: 20px;
            color: #ddd;
        }

        .contact-info a {
            color: #f1c40f;
            text-decoration: none;
        }

        /* Animations */
        .fadeIn {
            animation: fadeIn 2s ease-out;
        }

        @keyframes fadeIn {
            0% { opacity: 0; }
            100% { opacity: 1; }
        }

        .zoomIn {
            animation: zoomIn 0.5s ease;
        }

        @keyframes zoomIn {
            0% { transform: scale(0); }
            100% { transform: scale(1); }
        }

        /* Order Confirmation */
        .order-confirmation, .cadastro-confirmation {
            background-color: #27ae60;
            color: #000000;
            padding: 20px;
            margin-top: 20px;
            font-size: 20px;
            text-align: center;
            border-radius: 10px;
            display: none;
        }

        /* História */
        #historia {
            background-color: #333;
            color: #f1c40f;
            padding: 60px 20px;
            text-align: center;
        }

        #historia h2 {
            font-size: 50px;
            font-family: 'Merriweather', serif;
            margin-bottom: 30px;
        }

        #historia p {
            font-size: 20px;
            color: #ddd;
            font-family: 'Roboto', sans-serif;
            margin-top: 20px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
            line-height: 1.6;
        }

        .bounce-text span {
            display: inline-block;
            animation: bounce 0.6s ease forwards;
            animation-delay: calc(var(--i) * 0.05s);
            opacity: 0;
            transform: translateY(20px);
        }

        .bounce-text span:nth-child(n) {
            --i: calc(var(--n) + 1);
        }

        /* Define o número de cada span dinamicamente */
        .bounce-text span:nth-child(1)  { --n: 0; }
        .bounce-text span:nth-child(2)  { --n: 1; }
        .bounce-text span:nth-child(3)  { --n: 2; }
        .bounce-text span:nth-child(4)  { --n: 3; }
        .bounce-text span:nth-child(5)  { --n: 4; }
        .bounce-text span:nth-child(6)  { --n: 5; }
        .bounce-text span:nth-child(7)  { --n: 6; }
        .bounce-text span:nth-child(8)  { --n: 7; }
        .bounce-text span:nth-child(9)  { --n: 8; }
        .bounce-text span:nth-child(10) { --n: 9; }
        .bounce-text span:nth-child(11) { --n: 10; }
        .bounce-text span:nth-child(12) { --n: 11; }
        .bounce-text span:nth-child(13) { --n: 12; }
        .bounce-text span:nth-child(14) { --n: 13; }
        .bounce-text span:nth-child(15) { --n: 14; }
        .bounce-text span:nth-child(16) { --n: 15; }
        .bounce-text span:nth-child(17) { --n: 16; }
        .bounce-text span:nth-child(18) { --n: 17; }
        .bounce-text span:nth-child(19) { --n: 18; }
        .bounce-text span:nth-child(20) { --n: 19; }
        .bounce-text span:nth-child(21) { --n: 20; }
        .bounce-text span:nth-child(22) { --n: 21; }
        .bounce-text span:nth-child(23) { --n: 22; }
        .bounce-text span:nth-child(24) { --n: 23; }
        .bounce-text span:nth-child(25) { --n: 24; }
        .bounce-text span:nth-child(26) { --n: 25; }
        .bounce-text span:nth-child(27) { --n: 26; }
        .bounce-text span:nth-child(28) { --n: 27; }
        .bounce-text span:nth-child(29) { --n: 28; }
        .bounce-text span:nth-child(30) { --n: 29; }

        @keyframes bounce {
            0% {
                opacity: 0;
                transform: translateY(20px);
            }
            50% {
                transform: translateY(-10px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Tabs para cadastro/login */
        .tab-container {
            display: flex;
            margin-bottom: 20px;
            border-bottom: 1px solid #ccc;
        }

        .tab {
            padding: 10px 20px;
            cursor: pointer;
            background-color: #444;
            color: #fff;
            border: none;
            border-radius: 5px 5px 0 0;
            margin-right: 5px;
            transition: background-color 0.3s;
        }

        .tab.active {
            background-color: #800f0f;
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        /* Carrinho de compras */
        #carrinho {
            position: fixed;
            top: 100px;
            right: 20px;
            background-color: #333;
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
            z-index: 99;
            max-width: 300px;
            display: none;
        }

        #carrinho h3 {
            color: #f1c40f;
            margin-bottom: 10px;
        }

        #itens-carrinho {
            max-height: 200px;
            overflow-y: auto;
            margin-bottom: 10px;
        }

        .item-carrinho {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
            padding-bottom: 5px;
            border-bottom: 1px solid #555;
        }

        #total-carrinho {
            font-weight: bold;
            color: #f1c40f;
            margin: 10px 0;
        }

        #fechar-carrinho {
            background-color: #800f0f;
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 3px;
            cursor: pointer;
        }
    </style>
</head>
<body>

<header>
    <nav>
        <a href="#home">Home</a>
        <a href="#cardapio">Cardápio</a>
        <a href="#historia">História</a>
        <a href="#cadastro">Cadastro</a>
        <a href="#pedido">Pedido</a>
        <a href="#contato">Contato</a>
        <button id="btn-carrinho" style="background: none; border: none; color: #9c1414; font-size: 20px; cursor: pointer;">🛒 Carrinho</button>
    </nav>
</header>

<!-- Carrinho de compras -->
<div id="carrinho">
    <h3>Seu Pedido</h3>
    <div id="itens-carrinho">
        <!-- Itens do carrinho serão adicionados aqui -->
    </div>
    <div id="total-carrinho">Total: R$ 0,00</div>
    <button id="fechar-carrinho">Fechar</button>
    <button class="button" onclick="window.location.href='#pedido'" style="width: 100%; margin-top: 10px;">Finalizar Pedido</button>
</div>

<section id="home" class="fadeIn">
    <h1 class="bounce-text">
        <span>B</span><span>e</span><span>m</span><span>-</span><span>v</span><span>i</span><span>n</span><span>d</span><span>o</span><span> </span>
        <span>a</span><span>o</span><span> </span>
        <span>H</span><span>A</span><span>M</span><span>B</span><span>U</span><span>R</span><span>G</span><span>U</span><span>E</span><span>R</span><span> </span>
        <span>D</span><span>O</span><span> </span>
        <span>L</span><span>C</span>
    </h1>
    <p>Descubra a verdadeira experiência de um hambúrguer delicioso, feito com ingredientes frescos e de qualidade.</p>
    <img src="https://i.pinimg.com/1200x/ee/a8/ed/eea8ed3ce58d342694b5c7b0425fdbcb.jpg" alt="Hamburguer do LC">
    <button class="button" onclick="window.location.href='#cardapio';">Veja o Cardápio</button>
</section>

<section id="cardapio" class="zoomIn">
    <h1>Nosso Cardápio</h1>

    <h2>Lanches</h2>
    <div class="menu">
        <div>
            <img src="https://i.pinimg.com/1200x/ee/a8/ed/eea8ed3ce58d342694b5c7b0425fdbcb.jpg" alt="X-Gordão">
            <h3>X-Gordão</h3>
            <p>Hambúrguer gigante com queijo cheddar, bacon crocante, alface e molho especial.</p>
            <p class="preco">R$ 35,90</p>
            <button class="adicionar-carrinho" data-nome="X-Gordão" data-preco="35.90">Adicionar ao carrinho</button>
        </div>
        <div>
            <img src="https://i.pinimg.com/736x/9c/bb/0b/9cbb0b364cd135521111a7f26aa8f3bb.jpg" alt="X-Dudu">
            <h3>X-Dudu</h3>
            <p>Hambúrguer com frango grelhado, alface, tomate e molho de mostarda e mel.</p>
            <p class="preco">R$ 15,90</p>
            <button class="adicionar-carrinho" data-nome="X-Dudu" data-preco="15.90">Adicionar ao carrinho</button>
        </div>
        <div>
            <img src="https://i.pinimg.com/736x/eb/1a/3a/eb1a3a183a38099c33651af09b0ef134.jpg" alt="X-JG">
            <h3>X-JG</h3>
            <p>Hambúrguer com queijo prato, cebola caramelizada e maionese artesanal.</p>
            <p class="preco">R$ 25,90</p>
            <button class="adicionar-carrinho" data-nome="X-JG" data-preco="25.90">Adicionar ao carrinho</button>
        </div>
        <div>
            <img src="https://i.pinimg.com/736x/67/c3/00/67c30009e1438d8ea01cab1870236e27.jpg" alt="X-LC Supreme">
            <h3>X-LC Supreme</h3>
            <p>Hambúrguer com cheddar, bacon, cebola caramelizada e molho especial da casa.</p>
            <p class="preco">R$ 22,90</p>
            <button class="adicionar-carrinho" data-nome="X-LC Supreme" data-preco="22.90">Adicionar ao carrinho</button>
        </div>
        <div>
            <img src="https://i.pinimg.com/736x/28/42/21/284221b888cadab131e572ef6a9dcc01.jpg" alt="X-Vegano">
            <h3>X-Vegano</h3>
            <p>Hambúrguer de grão-de-bico com alface, tomate e molho tahine.</p>
            <p class="preco">R$ 27,90</p>
            <button class="adicionar-carrinho" data-nome="X-Vegano" data-preco="27.90">Adicionar ao carrinho</button>
        </div>
        <div>
            <img src="https://i.pinimg.com/736x/c4/9a/71/c49a717fcb00f17f1725663d605ccce5.jpg" alt="X-Bacon Melt">
            <h3>X-Bacon Melt</h3>
            <p>Hambúrguer com queijo derretido, bacon crocante, alface e maionese de alho.</p>
            <p class="preco">R$ 29,90</p>
            <button class="adicionar-carrinho" data-nome="X-Bacon Melt" data-preco="29.90">Adicionar ao carrinho</button>
        </div>
    </div>

    <h2>Aperitivos</h2>
    <div class="menu">
        <div>
            <img src="https://i.pinimg.com/736x/14/3f/12/143f12a232795ef16e191224f2791a56.jpg" alt="Batata Frita">
            <h3>Batata Frita</h3>
            <p>Fritas crocantes, servidas com molho de queijo.</p>
            <p class="preco">R$ 20,00</p>
            <button class="adicionar-carrinho" data-nome="Batata Frita" data-preco="20.00">Adicionar ao carrinho</button>
        </div>
        <div>
            <img src="https://i.pinimg.com/736x/3b/2d/80/3b2d80aa30b81d8b2f1341e5486c8287.jpg" alt="Cebola Grelhada">
            <h3>Cebola Grelhada</h3>
            <p>Cebola grelhada e crocante.</p>
            <p class="preco">R$ 20,00</p>
            <button class="adicionar-carrinho" data-nome="Cebola Grelhada" data-preco="20.00">Adicionar ao carrinho</button>
        </div>
        <div>
            <img src="https://i.pinimg.com/1200x/13/f5/17/13f5174923c5a77ec64ad26adf79611e.jpg" alt="Batata com Cheddar">
            <h3>Batata com Cheddar</h3>
            <p>Batata frita com cheddar derretido e bacon.</p>
            <p class="preco">R$ 18,99</p>
            <button class="adicionar-carrinho" data-nome="Batata com Cheddar" data-preco="18.99">Adicionar ao carrinho</button>
        </div>
        <div>
            <img src="https://i.pinimg.com/1200x/1b/31/db/1b31db5cf560c4dae5ca0e584c9f1fcf.jpg" alt="Nuggets">
            <h3>Nuggets</h3>
            <p>Frango clássico empanado.</p>
            <p class="preco">R$ 15,00</p>
            <button class="adicionar-carrinho" data-nome="Nuggets" data-preco="15.00">Adicionar ao carrinho</button>
        </div>
    </div>

    <h2>Bebidas</h2>
    <div class="menu">
        <div>
            <img src="https://i.pinimg.com/1200x/cf/29/04/cf2904a920ba034d48402aa4c1aabae7.jpg" alt="Coca-Cola">
            <h3>Coca-Cola</h3>
            <p>Refrigerante clássico, perfeito para acompanhar seu lanche.</p>
            <p class="preco">R$ 8,00</p>
            <button class="adicionar-carrinho" data-nome="Coca-Cola" data-preco="8.00">Adicionar ao carrinho</button>
        </div>
        <div>
            <img src="https://i.pinimg.com/736x/bb/79/80/bb7980542d02cfc1ffd7f781fa5bafb2.jpg" alt="Tanqueray">
            <h3>Tanqueray</h3>
            <p>Gin clássico, ideal para quem ama drinks sofisticados.</p>
            <p class="preco">R$ 30,90</p>
            <button class="adicionar-carrinho" data-nome="Tanqueray" data-preco="30.90">Adicionar ao carrinho</button>
        </div>
        <div>
            <img src="https://i.pinimg.com/1200x/f8/35/47/f8354745546ffa71dd7f712e28cefef7.jpg" alt="Beefeater">
            <h3>Beefeater</h3>
            <p>Gin clássico para os apreciadores de drinks especiais.</p>
            <p class="preco">R$ 30,00</p>
            <button class="adicionar-carrinho" data-nome="Beefeater" data-preco="30.00">Adicionar ao carrinho</button>
        </div>
        <div>
            <img src="https://i.pinimg.com/1200x/99/92/4d/99924da79293b1e21e3beb5842999fa2.jpg" alt="Água">
            <h3>Água</h3>
            <p>Refrescante e essencial para a sua refeição.</p>
            <p class="preco">R$ 5,00</p>
            <button class="adicionar-carrinho" data-nome="Água" data-preco="5.00">Adicionar ao carrinho</button>
        </div>
    </div>
</section>

<section id="historia">
    <h2>A História do Hambúrguer do LC</h2>
    <p>
        O Hambúrguer do LC nasceu em 2015 da paixão de Lucas e Carlos por hambúrgueres artesanais. 
        Começamos como um pequeno food truck no centro da cidade, com a missão de oferecer o melhor hambúrguer 
        com ingredientes frescos e de alta qualidade. 
    </p>
    <p>
        Com o tempo, conquistamos a confiança dos nossos clientes e em 2018 inauguramos nossa primeira loja física. 
        Hoje, somos referência em hambúrgueres gourmet na região, sempre mantendo o compromisso com a qualidade 
        e o sabor que nos tornaram famosos.
    </p>
    <p>
        Nossa filosofia é simples: usar apenas ingredientes selecionados, pão artesanal feito diariamente, 
        carnes de primeira qualidade e molhos especiais desenvolvidos com carinho pela nossa equipe.
    </p>
</section>

<section id="cadastro" class="zoomIn">
    <h1>Cadastro</h1>
    <div class="tab-container">
        <button class="tab active" onclick="openTab('cadastro-tab')">Cadastrar</button>
        <button class="tab" onclick="openTab('login-tab')">Login</button>
    </div>
    
    <div id="cadastro-tab" class="tab-content active">
        <div class="form-cadastro">
            <input type="text" id="nome-cadastro" placeholder="Nome completo" required>
            <input type="email" id="email-cadastro" placeholder="E-mail" required>
            <input type="tel" id="telefone-cadastro" placeholder="Telefone" required>
            <input type="password" id="senha-cadastro" placeholder="Senha" required>
            <input type="password" id="confirmar-senha" placeholder="Confirmar senha" required>
            <button onclick="cadastrarUsuario()">Cadastrar</button>
        </div>
    </div>
    
    <div id="login-tab" class="tab-content">
        <div class="form-cadastro">
            <input type="email" id="email-login" placeholder="E-mail" required>
            <input type="password" id="senha-login" placeholder="Senha" required>
            <button onclick="fazerLogin()">Entrar</button>
        </div>
    </div>
    
    <div id="cadastroConfirmation" class="cadastro-confirmation">
        <p id="mensagem-cadastro"></p>
    </div>
</section>

<section id="pedido" class="zoomIn">
    <h1>Finalizar Pedido</h1>
    <div class="form-pedido">
        <input type="text" id="nome-pedido" placeholder="Nome completo" required>
        <input type="text" id="endereco-pedido" placeholder="Endereço" required>
        <input type="text" id="telefone-pedido" placeholder="Número de telefone" required>
        <textarea id="observacoes" placeholder="Observações (opcional)" rows="3"></textarea>
        <button onclick="finalizarPedido()">Finalizar Compra</button>
    </div>
    <div id="orderConfirmation" class="order-confirmation">
        <p>Seu pedido foi confirmado! Em breve, entregaremos na sua porta.</p>
    </div>
</section>

<section id="contato">
    <h2>Entre em Contato</h2>
    <div class="contact-info">
        <p>Telefone: (11) 1234-5678</p>
        <p>Telefone: (12) 1399-9272</p>
        <p>Endereço: Rua Inglaterra, 135</p>
        <p>Endereço 2: Rua Pindorama, 144</p>
        <p><a href="mailto:contato@hamburguerdolc.com">contato@hamburguerdolc.com</a></p>
    </div>
    <div class="social-links">
        <a href="https://www.instagram.com/lc_hamburgueria" target="_blank">Instagram</a>
        <a href="https://www.facebook.com/lc_hamburgueria" target="_blank">Facebook</a>
        <a href="https://www.twitter.com/lc_hamburgueria" target="_blank">Twitter</a>
    </div>
</section>

<footer>
    <p>&copy; 2025 Hamburguer do LC. Todos os direitos reservados.</p>
</footer>

<script>
    // Sistema de cadastro e login
    let usuarios = JSON.parse(localStorage.getItem('usuarios')) || [];
    let usuarioLogado = JSON.parse(localStorage.getItem('usuarioLogado')) || null;
    
    // Carrinho de compras
    let carrinho = JSON.parse(localStorage.getItem('carrinho')) || [];
    
    // Função para abrir abas
    function openTab(tabName) {
        // Esconder todas as abas
        const tabContents = document.getElementsByClassName('tab-content');
        for (let i = 0; i < tabContents.length; i++) {
            tabContents[i].classList.remove('active');
        }
        
        // Remover classe active de todas as abas
        const tabs = document.getElementsByClassName('tab');
        for (let i = 0; i < tabs.length; i++) {
            tabs[i].classList.remove('active');
        }
        
        // Mostrar a aba selecionada
        document.getElementById(tabName).classList.add('active');
        
        // Adicionar classe active à aba clicada
        event.currentTarget.classList.add('active');
    }
    
    // Função para cadastrar usuário
    function cadastrarUsuario() {
        const nome = document.getElementById('nome-cadastro').value;
        const email = document.getElementById('email-cadastro').value;
        const telefone = document.getElementById('telefone-cadastro').value;
        const senha = document.getElementById('senha-cadastro').value;
        const confirmarSenha = document.getElementById('confirmar-senha').value;
        
        // Validações
        if (!nome || !email || !telefone || !senha || !confirmarSenha) {
            mostrarMensagemCadastro('Por favor, preencha todos os campos.', 'error');
            return;
        }
        
        if (senha !== confirmarSenha) {
            mostrarMensagemCadastro('As senhas não coincidem.', 'error');
            return;
        }
        
        if (senha.length < 6) {
            mostrarMensagemCadastro('A senha deve ter pelo menos 6 caracteres.', 'error');
            return;
        }
        
        // Verificar se o email já está cadastrado
        if (usuarios.find(usuario => usuario.email === email)) {
            mostrarMensagemCadastro('Este email já está cadastrado.', 'error');
            return;
        }
        
        // Cadastrar usuário
        const novoUsuario = {
            id: Date.now(),
            nome,
            email,
            telefone,
            senha
        };
        
        usuarios.push(novoUsuario);
        localStorage.setItem('usuarios', JSON.stringify(usuarios));
        
        mostrarMensagemCadastro('Cadastro realizado com sucesso! Faça login para continuar.', 'success');
        
        // Limpar formulário
        document.getElementById('nome-cadastro').value = '';
        document.getElementById('email-cadastro').value = '';
        document.getElementById('telefone-cadastro').value = '';
        document.getElementById('senha-cadastro').value = '';
        document.getElementById('confirmar-senha').value = '';
    }
    
    // Função para fazer login
    function fazerLogin() {
        const email = document.getElementById('email-login').value;
        const senha = document.getElementById('senha-login').value;
        
        // Validações
        if (!email || !senha) {
            mostrarMensagemCadastro('Por favor, preencha todos os campos.', 'error');
            return;
        }
        
        // Verificar credenciais
        const usuario = usuarios.find(u => u.email === email && u.senha === senha);
        
        if (usuario) {
            usuarioLogado = usuario;
            localStorage.setItem('usuarioLogado', JSON.stringify(usuario));
            mostrarMensagemCadastro(`Login realizado com sucesso! Bem-vindo, ${usuario.nome}.`, 'success');
            
            // Redirecionar para a página inicial após 2 segundos
            setTimeout(() => {
                window.location.href = '#home';
            }, 2000);
        } else {
            mostrarMensagemCadastro('Email ou senha incorretos.', 'error');
        }
    }
    
    // Função para mostrar mensagens de cadastro/login
    function mostrarMensagemCadastro(mensagem, tipo) {
        const elemento = document.getElementById('cadastroConfirmation');
        const mensagemElemento = document.getElementById('mensagem-cadastro');
        
        mensagemElemento.textContent = mensagem;
        elemento.style.display = 'block';
        
        if (tipo === 'success') {
            elemento.style.backgroundColor = '#27ae60';
        } else {
            elemento.style.backgroundColor = '#e74c3c';
        }
        
        // Esconder a mensagem após 5 segundos
        setTimeout(() => {
            elemento.style.display = 'none';
        }, 5000);
    }
    
    // Sistema de carrinho de compras
    document.addEventListener('DOMContentLoaded', function() {
        // Adicionar evento aos botões "Adicionar ao carrinho"
        const botoesCarrinho = document.querySelectorAll('.adicionar-carrinho');
        botoesCarrinho.forEach(botao => {
            botao.addEventListener('click', function() {
                const nome = this.getAttribute('data-nome');
                const preco = parseFloat(this.getAttribute('data-preco'));
                
                adicionarAoCarrinho(nome, preco);
            });
        });
        
        // Botão para abrir/fechar o carrinho
        document.getElementById('btn-carrinho').addEventListener('click', function() {
            const carrinhoElemento = document.getElementById('carrinho');
            if (carrinhoElemento.style.display === 'block') {
                carrinhoElemento.style.display = 'none';
            } else {
                carrinhoElemento.style.display = 'block';
                atualizarCarrinho();
            }
        });
        
        // Botão para fechar o carrinho
        document.getElementById('fechar-carrinho').addEventListener('click', function() {
            document.getElementById('carrinho').style.display = 'none';
        });
        
        // Atualizar carrinho ao carregar a página
        atualizarCarrinho();
    });
    
    function adicionarAoCarrinho(nome, preco) {
        // Verificar se o item já está no carrinho
        const itemExistente = carrinho.find(item => item.nome === nome);
        
        if (itemExistente) {
            itemExistente.quantidade += 1;
        } else {
            carrinho.push({
                nome: nome,
                preco: preco,
                quantidade: 1
            });
        }
        
        // Salvar no localStorage
        localStorage.setItem('carrinho', JSON.stringify(carrinho));
        
        // Atualizar exibição do carrinho
        atualizarCarrinho();
        
        // Mostrar mensagem de sucesso
        alert(`${nome} adicionado ao carrinho!`);
    }
    
    function atualizarCarrinho() {
        const itensCarrinho = document.getElementById('itens-carrinho');
        const totalCarrinho = document.getElementById('total-carrinho');
        
        // Limpar carrinho
        itensCarrinho.innerHTML = '';
        
        let total = 0;
        
        // Adicionar itens ao carrinho
        carrinho.forEach((item, index) => {
            const itemElemento = document.createElement('div');
            itemElemento.className = 'item-carrinho';
            itemElemento.innerHTML = `
                <span>${item.nome} x${item.quantidade}</span>
                <span>R$ ${(item.preco * item.quantidade).toFixed(2)}</span>
                <button onclick="removerDoCarrinho(${index})">❌</button>
            `;
            itensCarrinho.appendChild(itemElemento);
            
            total += item.preco * item.quantidade;
        });
        
        // Atualizar total
        totalCarrinho.textContent = `Total: R$ ${total.toFixed(2)}`;
    }
    
    function removerDoCarrinho(index) {
        carrinho.splice(index, 1);
        localStorage.setItem('carrinho', JSON.stringify(carrinho));
        atualizarCarrinho();
    }
    
    // Função para finalizar pedido
    function finalizarPedido() {
        const nome = document.getElementById('nome-pedido').value;
        const endereco = document.getElementById('endereco-pedido').value;
        const telefone = document.getElementById('telefone-pedido').value;
        const observacoes = document.getElementById('observacoes').value;
        
        // Validações
        if (!nome || !endereco || !telefone) {
            alert('Por favor, preencha todos os campos obrigatórios.');
            return;
        }
        
        if (carrinho.length === 0) {
            alert('Seu carrinho está vazio. Adicione itens antes de finalizar o pedido.');
            return;
        }
        
        // Calcular total
        let total = 0;
        carrinho.forEach(item => {
            total += item.preco * item.quantidade;
        });
        
        // Criar resumo do pedido
        let resumo = `Pedido realizado por: ${nome}\n`;
        resumo += `Endereço: ${endereco}\n`;
        resumo += `Telefone: ${telefone}\n`;
        if (observacoes) {
            resumo += `Observações: ${observacoes}\n`;
        }
        resumo += '\nItens do pedido:\n';
        
        carrinho.forEach(item => {
            resumo += `- ${item.nome} x${item.quantidade}: R$ ${(item.preco * item.quantidade).toFixed(2)}\n`;
        });
        
        resumo += `\nTotal: R$ ${total.toFixed(2)}`;
        
        // Mostrar confirmação
        document.getElementById('orderConfirmation').style.display = 'block';
        
        // Limpar carrinho
        carrinho = [];
        localStorage.setItem('carrinho', JSON.stringify(carrinho));
        atualizarCarrinho();
        
        // Limpar formulário
        document.getElementById('nome-pedido').value = '';
        document.getElementById('endereco-pedido').value = '';
        document.getElementById('telefone-pedido').value = '';
        document.getElementById('observacoes').value = '';
        
        // Em um sistema real, aqui você enviaria o pedido para o backend
        console.log('Pedido realizado:', resumo);
    }
</script>

</body>
</html>
