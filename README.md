# 🎮 Jogo da Velha em Java

Um simples jogo da velha feito em **Java** para rodar no terminal.  
Dois jogadores podem se enfrentar, alternando entre **X** e **O**.

---

## 🕹️ Regras do jogo

O tabuleiro é uma matriz 3x3.

Jogadores jogam alternadamente (X e O).

O jogo termina quando:
 - Um jogador completa uma linha, coluna ou diagonal.
 - O tabuleiro está cheio (empate).
---

# 🕹️ Como Jogar:
Para jogar, siga estes passos no terminal:

1. Execute o programa Java.
2. O tabuleiro será exibido com linhas e colunas numeradas de 0 a 2.
3. Quando for sua vez, digite dois números separados por espaço:  
   - O primeiro número é a linha (0, 1 ou 2).
   - O segundo número é a coluna (0, 1 ou 2).
   - Exemplo: `1 2` (marca na linha 1, coluna 2).
4. O jogo alterna entre os jogadores X e O até alguém vencer ou empatar.

Se digitar uma posição inválida ou já ocupada, o programa pedirá para tentar novamente.

---

# Como Fazer:
Vou explicar os blocos principais do seu código (usei nomes legíveis onde for útil):

1 - import java.util.Scanner;

   - Importa a classe Scanner para ler a entrada do usuário pelo terminal.

2 - public class jogo_da_velha { ... }

   - Declaração da classe principal. Observação: por convenção em Java usa-se JogoDaVelha (CamelCase). Se renomear a classe, renomeie também o arquivo para JogoDaVelha.java.

3- public static void main(String[] args) { ... }

   - Ponto de entrada do programa.

4 - char[][] board = new char[3][3];

   - Cria o tabuleiro 3x3 usando char.

5 - char currentPlayer = 'X';

   - Variável que guarda o jogador atual (começa com 'X').

6 - Scanner scanner = new Scanner(System.in);

   - Cria o scanner para ler linhas/colunas digitadas.

7 - Inicialização do tabuleiro:
    - for (int i = 0; i < 3; i++)
        for (int j = 0; j < 3; j++)
          board[i][j] = ' ';

 - Preenche cada célula com espaço em branco.

8 - Loop principal while (true) { ... } — cada iteração representa um turno:

   - printBoard(board); — exibe o tabuleiro atual.
    
  - Pede linha e coluna: int row = scanner.nextInt(); int col = scanner.nextInt();
    
    - Validação:
    
      - if (row < 0 || row > 2 || col < 0 || col > 2 || board[row][col] != ' ') {
        System.out.println("Posição inválida. Tente novamente.");
        continue;
        }
        
  - checa se a posição está no intervalo e se não está ocupada.
    
  - Marca a posição: board[row][col] = currentPlayer;
    
  - Verifica vitória: if (checkWin(board, currentPlayer)) { ... }
    
  - Se vitória: imprime tabuleiro e a mensagem e break.
    
  - Verifica empate: if (isBoardFull(board)) { ... }
    
  - Troca jogador:
    
      - currentPlayer = (currentPlayer == 'X') ? 'O' : 'X';

9 - scanner.close();
    - Fecha o scanner ao final.

10 - static void printBoard(char[][] board) { ... }
     - Imprime índices e o tabuleiro com "|" e "-----" entre linhas.

11 - static boolean checkWin(char[][] board, char player) { ... }
     - Verifica linhas, colunas e duas diagonais para ver se player venceu.

12 - static boolean isBoardFull(char[][] board) { ... }
     - Retorna true se não houver espaços vazios no tabuleiro.

---
### `Código`
Para rodar este script, você precisará ter o Java instalado.

1.  Clone este repositório ou baixe o arquivo `jogo_da_velha_java`.
2.  Abra o terminal ou prompt de comando.
3.  Navegue até o diretório onde o arquivo está salvo.
4.  Execute o script com o comando:

```bash
java jogo_da_velha_java


---

# 🙌 Agradecimentos

Obrigado a todos que conseguirem:
 - Executar o jogo 🎉
 - Compartilhar feedback 📝
 - Contribuir com melhorias 🚀
