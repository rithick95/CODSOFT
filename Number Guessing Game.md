# Number Guessing Game 

import java.util.Random;
import java.util.Scanner;

public class NumberGame {

    public static boolean playRound(int maxAttempts) {
        Random rand = new Random();
        int targetNumber = rand.nextInt(100) + 1;
        int attempts = 0;
        
        Scanner scanner = new Scanner(System.in);
        System.out.println("\nI have generated a random number between 1 and 100.");
        System.out.println("You have " + maxAttempts + " attempts to guess it correctly.\n");
        
        while (attempts < maxAttempts) {
            System.out.print("Attempt " + (attempts + 1) + "/" + maxAttempts + " - Enter your guess: ");
            int guess = scanner.nextInt();
            attempts++;
            
            if (guess < targetNumber) {
                System.out.println("Your guess is too low.");
            } else if (guess > targetNumber) {
                System.out.println("Your guess is too high.");
            } else {
                System.out.println("Congratulations! You guessed the number " + targetNumber + " correctly in " + attempts + " attempts.");
                return true;
            }
        }
        
        System.out.println("Sorry, you've run out of attempts. The correct number was " + targetNumber + ".");
        return false;
    }

    public static void startGame() {
        Scanner scanner = new Scanner(System.in);
        int roundsPlayed = 0;
        int roundsWon = 0;
        int maxAttempts = 10;
        
        System.out.println("Welcome to the Number Guessing Game!");
        
        while (true) {
            roundsPlayed++;
            System.out.println("\n--- Round " + roundsPlayed + " ---");
            
            if (playRound(maxAttempts)) {
                roundsWon++;
            }
            
            System.out.print("\nDo you want to play another round? (yes/no): ");
            String playAgain = scanner.next().toLowerCase();
            
            if (!playAgain.equals("yes")) {
                break;
            }
        }
        
        System.out.println("\nGame Over! You won " + roundsWon + " out of " + roundsPlayed + " rounds.");
    }

    public static void main(String[] args) {
        startGame();
    }
}
