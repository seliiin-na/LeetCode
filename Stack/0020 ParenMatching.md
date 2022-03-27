#### 1st Solution: 
check whether closing paren matches w/ opening
```cpp
bool isValid(string s) {
    stack<char> parenStack;
    if (s == "")
        return true;
    for (int i = 0; i < s.length(); i++) {
        if (s[i] == '(' or s[i] == '[' or s[i] == '{') { 
            parenStack.push(s[i]); // if opening paren, push onto stack
        } else { //is closing paren
            if (parenStack.empty()) // if closing paren without opening i.e. "]"
                return false;
            // compare closing to opening
            char curr = parenStack.top();
            parenStack.pop();
            // continue to check from inner paren outer paren
            if ((s[i] == ')' and curr != '(') or 
                (s[i] == ']' and curr != '[') or
                (s[i] == '}' and curr != '{'))
                return false;
        }
    }
    // return true if every opening paren gets popped off/get matched from stack
    return parenStack.empty();
}
```

#### 2nd Solution: 
push expected closing paren onto stack, & check whether closing matches w/ top of stack
```cpp
 bool isValid(string s) {
        stack<char> parenStack;
        // push expected future corresponding closing paren onto stack when we see 
        // an opening paren
        for (int i = 0; i < s.length(); i++) {
            if (s[i] == '(')
                parenStack.push(')');  
            else if (s[i] == '[')
                parenStack.push(']');
            else if (s[i] == '{')
                parenStack.push('}');
            else { //must be closing paren (check whether curr closing paren matches with the innermosted nested)
                if (parenStack.empty() or parenStack.top() != s[i])
                    return false;
                parenStack.pop();
            }
        }
        return parenStack.empty(); //everything pops out i.e. "{{" would be false
    }
```
