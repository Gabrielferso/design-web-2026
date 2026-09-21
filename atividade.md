## Tarefa 3 – Header Responsivo do IFRN com Tailwind

Recriar o cabeçalho do site do IFRN (conforme imagem de referência) utilizando **apenas classes Tailwind CSS** (versão 4), sem CSS customizado.



## O que fazer

### 1. Container centralizado (largura segura)

- Envolva todo o conteúdo do header em um container que limite a largura em telas grandes (ex: `max-w-7xl` ou `max-w-6xl`) e centralize com `mx-auto`.
- Adicione padding horizontal (`px-4` ou `px-6`) para não encostar nas bordas.

### 2. Layout do header (flexível)

- O header deve ser um container flexível (`flex`) com alinhamento vertical (`items-center`) e espaçamento entre os itens (`justify-between`).
- Em telas pequenas, os itens podem se reorganizar. Use `flex-wrap` se necessário.

### 3. Logo (h1)

- O logo é um link com texto longo. Use classes para:
  - Tamanho de fonte adequado (`text-2xl` ou `text-xl` no mobile, `text-3xl` no desktop).
  - Peso da fonte (`font-bold`).
  - Cor (verde escuro, ex: `text-green-800` ou `text-green-900`).
  - Remover sublinhado (`no-underline`).
- O slogan (p com classe `slogan`) deve ficar abaixo ou ao lado do logo (no layout do IFRN, ele aparece abaixo do logo em desktop e pode sumir no mobile). Use classes de responsividade para exibi-lo apenas em telas médias/grandes (`hidden md:block`).

### 4. Menu hambúrguer (botão)

- O botão `#menuToggle` deve ser visível apenas em telas pequenas (`md:hidden`).
- Use classes para estilo: sem borda, fundo transparente, padding, etc.
- O ícone `menu` já está presente.

### 5. Menu de navegação (itens do menu)

- Os itens do menu (que estão na imagem, mas **não** estão no código HTML fornecido – o código fornecido só tem o header, não o menu de navegação).  
  **Atenção:** O código do header.txt não contém os links de navegação (Processos seletivos, Cursos, Campi, etc.). Você precisará **adicionar** uma lista não ordenada (`<ul>`) com os itens de navegação, conforme mostrado na imagem.
- Essa lista deve aparecer em telas grandes (`hidden md:flex`) e ficar oculta em telas pequenas (substituindo o hambúrguer).
- Use `flex`, `gap-4` ou `gap-6`, `items-center` para alinhar.
- Os links devem ter cor escura e hover com verde.

### 6. Ícones sociais e ações (busca, contraste, modo escuro)

- Os itens dentro de `<ul class="social">` e `<ul class="actions">` devem ser organizados horizontalmente com `flex` e `items-center`.
- Use `gap-2` ou `gap-3` entre eles.
- A barra de busca (`form#busca`) deve se comportar como um campo de pesquisa: em telas grandes, pode estar visível; em telas pequenas, pode ser reduzido (apenas ícone) ou oculto. Use `flex` e `items-center`.
- O input deve ter borda, padding, cor de fundo, etc. Use classes como `border`, `rounded-full`, `px-3`, `py-1`, `bg-gray-100`, `focus:outline-none`, `focus:ring`.

### 7. Responsividade (mobile-first)

- No mobile, o header deve exibir: logo (apenas a parte "IFRN" ou o texto curto), botão hambúrguer, e talvez a busca (ícone). Os itens de navegação e os ícones sociais podem ser ocultos ou reorganizados.
- No desktop, todos os itens devem ser exibidos: logo + slogan, menu completo, ícones sociais, busca e botões de acessibilidade.



## Classes Tailwind que você provavelmente usará (consulte o cheatsheet)

- **Layout:** `flex`, `items-center`, `justify-between`, `flex-wrap`, `gap-*`
- **Container:** `max-w-7xl`, `mx-auto`, `px-4`, `py-2` (ou `py-4`)
- **Texto:** `text-*`, `font-*`, `text-green-800`, `text-gray-700`
- **Visibilidade:** `hidden`, `md:flex`, `md:block`, `md:hidden`
- **Botões:** `bg-transparent`, `border-none`, `cursor-pointer`, `p-2`, `rounded`
- **Formulário (busca):** `flex`, `items-center`, `bg-gray-100`, `rounded-full`, `px-3`, `py-1`, `border`, `focus:ring`
- **Links:** `no-underline`, `hover:text-green-600`, `transition`
- **Espaçamento:** `p-*`, `m-*`, `gap-*`, `space-x-*`

---

## Passo a passo para execução

1. **Atualize seu fork** do repositório da turma.
2. **Crie uma nova branch** para esta tarefa:  
   ```bash
   git checkout -b atividade-3-header
   ```
3. **Insira classes Tailwind** em cada elemento para reconstruir o layout, seguindo as orientações acima.
4. **Adicione a lista de navegação** (links) que não está no código original, conforme imagem (Processos seletivos, Cursos, Campi, Institucional, Acesso à Informação, Eventos, Serviços). 
5. **Commit e push**:
   ```bash
   git add .
   git commit -m "Tarefa 3 - Header responsivo com Tailwind"
   git push origin atividade-3-header
   ```
6.  **Envie o link da branch** no Google Sala de Aula.

## Dicas

- Use o **Cheatsheet** que foi fornecido para consultar rapidamente as classes.
- Utilize o **Tailwind Play** (https://play.tailwindcss.com/) para testar pequenos trechos.