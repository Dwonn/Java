# Java
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
