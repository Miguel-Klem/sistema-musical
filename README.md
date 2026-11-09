# 🎵 Sistema de Catálogo Web — Front-End (Sprint 1)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)


> **Projeto prático de Front-End desenvolvido em HTML5 e CSS3 puro.**  
> Aplicação baseada na regra de negócio de grandes plataformas (**Spotify, Netflix, Goodreads**), estruturada no padrão **Criador & Obra (1:N)**.

---

## 📌 1. Visão Geral do Projeto

Este repositório contém o **protótipo navegável de Front-End** desenvolvido durante as aulas práticas de LIMA (Linguagem de Marcação). O objetivo é simular o fluxo de trabalho real de uma *software house*, onde a interface do usuário (UI/UX) é totalmente prototipada antes da integração com o banco de dados e a lógica de servidor.

Nesta **Sprint 1**, focamos na estruturação semântica, acessibilidade, validação nativa de formulários, organização modular de estilos com CSS3 e responsividade para dispositivos móveis.

> ℹ️ **Nota:** Toda a lógica de backend (sessões de login, persistence em banco MySQL e manipulação com PHP) será implementada na **Sprint 2**.

---

## 🎭 2. Temas & Modelagem de Domínio (Criador vs. Obra)

O projeto base foi construído sob o tema **Sistema Musical**, mas sua arquitetura flexível permite que cada equipe adapte a aplicação para a regra de negócio escolhida:

| Tema | Criador (Entidade 1) | Obra (Entidade 2) | Exemplo de Dados |
| :--- | :--- | :--- | :--- |
| 🎵 **Músicas (Padrão)** | Artista / Banda | Música | Djavan — *Oceano* |
| 📚 **Livros** | Autor / Escritor | Livro | Machado de Assis — *Dom Casmurro* |
| 🎬 **Filmes** | Diretor / Estúdio | Filme | Christopher Nolan — *Inception* |
| 🎮 **Jogos** | Desenvolvedora | Jogo | Nintendo — *Zelda: Ocarina of Time* |
| 🍰 **Receitas** | Chef / Cozinheiro | Receita | Erick Jacquin — *Petit Gâteau* |
| 🎙️ **Podcasts** | Podcaster / Canal | Episódio | Podpah — *Episódio #500* |

---

## 🛠️ 3. Tecnologias & Conceitos Aplicados

### 📄 **HTML5 Semântico & Formulários**
- **Semântica:** Uso correto de tags como `<head>`, `<body>`, `<form>`, `<table>`, `<thead>`, `<tbody>`, `<tr>`, `<th>`, `<td>` e `<small>`.
- **Validações Nativas:** Uso de `required`, `type="email"`, `type="password"`, `type="url"`, `type="file"` e `accept="image/*"`.
- **Acessibilidade & UX:** Associação de `<label for="...">` com `<input id="...">`, atributos de autocompletar (`autocomplete="username"` e `autocomplete="current-password"`), `placeholder` informativo e abertura de links externos em novas abas (`target="_blank"`).
- **Upload de Arquivos:** Inclusão de `enctype="multipart/form-data"` no formulário para envio de imagens.

### 🎨 **CSS3 Moderno & Layout**
- **Variáveis CSS (`:root`):** Centralização de cores e propriedades reutilizáveis em um único arquivo `styles.css`.
- **Flexbox (1D Layout):** Centralização do card de login, alinhamento de filtros e distribuição de botões em cabeçalhos (`justify-content: space-between`).
- **CSS Grid (2D Layout):** 
  - Menu principal em grade responsiva (`menu-grid`).
  - Formulários organizados em 2 colunas (`grid-template-columns: 1fr 1fr`).
  - Uso de `grid-column: 1 / -1` para campos expandidos (como a `<textarea>` da letra da música).
- **Design Responsivo:** Adição de Media Queries (`@media (max-width: 768px)`) para conversão automática de grids e tabelas em layouts adaptados para celulares.

---

## 📱 4. Detalhamento das Telas do Sistema

O sistema é composto por **5 telas HTML** integradas a um único arquivo de estilos (`styles.css`):

```
📋 Fluxo de Navegação do Sistema:
 
 login.html ──► index.html ├──► cadastro_artista.html ──► cadastro_musica.html
                           └──► listagem_musicas.html
```

1. **`login.html` (Tela de Autenticação)**
   - Tela de entrada minimalista com cartão centralizado via Flexbox.
   - Campos com dicas visuais e área de credenciais de teste (`admin` / `123`).

2. **`index.html` (Menu Principal)**
   - Painel inicial com mensagem de boas-vindas customizada.
   - Grade com 3 cards navegáveis (Gerenciar Artistas, Cadastrar Músicas e Biblioteca).
   - Barra superior (`topbar`) com botão funcional para encerramento de sessão (`🚪 Sair`).

3. **`listagem_musicas.html` (Biblioteca / Listagem Geral)**
   - Barra de título com ações de navegação rápida.
   - Painel de filtros de busca por texto, criador e gênero musical.
   - Tabela detalhada de exibição com capa, título, artista, gênero, link direto para o YouTube e botões de ação (✏️ Editar / 🗑️ Excluir).

4. **`cadastro_artista.html` (Gestão do Criador)**
   - Formulário de cadastro em 2 colunas com envio de foto de perfil (`accept="image/*"`).
   - Tabela inferior integrada listando os criadores já cadastrados, contendo botão de atalho rápido (🟢 `🎵 Músicas`) para vincular obras diretamente.

5. **`cadastro_musica.html` (Gestão da Obra)**
   - Formulário com campo `<select>` obrigatório vinculando a obra a um criador existente (simulando chave estrangeira).
   - Campo `<input type="url">` para validação automática de links do YouTube.
   - Área de texto expandida (`<textarea>`) ocupando a largura total da grade.
   - Tabela de consulta de músicas cadastradas para o criador selecionado.

---

## 📁 5. Estrutura do Repositório

```text
.
├── login.html             # Tela 1: Formulário de Login / Autenticação
├── index.html             # Tela 2: Menu Principal / Painel de Cards
├── cadastro_artista.html  # Tela 3: Formulário & Tabela de Criadores (Artistas)
├── cadastro_musica.html   # Tela 4: Formulário & Tabela de Obras (Músicas)
├── listagem_musicas.html  # Tela 5: Biblioteca Geral com Filtros e Tabela
├── styles.css             # Estilo Global Único (CSS Variables + Grid + Flexbox)
└── README.md              # Documentação do Projeto
```

---

## 🎨 6. Customização de Temas e Paleta de Cores (`styles.css`)

Uma das maiores vantagens da arquitetura adotada é o **reaproveitamento visual**. Para personalizar o sistema com a identidade visual da sua equipe, basta alterar as variáveis no início do arquivo `styles.css`:

```css
:root {
  /* Cores Principais */
  --primary-color: #2563eb;       /* Azul principal (botões e links) */
  --primary-hover: #1d4ed8;       /* Tom mais escuro para efeito hover */
  
  /* Cores de Fundo e Estrutura */
  --bg-color: #f8fafc;            /* Fundo geral da página */
  --card-bg: #ffffff;             /* Fundo dos cartões e tabelas */
  --text-color: #0f172a;          /* Cor padrão das fontes */
  --border-color: #e2e8f0;        /* Cor das bordas e divisores */
  
  /* Semântica dos Botões de Ação */
  --red: #ef4444;                 /* Ação destrutiva / Excluir */
  --red-hover: #dc2626;
  --green: #10b981;               /* Ação positiva / Adicionar Obras */
  --green-hover: #059669;
}
```

---

## 💡 7. Destaques & Aprendizados Técnicos

- **Reaproveitamento de Classes CSS:** A tabela de listagem de artistas reutiliza 100% das regras visuais da tabela da biblioteca de músicas.
- **Formulários Robustos:** Entendimento prático sobre quando utilizar `method="post"` e a necessidade da propriedade `enctype="multipart/form-data"` ao lidar com upload de arquivos de imagem.
- **Formatação de Ícones com SVG Inline:** Utilização de Data URLs para renderizar o favicon da aba (`🎵`) sem a necessidade de arquivos externos.
- **Navegação Consistente:** Padronização de botões `.btn-back` (escuros para navegação) e `.btn-primary` (azuis para ações principais).

---

## 🚀 8. Como Executar o Projeto

1. Clone ou baixe este repositório para o seu computador:
   ```bash
   git clone https://github.com/seu-usuario/nome-do-repositorio.git
   ```
2. Acesse a pasta do projeto.
3. Abra o arquivo `login.html` em qualquer navegador web atualizado (Google Chrome, Mozilla Firefox, Microsoft Edge, Brave, Safari).
4. Navegue entre todas as telas através dos botões e links da interface.

---

## ✅ 9. Checklist de Avaliação & Entrega

- [x] **Navegabilidade:** Todas as 5 telas integradas e acessíveis por links internos.
- [x] **CSS Único:** Apenas 1 arquivo `styles.css` aplicando regras globais.
- [x] **Variáveis `:root`:** Paleta de cores definida e aplicada corretamente.
- [x] **Formulários:** Validação de campos obrigatórios e tipos corretos (`text`, `password`, `url`, `file`, `select`, `textarea`).
- [x] **Responsividade:** Layout testado em telas desktop e simulação mobile (F12).
- [x] **Empacotamento:** Arquivo `.zip` gerado no padrão recomendado: `tema_nomes-da-equipe.zip`.

---

## 🏁 10. Próximos Passos (Sprint 2)

Na próxima fase do projeto (**Sprint 2**), o front-end ganhará vida com a inclusão de:
- Conexão com banco de dados **MySQL / MariaDB**.
- Processamento de rotas e cadastros via **PHP**.
- Validação real de sessões de usuário (`session_start()`).
- Operações completas de **CRUD** (Create, Read, Update, Delete).

---

<div align="center">
  <sub>Desenvolvido com 💻, ☕ e código limpo. Sprint 1 — Front-End Finalizado!</sub>
</div>