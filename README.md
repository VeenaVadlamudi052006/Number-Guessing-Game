# Number-Guessing-Game

import java.util.*;
import java.util.Scanner;
import java.util.Random;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Random rand = new Random();
        int totalScore = 0;

        System.out.println("=== Number Guessing Game ===");

        while (true) {
            System.out.println("\n1. Play Game\n2. Exit");
            int choice = sc.nextInt();
            sc.nextLine();

            if (choice == 2) {
                System.out.println("Thank you for playing! Final Score: " + totalScore);
                break;
            }

            int number = rand.nextInt(100) + 1;
            int guess = 0, attempts = 0;

            System.out.println("Guess a number between 1 and 100:");

            while (guess != number) {
                System.out.print("Enter your guess: ");
                guess = sc.nextInt();
                sc.nextLine();
                attempts++;

                if (guess > number) System.out.println("Too high!");
                if (guess < number) System.out.println("Too low!");
            }

            int score = (10 - attempts) > 0 ? (10 - attempts) : 1;
            totalScore += score;
            System.out.println("🎉 Correct! Attempts: " + attempts + ", Score this round: " + score);
        }
    }
}
