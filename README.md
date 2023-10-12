# Dupla: Rafael Augusto Vilella de Albuquerque Lins e Guilherme Oliveira

# Sorting-Station

## Descrição do problema:

O projeto consiste na implementação de um sistema Ladder por meio do Software [Siemens's TIA Portal V15](https://support.industry.siemens.com/cs/document/109745155/simatic-step-7-including-plcsim-v13-sp2-trial-download?dti=0&lc=en-WW) para a resolução de uma das cenas predefinidas do Software [Factory IO](https://factoryio.com/) "Sorting-Station" . O problema em questão consiste sem separar objetos em função de suas cores.

<p align="center">
<img src=>
</p>

<p align="center"> 
<b>Figura 1:</b> Sorting Station.
</p>

Para esse cenário, temos três cores possíveis: Azul, Verde e Cinza. Essas cores são detectadas por um sensor que aciona os separadores, assegurando que cada objeto seja direcionado para a rampa correspondente. Abaixo está a ilustração do sensor.

<p align="center">
<img src=>
</p>

<p align="center"> 
<b>Figura 2:</b> Sensor.
</p>

O processo é iniciado ao pressionar o botão verde e interrompido ao pressionar o botão vermelho, ambos localizados no painel do CLP. Abaixo está a representação do painel.

<p align="center">
<img src=>
</p>

<p align="center"> 
<b>Figura 3:</b> Painel do CLP.
</p>

## Descrição da implementação lógica Realizada:

A implementação pode ser dividida em duas partes distintas. A primeira parte envolve o acionamento e controle do sistema. Por meio do controle do painel, podendo inicia-lo por meio do botão start, e podendo parar com o stop.

A segunda parte compreende o sensor que será responsável por identificar a cor de cada um dos objetos e acionar o comportamento correto. A tabela a seguir mostra a correspondência entre os valores inteiros e as cores:

| Inteiro     | Cor |
| :--------:  | :-------:|
| 1-3           |  Azul    |
| 4-6           |  Verde   |
| 7-8           |  Cinza   |

Dessa forma, o sistema é projetado para atuar de acordo com os valores inteiros detectados, acionando os separadores correspondentes para classificar os objetos de acordo com suas cores.

A visão esquemática dos blocos lógicos podem ser vizualidas [aqui]().

## Tabela de endereçamento: 

| Endereço    | Tag            | Tipo |
| :--------:  |:-------:       |:----:|
| %I0.0       | At exit        | Bool |
| %I0.1       | Start          | Bool |
| %I0.2       | Reset          | Bool |
| %I0.3       | Stop           | Bool |
| %I0.4       | Emergency stop | Bool |
| %I0.5       | Auto           | Bool |
| %I0.6       | Manual         | Bool |
| %Q0.0       | Entry conveyor | Bool |
| %Q0.1       | Stop blade     | Bool |
| %Q0.2       | Exit conveyor  | Bool |
| %Q0.3       | Sorter 1 turn  | Bool |
| %Q0.4       | Sorter 1 belt  | Bool |
| %Q0.5       | Sorter 2 turn  | Bool |
| %Q0.6       | Sorter 2 belt  | Bool |
| %Q0.7       | Sorter 3 turn  | Bool |
| %Q1.0       | Sorter 3 belt  | Bool |
| %Q1.1       | Start light    | Bool |
| %Q1.2       | Reset light    | Bool |
| %Q1.3       | Stop light     | Bool |
| %QD30       | Counter 1      | DInt |
| %QD34       | Counter 2      | DInt |
| %QD38       | Counter 3      | DInt |
| %ID30       | Vision sensor  | DInt |
| %QB0        | Digital output Byte 0 | Byte |
| %QB1        | Digital output Byte 1 | Byte |
| %MB0        | Clock_byte     | Byte |
| %M0.0       | Clock_10Hz     | Bool |
| %M0.1       | Clock_5Hz      | Bool |
| %M0.2       | Clock_2.5Hz    | Bool |
| %M0.3       | Clock_2Hz      | Bool |
| %M0.4       | Clock_1.25Hz   | Bool |
| %M0.5       | Clock_1Hz      | Bool |
| %M0.6       | Clock_0.625Hz  | Bool |
| %M0.7       | Clock_0.5Hz    | Bool |

## Resultado:

O vídeo abaixo mostra o processo automatizado em execução.

