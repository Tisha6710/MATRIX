# MATRIX
// matrix multiplication in java
import java.util.Scanner;

public class MatrixMultiplication {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Input dimensions for the first matrix
        System.out.print("Enter number of rows for first matrix: ");
        int r1 = sc.nextInt();
        System.out.print("Enter number of columns for first matrix: ");
        int c1 = sc.nextInt();

        // Input dimensions for the second matrix
        System.out.print("Enter number of rows for second matrix: ");
        int r2 = sc.nextInt();
        System.out.print("Enter number of columns for second matrix: ");
        int c2 = sc.nextInt();

        // Check if multiplication is possible
        if (c1 != r2) {
            System.out.println("Matrix multiplication is not possible.");
            return;
        }

        // Input first matrix
        int[][] matrix1 = new int[r1][c1];
        System.out.println("Enter elements of first matrix:");
        for (int i = 0; i < r1; i++) {
            for (int j = 0; j < c1; j++) {
                matrix1[i][j] = sc.nextInt();
            }
        }

        // Input second matrix
        int[][] matrix2 = new int[r2][c2];
        System.out.println("Enter elements of second matrix:");
        for (int i = 0; i < r2; i++) {
            for (int j = 0; j < c2; j++) {
                matrix2[i][j] = sc.nextInt();
            }
        }

        // Multiply matrices
        int[][] result = new int[r1][c2];
        for (int i = 0; i < r1; i++) {
            for (int j = 0; j < c2; j++) {
                for (int k = 0; k < c1; k++) {
                    result[i][j] += matrix1[i][k] * matrix2[k][j];
                }
            }
        }

        // Print result
        System.out.println("Resultant Matrix:");
        for (int i = 0; i < r1; i++) {
            for (int j = 0; j < c2; j++) {
                System.out.print(result[i][j] + " ");
            }
            System.out.println();
        }

        sc.close();
    }
}
