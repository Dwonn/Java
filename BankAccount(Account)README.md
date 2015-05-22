# Java
// Programmer: Dgoodwin4 
// Filename: Account.java 
// Last modified: 03/24/2015 
// Description: An Account object to model banking account data and behavior, along with a test program to instantiate and test the Account object.


  
    public class Account{
		private int id;
		private double balance, annualInterestRate, monthlyInterestRate, withdraw, deposit;
		
		private java.util.Date dateCreated = new java.util.Date();
		
		public Account( ){


		}

		public Account( int id, double initialBalance){
			this.id = id;
			balance = initialBalance;
			
			
		}
		
		//assessors
		public int getId( ){
			return id;
			
		}
		
		public double getBalance( ){
			return balance;
			
		}
		
		public double getAnnualInterestRate( ){
			return annualInterestRate;
			
		}
				
		public java.util.Date getDateCreated( ){
			return dateCreated;
			
		}
	
		public double getMonthlyInterestRate( ){
			return annualInterestRate / 12;
		
		}
		
		public double getwithdraw( ){
			return withdraw;
			
		}
		
		public double getdeposit( ){
			return deposit;
			
		}
		
		//mutator
		public void setId( int newId){
			id = newId;		
			
		}
		
		public void setBalance( double newBalance ){

			balance = newBalance;
			
		}		
		
		public  void setAnnualInterestRate( double newAnnualInterestRate){
			annualInterestRate = newAnnualInterestRate;
		
		}
		
		public  void  setMonthlyInterestRate (double newMonthlyInterestRate){
 			monthlyInterestRate = newMonthlyInterestRate;
			
			
		}
		
		public void setWithdraw (double newWithdraw){
			withdraw = newWithdraw;
			
		}
		
		public void setDeposit( double newDeposit){
			deposit = newDeposit;
			
				
	}
		
}	
		




// Programmer: Dgoodwin4 
// Filename: Checking.java 
// Last modified: 04/07/2015 
// Description: A checking object for modeling banking 

public class Checking extends Account {
	
	public Checking( ){
		
	}
	
	public Checking( double balance ){
		//this.setBalance( balance );
		super.setBalance( balance );
	}
	
	public Checking( String Id, double balance ){
		//this.setBalance( balance );
		super.setBalance( balance );
		//this.setId(Id );
		super.setId(Id);
	}
	
	@Override
	public String toString( ){
		
		return super.toString() + "Checking, 2015-12345, " + this.getId() + ", Balance: " + this.getBalance();
	}

}


//Programmer: dgoodwin4
//Filename: CertificateOfDeposit.java 
//Last modified: 04/30/15 
//Description: Design a class named CertificateOfDeposit that extends the Savings class.
 
package com.gsu.cis.bankaccount;

public class CertificateOfDeposit extends Savings {
	
	private double penalty = 1.5000;
	
	public CertificateOfDeposit( double interestRate ){
		super( interestRate );		
	}
	
	public CertificateOfDeposit( double interestRate, double balance, String accountName ){
		super( interestRate );
		this.setBalance( balance );
		this.setName( accountName );
	}
	
	public void withdraw( double amount ) throws Exception{
		super.withdraw( amount + (amount*penalty) );
	}
	
	public String toString( ){
		return super.toString( );
	}
	
}


// Programmer: Dgoodwin4 
// Filename: Savings.java 
// Last modified: 04/07/2015 
// Description: A savings object to model banking 
public class Savings extends Account {
	
	private double dInterestRate = 0;
	
	public Savings( double interestRate ){
		super();
		
		this.dInterestRate = interestRate;
	}
	
	public Savings( String accountName, double interestRate, double balance){
		this.setBalance( balance );
		this.setId( accountName );
		this.dInterestRate = interestRate;
	}
	
	@Override
	public String toString(){
		return "Account Type: Savings, 2015-12453: " + this.getId() + ", Balance: " + this.getBalance() + ", Rate: " + dInterestRate;
		
	}

}


//Programmer: dgoodwin4
//Filename: MoneyMarket.java 
//Last modified: 04/30/2015 
//Description: Design a class named MoneyMarket class that extends the Checking 
class and contains constructor for balance and account name, withdraw method and toString method.
 
package com.gsu.cis.bankaccount;


public class MoneyMarket extends Checking {
	
	// A private double data field named penalty for the account (default 0.2000). 
	private double penalty = 0.2000;
	
	public MoneyMarket( ){ }
	/**
	 * Constructor to implement a MoneyMarket object accepting the balance and account
	 * name as parameters
	 * @param balance
	 * @param accountName
	 */
	public MoneyMarket(  double balance, String accountName ){
		this.setBalance( balance );
		this.setName( accountName );
	}
	/**
	 * Method to perform withdrawal on account with noted penalty.
	 * 
	 * @param amount
	 * @throws Exception
	 */
	@Override
	public void withdraw( double amount ) throws Exception{
		super.withdraw( amount + (amount*penalty) );	
	}
	/**
	 * Method to return a string representation of MoneyMarket object
	 * 
	 * @return String
	 */
	@Override
	public String toString( ){
		return super.toString( );
	}

}


//Programmer: dgoodwin4
//Filename: TextFile.java 
//Last modified: 04/14/2015 
//Description: Reads the input file retrieving each number separated by a space into a int[] variable and returns that int[] array.

import java.util.*;
import java.io.*;

public class TextFile {

	public static int[] readNumbers( String filename ) throws IOException {
		
		//file instance
		File file = new file(filename);
		
		//create scanner for file
		Scanner input = new Scanner(file);
		
		//integer array of 24
		int[] numbers = new int[24];
		int i = 0;
		
		//read data file
		while (input.hasNext()) {
			
			numbers[i] = input.nextInt( );
			i++;
			
		}
		
		//close
		input.close();
		return numbers;
		
	}
	
}





//Programmer: dgoodwin4
//Filename: Transaction.java 
//Last modified: 04/30/2015 
//Description: a short description of what the program does

package com.gsu.cis.bankaccount;

public class Transaction {
	private String accountName;
	private String toAccountName;
	private String fromAccountName;
	private int function;
	private int accountType;
	private double balance;
	
	/**
	 * Description: Constructor to implement a Transaction object accepting
	 * the four basic attributes as parameters
	 *
	 * @param function
	 * @param accountType
	 * @param balance
	 * @param accountName
	 */	
	public Transaction(int function, int accountType, double balance, String accountName){
		this.function = function;
		this.accountType = accountType;
		this.balance = balance;
		this.accountName = accountName;
	}	
	/**
	 * Description: No-arg Constructor to implement a Transaction object
	 */		
	public Transaction(){
	
	}	
	/**
	 * Description: Constructor to implement a Transaction object accepting
	 * a String array of from a delimited line transaction file.
	 *
	 * @param line
	 */	
	public Transaction( String[] line ){
		setAttributes( line );
	}
	/**
	 * Description: Constructor to implement a Transaction object accepting
	 * a String array of from a delimited line transaction file.
	 *
	 * @param line
	 */	
	public void setAttributes(String[] attrArray){
		this.function = Integer.parseInt( attrArray[0] );
		// Create new Account function
		if(this.function == 1){ 
			this.accountType = Integer.parseInt( attrArray[1] );
			this.balance = Double.parseDouble( attrArray[2] );
			this.accountName = attrArray[3];
		// Deposit or Withdraw function
		}else if( this.function == 2 || this.function == 3 ){
			this.balance = Double.parseDouble( attrArray[1] );
			this.accountName = attrArray[2];
		// Transfer account
		}else if ( this.function == 4 ){
			this.balance = Double.parseDouble( attrArray[1] );
			this.fromAccountName = attrArray[2];
			this.toAccountName = attrArray[3];
		}else{
			// nothing
		}
	}
	/**
	 * Description: Returns the integer representation of the function
	 * from a transaction file.
	 *
	 * @return function
	 */	
	public int getFunction( ){ return this.function; }
	/**
	 * Description: Returns the integer representation of the account type
	 * from a transaction file.
	 *
	 * @return accountType
	 */	
	public int getAccountType( ){ return this.accountType; }
	/**
	 * Description: Returns the double representation of the amount tendered
	 * from a transaction file.
	 *
	 * @return amount
	 */
	public double getAmount( ){ return this.balance; }
	/**
	 * Description: Returns the account name for the current transaction
	 * from a transaction file
	 *
	 * @return accountName
	 */
	public String getAccountName( ){ return this.accountName; }
	/**
	 * Description: Returns the account name for the account transfer from account 
	 * for a transfer transaction
	 *
	 * @return fromAccountName
	 */
	public String getFromAccount( ){ return this.fromAccountName; }
	/**
	 * Description: Returns the account name for the account transfer to account for 
	 * a transfer transaction
	 *
	 * @return toAccountName
	 */
	public String getToAccount( ){ return this.toAccountName; }
	/**
	 * Description: Sets the function value for transaction
	 *
	 * @param function
	 */
	public void setFunction( int function ){ this.function = function; }
	/**
	 * Description: Sets the account type value for transaction
	 *
	 * @param accountType
	 */
	public void setAccountType( int accountType ){ this.accountType = accountType; }
	/**
	 * Description: Sets the amount value for transaction
	 *
	 * @param amount
	 */
	public void setAmount( double amount ){ this.balance =  amount; }
	/**
	 * Description: Sets the account name value for transaction
	 *
	 * @param accountName
	 */
	public void setAccountName( String accountName ){ this.accountName = accountName; }
	/**
	 * Description: Sets the from account name value for transfer transaction
	 *
	 * @param fromAccountName
	 */
	public void setFromAccount( String fromAccountName ){ this.fromAccountName = fromAccountName; }
	/**
	 * Description: Sets the to account name value for transfer transaction
	 *
	 * @param toAccountName
	 */
	public void setToAccount( String toAccountName ){ this.toAccountName = toAccountName; 
	}

}




//Programmer: dgoodwin4
//Filename: SemesterProject.java 
//Last modified: 04/14/2015 
//Description: a short description of what the program does

package com.gsu.cis.project;

import java.util.*;
import com.gsu.cis.bankaccount.*;

public class SemesterProject
{
	/** Attributes */
	private static Map<String, Account> theMap = new HashMap<String, Account>( );

	/**
	 * Operation: main
	 * Description: Entry/starting point for Java application which reads specified
	 * text file and processes that text file for banking transactions
	 *
	 * @param args
	 * @throws  
	 */
	public static void main ( String[] args )
	{
		/* 1. Get back file content array; each cell is a '|' delimited line
		 * 2. Split the line based on the '|' character
		 * 3. First cell in split array is the function, then call that function with the 
		 *    method below
		 * 4. Print map to file.
		 */
		try {
			String[] fileContents;
			String inputFileName = args[0];
			String outputFilename = args[1];
			fileContents = TextFile.read( inputFileName );
			
			for( String line : fileContents ){
				Transaction transaction = new Transaction( line.split( "\\|" ) );
				
				switch ( transaction.getFunction() ){
				case 1: newAccount( transaction.getAccountType(), transaction.getAmount(), transaction.getAccountName() );
				break;
				case 2: deposit( transaction.getAccountType(), transaction.getAmount(), transaction.getAccountName() );
				break;
				case 3: withdraw( transaction.getAccountType(), transaction.getAmount(), transaction.getAccountName());
				break;
				case 4: transfer( transaction.getAmount(), transaction.getFromAccount(), transaction.getToAccount() );
				break;
				case 5: printMap( outputFilename );
				break;
				case 6: break;
				default: System.out.println( "Invalid Transaction" );
				break;
				}
				
			}
		} catch (Exception e) {
			// TODO Auto-generated catch block
			System.out.println( e.getMessage() );
		}
		

	}
	/**
	 * Operation: newAccount
	 * Description:  method to create new Account type based on given parameters
	 *
	 * @param accountType
	 * @param initialBalance
	 * @param accountName
	 */
	private static void newAccount ( int accountType, double initialBalance, String accountName )
	{
		/**
		 * 1 – Checking
		 * 2 – Savings
		 * 3 – Money Market
		 * 4 – Certificate of Deposit
		 */
		double interest = 1.5;
		
		Account newAccount;
		switch ( accountType ){
		case 1: newAccount = new Checking( initialBalance, accountName );
		theMap.put( accountName, newAccount );
		break;
		case 2: newAccount = new Savings( interest, initialBalance, accountName );
		theMap.put( accountName, newAccount );
		break;
		case 3: newAccount = new MoneyMarket( initialBalance, accountName );
		theMap.put( accountName, newAccount );
		break;
		case 4: newAccount = new CertificateOfDeposit( interest, initialBalance, accountName );
		theMap.put( accountName, newAccount );
		break;
		default: System.out.println( "Invalid Transaction" );
		break;
		}
	}
	/**
	 * Operation: deposit
	 * Description:  method to find specified account by name and deposit
	 * given amount into that account.
	 *
	 * @param accountType
	 * @param amount
	 * @param accountName
	 */
	private static void deposit ( int accountType, double amount, String accountName )
	{
		try{
			Account account = findAccount( accountName );
			account.deposit(amount);
		}catch(Exception ex){
			System.out.println( ex.getMessage() );
		}
	}
	/**
	 * Operation: withdraw
	 * Description:  method to find account by account name and withdraw the 
	 * specified amount
	 *
	 * @param accountType
	 * @param amount
	 * @param accountName
	 */
	private static void withdraw( int accountType, double amount, String accountName )
	{
		try{
			Account account = findAccount( accountName );
			account.withdraw( amount );
		}catch(Exception ex){
			System.out.println( ex.getMessage() );
		}        
	}
	/**
	 * Operation: transfer
	 * Description  method to move/transfer given amount from specified "fromAccount"
	 * to specified "toAccount"
	 *
	 * @param amount
	 * @param fromAccount
	 * @param toAccount
	 */
	private static void transfer ( double amount, String fromAccount, String toAccount )
	{
		try{
			Account from = findAccount( fromAccount );
			Account to = findAccount( toAccount );

			if( to.transferFrom( from, amount ) ) 
				System.out.println("...transfer complete");

		}catch(Exception ex){
			System.out.println( ex.getMessage() );
		}
	}
	/**
	 * Operation: findAccount
	 * Description: method to find account object within map data structure
	 * by accountName
	 *
	 * @param accountName
	 * @return Account
	 */
	private static Account findAccount ( String accountName )
	{
		return theMap.get( accountName );
	}
	/**
	 * Operation: printMap
	 * Description:  prints the content/values of the Map<String, Account>
	 * data structure by calling the Account instance toString method.
	 * Also, provides an output file of the same contents.
	 *
	 * @param accountName
	 * @return Account
	 */
	private static void printMap ( String fileName )
	{
		try{
		ArrayList<String> accountList = new ArrayList<String>();
		for( Account account : theMap.values() ){
			System.out.println( account.toString() );
			accountList.add( account.toString() );
		}
		
		TextFile.write( accountList.toArray( new String[ accountList.size() ] ), fileName );
		}catch( Exception ex ){
			System.out.println( ex.toString() );
		}
	}
}
	
