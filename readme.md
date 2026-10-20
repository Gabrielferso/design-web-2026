
=======
# Calculadora Vue.js — Aula 01

Atividade prática da primeira aula de Vue.js.
## Objetivo

Construir uma calculadora com as **quatro operações** (`+`, `−`, `×`, `÷`) usando **apenas Vue.js** via CDN.

**Toda a estrutura visual e html com Vue já estão prontos.** Você só precisa implementar ** os 3 métodos** que fazem a funcionalidade da calculadora.



**Já está pronto:**

- Todo o HTML (a `<div id="app">`, os botões, o visor)
- Todo o visual em Tailwind CSS + DaisyUI
- Os botões já estão conectados aos métodos via `@click`
- A estrutura `Vue.createApp({...}).mount('#app')`
- O `data()` com os 4 campos do estado
- O método `clear()` completo como exemplo

**Falta fazer:**

3 métodos dentro do `<script>`:

| TODO | Método | Funcionalidade |
|---|---|---|
| **TODO 1** | `appendDigit(digit)` | Digita um número no visor |
| **TODO 2** | `setOperator(op)` | Registra o operador pendente |
| **TODO 3** | `calculate()` | Executa a conta |

Abra o `index.html` e siga os comentários `TODO` em cada método.

### TODO 1 — `appendDigit(digit)`

Recebe um dígito (`'0'` a `'9'`) e atualiza o visor.

<<<<<<< HEAD
<<<<<<< HEAD
- Tags HTML semânticas (`header`, `main`, `section`, `footer`)
- Atributos de acessibilidade (`role`, `aria-label`, `focus-visible`)
- Responsividade com mixins (mobile-first)
- Código SCSS organizado com variáveis e aninhamento

=======
- Use o **Cheatsheet** que foi fornecido para consultar rapidamente as classes.
- Utilize o **Tailwind Play** (https://play.tailwindcss.com/) para testar pequenos trechos.
- Use bg-green-800 ou bg-[#23472B] para o fundo do footer.
- Para os links do sitemap, text-white e hover:text-green-300.
- Para os ícones sociais, use text-2xl e hover:text-green-300.
- Aproveite o espaçamento gap-* para organizar os elementos.

=======
**Regras:**
1. Se `waitingForSecond` for `true`: **substitui** `this.display` pelo dígito e marca `waitingForSecond = false`.
2. Senão, se `this.display === '0'`: **substitui** pelo dígito (para nao concatenar).
3. Senão: **concatena** — `this.display = this.display + digit`.

**Exemplos:**
- `display='0'`, `digit='5'` → `display='5'`
- `display='12'`, `digit='3'` → `display='123'`
- `display='12'`, `waitingForSecond=true`, `digit='7'` → `display='7'`

### TODO 2 — `setOperator(op)`

Recebe um operador (`'+'`, `'-'`, `'*'`, `'/'`) e o registra para a próxima conta.

**Regras:**
1. Se `this.display === 'Erro'`: **saia** (`return`) sem fazer nada.
2. Se `this.operator !== null` **e** `this.waitingForSecond === false`: chame `this.calculate()` primeiro (para encadear `5 + 3 ×`).
3. `this.firstOperand = parseFloat(this.display)`
4. `this.operator = op`
5. `this.waitingForSecond = true`

### TODO 3 — `calculate()`

Executa a operação pendente e mostra o resultado.

**Regras:**
1. Se `this.operator === null` **ou** `this.firstOperand === null`: **retorne** (nada a fazer).
2. `const a = this.firstOperand`
3. `const b = parseFloat(this.display)`
4. Aplique o operador:
   - `'+'` → `a + b`
   - `'-'` → `a - b`
   - `'*'` → `a * b`
   - `'/'` → se `b === 0` → `'Erro'`; senão `a / b`
5. `this.display = String(resultado)`
6. `this.firstOperand = null`
7. `this.operator = null`
8. `this.waitingForSecond = true`

### Referência: o `clear()` já está pronto

Use como exemplo de como acessar o estado com `this`:

```js
clear() {
  this.display = '0';
  this.firstOperand = null;
  this.operator = null;
  this.waitingForSecond = false;
}
```

## Como testar

| Cliques | Visor deve mostrar |
|---|---|
| `7` `+` `5` `=` | `12` |
| `9` `×` `8` `=` | `72` |
| `1` `0` `÷` `4` `=` | `2.5` |
| `8` `−` `3` `=` | `5` |
| `5` `÷` `0` `=` | `Erro` |
| `7` `+` `3` `=` `×` `2` `=` | `20` |
| `7` `+` `3` `×` `2` `=` | `20` |
| `C` | `0` |
| `5` `÷` `0` `=` `7` `+` `1` `=` | `8` (recupera do `Erro`) |



## Entrega no GSA

```bash
git checkout -b aula-01-calculadora
git add .
git commit -m "Aula 01 — Calculadora Vue"
git push -u origin aula-01-calculadora
```

No GitHub, abra a aba **Branches**, encontre `aula-01-calculadora` e **copie a URL** da branch (algo como `https://github.com/<usuario>/<repo>/tree/aula-01-calculadora`). Cole esse link no GSA.

