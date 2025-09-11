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
### `Código`
import java.util.Scanner;

public class jogo_da_velha {
    public static void main(String[] args) {
        char[][] board = new char[3][3];
        char currentPlayer = 'X';
        Scanner scanner = new Scanner(System.in);

        // Inicializa o tabuleiro
        for (int i = 0; i < 3; i++)
            for (int j = 0; j < 3; j++)
                board[i][j] = ' ';

        while (true) {
            printBoard(board);
            System.out.println("Jogador " + currentPlayer + ", informe linha e coluna (0-2):");
            int row = scanner.nextInt();
            int col = scanner.nextInt();

            if (row < 0 || row > 2 || col < 0 || col > 2 || board[row][col] != ' ') {
                System.out.println("Posição inválida. Tente novamente.");
                continue;
            }

            board[row][col] = currentPlayer;

            if (checkWin(board, currentPlayer)) {
                printBoard(board);
                System.out.println("Jogador " + currentPlayer + " venceu!");
                break;
            }

            if (isBoardFull(board)) {
                printBoard(board);
                System.out.println("Empate!");
                break;
            }

            currentPlayer = (currentPlayer == 'X') ? 'O' : 'X';
        }
        scanner.close();
    }

    static void printBoard(char[][] board) {
        System.out.println("  0 1 2");
        for (int i = 0; i < 3; i++) {
            System.out.print(i + " ");
            for (int j = 0; j < 3; j++) {
                System.out.print(board[i][j]);
                if (j < 2) System.out.print("|");
            }
            System.out.println();
            if (i < 2) System.out.println("  -----");
        }
    }

    static boolean checkWin(char[][] board, char player) {
        for (int i = 0; i < 3; i++)
            if ((board[i][0] == player && board[i][1] == player && board[i][2] == player) ||
                (board[0][i] == player && board[1][i] == player && board[2][i] == player))
                return true;
        if ((board[0][0] == player && board[1][1] == player && board[2][2] == player) ||
            (board[0][2] == player && board[1][1] == player && board[2][0] == player))
            return true;
        return false;
    }

    static boolean isBoardFull(char[][] board) {
        for (int i = 0; i < 3; i++)
            for (int j = 0; j < 3; j++)
                if (board[i][j] == ' ')
                    return false;
        return true;
    }
}

---

# 🙌 Agradecimentos

Obrigado a todos que conseguirem:
 - Executar o jogo 🎉
 - Compartilhar feedback 📝
 - Contribuir com melhorias 🚀
