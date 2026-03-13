# Pattern printing problems

## 1. WAP to print below Pattern.
```
*
* *
* * *
* * * *
* * * * *
```

<details>
  <summary>Solution!</summary>


```java title="Java"
class Index {
    public static void main(String[] args) {
        
        for (int i=1; i<=5; i++) {
            for (int j=1; j<=i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}
```


```js title="JavaScript"
for (let i=1; i<=5; i++) {
    for (let j=1; j<=i; j++) {
        process.stdout.write("* ");
    }
    console.log();
}
```


```python title="Python"
for i in range(1, 6):
    print("* " * i)
```
</details>

## 2. WAP to print below Pattern.
```
        *
      * *
    * * *
  * * * *
* * * * *
```
<details>
  <summary>Solution!</summary>


```java title="Java"
class Index {
    public static void main(String[] args) {
        
        for (int i=1; i<=5; i++) {
            for (int j=5; j>i; j--) {
                System.out.print("  ");
            }
            for (int j=1; j<=i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}
```


```js title="JavaScript"
for (let i=1; i<=5; i++) {
    for (let j=5; j>i; j--) {
        process.stdout.write("  ");
    }
    for (let j=1; j<=i; j++) {
        process.stdout.write("* ");
    }
    console.log();
}
```


```python title="Python"
for i in range(1, 6):
    print("  " * (5-i), end="")
    print("* " * i)
```

</details>

## 3. WAP to print below Pattern.
```
    *
   * *
  * * *
 * * * *
* * * * *
```
<details>
  <summary>Solution!</summary>


```java title="Java"
class Index {
    public static void main(String[] args) {
        
        for (int i=1; i<=5; i++) {
            for (int j=5; j>i; j--) {
                System.out.print(" ");
            }
            for (int j=1; j<=i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}
```


```js title="JavaScript"
for (let i=1; i<=5; i++) {
    for (let j=5; j>i; j--) {
        process.stdout.write(" ");
    }
    for (let j=1; j<=i; j++) {
        process.stdout.write("* ");
    }
    console.log();
}
```


```python title="Python"
for i in range(1, 6):
    print(end=" " * (5-i))
    print("* " * i)
```
</details>

## 4. WAP to print below Pattern.
```
1
2 2
3 3 3
4 4 4 4
5 5 5 5 5
```
<details>
  <summary>Solution!</summary>


```java title="Java"
class Index {
    public static void main(String[] args) {
        
        for (int i=1; i<=5; i++) {
            for (int j=1; j<=i; j++) {
                System.out.print(i + " ");
            }
            System.out.println();
        }
    }
}
```


```js title="JavaScript"
for (let i=1; i<=5; i++) {
    for (let j=1; j<=i; j++) {
        process.stdout.write(i + " ");
    }
    console.log();
}
```


```python title="Python"
for i in range(1, 6):
    print((str(i) + " ") * i)
```
</details>

## 5. WAP to print below Pattern.
```
1
2 3
4 5 6
7 8 9 10
11 12 13 14 15
```
<details>
  <summary>Solution!</summary>


```java title="Java"
class Index {
    public static void main(String[] args) {
        
        int k = 1;
        for (int i=1; i<=5; i++) {
            for (int j=1; j<=i; j++) {
                System.out.print(k + " ");
                k=k+1;
            }
            System.out.println();
        }
    }
}
```


```js title="JavaScript"
let k = 1;
for (let i=1; i<=5; i++) {
    for (let j=1; j<=i; j++) {
        process.stdout.write(k + " ");
        k=k+1;
    }
    console.log();
}
```


```python title="Python"
k = 1
for i in range(1, 6):
    for j in range(1, i+1):
        print(k, end=" ")
        k += 1
    print()
```
</details>

## 6. WAP to print below Pattern.
```
A
A B
A B C
A B C D
A B C D E
```
<details>
  <summary>Solution!</summary>


```java title="Java"
class Index {
    public static void main(String[] args) {
        
        for (char i=65; i<70; i++) {
            for (char j=65; j<=i; j++) {
                System.out.print(j + " ");
            }
            System.out.println();
        }
    }
}
```


```js title="JavaScript"
for (let i=65; i<70; i++) {
    for (let j=65; j<=i; j++) {
        process.stdout.write(String.fromCharCode(j) + " ");
    }
    console.log();
}
```


```python title="Python"
for i in range(65, 70):
    for j in range(65, i+1):
        print(chr(j), end=" ")
    print()
```
</details>

## 7. WAP to print below Pattern.
```
A
B B
C C C
D D D D
E E E E E
```
<details>
  <summary>Solution!</summary>


```java title="Java"
class Index {
    public static void main(String[] args) {
        
        for (char i=65; i<70; i++) {
            for (char j=65; j<=i; j++) {
                System.out.print(i + " ");
            }
            System.out.println();
        }
    }
}
```


```js title="JavaScript"
for (let i=65; i<70; i++) {
    for (let j=65; j<=i; j++) {
        process.stdout.write(String.fromCharCode(i) + " ");
    }
    console.log();
}
```


```python title="Python"
for i in range(65, 70):
    for j in range(65, i+1):
        print(chr(i), end=" ")
    print()
```
</details>
