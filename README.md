# carloan-

import java.util.Scanner;


public class carloan {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TOD
        double downpayment = 0, carprice = 0,interest = 0,ir = 0;
        double totalInterest,monthlyRepayment,principal,balance;
        int loan = 0;
       
        Scanner input= new Scanner (System.in);
       
        System.out.println("-------------------------------------------------------------------------");
        
        while (carprice < 30000){
            System.out.print("Enter the car price: ");
            carprice = input.nextDouble();
        }
        
        while(downpayment <= 0) {
            System.out.print("Enter your downpayment: ");
            downpayment = input.nextDouble();
        }
        while(loan < 5 || loan > 9) {
            System.out.print("Enter your loan period: ");
            loan = input.nextInt();
        }
        
        while(interest < 3 || interest > 7){
            System.out.print("Enter your interest rate: ");
            interest = input.nextDouble();
            ir = interest / 100;
        }
        totalInterest = (carprice - downpayment)*ir*loan;
        monthlyRepayment = (carprice - downpayment + totalInterest)/(loan*12);
   
        System.out.printf("Monthly Repayment is RM %.2f ", monthlyRepayment );
        
        System.out.println("\n-------------------------------------------------------------------------");
   
        System.out.print ("Years \t\t Principal \t\t Interest \t\t Balance \t ");
        
         for (int year = 1;year <= loan;year++){
            principal = monthlyRepayment * 12 * year;
            ir = totalInterest/loan * year;
            balance = monthlyRepayment * 12 * (loan - year);
   
        System.out.printf ("\n  %d \t\t %.2f \t\t %.2f \t\t %.2f\t", year,principal,ir,balance);
        year ++;
        }
    }
    }
    
