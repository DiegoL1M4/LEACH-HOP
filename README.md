# LEACH-HOP

O LEACH-HOP é um protocolo de clustering que usa o multi-hop em suas operações.

## Fluxograma do Algoritmo
**1-** **(Condicional: Intercluster):** Todos os nós, antes do inicio do primeiro round, vão enviar suas localização à estação base, **gastando energia de transmissão**. Com todas as localizações, a BS mede as distâncias entre os nós e envia os setores de cada um, **gastando energia de recepção**. 

**2-** Todos os nós realizam o cálculo do CH, os que se tornam ficam isolados em uma lista CH. O algoritmo só continua se houver ao menos um CH.

**3-** Todos os CH **gastam energia de transmissão** no envio do pacote de broadcast.

**4-** Os CHs vão receber os pacotes uns dos outros por estarem com o radio ligado, **gastando energia na recepção**.

**5-** Os NCH irão receber os pacotes, **gastando energia de recepção**, e vão escolher o CH mais proximo para ser seu CH.

**6-** Os NCH vão enviar uma resposta ao CH escolhido, **gastando energia de transmissão**.

**7-** Os CH **gastam energia de recepção** do pacote de resposta para cada um dos nós que entrarão no cluster. 

**8-** O CH enviará a tabela TDMA com o slot de tempo de envio, o nó de destino e os slots que o nó necessita ativa o rádio para receber os pacotes, **gastando energia de transmissão** usando a distância máxima do nó mais distante.

**9-** Os NCH **gastam energia de recepção** dos pacotes TDMA.

**10-** Todos os CHs configuram o rádio para alcançar a BS. Já tendo o BS como nó de destino.

**11-** **(Condicional: Intracluster):** seleciona, dentre a lista de nós que foi recebida junto ao TDMA, o nó vizinho mais próximo que esteja em qualquer setor menor. Define o nó como destino.

**12-** **(Condicional: Intercluster):** seleciona, dentre a lista de CH que foi criada com os broadcasts, o CH mais próximo que esteja em qualquer setor menor. Define o CH como destino.

**13-** Inicio da fase dos frames:

   13.1- Todos os NCH **gastam energia de transmissão** de dados para o seu destino escolhido. **(Condicional: Intracluster):** gasta energia de agregação de dados baseado na quantidade de nós que envia dados a ele mais o seu próprio pacote.
   
   13.2- Todos os CH **gastam energia de recepção** baseado na quantidade de nós que envia dados pra ele.
   
   13.3- **(Condicional: Intracluster):** Todos os NCH **gastam energia de recepção** baseado na quantidade de nós que envia dados pra ele.
   
   13.4- Todos os CH enviam seus pacotes para seus destinos, **gastando energia de transmissão**. Quando o intercluster está ativo, o algoritmo identifica o CH de destino, **gasta energia de transmissão** do CH atual e **gasta energia de recepção** do CH destino. O algoritmo assume o CH destino como o atual e realiza o mesmo procedimento até identificar que o destino é a BS, enviando para ela o pacote. Todos os CHs irão realizar esse processo, repassando os pacotes.
   
**14-** Reseta os valores e incrementa o round e o total de frames.
