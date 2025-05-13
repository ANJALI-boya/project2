import java.util.Scanner;

public class QuizApp {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Questions, options, and correct answers
        String[] questions = {
            "What is the capital of India?",
            "Which language is used for Android development?",
            "What is the result of 3 + 2 * 2?",
            "Which keyword is used to create a subclass in Java?"
        };

        String[][] options = {
            {"1. Mumbai", "2. Delhi", "3. Kolkata", "4. Chennai"},
            {"1. Python", "2. Java", "3. Swift", "4. C++"},
            {"1. 10", "2. 7", "3. 9", "4. 8"},
            {"1. super", "2. extends", "3. implements", "4. inherits"}
        };

        int[] answers = {2, 2, 2, 2}; // correct option numbers (1-based index)

        int score = 0;

        System.out.println(" Welcome to the Java Quiz!\n");

        for (int i = 0; i < questions.length; i++) {
            System.out.println("Q" + (i + 1) + ": " + questions[i]);
            for (String option : options[i]) {
                System.out.println(option);
            }

            System.out.print("Your answer (1-4): ");
            int userAnswer = scanner.nextInt();

            if (userAnswer == answers[i]) {
                System.out.println(" Correct!\n");
                score++;
            } else {
                System.out.println(" Incorrect! Correct answer was option " + answers[i] + ".\n");
            }
        }

        System.out.println(" Quiz Over!");
        System.out.println("Your score: " + score + " out of " + questions.length);
        scanner.close();
    }
}
