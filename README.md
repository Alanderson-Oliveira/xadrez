# 🏰 Jogo de Xadrez em C


## ✨ Características

- 🎯 **Movimentos válidos** calculados automaticamente para cada peça
- 💾 **Sistema de salvamento** de jogadas em arquivo binário
- 🎨 **Interface visual** com símbolos Unicode para as peças
- ⚔️ **Modo dois jogadores** (Humano vs IA)
- 📊 **Sistema de avaliação** de posições no tabuleiro
- 🔄 **Detecção automática** de capturas e fim de jogo

## 🛠️ Pré-requisitos

- **Compilador C** (GCC recomendado)
- **Sistema Windows** (para algumas funcionalidades específicas como `conio.h`)
- **Terminal** com suporte a Unicode (para visualização das peças)

## 📦 Instalação

### Windows com GCC/MinGW

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/xadrez.git
cd xadrez

# Compile o jogo
gcc -o xadrez xadrez.c -lm

# Execute o jogo
./xadrez.exe
```

### Linux/WSL

```bash
# Compile com suporte a matemática
gcc -o xadrez xadrez.c -lm

# Execute
./xadrez
```

## 🎮 Como Jogar

### Iniciando o Jogo

1. Execute o programa compilado
2. O tabuleiro será exibido com as peças em suas posições iniciais
3. O jogador humano sempre joga com as peças brancas (números positivos)
4. A IA joga com as peças pretas (números negativos)

### Sistema de Coordenadas

O jogo usa um sistema de coordenadas simples:

- **Linhas**: 0-7 (de cima para baixo)
- **Colunas**: 0-7 (da esquerda para direita)
- **Entrada**: Digite a coordenada como dois dígitos (ex: `34` = linha 3, coluna 4)

### Fazendo uma Jogada

1. **Selecione a peça**: Digite as coordenadas da peça que deseja mover
2. **Veja os movimentos**: O jogo mostrará todos os movimentos válidos
3. **Escolha o destino**: Digite as coordenadas de destino
4. **Confirmação**: A jogada será executada automaticamente

### Exemplo de Jogada

```
Qual peça deseja mover?
Linha: 1
Coluna: 4
Linha para: 3
Coluna para: 4
```

## 🎯 Funcionalidades

### Peças e Movimentos

| Código | Peça   | Branca | Preta |
| ------ | ------ | ------ | ----- |
| ±1     | Peão   | 1      | -1    |
| ±2     | Cavalo | 2      | -2    |
| ±3     | Bispo  | 3      | -3    |
| ±4     | Torre  | 4      | -4    |
| ±5     | Dama   | 5      | -5    |
| ±6     | Rei    | 6      | -6    |



## 🏗️ Estrutura do Código

```
xadrez.c
├── Estruturas de Dados
│   ├── stjogada - Representa uma jogada
│   ├── stpeca - Representa uma peça
│   └── stposicao - Estado do tabuleiro
├── Funções de Movimento
│   ├── peaoBranco/peaoPreto
│   ├── torreBranca/torrePreta
│   ├── cavaloBranco/cavaloPreto
│   ├── bispoBranco/bispoPreto
│   ├── damaBranca/damaPreta
│   └── reiBranco/reiPreto
├── Sistema de IA
│   ├── ExecutaIA - Algoritmo principal
│   ├── AvaliaPosicao - Função de avaliação
│   └── CopiaPosicao - Cópia de estado
└── Gerenciamento
    ├── SalvaJogada - Persistência
    └── LiberaMemoria - Limpeza
```

## 🧠 Algoritmos Implementados

### Minimax com Poda Alpha-Beta

```c
stjogada ExecutaIA(stposicao atual, int nivel, double alfa, double beta)
```

- **Profundidade**: Até 9 níveis (configurável)
- **Poda Alpha-Beta**: Otimização para reduzir o espaço de busca
- **Avaliação**: Sistema baseado em valor material e posicionamento

### Sistema de Avaliação

| Peça         | Valor Base  |
| ------------ | ----------- |
| Peão         | 1 ponto     |
| Cavalo/Bispo | 3 pontos    |
| Torre        | 5 pontos    |
| Dama         | 9 pontos    |
| Rei          | 1000 pontos |

_Penalidades aplicadas para peças sob ataque_

## 🎨 Interface

### Tabuleiro Visual

```
     0  1  2  3  4  5  6  7
    ------------------------
0 | -4 -2 -3 -5 -6 -3 -2 -4 |
1 | -1 -1 -1 -1 -1 -1 -1 -1 |
2 |  0  0  0  0  0  0  0  0 |
3 |  0  0  0  0  0  0  0  0 |
4 |  0  0  0  0  0  0  0  0 |
5 |  0  0  0  0  0  0  0  0 |
6 |  1  1  1  1  1  1  1  1 |
7 |  4  2  3  5  6  3  2  4 |
    ------------------------
```

### Indicadores

- **Números positivos**: Peças brancas (jogador)
- **Números negativos**: Peças pretas (IA)
- **0**: Casas vazias

## 📁 Arquivos Gerados

- `jogadas.bin`: Arquivo binário com histórico de todas as jogadas

## 🚀 Melhorias Futuras

- [ ] Interface gráfica completa
- [ ] Detecção de xeque e xeque-mate
- [ ] Implementação de roque e en passant
- [ ] Modo multiplayer online
- [ ] Diferentes níveis de dificuldade
- [ ] Análise de partidas salvas










