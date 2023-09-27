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
            display: flex; /* Divide a página em duas caixas */
            flex-wrap: wrap; /* Permite que as caixas sejam empilhadas em telas menores */
            justify-content: space-between; /* Espaço entre as duas caixas */
            padding: 20px;
        }

        /* Estilos para a caixa de compartilhamento de link do perfil */
        #profile-link-box {
            flex: 1; /* Cresce para preencher o espaço disponível */
            background-color: rgba(255, 255, 255, 0.0); /* Fundo branco com transparência */
            padding: 10px;
            border-radius: 10px;
            margin-right: 10px; /* Espaço à direita para separar da caixa de feeds */
            margin-bottom: 10px; /* Espaço abaixo da caixa */
        }

        /* Estilos para a caixa de feeds */
        #feed-box {
            background-color: rgba(255, 255, 255, 0.8); /* Fundo branco com transparência */
            padding: 200px;
            border-radius: 10px;
            margin-right: 20px; /* Espaço à direita para separar da caixa de curtidas/comentários */
            margin-bottom: 20px; /* Espaço abaixo da caixa */
        }

        /* Estilos para a caixa de curtidas/comentários */
        #likes-comments-box {
            background-color: rgba(255, 255, 255, 0.8); /* Fundo branco com transparência */
            padding: 200px;
            border-radius: 10px;
            margin-bottom: 20px; /* Espaço abaixo da caixa */
        }

        #profile-link-box p {
            font-size: 14px;
            text-align: center;
        }

        #profile-link-box .copy {
            background-color: #007BFF;
            color: white;
            padding: 5px;
            border-radius: 5px;
            text-align: center;
        }

        #profile-link-box .copy a {
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
        
        /* Estilos para as postagens no feed */
        .postagem {
            border: 1px solid #ddd;
            border-radius: 10px;
            padding: 10px;
            margin-bottom: 20px;
            box-sizing: border-box; /* Garante que a largura inclua preenchimento e bordas */
            background-color: white;
            box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.2); /* Adiciona uma sombra sutil às postagens */
        }

        .postagem img {
            max-width: 100%; /* Garante que as imagens não ultrapassem a largura da postagem */
            height: auto; /* Mantém a proporção da imagem */
        }

        .postagem button {
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 5px;
            padding: 5px 10px;
            cursor: pointer;
            margin-top: 10px;
        }

        .postagem button:hover {
            background-color: #0056b3; /* Cor quando o cursor passa por cima */
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

        <section id="feed-box">
            <h2>Feed de Postagens</h2>
            <div id="feed">
                <!-- Aqui serão exibidas as postagens do feed -->
            </div>
        </section>


        <section id="likes-comments-box">
            <h2>Curtidas e Comentários</h2>
            <div id="curtidasComentarios">
                <!-- Aqui serão exibidas as curtidas e comentários -->
            </div>
        </section>
    </main>

    <footer>
        &copy; 2023 Minha Rede Social
    </footer>

    <script>
        // O restante do seu código JavaScript permanece inalterado
        // ...
    </script>
</body>
</html>
