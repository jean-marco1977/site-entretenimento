# 🌐 Atividade Prática: Meu Portal de Entretenimento Digital

### Disciplina: Desenvolvimento Web & SGBD
**Estudante:** [Seu Nome Aqui]  
`HTML5` `CSS3` `Flexbox` `IA-Assisted`

---

## 📝 Sobre o Projeto
Este projeto consiste no desenvolvimento de uma página web para o portal **“Meu Portal de Entretenimento Digital”**. A página foi estruturada utilizando HTML5 semântico e estilizada com três abordagens de CSS (Inline, Interno e Externo). O layout foi modularizado em três colunas responsivas utilizando o modelo **Flexbox**, garantindo uma visualização moderna e fluida tanto em desktops quanto em dispositivos móveis.

---

## 🗮️ Lógica e Arquitetura do Layout
A página foi construída dividindo as responsabilidades visuais e estruturais em três arquivos principais:
1. **`reset.css`**: Baseado no modelo clássico de Eric Meyer para zerar inconsistências nativas entre navegadores.
2. **`estilo.css`**: Arquivo externo responsável pelo ecossistema global do layout (fundo, fontes, blocos e o grid Flexbox).
3. **`portal.html`**: Estrutura semântica contendo a marcação do conteúdo, regras de CSS Interno (IDs de personalização) e CSS Inline.

---

## 📂 Arquivos do Sistema

### 1. Folha de Estilo Base (`reset.css`)
```css
/* reset.css - Baseado no modelo de Eric Meyer */
html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
	display: block;
}
body {
	line-height: 1;
}
ol, ul {
	list-style: none;
}
blockquote, q {
	quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
	content: '';
	content: none;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
}
```

### 2. Folha de Estilo Principal (`estilo.css`)
```css
/* estilo.css - Folha de Estilo Principal */

/* Configurações Globais do Corpo da Página */
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #121214;
    color: #e1e1e6;
    padding: 20px;
    line-height: 1.6;
}

/* Estilização do Cabeçalho do Portal usando o ID */
#cabecalho-principal {
    text-align: center;
    margin-bottom: 40px;
    padding: 20px;
    border-bottom: 2px solid #29292e;
}

#cabecalho-principal h1 {
    font-size: 2.5rem;
    color: #04d361;
    font-weight: bold;
}

/* CONTAINER FLEXBOX: Organiza as três colunas lado a lado */
.container-flex {
    display: flex;
    flex-direction: row;      /* Alinha os itens na horizontal */
    justify-content: space-between; /* Distribui o espaço igualmente entre as colunas */
    gap: 20px;                /* Define o espaçamento entre as colunas */
    flex-wrap: wrap;          /* Permite quebra de linha em telas pequenas (responsividade) */
}

/* ESTILO COMPARTILHADO DAS SEÇÕES (CLASSES) */
.secao-card {
    flex: 1;                  /* Faz com que as 3 colunas tenham tamanhos flexíveis iguais */
    min-width: 280px;         /* Impede que a coluna esmague demais em telas menores */
    background-color: #202024;
    padding: 25px;
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
}

/* Padronização dos títulos internos das seções */
.titulo-secao {
    font-size: 1.8rem;
    margin-bottom: 15px;
    border-bottom: 1px solid #41414d;
    padding-bottom: 8px;
}

/* Padronização dos textos descritivos */
.texto-explicativo {
    font-size: 1rem;
    color: #a8a8b3;
    margin-bottom: 15px;
}

/* Padronização das Imagens Ilustrativas */
.imagem-ilustrativa {
    width: 100%;              /* Ajusta a imagem ao tamanho total da coluna */
    height: 160px;            /* Define uma altura fixa para manter a simetria */
    object-fit: cover;        /* Recorta a imagem proporcionalmente sem distorcer */
    border-radius: 6px;
    margin-bottom: 15px;
    display: block;
}
```

### 3. Código Estrutural (`portal.html`)
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Portal de Entretenimento Digital</title>
    
    <!-- Link para o arquivo de CSS Reset (Eric Meyer) -->
    <link rel="stylesheet" href="reset.css">
    
    <!-- Link para a folha de estilo externa principal -->
    <link rel="stylesheet" href="estilo.css">

    <!-- CSS INTERNO: Utilizado para estilizar cores específicas de cada ID de seção -->
    <style>
        #secao-filmes h2 {
            color: #ff3366; /* Rosa/Vermelho para Filmes */
        }
        #secao-musica h2 {
            color: #1db954; /* Verde para Música */
        }
        #secao-games h2 {
            color: #00b0ff; /* Azul para Games */
        }
    </style>
</head>
<body>

    <!-- Cabeçalho Principal usando ID -->
    <header id="cabecalho-principal">
        <h1>Meu Portal de Entretenimento Digital</h1>
    </header>

    <!-- CONTAINER FLEXBOX PRINCIPAL -->
    <main class="container-flex">

        <!-- SEÇÃO 1: Filmes e Séries -->
        <section id="secao-filmes" class="secao-card">
            <h2 class="titulo-secao">Filmes e Séries</h2>
            <p class="texto-explicativo">Explore as últimas novidades das plataformas de streaming, análises de grandes lançamentos do cinema e críticas de séries consagradas.</p>
            
            <!-- Imagem 1 com CSS INLINE aplicando borda diretamente no elemento -->
            <img class="imagem-ilustrativa" src="https://unsplash.com" alt="Cinema" style="border: 2px solid #ff3366;">
            
            <p class="texto-explicativo">As maratonas de fim de semana ganharam cara nova com produções originais e narrativas cada vez mais imersivas de Hollywood e do mundo.</p>
            <img class="imagem-ilustrativa" src="https://unsplash.com" alt="Streaming de Filmes">
        </section>

        <!-- SEÇÃO 2: Música e Podcasts -->
        <section id="secao-musica" class="secao-card">
            <h2 class="titulo-secao">Música e Podcasts</h2>
            <p class="texto-explicativo">Sintonize nos lançamentos de álbuns, playlists customizadas e as melhores produções em áudio que dominam os fones de ouvido globalmente.</p>
            <img class="imagem-ilustrativa" src="https://unsplash.com" alt="Fones de ouvido e Música">
            
            <p class="texto-explicativo">Os podcasts continuam em alta como o formato ideal para absorver conhecimento, notícias e histórias envolventes enquanto você faz suas tarefas.</p>
            <img class="imagem-ilustrativa" src="https://unsplash.com" alt="Estúdio de Podcast">
        </section>

        <!-- SEÇÃO 3: Games e Tecnologia -->
        <section id="secao-games" class="secao-card">
            <h2 class="titulo-secao">Games e Tecnologia</h2>
            <p class="texto-explicativo">Acompanhe as atualizações da nova geração de consoles, análises de jogos indie cativantes e os hardwares mais potentes do mercado.</p>
            <img class="imagem-ilustrativa" src="https://unsplash.com" alt="Console de videogame">
            
            <p class="texto-explicativo">A tecnologia avança transformando o entertainment com Realidade Virtual (VR) e inteligência artificial aplicadas ao design de games inovadores.</p>
            <img class="imagem-ilustrativa" src="https://unsplash.com" alt="Óculos VR">
        </section>

    </main>

</body>
</html>
```

---

## 🚀 Registro das Interações com a IA

### 💬 Etapa 1 – Estrutura
*   **Usuário:** “IA, revise minha estrutura HTML. Estou usando corretamente as tags `<div>`, `<h1>` e `<img>`?”
*   **IA:** "Sua estrutura está excelente e segue perfeitamente as diretrizes do HTML5 Semântico. Você evitou o uso excessivo de `<div>` e adotou tags estruturais modernas (`<header>`, `<main>`, `<section>`). O `<h1>` foi isolado perfeitamente no topo como título principal único do portal e as tags `<img>` trazem o atributo descritivo `alt` preenchido de forma adequada para fins de acessibilidade."

### 💬 Etapa 2 – CSS Interno e Externo
*   **Usuário:** “IA, como posso definir estilos diferentes para cada seção usando classes e IDs?”
*   **IA:** "A técnica ideal consiste em dividir as responsabilidades por especificidade. No arquivo externo (`estilo.css`), utilizamos a classe `.secao-card` para injetar as propriedades repetíveis que estruturam os três blocos igualmente (background, padding, cantos). Em paralelo, no bloco `<style>` interno de `portal.html`, chamamos os IDs específicos (`#secao-filmes`, `#secao-musica`, `#secao-games`) para sobrepor e aplicar cores únicas e estilizadas nos elementos de título `<h2>` de cada card."

### 💬 Etapa 3 – Flexbox
*   **Usuário:** “IA, me ajude a configurar o layout flexível com três colunas ajustáveis.”
