<img alt="Tela 01" src="infografico.png" style="margin: 15px 0" />

# Tokens: A Unidade Fundamental dos Modelos de Linguagem

Modelos de linguagem, como o GPT, não "leem" textos da mesma forma que os seres humanos. Para um computador, processar palavras inteiras diretamente apresenta uma série de problemas estruturais que dificultam o entendimento e a generalização.

Os cinco principais desafios são:

* **Aglutinamento variável:** A forma como as palavras se juntam ou se modificam em diferentes contextos seria complexa de mapear.
* **Vocabulário imenso:** O número de palavras em um idioma é tão grande que seria impraticável criar um dicionário completo e generalizável.
* **Diferentes línguas:** A complexidade de lidar com múltiplos idiomas e suas estruturas únicas simultaneamente seria enorme.
* **Erros de escrita:** Palavras com erros de digitação (typos) seriam tratadas como conceitos totalmente novos e desconhecidos.
* **Novas palavras:** A dificuldade em lidar com neologismos, gírias ou termos técnicos que surgem constantemente seria um obstáculo.

Para superar essas barreiras, os modelos de linguagem não trabalham com palavras, mas com "peças" menores que as formam. Essa abordagem, conhecida como **tokenização**, resolve elegantemente cada um desses desafios.

## A Solução: O Que São Tokens?
Um token é a unidade fundamental com a qual os modelos de linguagem trabalham. Em vez de processar palavras inteiras, o modelo realiza uma "quebra de palavras" em pedaços menores e mais gerenciáveis. Esses tokens podem ser vistos como "pedaços que formam o sentido" do texto.

Essa abordagem oferece muito mais facilidade e flexibilidade para lidar com qualquer tipo de idioma. Veja um exemplo prático de como isso funciona:

> Imagina a palavra **"Bicicleta"**. Para um modelo como o GPT, isso pode não ser uma unidade única, mas sim ser dividida em dois ou mais tokens — que são os "pedaços que formam o sentido" — dependendo de como o modelo foi treinado.



Essa quebra não é aleatória. O token "Bici" pode aparecer em "Bicicleta", "bicicletaria" ou até mesmo em um neologismo como "bicicletar". Ao aprender o significado desses pedaços, o modelo se torna imune a vocabulários imensos e novas palavras, tratando-as como combinações de partes que já conhece.

## Como a Tokenização Funciona na Prática
Os tokens podem ter diferentes formas. Alguns podem ser palavras inteiras, enquanto outros são "conjuntinhos" de caracteres, também conhecidos como sub-palavras.

O critério para definir como o texto será quebrado é aprendido a partir dos dados de treinamento, com base em dois fatores principais:

* **Frequência:** Combinações de caracteres que aparecem com muita frequência nos dados de treinamento tendem a se tornar um único token.
* **Tamanho:** Como regra geral, palavras mais longas e menos comuns são divididas em um número maior de tokens, enquanto palavras curtas e frequentes (como 'e', 'ou', 'um') costumam ser um token único.

Essa mecânica de divisão não é apenas um detalhe técnico; ela tem implicações diretas na forma como interagimos com esses modelos.

## Por Que Isso é Importante para Você: Impacto no Custo e no Contexto
A maneira como um texto é dividido em tokens tem duas consequências diretas e muito importantes para o usuário:

* **Custo Computacional:** Cada token exige processamento. Portanto, quanto mais tokens um texto gera, maior o custo computacional para analisá-lo. Em serviços comerciais (como APIs da OpenAI ou da AWS), isso se traduz diretamente em um custo financeiro maior, pois o faturamento é frequentemente baseado na quantidade de tokens processados.
* **Limitação de Contexto:** Os modelos de linguagem têm uma "janela de contexto", que é a quantidade máxima de texto que conseguem "ler" de uma só vez para entender uma solicitação. Cada token consome uma parte desse espaço limitado, e em muitos serviços (seja na API do GPT, na AWS ou outros), esgotar essa janela pode limitar a capacidade do modelo de considerar todo o contexto fornecido.

Portanto, compreender o que são tokens é fundamental para usar os modelos de linguagem de forma mais eficiente e consciente de seus custos e limitações.

### [Assista ao resumo em vídeo](https://github.com/user-attachments/assets/9424bdb7-2f70-4ca4-a3fb-87b7a32ac985)
