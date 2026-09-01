## Tarefa 8 – Seção de Notícias com Tailwind

 A partir da estrutura HTML fornecida (apenas com tags semânticas e conteúdo), você deve adicionar classes Tailwind para reproduzir o layout da imagem de referência (seção de notícias do IFRN).




### Imagem de referência

A imagem mostra uma lista de notícias, cada uma com:
- **Categoria** (ex: "Reunião", "Arte e Cultura", "Jogos Intercampi Estudantis 2026").
- **Título** (em destaque).
- **Descrição** curta.
- **Data** (relativa, ex: "Há 1 hora, 3 minutos").
- **Imagem** (thumbnail) – você deve adicionar imagens placeholder.


### O que fazer?

1. **Adicione classes Tailwind** a todos os elementos para reproduzir o layout da imagem.
   - **Imagens:** devem ter largura total (`w-full`), altura fixa (`h-48` ou similar) e `object-cover` para não distorcer.
   - **Layout:** organize as notícias em um **grid responsivo** (1 coluna em mobile, 2 ou 3 em desktop).
   - **Categoria:** use um badge com fundo verde claro e texto verde escuro.
   - **Data:** texto cinza pequeno, alinhado à direita ou após a categoria.
   - **Título:** verde escuro, negrito, tamanho médio.
   - **Descrição:** cinza, tamanho normal.
   - **Card:** fundo branco, borda arredondada, sombra suave, espaçamento interno.
   - **Efeito hover:** ao passar o mouse, a sombra deve aumentar ou a borda mudar.

2. **Use apenas classes utilitárias** – não crie CSS próprio.
3. **Consulte o cheatsheet** para encontrar as classes adequadas.
4. **Teste a responsividade** redimensionando a janela.


## Classes Tailwind que você provavelmente usará (consulte o cheatsheet)

- Use grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 para o container.
- Para o card: bg-white rounded-xl shadow-md overflow-hidden hover:shadow-xl transition duration-300.
- Para a imagem: w-full h-48 object-cover.
- Para a categoria: inline-block bg-green-100 text-green-800 text-xs font-semibold px-3 py-1 rounded-full.
- Para o título: text-xl font-bold text-green-800 mt-2.
- Para a descrição: text-gray-700 text-sm.
- Para a data: text-gray-500 text-xs.

---

## Passo a passo para execução

1. **Atualize seu fork** do repositório da turma.
2. **Crie uma nova branch** para esta tarefa:  
   ```bash
   git checkout -b atividade-8-noticias
   ```
3. **Insira classes Tailwind** em cada elemento para reconstruir o layout, seguindo as orientações acima.
4. **Adicione a lista de navegação** (links) que não está no código original, conforme imagem (Processos seletivos, Cursos, Campi, Institucional, Acesso à Informação, Eventos, Serviços). 
5. **Commit e push**:
   ```bash
   git add .
   git commit -m "Tarefa 8 - Seção de Notícias com Tailwind"
   git push origin atividade-8-noticias
   ```
6.  **Envie o link da branch** no Google Sala de Aula.

## Dicas

- Use o **Cheatsheet** que foi fornecido para consultar rapidamente as classes.
- Utilize o **Tailwind Play** (https://play.tailwindcss.com/) para testar pequenos trechos.