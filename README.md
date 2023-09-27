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
            justify-content: space-between; /* Espaço entre as duas caixas */
            padding: 40px;
        }

        /* Estilos para a caixa da esquerda (feed de postagens) */
        #left-box {
            flex: 1; /* Cresce para preencher o espaço disponível */
            background-color: rgba(255, 255, 255, 0.8); /* Fundo branco com transparência */
            padding: 20px;
            border-radius: 15px;
            overflow-y: auto; /* Adiciona uma barra de rolagem se o conteúdo for longo */
            max-height: 500px; /* Altura máxima do feed */
        }

        /* Estilos para a caixa da direita (formulário de entrada de links) */
        #right-box {
            flex: 1; /* Cresce para preencher o espaço disponível */
            background-color: rgba(255, 255, 255, 0.8); /* Fundo branco com transparência */
            padding: 20px;
            border-radius: 10px;
        }

        #feed {
            /* Estilos para a seção de feed de links e postagens */
            display: flex;
            flex-direction: column; /* Empilha as postagens verticalmente */
            gap: 10px; /* Espaço entre as postagens */
        }

        .postagem {
            border: 1px solid #ddd;
            border-radius: 10px;
            padding: 10px;
            width: 100%;
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

        /* Estilos para a seção de curtidas e comentários */
        .curtidas-comentarios {
            flex: 1; /* Cresce para preencher o espaço disponível */
            background-color: rgba(255, 255, 255, 0.8); /* Fundo branco com transparência */
            padding: 20px;
            border-radius: 15px;
            margin-left: 20px; /* Espaço à esquerda para separar do feed de postagens */
        }
    </style>
</head>
<body>
    <header>
        <h1>Divulgador De Rede Social</h1>
        <button id="loginButton">Entrar</button>
    </header>
    
    <main>
        <section id="left-box">
            <h2>Feed de Postagens</h2>
            <div id="feed">
                <!-- Aqui serão exibidas as postagens do feed -->
            </div>
        </section>

        <section id="right-box">
            <h2>Compartilhe sua Foto ou Link</h2>
            <form id="postForm">
                <label for="linkPostagem">Link da sua Foto ou Postagem:</label>
                <input type="text" id="linkPostagem" required>
                <button type="submit">Compartilhar</button>
            </form>
        </section>

        <section class="curtidas-comentarios">
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
        let userProfile = null;
        let feed = [];

        // Event listener para o botão "Entrar"
        const loginButton = document.getElementById('loginButton');
        loginButton.addEventListener('click', () => {
            const loginSection = document.getElementById('login');
            loginSection.style.display = 'block';
        });

        // Event listener para o formulário de entrada
        const loginForm = document.getElementById('loginForm');
        loginForm.addEventListener('submit', (e) => {
            e.preventDefault();

            // Obtenha os valores do formulário
            const nome = document.getElementById('nome').value;
            const instagram = document.getElementById('instagram').value;

            // Exibe informações do perfil do usuário após o login
            const profileSection = document.getElementById('user-profile');
            const profileName = document.getElementById('profile-name');
            const profileInstagram = document.getElementById('profile-instagram');
            const userPoints = document.getElementById('user-points');

            profileName.textContent = nome;
            profileInstagram.textContent = instagram;
            profileInstagram.href = instagram;
            userPoints.textContent = 0; // Define a contagem de pontos inicial

            // Oculta a seção de login e mostra a seção do perfil do usuário
            const loginSection = document.getElementById('login');
            loginSection.style.display = 'none';
            profileSection.style.display = 'block';

            // Salva o perfil do usuário para referência posterior
            userProfile = {
                nome,
                instagram,
                pontos: 0
            };
        });

        // Exemplo de função para adicionar pontos ao perfil do usuário
        function adicionarPontos(pontos) {
            if (userProfile) {
                userProfile.pontos += pontos;
                const userPoints = document.getElementById('user-points');
                userPoints.textContent = userProfile.pontos;
            }
        }

        // Função para adicionar uma nova postagem ao feed
        function adicionarPostagem(linkInstagram) {
            const novaPostagem = {
                link: linkInstagram,
                curtidas: 0,
                comentarios: [],
            };

            feed.push(novaPostagem);

            atualizarFeed();
        }

        // Função para atualizar o feed com as postagens
        function atualizarFeed() {
            const feedSection = document.getElementById('feed');
            feedSection.innerHTML = '';

            feed.forEach((postagem, index) => {
                const postagemDiv = document.createElement('div');
                postagemDiv.classList.add('postagem');

                const imagem = document.createElement('img');
                imagem.src = postagem.link;
                postagemDiv.appendChild(imagem);

                const curtirButton = document.createElement('button');
                curtirButton.textContent = 'Curtir';
                curtirButton.addEventListener('click', () => curtirPostagem(index));
                postagemDiv.appendChild(curtirButton);

                const comentarioButton = document.createElement('button');
                comentarioButton.textContent = 'Comentar';
                comentarioButton.addEventListener('click', () => comentarPostagem(index));
                postagemDiv.appendChild(comentarioButton);

                const curtidasSpan = document.createElement('span');
                curtidasSpan.textContent = `Curtidas: ${postagem.curtidas}`;
                postagemDiv.appendChild(curtidasSpan);

                const comentariosUl = document.createElement('ul');
                postagem.comentarios.forEach((comentario) => {
                    const comentarioLi = document.createElement('li');
                    comentarioLi.textContent = comentario;
                    comentariosUl.appendChild(comentarioLi);
                });
                postagemDiv.appendChild(comentariosUl);

                feedSection.appendChild(postagemDiv);
            });
        }

        // Função para curtir uma postagem
        function curtirPostagem(index) {
            if (userProfile) {
                feed[index].curtidas++;
                atualizarFeed();

                // Adicione pontos ao perfil do usuário que curtiu
                adicionarPontos(1);
            }
        }

        // Função para comentar em uma postagem
        function comentarPostagem(index) {
            if (userProfile) {
                const comentario = prompt('Digite seu comentário:');
                if (comentario) {
                    feed[index].comentarios.push(`${userProfile.nome}: ${comentario}`);
                    atualizarFeed();
                }
            }
        }

        // Event listener para o formulário de compartilhamento de postagens
        const postForm = document.getElementById('postForm');
        postForm.addEventListener('submit', (e) => {
            e.preventDefault();
            const linkPostagem = document.getElementById('linkPostagem').value;
            adicionarPostagem(linkPostagem);
            document.getElementById('linkPostagem').value = ''; // Limpar o campo após o compartilhamento
        });
    </script>
</body>
</html>
