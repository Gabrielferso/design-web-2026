## Tarefa 10 – Seção de eventos

**Objetivo:** A partir do código HTML limpo (sem classes), você deve adicionar classes Tailwind para estilizar a seção "Eventos" do site do IFRN, reproduzindo o layout da imagem de referência.


### regras

- Use apenas classes utilitárias do Tailwind – sem CSS customizado.
- Não modifique a estrutura HTML (tags, conteúdo, atributos href, src, etc.).
- Consulte o Cheatsheet para encontrar as classes adequadas.


---

## Passo a passo para execução

1. **Atualize seu fork** do repositório da turma.
2. **Crie uma nova branch** para esta tarefa:  
   ```bash
   git checkout -b features/atividade-10-evento
   ```
3. **Insira classes Tailwind** em cada elemento para reconstruir o layout, visualizando como está o site do IFRN e criar a estrutura adequada com as classes mais proeminentes.
   
4. **Commit e push**:
   ```bash
   git add .
   git commit -m "Atividade 10 - Seção de eventos"
   git push origin atividade-9-footer
   ```

5.  **Envie o link da branch** no Google Sala de Aula.

## Dicas

- Use o **Cheatsheet** que foi fornecido para consultar rapidamente as classes.
- Utilize o **Tailwind Play** (https://play.tailwindcss.com/) para testar pequenos trechos.
- **Cores institucionais:**
  - Verde escuro: `#23472B`
  - Verde funcional: `#58B06B`
  - Verde claro (bordas): `#AAD8B5`
  - Fundo da seção: `#E8F2EC`
- **Status diferenciados:** "Em breve" e "Em andamento" devem ter cores diferentes para transmitir a informação visualmente.
- **Acessibilidade:** mantenha os `aria-hidden="true"` nos ícones e o `title` nos chips de campus.
- **Hover:** cada card deve ter um efeito sutil (sombra + borda mais forte) ao passar o mouse.


#### Container geral da seção
```html
<section class="bg-[#E8F2EC] py-16">
  <div class="max-w-7xl mx-auto px-4">
```

#### Cabeçalho (título + botão + descrição)
Aqui é uma parte do código, mas é preciso fazer os ajustes mais finos.

```html
<div class="flex flex-col md:flex-row md:items-center md:justify-between gap-4 mb-6">
  <h2 class="text-3xl md:text-4xl font-bold text-[#23472B]">Eventos</h2>
  <a href="/eventos/" class="inline-flex items-center gap-2 text-sm font-medium text-[#23472B] border border-[#23472B] rounded-full px-4 py-2 hover:bg-[#23472B] hover:text-white transition self-start md:self-auto">
    Todos os eventos
    <i class="ph ph-caret-right"></i>
  </a>
</div>
<p class="text-[#3A3A3A] max-w-3xl mb-10 leading-relaxed">...</p>
```

#### Grade de cards
```html
<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
```
> 💡 Na imagem original aparecem 5 cards em uma linha, mas com `lg:grid-cols-4` você mantém um layout equilibrado. Para 5 colunas, use `lg:grid-cols-5`.

#### Cada card (link `<a>`)
```html
<a href="#" class="bg-white rounded-2xl border border-[#AAD8B5] p-5 flex flex-col gap-3 hover:shadow-md hover:border-[#58B06B] transition-all duration-200">
```

#### Status (span)
```html
<span class="inline-flex items-center gap-1 text-xs font-semibold text-[#23472B]">
  <i class="ph ph-warning"></i>
  Em breve
</span>
```
> Para "Em andamento", mude a cor e o ícone:
> ```html
> <span class="inline-flex items-center gap-1 text-xs font-semibold text-[#58B06B]">
>   <i class="ph ph-circle"></i>
>   Em andamento
> </span>
> ```

#### Chip de Campus
```html
<span class="inline-flex items-center gap-1 text-xs text-gray-600 border border-gray-200 rounded-full px-3 py-1 self-start">
  <i class="ph ph-buildings"></i>
  Pau dos Ferros
</span>
```

#### Título do evento
```html
<h3 class="text-base font-medium text-[#1A1A1A] leading-snug flex-1">
  Vivências em Arte
</h3>
```

#### Data (bloco com dia/mês/ano)
```html
<div class="flex items-end gap-2 mt-2">
  <span class="text-4xl font-bold text-[#23472B] leading-none">07</span>
  <div class="flex flex-col text-xs font-semibold text-[#23472B] uppercase">
    <span>dez</span>
    <span class="text-gray-500 font-normal">2026</span>
  </div>
</div>
```

