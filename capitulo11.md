# Capítulo 11: Pseudo-classes e Pseudo-elementos

## Introdução

Bem-vindos ao fascinante mundo das pseudo-classes e pseudo-elementos! Neste capítulo, vamos explorar duas poderosas ferramentas do CSS que permitem estilizar elementos HTML de maneiras incrivelmente específicas e dinâmicas.

Imagine poder alterar o estilo de um botão quando o mouse passa sobre ele, ou adicionar conteúdo decorativo a um elemento sem modificar o HTML. Essas são apenas algumas das possibilidades que as pseudo-classes e pseudo-elementos nos oferecem.

As pseudo-classes nos permitem selecionar e estilizar elementos com base em seus estados ou relações com outros elementos, enquanto os pseudo-elementos nos permitem estilizar partes específicas de um elemento ou até mesmo criar novos elementos virtuais.

Prepare-se para uma jornada emocionante que elevará suas habilidades de estilização CSS a um novo patamar. Vamos mergulhar fundo nesse universo e desbloquear um novo nível de controle e criatividade em seus designs web!

## 11.1 Pseudo-classes

### O que são Pseudo-classes?

Pseudo-classes são seletores especiais que permitem estilizar elementos HTML baseados em estados específicos ou em sua relação com outros elementos no documento. Elas começam com dois pontos (:) e são adicionadas ao final de um seletor.

### Pseudo-classes de Estado

#### :hover

A pseudo-classe `:hover` é usada para estilizar um elemento quando o cursor do mouse está sobre ele.

```css
button {
  background-color: blue;
  color: white;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: darkblue;
}
```

Neste exemplo:
- O botão normalmente tem um fundo azul.
- Quando o mouse passa sobre o botão, o fundo muda para azul escuro.
- A transição suaviza a mudança de cor.

#### :focus

A pseudo-classe `:focus` estiliza um elemento quando ele recebe foco (por exemplo, quando selecionado com o teclado).

```css
input {
  border: 2px solid #ccc;
}

input:focus {
  border-color: blue;
  outline: none;
}
```

Aqui:
- Os campos de input têm uma borda cinza por padrão.
- Quando focados, a borda muda para azul.
- Removemos o outline padrão do navegador para um visual mais limpo.

#### :active

`:active` é aplicado quando um elemento está sendo ativado pelo usuário (por exemplo, um botão sendo clicado).

```css
button:active {
  transform: scale(0.95);
}
```

Este código faz o botão parecer "pressionado" quando clicado, reduzindo ligeiramente seu tamanho.

### Pseudo-classes de Estado de Formulário

#### :checked

Aplicada a elementos de input do tipo checkbox ou radio quando estão marcados.

```css
input[type="checkbox"]:checked + label {
  color: green;
}
```

Este exemplo muda a cor do texto do label para verde quando o checkbox associado está marcado.

#### :disabled e :enabled

Estilos para elementos de formulário desabilitados ou habilitados.

```css
input:disabled {
  background-color: #f0f0f0;
  cursor: not-allowed;
}

input:enabled {
  background-color: white;
}
```

### Pseudo-classes Estruturais

#### :first-child e :last-child

Selecionam o primeiro e o último filho de um elemento pai.

```css
li:first-child {
  font-weight: bold;
}

li:last-child {
  border-bottom: none;
}
```

#### :nth-child(n)

Seleciona elementos baseados em sua posição em um grupo de irmãos.

```css
/* Seleciona itens pares */
li:nth-child(even) {
  background-color: #f0f0f0;
}

/* Seleciona cada terceiro item */
li:nth-child(3n) {
  color: red;
}
```

### Pseudo-classes de Negação

#### :not()

Seleciona elementos que não correspondem ao seletor especificado.

```css
/* Estiliza todos os parágrafos, exceto aqueles com a classe 'special' */
p:not(.special) {
  color: gray;
}
```

## 11.2 Pseudo-elementos

### O que são Pseudo-elementos?

Pseudo-elementos permitem estilizar partes específicas de um elemento ou criar elementos virtuais. Eles começam com dois pontos duplos (::) e são adicionados ao final de um seletor.

### ::before e ::after

Estes pseudo-elementos permitem inserir conteúdo antes ou depois do conteúdo de um elemento.

```css
.quote::before {
  content: '"';
  font-size: 2em;
  color: #999;
}

.quote::after {
  content: '"';
  font-size: 2em;
  color: #999;
}
```

Neste exemplo:
- Adicionamos aspas antes e depois do texto de elementos com a classe `quote`.
- O `content` especifica o que será inserido.
- Estilizamos as aspas para serem maiores e em uma cor cinza.

### ::first-letter e ::first-line

Estilizam a primeira letra ou a primeira linha de um elemento de bloco.

```css
p::first-letter {
  font-size: 2em;
  font-weight: bold;
  color: #333;
}

p::first-line {
  font-style: italic;
}
```

### ::selection

Estiliza a parte do texto que foi selecionada pelo usuário.

```css
::selection {
  background-color: yellow;
  color: black;
}
```

Este código muda a cor de fundo para amarelo e o texto para preto quando o usuário seleciona texto na página.

## 11.3 Combinando Pseudo-classes e Pseudo-elementos

Podemos combinar pseudo-classes e pseudo-elementos para criar efeitos ainda mais específicos.

```css
a:hover::after {
  content: ' ➔';
  color: blue;
}
```

Neste exemplo, uma seta azul aparece após o texto do link quando o mouse passa sobre ele.

## 11.4 Exemplo Prático: Estilização Avançada de um Formulário

Vamos criar um formulário estilizado usando várias pseudo-classes e pseudo-elementos:

```html
<form class="styled-form">
  <div class="form-group">
    <input type="text" id="name" required>
    <label for="name">Nome</label>
  </div>
  <div class="form-group">
    <input type="email" id="email" required>
    <label for="email">Email</label>
  </div>
  <div class="form-group">
    <input type="checkbox" id="terms">
    <label for="terms">Aceito os termos e condições</label>
  </div>
  <button type="submit">Enviar</button>
</form>
```

```css
.styled-form .form-group {
  position: relative;
  margin-bottom: 20px;
}

.styled-form input[type="text"],
.styled-form input[type="email"] {
  width: 100%;
  padding: 10px;
  border: none;
  border-bottom: 2px solid #ccc;
  outline: none;
  transition: border-color 0.3s;
}

.styled-form label {
  position: absolute;
  top: 10px;
  left: 0;
  color: #999;
  transition: all 0.3s;
  pointer-events: none;
}

/* Efeito de label flutuante */
.styled-form input:focus + label,
.styled-form input:not(:placeholder-shown) + label {
  top: -20px;
  font-size: 0.8em;
  color: #4a90e2;
}

/* Estilização da borda quando focado */
.styled-form input:focus {
  border-color: #4a90e2;
}

/* Estilização do checkbox */
.styled-form input[type="checkbox"] {
  display: none;
}

.styled-form input[type="checkbox"] + label::before {
  content: '';
  display: inline-block;
  width: 20px;
  height: 20px;
  margin-right: 10px;
  border: 2px solid #ccc;
  vertical-align: text-bottom;
}

.styled-form input[type="checkbox"]:checked + label::before {
  background-color: #4a90e2;
  border-color: #4a90e2;
}

.styled-form input[type="checkbox"]:checked + label::after {
  content: '✓';
  position: absolute;
  left: 5px;
  color: white;
}

/* Estilização do botão */
.styled-form button {
  padding: 10px 20px;
  background-color: #4a90e2;
  color: white;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s;
}

.styled-form button:hover {
  background-color: #3a7bc8;
}

.styled-form button:active {
  transform: scale(0.98);
}
```

Neste exemplo prático:

- Usamos `:focus` e `:not(:placeholder-shown)` para criar um efeito de "label flutuante".
- Aplicamos `::before` e `::after` para criar um checkbox customizado.
- Utilizamos `:hover` e `:active` para estilizar interações com o botão.
- Combinamos várias pseudo-classes e pseudo-elementos para criar uma experiência de formulário rica e interativa.

## Conclusão

Pseudo-classes e pseudo-elementos são ferramentas incrivelmente poderosas no arsenal de um desenvolvedor web. Elas permitem criar interações ricas e estilos dinâmicos sem a necessidade de JavaScript ou marcação HTML adicional.

Neste capítulo, exploramos uma variedade de pseudo-classes e pseudo-elementos, desde os mais básicos até usos mais avançados. Lembre-se de que a prática é crucial para dominar essas técnicas. Experimente combinar diferentes pseudo-classes e pseudo-elementos, e veja como eles podem transformar sua abordagem ao design web.

À medida que você avança em sua jornada de desenvolvimento, você descobrirá que pseudo-classes e pseudo-elementos são essenciais para criar interfaces modernas, interativas e acessíveis. Continue explorando e experimentando, e você descobrirá ainda mais maneiras criativas de usar essas poderosas ferramentas CSS!