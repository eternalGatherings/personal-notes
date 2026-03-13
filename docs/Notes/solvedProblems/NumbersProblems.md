# Problems on numbers

## 1. Write a program to swap two numbers without using third variable.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int a = 10;
    int b = 20;
    
    a = a + b;
    b = a - b;
    a = a - b;
    
    System.out.println(a);
    System.out.println(b);
}
```
```java title="Java"
public static void main(String[] args) {
    int a = 10;
    int b = 20;
    
    b = a + b - (a = b);
    
    System.out.println(a);
    System.out.println(b);
}
```


```javascript title="JavaScript"
let a = 10;
let b = 20;

a = a + b;
b = a - b;
a = a - b;

console.log(a);
console.log(b);
```
```javascript title="JavaScript"
let a = 10;
let b = 20;

b = a + b - (a = b);

console.log(a);
console.log(b);
```
```javascript title="JavaScript"
let a = 10;
let b = 20;

[a, b] = [b, a];

console.log(a);
console.log(b);
```


```python title="Python"
a = 10
b = 20

a = a + b
b = a - b
a = a - b

print(a)
print(b)
```
```python title="Python"
a = 10
b = 20

a, b = b, a

print(a)
print(b)
```
```python title="Python"
a = 10
b = 20

[a, b] = [b, a]

print(a)
print(b)
```
</details>

## 2. WAP to convert -ve number to +ve number
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    // Approach - 1
    int num = -10;
    System.out.println(Math.abs(num));
    
    // Approach - 2
    String value = "-10.523";
    System.out.println(new BigDecimal(value).abs());
}
```


```javascript title="JavaScript"
// Approach - 1
let num = -10;
console.log(Math.abs(num));

// Approach - 2
let value = "-10";
console.log(Math.abs(value));
```


```python title="Python"
# Approach - 1
num = -10
print(abs(num))

# Approach - 2
value = "-10"
print(abs(int(value)))
```
</details>

## 3. WAP to find factorial of a given number.
**Input:** 5      
**Output:** 120
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int number = 5;
    
    int fact = 1;
    for (int i=1; i<=number; i++) {
        fact *= i;
    }
    
    System.out.println(fact);
}
```


```javascript title="JavaScript"
const number = 5;
    
let fact = 1;
for (let i=1; i<=number; i++) {
    fact *= i;
}

console.log(fact);
```


```python title="Python"
number = 5
    
fact = 1
for i in range(1, number+1):
    fact *= i

print(fact)
```
</details>

## 4. WAP to print first 10 Fibonacci numbers.
**Output:** 0, 1, 1, 2, 3, 5, 8, 13, 21, 34

<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int a = 0;
    int b = 1;
    
    System.out.print(a + ", " + b + ", ");
    
    for (int i=2; i<10; i++) {
        int c = a + b;
        a = b;
        b = c;
        
        System.out.print(c + ", ");
    }
}
```


```javascript title="JavaScript"
let fibs = [];

fibs.push(0);
fibs.push(1);
for (let i=2; i<10; i++) {
    fibs.push(fibs[i-2] + fibs[i-1]);
}

console.log(fibs.join(", "));
```


```python title="Python"
fibs = []

fibs.append(0)
fibs.append(1)
for i in range(2, 10):
    fibs.append(fibs[i-2] + fibs[i-1])

print(", ".join(map(str, fibs)))
```
</details>

## 5. WAP to find given number is prime number or not.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int number = 7;
    
    boolean isPrimeNumber = true;
    for (int i=2; i<number; i++) {
        if (number % i == 0) {
            isPrimeNumber = false;
            break;
        }
    }
    
    System.out.println("The given number " + number + " is " + (isPrimeNumber ? "prime number." : "not a prime number"));
}
```


```javascript title="JavaScript"
const number = 7;
    
let isPrimeNumber = true;
for (let i=2; i<number; i++) {
    if (number % i === 0) {
        isPrimeNumber = false;
        break;
    }
}

console.log("The given number " + number + " is " + (isPrimeNumber ? "prime number." : "not a prime number"));
```


```python title="Python"
number = 7
    
isPrimeNumber = True
for i in range(2, number):
    if number % i == 0:
        isPrimeNumber = False
        break

print("The given number", number, "is", ("prime number." if isPrimeNumber else "not a prime number"));
```
</details>

## 6. WAP to calculate the sum of the digits of the given Number.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int number = 143;
	int sum = 0;
	
	while (number != 0) {
		int rem = number % 10;
		number = (int) number / 10;
		sum += rem;
	}
	
	System.out.println(sum);
}
```


```javascript title="JavaScript"
let number = 143;
let sum = 0;

while (number != 0) {
	let rem = number % 10;
	number = parseInt(number / 10);
	sum += rem;
}

console.log(sum);
```


```python title="Python"
number = 143
sum = 0

while number != 0:
	rem = number % 10
	number = int(number / 10)
	sum += rem

print(sum)
```
</details>

## 7. WAP to calculate the sum of square of the digits of the given Number.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int number = 143;
	int squreSum = 0;
	
	while (number != 0) {
		int rem = number % 10;
		number = (int) number / 10;
		squreSum += rem * rem;
	}
	
	System.out.println(squreSum);
}
```


```javascript title="JavaScript"
let number = 143;
let squreSum = 0;

while (number != 0) {
	let rem = number % 10;
	number = parseInt(number / 10);
	squreSum += rem * rem;
}

console.log(squreSum);
```


```python title="Python"
number = 143
squreSum = 0

while number != 0:
	rem = number % 10
	number = int(number / 10)
	squreSum += rem * rem

print(squreSum)
```
</details>

## 8. WAP to count how many times 1 is repeated in a given number.
**Input:** 110151   
**Output:** 4

<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int number = 110151;
    int count = 0;
    
    while (number != 0) {
        int rem = number % 10;
        number = (int) number / 10;
        if (rem == 1)
            count++;
    }
    
    System.out.println(count);
}
```


```javascript title="JavaScript"
let number = 110151;
let count = 0;

while (number != 0) {
    let rem = number % 10;
    number = parseInt(number / 10);
    if (rem === 1)
        count++;
}

console.log(count);
```


```python title="Python"
number = 110151
count = 0

while (number != 0):
    rem = number % 10
    number = int(number / 10)
    if (rem == 1):
        count += 1

print(count)
```
</details>

## 9. WAP to reverse a number.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int number = 110151;
    int reversedNum = 0;
    
    while (number != 0) {
        int rem = number % 10;
        reversedNum = reversedNum  * 10 + rem;
        number = (int) number / 10;
    }
    
    System.out.println(reversedNum);
}
```


```javascript title="JavaScript"
let number = 110151;
let reversedNum = 0;

while (number != 0) {
    let rem = number % 10;
    reversedNum = reversedNum  * 10 + rem;
    number = parseInt(number / 10);
}

console.log(reversedNum);
```


```python title="Python"
number = 110151
reversedNum = 0

while (number != 0):
    rem = number % 10
    reversedNum = reversedNum  * 10 + rem
    number = int(number / 10)

print(reversedNum)
```
</details>

## 10. WAP to check whether a given number is palindrome or not.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int number = 110151;
    int numberCopy = number;
    int reversedNum = 0;
    
    while (number != 0) {
        int rem = number % 10;
        reversedNum = reversedNum  * 10 + rem;
        number = (int) number / 10;
    }
    
    System.out.println("The given number " + numberCopy + (numberCopy == reversedNum ? " is palindrome." : " is not palindrome."));
}
```


```javascript title="JavaScript"
let number = 110151;
const numberCopy = number;
let reversedNum = 0;

while (number != 0) {
    let rem = number % 10;
    reversedNum = reversedNum  * 10 + rem;
    number = parseInt(number / 10);
}

console.log("The given number " + numberCopy + (numberCopy == reversedNum ? " is palindrome." : " is not palindrome."));
```


```python title="Python"
number = 110151
numberCopy = number
reversedNum = 0

while (number != 0):
    rem = number % 10
    reversedNum = reversedNum  * 10 + rem
    number = int(number / 10)

print("The given number", numberCopy, ("is palindrome." if numberCopy == reversedNum else "is not palindrome."));
```
</details>

## 11. WAP to Write a program to check whether the given number is armstrong number or not.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int number = 153;
    int numberCopy = number;
    int qubeSum = 0;
    
    while (number != 0) {
        int rem = number % 10;
        qubeSum += rem * rem * rem;
        number = (int) number / 10;
    }
    
    System.out.println("The given number " + numberCopy + (numberCopy == qubeSum ? " is armstrong number." : " is not armstrong number."));
}
```


```javascript title="JavaScript"
let number = 153;
const numberCopy = number;
let qubeSum = 0;

while (number != 0) {
    let rem = number % 10;
    qubeSum += rem * rem * rem;
    number = parseInt(number / 10);
}

console.log("The given number " + numberCopy + (numberCopy == qubeSum ? " is armstrong number." : " is not armstrong number."));
```


```python title="Python"
number = 153
numberCopy = number
qubeSum = 0

while (number != 0):
    rem = number % 10
    qubeSum += rem * rem * rem
    number = int(number / 10)

print("The given number", numberCopy, ("is armstrong number." if numberCopy == qubeSum else "is not armstrong number."));
```
</details>

## 12. WAP to check whether the given number is Strong number or not.
A strong number, also known as a factorial number, is a number in which the sum of the factorials of its digits equals the number itself.

**Example:**

- Consider the number 145:
	- The digits are 1, 4, and 5.
	- The factorial of 1 is 1! = 1.
	- The factorial of 4 is 4! = 4 × 3 × 2 × 1 = 24.
	- The factorial of 5 is 5! = 5 × 4 × 3 × 2 × 1 = 120.
	- The sum of the factorials is 1 + 24 + 120 = 145, which is equal to the original number. Therefore, 145 is a strong number.

<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int number = 145;
    int numberCopy = number;
    int sumFact = 0;
    
    while (number != 0) {
        int rem = number % 10;
        number = number / 10;
        
        int fact = 1;
        for (int i=1; i<=rem; i++) {
            fact = fact * i;
        }
        
        sumFact = sumFact + fact;
    }
    
    System.out.println("The given number " + numberCopy + (numberCopy == sumFact ? " is strong number." : " is not strong number."));
}
```


```javascript title="JavaScript"
let number = 145;
const numberCopy = number;
let sumFact = 0;

while (number !== 0) {
    let rem = number % 10;
    number = parseInt(number / 10);
    
    let fact = 1;
    for (let i=1; i<=rem; i++) {
        fact = fact * i;
    }
    
    sumFact = sumFact + fact;
}

console.log("The given number " + numberCopy + (numberCopy === sumFact ? " is strong number." : " is not strong number."));
```


```python title="Python"
number = 145
numberCopy = number
sumFact = 0

while number != 0:
    rem = number % 10
    number = int(number / 10)

    fact = 1
    for i in range(1, rem+1):
        fact = fact * i

    sumFact = sumFact + fact

print("The given number", numberCopy, "is strong number." if numberCopy == sumFact else "is not strong number.");
```
</details>

## 13. WAP to check whether the given number is Perfect number or not.
A perfect number is a positive integer that is equal to the sum of its proper divisors (excluding itself). In other words, if you list all the positive divisors of the number and sum them up, the sum will be twice the number because the number itself is included in the list of divisors.

**Example:**            
- 6 is a perfect number:
	- The divisors of 6 are 1, 2, 3, and 6.
	- The proper divisors (excluding 6 itself) are 1, 2, and 3.
	- The sum of the proper divisors is 1 + 2 + 3 = 6, which is equal to the original number.

- 28 is a perfect number:
	- The divisors of 28 are 1, 2, 4, 7, 14, and 28.
	- The proper divisors (excluding 28 itself) are 1, 2, 4, 7, and 14.
	- The sum of the proper divisors is 1 + 2 + 4 + 7 + 14 = 28, which is equal to the original number.

<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int number = 6;
    int sum = 0;
    
    for (int i=1; i<number; i++) {
        if (number % i == 0)
            sum = sum + i;
    }
    
    System.out.println("The given number " + number + (number == sum ? " is perfect number." : " is not perfect number."));
}
```


```javascript title="JavaScript"
const number = 6;
let sum = 0;

for (let i=1; i<number; i++) {
    if (number % i === 0)
        sum = sum + i;
}

console.log("The given number", number, number == sum ? "is perfect number." : "is not perfect number.");
```


```python title="Python"
number = 6
sum = 0

for i in range(1, number):
    if number % i == 0:
        sum += i

print("The given number", number, "is perfect number." if number == sum else "is not perfect number.");
```
</details>
