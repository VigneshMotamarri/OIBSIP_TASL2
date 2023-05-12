# OIBSIP_TASL2
Number Guessing Game
import java.util.*;

public class NumGuessingGame {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        Random rand = new Random();
        int randomNumber = rand.nextInt(100) + 1;
        int attempts = 10;
        int score = 0;

        System.out.println("Welcome to the Number Guessing Game!");
        System.out.println("You have " + attempts + " attempts to guess the number.");
        System.out.print("Enter your guess (1-100): ");

        while (attempts > 0) {
            int guess = input.nextInt();
            if (guess == randomNumber) {
                System.out.println("Congratulations! You guessed the number!");
                score += attempts;
                break;
            } else if (guess > randomNumber) {
                System.out.println("Your guess is too high. Try again.");
            } else {
                System.out.println("Your guess is too low. Try again.");
            }

            attempts--;
            if (attempts > 0) {
                System.out.println("You have " + attempts + " attempts left.");
                System.out.print("Enter your guess (1-100): ");
            }
        }

        if (attempts == 0) {
            System.out.println("Game over. The number was " + randomNumber);
        }

        System.out.println("Your score is " + score);
        input.close();
    }
}
