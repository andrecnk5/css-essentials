# Capítulo 6. Propriedades de texto

## Introdução

Bem-vindo ao Capítulo 6, onde exploraremos as propriedades de texto no CSS. O texto é um componente fundamental de qualquer página web, e o CSS oferece uma ampla gama de propriedades para controlar sua aparência e formatação. Neste capítulo, aprenderemos como manipular fontes, tamanhos, cores, espaçamentos e muito mais para criar textos atraentes e legíveis em nossos projetos web.

## 6.1 Fontes

As propriedades de fonte controlam a aparência geral do texto.

### 6.1.1 font-family

Define a família de fontes para o texto.

```css
p {
    font-family: Arial, Helvetica, sans-serif;
}
```

É uma boa prática fornecer alternativas em caso de a primeira opção não estar disponível.

### 6.1.2 font-size

Controla o tamanho do texto.

```css
h1 {
    font-size: 32px;
}

p {
    font-size: 1em; /* Relativo ao tamanho da fonte do elemento pai */
}
```

### 6.1.3 font-weight

Define a espessura dos caracteres.

```css
strong {
    font-weight: bold;
}

h2 {
    font-weight: 700; /* Valores numéricos de 100 a 900 */
}
```

### 6.1.4 font-style

Especifica o estilo da fonte (normal, itálico, oblíquo).

```css
em {
    font-style: italic;
}
```

### 6.1.5 font (shorthand)

Uma forma abreviada de definir várias propriedades de fonte de uma só vez.

```css
p {
    font: italic bold 16px/1.5 Arial, sans-serif;
}
```

## 6.2 Cor e Fundo

### 6.2.1 color

Define a cor do texto.

```css
p {
    color: #333333;
}

span {
    color: rgb(255, 0, 0);
}
```

### 6.2.2 background-color

Define a cor de fundo do elemento.

```css
.highlight {
    background-color: yellow;
}
```

## 6.3 Alinhamento e Espaçamento

### 6.3.1 text-align

Controla o alinhamento horizontal do texto.

```css
.center {
    text-align: center;
}

.right {
    text-align: right;
}
```

### 6.3.2 line-height

Define a altura da linha, afetando o espaçamento vertical entre linhas de texto.

```css
p {
    line-height: 1.6;
}
```

### 6.3.3 letter-spacing

Ajusta o espaçamento entre caracteres.

```css
h1 {
    letter-spacing: 2px;
}
```

### 6.3.4 word-spacing

Controla o espaçamento entre palavras.

```css
.wide-words {
    word-spacing: 5px;
}
```

## 6.4 Decoração e Transformação

### 6.4.1 text-decoration

Adiciona decorações ao texto, como sublinhado ou riscado.

```css
a {
    text-decoration: none; /* Remove o sublinhado padrão dos links */
}

.strikethrough {
    text-decoration: line-through;
}
```

### 6.4.2 text-transform

Modifica a capitalização do texto.

```css
.uppercase {
    text-transform: uppercase;
}

.capitalize {
    text-transform: capitalize;
}
```

## 6.5 Sombra e Contorno

### 6.5.1 text-shadow

Adiciona sombra ao texto.

```css
h1 {
    text-shadow: 2px 2px 4px #000000;
}
```

### 6.5.2 text-outline (experimental)

Cria um contorno ao redor do texto.

```css
h2 {
    -webkit-text-stroke: 1px black; /* Para navegadores WebKit */
    text-stroke: 1px black; /* Padrão, mas com suporte limitado */
}
```

## 6.6 Quebra e Estouro de Texto

### 6.6.1 white-space

Controla como o espaço em branco dentro do elemento é tratado.

```css
pre {
    white-space: pre-wrap;
}
```

### 6.6.2 word-wrap

Especifica se o navegador pode quebrar linhas dentro de palavras para evitar estouro.

```css
p {
    word-wrap: break-word;
}
```

### 6.6.3 text-overflow

Define como o conteúdo que transborda é sinalizado para o usuário.

```css
.ellipsis {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}
```

## 6.7 Exemplo Prático

Vamos criar um exemplo que demonstra várias propriedades de texto:

HTML:
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Exemplo de Propriedades de Texto</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Bem-vindo ao Nosso Site</h1>
    <p class="intro">Este é um parágrafo introdutório com <span class="highlight">texto destacado</span>.</p>
    <p class="content">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam auctor, nunc id aliquam tincidunt, nisi nunc tincidunt urna, nec aliquam nunc nunc nec nunc.</p>
    <a href="#" class="btn">Leia Mais</a>
</body>
</html>
```

CSS (styles.css):
```css
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #333;
    padding: 20px;
}

h1 {
    font-size: 2.5em;
    color: #2c3e50;
    text-transform: uppercase;
    letter-spacing: 2px;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
}

.intro {
    font-size: 1.2em;
    font-weight: bold;
    color: #34495e;
}

.highlight {
    background-color: #f1c40f;
    padding: 2px 5px;
    border-radius: 3px;
}

.content {
    text-align: justify;
    word-spacing: 2px;
    max-width: 600px;
}

.btn {
    display: inline-block;
    background-color: #3498db;
    color: white;
    text-decoration: none;
    padding: 10px 20px;
    border-radius: 5px;
    text-transform: uppercase;
    font-weight: bold;
    transition: background-color 0.3s;
}

.btn:hover {
    background-color: #2980b9;
}
```

Este exemplo demonstra o uso de várias propriedades de texto para criar uma página web visualmente atraente e legível.

## Conclusão

As propriedades de texto no CSS oferecem um controle poderoso sobre a aparência e o formato do conteúdo textual em nossas páginas web. Dominar essas propriedades permite criar designs tipográficos sofisticados e melhorar significativamente a legibilidade e a estética geral de seus sites.

Pontos-chave para lembrar:
1. Use `font-family` para garantir que suas fontes sejam consistentes em diferentes dispositivos.
2. Combine `font-size`, `line-height`, e `letter-spacing` para melhorar a legibilidade.
3. Utilize `text-transform` e `text-decoration` para criar ênfase e hierarquia visual.
4. Experimente com `text-shadow` para efeitos sutis que podem melhorar o design.

No próximo capítulo, exploraremos as propriedades de layout no CSS, aprendendo como posicionar e organizar elementos em nossas páginas web de maneira eficaz.