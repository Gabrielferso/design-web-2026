# Catálogo de Oficinas Vue.js

Atividade prática da terceira semana de Vue.js.

## Objetivo

Construir um **catálogo dinâmico de oficinas** usando **apenas Vue.js** via CDN. O usuário poderá adicionar oficinas, marcar favoritas, excluir itens e filtrar a lista.

Nesta atividade, você vai trabalhar com **listas** (`v-for`), **identificação de itens** (`:key`), **eventos** (`@click` e `@submit.prevent`), **classes dinâmicas** (`:class`), **arrays**, **métodos** e uma propriedade **computada** (`computed`).

**Toda a estrutura visual e o HTML com Vue já estão prontos.** Você só precisa implementar **3 métodos e 1 propriedade computada** para completar as funcionalidades do catálogo.

**Já está pronto:**

- Todo o HTML (campo para nova oficina, botões, filtros e lista)
- Todo o visual em Tailwind CSS + DaisyUI
- O `v-model` que liga o campo de texto ao estado
- Os eventos: `@submit.prevent` para adicionar, `@click` para favoritar e excluir
- O `v-for` que monta a lista e o `:key` que identifica cada oficina
- As condições `v-if`/`v-else` do estado vazio e do aviso **Favorita**
- O `:class` que destaca os filtros e altera o botão **Favoritar**
- A estrutura `Vue.createApp({...}).mount('#app')`
- O `data()` com três oficinas iniciais e os demais dados necessários
- O método `limparCampo()` completo como exemplo
- O `computed` com um retorno provisório para a lista aparecer antes do TODO 4

**Falta fazer:**

3 métodos e 1 propriedade computada dentro do `<script>`:

| TODO       | Método / computed                 | Funcionalidade                         |
| ---------- | --------------------------------- | -------------------------------------- |
| **TODO 1** | `adicionarOficina()`              | Adiciona uma oficina ao array          |
| **TODO 2** | `alternarFavorito(id)`            | Marca ou desmarca uma oficina favorita |
| **TODO 3** | `removerOficina(id)`              | Exclui a oficina selecionada           |
| **TODO 4** | `oficinasVisiveis()` (`computed`) | Mostra todas ou apenas as favoritas    |

Abra o `index.html` e siga os comentários `TODO` dentro do `<script>`. **Não modifique o HTML nem o `data()`**: trabalhe somente nos TODOs indicados.

### TODO 1 — `adicionarOficina()`

Recebe o texto digitado em `novaOficina` e adiciona um novo objeto à lista `oficinas`.

**Regras:**
1. Crie `const titulo = this.novaOficina.trim()`.
2. Se `titulo === ''`, use `return` (não adicione oficina vazia).
3. Use `this.oficinas.push(...)` para adicionar um objeto com `id: this.proximoId`, `titulo: titulo` e `favorita: false`.
4. Aumente `this.proximoId` em 1 para que a próxima oficina tenha outro identificador.
5. Chame `this.limparCampo()`.

**Exemplos:**
- Digitar `Robótica` e clicar em **Adicionar**, aparece mais uma oficina.
- Tentar adicionar um campo vazio, a lista não deve mudar.

**Após concluir, faça um commit (sem push):**

```bash
git add index.html
git commit -m "feat: adiciona oficinas a lista"
```

### TODO 2 — `alternarFavorito(id)`

Deve ser chamado quando o usuário clicar no botão **Favoritar**, de uma oficina.

**Regras:**
1. Procure a oficina com `this.oficinas.find(item => item.id === id)` e guarde o resultado em uma variável `oficina`.
2. Se a oficina não existir, use `return`.
3. Inverta o valor de `oficina.favorita` usando `!`.
4. Observe o texto do botão, a classe visual e o aviso **Favorita**: o HTML já reage à mudança de estado.


**Após concluir, faça um commit (sem push):**

```bash
git add index.html
git commit -m "feat: alterna oficinas favoritas"
```

### TODO 3 — `removerOficina(id)`

É chamado ao clicar em **Excluir** no item correspondente.

**Regras:**
1. Use `this.oficinas.filter(...)` para produzir um array apenas com itens cujo `item.id !== id`.
2. Atribua esse novo array a `this.oficinas`.
3. Observe a atualização da lista sem manipular o HTML manualmente.


**Após concluir e testar, faça um commit (sem push):**

```bash
git add index.html
git commit -m "feat(aula-46): remove oficina pelo id"
```

### TODO 4 — `oficinasVisiveis()` (`computed`)

É uma propriedade computada: produz uma lista a partir de `oficinas` e do filtro atual. O HTML já utiliza `oficinasVisiveis` no `v-for` e no contador.

**Regras:**
1. Dentro de `computed`, localize `oficinasVisiveis()`.
2. **Substitua** o retorno provisório `return this.oficinas;` por uma condição `if`.
3. Se `this.filtro === 'favoritas'`, retorne `this.oficinas.filter(oficina => oficina.favorita)`.
4. Caso contrário, retorne `this.oficinas`.

**Após concluir, faça um commit (sem push):**

```bash
git add index.html
git commit -m "feat(aula-46): filtra oficinas favoritas"
```

### Referência: o `limparCampo()` já está pronto

Use como exemplo de como acessar o estado com `this`:

```js
limparCampo() {
  this.novaOficina = '';
}
```


## Entrega no GSA

Crie uma branch para a atividade. **Após cada TODO concluído e testado, faça o commit local correspondente**. Não precisa dar `push` a cada TODO. Faça um único `push` ao finalizar.


