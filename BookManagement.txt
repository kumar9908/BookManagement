import java.util.LinkedHashMap;
import java.util.Map;
import java.util.Scanner;

public class BookManagement {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Map<Integer, String> book = new  LinkedHashMap<Integer, String>();
		Scanner sc = new Scanner(System.in);
		int option,bookId;
		String name;
		do {
			System.out.println("1.Add Book");
			System.out.println("2.Find Book");
			System.out.println("3.Update Book");
			System.out.println("4.Delete Book");
			System.out.println("5.Display All Books");
			System.out.println("6.EXIT");
			System.out.println("Enter your choice : ");
			option = sc.nextInt();
			switch (option) {
			case 1: {
				//Add book
				System.out.println("Enter the book id : ");
				bookId = sc.nextInt();
				System.out.println("Enter the book name : ");
				name = sc.next();
				book.put(bookId, name);
				break;
			}
			case 2: {
				//Find book
				System.out.println("Enter the book id : ");
				bookId = sc.nextInt();
				if (book.containsKey(bookId)) {
					 
		            // Mapping
		            name = book.get(bookId);
		 
		            // Printing value for the corresponding key
		            System.out.println("Name of Book : "+name);
				}
				else {
					System.out.println("Book not Found!");
				}
				break;
			}
			case 3: {
				//Update book details
				System.out.println("Enter the book id : ");
				bookId = sc.nextInt();
				if (book.containsKey(bookId)) {
					System.out.println("Enter the new book name : ");
					name = sc.next();
					book.put(bookId, name);
				}
				else {
					System.out.println("Book not found !");
				}
				break;
				
			}
			case 4: {
				//Delete book
				System.out.println("Enter the book id : ");
				bookId = sc.nextInt();
				book.remove(bookId);
				break;
				
			}
			case 5: {
				//Display Books
				for (Map.Entry<Integer, String> e : book.entrySet())
		            System.out.println("Book id : " + e.getKey() + "   Book Name : " + e.getValue());
				//System.out.println(book);
				break;
			}
			case 6: {
				//Exit
				return;
			}
			default:
				System.out.println("Invalid Input");
			}
			System.out.println("\n");
		} while (option!=6);
	}
}