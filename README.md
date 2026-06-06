# ENEM Banco de Questões

Um aplicativo desktop para consulta, gerenciamento e edição de questões do ENEM e de outros vestibulares. Desenvolvido com Tauri (Rust) e Vanilla JS/HTML/CSS.

## Funcionalidades

O aplicativo é dividido em três áreas principais:
1. **Filtros (Esquerda):** Permite buscar questões específicas filtrando por Banco, Área, Ano, Período, Tema, Subtema e Sub-subtema.
2. **Visualizador de Questões (Centro):** Exibe as questões encontradas. Permite ajustar o tamanho das imagens, selecionar questões para exportação, ver/ocultar gabaritos e excluir questões.
3. **Navegação (Direita):** Uma lista rápida para você navegar entre as questões filtradas.

### Como adicionar uma nova questão
Clique no botão **"+ Nova Questão"** no menu de filtros. Um editor será aberto onde você poderá:
- Selecionar o Banco, Área, Ano e Período.
- Classificar por Tema, Subtema e Sub-subtema.
- Escrever o enunciado com suporte a equações matemáticas (via KaTeX) e imagens (usando a tag `@img{ID_DA_IMAGEM}`).
- Adicionar as alternativas e marcar a correta com `[x]`.
- Utilizar a **Inteligência Artificial (DeepSeek)** para classificar ou sugerir alternativas automaticamente.

### Importação e Exportação
Você pode gerenciar sua base de dados clicando em **"Importar / Exportar"**:
- **Exportar Backup:** Cria um arquivo `.zip` com todas as suas questões e imagens.
- **Importar Backup:** Restaura um banco de dados a partir de um `.zip`. Útil para migrar entre computadores ou compartilhar bancos de questões. **Nota: Existe um arquivo `.zip` com banco de questões já disponível neste repositório que pode ser importado para começar a usar o aplicativo imediatamente!**
- **Exportar Selecionadas:** Você pode selecionar questões específicas no visualizador e exportá-las em formato `.tex` (LaTeX), `.docx` (Word), ou copiá-las como texto/LaTeX para a área de transferência.

## 🗂️ Categorias e Organização

O aplicativo precisa de "Áreas" para organizar as questões (ex: Física, Matemática, História). A base de dados é mantida em pastas locais no seu computador.

Ao clicar em **"Abrir Pasta de Dados"**, você acessará a pasta `areas/`. Lá você pode criar arquivos de texto (ex: `Fisica.txt` ou `Fisica.md`) e estruturar suas categorias usando a seguinte regra de formatação (Markdown):
- `# Tema Geral` (com 1 hashtag)
- `## Subtema` (com 2 hashtags)
- `- Sub-subtema` (em forma de lista com traço)

O sistema fará a leitura automática dessa estrutura para popular os filtros de busca e as opções no cadastro de novas questões.

## 📦 Dependências e Tecnologias

O projeto utiliza as seguintes tecnologias:
- **[Tauri](https://tauri.app/):** Framework para criar aplicações desktop leves e seguras usando tecnologias web (Rust no backend).
- **Frontend Vanilla:** HTML, CSS e JavaScript puros (sem frameworks pesados).
- **[KaTeX](https://katex.org/):** Para renderização rápida de equações matemáticas no formato LaTeX.
- **[docx](https://docx.js.org/):** Para exportação de questões em formato Word (`.docx`).

**Dependências principais (`package.json`):**
- `@tauri-apps/cli`: ^2
- `@tauri-apps/plugin-clipboard-manager`: ^2.3.2
- `@tauri-apps/plugin-dialog`: ^2.7.0
- `@tauri-apps/plugin-fs`: ^2.5.0
- `docx`: ^9.0.0
- `katex`: ^0.16.45

## 🛠️ Como Instalar

Atualmente, o repositório disponibiliza diretamente o instalador do aplicativo para facilitar o uso!

1. Baixe o arquivo de instalação (ex: `.msi` ou `.exe` para Windows).
2. Execute o instalador e siga os passos na tela.
3. Após instalar e abrir o aplicativo, clique em **"Importar / Exportar"** e importe o arquivo `.zip` (banco de questões) disponível aqui no repositório para já começar com várias questões prontas!

## ⚖️ Licença e Uso
Este software foi desenvolvido com fins educacionais e acadêmicos. As questões cadastradas pertencem aos seus respectivos criadores e bancas organizadoras. A distribuição deste software deve permanecer livre e gratuita. O uso deste software não implica a transferência dos direitos autorais das questões armazenadas ou referenciadas.
