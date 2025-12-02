MyMusic — Recomendador Musical

Descrição do Projeto

O MyMusic é uma aplicação web interativa desenvolvida com foco no front-end puro (HTML, CSS e JavaScript), projetada para oferecer recomendações musicais e integrar-se com o serviço Spotify.

O projeto demonstra a implementação de um fluxo de autenticação (simulado em client-side) e a integração com APIs externas, utilizando o fluxo de autorização PKCE do Spotify para acesso seguro aos dados do usuário.

Recursos Principais

Autenticação Simples: Sistema de Cadastro e Login simulado, utilizando localStorage para persistir dados básicos do usuário.

Recomendações Dinâmicas: Realiza buscas por faixas e artistas utilizando as APIs do Spotify (preferencial) e do MusicBrainz (como fallback).

Integração Spotify (PKCE): Implementação completa do fluxo de autorização (Authorization Code with PKCE) para:

Obter Access Tokens e realizar buscas na API do Spotify.

Carregar as Playlists do usuário.

Criar e adicionar faixas a uma Playlist de destino ("MyMusic — Salvas").

Interface Responsiva: Estilização moderna e responsiva utilizando CSS puro (style.css).

Tecnologias Utilizadas

HTML5 & CSS3 (Estilo personalizado com variáveis e cores vibrantes).

JavaScript (ES6+): Lógica de aplicação, manipulação do DOM e chamadas assíncronas de API.

APIs:

Spotify Web API: Utilizada para buscas e gestão de playlists.

MusicBrainz API: Utilizada como API de fallback para dados de artistas.

Autenticação: O fluxo de login e registro é feito no client-side (via localStorage e sessionStorage no js/auth.js).

Instalação e Configuração

Para que a aplicação funcione corretamente, especialmente a integração com o Spotify, é necessário configurar as credenciais e a URI de redirecionamento.

1. Clonar o Repositório

git clone [https://github.com/Jvriosbrito/Trabalho-final-Programa-o-web.git](https://github.com/Jvriosbrito/Trabalho-final-Programa-o-web.git)
cd Trabalho-final-Programa-o-web


2. Configuração do Spotify API

O projeto utiliza o fluxo PKCE, que requer um Client ID do Spotify e uma Redirect URI configurada.

Crie um Aplicativo no Spotify Developers:

Acesse o Spotify Developer Dashboard.

Clique em "Create App" e registre um novo aplicativo.

Salve o seu Client ID.

Configure o Redirecionamento (Redirect URI):

Dentro das configurações do seu aplicativo no Dashboard, adicione a seguinte URL como Redirect URI:

[http://127.0.0.1:5500/](http://127.0.0.1:5500/)


Importante: O projeto está configurado no arquivo js/spotify.js para usar http://127.0.0.1:5500 (porta padrão do Live Server VS Code). Você DEVE utilizar um servidor local que use essa URI.

Atualize o Client ID no Código:

Abra o arquivo js/spotify.js.

Substitua o valor da constante SPOTIFY_CLIENT_ID pelo seu ID gerado:

// js/spotify.js
const SPOTIFY_CLIENT_ID = 'SEU_NOVO_CLIENT_ID_AQUI'; 


3. Execução Local

Você pode rodar o projeto localmente usando uma extensão de servidor, como o Live Server do VS Code:

Abra a pasta do projeto no VS Code.

Clique com o botão direito no index.html e selecione "Open with Live Server".

O navegador deve abrir o projeto na URI configurada (http://127.0.0.1:5500/).

Estrutura do Projeto

.
├── css/
│   └── style.css          # Estilos principais da aplicação.
├── js/
│   ├── api.js             # Funções para buscar dados (Spotify e MusicBrainz).
│   ├── app.js             # Lógica principal da interface (renderização, navegação).
│   ├── auth.js            # Lógica de login/registro (simulado localmente).
│   └── spotify.js         # Lógica do fluxo de autenticação PKCE do Spotify.
└── index.html             # Estrutura principal da aplicação web.



Contribuições

Contribuições são bem-vindas! Se você encontrou um erro ou tem uma sugestão de recurso, sinta-se à vontade para abrir uma Issue ou enviar um Pull Request.

Licença

Este projeto está licenciado sob a Licença MIT.
