# Console-Calculator

import java.util.Scanner;

public class ConsoleCalculator {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        boolean cals = true;

        while (cals) {
            showMenu();
            String choice = sc.nextLine();

            switch (choice) {
                case "1":
                    performOperation(sc, "add");
                    break;
                case "2":
                    performOperation(sc, "subtract");
                    break;
                case "3":
                    performOperation(sc, "multiply");
                    break;
                case "4":
                    performOperation(sc, "divide");
                    break;
                case "5":
                    System.out.println("Exiting. Goodbye!");
                    cals = false;
                    break;
                default:
                    System.out.println("Invalid choice. Please pick 1–5.");
                    break;
            }
        }

        sc.close();
    }

    private static void showMenu() {
        System.out.println("\n=== SIMPLE CALCULATOR ===");
        System.out.println("1) Add");
        System.out.println("2) Subtract");
        System.out.println("3) Multiply");
        System.out.println("4) Divide");
        System.out.println("5) Exit");
        System.out.print("Choose an option: ");
    }

    private static void performOperation(Scanner sc, String op) {
        System.out.print("Enter first number: ");
        double a = readDouble(sc);

        System.out.print("Enter second number: ");
        double b = readDouble(sc);

        double result;
        switch (op) {
            case "add":
                result = add(a, b);
                break;
            case "subtract":
                result = subtract(a, b);
                break;
            case "multiply":
                result = multiply(a, b);
                break;
            case "divide":
                if (b == 0) {
                    System.out.println("Error: Cannot divide by zero.");
                    return;
                }
                result = divide(a, b);
                break;
            default:
                System.out.println("Unknown operation.");
                return;
        }

        System.out.printf("Result: %.4f\n", result);
    }

    private static double readDouble(Scanner sc) {
        while (true) {
            try {
                String line = sc.nextLine().trim();
                return Double.parseDouble(line);
            } catch (NumberFormatException e) {
                System.out.print("Not a number. Try again: ");
            }
        }
    }

    // Arithmetic methods
    private static double add(double x, double y)       { return x + y; }
    private static double subtract(double x, double y)  { return x - y; }
    private static double multiply(double x, double y)  { return x * y; }
    private static double divide(double x, double y)    { return x / y; }
}
