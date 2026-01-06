<img alt="Tela 01" src="infografico.png" style="margin: 15px 0" />

# Desvendando o Feedforward: A "Conversa Individual" de Cada Token

## 1. Introdução: O Processamento Individual Pós-Atenção
Em um modelo Transformer, depois que os tokens passam pelo mecanismo de **Atenção (Multi-Head)** — uma fase colaborativa onde eles "olham uns para os outros" para entender o contexto — eles entram em uma nova etapa: a camada **Feedforward**.

A diferença entre essas duas fases é fundamental. Enquanto a atenção serve para misturar as informações, permitindo que cada token se enriqueça com o contexto dos seus vizinhos, a camada Feedforward muda completamente a dinâmica. Aqui, a lógica é aplicada de forma independente e isolada para cada token. Esta é a etapa do "processamento individual", onde cada palavra tem a chance de "refletir" sobre o que aprendeu.

Para entender como essa reflexão solitária funciona, vamos usar uma analogia simples e poderosa.

## 2. A Analogia Central: A Conversa Individual
A melhor forma de visualizar o processamento independente da camada Feedforward é imaginá-la como uma conversa entre duas pessoas.

> *"Imagina que eu estou falando com você. Mesmo que a gente esteja na mesma conversa, você é um componente e eu sou outro. O que você vai reter de informação é diferente do que eu vou reter."*

Assim como em um diálogo, embora todos os tokens compartilhem o mesmo contexto geral (a "conversa"), cada um processa essa informação de maneira única. Essa interpretação particular é moldada por um conjunto de pesos exclusivo (as matrizes $W_1, W_2, b_1$ e $b_2$ que veremos a seguir), garantindo que cada token desenvolva uma compreensão refinada antes de seguir adiante.

Agora, vamos mergulhar nos detalhes técnicos de como essa "conversa individual" realmente acontece.



## 3. A Jornada de um Token: O Processo em 3 Passos
Cada token, de forma isolada, embarca em uma jornada de três passos dentro da camada Feedforward. Lembre-se: ao contrário da camada de atenção, onde os tokens interagiam, esta jornada é completamente solitária. Ela serve para transformar a informação contextualizada que ele recebeu da etapa anterior.

### 3.1. Passo 1: Expansão e Reflexão (Primeira Transformação Linear)
A jornada começa com uma transformação matemática:
$$x \cdot W_1 + b_1$$
Nesta etapa, o modelo pega a informação contida no token e a expande, projetando-a para um espaço de maior dimensão. Essa expansão dá ao modelo mais "espaço de manobra" para identificar e aprender relações não-lineares complexas entre as características do token, algo que seria mais difícil em sua dimensão original. O termo $b_1$ atua como um "ajuste fino" inicial nesta etapa de expansão.

### 3.2. Passo 2: O Filtro de Relevância (Ativação ReLU)
Após a expansão, a informação passa por um filtro crucial. Esse filtro é uma função de ativação chamada **ReLU (Rectified Linear Unit)**, que aplica uma regra matemática simples:
$$f(x) = max(0, x)$$
Sua função é decidir o que é relevante para seguir adiante. Se um valor resultante da expansão for positivo, ele é mantido; se for negativo (considerado irrelevante), ele é simplesmente zerado. É um mecanismo de seleção que mantém apenas os sinais mais fortes e úteis.

### 3.3. Passo 3: Condensação e Ajuste Final (Segunda Transformação Linear)
Finalmente, a informação que sobreviveu ao filtro passa por uma segunda transformação linear:
$$resultado\_filtrado \cdot W_2 + b_2$$
O objetivo aqui é o oposto do primeiro passo: pegar as características relevantes e filtradas e condensá-las de volta, ajustando o token para sua forma final. O termo $b_2$ fornece o "ajuste fino" final antes que o resultado seja enviado para a próxima camada do modelo.

Esses três passos garantem que cada token processe a informação contextual de maneira profunda e individualizada.

## 4. Resumo Técnico: O Ciclo de Processamento Individual
O fluxo completo que ocorre localmente para cada token pode ser resumido de forma concisa:

* **Expande/Evolui:** A informação do token é repensada e ampliada para explorar novas características.
* **Filtra:** Apenas as informações mais relevantes são mantidas, enquanto o que é considerado ruído ou irrelevante é zerado.
* **Condensa:** A informação filtrada é consolidada em um resultado final, pronto para a próxima etapa.

É essa combinação de entendimento contextual (da Atenção) com um processamento individual que é igualmente robusto (do Feedforward) que confere aos modelos Transformer sua impressionante capacidade.

### [Assista ao resumo em vídeo](https://github.com/user-attachments/assets/9251cac4-66c9-47f1-98f4-0f10f1577433)
