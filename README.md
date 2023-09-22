# ASSIGNMENT
QUESTION 1: public class PalindromeChecker {
    public static void main(String[] args) {
        String inputStr = "ABCDCBA";
        
        if (isPalindrome(inputStr)) {
            System.out.println("Palindrome");
        } else {
            System.out.println("Not Palindrome");
        }
    }
    
    public static boolean isPalindrome(String s) {
        // Remove spaces and convert to lowercase (if needed)
        s = s.replaceAll(" ", "").toLowerCase();
        
        int left = 0;
        int right = s.length() - 1;
        
        while (left < right) {
            if (s.charAt(left) != s.charAt(right)) {
                return false;
            }
            left++;
            right--;
        }
        
        return true;
    }
}
OUESTION 2: public class CharacterCount {
    public static void main(String[] args) {
        String inputStr = "Take u forward is Awesome";
        
        int vowelsCount = 0;
        int consonantsCount = 0;
        int spacesCount = 0;
        
        inputStr = inputStr.toLowerCase(); // Convert the string to lowercase for easier comparison
        
        for (int i = 0; i < inputStr.length(); i++) {
            char ch = inputStr.charAt(i);
            
            if (ch == ' ') {
                spacesCount++;
            } else if (ch >= 'a' && ch <= 'z') {
                if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u') {
                    vowelsCount++;
                } else {
                    consonantsCount++;
                }
            }
        }
        
        System.out.println("Vowels: " + vowelsCount);
        System.out.println("Consonants: " + consonantsCount);
        System.out.println("White spaces: " + spacesCount);
    }
}


OUESTION 3: public class RemoveVowels {
    public static void main(String[] args) {
        String inputStr = "take u forward";
        
        String result = removeVowels(inputStr);
        
        System.out.println("Input String: " + inputStr);
        System.out.println("String after removing vowels: " + result);
    }
    
    public static String removeVowels(String str) {
        StringBuilder result = new StringBuilder();
        
        // Convert the input string to lowercase for easier comparison
        str = str.toLowerCase();
        
        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            
            // Check if the character is not a vowel (a, e, i, o, u)
            if (ch != 'a' && ch != 'e' && ch != 'i' && ch != 'o' && ch != 'u') {
                result.append(str.charAt(i));
            }
        }
        
        return result.toString();
    }
}


QUESTION 4: public class RemoveWhitespaces {
    public static void main(String[] args) {
        String inputStr = "Take you forward";
        
        String result = removeWhitespaces(inputStr);
        
        System.out.println("Input String: " + inputStr);
        System.out.println("String after removing whitespaces: " + result);
    }
    
    public static String removeWhitespaces(String str) {
        // Use the replaceAll() method to remove all whitespaces
        return str.replaceAll("\\s", "");
    }
}


QUESTION 5: public class RemoveNonAlphabets {
    public static void main(String[] args) {
        String inputStr = "take12% *&u ^$#forward";
        
        String result = removeNonAlphabets(inputStr);
        
        System.out.println("Input String: " + inputStr);
        System.out.println("String after removing non-alphabet characters: " + result);
    }
    
    public static String removeNonAlphabets(String str) {
        StringBuilder result = new StringBuilder();
        
        // Convert the input string to lowercase for easier comparison
        str = str.toLowerCase();
        
        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            
            // Check if the character is an alphabet (a to z)
            if (ch >= 'a' && ch <= 'z') {
                result.append(str.charAt(i));
            }
        }
        
        return result.toString();
    }
}


QUESTION 6: public class ReverseString {
    public static void main(String[] args) {
        String inputStr = "123xyz";
        
        String reversedStr = reverseString(inputStr);
        
        System.out.println("Input String: " + inputStr);
        System.out.println("Reversed String: " + reversedStr);
    }
    
    public static String reverseString(String str) {
        StringBuilder reversed = new StringBuilder();
        
        for (int i = str.length() - 1; i >= 0; i--) {
            reversed.append(str.charAt(i));
        }
        
        return reversed.toString();
    }
}

QUESTION 7: 
public class CapitalizeFirstAndLast {
    public static void main(String[] args) {
        String inputStr = "take u forward is awesome";
        
        String result = capitalizeFirstAndLast(inputStr);
        
        System.out.println("Input String: " + inputStr);
        System.out.println("String after capitalizing first and last characters: " + result);
    }
    
    public static String capitalizeFirstAndLast(String str) {
        StringBuilder result = new StringBuilder();
        
        // Split the input string into words based on whitespace
        String[] words = str.split(" ");
        
        for (String word : words) {
            if (word.length() == 0) {
                // Handle empty words
                result.append(" ");
            } else if (word.length() == 1) {
                // Handle single-character words
                result.append(Character.toUpperCase(word.charAt(0)));
            } else {
                // Capitalize the first character and the last character of the word
                result.append(Character.toUpperCase(word.charAt(0)))
                      .append(word.substring(1, word.length() - 1))
                      .append(Character.toUpperCase(word.charAt(word.length() - 1)));
            }
            
            // Add a space between words
            result.append(" ");
        }
        
        return result.toString().trim(); // Trim to remove the trailing space
    }
}

QUESTION 8:  import java.util.Arrays;

public class AnagramChecker {
    public static void main(String[] args) {
        String str1 = "CAT";
        String str2 = "ACT";
        
        boolean result = areAnagrams(str1, str2);
        
        System.out.println("Are \"" + str1 + "\" and \"" + str2 + "\" anagrams? " + result);
    }
    
    public static boolean areAnagrams(String s1, String s2) {
        // Remove spaces and convert to lowercase (if needed)
        s1 = s1.replaceAll(" ", "").toLowerCase();
        s2 = s2.replaceAll(" ", "").toLowerCase();
        
        // Check if the lengths of both strings are different
        if (s1.length() != s2.length()) {
            return false;
        }
        
        // Convert strings to character arrays and sort them
        char[] charArray1 = s1.toCharArray();
        char[] charArray2 = s2.toCharArray();
        Arrays.sort(charArray1);
        Arrays.sort(charArray2);
        
        // Compare sorted character arrays
        return Arrays.equals(charArray1, charArray2);
    }
}
