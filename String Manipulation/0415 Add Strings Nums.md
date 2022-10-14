### Things to Note:
- use StringBuilder() to create a mutable string of chars to store result
    - whereas String objects are immutable
- keep track of indices in our given 2 strings
- REMEMBER to add a carry number: if sum > 9, carry 1 to the next index
    - check remaining carryings in the end! 
- REMEMBER to reverse the string in the end
    - because though we look back to front from our input, we append front to back to our result
- 


```java
public String addStrings(String num1, String num2) {
    // declare indices to walk through the two strings 
    int num1_index = num1.length() - 1;
    int num2_index = num2.length() - 1;
    int carry = 0; // to carry over sums over 9
    StringBuilder result = new StringBuilder(); // store result
    while (num1_index >= 0 || num2_index >= 0) {
        int n1 = 0, n2 = 0;
        if (num1_index >= 0)
            n1 = num1.charAt(num1_index) - '0';
        if (num2_index >= 0)
            n2 = num2.charAt(num2_index) - '0';
        int sum = n1 + n2 + carry;

        // add sum to result (only values 0-9) 
        // i.e. 6+7=13, only want to add 3 at curr index
        result.append((sum % 10));
        // i.e. 6+7=13, want to add 1 (tenth index) to the next index we look at 
        carry = sum / 10;

        // move indices toward the left 
        num1_index--;
        num2_index--;
    }
    // add the carrying # if we have any left 
    if (carry > 0) 
        result.append(carry);
    // reserse the string we built and convert stringBuilder to string
    return result.reverse().toString();
}

```
