# Capítulo 2. Sintaxe básica

## Introdução

Bem-vindo ao Capítulo 2, onde desvendamos os segredos da sintaxe básica do CSS. Assim como qualquer linguagem, o CSS possui uma estrutura e regras específicas que precisamos seguir para comunicar efetivamente nossas intenções de estilo. Neste capítulo, exploraremos os componentes fundamentais da sintaxe CSS e aprenderemos como construir regras de estilo eficazes.

## 2.1 Estrutura de uma regra CSS

Uma regra CSS é composta por três partes principais:

1. Seletor
2. Propriedade
3. Valor

Vejamos um exemplo simples:

```css
p {
    color: blue;
}
```

Neste exemplo:
- `p` é o seletor
- `color` é a propriedade
- `blue` é o valor

## 2.2 Seletores

Os seletores são usados para "selecionar" os elementos HTML que queremos estilizar. Existem vários tipos de seletores:

### 2.2.1 Seletor de elemento
Seleciona todos os elementos de um tipo específico.

```css
p {
    font-size: 16px;
}
```

### 2.2.2 Seletor de classe
Seleciona elementos com uma classe específica.

```css
.destaque {
    background-color: yellow;
}
```

### 2.2.3 Seletor de ID
Seleciona um elemento com um ID específico.

```css
#cabecalho {
    background-color: black;
    color: white;
}
```

### 2.2.4 Seletor universal
Seleciona todos os elementos.

```css
* {
    margin: 0;
    padding: 0;
}
```

### 2.2.5 Seletores combinados
Podemos combinar seletores para maior especificidade.

```css
div.container p {
    line-height: 1.5;
}
```

## 2.3 Propriedades e valores

As propriedades definem qual aspecto do elemento você quer estilizar, e os valores especificam como você quer estilizá-lo.

```css
h1 {
    font-size: 24px;
    color: #333;
    text-align: center;
    text-decoration: underline;
}
```

Neste exemplo, temos quatro pares de propriedade-valor:
- `font-size: 24px;`
- `color: #333;`
- `text-align: center;`
- `text-decoration: underline;`

## 2.4 Comentários em CSS

Comentários são úteis para documentar seu código. Em CSS, os comentários são escritos assim:

```css
/* Isto é um comentário CSS */
p {
    color: red; /* Isso torna o texto vermelho */
}
```

## 2.5 Agrupamento e aninhamento

Para economizar espaço e tornar o código mais legível, podemos agrupar seletores e aninhar regras.

### 2.5.1 Agrupamento de seletores

```css
h1, h2, h3 {
    font-family: Arial, sans-serif;
}
```

### 2.5.2 Aninhamento de seletores

```css
nav {
    background-color: #333;
}

nav ul {
    list-style-type: none;
}

nav ul li {
    display: inline-block;
}

nav ul li a {
    color: white;
    text-decoration: none;
}
```

## 2.6 Cascata e especificidade

O "C" em CSS significa "Cascading" (Cascata). Isso se refere à forma como os estilos são aplicados quando há múltiplas regras conflitantes. A especificidade determina qual regra tem precedência.

```css
p {
    color: blue;
}

.texto-destaque {
    color: red;
}

#paragrafo-principal {
    color: green;
}
```

Neste exemplo, se um parágrafo tiver tanto a classe `texto-destaque` quanto o ID `paragrafo-principal`, a cor será verde, pois o seletor de ID tem maior especificidade.

## 2.7 Exemplo prático

Vamos criar um exemplo mais completo para demonstrar vários aspectos da sintaxe CSS:

HTML:
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Meu Blog</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header id="cabecalho">
        <h1>Meu Blog Incrível</h1>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#sobre">Sobre</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <article class="post">
            <h2>Meu Primeiro Post</h2>
            <p class="destaque">Este é um parágrafo destacado.</p>
            <p>Este é um parágrafo normal.</p>
        </article>
    </main>
    <footer>
        <p>&copy; 2024 Meu Blog. Todos os direitos reservados.</p>
    </footer>
</body>
</html>
```

CSS (styles.css):
```css
/* Estilos gerais */
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
}

/* Estilos do cabeçalho */
#cabecalho {
    background-color: #333;
    color: white;
    padding: 1rem;
}

#cabecalho h1 {
    margin: 0;
}

/* Estilos da navegação */
nav ul {
    list-style-type: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin-right: 10px;
}

nav ul li a {
    color: white;
    text-decoration: none;
}

nav ul li a:hover {
    text-decoration: underline;
}

/* Estilos do conteúdo principal */
main {
    padding: 2rem;
}

.post h2 {
    color: #333;
}

.post p {
    color: #666;
}

.post .destaque {
    background-color: #f4f4f4;
    border-left: 3px solid #333;
    padding: 10px;
}

/* Estilos do rodapé */
footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 1rem;
    position: fixed;
    bottom: 0;
    width: 100%;
}
```

Este exemplo demonstra vários conceitos que discutimos, incluindo diferentes tipos de seletores, agrupamento, aninhamento e especificidade.

## Conclusão

Neste capítulo, exploramos a sintaxe básica do CSS, incluindo seletores, propriedades, valores, e como estruturar nossas regras de estilo. Compreender esses fundamentos é crucial para se tornar proficiente em CSS. À medida que você pratica e experimenta com diferentes combinações, você desenvolverá uma intuição para escrever CSS eficiente e eficaz.

No próximo capítulo, mergulharemos mais fundo no conceito de seletores CSS e aprenderemos técnicas avançadas para selecionar elementos com precisão.