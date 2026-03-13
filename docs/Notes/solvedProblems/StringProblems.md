# Problems on strings.

## 1. WAP to find the length of a string without using inbuilt method.
<details open>
  <summary>Solution!</summary>
	

```java title="Java"
public static void main(String[] args) {
    String s1 = "Sachin";

    int count = 0;
    boolean endOfString = false;
    while (!endOfString) {
	try {
	    s1.charAt(count);
	    count++;
	} catch (Exception ex) {
	    endOfString = true;
	}
    }
    
    System.out.println(count);
}
```


```javascript title="JavaScript"
const s1 = "Sachin";

let count = 0;
for (i of s1) {
    count++;
}

console.log(count);
```


```python title="Python"
s1 = "Sachin"

count = 0
for i in s1:
    count += 1

print(count)
```
</details>

## 2. WAP to reverse a string.
**Input:** "hi how are you"                
**Output:** "uoy era woh ih"
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    String s1 = "hi how are you";

    String rev = "";
    for (int i=0; i<s1.length(); i++) {
        rev = s1.charAt(i) + rev;
    }
    
    System.out.println(rev);
}
```


```javascript title="JavaScript"
const s1 = "hi how are you";
let rev = "";

for (i of s1) {
    rev = i + rev;
}

console.log(rev);
```


```python title="Python"
s1 = "hi how are you"

# Approach - 1
rev1 = ""

for i in s1:
    rev1 = i + rev1

print(rev1)

# Approach - 2
rev2 = ''.join(reversed(s1))
print(rev2)

# Approach - 3
rev3 = s1[::-1]
print(rev3)
```
</details>

## 3. WAP to get bellow output.
**Input:** "hi how are you"                
**Output:** "ih woh era uoy"
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    String s1 = "hi how are you";
    String result = "";
    
    for (String s : s1.split(" ")) {
        String rev = "";
        for (int i=0; i<s.length(); i++)
            rev = s.charAt(i) + rev;
        result += rev + " ";
    }
    
    System.out.println(result);
}
```


```javascript title="JavaScript"
const s1 = "hi how are you";
let result = "";

for (const s of s1.split(" ")) {
    let rev = "";
    for (const i of s)
        rev = i + rev;
    result += rev + " ";
}

console.log(result);
```


```python title="Python"
s1 = "hi how are you"
result = ""

for s in s1.split(" "):
    rev = "";
    for i in s:
        rev = i + rev
    result += rev + " "

print(result);
```
</details>

## 4. WAP to get bellow output.
**Input:** "hi how are you"                
**Output:** "you are how hi"
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    String s1 = "hi how are you";
    String result = "";
    
    for (String s : s1.split(" ")) {
        result = " " + s + result;
    }
    
    System.out.println(result);
}
```


```javascript title="JavaScript"
const s1 = "hi how are you";
let result = "";

for (const s of s1.split(" ")) {
    result = " " + s + result;
}

console.log(result);
```


```python title="Python"
s1 = "hi how are you"
result = ""

for s in s1.split(" "):
    result = " " + s + result

print(result)
```
</details>

## 5. Replace the "World" in "Hello World" to "Universe".
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    String s1 = "Hello World";
    String s2 = "Universe";
    
    String result = "";
    for (String i : s1.split("\\s")) {
        if (i.equals("World"))
            result += s2 + " ";
        else
            result += i + " ";
    }
    
    System.out.println(result);
}
```


```javascript title="JavaScript"
const s1 = "Hello World";
const s2 = "Universe";

let result = "";
for (i of s1.split(" ")) {
    if (i === 'World')
        result += s2 + " ";
    else
        result += i + " ";
}

console.log(result);
```


```python title="Python"
s1 = "Hello World"
s2 = "Universe"

result = ""
for i in s1.split():
    if i == 'World':
        result += s2 + " "
    else:
        result += i + " "

print(result)
```
</details>

## 6. WAP to add comma between each word of a given string.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    String s1 = "Hello Welcome to Java";
    
    System.out.println(String.join(", ", s1.split(" ")));
}
```


```javascript title="JavaScript"
const s1 = "Hello Welcome to JavaScript";

console.log(s1.split(" ").join(", "));
```


```python title="Python"
s1 = "Hello Welcome to Python"

print(", ".join(s1.split()))
```
</details>

## 7. WAP to print alternative characters from a given string.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    String s1 = "Hello World";

    for (int i = 0; i < s1.length(); i += 2) {
        System.out.print(s1.charAt(i));
    }
}
```


```javascript title="JavaScript"
const s1 = "Hello World";

for (let i=0; i<s1.length; i += 2) {
    process.stdout.write(s1[i])
}
```


```python title="Python"
s1 = "Hello World"

for i in range(0, len(s1), 2):
    print(s1[i], end="")
```
</details>

## 8. WAP to print ASCII values of a string
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    String s1 = "Hello World";
    
    for (int i : s1.toCharArray()) {
        System.out.println(i);
    }
}
```


```javascript title="JavaScript"
const s1 = "Hello World";

for (i in s1) {
    console.log(s1.charCodeAt(i));
}
```


```python title="Python"
s1 = "Hello World"

for i in s1:
    print(ord(i))
```
</details>

## 9. WAP to convert Uppercase to Lowercase and viceversa.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    // To lowerCase
    String s1 = "SACHIN";
    System.out.print(s1.toLowerCase());
}
```
```java title="Java"
public static void main(String[] args) {
    // To upperCase
    String s2 = "sachin";
    System.out.print(s1.toUpperCase());
}
```
```java title="Java"
public static void main(String[] args) {
    // To swap case
    String s3 = "Sachin";
    
    for (char i : s3.toCharArray())
        if (Character.isLowerCase(i))
            System.out.print(Character.toUpperCase(i));
        else if (Character.isUpperCase(i))
            System.out.print(Character.toLowerCase(i));
}
```


```javascript title="JavaScript"
// To lowerCase
const s1 = "SACHIN";
console.log(s1.toLowerCase());
```
```javascript title="JavaScript"
// To upperCase
const s2 = "sachin";
console.log(s1.toUpperCase());
```
```javascript title="JavaScript"
// To swap case
const s3 = "Sachin"

for (i of s3)
    if (/[A-Z]/.test(i))
        process.stdout.write(i.toLowerCase());
    else if (/[a-z]/.test(i))
        process.stdout.write(i.toUpperCase());
```


```python title="Python"
# To lowerCase
s1 = "SACHIN"
print(s1.lower())
```
```python title="Python"
# To upperCase
s2 = "sachin"
print(s2.upper())
```
```python title="Python"
# To swap case (1)
s3 = "Sachin"

for i in s3:
    if i.isupper():
        print(i.lower(), end="")
    elif i.islower():
        print(i.upper(), end="")
```
```python title="Python"
# To swap case (2)
s3 = "Sachin"
print(''.join([char.upper() if char.islower() else char.lower() for char in s3]))
```
</details>

## 10. WAP to convert Uppercase to Lowercase and viceversa without using inbuilt method.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    // To lowerCase
    String s1 = "SACHIN";
    
    for (int i : s1.toCharArray())
        System.out.print((char) (i + 32));
}
```
```java title="Java"
public static void main(String[] args) {
    // To upperCase
    String s2 = "sachin";
    
    for (int i : s2.toCharArray())
        System.out.print((char) (i - 32));
}
```
```java title="Java"
public static void main(String[] args) {
    // To swap case
    String s3 = "Sachin";
    
    for (int i : s3.toCharArray())
        if (97 <= i && i <= 112)
            System.out.print((char) (i - 32));
        else if (65 <= i && i <= 90)
            System.out.print((char) (i + 32));
}
```


```javascript title="JavaScript"
// To lowerCase
const s1 = "SACHIN"

for (i of s1)
    process.stdout.write(String.fromCharCode(i.charCodeAt(0) + 32));
```
```javascript title="JavaScript"
// To upperCase
const s2 = "sachin"

for (i of s2)
    process.stdout.write(String.fromCharCode(i.charCodeAt(0) - 32));
```
```javascript title="JavaScript"
// To swap case
const s3 = "Sachin"

for (i of s3)
    if ("a" <= i && i <= "z")
        process.stdout.write(String.fromCharCode(i.charCodeAt(0) - 32));
    else if ("A" <= i && i <= "Z")
        process.stdout.write(String.fromCharCode(i.charCodeAt(0) + 32));
```


```python title="Python"
# To lowerCase
s1 = "SACHIN"

for i in s1:
    print(chr(ord(i) + 32), end="")
```
```python title="Python"
# To upperCase
s2 = "sachin"

for i in s2:
    print(chr(ord(i) - 32), end="")
```
```python title="Python"
# To swap case
s3 = "Sachin"

for i in s3:
    if "a" <= i <= "z":
        print(chr(ord(i) - 32), end="")
    elif "A" <= i <= "Z":
        print(chr(ord(i) + 32), end="")
```
</details>

## 11. WAP to check if given string is Palindrome or not.
<details>
  <summary>Solution!</summary>

$${\color{green}Reversing‎ a‎ string‎ can‎ be‎ done‎ in‎ multiple‎ ways}$$ [Link](https://github.com/SachinKn-notes/All-notes/blob/master/05_Programs-2.md#2-wap-to-reverse-a-string)


```java title="Java"
public static void main(String[] args) {
    String s = "MoM";

    String rev = "";
    for (int i=0; i<s.length(); i++) {
        rev = s.charAt(i) + rev;
    }
    
    System.out.println(s.equals(rev) ? "Palindrome" : "Not Palindrome");
}
```


```javascript title="JavaScript"
const s = 'MoM'

let rev = "";

for (i of s) {
    rev = i + rev;
}

console.log(s === rev ? "Palindrome" : "Not Palindrome")
```


```python title="Python"
s = 'MOM'

rev = s[::-1] # Reversing a string.

print("Palindrome" if s == rev else "Not Palindrome")
```
</details>

## 12. WAP to Search for a character in a given string and return corresponding index
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    String s = "Hello World";
    char ch = 'W';
    
    // Approach - 1
    System.out.println(s.indexOf(ch));
    
    // Approach - 2
    for (int i=0; i<s.length(); i++) {
        if (s.charAt(i) == ch) {
            System.out.println(i);
            break;
        }
    }
}
```


```javascript title="JavaScript"
const s = "Hello World"
const ch = "W" 

// Approach - 1
console.log(s.indexOf(ch))

// Approach - 2
for (i in s) {
    if (s[i] === ch) {
        console.log(i);
        break;
    }
}

// Approach - 3
s.split('').forEach((c, index) => {
    if (c === ch) {
        console.log(index);
    }
})
```


```python title="Python"
s = "Hello World"
ch = "W"

# Approach - 1
print(s.find(ch))

# Approach - 2
for i, c in enumerate(s):
    if (c == ch):
        print(i)
        break
```
</details>

## 13. WAP to replace all the characters with "_" if the character occurs more then once in a string.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    String s1 = "hellohi";

    for (int i=0; i<s1.length(); i++) {
        if (s1.charAt(i) != '_' && getCharCount(s1, s1.charAt(i)) > 1)
            s1 = s1.replaceAll(String.valueOf(s1.charAt(i)), "_");
    }
    
    System.out.println(s1);
}

public static int getCharCount(String stringValue, char ch) {
    int count = 0;
    
    for (int i=0; i<stringValue.length(); i++) {
        if (stringValue.charAt(i) == ch)
            count++;
    }
    
    return count;
}
```


```javascript title="JavaScript"
let s1 = "hellohi";

for (const i of s1) {
    if (i !== '_' && getCharCount(s1, i) > 1) {
        s1 = s1.replace(new RegExp(i, "g"), "_");
    }
}

console.log(s1);

function getCharCount(stringValue, ch) {
    let count = 0;
    for (const i of stringValue) {
        if (i === ch)
            count++;
    }
    return count;
}
```


```python title="Python"
s1 = "hellohi"

# Approach - 1
def getCharCount(stringValue, ch):
    count = 0
    for i in stringValue:
        if i == ch:
            count += 1
    return count

for i in s1:
    if i != '_' and getCharCount(s1, i) > 1:
        s1 = s1.replace(i, '_')

# Approach - 2
for i in s1:
    if i != '_' and s1.count(i) > 1:
        s1 = s1.replace(i, '_')

print(s1)
```
</details>

## 14. WAP to find lengthiest word in a sentence.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    String s1 = "hardest choices require the strongest wills";
    String longWorld = "";
    
    for (String s : s1.split(" ")) {
        if (s.length() > longWorld.length())
            longWorld = s;
    }
    
    System.out.println(longWorld);
}
```


```javascript title="JavaScript"
const s1 = "hardest choices require the strongest wills";
let longWorld = "";

for (const s of s1.split(" ")) {
    if (s.length > longWorld.length)
        longWorld = s;
}

console.log(longWorld);
```


```python title="Python"
s1 = "hardest choices require the strongest wills"
longWorld = ""

for s in s1.split(" "):
    if len(s) > len(longWorld):
        longWorld = s

print(longWorld)
```
</details>

## 15. WAP to print how many vowels are there in a given string.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    String s1 = "reality is often disappointing";
    
    // Approach - 1
    int count1 = 0;
    for (int i=0; i<s1.length(); i++) {
        if (List.of('a', 'e', 'i', 'o', 'u').contains(s1.charAt(i)))
            count1++;
    }
    
    System.out.println(count1);
    
    // Approach - 2
    int count2 = 0;
    for (int i=0; i<s1.length(); i++) {
        if (Pattern.compile("[aeiou]").matcher(String.valueOf(s1.charAt(i))).find())
            count2++;
    }
    
    System.out.println(count2);
    
    Stream.of(List.of('a', 'e', 'i', 'o', 'u'));
}
```


```javascript title="JavaScript"
const s1 = "reality is often disappointing";

// Approach - 1
let count1 = 0;
for (const s of s1) {
    if (['a', 'e', 'i', 'o', 'u'].includes(s))
        count1++;
}

console.log(count1);

// Approach - 2
let count2 = 0;
for (const s of s1) {
    if (/[aeiou]/.test(s))
        count2++;
}

console.log(count2);
```


```python title="Python"
s1 = "reality is often disappointing"

# Approach - 1
count1 = 0
for s in s1:
    if s in ['a', 'e', 'i', 'o', 'u']:
        count1 += 1

print(count1)

# Approach - 2
import re

count2 = 0
for s in s1:
    if re.search("[aeiou]", s):
        count2 += 1

print(count2)
```
</details>

## 16. WAP to separate alphabets, numbers & special characters in a given string.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    String s1 = "example_123@gmail.com";

    String alphabets = "";
    String numbers = "";
    String specChars = "";

    for (int i = 0 ; i < s1.length(); i++) {
        char letter = s1.charAt(i);
        
        if (Character.isAlphabetic(letter))
            alphabets += letter;
        else if (Character.isDigit(letter))
            numbers += letter;
        else
            specChars += letter;
    }

    System.out.println("Alphabets: " + alphabets);
    System.out.println("Numbers: " + numbers);
    System.out.println("SpecialChars: " + specChars);
}
```


```javascript title="JavaScript"
const s1 = "example_123@gmail.com";

let alphabets = "";
let numbers = "";
let specChars = "";

for (const letter of s1) {
    if (/[a-zA-Z]/.test(letter))
        alphabets += letter;
    else if (/[0-9]/.test(letter))
        numbers += letter;
    else
        specChars += letter;
}

console.log("Alphabets: " + alphabets);
console.log("Numbers: " + numbers);
console.log("SpecialChars: " + specChars);
```


```python title="Python"
import re

s1 = "example_123@gmail.com"

alphabets = ""
numbers = ""
specChars = ""

for letter in s1:
    if re.search(r"[a-zA-Z]", letter):
        alphabets += letter
    elif re.search(r"[0-9]", letter):
        numbers += letter
    else:
        specChars += letter

print("Alphabets: " + alphabets)
print("Numbers: " + numbers)
print("SpecialChars: " + specChars)
```
</details>

## 17. WAP to sum up all the numbers present in a given string.
```
Input: "Sachin@123"
Output: 6
```
<details>
  <summary>Solution!</summary>


```java title="Java"
class Index {
    public static void main(String[] args) {
        String s1 = "soft123";

        int sum = 0;
        for (int i = 0; i < s1.length(); i++) {
            if (s1.charAt(i) >= '0' && s1.charAt(i) <= '9')
                sum += s1.charAt(i) - '0';
        }

        System.out.println(sum);
    }
}
```
```java title="Java"
class Index {
    public static void main(String[] args) {
        String s1 = "Sachin@123";
        
        int sum = s1.chars()
                .filter(Character::isDigit)
                .mapToObj(Character::getNumericValue)
                .reduce(0, (a, b) -> a + b);
                
        System.out.println(sum);
    }
}
```


```js title="JavaScript"
let s1 = "Sachin@123";

let sum = 0;
for (let i = 0; i < s1.length; i++) {
    if (s1[i] >= '0' && s1[i] <= '9')
        sum += s1[i] -'0';
}

console.log(sum);
```


```python title="Python"
s1 = "Sachin@123"

sum = 0
for i in range(len(s1)):
    if '0' <= s1[i] <= '9':
        sum += int(s1[i])

print(sum)
```
</details>

## 18. WAP to to merge the alternate char from 2 given string. If a string is longer than the other, append the additional letter onto the end of the merged string.
```
Input:
String s1 = "Vidya";
String s2 = "Sachinaaa";

Output:
VSiadcyhainaaa
```
<details>
  <summary>Solution!</summary>


```java title="Java"
class Index {
    public static void main(String[] args) {
        
        String s1 = "Vidya";
        String s2 = "Sachinaaa";

        int maxLength = s1.length() > s2.length() ? s1.length() : s2.length();

        String result = "";
        for (int i=0; i<maxLength; i++) {
            if (i < s1.length())
                result = result + s1.charAt(i);
            if (i < s2.length())
                result = result + s2.charAt(i);
        }

        System.out.println(result);
    }
}
```


```js title="JavaScript"
let s1 = "Vidya";
let s2 = "Sachinaaa";

let maxLength = s1.length > s2.length ? s1.length : s2.length;

let result = "";
for (let i = 0; i < maxLength; i++) {
  if (i < s1.length)
    result = result + s1.charAt(i);
  if (i < s2.length)
    result = result + s2.charAt(i);
}

console.log(result);
```


```python title="Python"
s1 = "Vidya"
s2 = "Sachinaaa"

maxLength = len(s1) if len(s1) > len(s2) else len(s2)

result = ""
for i in range(maxLength):
  if i < len(s1):
    result = result + s1[i]
  if i < len(s2):
    result = result + s2[i]

print(result)
```
</details>
