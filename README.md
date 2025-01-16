# 🐍 Snake Game com Aprendizado por Reforço 💡

<p align="center">
  <a href="https://github.com/Edu-png">
    <img src="https://img.shields.io/badge/Autor-Eduardo%20Coqueiro-purple?style=flat&logo=github" alt="Autor">
  </a>
  <a href="mailto:eduardocoqueiro@gmail.com">
    <img src="https://img.shields.io/badge/Email-eduardocoqueiro%40gmail.com-purple?style=flat&logo=gmail" alt="Email">
  </a>
  <a href="https://linkedin.com/in/eduardocoqueiro/">
    <img src="https://img.shields.io/badge/LinkedIn-Eduardo%20Coqueiro-purple?style=flat&logo=linkedin" alt="LinkedIn">
  </a>
</p>

![CAPAS - PROJETOS (5)](https://github.com/user-attachments/assets/24de7a7c-c747-4bfb-a1b0-6f742e59e8ed)

## Sumário 🎯

- [🐍 Snake Game com Aprendizado por Reforço 💡](#-snake-game-com-aprendizado-por-reforço-)
  - [Resumo 📄](#resumo-)
  - [Objetivo 🎯](#objetivo-)
  - [Estrutura do Projeto 🛠](#estrutura-do-projeto-)
  - [Introdução ☀](#introdução-)
  - [Pipeline do Projeto 🛠](#pipeline-do-projeto-)
  - [Metodologia 🧪](#metodologia-)
  - [Resultados e Conclusões 📈](#resultados-e-conclusões-)
    - [Vídeo Inicial: Movimentos Aleatórios 🎥](#1-vídeo-inicial-movimentos-aleatórios-)
    - [Progresso do Treinamento](#2-progresso-do-treinamento)
    - [Vídeo Final: Agente Após 1000+ Tentativas 🎥](#3-vídeo-final-agente-após-1000-tentativas-)
    - [Conclusões 🚀](#conclusões-)
  - [Considerações Finais 🚀](#considerações-finais-)
  - [Agradecimentos 👏](#agradecimentos-)
  - [📞 Contato](#-contato)


## Resumo 📄

Este projeto combina o clássico jogo da cobra com conceitos de aprendizado por reforço, utilizando redes neurais e técnicas de treinamento. A meta é treinar um agente de IA capaz de maximizar a pontuação no jogo de forma autônoma. Através do uso de bibliotecas como `Pygame`, `PyTorch` e `Numpy`, exploramos conceitos como:

- Redes neurais simples para tomada de decisão.
- Exploração e exploração durante o treinamento.
- Técnicas de otimização como gradient descent e backpropagation.
- Visualização de resultados com gráficos de desempenho.

---

## Objetivo 🎯

O objetivo principal do projeto é:

1. **Criar uma IA para o Snake Game:** Desenvolver um agente que aprenda a maximizar a pontuação, utilizando aprendizado por reforço.
2. **Explorar Algoritmos de Aprendizado:** Implementar uma rede neural que avalia estados do jogo e decide ações com base em recompensas.
3. **Visualizar Progresso:** Monitorar o desempenho do agente durante o treinamento com gráficos de pontuação.
4. **Documentar o Processo:** Fornecer insights e etapas claras sobre a implementação, desafios e lições aprendidas.

---

## Estrutura do Projeto 🛠

- **Jogabilidade Manual:** Baseada em `snake_game_human.py` para jogadores humanos.
- **Jogabilidade Automatizada com IA:** Utilizando `snake_game_ML.py` e a classe `Agent`.
- **Modelo e Treinamento:** Arquivo `model.py` com definição de rede neural e `agent.py` para lógica de treinamento.
- **Visualização:** Utilizando `helper.py` para gráficos interativos de progresso.
- **Pipeline Completo:** Desde o treinamento até a execução do agente no jogo.

---
## Introdução ☀

Este projeto combina o clássico Snake Game com inteligência artificial, utilizando aprendizado por reforço para treinar um agente que joga de forma autônoma. A implementação envolve o uso de uma rede neural criada com `PyTorch` para avaliar estados do jogo e tomar decisões estratégicas, enquanto o ambiente gráfico é gerenciado pelo `Pygame`. Por meio de recompensas e penalidades, o agente aprende a maximizar sua pontuação ao longo de várias partidas, destacando conceitos como exploração versus exploração, ajuste de pesos na rede neural e otimização baseada em gradientes. Este trabalho demonstra a aplicação prática de algoritmos de IA em um problema clássico, proporcionando insights valiosos sobre aprendizado por reforço.

## Pipeline do Projeto 🛠

A estrutura do projeto foi organizada para treinar uma IA capaz de jogar o Snake Game de forma autônoma, com as seguintes etapas principais:

1. **Configuração do Ambiente de Jogo:** Criação de um ambiente gráfico interativo utilizando `Pygame`.
2. **Definição da IA:** Implementação de uma rede neural simples com `PyTorch` para avaliar estados e tomar decisões.
3. **Treinamento do Agente:** Uso de aprendizado por reforço para ajustar os pesos da rede neural, maximizando as recompensas.
4. **Monitoramento de Desempenho:** Visualização da evolução da pontuação através de gráficos interativos.
5. **Automação do Jogo:** Integração do agente treinado com o ambiente para jogar sem intervenção humana.

## Metodologia 🧪

O desenvolvimento do projeto seguiu uma abordagem estruturada e iterativa, com as seguintes etapas detalhadas:

### 1. **Configuração do Ambiente de Jogo**
- **Biblioteca Utilizada:** `Pygame` foi a base para criar o ambiente gráfico e simular o jogo Snake.
- **Desenvolvimento do Jogo Manual:** Um jogo inicial foi implementado (`snake_game_human.py`) para simular a jogabilidade manual, permitindo interações básicas do jogador.
- **Componentes do Jogo:**
  - Movimento da cobra em quatro direções (cima, baixo, esquerda, direita).
  - Geração de alimentos em posições aleatórias.
  - Detecção de colisões com as bordas ou o próprio corpo.

---

### 2. **Definição da IA e Função de Recompensa**
- **Modelo da Rede Neural:**
  - Arquivo `model.py` com a definição de uma rede neural simples (camadas lineares) implementada em `PyTorch`.
  - A arquitetura da rede possui três camadas: entrada (estado do jogo), oculta e saída (ações possíveis: virar à esquerda, continuar reto ou virar à direita).
- **Estados e Ações:**
  - Representação do estado do jogo em um vetor de 11 elementos que inclui:
    - Perigos próximos (frente, esquerda, direita).
    - Direção atual da cobra.
    - Posição relativa do alimento.
  - Ações possíveis:
    - Manter a direção atual.
    - Virar à esquerda.
    - Virar à direita.
- **Função de Recompensa:**
  - +10 pontos por comer o alimento.
  - -10 pontos ao colidir com bordas ou com o próprio corpo.
  - Penalidades menores para movimentos ineficazes.

---

### 3. **Treinamento do Agente**
- **Treinamento de Memória Curta e Longa:**
  - Implementação do agente no arquivo `agent.py` utilizando `deque` para armazenar memórias de jogadas anteriores.
  - Treinamento de memória curta (após cada jogada) e longa (em lotes maiores) para ajustar os pesos da rede neural.
- **Exploração e Exploração:**
  - Decisão probabilística entre explorar novas ações ou explorar ações conhecidas (definido pela taxa de exploração `epsilon`).
- **Algoritmo de Otimização:**
  - Uso de `Adam Optimizer` para minimizar o erro na previsão de recompensas futuras.
  - A função de perda utilizada foi `MSELoss`.

---

### 4. **Automação do Jogo**
- **Execução da IA no Jogo:**
  - O agente treinado foi integrado ao ambiente (`snake_game_ML.py`) para jogar de forma autônoma, tomando decisões com base nos estados do jogo e na política aprendida.
- **Limitação de Iterações:**
  - Para evitar loops infinitos, foi implementada uma limitação no número de frames sem progresso.

---

### 5. **Visualização e Monitoramento**
- **Gráficos de Progresso:**
  - O arquivo `helper.py` foi utilizado para gerar gráficos interativos que mostram:
    - A pontuação de cada jogo.
    - A pontuação média ao longo do tempo.
  - Esses gráficos foram atualizados em tempo real durante o treinamento.
- **Métricas de Desempenho:**
  - Comparação da maior pontuação alcançada pelo agente em relação ao progresso geral.
  - Monitoramento da consistência do aprendizado através da média de pontuação.

---

### 6. **Aprimoramentos e Testes**
- **Validação do Modelo:**
  - Testes foram realizados com diferentes configurações de hiperparâmetros (taxa de aprendizado, taxa de exploração, e arquitetura da rede).
- **Iterações de Treinamento:**
  - Várias partidas foram simuladas até que o agente mostrasse um desempenho consistente e otimizado.
- **Aprimoramento da Função de Recompensa:**
  - Penalidades e recompensas foram ajustadas para incentivar o agente a adotar estratégias mais eficazes.

---

### Ferramentas e Bibliotecas
- **Pygame:** Para criar o ambiente gráfico e simular o jogo.
- **PyTorch:** Para a implementação e treinamento da rede neural.
- **Numpy:** Para operações matemáticas e manipulação de dados.
- **Matplotlib:** Para criar gráficos interativos e visualizar o progresso.

Essa metodologia detalha como o projeto foi implementado, treinado e avaliado, cobrindo desde a configuração inicial até as iterações finais de aprimoramento.

## Resultados e Conclusões 📈

Os resultados do projeto demonstram a eficácia do aprendizado por reforço na automação do Snake Game. O agente inicialmente apresentava movimentos aleatórios e ineficientes, mas, com o passar do treinamento, começou a tomar decisões mais inteligentes, aumentando sua pontuação de forma consistente. 

### 1. Vídeo Inicial: Movimentos Aleatórios 🎥
*Este vídeo mostra o comportamento da cobra antes do treinamento significativo, onde ela colide rapidamente devido à ausência de estratégias.*

[Espaço reservado para o vídeo inicial]

---

### 2. Progresso do Treinamento
Os gráficos e imagens a seguir ilustram o progresso do agente em diferentes estágios de treinamento:

#### Após 50 Tentativas
[Espaço reservado para imagem da cobra após 50 tentativas]

#### Após 100 Tentativas
[Espaço reservado para imagem da cobra após 100 tentativas]

#### Após 300 Tentativas
[Espaço reservado para imagem da cobra após 300 tentativas]

#### Após 700 Tentativas
[Espaço reservado para imagem da cobra após 700 tentativas]

#### Após 1000 Tentativas
[Espaço reservado para imagem da cobra após 1000 tentativas]

---

### 3. Vídeo Final: Agente Após 1000+ Tentativas 🎥
*Este vídeo mostra o agente jogando de forma otimizada, com decisões rápidas e estratégias eficazes para evitar colisões e maximizar a pontuação.*

[Espaço reservado para o vídeo final]

---

### Conclusões 🚀

1. **Aprendizado Progressivo:** 
   - O agente apresentou uma curva de aprendizado clara, passando de movimentos aleatórios para estratégias otimizadas após 1000 tentativas.

2. **Impacto da Função de Recompensa:** 
   - Ajustes na função de recompensa foram cruciais para incentivar o agente a adotar comportamentos mais eficazes, como evitar colisões e buscar alimentos.

3. **Visualização do Progresso:**
   - Os gráficos demonstraram uma melhoria consistente na pontuação média ao longo do tempo, indicando um treinamento eficaz.

4. **Próximos Passos:**
   - Explorar arquiteturas de rede mais complexas.
   - Implementar uma interface gráfica mais interativa e detalhada.
   - Adicionar métricas para medir a eficiência energética do agente (número de movimentos por alimento).

Com essas conclusões, o projeto demonstra como conceitos teóricos de aprendizado por reforço podem ser aplicados a problemas práticos, gerando resultados significativos e proporcionando insights sobre inteligência artificial.

## Considerações Finais 🚀

Este projeto demonstrou a aplicação prática do aprendizado por reforço em um ambiente simulado, como o Snake Game, explorando conceitos fundamentais de inteligência artificial e otimização. Através do desenvolvimento e treinamento do agente, foram alcançados resultados significativos, destacando a evolução progressiva do comportamento da IA ao longo de várias tentativas.

### Pontos de Destaque:
1. **Evolução do Agente:** 
   - O agente evoluiu de movimentos aleatórios para estratégias inteligentes, demonstrando a capacidade do aprendizado por reforço em adaptar-se a desafios e melhorar seu desempenho.
2. **Flexibilidade e Escalabilidade:** 
   - A implementação, baseada em bibliotecas robustas como `PyTorch` e `Pygame`, oferece uma base sólida para expandir o projeto com arquiteturas de rede mais avançadas ou novos ambientes de teste.
3. **Visualização e Monitoramento:** 
   - A utilização de gráficos para monitorar o progresso do treinamento foi fundamental para entender os avanços e ajustar os parâmetros do modelo.

### Limitações e Melhorias Futuras:
1. **Simplicidade do Modelo:** 
   - A rede neural utilizada é relativamente simples, podendo ser substituída por modelos mais sofisticados para explorar padrões complexos no ambiente.
2. **Exploração de Hiperparâmetros:** 
   - Estudos mais aprofundados sobre hiperparâmetros, como taxa de aprendizado e gama de desconto, podem levar a um treinamento mais eficiente.
3. **Ambiente Simples:** 
   - O Snake Game apresenta um ambiente estático e previsível. Projetos futuros podem incorporar ambientes dinâmicos ou multijogadores para aumentar a complexidade do aprendizado.

### Impacto e Aprendizados:
Este projeto evidenciou como um problema clássico de jogo pode ser transformado em um desafio de aprendizado por reforço, proporcionando não apenas resultados práticos, mas também um aprendizado valioso sobre conceitos como exploração, exploração e ajustes de recompensas.

Com a possibilidade de melhorias contínuas e aplicações em problemas mais complexos, este projeto se apresenta como uma base sólida para explorar os horizontes da inteligência artificial em ambientes simulados e no mundo real.

## Agradecimentos 👏

Gostaria de expressar minha gratidão a todas as pessoas e recursos que contribuíram para a realização deste projeto. Em especial:

1. **Comunidade de Desenvolvedores:** Pelas bibliotecas poderosas como `PyTorch`, `Pygame` e `Matplotlib`, que tornaram este projeto possível.
2. **Criadores de Conteúdo:** O vídeo original que inspirou este projeto serviu como uma fonte rica de conhecimento e direcionamento prático para implementar aprendizado por reforço no Snake Game.
3. **Plataformas de Aprendizado:** Cursos e materiais online foram essenciais para aprofundar os conhecimentos necessários na implementação de redes neurais e algoritmos de aprendizado por reforço.

Este projeto não seria possível sem essas contribuições diretas e indiretas. A todos, meu muito obrigado!

<div align="center">
  <img src="https://github.com/user-attachments/assets/54afb33c-97be-40b6-8c96-0f12852e946f" alt="thank-you" width="500">
</div>

## 📞 Contato
- **LinkedIn:** [Eduardo Coqueiro](https://www.linkedin.com/in/eduardocoqueiro/)
- **Site:** [Eduardo Coqueiro](https://dataguy.my.canva.site/eduardo-coqueiro)
- **Kaggle:** [Eduardo Coqueiro](https://www.kaggle.com/eduardocoqueiro)

