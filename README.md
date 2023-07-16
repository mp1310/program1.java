# program1.java

import java.util.Scanner;

class Calculator {
    private double a;
    private double b;

    public Calculator(double a, double b) {
        this.a = a;
        this.b = b;
    }

    public double add() {
        return a + b;
    }

    public double subtract() {
        return a - b;
    }

    public double multiply() {
        return a * b;
    }

    public double divide() {
        if (b != 0) {
            return a / b;
        } else {
            throw new ArithmeticException("Cannot divide by zero");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter the value of 'a': ");
        double a = scanner.nextDouble();

        System.out.print("Enter the value of 'b': ");
        double b = scanner.nextDouble();

        System.out.print("Enter the type of operation (+, -, *, /): ");
        String operation = scanner.next();

        Calculator calculator = new Calculator(a, b);
        double result;

        switch (operation) {
            case "+":
                result = calculator.add();
                System.out.println("Result: " + result);
                break;
            case "-":
                result = calculator.subtract();
                System.out.println("Result: " + result);
                break;
            case "*":
                result = calculator.multiply();
                System.out.println("Result: " + result);
                break;
            case "/":
                try {
                    result = calculator.divide();
                    System.out.println("Result: " + result);
                } catch (ArithmeticException e) {
                    System.out.println("Error: " + e.getMessage());
                }
                break;
            default:
                System.out.println("Invalid operation");
        }

        scanner.close();
    }
}

