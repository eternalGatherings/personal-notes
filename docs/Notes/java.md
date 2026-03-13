# Core Java Notes.
## 1. Introduction to Java.

**Language:**
- Language is a medium to communicate between two entities.

**Programming Language:**
- It is a medium to communicate between human and a machine.
- We have various programming languages like C, C++, JAVA, Python & C#.

**How a programming language is built.**
1. English Language. <img src="https://github.com/user-attachments/assets/149c4e29-bf88-46cd-a3f3-ab7a6324e98f">
2. Java. <img src="https://github.com/user-attachments/assets/ea530022-7a0d-419a-abc3-96743c54e91e">

**Tokens:** It is a smallest unit of program.
1. Identifiers.
2. Literals.
3. Comments.
4. Keywords.
5. Operators.
6. Separators.

**1. Identifiers:** Identifiers are the names given for any java programs.

**2. Literals:** Literals are the values which are used in java programming language. In literals we have
- **Numeric Literals.**
    - **Integers:** Any number without decimal value is called as Integer literal.                  
        Ex. 1, 10, 25, 36
    - **Decimal:** Any number with decimal value is called as decimal literal.                
        Ex. 5.56, 76.36, 89.48

- **Character Literals:** Anything which is enclosed with single quotes is called as character literals.                    
      Ex. 'A', '9', '$'

- **String Literals:** Anything which is enclosed with double quotes is called as string literals.                     
      Ex. "Hello", "123", "A", "$", "", "Hello@#123"

- **Boolean Literals:** We have only 2 values in boolean literal that is **true** & **false**.

**3. Comments:** Comments are used to provide the additional information or to skip the particular line of code. In comments we have.
- Single line comment.
    ```java title="Java"
    // This is a single line command.
    ```
- Multi line or Block comment.
    ```java title="Java"
    /*
    * This is a
    * multi line
    * or block
    * command.
    */
    ```

**4. Keywords:** Keywords are the predefined words. It has its own meaning. Keywords in java are.
```text
1. abstract      11. continue      21. for             31. new           41. switch
2. assert        12. default       22. goto            32. package       42. synchronized
3. boolean       13. do            23. if              33. private       43. this
4. break         14. double        24. implements      34. protected     44. throw
5. byte          15. else          25. import          35. public        45. throws
6. case          16. enum          26. instance of     36. return        46. transient
7. catch         17. extends       27. int             37. short         47. try
8. char          18. final         28. interface       38. static        48. void
9. class         19. finally       29. long            39. strictfp      49. volatile
10. const        20. float         30. native          40. super         50. while
```

**5. Operators:** Operators are the symbols used to perform some operations.

<table>
    <tr><th>Operator type</th><th>Category</th><th>Precedence</th></tr>
    <tr>
        <td rowspan="2">Unary</td>
        <td>post fix</td>
        <td> &nbsp; expr++ &nbsp; expr-- &nbsp; </td>
    </tr>
    <tr>
        <td>pre fix</td>
        <td> &nbsp; ++expr &nbsp; --expr &nbsp; </td>
    </tr>
    <tr>
        <td rowspan="2">Arithmetic</td>
        <td>Multiplicative</td>
        <td> &nbsp; * &nbsp; / &nbsp; % &nbsp; </td>
    </tr>
    <tr>
        <td>Additive</td>
        <td> &nbsp; + &nbsp; - &nbsp; </td>
    </tr>
    <tr>
        <td>Shift</td>
        <td>Shift</td>
        <td> &nbsp; << &nbsp; >> &nbsp; >>> &nbsp; </td>
    </tr>
    <tr>
        <td rowspan="2">Relational</td>
        <td>Comparison</td>
        <td> &nbsp; < &nbsp; > &nbsp; <= &nbsp; >= &nbsp; instanceOf &nbsp; </td>
    </tr>
    <tr>
        <td>Equality</td>
        <td> &nbsp; == &nbsp; != &nbsp; </td>
    </tr>
    <tr>
        <td rowspan="3">Bitwise</td>
        <td>Bitwise AND</td>
        <td> &nbsp; & &nbsp; </td>
    </tr>
    <tr>
        <td>Bitwise exclusive OR</td>
        <td> &nbsp; ^ &nbsp; </td>
    </tr>
    <tr>
        <td>Bitwise inclusive OR</td>
        <td> &nbsp; | &nbsp; </td>
    </tr>
    <tr>
        <td rowspan="2">Bitwise</td>
        <td>Logical AND</td>
        <td> &nbsp; && &nbsp; </td>
    </tr>
    <tr>
        <td>Logical OR</td>
        <td> &nbsp; || &nbsp; </td>
    </tr>
    <tr>
        <td>Ternary</td>
        <td>Ternary</td>
        <td> &nbsp; ? &nbsp; : &nbsp; </td>
    </tr>
    <tr>
        <td>Assignment</td>
        <td>Assignment</td>
        <td> &nbsp; = &nbsp; += &nbsp; -= &nbsp; *= &nbsp; /= &nbsp; %= &nbsp; &= &nbsp; ^= &nbsp; |= &nbsp; <<= &nbsp; >>= &nbsp; >>>= &nbsp; </td>
    </tr>
</table>

**6. Separators:** Separators are used to separate the given java code.
- braces {}
- brackets []
- parenthesis ()
- semicolon ;
- comma ,

## 2. History of java.
- **James Gosling** is a founder of JAVA in the year 1991 and the software was named as **Green Talk**.
- Later they renamed to **Oak Oak** as a symbol of strength and it is a national tree of Germany. At the same time there was already an existing company called Oka Technologies whick became a legal issue and changed the software name from **Oak** to **Java** in the year 1995.
- Java 1.0 was originally released by **Sun Microsystems** in the year 1995, but **Oracle** acquires Sun Microsystems in the year 2010.

## 3. Architecture of Java.
### i. Diagram.
<img src="https://github.com/user-attachments/assets/88262b23-a869-4452-aeb2-619e09c7343d">

- Write java program in Text editor and save the file with **.java** extension.
- To convert this Human readable format to Machine readable format we have to perform 2 operations in the command prompt. That is
    a. Java Compiler **(javac)**
    b. Java Interpretr **(java)**
- The .java file will be given as an input for the compiler which checks for
    a. Checks for Syntax & Rules
    b. Translate from **.java** file (human readable format) to **.class** file (byte code format)
- If we violate any syntax or rule we will get **compile time error**.
- Once the .class file is generated it is an intermediate code which is in byte code format where it cannot be understood neither by humans nor by machine.
- The **.class** file will be given as an input for the interpreter which will converts to **binary file** and intern given to the OS to generate output.
    a. Interpreter will Read the code line by line
    b. Translate from **.class** file (byte code format) to **binary code** (01010011)
- During execution if we find any abnormal statements like 1/0 we get arithmetic exception that is **run time error**.

### ii. JVM (Java Virtual Machine):
It is a virtual machine which doesn't exists physically & it is whole responsible to execute the java program.

### iii. JRE (Java Runtime Environment):
It is an environmental setup provided to run java program.

### iv. JDK (Java Development Kit):
It is a kit which consists of all the library files and utilities to develop a java software. It is whole responsible to convert from .java file to .class file.

### v. JIT (Just In Time):
It is whole responsible to convert from .class file to binary format.

### vi. Why Java is platform independent?
Java is considered platform-independent because of its use of the Java Virtual Machine (JVM), which allows Java code to be executed on any device or operating system that has a JVM implementation, regardless of the underlying platform.

Note: Always the java program will executes from **left to right** & **top to bottom**.

## 4. Variables.
Variable is a named memory location which can store some value or data and it can change n-number of times during execution.

### Types of variables.
Variables are of 2 types.
- Primitive type.
- Non primitive type **/** Reference type **/** class type.

<img width="700" src="https://github.com/user-attachments/assets/82a3c762-ec2f-415b-860c-1620a2f08b0a">

### Variable declaration.
**Syntax:**
- data_type variable_name;

**Example:**
- int a;
- String s1;

### Variable initialization.
**Syntax:**
- variable_name = value;

**Example:**
- a = 10;
- s1 = "Sachin";

### Variable utilization.
**Example:**
- System.out.println(a);
- System.out.println(s1);

### Variable declaration and initialization in a single line.
**Syntax:**
- data_type variable_name = value;

**Example:**
- int a = 10;
- String s1 = "Sachin";

### Variable re-initialization.
**Syntax:**
- variable_name = new_value;

**Example:**
- a = 20;
- s1 = "Sachin Kn";

### Copying the value from one variable to another variable.
int x = 10;
int y = x;
System.out.println(x);
System.out.println(y);

## 5. Methods.
## 6. Constructor.
## 7. Static.
## 8. non-static and JVM memory.
## 9. Access Modifiers.

## 10. Java Types.
### i. Class
### ii. Interface
### iii. Enum
### iv. Annotation

## 11. Condition statements.
## 12. Loop statements.

## 13. Arrays.
## 14. String Functions.
## 15. class and object.

## 16. programming.
  - factorial.
  - Fibonacci series.
  - Reverse a String.
  - Prime no.
  - Odd even.
  - Patterns.

## 17. Blocks.
## 18. Pass by value.
## 19. Pass by reference.

## 20. Oops.
### i. Inheritance.
### ii. Abstraction.
### iii. Polymorphism.
#### a. Method Overloading.
#### b. Method Overriding.
### iv. Encapsulation.
### v. Composition.

## 21. Abstract class & Interface.
## 22. Package.
## 23. Collections.
## 24. Object class.
## 25. String class.
## 26. Exception handling.
## 27. Threads.
## 28. File handling.
## 29. Streams.
