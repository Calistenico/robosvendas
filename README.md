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

    </style>
</head>
<body>
    <header>
        <h1>Divulgador De Rede Social</h1>
        <button id="loginButton">Entrar</button>
    </header>
    
    <main>

        <section id="profile-link-box">
            <h2>Compartilhe seu Perfil</h2>
            <p class="copy">Divulgue seu perfil organicamente com potencial de tráfego pago. <a href="#">Saiba mais</a></p>
            <form id="postForm">
                <label for="linkPostagem">Link do seu Perfil:</label>
                <input type="text" id="linkPostagem" required>
                <button type="submit">Compartilhar</button>
            </form>
        </section>

        <section id="shared-content-box">
            <h2>Fotos e Feeds Compartilhados</h2>
            <div id="sharedContent">
                <!-- Aqui serão exibidas as fotos e feeds compartilhados -->
            </div>
        </section>
    </main>

    <footer>
        &copy; 2023 Minha Rede Social
    </footer>

    <script>
        // Função para adicionar conteúdo compartilhado
        function addSharedContent(content) {
            const sharedContent = document.getElementById('sharedContent');
            const contentDiv = document.createElement('div');
            contentDiv.className = 'postagem';
            
            // Botão "Abrir Link"
            const openLinkButton = document.createElement('a');
            openLinkButton.textContent = 'Abrir Link';
            openLinkButton.href = content; // Define o link para o botão
            openLinkButton.target = '_blank'; // Abrir o link em uma nova guia
            contentDiv.appendChild(openLinkButton);
            
            sharedContent.appendChild(contentDiv);
        }

        // Função para compartilhar conteúdo
        document.getElementById('postForm').addEventListener('submit', function (e) {
            e.preventDefault();
            const linkPostagem = document.getElementById('linkPostagem').value;
            
            // Verifique se o campo não está vazio
            if (linkPostagem.trim() !== '') {
                // Crie uma entrada com o conteúdo compartilhado
                addSharedContent(linkPostagem);

                // Limpe o campo após o compartilhamento
                document.getElementById('linkPostagem').value = '';

                // Remova o conteúdo compartilhado após 1 hora
                setTimeout(function () {
                    contentDiv.remove();
                }, 3600000); // 1 hora em milissegundos
            }
        });

        // O restante do seu código JavaScript pode ser adicionado aqui

        // Exemplo de uso: adicionar conteúdo compartilhado após algum tempo (1 hora)
        setTimeout(function () {
            const conteudoExemplo = '<p>Conteúdo compartilhado após 1 hora</p>';
            addSharedContent(conteudoExemplo);
        }, 3600000); // 1 hora em milissegundos
    </script>
</body>
</html>
