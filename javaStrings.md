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
    
    
 
 
