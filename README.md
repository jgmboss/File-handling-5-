import java.io.FileReader;
import java.io.BufferedReader;
import java.io.IOException;
import java.util.Scanner;

public class Qfive
{
    public static void main (String [] args) throws IOException {
        Scanner input = new Scanner(System.in);
        boolean end; 
        while (end = false) {
            System.out.println ("1. Search for a term");
            System.out.println ("2. Search for a keyweord in description");
            System.out.println ("3. End");
            System.out.println ("Please select a 1, 2 or 3");
            int option = input.nextInt();
            if (option == '1'){
                System.out.println ("enter the term you would like to search");
                String search = input.nextLine();
                option1(search);

            } 
            else if (option == '2'){
                System.out.println ("enter a desription you would like to search");
                String description = input.nextLine();
                option2(description);

            }
            else if (option == '3'){
                end = true;
            }
            else {
                System.out.println ("enter valid number");

            }

        }
    }

    public static void option1 (String search) throws IOException {
        FileReader fr = new FileReader ("Macintosh HD \\ Users \\ rexpon \\ Documents.txt");
        BufferedReader br = new BufferedReader(fr);
        String line;
        boolean found;
        while((line = br.readLine()) != null){
            line = br.readLine();
            if (line.equalsIgnoreCase(search)){
                System.out.println("word found "+ line);
                found = true;
                break;
            }
        }
        if (found = false){
            System.out.println ("search not found");
        }
    }
    
    public static void option2 (String description) throws IOException{
        FileReader fr = new FileReader (".txt");
        BufferedReader br = new BufferedReader(fr);
        String line1;
        String line2;
        boolean found;
        while ((line1 = br.readLine()) != null) {
            line2 = br.readLine();
            if (line2.contains(description)){
                found = true;
                System.out.println ("word found "+ line1 + line2);
            }
        }
        if (found = false){
            System.out.println("search not found");
        }
    }
}
