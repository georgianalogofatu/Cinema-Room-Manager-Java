import java.util.Scanner;

public class Cinema {
	final static Scanner scanner = new Scanner(System.in);
	
	public static void displayCinema(int numberOfSeatsEachRow, int numberOfRows, String[][] matrix) {
		System.out.println("Cinema:");
      	System.out.print("  ");
		for (int i = 1; i <= numberOfSeatsEachRow; i++)
			System.out.print(i + " ");
		
		System.out.println();
		
		for( int i = 0; i < numberOfRows; i++ ) {
			System.out.print(i+1 +" ");
			for (int j = 0; j < numberOfSeatsEachRow; j++)
		        System.out.print(matrix[i][j] + " ");
			System.out.println();
		}
		
	}
	
	
	public static void main(String[] args) {
		
		System.out.println("Enter the number of rows:");
		int numberOfRows = scanner.nextInt();
		System.out.println("Enter the number of seats in each row:");
		int numberOfSeatsEachRow = scanner.nextInt();
		int numberOfSeats = numberOfSeatsEachRow * numberOfRows;
		int priceOneTicket;
		int value;
		int rowNumber;
		int seatNumber;
		float numberOfPurchasedTickets = 0;
		float percentage = 0;
		int currentIncome = 0;
		int totalIncome = 0;
	    String[][] matrix = new String[numberOfRows][numberOfSeatsEachRow];
		
		for( int i = 0; i < numberOfRows; i++ )
			for (int j = 0; j < numberOfSeatsEachRow; j++)
				matrix[i][j] = "S";
		
    do {
		System.out.println("\n1. Show the seats.\n2. Buy a ticket\n3. Statistics\n0. Exit");
		value = scanner.nextInt();
		switch(value) {
		case 1:
			displayCinema(numberOfSeatsEachRow, numberOfRows,  matrix);
		    break;
		case 2:
			do {
				System.out.println("\nEnter a row number: ");
				rowNumber = scanner.nextInt();
				System.out.println("Enter a seat number in that row: ");
				seatNumber = scanner.nextInt();
				
				while(rowNumber < 0 || rowNumber > matrix.length || seatNumber < 0 || seatNumber > matrix.length)
				{
					System.out.println("\nWrong input!");
					System.out.println("\nEnter a row number: ");
					rowNumber = scanner.nextInt();
					System.out.println("Enter a seat number in that row: ");
					seatNumber = scanner.nextInt();
					
				}
				
				
				if(matrix[rowNumber-1][seatNumber-1] == "B")
					System.out.println("\nThat ticket has already been purchased!");
				
				} while(matrix[rowNumber-1][seatNumber-1] == "B");
			
			if(numberOfSeats < 60) {
			    priceOneTicket = 10;
			} else {
				if ( rowNumber <=  numberOfRows / 2)
				   priceOneTicket = 10;
				else
				   priceOneTicket = 8;
			}
		    System.out.println("\nTicket price: $" + priceOneTicket);
		    matrix[rowNumber-1][seatNumber-1] = "B";
		    numberOfPurchasedTickets ++;
		    percentage = numberOfPurchasedTickets * 100 / numberOfSeats;
		    currentIncome += priceOneTicket;
		    break;
		case 3:
			System.out.println("\nNumber of purchased tickets: " + (int) numberOfPurchasedTickets);
			System.out.printf("Percentage: %.2f",percentage);
			System.out.println("%");
			System.out.println("Current Income: $" + currentIncome);
			
			if(numberOfSeats < 60) {
			    totalIncome = numberOfSeats * 10;
			} else {
				totalIncome = (numberOfRows / 2) * numberOfSeatsEachRow * 10 + ( numberOfRows - numberOfRows / 2 ) * numberOfSeatsEachRow * 8;
			}
			System.out.println("Total Income: $" + totalIncome);
			break;
		case 0:
			break;
		default: System.out.println("Please enter 0, 1, 2 or 3/n");
		     
		}
    } while(value != 0);
		
	
			
	}
}
