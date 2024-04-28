import javax.swing.*;
import java.util.Scanner;

class ATM
{
    float balance;
    int PIN=5674;
     public void checkPin()
     {
         System.out.println("Enter your pin");
         Scanner sc=new Scanner(System.in);
         int enteredPin=sc.nextInt();
         if(enteredPin==PIN)
         {
           menu();
         }
         else
         {
             System.out.println("Enter a valid pin!");
         }
     }
     public void menu()
     {
         System.out.println("  Enter Your Choice");
         System.out.println(" 1. Check A/c Balance");
         System.out.println(" 2. Withdraw money");
         System.out.println(" 3. Deposit Money");
         System.out.println(" 4. exit");
         Scanner sc=new Scanner(System.in);
         int opt=sc.nextInt();
         if(opt==1)
         {
            checkBalance();
         }
         else if( opt==2)
         {
             withdrawMoney();
         }
         else if (opt==3)
     {
         depositMoney();
     }
         else if(opt==4)
     {
         return;
     }
         else {
             System.out.println("Enter a valid choice");
             menu();
     }

     }

     public void checkBalance()
     {
         System.out.println("Balance:"+balance);
         menu();
     }
     public void withdrawMoney()
     {
         System.out.println("Enter Amount to withdraw");
         Scanner sc=new Scanner(System.in);
         float amount=sc.nextFloat();
         if(amount>balance)
         {
             System.out.println("insufficient balance!");

         }
         else {
             balance=balance-amount;
             System.out.println("withdraw successfull");
         }
         menu();
     }
     public void depositMoney()
     {
         System.out.println("Enter amount to deposit");
         Scanner sc=new Scanner(System.in);
         float amount=sc.nextFloat();
         balance=balance+amount;
          menu();
     }
}
public class AtmMachine
{
public static void main(String[] args)
{
ATM obj=new ATM();
obj.checkPin();
}
}
