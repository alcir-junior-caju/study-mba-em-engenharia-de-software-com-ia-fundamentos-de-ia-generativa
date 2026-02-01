<img alt="Tela 01" src="infografico.png" style="margin: 15px 0" />

# O que é a Janela de Contexto em IA? Um Guia para Iniciantes

## 1. Introdução: A Memória de Curto Prazo da IA
Imagine que você está no meio de uma conversa. Sua capacidade de responder de forma coerente depende do que foi dito nos últimos minutos. A **Janela de Contexto** de um modelo de Inteligência Artificial funciona de maneira muito parecida: ela é a memória de curto prazo da IA, limitando a quantidade de informações que ela consegue reter de uma vez para manter o "diálogo".

Formalmente, a **Janela de Contexto (Context Window)** é o número máximo de *tokens* (pedaços de palavras) que um modelo de IA pode processar de uma só vez.

> *Para gerar uma continuação lógica, "o modelo pega um token e tenta prever o próximo", olhando para trás, para a informação contida dentro dessa janela, para entender o que foi dito e prever o que virá a seguir.*

Entender essa limitação é fundamental para compreender como os modelos de linguagem funcionam.



## 2. O Limite da "Memória": Por Que a Janela de Contexto Importa?
O conceito mais importante sobre a janela de contexto é que ela **não é infinita**. Embora os modelos de IA estejam evoluindo rapidamente para processar cada vez mais informações, todos eles possuem um "teto" — uma limitação física e lógica de quantos tokens conseguem considerar simultaneamente.

A evolução dos modelos de linguagem ilustra bem esse avanço:
* **GPT-3.5:** Possuía uma janela de contexto mais restrita.
* **GPT-4 Turbo:** Aumentou significativamente essa capacidade, permitindo processar muito mais informação de uma vez.

A principal lição aqui é que, mesmo com o avanço da tecnologia, a existência de um limite é uma regra universal.

## 3. Os 3 Principais Desafios de uma Janela de Contexto Grande
Embora uma janela de contexto maior pareça sempre melhor, na prática, ela introduz três desafios importantes que afetam a precisão, o custo e a velocidade do modelo.

### 1. Falhas no Mecanismo de Atenção ("Lost in the Middle")
O mecanismo de "atenção" é o que permite que o modelo identifique quais partes do texto são mais relevantes. Embora poderoso, não é perfeito. Em textos muito longos, o modelo pode começar a ter falhas na recuperação de informações.
* **O Fenômeno:** O modelo tende a "esquecer" ou dar menos importância a informações que estão no meio de um contexto muito extenso.

### 2. O Viés de Recência (Foco no Final do Texto)
Os modelos de IA geralmente apresentam um "Viés de Recência", o que significa que eles tendem a dar mais peso e importância aos tokens mais recentes. O que foi lido por último tem um impacto maior na resposta.

> **💡 Dica Prática de Engenharia de Prompt:**
> Se você precisar usar um prompt muito grande, **deixe as instruções cruciais ou a pergunta final para o final do texto**. Se a instrução mais importante for colocada no início de um texto gigante, ela corre o risco de se "diluir" e ser ignorada.

### 3. Custo Computacional e Desempenho
Aumentar a janela de contexto tem consequências diretas em recursos, criando um *trade-off* inevitável:

| Fator | Impacto |
| :--- | :--- |
| **Recursos** | Exige muito mais poder computacional (VRAM/GPU). |
| **Custo** | Aumenta significativamente o custo de operação por chamada. |
| **Latência** | Torna o modelo mais lento para processar a entrada e gerar uma resposta. |

## 4. Conclusão: O Essencial sobre a Janela de Contexto
Para um iniciante no mundo da IA, compreender a janela de contexto se resume a três ideias centrais:

1.  **É uma memória limitada:** Todo modelo tem um limite de quanta informação consegue "lembrar" de uma vez.
2.  **O final importa mais:** Devido ao viés de recência, as instruções mais importantes devem ir no final.
3.  **Existe um custo:** Janelas maiores significam mais poder, mas também maior custo financeiro e maior tempo de resposta.

Dominar esses conceitos é o primeiro passo para usar a IA de forma mais inteligente.

### [Assista ao resumo em vídeo](https://github.com/user-attachments/assets/d7c38a87-3a17-4082-b00f-a4485cfbd43a)
