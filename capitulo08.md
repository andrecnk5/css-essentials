# Capítulo 8. Flexbox

## Introdução

Bem-vindos ao Capítulo 8, onde mergulharemos profundamente no mundo do Flexbox (Flexible Box Layout). O Flexbox é uma poderosa ferramenta de layout CSS que revolucionou a forma como criamos designs responsivos e flexíveis. 

Neste capítulo, exploraremos todos os aspectos do Flexbox, desde seus conceitos fundamentais até técnicas avançadas. O Flexbox nos permite criar layouts complexos com muito menos código e maior flexibilidade do que os métodos tradicionais. Seja você um iniciante ou um desenvolvedor experiente, dominar o Flexbox é essencial para criar interfaces modernas e adaptáveis.

Vamos começar nossa jornada entendendo o que é o Flexbox, por que ele é tão útil e como podemos aplicar em nossos projetos web.

## 8.1 O que é Flexbox?

Flexbox é um módulo de layout CSS projetado para facilitar o design de estruturas flexíveis e responsivas. Ele fornece uma maneira mais eficiente de dispor, alinhar e distribuir espaço entre itens em um container, mesmo quando suas dimensões são desconhecidas ou dinâmicas.

### Conceitos Básicos:

1. **Flex Container**: O elemento pai que recebe `display: flex`.
2. **Flex Items**: Os filhos diretos do flex container.
3. **Main Axis**: O eixo principal do container (horizontal por padrão).
4. **Cross Axis**: O eixo perpendicular ao main axis.

## 8.2 Propriedades do Flex Container

Vamos explorar as propriedades que podem ser aplicadas ao flex container.

### 8.2.1 display: flex

Esta é a propriedade que inicia o contexto flexbox.

```css
.container {
    display: flex;
}
```

Este código transforma o elemento `.container` em um flex container, e todos os seus filhos diretos se tornam flex items.

### 8.2.2 flex-direction

Define a direção do main axis.

```css
.container {
    display: flex;
    flex-direction: row; /* Padrão */
    /* Outras opções: row-reverse, column, column-reverse */
}
```

- `row`: Da esquerda para a direita (padrão)
- `row-reverse`: Da direita para a esquerda
- `column`: De cima para baixo
- `column-reverse`: De baixo para cima

### 8.2.3 flex-wrap

Controla se os flex items devem quebrar linha ou não.

```css
.container {
    display: flex;
    flex-wrap: nowrap; /* Padrão */
    /* Outras opções: wrap, wrap-reverse */
}
```

- `nowrap`: Todos os items em uma única linha (padrão)
- `wrap`: Items quebram para a próxima linha quando necessário
- `wrap-reverse`: Items quebram para a linha anterior quando necessário

### 8.2.4 justify-content

Alinha os flex items ao longo do main axis.

```css
.container {
    display: flex;
    justify-content: flex-start; /* Padrão */
    /* Outras opções: flex-end, center, space-between, space-around, space-evenly */
}
```

- `flex-start`: Items alinhados ao início do container
- `flex-end`: Items alinhados ao final do container
- `center`: Items centralizados
- `space-between`: Items distribuídos uniformemente, primeiro e último item nas extremidades
- `space-around`: Items distribuídos com espaço igual ao redor deles
- `space-evenly`: Items distribuídos com espaço igual entre eles

### 8.2.5 align-items

Alinha os flex items ao longo do cross axis.

```css
.container {
    display: flex;
    align-items: stretch; /* Padrão */
    /* Outras opções: flex-start, flex-end, center, baseline */
}
```

- `stretch`: Items esticados para preencher o container (padrão)
- `flex-start`: Items alinhados ao início do cross axis
- `flex-end`: Items alinhados ao final do cross axis
- `center`: Items centralizados no cross axis
- `baseline`: Items alinhados pela linha de base do texto

### 8.2.6 align-content

Alinha as linhas de flex items quando há espaço extra no cross axis (só funciona quando há múltiplas linhas).

```css
.container {
    display: flex;
    flex-wrap: wrap;
    align-content: stretch; /* Padrão */
    /* Outras opções: flex-start, flex-end, center, space-between, space-around */
}
```

## 8.3 Propriedades dos Flex Items

Agora, vamos explorar as propriedades que podem ser aplicadas aos flex items.

### 8.3.1 flex-grow

Define a capacidade de um flex item crescer.

```css
.item {
    flex-grow: 0; /* Padrão */
}
```

Um valor maior que 0 permite que o item cresça para preencher o espaço disponível.

### 8.3.2 flex-shrink

Define a capacidade de um flex item encolher.

```css
.item {
    flex-shrink: 1; /* Padrão */
}
```

Um valor maior que 0 permite que o item encolha se necessário.

### 8.3.3 flex-basis

Define o tamanho base de um flex item antes da distribuição do espaço restante.

```css
.item {
    flex-basis: auto; /* Padrão */
}
```

Pode ser um comprimento (e.g., 20%, 5rem) ou auto.

### 8.3.4 flex (shorthand)

Combina flex-grow, flex-shrink e flex-basis.

```css
.item {
    flex: 0 1 auto; /* Padrão */
    /* Outras opções comuns: flex: 1 (flex-grow: 1, flex-shrink: 1, flex-basis: 0%) */
}
```

### 8.3.5 align-self

Permite sobrescrever o alinhamento definido por align-items para um item específico.

```css
.item {
    align-self: auto; /* Padrão */
    /* Outras opções: flex-start, flex-end, center, baseline, stretch */
}
```

## 8.4 Exemplo Prático Detalhado

Vamos criar um layout flexbox mais complexo para demonstrar várias propriedades em ação.

HTML:
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exemplo Avançado de Flexbox</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="flex-container">
        <header class="flex-header">Cabeçalho</header>
        <main class="flex-main">
            <nav class="flex-nav">
                <ul>
                    <li><a href="#">Link 1</a></li>
                    <li><a href="#">Link 2</a></li>
                    <li><a href="#">Link 3</a></li>
                </ul>
            </nav>
            <article class="flex-content">
                <h1>Conteúdo Principal</h1>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam eget felis eget nunc lobortis mattis aliquam faucibus purus in.</p>
            </article>
            <aside class="flex-sidebar">Barra Lateral</aside>
        </main>
        <footer class="flex-footer">Rodapé</footer>
    </div>
</body>
</html>
```

CSS (styles.css):
```css
body {
    margin: 0;
    font-family: Arial, sans-serif;
}

.flex-container {
    display: flex;
    flex-direction: column;
    min-height: 100vh; /* Altura mínima de 100% da viewport */
}

.flex-header, .flex-footer {
    background-color: #333;
    color: white;
    padding: 1rem;
    text-align: center;
}

.flex-main {
    display: flex;
    flex: 1; /* Cresce para ocupar o espaço disponível */
}

.flex-nav {
    background-color: #f0f0f0;
    padding: 1rem;
    width: 200px; /* Largura fixa */
}

.flex-nav ul {
    list-style-type: none;
    padding: 0;
}

.flex-nav li {
    margin-bottom: 0.5rem;
}

.flex-content {
    flex: 1; /* Cresce para ocupar o espaço disponível */
    padding: 1rem;
}

.flex-sidebar {
    background-color: #ddd;
    padding: 1rem;
    width: 150px; /* Largura fixa */
}

/* Responsividade */
@media (max-width: 768px) {
    .flex-main {
        flex-direction: column;
    }

    .flex-nav, .flex-sidebar {
        width: auto;
    }
}
```

Explicação detalhada:

1. **Flex Container Principal**:
   - `.flex-container` usa `display: flex` e `flex-direction: column` para criar um layout vertical.
   - `min-height: 100vh` garante que o container ocupe pelo menos toda a altura da viewport.

2. **Cabeçalho e Rodapé**:
   - Usam padding e cores de fundo para estilização básica.

3. **Conteúdo Principal**:
   - `.flex-main` é outro flex container, desta vez com direção padrão (row).
   - `flex: 1` faz com que ocupe todo o espaço disponível entre o cabeçalho e o rodapé.

4. **Navegação e Barra Lateral**:
   - Têm larguras fixas de 200px e 150px respectivamente.

5. **Conteúdo Central**:
   - Usa `flex: 1` para ocupar todo o espaço restante entre a navegação e a barra lateral.

6. **Responsividade**:
   - A media query muda o layout para uma coluna única em telas menores.
   - Ajusta as larguras da navegação e barra lateral para se adaptarem à largura total.

Este exemplo demonstra como o Flexbox pode ser usado para criar um layout complexo e responsivo com relativamente pouco código CSS. O layout se adapta automaticamente a diferentes tamanhos de tela, reorganizando os elementos conforme necessário.

## Conclusão

O Flexbox é uma ferramenta incrivelmente poderosa para criar layouts flexíveis e responsivos. Neste capítulo, exploramos suas propriedades principais e como elas podem ser combinadas para criar designs complexos.

Pontos-chave para lembrar:
1. O Flexbox trabalha com um sistema de container e items.
2. A direção do flex determina o comportamento dos items.
3. Propriedades como `justify-content` e `align-items` oferecem controle preciso sobre o posicionamento.
4. Flexbox é excelente para layouts unidimensionais e alinhamento.
5. Combinado com media queries, o Flexbox permite criar designs verdadeiramente responsivos.

Praticar regularmente com o Flexbox é essencial para dominar sua utilização. Experimente diferentes combinações de propriedades e observe como elas interagem entre si. No próximo capítulo, exploraremos o CSS Grid, outro sistema de layout poderoso que complementa o Flexbox em muitos aspectos.