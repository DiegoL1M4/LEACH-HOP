# LEACH-HOP

O LEACH-HOP é um protocolo de clustering que usa o multi-hop em suas operações.

## Fluxograma do Algoritmo
1- **(Condicional: Intercluster):** Todos os nós, antes do inicio do primeiro round, vão enviar suas localização à estação base. Com todas as localizações, a BS mede as distâncias entre os nós e define os setores de cada um dos nós. Todos os nós **gastam energia enviando e recebendo**. 

2- Todos os nós realizam o cálculo do CH, os que se tornam ficam isolados em uma lista CH. O algoritmo só continua se houver ao menos um CH.

3- Todos os CH **gastam energia de transmissão** no envio do pacote de broadcast.

4- **(Condicional: Intercluster):** Os CHs vão receber os pacotes uns dos outros, **gastando energia na recepção**.

5- Os NCH irão receber os pacotes, **gastando energia de recepção**, e vão escolher o CH mais proximo para ser seu CH.

6- Os NCH vão enviar uma resposta ao CH escolhido, **gastando energia de transmissão**.

7- Os CH **gastam energia de recepção** do pacote de resposta de cada um dos nós que entrarão no cluster. 

8- O CH enviará a tabela TDMA e uma lista com todos os elementos do seu cluster para os membros do seu cluster, **gastando energia de transmissão** com a distância máxima do nó mais distante.

9- Os NCH **gastam energia de recepção** dos pacotes TDMA.

10- Todos os CHs configuram o rádio para alcançar a BS.

11- **(Condicional: Intracluster):** seleciona, dentre a lista de nós que foi recebida junto ao TDMA, o nó vizinho mais próximo que esteja em qualquer setor menor. Define como destino.

12- **(Condicional: Intercluster):** seleciona, dentre a lista de CH que foi criada com os broadcasts, o CH mais próximo que esteja em qualquer setor menor. Define como destino.

13- Inicio da fase dos frames:
   13.1-
   13.2- 
   13.3-

**(Condicional: Intracluster)**
**(Condicional: Intrercluster)**
