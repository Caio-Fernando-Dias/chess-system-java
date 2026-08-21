# Chess System - Jogo de Xadrez em Java

<div align="center">
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white" />
  <img src="https://img.shields.io/badge/POO-005C84?style=for-the-badge" />
</div>

## Sobre o Projeto
Este projeto é um jogo de Xadrez completo executado diretamente no console (terminal), desenvolvido inteiramente em **Java**. O sistema aplica conceitos fortes de **Programação Orientada a Objetos (POO)** como Encapsulamento, Herança, Polimorfismo, e Tratamento de Exceções. 

O tabuleiro e as peças de xadrez foram construídos com base em uma arquitetura em camadas, separando as lógicas genéricas de tabuleiros de mesa (`boardgame`) das regras estritas e específicas do xadrez (`chess`).

## Tecnologias Utilizadas
* **Backend:** Java (JDK)
* **Design de Software:** POO (Programação Orientada a Objetos)

## Funcionalidades
* **Lógica Completa de Xadrez:** Movimentação padrão de todas as peças (Peão, Torre, Cavalo, Bispo, Rainha, Rei).
* **Movimentos Especiais:** 
  * Roque Pequeno (Kingside Castling)
  * Roque Grande (Queenside Castling)
  * En Passant
  * Promoção de Peão
* **Controle de Estado:** Identificação precisa de estado de Check e Checkmate.
* **Interface via Console:** Exibição do tabuleiro em tempo real com captura de peças e exibição do histórico de rodadas (com suporte a exibição de cores e limpeza de tela, a depender do terminal).
* **Tratamento de Exceções:** Sistema robusto impedindo que jogadores realizem movimentos impossíveis, acessem casas inexistentes ou coloquem seu próprio rei em Check.

## Estrutura da Aplicação
A aplicação segue um padrão rigoroso de separação de camadas:
* `boardgame`: Camada de tabuleiro genérico. Contém classes base genéricas de `Board` e `Piece`, além de exceções locais. Foi criada visando total reaproveitamento: pode ser usada facilmente como base para a criação de qualquer outro jogo de matriz de tabuleiro (como Damas ou Jogo da Velha).
* `chess`: Camada de xadrez. Contém a lógica de partida, regras estritas do esporte, os movimentos específicos de cada peça (as sub-classes de `ChessPiece`) e a engine de turnos que detecta fim de jogo e validações (`ChessMatch`).
* `application`: Camada de interface de usuário. Contém o ponto de entrada do sistema (`Program`) e as abstrações de console (`UI`), onde ocorre a impressão dos dados de tela, tradução das coordenadas do xadrez e interação via teclado com os jogadores.

## 🔧 Como Executar Localmente

### 1. Pré-requisitos
* Ter o **Java Development Kit (JDK)** instalado na sua máquina.

### 2. Executando a Aplicação
No terminal do seu sistema operacional, navegue até a pasta de arquivos `.class` (geralmente gerada pela IDE como `bin` ou similar) e rode o programa.

Se desejar compilar manualmente pelo terminal a partir do diretório raiz:
```bash
# Navegue até a pasta source
cd src

# Compile todos os arquivos Java
javac application/Program.java -d ../bin

# Volte um nível e execute a partir da pasta compilada
cd ..
java -cp bin application.Program
```

*(Obs: Por ser uma interface dinâmica feita no terminal, garanta que seu terminal ou console integrado tenha suporte nativo aos códigos de escape ANSI para que as cores das peças e a limpeza de tela funcionem apropriadamente).*
