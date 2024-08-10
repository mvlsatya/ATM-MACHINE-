# ATM-MACHINE-
package atm;
import java.util.Scanner;

public class Atm {
    public static void main(String[] args) {
        int initialAmount = 1000;
        int pin = 2288;
        Scanner sc = new Scanner(System.in);

        System.out.println("WELCOME TO SBI ATM MACHINE");
        System.out.println("Enter the pin:");

        int enteredPin = sc.nextInt();

        if (enteredPin == pin) {
            System.out.println("Pin is correct");

            while (true) {
                System.out.println("\n1. Check Balance");
                System.out.println("2. Deposit Money");
                System.out.println("3. Withdraw Money");
                System.out.println("4. Exit");
                System.out.print("Choose an option: ");
                
                int num = sc.nextInt();

                switch (num) {
                    case 1:
                        System.out.println("Your balance amount is: " + initialAmount);
                        break;

                    case 2:
                        System.out.println("Enter the amount to deposit:");
                        int depositMoney = sc.nextInt();
                        initialAmount += depositMoney;
                        System.out.println("Amount successfully deposited. New balance: " + initialAmount);
                        break;

                    case 3:
                        System.out.println("Enter the amount to withdraw:");
                        int withdrawMoney = sc.nextInt();
                        if (withdrawMoney <= initialAmount) {
                            initialAmount -= withdrawMoney;
                            System.out.println("Amount successfully withdrawn. New balance: " + initialAmount);
                        } else {
                            System.out.println("Insufficient balance.");
                        }
                        break;

                    case 4:
                        System.out.println("Thank you for using SBI ATM. Goodbye!");
                       
                        System.exit(0); // Exit the program
                        break;

                    default:
                        System.out.println("Invalid option. Please choose again.");
                }
            }
        } else {
            System.out.println("Invalid pin. Please try again.");
        }
        sc.close();
    }
}
