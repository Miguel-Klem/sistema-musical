# 🎵 Sistema de Catálogo Web — Front-End (Sprint 1)

> **Projeto de Front-End desenvolvido em HTML5 e CSS3 puro.**  
> Estrutura modular baseada no conceito **Criador & Obra** (ex.: Artistas e Músicas, Autores e Livros, Diretores e Filmes).

---

## 📌 Sobre o Projeto

Este projeto consiste no desenvolvimento do **Front-End** de uma aplicação web de catalogação. A proposta simula o modelo de software house, onde construímos um protótipo visual navegável e responsivo para atender a uma regra de negócio comum em grandes plataformas (como Spotify, Netflix e Goodreads): gerenciar entidades que se relacionam no formato **1 Criador para N Obras**.

Na **Sprint 1**, focamos exclusivamente na interface visual (HTML5 + CSS3). As regras de backend, manipulação de banco de dados e sessões em PHP serão implementadas na **Sprint 2**.

---

## 🎭 Temas Sugeridos

O projeto base foi construído sob o tema **Sistema Musical**, mas a estrutura pode ser adaptada para qualquer um dos temas abaixo:

| Tema | Criador (Entidade 1) | Obra (Entidade 2) |
| :--- | :--- | :--- |
| 🎵 **Músicas (Padrão)** | Artista / Banda | Música |
| 📚 **Livros** | Autor / Escritor | Livro |
| 🎬 **Filmes** | Diretor / Estúdio | Filme |
| 🎮 **Jogos** | Desenvolvedora / Estúdio | Jogo |
| 🍰 **Receitas** | Chef / Cozinheiro | Receita |
| 🎙️ **Podcasts** | Podcaster / Canal | Episódio |

---

## 🛠️ Tecnologias Utilizadas

- **HTML5**: Semântica, formulários estruturados, validações nativas e suporte a acessibilidade.
- **CSS3**:
  - **Flexbox**: Centralização de componentes, alinhamentos de barras de título e ações.
  - **CSS Grid**: Layouts em grade para menus e formulários em 2 colunas.
  - **Variáveis CSS (`:root`)**: Padronização e fácil customização da paleta de cores.
  - **Design Responsivo**: Media queries (`@media max-width: 768px`) para adaptação a dispositivos móveis.

---

## 📱 Telas do Sistema

O sistema é composto por **5 telas HTML** integradas por um **único arquivo de estilo CSS**:

1. **`login.html` (Tela de Autenticação)**
   - Cartão de login centralizado na tela com Flexbox.
   - Campos de usuário e senha com `autocomplete` e validações nativas.
   - Dica com credenciais de teste para prototipação.

2. **`index.html` (Menu Principal)**
   - Grade com 3 cards navegáveis estruturados em CSS Grid.
   - Acesso rápido para Gerenciar Criadores, Cadastrar Obras e Biblioteca Geral.
   - Barra superior (`topbar`) com botão de logout.

3. **`listagem_musicas.html` (Biblioteca / Listagem Geral)**
   - Barra de título com ações principais (`space-between`).
   - Form de filtro contendo busca textual, `<select>` por criador e gênero.
   - Tabela organizada (`<table>`, `<thead>`, `<tbody>`) listando todas as obras com links externos para visualização (YouTube) e botões de ação (Editar/Excluir).

4. **`cadastro_artista.html` (Cadastro do Criador)**
   - Formulário em 2 colunas (`grid-template-columns: 1fr 1fr`).
   - Suporte a upload de arquivos com `type="file"`, `accept="image/*"` e atributo `enctype="multipart/form-data"`.
   - Tabela de listagem dos criadores cadastrados com botão direto para adicionar obras associadas.

5. **`cadastro_musica.html` (Cadastro da Obra)**
   - Associação com o Criador via `<select>` obrigatório (chave estrangeira na UI).
   - Validação de link externo com `<input type="url">`.
   - Campo expandido de texto (`<textarea>`) ocupando a largura total do formulário (`grid-column: 1 / -1`).
   - Tabela de listagem contendo as obras específicas vinculadas.

---

## 📁 Estrutura do Repositório

```text
.
├── login.html             # Tela de Login
├── index.html             # Menu Principal
├── cadastro_artista.html  # Form & Listagem do Criador
├── cadastro_musica.html   # Form & Listagem da Obra
├── listagem_musicas.html  # Biblioteca / Listagem Geral
└── styles.css             # Estilo Global (CSS Variables + Grid + Flexbox)
```

---

## 🎨 Como Personalizar as Cores do Tema

Para alterar a paleta de cores para o tema escolhido pela sua equipe, basta editar as variáveis no topo do arquivo `styles.css`:

```css
:root {
  --primary-color: #2563eb;       /* Cor principal (botões e destaques) */
  --primary-hover: #1d4ed8;       /* Cor de hover dos botões */
  --bg-color: #f8fafc;            /* Cor de fundo da página */
  --card-bg: #ffffff;             /* Cor de fundo dos cards e tabelas */
  --text-color: #0f172a;          /* Cor padrão do texto */
  --red: #ef4444;                 /* Cor para excluir / avisos */
  --green: #10b981;               /* Cor para ações secundárias / confirmação */
}
```

---

## 🚀 Como Executar o Projeto

1. Faça o clone ou o download deste repositório.
2. Abra a pasta do projeto.
3. Abra o arquivo `login.html` em qualquer navegador web (Google Chrome, Firefox, Edge, Safari).
4. Navegue entre as telas através dos botões e links internos.

---

## ✅ Checklist de Entrega

- [x] 5 telas HTML criadas e vinculadas (`login`, `index`, `cadastro_artista`, `cadastro_musica`, `listagem_musicas`).
- [x] Estilização unificada em um único arquivo `styles.css`.
- [x] Paleta de cores personalizada no `:root`.
- [x] Design responsivo testado em desktop e mobile (F12).
- [x] Validação de campos obrigatórios (`required`, `type="url"`, `accept="image/*"`).
- [x] Estrutura da pasta compactada no padrão `tema_nomes-da-equipe.zip`.