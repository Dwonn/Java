# Java
// Programmer: DGoodwin4
// Filename: ComputeArea.java
// Last modified: 2015.01.25
// Description: Computing Area of Triangle in Inches, Centimeters & Square Feet

    import java.util.Scanner; // Scanner is in the java.util package

    public class ComputeArea {
    public static void main(String[] args) {
		//Create a scanner object
		Scanner input = new Scanner(System.in);
	//Declare the constant values
	final double HALF = 0.5;
	final double CENT_CONV = 6.4516;
	final double SQFT_CONV = 144;
	
	// Prompt the user to enter a base
	System.out.print("Enter a number for base in inches: ");
	double base = input.nextDouble();

	// Prompt the user to enter a height
	System.out.print("Enter a number for height in inches: ");
	double height = input.nextDouble();

	// Compute area for Triangle; 
	double area = (base * height) * 0.5;
	
	// Display results in square inches
	System.out.println("The area for the square of base in Inches is " +
		height + " is " + area);
	
	// Display results in square centimeters
	System.out.println("The area for the square of base in Centimeters is " +
		area*CENT_CONV);

	// Display results in square feet
	System.out.println("The area for the Square Feet is  " +
		area/SQFT_CONV); 

      }
    }

// Programmer: DGoodwin4
// Filename: SubtractionQuiz.java
// Last modified: 2015.01.25
// Description: Subtraction quiz with right or wrong response

    import java.util.Scanner;

    public class SubtractionQuiz{
    public static void main(String[] args) {
		// Freebie
		int number1 = (int )(Math.random(  ) * 10 );
    		int number2 = (int )(Math.random(  ) * 10 );

		if (number1 < number2) {
			int temp = number1;
			number1 = number2;
			number2 = temp;
		}

	System.out.print
		("What is " + number1 + " - " + number2 + "? ");
		Scanner input = new Scanner(System.in);
		int answer = input.nextInt();

	if (number1 - number2 == answer)
		System.out.println("You are correct!");
	else
		System.out.println("You answer is wrong\n" + number1 + " - "
			+ number2 + " is " + (number1 - number2));
      }
    }


	
	


// Programmer: DGoodwin4
// Filename: ImproperFractions.java
// Last modified: 2015.02.2
// Description: Program to evaluate fractions

    import java.util.*;

    public class ImproperFractions {
    public static void main(String args[]) {
		Scanner input = new Scanner(System.in);

		System.out.print("Enter a numerator: ");
		int numerator = input.nextInt();
		System.out.print("Enter a denominator: ");
		int denominator = input.nextInt();

	if (numerator < denominator) {
		System.out.println(numerator + " / " + denominator + " is a proper fraction"); 
	}
	
	else if( numerator % denominator == 0 ) {
		System.out.print(numerator + " / " + denominator + " is an improper fraction ");
	
		
		System.out.println("it can be reduced to " + numerator/denominator);
	}
	else{ 
		System.out.print(numerator + " / " + denominator + " is an improper fraction ");
		System.out.print("and its mixed fraction is " + numerator/denominator + " + " + numerator % denominator + " / " + denominator); 
    }
      }

// Programmer: DGoodwin4
// Filename: RepeatAdditionQuiz
// Last modified: 2/3/2015
// Description: This example creates a program to let a first grader practice additions. 

    import java.util.Scanner;
      public class AdditionQuiz {
    public static void main( String[] args ) {
      int number1 = ( int )( System.currentTimeMillis( ) % 10 );
      int number2 = ( int )( System.currentTimeMillis() / 7 % 10 );

    // Create a Scanner
    Scanner input = new Scanner( System.in );

    System.out.print( "What is " + number1 + " + " + number2 + "? " );

    int answer = input.nextInt( );

    while ( number1 + number2 != answer) {
    System.out.print("Wrong answer. Try again. What is " + number1 + " + " + number2 + "? ");  
    answer = input.nextInt();
	}

    System.out.println("You got it!");
    }
    }



// Programmer: dgoodwin4	
// Filename: MaxValue.java
// Last modified: 2015.02.10
// Description: A program to find the max value and the number of occurrences.

    import java.util.Scanner;

    public class MaxValue {
    public static void main(String[] args) {
		//Scanner import
		Scanner input = new Scanner(System.in);
	
	// TODO Auto-generated method stub
	int max = 0;
	int count = 1;
	int userinput; 


	//Prompt user to enter integer 
	System.out.print("Enter a list of integers, enter in 0 when complete; ");

	do{
		userinput = input.nextInt();
		if(userinput > max){
			max = userinput;
			count = 1;
		}else if(userinput == max){
			count++;
		}
	}while(userinput !=0);


    System.out.println("Max number is " + max);
    System.out.println("Occurrence of max is " + count);
	
    }
     }
    }
      }



// Programmer: dgoodwin4
// Filename: SumNumbers.java
// Last Modified: 02/10/2015
// Description: Write a program that reads integers and return the sum.

    import java.util.*;
    public class SumNumbers {
    public static void main(String[] args) {

      int sum = sumUp();
		System.out.println( "The sum of the numbers is " + sum);
    	}
		
    // TODO Auto-generated method stub
    public static int sumUp(){
    
    // Create a Scanner
    Scanner input = new Scanner(System.in);
		// Declare variables for n and sum
		int sum = 0;
		int number = 0;
		
		System.out.print( "Enter numbers:" );
		  number = input.nextInt();

		while( number != 0 ){
			sum = sum + number;
			number = input.nextInt();
    	}
		
		return sum;
      }
    }
    System.out.println("Max number is " + max);
    System.out.println("Occurrence of max is " + count);
    	}
    }



// Programmer: DGoodwin4	
//Filename: FindMinimum.java
//Last Modified: 2015.02.17
//Description: Create a method that returns the index of the smallest element in an array to integers.


    import java.util.*;

    public class FindMinimum { 
    public static void main(String[] args) {
	
    // Declare array of 10
    double[] numbers = new double[ 10 ];

    // Ask user to enter ten numbers
    Scanner input = new Scanner( System.in );
    System.out.print( "Enter ten numbers: " );

    // Loop
    for( int i = 0; i < numbers.length; i++ )
		numbers[ i ] = input.nextDouble();
    //call
    System.out.println("The index of the min is " + indexOfSmallestElement (numbers));
    }
    public static int indexOfSmallestElement(double[] array) {
		double min = array[ 0 ];
		int minIndex = 0;
		
		for (int i = 1; i < array.length; i++)
			if (min > array[ i ]) {
				min = array[ i ];
				minIndex = i;
		}
    return minIndex;
    } 
    }



//Programmer: Dgoodwin4
// Filename: MatrixSum.java
// Last modified: 2015.02.24
// Description: A multidimensional array calculating the sum of columns

    public class MatrixSum {
    public static void main(String[] args) {
    java.util.Scanner input = new java.util.Scanner( System.in );	
	
    System.out.print("Enter a 3 by 4 matrix row by row: ");
    //2. Create my matrix array with 3 rows, 4 columns
    double [][] m = new double[ 3 ][ 4 ];
	  
    //3. Loop through values on command line
    for( int row = 0; row < m.length; row++){
		for( int column = 0; column < m[ row ].length; column++ )
			m[ row ][ column ] = input.nextDouble();
    }

    //4. Loop through each set, summing the column
    for( int column = 0; column < m[ 2 ].length; column++ ){
		System.out.println( "Sum of the elements at column " + column + "; " + sumColumn(m, column) );
     }
    }
    
    public static double sumColumn( double[][] m, int columnIndex ){
		//1. declare a running total variable…
		double total = 0;
		//2. Loop through each row, summing the column at that index
		for( int i = 0; i < m.length; i++){
			total = total + m[ i ][ columnIndex ];
		}
		return total; 
      }
    }
