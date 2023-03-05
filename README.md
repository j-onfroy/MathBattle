"""# MathBattle"""
"""This is game MathBattle clone"""
import java.util.Random;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Random random = new Random();
        Scanner scanner = new Scanner(System.in);

        System.out.println(" MathBattle. Click on any a button");
        scanner.nextLine();

        int n = 0;
        while (true) {
            int c1, c2, c3;
            int c4;
            int a = random.nextInt(20) + 1;
            int b = random.nextInt(20) + 1;

            c1 = a + b;
            c2 = a - b;
            c3 = a * b;

            String[] operators = {"+", "-", "*", "/"};
            int[] question;

            int index = random.nextInt(3);
            int indexQuestin = random.nextInt(3);

            if ((a % b == 0) & indexQuestin < 2) {
                c4 = a / b;
                question = new int[]{c1, c2, c3, c4};
            } else {
                question = new int[]{c1, c2, c3};
            }
            String operator = operators[index];
            System.out.println(a + operator + b + "=" + question[indexQuestin] + " Correct 1 \n Incorect 0");

            int answer = scanner.nextInt();
            if (answer == 1) {
                if (question[index] == question[indexQuestin]) {
                    n++;
                } else break;


            } else {
                if (question[index] != question[indexQuestin]) {
                    n++;
                } else break;
            }


        }
        System.out.println("Siz to'plagan ball = " + n);


    }
}
