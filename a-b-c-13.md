Welcome to the a-b-c-13 wiki!

Задача 1 — Сумирай до 13 Дават ни се три числа a, b и c. 
Отпечатайте дали трите числа могат да се сумират до 13, като единственото
нещо което можем да правим е да сменяме знака пред тях. Вход 
•
Входът се чете от конзолата, на първият ред ще получите числата a, b и c,
разделени със интервали. Изход • Отпечатайте "Yes" ако числата могат да се сумират до 13, или "No" ако не могат. 
Ограничения • а, b и c ще са цели числа в диапазона [-1 000 000…1 000 000]. 
• 
Позволено време: 100 мс. Позволена памет: 16 MB. Примерен вход и изход Вход Изход Коментари -10 2 -1 Yes 
Сменяме знаците на -10 и -1, за да получим 10 + 2 + 1 = 13 съответно изписваме "Yes"

Вход Изход Коментари -1 10 -1 No Независимо как сменяме знаците, няма как да получим 13 съответно изписваме "No"

package zad;

import java.util.Scanner;

public class Zad {

public static void main(String[] args) {

    Scanner scan = new Scanner(System.in);
    String[] array = scan.nextLine().split(" +");
    int a = Math.abs(Integer.parseInt(array[0]));
    int b = Math.abs(Integer.parseInt(array[1]));
    int c = Math.abs(Integer.parseInt(array[2]));
    scan.close();

    if (a + b + c < 13) {
        System.out.println("No");   
    }
    else if (a + b + c == 13) {
        System.out.println("Yes");
    }
    else {
        if(sum(sum(a, b), c) == 13) {
            System.out.println("Yes");
        }
        else if(sum(sum(b, c), a) == 13) {
            System.out.println("Yes");
        }   

        else if((sum(a, b) + c) == 13) {
                 System.out.println("Yes");
        }
        else if((sum(a, c) + b) == 13) {
                 System.out.println("Yes");
        }
        else if((sum(b, c) + a) == 13) {
                 System.out.println("Yes");
        }
        else {
                 System.out.println("No");
        }
    }
}

private static int sum(int a, int b) {
    if (a > b) {
     return a - b;
    } else {
        return b-a; 
 }

 }
}
