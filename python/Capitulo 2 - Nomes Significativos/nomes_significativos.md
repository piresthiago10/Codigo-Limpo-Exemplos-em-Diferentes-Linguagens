# Capítulo II - Nomes Significativos

Há nomes por todos os lados em um software: variáveis, funções, parâmetros, classes, pacotes, arquivos e diretórios é necessário que todos estes estevam bem nomeados, e para isso existem algumas regras.

**Use nomes que Revelem seu propósito**, escolher bons nomes leva tempo e leva a economia de tempo, sempre que possível troque os por melhores. Os nomes de veriáveis, funções e classes devem devem responder porque existe, o que faz e como é usado. O uso de comentários demontra uma falha no propósito de nomear a variável.

```
d = 0  # decorrido em dias
```
O nome d não revela nada, não dá ideia de tempo, se for utilizado em outra parte do código será difícil identificar seu propósito.

```
elapsed_time_in_days = 0
days_since_creation = 0
days_since_modification = 0
file_age_in_days = 0
```
Escolher bons nomes ajudam no entendimento do código, já o oposto dificulta seu entendimento. Veja o exemplo abaixo:

```
def get_them():
    list1 = []
    for x in the_list:
        if x[0] == 4:
            list1.append(x)
    return list1 
```
É difícil entender o que o código faz, apesar do python obrigar o uso de identação e o código ser simples o contexto não está explícito. Para poder enteder devemos ter respostas de perguntas como:

1. Que tipo de coisas estão em the_list?
2. Qual a importância de um item na posição zero na the_list?
3. Qual a importância do valor 4?
4. Como eu usaria a lista retornada?

Se abstrairmos o código como parte do jogo *campo minado*, the_list é o tabuleiro com uma lista de células, logo podemos chamá-la de game_board, cada quadrado do tabuleiro é um vetor simples, na posição zero é armazenada um valor de estatus e que 4 significa "marcado com uma bandeirinha". Com nomes siginificativos o contexto do código fica óbvio.
```
def get_flagged_cells():
    flagged_cells = []
    for cell in game_board:
        if cell[STATUS_VALUE] == FLAGGED:
            flagged_cells.append(cell)
    return flagged_cells 
```
A simplicidade do código continuou a mesma, com o mesmo número de variáveis, as mesmas estruturas de dados e operados, a diferença está em simples alterações de nomes que permitiram mais facílmente o que está acontecendo.