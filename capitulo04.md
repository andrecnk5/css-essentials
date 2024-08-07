# Capítulo 4. Seletores

## Introdução

Bem-vindo ao Capítulo 4, onde exploraremos o fascinante mundo dos seletores CSS. Os seletores são a base para aplicar estilos em elementos HTML específicos. Dominar os seletores é crucial para criar designs web precisos e eficientes. Neste capítulo, examinaremos diversos tipos de seletores, desde os mais básicos até os mais avançados, e aprenderemos como usá-los efetivamente em nossos projetos.

## 4.1 O que são Seletores?

Seletores são padrões usados para selecionar e estilizar elementos HTML. Eles são a ponte entre o seu HTML e o CSS, permitindo que você direcione elementos específicos para aplicar estilos.

## 4.2 Tipos de Seletores

Vamos explorar os diferentes tipos de seletores, do mais simples ao mais complexo.

### 4.2.1 Seletor Universal

O seletor universal (`*`) seleciona todos os elementos na página.

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

### 4.2.2 Seletor de Elemento

Seleciona todos os elementos de um tipo específico.

```css
p {
    line-height: 1.6;
}

h1 {
    color: navy;
}
```

### 4.2.3 Seletor de Classe

Seleciona elementos com uma classe específica. É precedido por um ponto (`.`).

```css
.destaque {
    background-color: yellow;
}

.btn {
    padding: 10px 15px;
    border-radius: 5px;
}
```

### 4.2.4 Seletor de ID

Seleciona um elemento com um ID específico. É precedido por uma hashtag (`#`).

```css
#header {
    background-color: #333;
    color: white;
}

#main-content {
    padding: 20px;
}
```

### 4.2.5 Seletor de Atributo

Seleciona elementos baseados em seus atributos ou valores de atributos.

```css
[type="text"] {
    border: 1px solid #ccc;
}

[href^="https"] {
    color: green;
}

[lang|="en"] {
    font-style: italic;
}
```

### 4.2.6 Seletores Combinadores

#### Seletor Descendente (espaço)
Seleciona elementos que são descendentes de outro elemento.

```css
article p {
    font-size: 16px;
}
```

#### Seletor Filho (>)
Seleciona elementos que são filhos diretos de outro elemento.

```css
ul > li {
    list-style-type: square;
}
```

#### Seletor Irmão Adjacente (+)
Seleciona um elemento que é o próximo irmão de outro.

```css
h1 + p {
    font-weight: bold;
}
```

#### Seletor Irmão Geral (~)
Seleciona elementos que são irmãos de outro elemento.

```css
h1 ~ p {
    color: gray;
}
```

### 4.2.7 Pseudo-classes

Selecionam elementos baseados em um estado específico.

```css
a:hover {
    text-decoration: underline;
}

input:focus {
    outline: 2px solid blue;
}

li:nth-child(odd) {
    background-color: #f2f2f2;
}
```

### 4.2.8 Pseudo-elementos

Permitem estilizar partes específicas de um elemento.

```css
p::first-line {
    font-weight: bold;
}

h1::before {
    content: "»";
    color: red;
}
```

## 4.3 Especificidade e Cascata

A especificidade determina qual regra CSS deve ser aplicada quando há conflitos. Entender a especificidade é crucial para escrever CSS eficiente.

Ordem de especificidade (do menor para o maior):
1. Seletores de elemento e pseudo-elementos
2. Classes, atributos e pseudo-classes
3. IDs
4. Estilos inline
5. !important (use com cautela)

Exemplo:

```css
p {
    color: blue;
}

.texto {
    color: red;
}

#paragrafo-principal {
    color: green;
}
```

No HTML:
```html
<p id="paragrafo-principal" class="texto">Este parágrafo será verde.</p>
```

O seletor de ID tem a maior especificidade, então a cor verde será aplicada.

## 4.4 Exemplo Prático

Vamos criar um exemplo mais complexo para demonstrar o uso de vários seletores:

HTML:
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Exemplo de Seletores CSS</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header id="main-header">
        <h1>Meu Blog</h1>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">Sobre</a></li>
                <li><a href="#contact">Contato</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <article class="post">
            <h2>Primeiro Post</h2>
            <p>Este é o conteúdo do primeiro post.</p>
            <a href="#" class="read-more">Leia mais</a>
        </article>
        <article class="post">
            <h2>Segundo Post</h2>
            <p>Este é o conteúdo do segundo post.</p>
            <a href="#" class="read-more">Leia mais</a>
        </article>
    </main>
    <footer>
        <p>&copy; 2024 Meu Blog</p>
    </footer>
</body>
</html>
```

CSS (styles.css):
```css
/* Estilos gerais */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #333;
}

/* Cabeçalho */
#main-header {
    background-color: #333;
    color: white;
    padding: 1rem;
}

#main-header h1 {
    margin-bottom: 0.5rem;
}

/* Navegação */
nav ul {
    list-style-type: none;
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

/* Conteúdo principal */
main {
    padding: 20px;
}

.post {
    background-color: #f4f4f4;
    margin-bottom: 20px;
    padding: 15px;
    border-radius: 5px;
}

.post h2 {
    color: #444;
}

.post p {
    margin: 10px 0;
}

.read-more {
    display: inline-block;
    background-color: #333;
    color: white;
    padding: 5px 10px;
    text-decoration: none;
    border-radius: 3px;
}

.read-more:hover {
    background-color: #555;
}

/* Rodapé */
footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 10px;
    position: fixed;
    bottom: 0;
    width: 100%;
}

/* Pseudo-classes e pseudo-elementos */
.post:nth-child(even) {
    background-color: #e9e9e9;
}

.post h2::before {
    content: "📌 ";
}

/* Seletor de atributo */
[href^="#"] {
    font-weight: bold;
}
```

Este exemplo demonstra o uso de vários tipos de seletores, incluindo seletores de elemento, classe, ID, pseudo-classes, pseudo-elementos e seletores de atributo.

## Conclusão

Neste capítulo, exploramos a vasta gama de seletores CSS disponíveis para os desenvolvedores web. Dominar esses seletores permite criar estilos precisos e eficientes, melhorando tanto a aparência quanto a manutenibilidade do seu código CSS.

Lembre-se, a prática é fundamental para se tornar proficiente no uso de seletores. Experimente diferentes combinações e observe como elas afetam seus elementos HTML. No próximo capítulo, mergulharemos no conceito de Box Model, que é crucial para entender como o layout e o espaçamento funcionam no CSS.