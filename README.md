# Flappy Bird com IA (NEAT)

Este projeto é uma implementação do jogo Flappy Bird usando a biblioteca Pygame, com um foco especial no treinamento de uma Inteligência Artificial (IA) para jogar e se tornar invencível utilizando o algoritmo NEAT.

## Tecnologias Utilizadas

- Python 3.x
- Pygame
- NEAT (NeuroEvolution of Augmenting Topologies)

## Objetivo do Projeto

O principal objetivo deste projeto é aplicar técnicas de neuroevolução para treinar uma IA capaz de jogar Flappy Bird de maneira autônoma. A IA aprende a jogar utilizando redes neurais evolutivas, ajustando seus parâmetros ao longo das gerações até atingir um alto desempenho.

## Cálculo para Tomada de Decisão

![image](https://github.com/user-attachments/assets/090bec6d-9f86-45b8-be01-4ba191bc55c3)

A IA aprende a jogar Flappy Bird utilizando um modelo de rede neural evolutiva, onde cada pássaro recebe entradas do ambiente e decide se deve pular ou não com base em um cálculo interno.

### Cálculo para Tomada de Decisão

A IA recebe as seguintes variáveis como entrada para sua rede neural:
 - Altura do pássaro em relação ao solo.
 - Distância horizontal até o próximo cano.
 - Altura do topo do próximo cano (posição do espaço entre os canos).
 - Velocidade vertical do pássaro.
   
A rede neural, definida pelo NEAT, calcula um valor de saída baseado nessas entradas. O cálculo interno segue a estrutura:
![image](https://github.com/user-attachments/assets/3921b616-61ff-49ad-8522-b3d4576f4f84)

Onde:
 - W1, W2, W3, W4 são os pesos aprendidos pela IA para cada entrada X.
 - b é o viés ajustado pela evolução.
 - f é a função de ativação (geralmente uma sigmoide ou ReLU), que decide se o pássaro deve pular ou não.

Se a saída da rede neural for maior que um certo limiar (por exemplo, 0.5), o pássaro pula; caso contrário, ele continua caindo.

### Evolução da IA (NEAT)
 - Inicialmente, os pássaros tomam decisões aleatórias.
 - Cada geração é avaliada pelo tempo de sobrevivência e distância percorrida.
 - Os melhores pássaros passam seus genes (pesos da rede neural) para a próxima geração.
 - Pequenas mutações são introduzidas para melhorar o desempenho ao longo do tempo.

## Instalação

1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/IA_FlappyBird.git
   cd IA_FlappyBird
   ```
2. Instale as dependências:
   ```bash
   pip install pygame neat-python
   ```

## Como Executar

### Para Jogar Manualmente
Para jogar Flappy Bird manualmente, defina a variável ai_jogando = False

### Para treinar a IA
Para iniciar o treinamento da IA com NEAT, defina a variável ai_jogando = True

## Estrutura do Projeto
```
flappy-bird-neat/
│-- imgs/                 # Imagens e sons do jogo
│-- FlappyBird.py         # Implementação do jogo mais ia
│-- config.txt            # Configuração do algoritmo NEAT
│-- README.md             # Documentação do projeto
```

## Configuração do NEAT
O comportamento da IA pode ser ajustado no arquivo `config.txt`, onde é possível modificar parâmetros como número de neurônios, taxa de mutação, tamanho da população e outros.

