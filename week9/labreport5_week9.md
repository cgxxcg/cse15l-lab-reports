# Lab report 5

## Part 1

Student:  I'm trying to read in the integer from "input.txt" and keep track of the "count" and "sum". But I'm getting weird output. 
I think the problem might be an issue with how I'm reading the input file. Here is my command on terminal and output. <br>
<img width="469" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/339f89f9-9a9b-4262-8f14-4b9aac33b9f6">

TA: Hi, you can find a way to figure out what happens to the variables inside the loop. There is a simple way to do it and show the result in the terminal!

Student: <br>
<img width="599" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/23cdea07-56bf-42ec-946c-13d8d8c29579"> <br>
<img width="470" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/c4a13316-65f0-4b78-89b5-327dbdd1a1c6"> <br>
Thank you! I printed out the "count" and "sum" inside the loop, and I found that "count" is not incrementing. Another problem is that the printed results are concatenated and it looks like "112", but it is actually "1" for "count", and "12" for "sum". 


Directory Structure: <br>
<img width="274" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/7533890f-5a08-4e06-bed5-59bc5449085b"> <br>
For run.sh: <br>

```
javac Main.java
if [ $? -eq 0 ]; then
    java Main
fi
```

<br>
For input.txt: <br>

```
1 2 4 5
```

<br>
For Main.java before fixing the bug: <br>

```
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        int count = 0;
        int sum = 0;
        try (Scanner scanner = new Scanner(new File("input.txt"))) {
            while (scanner.hasNextInt()) {
                sum = sum + scanner.nextInt();
            }
        } catch (FileNotFoundException e) {
            System.out.println("File not found: " + e.getMessage());
        }
        count ++;
        System.out.print(count);
        System.out.print(sum);
    }
}
```


Command line to trigger the bug: <br>
<img width="480" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/3c8fdb13-b187-420d-9e64-b545c0816094"> <br>
To fix the bug, I put the count incrementation line inside while loop, so each time we're adding the new element, the count increments too. I also added "\n" and two strings in the print statements for better visualization. <br>

```
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        int count = 0;
        int sum = 0;
        try (Scanner scanner = new Scanner(new File("input.txt"))) {
            while (scanner.hasNextInt()) {
                sum = sum + scanner.nextInt();
                count +=1;
            }
        } catch (FileNotFoundException e) {
            System.out.println("File not found: " + e.getMessage());
        }
        
        System.out.print("Sum: "+ sum + "\n");
        System.out.print("Count: "+ count + "\n");
    }
}
```

<img width="423" alt="image" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/e4f502f9-8869-4b2a-ba69-4bfefc88f917">


## Part 2
I think Vim and file exploration are cool. Being able to edit files and do a bunch of commands to get the file information on the terminal is fun. My friend who's taking CSE 30 told me that ssh will also be useful for that class. 

