# Cheatsheet Tailwind CSS v4 – Semana 4


## Como usar

- Cada seção lista as classes mais comuns, com descrição e um **xemplo visual**.
- Use a **busca** do seu navegador (Ctrl+F) para encontrar uma classe específica.
- Ao final, um **exemplo completo** mostra como construir um componente real.
- Link do CDN V4 - `<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>`


## 1. Layout (Display, Position, Overflow)

| Classe            | Descrição                                                              | Exemplo                                                          |
| ----------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------- |
| `block`           | Ocupa toda a largura disponível.                                       | `<div class="block bg-green-200 p-2">Bloco</div>`                |
| `inline-block`    | Largura ajustada ao conteúdo, mas permite padding.                     | `<span class="inline-block bg-blue-200 p-2">Inline-block</span>` |
| `inline`          | Não aceita largura/altura, apenas conteúdo.                            | `<span class="inline bg-red-200 p-1">Inline</span>`              |
| `hidden`          | Remove o elemento da tela (`display: none`).                           | `<div class="hidden">Invisível</div>`                            |
| `relative`        | Posicionamento relativo (referência para filhos absolutos).            | `<div class="relative">...</div>`                                |
| `absolute`        | Posicionamento absoluto em relação ao pai mais próximo com `relative`. | `<div class="absolute top-0 right-0">...</div>`                  |
| `fixed`           | Posicionamento fixo em relação à janela do navegador.                  | `<div class="fixed bottom-4 right-4">...</div>`                  |
| `sticky`          | Comportamento híbrido: relativo até o scroll, depois fixo.             | `<div class="sticky top-0">...</div>`                            |
| `overflow-auto`   | Adiciona scroll se o conteúdo transbordar.                             | `<div class="overflow-auto h-20">...</div>`                      |
| `overflow-hidden` | Oculta o conteúdo que transborda.                                      | `<div class="overflow-hidden">...</div>`                         |
| `z-10`, `z-20`, … | Controla a ordem de empilhamento (quanto maior, mais acima).           | `<div class="z-10">...</div>`                                    |

---

## 2. Espaçamento (Padding, Margin, Gap)

| Classe         | Descrição                                    | Equivalente                                   |
| -------------- | -------------------------------------------- | --------------------------------------------- |
| `p-1` … `p-12` | Padding em todos os lados.                   | `padding: 0.25rem` … `3rem`                   |
| `px-4`         | Padding horizontal (esquerda + direita).     | `padding-left: 1rem; padding-right: 1rem`     |
| `py-2`         | Padding vertical (topo + base).              | `padding-top: 0.5rem; padding-bottom: 0.5rem` |
| `pt-6`         | Padding apenas no topo.                      | `padding-top: 1.5rem`                         |
| `m-1` … `m-12` | Margem em todos os lados.                    | `margin: 0.25rem` … `3rem`                    |
| `mx-auto`      | Margem horizontal automática (centraliza).   | `margin-left: auto; margin-right: auto`       |
| `my-4`         | Margem vertical (topo + base).               | `margin-top: 1rem; margin-bottom: 1rem`       |
| `gap-2`        | Espaçamento entre itens em grid/flex.        | `gap: 0.5rem`                                 |
| `space-x-4`    | Espaçamento horizontal entre filhos diretos. | `& > * + * { margin-left: 1rem }`             |
| `space-y-2`    | Espaçamento vertical entre filhos diretos.   | `& > * + * { margin-top: 0.5rem }`            |

---

## 3. Tipografia e Texto

| Classe                                                   | Descrição                                         | Exemplo                                      |
| -------------------------------------------------------- | ------------------------------------------------- | -------------------------------------------- |
| `text-xs` … `text-6xl`                                   | Tamanho da fonte (0.75rem … 4rem).                | `<p class="text-2xl">Título</p>`             |
| `font-thin` … `font-black`                               | Peso da fonte (100 … 900).                        | `<p class="font-bold">Negrito</p>`           |
| `text-left`, `text-center`, `text-right`, `text-justify` | Alinhamento do texto.                             | `<p class="text-center">Centralizado</p>`    |
| `uppercase`, `lowercase`, `capitalize`                   | Transformação de caixa.                           | `<span class="uppercase">maiúsculo</span>`   |
| `leading-3` … `leading-10`                               | Altura da linha (espaçamento entre linhas).       | `<p class="leading-relaxed">...</p>`         |
| `tracking-wide`                                          | Espaçamento entre caracteres.                     | `<p class="tracking-wide">Espaçado</p>`      |
| `line-clamp-1` … `line-clamp-6`                          | Limita o texto a um número de linhas (com `...`). | `<p class="line-clamp-2">Texto longo...</p>` |

---

## 4. Cores (Background, Texto, Bordas)

### 4.1 Cores de fundo (`bg-`)
> [Link com as cores e como são usadas no tailwind](https://tailwindcss.com/docs/colors)

| Classe                                            | Descrição                          |
| ------------------------------------------------- | ---------------------------------- |
| `bg-white`, `bg-black`                            | Branco e preto puros.              |
| `bg-gray-100` … `bg-gray-900`                     | Escala de cinza (50–950).          |
| `bg-red-500`, `bg-blue-600`, `bg-green-400`, etc. | Cores da paleta Tailwind (50–950). |
| `bg-transparent`                                  | Fundo transparente.                |
| `bg-current`                                      | Usa a cor do texto atual.          |

**Exemplo:** `<div class="bg-blue-500 text-white p-4">Fundo azul</div>`

### 4.2 Cor do texto (`text-`)

Mesma paleta de cores, mas aplicada ao texto.

**Exemplo:** `<p class="text-red-600">Texto vermelho</p>`

### 4.3 Cor da borda (`border-`)

| Classe                           | Descrição                    |
| -------------------------------- | ---------------------------- |
| `border-gray-200`                | Borda cinza claro.           |
| `border-2`, `border-4`           | Espessura da borda.          |
| `border-dashed`, `border-dotted` | Estilo tracejado/pontilhado. |
| `border-t-4`                     | Borda apenas no topo.        |

**Exemplo:** `<div class="border-2 border-blue-500 rounded-lg">...</div>`

---

## 5. Flexbox

| Classe                                                                                                  | Descrição                                |
| ------------------------------------------------------------------------------------------------------- | ---------------------------------------- |
| `flex`                                                                                                  | Ativa o Flexbox (display: flex).         |
| `flex-row` (padrão)                                                                                     | Direção horizontal.                      |
| `flex-col`                                                                                              | Direção vertical (coluna).               |
| `flex-wrap`                                                                                             | Permite quebra de linha.                 |
| `justify-start`, `justify-center`, `justify-end`, `justify-between`, `justify-around`, `justify-evenly` | Alinhamento horizontal (eixo principal). |
| `items-start`, `items-center`, `items-end`, `items-stretch`, `items-baseline`                           | Alinhamento vertical (eixo transversal). |
| `gap-2`                                                                                                 | Espaçamento entre itens.                 |
| `flex-1`, `flex-auto`, `flex-none`                                                                      | Controle de crescimento dos itens.       |
| `order-1`, `order-last`                                                                                 | Ordenação dos itens.                     |

**Exemplo:**  
```html
<div class="flex justify-between items-center gap-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

---

## 6. Grid

| Classe                                  | Descrição                                    |
| --------------------------------------- | -------------------------------------------- |
| `grid`                                  | Ativa o Grid (display: grid).                |
| `grid-cols-1` … `grid-cols-12`          | Número de colunas (1 a 12).                  |
| `grid-rows-1` … `grid-rows-6`           | Número de linhas.                            |
| `col-span-1` … `col-span-12`            | Quantas colunas o item ocupa.                |
| `row-span-1` … `row-span-6`             | Quantas linhas o item ocupa.                 |
| `gap-4`                                 | Espaçamento entre células (linha + coluna).  |
| `gap-x-2`, `gap-y-4`                    | Espaçamento específico por eixo.             |
| `place-items-center`                    | Centraliza itens horizontal e verticalmente. |
| `auto-cols-auto`, `auto-rows-min`, etc. | Tamanho automático das colunas/linhas.       |

**Exemplo:**  
```html
<div class="grid grid-cols-3 gap-4">
  <div class="col-span-2">Item maior</div>
  <div>Item 2</div>
  <div>Item 3</div>
  <div>Item 4</div>
</div>
```

---

## 7. Responsividade (Breakpoints)

Responsividade é o nome que damos quando um site se ajusta para ficar legível em telas pequenas e grandes. No Tailwind isso é feito com prefixos que você coloca antes das classes.

| Prefixo | Quando começa a valer | O que isso significa, simples |
| ------- | --------------------- | ---------------------------- |
| (sem)   | todas as telas        | regra padrão (sempre)        |
| `sm:`   | 640px                 | celulares (em pé)            |
| `md:`   | 768px                 | tablets                      |
| `lg:`   | 1024px                | notebooks                    |
| `xl:`   | 1280px                | desktops maiores             |
| `2xl:`  | 1536px                | telas muito grandes          |

Como usar: escreva o prefixo antes da classe. Exemplo fácil:

```html
<div class="text-sm md:text-lg lg:text-2xl">
  O texto aumenta em telas maiores.
</div>
```

---

### 7.1 Container responsivo

O `container` serve para deixar o conteúdo com largura agradável e sempre centralizado. É bom para páginas com texto, artigos ou seções principais.

Jeito rápido de usar:
- Coloque `container` no elemento que envolve seu conteúdo.
- Adicione `mx-auto` para centralizar.
- Use `px-4` (ou `sm:px-6`) para dar espaço nas laterais em telas pequenas/maiores.

Larguras aproximadas que o `container` usa por padrão:

| Quando | Largura máxima aproximada |
| ------ | ------------------------- |
| base   | 100% (sem limite pequeno) |
| sm     | ~640px                    |
| md     | ~768px                    |
| lg     | ~1024px                   |
| xl     | ~1280px                   |
| 2xl    | ~1536px                   |

Exemplo simples:

```html
<div class="container mx-auto px-4 sm:px-6">
  <section class="py-8">
    <h1 class="text-2xl font-bold">Título</h1>
    <p class="mt-2 text-gray-600">Conteúdo centralizado que não fica largo demais em telas grandes.</p>
  </section>
</div>
```

Se você usa Tailwind com build (npm), dá para mudar esses valores em `tailwind.config.js` — por exemplo para deixar o `container` sempre centralizado e com outro `padding` padrão.

---

## 8. Estados (Hover, Focus, Active, etc.)

| Prefixo        | Descrição                                                  |
| -------------- | ---------------------------------------------------------- |
| `hover:`       | Aplica ao passar o mouse.                                  |
| `focus:`       | Aplica quando o elemento está em foco (teclado ou clique). |
| `active:`      | Aplica enquanto o elemento está sendo clicado.             |
| `disabled:`    | Aplica quando o elemento está desabilitado.                |
| `group-hover:` | Aplica quando um elemento pai com `group` está em hover.   |
| `dark:`        | Aplica apenas no modo escuro (se habilitado).              |

**Exemplo:**  
```html
<button class="bg-blue-500 hover:bg-blue-700 focus:ring-2 focus:ring-blue-300">
  Clique
</button>
```

---

## 9. Animações e Transições

| Classe                                                            | Descrição                                        |
| ----------------------------------------------------------------- | ------------------------------------------------ |
| `transition`                                                      | Habilita transições para todas as propriedades.  |
| `transition-colors`, `transition-transform`, `transition-opacity` | Transição específica.                            |
| `duration-75` … `duration-1000`                                   | Duração da transição (ms).                       |
| `ease-in`, `ease-out`, `ease-in-out`                              | Curva de aceleração.                             |
| `transform`                                                       | Habilita transformações (escala, rotação, etc.). |
| `hover:scale-105`                                                 | Aumenta 5% no hover.                             |
| `hover:rotate-12`                                                 | Rotaciona 12 graus no hover.                     |
| `animate-spin`                                                    | Rotação infinita (loading).                      |
| `animate-pulse`                                                   | Efeito de pulsação.                              |
| `animate-bounce`                                                  | Efeito de quicar.                                |

**Exemplo:**  
```html
<div class="transition duration-300 ease-in-out hover:scale-105 hover:rotate-3">
  Hover em mim!
</div>
```

---

## 10. Utilitários Extras

| Classe                                          | Descrição                                             |
| ----------------------------------------------- | ----------------------------------------------------- |
| `rounded`, `rounded-lg`, `rounded-full`         | Arredondamento de bordas.                             |
| `shadow`, `shadow-md`, `shadow-lg`, `shadow-xl` | Sombras (crescentes).                                 |
| `shadow-none`                                   | Remove sombra.                                        |
| `opacity-0` … `opacity-100`                     | Opacidade (0% a 100%).                                |
| `cursor-pointer`, `cursor-not-allowed`          | Estilo do cursor.                                     |
| `object-cover`, `object-contain`                | Ajuste de imagem dentro de container.                 |
| `select-none`                                   | Impede seleção de texto.                              |
| `sr-only`                                       | Oculta visualmente, mas mantém para leitores de tela. |




## Exemplo Combinado – Cartão de Produto

```html
<div class="max-w-sm mx-auto bg-white rounded-2xl shadow-md overflow-hidden hover:shadow-xl transition duration-300">
  <img src="https://picsum.photos/400/200" alt="Produto" class="w-full h-48 object-cover">
  <div class="p-6">
    <span class="inline-block bg-green-100 text-green-800 text-xs font-semibold px-3 py-1 rounded-full uppercase tracking-wide">
      Novo
    </span>
    <h3 class="mt-2 text-xl font-bold text-gray-800">Produto Incrível</h3>
    <p class="mt-1 text-gray-600 text-sm">Descrição breve do produto, com destaque para seus benefícios.</p>
    <div class="mt-4 flex items-center justify-between">
      <span class="text-2xl font-bold text-gray-900">R$ 99,90</span>
      <button class="bg-blue-600 hover:bg-blue-700 text-white font-semibold py-2 px-4 rounded-full transition">
        Comprar
      </button>
    </div>
  </div>
</div>
```


## Como personalizar (tailwind.config.js)

Se você estiver usando o Tailwind com build (npm), pode criar um arquivo `tailwind.config.js` para:

- Adicionar cores customizadas.
- Estender breakpoints.
- Criar classes com `@apply` (para componentes reutilizáveis).
- Habilitar o modo escuro (`darkMode: 'class'`).

Exemplo mínimo:
```js
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {
      colors: {
        'ifrn-green': '#23472B',
        'ifrn-light': '#AAD8B5',
      },
      fontFamily: {
        'inter': ['Inter', 'sans-serif'],
      },
    },
  },
  plugins: [],
}
```

---
