# Brasil Prev
Clone este repositório, rode o comando `pip install requirements.txt` para instalar as dependências do projeto (é recomendável rodar
`pip install --upgrade pip` antes).

Os testes podem ser executados por `python -m unittest test_regras.py`.

O resultado do exercício se obtém ao executar o comando `python main.py `

Abaixo segue um resultado da execução como exemplo:

Timeouts: 289

Média de turnos - 965.18

Percentual de vitórias por perfil
{'impulsivo': 43.333333333333336, 'exigente': 53.0, 'cauteloso': 2.0, 'aleatorio': 2.0}


Maior vencedor - exigente (159 vitórias)

## O Desafio
Considere o seguinte jogo hipotético muito semelhante ao Banco Imobiliário, 
onde várias das suas mecânicas foram simplificadas. 
Numa partida desse jogo, os jogadores se alteram em rodadas, numa
ordem definida aleatoriamente no começo da partida. Os jogadores sempre começam
uma partida com saldo de 300 para cada um.


Nesse jogo, o tabuleiro é composto por 20 propriedades em sequência. Cada propriedade tem
um custo de venda, um valor de aluguel, um proprietário caso já estejam compradas, e seguem
uma determinada ordem no tabuleiro. Não é possível
construir hotéis e nenhuma outra melhoria sobre as propriedades do tabuleiro, por
simplicidade do problema.

No começo da sua vez, o jogador joga um dado equiprovável de 6 faces que determina
quantos espaços no tabuleiro o jogador vai andar.

+ Ao cair numa propriedade sem proprietário, o jogador pode escolher entre
comprar ou não a propriedade. Esse é a única forma pela qual uma propriedade
pode ser comprada.

+ Ao cair numa propriedade com proprietário, ele deve pagar ao proprietário o valor do
aluguel da propriedade.

+ Ao completar uma volta no tabuleiro, o jogador ganha 100 de saldo.

Jogadores só podem comprar propriedades caso ela não tenha dono e o jogador
tenha o dinheiro da venda. Ao comprar uma propriedade, o jogador perde o
dinheiro e ganha a posse da propriedade.

Cada um dos jogadores tem uma implementação de comportamento diferente,
que dita as ações que eles vão tomar ao longo do jogo. Mais detalhes sobre o
comportamento serão explicados mais à frente.

Um jogador que fica com saldo negativo perde o jogo, e não joga mais. 
Perde as suas propriedades, portanto, podem ser compradas por qualquer outro jogador.

Termina quando restar somente um jogador com saldo positivo, a
qualquer momento da partida. Esse jogador é declarado o vencedor.

Desejamos rodar uma simulação para decidir qual a melhor estratégia.
Para isso, idealizamos uma partida com 4 diferentes tipos de
jogadores. Os comportamentos definidos são:

+ O jogador um é impulsivo;

+ O jogador dois é exigente;

+ O jogador três é cauteloso;

+ O jogador quatro é aleatório;

O jogador *impulsivo* compra qualquer propriedade sobre a qual ele parar.

O jogador *exigente* compra qualquer propriedade, desde que o valor do aluguel dela seja
maior que 50.

O jogador *cauteloso* compra qualquer propriedade desde que ele tenha uma
reserva de 80 saldo sobrando após realizada a compra.

O jogador *aleatório* compra a propriedade que ele parar em cima com
probabilidade de 50%.

Caso o jogo demore muito, como é de costume em jogos dessa natureza, o jogo
termina na milésima rodada com a vitória do jogador com mais saldo. O critério
de desempate é a ordem de turno dos jogadores nesta partida.
