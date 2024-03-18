//# Stack1-DSA-
//Stack program made in Collage using java
/*
name : Maharshi Bhatt
Date : 17/03/2024
aim  : concept of stack 
*/
import java.util.*;

class Stack1 {
    static int top = -1;
    int size;

    public static void main(String[] args) {
        Stack1 s1 = new Stack1();
        Scanner sc = new Scanner(System.in);
        System.out.print("\u001b[33mEnter size of stack: \u001b[0m");
        s1.size = sc.nextInt();
        int[] s = new int[s1.size];
        int choice = 0;
        do {
            System.out.println("\n1.Push\n2.Pop\n3.Peek\n4.Change\n5.Display\n6.Exit");
            System.out.print("\u001b[32mEnter Choice : \u001b[0m");
            choice = sc.nextInt();
            switch (choice) {
                case 1:
                    s1.push(s);
                    break;
                case 2:
                    s1.pop(s);
                    break;
                case 3:
                    s1.peek(s);
                    break;
                case 4:
                    s1.change(s);
                    break;
                case 5:
                    s1.display(s);
                    break;
                case 6:
                    System.out.println("\u001b[34mExiting...");
                    break;
                default:
                    System.out.println("\u001b[31mWrong Choice!");
                    break;
            }

        } while (choice != 6);
        sc.close();
    }

    void push(int s[]) {
        Scanner sc = new Scanner(System.in);
        if (top >= s.length - 1) {
            System.out.println("\u001b[31mStack is Overflow !\u001b[0m");
            return;
        }
        top++;
        System.out.print("Enter element to push: ");
        s[top] = sc.nextInt();
    }

    void pop(int s[]) {
        if (top == -1) {
            System.out.println("\u001b[31mStack is Underflow!\u001b[0m");
            return;
        }
        System.out.println("Deleting " + s[top]);
        top--;
    }

    void display(int s[]) {
        if (top == -1) {
            System.out.println("\u001b[31mStack is Empty!\u001b[0m");
            return;
        }
        System.out.println("Stack elements:");
        for (int i = top; i >= 0; i--) {
            System.out.println("|" + s[i] + "|");
        }
    }

    void peek(int s[]) {

        Scanner sc = new Scanner(System.in);
        System.out.print("Enter position : ");
        int i = sc.nextInt();
        int temp = top - i +1;
        if(temp <= -1){
            System.out.print("\u001b[31mStack underflow !\u001b[0m");
        }
        System.out.println(s[temp]);
    }

    void change(int s[]) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter position : ");
        int i = sc.nextInt();
        int temp = top - i +1;
        if(temp <= -1){
            System.out.print("\u001b[31mStack underflow !\u001b[0m");
        }

        System.out.println(i + "th element is changing.....");
        System.out.print("Enter new value: ");
        s[i] = sc.nextInt();
    }
}
