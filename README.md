<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Divulgador de Rede Social</title>
    <style>
        /* Estilos para o aplicativo */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-image: url('https://neilpatel.com/wp-content/uploads/2019/07/ilustracao-representando-smartphone-com-post-do-ap.jpeg');
            background-size: cover;
            background-repeat: no-repeat;
        }

        header {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 10px;
        }

        header h1 {
            margin: 0;
        }

        button {
            background-color: #f33207;
            color: white;
            border: none;
            border-radius: 5px;
            padding: 5px 10px;
            cursor: pointer;
        }

        main {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
        }

        /* Estilos para a caixa de compartilhamento de link do perfil */
        .content-box {
            width: 100%;
            max-width: 400px;
            background-color: rgba(255, 255, 255, 0.9);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        .content-box h2 {
            text-align: center;
            margin-bottom: 10px;
        }

        .content-box p {
            font-size: 16px;
            text-align: center;
            margin-bottom: 20px;
        }

        .copy {
            background-color: #434446;
            color: white;
            padding: 10px;
            border-radius: 5px;
            text-align: center;
            margin-top: 11px;
        }

        .copy a {
            color: white;
            text-decoration: none;
        }

        /* Estilos para o formulário de compartilhamento de link */
        #postForm label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }

        #postForm input[type="text"] {
            width: 100%;
            padding: 5px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        #postForm button[type="submit"] {
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 5px;
            padding: 5px 10px;
            cursor: pointer;
        }

        /* Estilos para os botões de ação */
        .action-buttons {
            display: flex;
            justify-content: space-between;
            margin-top: 10px;
        }

        .action-buttons button {
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 5px;
            padding: 5px 10px;
            cursor: pointer;
        }

        .action-buttons button:first-child {
            margin-right: 5px;
        }

        .action-buttons a {
            text-decoration: none;
        }

        .action-buttons button:hover {
            background-color: #0056b3;
        }

        /* Estilos para a carteira de pontos */
        #points-wallet {
            width: 100%;
            max-width: 120px;
            background-color: rgba(168, 168, 168, 0.9);
            padding: 12px;
            border-radius: 8px;
            margin-bottom: 18px;
            text-align: center;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        #points-wallet h2 {
            font-size: 16px;
            margin: 0;
        }

        #points-wallet p {
            font-size: 18px;
            margin: 0;
        }

        /* Estilos para a seção de compartilhamento de feeds e fotos */
        #shared-content-box {
            background-color: rgba(255, 255, 255, 0.9);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        #shared-content-box h2 {
            text-align: center;
            margin-bottom: 20px;
        }

        /* Estilos para os botões de acesso ao conteúdo compartilhado */
        .postagem {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 10px;
        }

        .postagem button {
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 5px;
            padding: 5px 10px;
            cursor: pointer;
        }

        .postagem button:disabled {
            background-color: #ccc;
            cursor: not-allowed;
        }
    </style>
</head>
<body>
    <header>
        <h1>Divulgador De Rede Social</h1>
        <button id="loginButton">Entrar</button>
    </header>
    
    <main>
        <section id="points-wallet">
            <h2>Carteira de Pontos</h2>
            <p id="user-points">Pontos: 20</p>
        </section>
        <section id="profile-link-box" class="content-box">
            <p class="copy">
               Mas aqui está o melhor: ganhe pontos a cada ação! 😲<br>
                1 ponto por cada curtida 💖<br>
                1 ponto por cada comentário 🗨️<br>
                E o que você pode fazer com esses pontos? 🤔<br>
                <br>
                Quando você acumular 2 pontos, você pode impulsionar sua própria publicação para alcançar mais pessoas e obter ainda mais curtidas, comentários e compartilhamentos! 🚀🔝<br>
                <br>
                O aplicativo perfeito para aqueles que buscam conexões autênticas e crescimento na rede social! 🤝<br>
                <br>
                Comece a acumular pontos enquanto sua presença na rede social decola! 📱💥<br>
                <br>
                #Compartilhar. #Curtir. #Comentar. #Crescer. 📈💫
            </p>
            
            <h2>Compartilhe seus Feeds, Stories e Fotos</h2>
            <p>Divulgue seu perfil organicamente com potencial de tráfego pago.
            <form id="postForm">
                <label for="linkPostagem">Link do seu Perfil:</label>
                <input type="text" id="linkPostagem" required>
                <button type="submit">Compartilhar</button>
            </form>
            <p class="copy">Cada compartilhamento custa 2 pontos.</p>
        </section>

        <section id="shared-content-box">
            <h2>Ganhe Pontos Curtindo e Comentando Feeds, Stories e Fotos</h2>
            <div id="sharedContent">
                <!-- Aqui serão exibidos os botões de acesso ao conteúdo compartilhado -->
            </div>
        </section>
    </main>

    <footer>
        &copy; 2023 Criado com o propósito de uma divulgação orgânica de perfil de Rede Social
    </footer>

    <script>
        // Simulação de carteira de pontos para o usuário
        let userPoints = 20; // Começa com 20 pontos
        const userPointsDisplay = document.getElementById('user-points');
        const sharedLinks = new Set(); // Usado para rastrear links compartilhados
    
        // Função para adicionar conteúdo compartilhado
        function addSharedContent(content) {
            if (!sharedLinks.has(content)) {
                sharedLinks.add(content); // Adiciona o link à lista de links compartilhados
                const sharedContent = document.getElementById('sharedContent');
                const contentDiv = document.createElement('div');
                contentDiv.className = 'postagem';
    
                // Botão "Acesso ao Link"
                const openLinkButton = document.createElement('button');
                openLinkButton.textContent = 'Acesso ao Link';
                openLinkButton.addEventListener('click', function () {
                    window.open(content, '_blank'); // Abre o link em uma nova guia
                    // Adiciona 1 ponto ao usuário ao abrir o link
                    userPoints += 1;
                    updatePointsDisplay();
                    openLinkButton.disabled = true; // Desabilita o botão após abrir o link
                });
    
                contentDiv.appendChild(openLinkButton);
                contentDiv.style.marginBottom = '10px'; // Adicione uma margem inferior de 10px entre os botões
    
                sharedContent.appendChild(contentDiv);
            }
        }
    
        // Função para atualizar a exibição de pontos do usuário
        function updatePointsDisplay() {
            userPointsDisplay.textContent = `Pontos: ${userPoints}`;
        }
    
        // Função para processar o formulário de compartilhamento de perfil
        const postForm = document.getElementById('postForm');
        postForm.addEventListener('submit', function (e) {
            e.preventDefault(); // Impede o envio padrão do formulário
    
            const linkPostagem = document.getElementById('linkPostagem').value;
            if (linkPostagem && !sharedLinks.has(linkPostagem)) {
                addSharedContent(linkPostagem);
                userPoints -= 2; // Remove 2 pontos ao compartilhar
                updatePointsDisplay(); // Atualiza a exibição de pontos
                document.getElementById('linkPostagem').value = ''; // Limpa o campo após o compartilhamento
            } else if (sharedLinks.has(linkPostagem)) {
                alert('Este link já foi compartilhado.');
            }
        });
    
        // Atualiza os pontos do usuário na inicialização
        updatePointsDisplay();
    </script>
    
</body>

