# CSE_Lab_Codes
Java codes for Lab Classes of Computer Science &amp; Engineering's Courses<br>
#### Example 1: A java code to count character, word, special character, white spaces from a string inputed by user

```
import java.util.Scanner;
public class Count {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String str = sc.nextLine();
        
        int charCount = 0;
        int wordCount = 0;
        int specialCharCount = 0;
        int spaceCount = 0;

        for (int i = 0; i < str.length(); i++) {
            if (Character.isLetter(str.charAt(i))) {
                charCount++;
            } else if (Character.isWhitespace(str.charAt(i))) {
                spaceCount++;
            } else {
                specialCharCount++;
            }
        }

        String[] words = str.split("\\s+");
        wordCount = words.length;

        System.out.println("Number of characters: " + charCount);
        System.out.println("Number of words: " + wordCount);
        System.out.println("Number of special characters: " + specialCharCount);
        System.out.println("Number of white spaces: " + spaceCount);
    }
}
```
#### Output : ![Screenshot 2023-01-23 145243](https://user-images.githubusercontent.com/27882232/213999113-d409ce6c-c64b-4e40-87aa-5117c1abb0cd.jpg)
***
#### Example 2: A java code to count new lines, white spaces & number digit from a stream inputed by user

```
import java.util.Scanner;

public class CharacterNewLinesSpaceDigit {
    public static void main(String[] args) {
        int newlines = 0, blankSpaces = 0, digits = 0;
        char a=' ';
        Scanner scan = new Scanner(System.in);
        System.out.println("Enter a character stream: ");
        do {
            newlines++;
            String input = scan.nextLine();
            for (int i = 0; i < input.length(); i++) {
                a = input.charAt(i);
                if (a == ' ') {
                    blankSpaces++;
                } else if (Character.isDigit(a)) {
                    digits++;
                }
                if(a == '*'){
                    break;
                }
            }
        } while (a != '*');
        System.out.println("Newline: " + newlines);
        System.out.println("Blank Space: " + blankSpaces);
        System.out.println("Digit: " + digits);
        
    }
}
```
#### Output :![Screenshot 2023-01-23 150535](https://user-images.githubusercontent.com/27882232/214001600-ced6d377-b30e-4c59-a318-800a64e57e91.jpg)
***
#### Example 3: A java code to count keywords from a stream inputed by user

```
import java.util.Scanner;

public class KeywordCount {
    public static void main(String[] args) {
        int ifCount = 0, elseCount = 0, gotoCount = 0, whileCount = 0, forCount = 0, doCount = 0;
        String a;
        Scanner scan = new Scanner(System.in);
        System.out.println("Enter a character stream: ");
        do {
            a = scan.next();
            if (a.equals("if")) {
                ifCount++;
            } else if (a.equals("else")) {
                elseCount++;
            } else if (a.equals("goto")) {
                gotoCount++;
            } else if (a.equals("while")) {
                whileCount++;
            } else if (a.equals("for")) {
                forCount++;
            } else if (a.equals("do")) {
                doCount++;
            }
        } while (!a.equals("*"));
        System.out.println("Total 'if' found: " + ifCount);
        System.out.println("Total 'else' found: " + elseCount);
        System.out.println("Total 'goto' found: " + gotoCount);
        System.out.println("Total 'while' found: " + whileCount);
        System.out.println("Total 'for' found: " + forCount);
        System.out.println("Total 'do' found: " + doCount);
    }
}

```
#### Output : ![Screenshot 2023-01-23 154052](https://user-images.githubusercontent.com/27882232/214008673-d532d99e-9c3e-4aef-bbd9-5fd266f1156e.jpg)

***
#### Example 4 : A java code to count new lines, white spaces & number digit from a stream from a file

```
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class CharacterCountFromFile {
    public static void main(String[] args) {
        int newlines = -1, blankSpaces = 0, digits = 0;
        char a;
        
        File file = new File("E:/testtext.txt");
        try {
            Scanner scan = new Scanner(file);
			/*
			 * while (scan.hasNextLine()) { newlines++; String line = scan.nextLine(); for
			 * (int i = 0; i < line.length(); i++) { a = line.charAt(i); if (a == ' ') {
			 * blankSpaces++; } else if (Character.isDigit(a)) { digits++; } if(a == '*'){
			 * break; } } }
			 */
            String fileContent = "";
            while (scan.hasNextLine()) {
                newlines++;
                String line = scan.nextLine();
                fileContent += line + "\n";
                for (int i = 0; i < line.length(); i++) {
                    a = line.charAt(i);
                    if (a == ' ') {
                        blankSpaces++;
                    } else if (Character.isDigit(a)) {
                        digits++;
                    }
                    if(a == '*'){
                        break;
                    }
                }
            }
            System.out.println("File Content:\n" + fileContent);


            scan.close();
        } catch (FileNotFoundException e) {
            System.out.println("File not found: " + file);
        }
        System.out.println("------------------------------");

        System.out.println("Newline: " + newlines);
        System.out.println("Blank Space: " + blankSpaces);
        System.out.println("Digit: " + digits);
    }
}

```
#### Input File : [testtext.txt](https://github.com/habibcse009/JavaCodes_Character_Stream/files/10478460/testtext.txt)

#### Output :![Screenshot 2023-01-23 154551](https://user-images.githubusercontent.com/27882232/214009348-60a56688-fb84-408a-8032-6c7e50955b6a.jpg)
