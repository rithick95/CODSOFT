#Student Grade Calculator

import java.util.Scanner;

public class student {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        double subject1 = 0.25;
        double subject2 = 0.25;
        double subject3 = 0.25;
        double subject4 = 0.25;
        
        System.out.println("Enter Subject1 Score:");
        double subject1score = sc.nextDouble();
        System.out.println("Enter Subject2 Score:");
        double subject2score = sc.nextDouble();
        System.out.println("Enter Subject3 Score:");
        double subject3score = sc.nextDouble();
        System.out.println("Enter Subject4 Score:");
        double subject4score = sc.nextDouble();
        
        double subject1weight = subject1 * subject1score;
        double subject2weight = subject2 * subject2score;
        double subject3weight = subject3 * subject3score;
        double subject4weight = subject4 * subject4score;
        
        double finalgrade = subject1weight + subject2weight + subject3weight + subject4weight;
        
        System.out.printf("Your Final Grade is: %.2f\n", finalgrade);
      
        if (finalgrade >= 90) {
            System.out.println("You Received an A");
        } else if (finalgrade >= 80) {
            System.out.println("You Received a B");
        } else if (finalgrade >= 70) {
            System.out.println("You Received a C");
        } else if (finalgrade >= 60) {
            System.out.println("You Received a D");
        } else {
            System.out.println("You Received an F");
        }
        sc.close();
    }
}
