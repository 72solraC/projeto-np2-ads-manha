
# Semana de Provas — Introdução prática a Árvores e Grafos (Python)

Este pacote contém **duas miniatividades** simples, pensadas para computadores modestos e para turmas heterogêneas. Não há dependências externas além da biblioteca padrão do Python (Tkinter já vem com o Python no Windows).

## Estrutura
```
prova_intro_arvores_grafos/
  arvore/
    app_tree.py         # interface Tkinter travada (NÃO alterar)
    tree_logic.py       # <-- você edita AQUI (implementar navigate_tree)
  grafo/
    app_graph.py        # interface Tkinter travada (NÃO alterar)
    graph_logic.py      # <-- você edita AQUI (implementar connected)
  run_tree.bat
  run_graph.bat
  README.md
```
> Recomendação: usar **Python 3.10+** no Windows.

## Como rodar (Windows)
1. Extraia o `.zip` para uma pasta local (por exemplo, Área de Trabalho).
2. Clique duas vezes em `run_tree.bat` (Árvore) ou `run_graph.bat` (Grafo).  
   (Ou use o Prompt de Comando e rode `python arvore/app_tree.py` e `python grafo/app_graph.py`.)

---

## Atividade 1 — Árvore de Decisão (básica)

**Objetivo:** entender o papel de uma árvore binária para *tomar decisões hierárquicas*.  
**O que fazer:** abrir `arvore/tree_logic.py` e implementar a função `navigate_tree(node, answers)`.

- A interface mostra um pequeno **classificador de animais**.
- Você digita uma sequência de respostas (`sim`/`não`) e a UI mostra a **decisão final**.
- **Não altere** `app_tree.py`.

### Exemplo de respostas
- `sim, não` (ou `sim nao`) → percorre “voa?” → *sim* → “é noturno?” → *não* → resultado.

---

## Atividade 2 — Rede de Contatos (grafo)

**Objetivo:** entender que grafos modelam relações e que uma busca simples encontra conexões.  
**O que fazer:** abrir `grafo/graph_logic.py` e implementar a função `connected(graph, a, b)`.

- A interface desenha um **grafo de amizades** simples.
- Você digita dois nomes (`A` e `B`) e o app responde se há **algum caminho** ligando os dois.
- **Não altere** `app_graph.py`.

---

## Regras e Orientações
- **Entrega máxima (10 pts)** está detalhada abaixo. A **média** para aprovação é **5**.
- Você pode usar IA como apoio, **mas explique** no final o que você aprendeu.
- Código deve rodar sem erros, apenas com Python padrão.
- Não crie novas dependências, não altere as interfaces Tkinter.

---

## Rubrica de Avaliação (total 10 pts)

### Parte Árvore — 5.0 pts
1. **Lógica de navegação correta (3.0 pts):**
   - Percorre a árvore da raiz até um **nó folha** com base em `answers` (lista de strings `"sim"`/`"não"` — aceitar variações como `nao`, espaços e maiúsculas/minúsculas).
   - Retorna a **decisão final** (string) quando a folha é alcançada.
   - Lida com sequências mais curtas/longas de forma **amigável** (ver mensagens da UI).
2. **Tratamento básico de erros (1.0 pt):**
   - Se a resposta não for reconhecida (`"talvez"`, vazio etc.), levanta `ValueError` com mensagem curta e clara.
3. **Clareza do código (1.0 pt):**
   - Comentários concisos explicando a estratégia.
   - Nomes de variáveis legíveis.
   - Sem alterar a interface.

### Parte Grafo — 4.0 pts
1. **Busca de conectividade correta (3.0 pts):**
   - Implementar uma **busca** (BFS com fila **ou** DFS) que verifica se existe um **caminho** entre `a` e `b`.
   - Considerar grafos **não direcionados** conforme a estrutura fornecida (listas de adjacência).
   - Ignorar diferenças de maiúsculas/minúsculas (normalizar nomes) **ou** documentar que são sensíveis a caso (mas manter consistente).
2. **Tratamento básico de erros (1.0 pt):**
   - Se um vértice não existir, retornar `False` **ou** levantar `ValueError` com mensagem clara (a interface lida com ambas).

### Relato de Aprendizagem — 1.0 pt
- Ao final, escreva 3–5 linhas explicando:
  - O que é uma **árvore de decisão** e **para que serve**.
  - O que é um **grafo** e um exemplo do cotidiano (rotas, redes sociais, etc.).
  - Onde a IA te ajudou e o que você conseguiu **entender de verdade**.

> **Nota de corte:** a média é **5,0**.  
> Exemplos de composições de nota que **aprovam**: Árvore 3.5 + Grafo 1.5 + Relato 0 = 5.0; ou Árvore 2.5 + Grafo 2.5 + Relato 0.5 = 5.5.

---

## Dicas
- Comece pela **árvore** (mais curto).
- No grafo, experimente **imprimir** uma fila/stack para ver a ordem de visita.
- Teste nomes que **não** estão no grafo para validar tratamento de erros.

Bom trabalho! :)
