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
            background-size: cover; /* Para cobrir toda a área do corpo */
            background-repeat: no-repeat; /* Evita repetição da imagem de fundo */
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
            flex-direction: column; /* Alterado para uma coluna */
            align-items: center; /* Centraliza o conteúdo na horizontal */
            padding: 20px;
        }

        /* Estilos para a caixa de compartilhamento de link do perfil */
        #profile-link-box {
            background-color: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
        }

        /* Estilos para a caixa de compartilhamento de fotos/feeds */
        #shared-content-box {
            background-color: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
        }

        #profile-link-box p, #shared-content-box p {
            font-size: 14px;
            text-align: center;
        }

        #profile-link-box .copy, #shared-content-box .copy {
            background-color: #007BFF;
            color: white;
            padding: 5px;
            border-radius: 5px;
            text-align: center;
        }

        #profile-link-box .copy a, #shared-content-box .copy a {
            color: white;
            text-decoration: none;
        }

        /* Estilos para o formulário de compartilhamento de link */
        #postForm {
            margin-top: 10px;
        }

        #postForm label {
            display: block;
            margin-bottom: 5px;
        }

        #postForm input[type="text"] {
            width: 100%;
            padding: 5px;
            margin-bottom: 10px;
        }

        #postForm button {
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
            margin-right: 5px; /* Adiciona margem à direita para separar os botões */
        }

        .action-buttons a {
            text-decoration: none;
        }

        .action-buttons button:hover {
            background-color: #0056b3;
        }

        /* Estilos para a lista de dados (simulando a base de dados) */
        #data-list {
            width: 100%;
            max-width: 400px;
            background-color: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
        }

        #data-list h2 {
            text-align: center;
        }

        #data-list ul {
            list-style: none;
            padding: 0;
        }

        #data-list li {
            margin-bottom: 10px;
        }

        /* Estilos para a carteira de pontos */
        #points-wallet {
            width: 100%;
            max-width: 120px;
            background-color: rgba(168, 168, 168, 0.8);
            padding: 12px;
            border-radius: 8px;
            margin-bottom: 18px;
        }

        #points-wallet h2 {
            text-align: center;
        }

        #points-wallet p {
            text-align: center;
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
        <section id="profile-link-box">
            <h2>Compartilhe seus Feeds Storys e Fotos</h2>
            <p class="copy">Divulgue seu perfil organicamente com potencial de tráfego pago. <a href="#">Saiba mais</a></p>
            <form id="postForm">
                <label for="linkPostagem">Link do seu Perfil:</label>
                <input type="text" id="linkPostagem" required>
                <button type="submit">Compartilhar</button>
            </form>
        </section>

        <section id="shared-content-box">
            <h2>Ganhe Pontos Curtindo e Comentando Feeds Storys e Fotos</h2>
            <div id="sharedContent">
                <!-- Aqui serão exibidos os botões de acesso ao conteúdo compartilhado -->
            </div>
        </section>


        </section>
        


    </main>

    <footer>
        &copy; 2023 Criado Com o proposito de uma Divulgação organica de perfil de Rede Social
    </footer>

    <script>
        // Simulação de base de dados
        const database = [];
        // Simulação de carteira de pontos para o usuário
        let userPoints = 20; // Começa com 20 pontos
        const userPointsDisplay = document.getElementById('user-points');

        // Função para adicionar dados à "base de dados" (simulação)
        function addToDatabase(data) {
            database.push(data);
            updateDatabaseList();
        }

        // Função para atualizar a lista na página
        function updateDatabaseList() {
            // ... (código anterior) ...
        }

        // Função para adicionar conteúdo compartilhado
function addSharedContent(content) {
    const sharedContent = document.getElementById('sharedContent');
    const contentDiv = document.createElement('div');
    contentDiv.className = 'postagem';

    // Botão "Acesso ao Link"
    const openLinkButton = document.createElement('button');
    openLinkButton.textContent = 'Acesso ao Link';
    let isButtonClicked = false; // Variável para controlar se o botão foi clicado

    openLinkButton.addEventListener('click', function () {
        if (!isButtonClicked) { // Verifica se o botão não foi clicado antes
            window.open(content, '_blank'); // Abre o link em uma nova guia
            // Adiciona 1 ponto ao usuário ao clicar no botão
            userPoints += 1;
            updatePointsDisplay();
            isButtonClicked = true; // Define a variável como true para evitar cliques repetidos
            openLinkButton.disabled = true; // Desabilita o botão
        }
    });

    contentDiv.appendChild(openLinkButton);
    contentDiv.style.marginBottom = '10px'; // Adicione uma margem inferior de 10px entre os botões

    sharedContent.appendChild(contentDiv);

    // Diminui os pontos do usuário ao compartilhar
    userPoints -= 2;
    updatePointsDisplay();
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
            if (linkPostagem) {
                addToDatabase(linkPostagem);
                addSharedContent(linkPostagem);
                document.getElementById('linkPostagem').value = ''; // Limpa o campo após o compartilhamento
            }
        });

        // O restante do seu código JavaScript pode ser adicionado aqui

        // Exemplo de uso: adicionar conteúdo compartilhado após algum tempo (1 hora)
        setTimeout(function () {
            const conteudoExemplo = 'https://exemplo.com';
            addSharedContent(conteudoExemplo);
        }, 3600000); // 1 hora em milissegundos

        // Atualiza a lista da "base de dados" e os pontos do usuário na inicialização
        updateDatabaseList();
        updatePointsDisplay();
    </script>
</body>
</html>
