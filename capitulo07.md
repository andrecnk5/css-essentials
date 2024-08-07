# Capítulo 7. Propriedades de layout

## Introdução

Bem-vindos ao Capítulo 7, onde mergulharemos profundamente no fascinante mundo das propriedades de layout do CSS. O layout é o alicerce de qualquer design web eficaz, determinando como os elementos são posicionados e organizados na página. Neste capítulo, exploraremos em detalhes as principais propriedades e técnicas de layout, desde os conceitos básicos até as abordagens mais modernas e poderosas.

Entender e dominar as propriedades de layout é crucial para criar designs web responsivos, atraentes e funcionais. Vamos começar nossa jornada explorando cada aspecto do layout CSS, com exemplos práticos e explicações detalhadas para cada conceito.

## 7.1 Display

A propriedade `display` é fundamental para o layout CSS, pois define como um elemento deve ser renderizado na página.

### 7.1.1 display: block

Elementos block ocupam toda a largura disponível e começam em uma nova linha.

```css
div {
    display: block;
    width: 300px;
    height: 100px;
    background-color: #f0f0f0;
    margin: 10px;
}
```

Neste exemplo:
- O `div` ocupa toda a largura disponível do seu contêiner.
- Definimos uma largura de 300px e altura de 100px para visualização.
- A margem de 10px cria espaço ao redor do elemento.

### 7.1.2 display: inline

Elementos inline fluem com o texto e não quebram a linha.

```css
span {
    display: inline;
    background-color: yellow;
    padding: 5px;
}
```

Aqui:
- O `span` se comporta como texto, ficando na mesma linha que o conteúdo ao redor.
- O padding é aplicado, mas não afeta o fluxo do texto.

### 7.1.3 display: inline-block

Combina características de elementos block e inline.

```css
.inline-block {
    display: inline-block;
    width: 100px;
    height: 100px;
    background-color: #ddd;
    margin: 5px;
}
```

Neste caso:
- Os elementos ficam na mesma linha (como inline).
- Podemos definir width e height (como block).
- As margens verticais são respeitadas.

## 7.2 Position

A propriedade `position` controla como um elemento é posicionado no documento.

### 7.2.1 position: static

Este é o valor padrão. O elemento segue o fluxo normal do documento.

```css
.static {
    position: static;
    /* Outras propriedades não têm efeito */
}
```

### 7.2.2 position: relative

O elemento é posicionado relativamente à sua posição normal.

```css
.relative {
    position: relative;
    top: 20px;
    left: 20px;
    background-color: lightblue;
}
```

Neste exemplo:
- O elemento é movido 20px para baixo e 20px para a direita da sua posição original.
- O espaço original do elemento é preservado no fluxo do documento.

### 7.2.3 position: absolute

O elemento é removido do fluxo normal e posicionado em relação ao ancestral posicionado mais próximo.

```css
.container {
    position: relative;
    height: 200px;
    border: 1px solid black;
}

.absolute {
    position: absolute;
    top: 50px;
    right: 30px;
    background-color: pink;
    padding: 10px;
}
```

Aqui:
- O elemento `.absolute` é posicionado a 50px do topo e 30px da direita do `.container`.
- Ele não afeta o posicionamento de outros elementos.

### 7.2.4 position: fixed

Similar ao `absolute`, mas posicionado em relação à viewport.

```css
.fixed-header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background-color: #333;
    color: white;
    padding: 10px;
}
```

Este exemplo cria um cabeçalho fixo que permanece no topo da página mesmo ao rolar.

### 7.2.5 position: sticky

Um híbrido entre `relative` e `fixed`.

```css
.sticky-nav {
    position: sticky;
    top: 0;
    background-color: #f9f9f9;
    padding: 10px;
    z-index: 100;
}
```

O elemento se comporta como `relative` até atingir um limite especificado, então se torna `fixed`.

## 7.3 Flexbox

Flexbox é um modelo de layout unidimensional que oferece grande flexibilidade.

```css
.container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.item {
    flex: 1;
    padding: 20px;
    margin: 10px;
    background-color: #e0e0e0;
}
```

Neste exemplo:
- O contêiner usa `display: flex` para ativar o Flexbox.
- `justify-content: space-between` distribui os itens uniformemente na horizontal.
- `align-items: center` centraliza os itens verticalmente.
- Cada item usa `flex: 1` para crescer e ocupar espaço igual.

## 7.4 Grid

CSS Grid é um sistema de layout bidimensional poderoso.

```css
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 20px;
    padding: 20px;
}

.grid-item {
    background-color: #f0f0f0;
    padding: 20px;
    text-align: center;
}
```

Aqui:
- `display: grid` ativa o Grid.
- `grid-template-columns: repeat(3, 1fr)` cria 3 colunas de largura igual.
- `grid-gap: 20px` adiciona espaçamento entre os itens do grid.

## 7.5 Float

Embora menos usado em layouts modernos, `float` ainda é útil em certos cenários.

```css
.float-left {
    float: left;
    width: 200px;
    margin-right: 20px;
    background-color: #f0f0f0;
    padding: 10px;
}

.clear {
    clear: both;
}
```

- `float: left` move o elemento para a esquerda, permitindo que o texto flua ao redor.
- `clear: both` em um elemento subsequente garante que ele apareça abaixo dos elementos flutuantes.

## 7.6 Exemplo Prático Combinado

Vamos criar um layout que combina várias técnicas:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Layout Combinado</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header class="fixed-header">Cabeçalho Fixo</header>
    <nav class="sticky-nav">
        <a href="#">Home</a>
        <a href="#">Sobre</a>
        <a href="#">Contato</a>
    </nav>
    <main class="container">
        <aside class="sidebar">
            <div class="float-left">Conteúdo Flutuante</div>
        </aside>
        <section class="content">
            <div class="grid-container">
                <div class="grid-item">Item 1</div>
                <div class="grid-item">Item 2</div>
                <div class="grid-item">Item 3</div>
                <div class="grid-item">Item 4</div>
                <div class="grid-item">Item 5</div>
                <div class="grid-item">Item 6</div>
            </div>
        </section>
    </main>
    <footer>Rodapé</footer>
</body>
</html>
```

CSS (styles.css):
```css
body {
    margin: 0;
    font-family: Arial, sans-serif;
    padding-top: 60px; /* Espaço para o cabeçalho fixo */
}

/* Cabeçalho fixo */
.fixed-header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background-color: #333;
    color: white;
    padding: 10px;
    text-align: center;
    z-index: 1000;
}

/* Navegação sticky */
.sticky-nav {
    position: sticky;
    top: 0;
    background-color: #f9f9f9;
    padding: 10px;
    text-align: center;
    z-index: 100;
}

.sticky-nav a {
    margin: 0 10px;
    text-decoration: none;
    color: #333;
}

/* Container principal usando Flexbox */
.container {
    display: flex;
    margin: 20px;
}

/* Barra lateral */
.sidebar {
    flex: 0 0 200px;
    padding: 20px;
    background-color: #f0f0f0;
}

/* Conteúdo principal */
.content {
    flex: 1;
    padding: 20px;
}

/* Grid dentro do conteúdo principal */
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 20px;
}

.grid-item {
    background-color: #ddd;
    padding: 20px;
    text-align: center;
}

/* Elemento flutuante na barra lateral */
.float-left {
    float: left;
    width: 100%;
    background-color: #ccc;
    padding: 10px;
    margin-bottom: 10px;
}

/* Rodapé */
footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 10px;
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
}

/* Media query para responsividade */
@media (max-width: 768px) {
    .container {
        flex-direction: column;
    }

    .sidebar {
        flex: none;
        width: auto;
    }

    .grid-container {
        grid-template-columns: repeat(2, 1fr);
    }
}
```

Explicação detalhada:

1. **Cabeçalho Fixo**: Usa `position: fixed` para manter o cabeçalho sempre visível no topo da página.

2. **Navegação Sticky**: Implementa uma navegação que se torna fixa quando o usuário rola a página, usando `position: sticky`.

3. **Layout Flexbox**: O container principal usa Flexbox para criar um layout de duas colunas (barra lateral e conteúdo principal).

4. **Grid no Conteúdo Principal**: Dentro da seção de conteúdo, usamos CSS Grid para criar um layout de 3 colunas para os itens.

5. **Elemento Flutuante**: Na barra lateral, demonstramos o uso de `float` para posicionar um elemento.

6. **Rodapé Fixo**: Similar ao cabeçalho, mas fixado na parte inferior da página.

7. **Responsividade**: Incluímos uma media query para ajustar o layout em telas menores, alterando o Flexbox para uma coluna e o Grid para duas colunas.

Este exemplo demonstra como diferentes técnicas de layout podem ser combinadas para criar uma página web complexa e responsiva. Cada técnica (position, flexbox, grid, float) é utilizada onde é mais apropriada, resultando em um layout flexível e robusto.

## Conclusão

Neste capítulo, exploramos as principais propriedades e técnicas de layout em CSS. Desde os conceitos básicos como `display` e `position`, até os sistemas mais avançados como Flexbox e Grid, cada ferramenta tem seu lugar no arsenal de um desenvolvedor web.

Pontos-chave para lembrar:
1. Use `display` para controlar como os elementos são renderizados.
2. `position` é crucial para layouts específicos e elementos fixos/absolutos.
3. Flexbox é excelente para layouts unidimensionais e alinhamento.
4. CSS Grid oferece controle poderoso sobre layouts bidimensionais.
5. Combine diferentes técnicas para criar layouts complexos e responsivos.

Praticar e experimentar com essas propriedades é essencial para dominar o layout CSS. No próximo capítulo, exploraremos técnicas avançadas de CSS, incluindo animações e transições, para adicionar dinamismo às nossas páginas web.