# Java String Notes
All important questions and notes.

<h1>What is String?</h1>

<p>Strings are defined as an array of characters. The difference between a character array and a string is the string is terminated with a special character ‘\0’.</p>

<h1>Check if given String is Pangram or not</h1><br>
<p>A pangram is a sentence containing every letter in the English Alphabet.</p>


```java
class HelloWorld {
    public static void main(String[] args) {
        // System.out.println("Hello, World!");
        String str
            = "The quick brown fox jumps over the lazy dog";
            
            if(check(str)){
                System.out.println("It Is pangram");
            }else{
                System.out.println("Not Pangram");
            }
 
    }

    public static boolean check(String str){
        
        boolean[] mark = new boolean[26];
        
        int index = 0;
        
        for(int i = 0; i < str.length(); i++){
            if('A' <= str.charAt(i) && str.charAt(i) <= 'Z'){
                index = str.charAt(i) - 'A';
            } else if('a' <= str.charAt(i) && str.charAt(i) <= 'z'){
                index = str.charAt(i) - 'a';
            }else{
                continue;
            }
                 mark[index] = true; 

        }

        for(int i = 0; i <= 25; i++){
            if(mark[i] == false)
            return (false);
        }
        return (true);
    }
}
```

<h1>Function to copy string</h1>


```java
class GFG{    
static void myCopy(char s1[], char s2[]){

    int i = 0;
    for (i = 0; i < s1.length; i++)
         s2[i] = s1[i];
}
 
public static void main(String[] args)
{
    char s1[] = "GEEKSFORGEEKS".toCharArray();
    char s2[] = new char[s1.length];
    myCopy(s1, s2);
    System.out.println(String.valueOf(s2));
}
}
```

<h1>Missing characters to make a string Pangram</h1>

```java
class GFG{
     
private static ArrayList<Character>missingChars(
    String str, int strLength)
{
    final int MAX_CHARS = 26;
     
    // A boolean array to store characters
    // present in string.
    boolean[] present = new boolean[MAX_CHARS];
    ArrayList<Character> charsList = new ArrayList<>();
     
    // Traverse string and mark characters
    // present in string.
    for(int i = 0; i < strLength; i++)
    {
        if ('A' <= str.charAt(i) &&
                   str.charAt(i) <= 'Z')
            present[str.charAt(i) - 'A'] = true;
        else if ('a' <= str.charAt(i) &&
                        str.charAt(i) <= 'z')
            present[str.charAt(i) - 'a'] = true;
    }
     
    // Store missing characters in alphabetic
    // order.
    for(int i = 0; i < MAX_CHARS; i++)
    {
        if (present[i] == false)
            charsList.add((char)(i + 'a'));
    }
    return charsList;
}
 
// Driver Code
public static void main(String[] args)
{
    String str = "The quick brown fox jumps " +
                 "over the dog";
                  
    ArrayList<Character> missing = GFG.missingChars(
        str, str.length());
         
    if (missing.size() >= 1)
    {
        for(Character character : missing)
        {
            System.out.print(character);
        }
    }
}
}
 ```
 
 <h1>Removing punctuations from a given string</h1>
 
 ```java
 public class Test
{
    public static void main(String[] args)
    {
        // input string
        String str = "Welcome???@@##$ to#$% Geeks%$^for$%^&Geeks";
         
        // similar to Matcher.replaceAll
        str = str.replaceAll("\\p{Punct}","");
         
        System.out.println(str);
    }
     
}
```

<h1>Program to check if input is an integer or a string</h1>

```java
static boolean isNumber(String s)
    {
        for (int i = 0; i < s.length(); i++)
            if (Character.isDigit(s.charAt(i)) == false)
                return false;
 
        return true;
    }
 
    // Driver code
    static public void main(String[] args)
    {
        // Saving the input in a string
        String str = "6790";
 
        // Function returns 1 if all elements
        // are in range '0 - 9'
        if (isNumber(str))
            System.out.println("Integer");
 
        // Function returns 0 if the
        // input is not an integer
        else
            System.out.println("String");
    }
```
    
    
<h1>Java program to swap first and last characters of words in a sentence</h1>

```java
class SwapFirstLastCharacters {
    static String count(String str)
    {
        // Create an equivalent char array
        // of given string
        char[] ch = str.toCharArray();
        for (int i = 0; i < ch.length; i++) {
 
            // k stores index of first character
            // and i is going to store index of last
            // character.
            int k = i;
            while (i < ch.length && ch[i] != ' ')
                i++;
             
            // Swapping
            char temp = ch[k];
            ch[k] = ch[i - 1];
            ch[i - 1] = temp;
 
            // We assume that there is only one space
            // between two words.
        }
        return new String(ch);
    }
    public static void main(String[] args)
    {
        String str = "geeks for geeks";
        System.out.println(count(str));
    }
}
```

<h1>Get the first letter of each word in a string using regex</h1>

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;
 
public class Test {
    static void printFirst(String s)
    {
        Pattern p = Pattern.compile("\\b[a-zA-Z]");
        Matcher m = p.matcher(s);
 
        while (m.find())
            System.out.print(m.group());
 
        System.out.println();
    }
 
    public static void main(String[] args)
    {
        String s1 = "Geeks for Geeks";
        String s2 = "A Computer Science Portal for Geeks";
        printFirst(s1);
        printFirst(s2);
    }
}
```

<h1>Reverse words in a given String in Java</h1>

```java
import java.util.regex.Pattern;
public class Exp {
 
    // Method to reverse words of a String
    static String reverseWords(String str)
    {
 
        // Specifying the pattern to be searched
        Pattern pattern = Pattern.compile("\\s");
 
        // splitting String str with a pattern
        // (i.e )splitting the string whenever their
        // is whitespace and store in temp array.
        String[] temp = pattern.split(str);
        String result = "";
 
        // Iterate over the temp array and store
        // the string in reverse order.
        for (int i = 0; i < temp.length; i++) {
            if (i == temp.length - 1)
                result = temp[i] + result;
            else
                result = " " + temp[i] + result;
        }
        return result;
    }
 
    
    public static void main(String[] args)
    {
        String s1 = "Welcome to geeksforgeeks";
        System.out.println(reverseWords(s1));
 
        String s2 = "I love Java Programming";
        System.out.println(reverseWords(s2));
    }
}

Output
geeksforgeeks to Welcome
Programming Java love I
```

<h1>Reverse a String in Java 2 Methods</h1>
<h4>1<sup>st</sup></h4>

```java
import java.io.*;
import java.util.Scanner;
  
class GFG {
    public static void main (String[] args) {
        
        String str= "Geeks", nstr="";
        char ch;
        
      System.out.print("Original word: ");
      System.out.println("Geeks"); //Example word
        
      for (int i=0; i<str.length(); i++)
      {
        ch= str.charAt(i); //extracts each character
        nstr= ch+nstr; //adds each character in front of the existing string
      }
      System.out.println("Reversed word: "+ nstr);
    }
}
```

<h4>2<sup>nd</sup></h4>

```java
import java.lang.*;
import java.io.*;
import java.util.*;
  
// Class of ReverseString
class ReverseString {
    public static void main(String[] args)
    {
        String input = "GeeksForGeeks";
  
        // convert String to character array
        // by using toCharArray
        char[] try1 = input.toCharArray();
  
        for (int i = try1.length - 1; i >= 0; i--)
            System.out.print(try1[i]);
    }
}
```

<h1>Check if String is Palindrome or not</h1>

```java
import java.util.*;

class HelloWorld {
    public static void main(String[] args) {
        // System.out.println("Hello, World!");
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        boolean flag = true;
        
        str = str.toLowerCase();
        
        for(int i = 0; i < str.length()/2; i++){
            if(str.charAt(i) != str.charAt(str.length() -i-1)){
                flag = false;
                break;
            }
        }
        
        if(flag){
            System.out.println("String is Palindrome");
        }else{
            System.out.println("Not Palindrome");
        }
    }
}
```








    
 
 
