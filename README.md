# Driver-Project-Java-
/**
 * Write a description of class Project2Driver here.
 *
 * @author (your name)
 * @version (a version number or a date)
 */
import java.util.ArrayList;

public class Project2Driver{
    final public static double INTEREST_RATE = 0.013;  // 1.3%

    public static void main( String[] args ){
        ArrayList<Account> accounts = new ArrayList<Account>();  // container for accounts

        // checking account with an initial balance of $100
        CheckingAccount checking = new CheckingAccount( 100.0 );

        // savings account with an initial balance of $1000 and an interest rate
        SavingsAccount savings = new SavingsAccount( 1020.0, INTEREST_RATE );

        // details of transactions
        double monthlyExpenses = 756.34;
        int electricBillCheckNum = 2123;
        double electricBill = 60.34;
        int registationCheckNum = 2124;
        double registration = 50.00;
        double dinnerMoney = 55.32;
        double futureCar = 200.0;

        // checking account transactions
        checking.deposit( monthlyExpenses );
        checking.processCheck( electricBillCheckNum, electricBill );
        checking.withdraw( dinnerMoney );
        checking.processCheck( registationCheckNum, registration );
        checking.processCheck( registationCheckNum, registration ); // second attempt, should fail
        accounts.add( checking );

        // savings account transactions
        savings.deposit( futureCar );
        savings.applyInterest( );
        accounts.add( savings );

        // Display account information
        System.out.println("\nInformation about all accounts:");
        for( Account acct : accounts ){
            System.out.println( acct );
        }
    }
}
