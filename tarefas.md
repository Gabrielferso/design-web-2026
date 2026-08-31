## Tarefas – Prática Guiada com Tailwind


### 1. Código base  (serve para todas as tarefas)

A artir do mesmo arquivo `index.html` usado na aula anterior (com CDN do Tailwind). Caso não tenham, podem criar um novo com:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Prática Tailwind - Dia 2 [Atividade n]</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 p-6">
  <!-- Os alunos substituirão o conteúdo aqui -->
</body>
</html>
```


## 2. Tarefas
### Tarefa 1 – Card de Notícia Inspirado no IFRN

Recriar o card da notícia “Prêmio IEL 2026” (conforme imagem de referência) utilizando Tailwind CSS. O card deve conter imagem, título, descrição e badges com os prêmios conquistados.


Você deve baixar uma imagem **do PixaBay** (ou outro banco de imagens livre) que represente **premiação, troféu ou evento institucional**. 


#### Layout esperado (visual)

- **Card centralizado** na tela, com largura máxima de ~400px.
- **Imagem** no topo, ocupando toda a largura do card, com altura fixa (ex: 180px) e `object-cover`.
- **Título** em verde escuro (aproximação do verde institucional IFRN), com tamanho grande e negrito.
- **Descrição** em cinza, tamanho médio, com espaçamento.

---

#### Cores aproximadas no Tailwind

| Elemento                 | Cor IFRN (aproximada)    | Classe Tailwind sugerida             |
| ------------------------ | ------------------------ | ------------------------------------ |
| Fundo do card            | Branco                   | `bg-white`                           |
| Título                   | Verde escuro (`#23472B`) | `text-green-800` ou `text-green-900` |
| Descrição                | Cinza médio              | `text-gray-700`                      |
| Fundo dos badges         | Verde claro (`#AAD8B5`)  | `bg-green-200` ou `bg-green-100`     |
| Texto dos badges         | Verde escuro             | `text-green-800`                     |
| Borda do card (opcional) | Verde claro              | `border border-green-200`            |
| Sombra                   | Suave                    | `shadow-md` ou `shadow-lg`           |

---

#### Classes recomendadas

**Container do card:**
- `max-w-sm` (ou `max-w-md`) – largura máxima
- `mx-auto` – centralizar horizontalmente
- `mt-10` – margem superior
- `bg-white` – fundo branco
- `rounded-xl` ou `rounded-2xl` – bordas arredondadas
- `shadow-md` – sombra
- `overflow-hidden` – para a imagem não ultrapassar as bordas arredondadas
- `border border-green-200` (opcional)

**Imagem:**
- `w-full` – largura total
- `h-48` – altura fixa
- `object-cover` – ajuste da imagem sem distorção

**Conteúdo interno:**
- `p-6` – espaçamento interno
- `space-y-3` – espaçamento vertical entre os elementos

**Título:**
- `text-2xl` ou `text-3xl`
- `font-bold`
- `text-green-800`

**Descrição:**
- `text-gray-700`
- `text-base`



### Passo a passo

1. **Baixe uma imagem** do PixaBay (ex: pesquisa por "award" ou "trophy") e salve na pasta do projeto como `premio.jpg` (ou use uma URL direta).
2. No `index.html`, dentro do `<body>`, crie uma `div` com as classes do container.
3. Dentro, adicione uma tag `<img>` com `src="premio.jpg"` e as classes de estilo.
4. Abaixo da imagem, crie uma `div` para o conteúdo (`p-6`).
5. Adicione o título (`<h2>`), a descrição (`<p>`) e os badges (`<span>` ou `<div>`).
6. Ajuste cores e espaçamentos até que o resultado se aproxime da imagem de referência.





### Tarefa 2 – Seção de listagem de notícias

A partir do card individual criado na Tarefa 1, construir uma **página completa de listagem de notícias**, com múltiplos cards organizados em um **grid responsivo**, seguindo o estilo da imagem de referência fornecida (título "Notícias" e vários cards com categoria, título, descrição, data).


#### Imagem de referência (enviada)

A imagem mostra uma seção **"Notícias"** com três cards empilhados verticalmente (em mobile) ou lado a lado (em desktop). Cada card contém:

- **Categoria** (ex: "Prêmio IEL 2026", "Pesquisa", "Internacionalização") – representada por um badge ou tag.
- **Título** (ex: "IFRN tem projetos entre os vencedores do Prêmio IEL 2026").
- **Descrição** curta (ex: "Instituto conquistou o 1º lugar em Educação Inovadora - Nível Técnico e o 2º lugar em Educação Inovadora - Nível Superior").
- **Data** relativa (ex: "Há 20 horas, 40 minutos").

Além disso, a seção tem um **cabeçalho** com o título "Notícias".


#### O que você deve fazer

1. **Reaproveite** o código do card da Tarefa 1 (ou crie um novo) e **duplique-o** para criar pelo menos **3 cards** com conteúdos diferentes (use os exemplos da imagem ou crie seus próprios).
2. **Organize os cards em um grid** que seja:
   - **1 coluna** em telas pequenas (mobile).
   - **2 colunas** em telas médias (tablet).
   - **3 colunas** em telas grandes (desktop).
3. **Adicione um cabeçalho** com o título "Notícias" (estilizado com verde escuro e tamanho adequado).
4. **Personalize cada card**:
   - **Imagem**: cada card deve ter uma imagem diferente (baixe 3 imagens do PixaBay – pode ser sobre premiação, pesquisa, intercâmbio, etc.) ou use a mesma imagem se preferir.
   - **Badge de categoria**: use cores diferentes para cada categoria (ex: verde, azul, amarelo) para destacar.
   - **Título, descrição e data**: preencha com informações fictícias ou inspiradas na imagem.

---

#### Classes recomendadas (consulte o cheatsheet)

**Estrutura da seção:**
- `max-w-7xl mx-auto px-4 py-10` – container centralizado com espaçamento.
- `text-3xl font-bold text-green-800 mb-8` – título "Notícias".

**Grid responsivo:**
- `grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6` – 1 coluna no mobile, 2 no tablet, 3 no desktop, com espaçamento.

**Card (reutilize o da Tarefa 1, mas ajuste):**
- `bg-white rounded-xl shadow-md overflow-hidden hover:shadow-xl transition duration-300` – card com hover.
- `flex flex-col` – para empilhar conteúdo verticalmente.

**Imagem:**
- `w-full h-48 object-cover` – imagem ocupando largura total com altura fixa.

**Conteúdo:**
- `p-5 flex flex-col flex-1` – padding e preenchimento do espaço.
- `space-y-2` – espaçamento entre elementos.

**Badge de categoria:**
- `inline-block text-xs font-semibold px-3 py-1 rounded-full` – base.
- Cores personalizadas (ex: `bg-green-100 text-green-800`, `bg-blue-100 text-blue-800`, `bg-yellow-100 text-yellow-800`).

**Título:**
- `text-xl font-bold text-green-800` – tamanho e cor.

**Descrição:**
- `text-gray-700 text-sm flex-1` – ocupa espaço restante.

**Data:**
- `text-gray-500 text-xs mt-2` – alinhada ao final.


#### Passo a passo

1. **Baixe 3 imagens** do PixaBay (temas: premiação, pesquisa, intercâmbio, etc.) e salve na pasta do projeto (ex: `noticia1.jpg`, `noticia2.jpg`, `noticia3.jpg`).
2. **Estrutura HTML**:
   - Crie uma seção `<section>` com o título "Notícias".
   - Dentro, crie o container do grid.
   - Dentro do grid, insira 3 `<div class="card">` com os conteúdos variados.
3. **Ajuste os textos** conforme a imagem de referência ou crie textos próprios.
4. **Aplique as classes** para estilizar e tornar o layout responsivo.
5. **Teste** redimensionando a janela do navegador para verificar as quebras de coluna.


---

### Entrega

- Crie uma branch chamada **`atividade-n`** a partir da `main`.
- Desenvolva o card nessa branch.
- Comite e envie:
  ```bash
  git add .
  git commit -m "titulo da tarefa do GSA"
  git push origin atividade-n
  ```
- Cole o link da branch no Google Sala de Aula.


### Rúbrica (checklist pra saber se fez certo)

| Critério                             | Peso |
| ------------------------------------ | ---- |
| Uso correto das classes solicitadas  | 40%  |
| Fidelidade ao layout esperado        | 30%  |
| Funcionamento responsivo (Tarefa 3)  | 20%  |
| Commits organizados e branch correta | 10%  |
