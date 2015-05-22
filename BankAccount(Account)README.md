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
			
