# Problems on Arrays

## 1. WAP to Merge two lists
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    List<Integer> l1 = List.of(1, 2, 3);
    List<Integer> l2 = List.of(4, 5, 6);
    
    // Approach - 1
    List<Integer> merged1 = new ArrayList<>();
    merged1.addAll(l1);
    merged1.addAll(l2);
    
    System.out.println(merged1);
    
    // Approach - 2
    List<Integer> merged2 = new ArrayList<>(l1);
    merged2.addAll(l2);
    
    System.out.println(merged2);
    
    // Approach - 3
    List<Integer> merged3 = new ArrayList<>();
    Collections.addAll(merged3, l1.toArray(new Integer[0]));
    Collections.addAll(merged3, l2.toArray(new Integer[0]));
    
    System.out.println(merged3);
    
    // Approach - 4
    List<Integer> merged4 = Stream.concat(l1.stream(), l2.stream()).collect(Collectors.toList());
    
    System.out.println(merged4);
}
```


```javascript title="JavaScript"
const l1 = [1, 2, 3];
const l2 = [4, 5, 6];
 
// Approach - 1
console.log([...l1, ...l2]);
 
// Approach - 2
console.log(l1.concat(l2));

// Approach - 3
const l3 = []
l3.push(...l1);
l3.push(...l2);
console.log(l3);

// Approach - 4
console.log(l2.reduce((acc, cur) => {
    acc.push(cur);
    return acc;
}, [...l1]));

// Approach - 5
console.log(combine1([l1, l2]));
 
function combine1(l1) {
    let arr = []
    l1.forEach(i => {
        i.forEach(j => {
            arr.push(j);
        });
    });
    return arr;
}
```


```python title="Python"
l1 = [1, 2, 3]
l2 = [4, 5, 6]
 
# Approach - 1
l3 = l1 + l2
print(l3)

# Approach - 2
l4 = []
l4.extend(l1)
l4.extend(l2)
print(l4)
 
# Approach - 3
l5 = []
for i, j in zip(l1, l2):
    l5.append(i)
    l5.append(j)

print(l5)
```
</details>

## 2. WAP to get the below output.
**Input:** s1 = "hello world welcome to javaScript programming hi there"             
**Output:** { h: [ 'hello', 'hi' ], w: [ 'world', 'welcome' ], t: [ 'to', 'there' ], j: [ 'javaScript' ], p: [ 'programming' ] }                
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    String s1 = "hello world welcome to javaScript programming hi there";

    // Approach - 1
    Map<Character, List<String>> result1 = new HashMap<>();
    for (String i : s1.split(" ")) {
        if (result1.containsKey(i.charAt(0))) {
            result1.get(i.charAt(0)).add(i);
        } else
            result1.put(i.charAt(0), new ArrayList<String>() {{add(i);}});
    }
    
    System.out.println(result1);
    
    // Approach - 2
    Map<Character, List<String>> result2 = new HashMap<>();
    for (String i : s1.split(" ")) {
        Object o = result2.containsKey(i.charAt(0))
            ? result2.get(i.charAt(0)).add(i)
            : result2.put(i.charAt(0), new ArrayList<String>() {{add(i);}});
    }
    
    System.out.println(result2);
}
```


```javascript title="JavaScript"
const s1 = "hello world welcome to javaScript programming hi there";

// Approach - 1
let result1 = {};

for (i of s1.split(" ")) {
    if (result1.hasOwnProperty(i[0]))
        result1[i[0]].push(i);
    else
        result1[i[0]] = [i];
}

console.log(result1);

// Approach - 2
let result2 = {};

for (i of s1.split(" ")) {
    result2[i[0]] ? result2[i[0]].push(i) : result2[i[0]] = [i];
}

console.log(result2);
```


```python title="Python"
s1 = "hello world welcome to javaScript programming hi there";

# Approach - 1
result1 = {}
for i in s1.split(" "):
    if i[0] not in result1:
        result1[i[0]] = [i]
    else:
        result1[i[0]].append(i)

print(result1)

# Approach - 2
from collections import defaultdict

result2 = defaultdict(list)
for word in s1.split(" "):
    result2[word[0]] += [word]

print(dict(result2))
```

**Output**
```javascript title="JavaScript"
{
  h: [ 'hello', 'hi' ],
  w: [ 'world', 'welcome' ],
  t: [ 'to', 'there' ],
  j: [ 'javaScript' ],
  p: [ 'programming' ]
}
```
</details>

## 3. WAP to check whether the list contains particular value.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    List<Integer> l1 = List.of(1, 3, 5, 7, 2, 3, 1, 7, 6);
    
    System.out.println(islistContainsValue(l1, 4));
}

public static boolean islistContainsValue(List<Integer> list, int value) {
    for (int i : list) {
        if (i == value)
            return true;
    }
    return false;
}
```


```javascript title="JavaScript"
const l1 = [1, 3, 5, 7, 2, 3, 1, 7, 6];

console.log(islistContainsValue(l1, 4));

function islistContainsValue(list, value) {
    for (const i of list) {
        if (i === value)
            return true;
    }
    return false;
}
```


```python title="Python"
l1 = [1, 3, 5, 7, 2, 3, 1, 7, 6];

def islistContainsValue(list, value):
    for i in list:
        if i == value:
            return True
    return False

print(islistContainsValue(l1, 4));
```
</details>

## 4. WAP to remove duplicates from a list.
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    List<Integer> l1 = List.of(1, 3, 5, 7, 2, 3, 1, 7, 6);
    
    List<Integer> dup = new ArrayList<>();
    List<Integer> result = new ArrayList<>();
    
    for (int i : l1) {
        if (islistContainsValue(result, i))
            dup.add(i);
        else
            result.add(i);
    }
    
    System.out.println("Duplicate values: " + dup);
    System.out.println("Results: " + result);
}

public static boolean islistContainsValue(List<Integer> list, int value) {
    for (int i : list) {
        if (i == value)
            return true;
    }
    return false;
}
```


```javascript title="JavaScript"
const l1 = [1, 3, 5, 7, 2, 3, 1, 7, 6];

let dup = [];
let result = [];

for (const i of l1) {
    if (islistContainsValue(result, i))
        dup.push(i);
    else
        result.push(i);
}

console.log("Duplicate values:", dup);
console.log("Results:", result);

function islistContainsValue(list, value) {
    for (const i of list) {
        if (i === value)
            return true;
    }
    return false;
}
```


```python title="Python"
l1 = [1, 3, 5, 7, 2, 3, 1, 7, 6]

dup = []
result = []

for i in l1:
    if i in result:
        dup.append(i)
    else:
        result.append(i)

print("Duplicate values:", dup)
print("Results:", result)
```
</details>

## 5. WAP to find the indices of two numbers in the array that add up to the given target.
```python title="Python"
Input:
numbers = [2, 7, 11, 15]
target = 22

Output: 1, 3
```
```
Explanation:
- 7 + 15 = 22 (matches the target)
- index of 7 is 1 and index of 15 is 3
- So, the output is 1, 3 (indices of the two numbers).
```
<details>
  <summary>Solution!</summary>


```java title="Java"
public static void main(String[] args) {
    int[] numbers = {2, 7, 11, 15};
    int target = 22;

    List<Integer> l1 = new ArrayList<>();
    outer:
    for (int i = 0; i < numbers.length; i++) {
        for (int j = 0; j < numbers.length; j++) {
            if (i != j && numbers[i]+numbers[j] == target) {
                l1.add(i);
                l1.add(j);
                break outer;
            }
        }
    }

    System.out.println(l1);
}
```


```javascript title="JavaScript"
let numbers = [2, 7, 11, 15];
let target = 22;

let l1 = [];
outer:
for (let i = 0; i < numbers.length; i++) {
  for (let j = 0; j < numbers.length; j++) {
    if (i != j && numbers[i] + numbers[j] == target) {
      l1.push(i);
      l1.push(j);
      break outer;
    }
  }
}

console.log(l1);
```


```python title="Python"
numbers = [2, 7, 11, 15]
target = 22

def findTowSum(nums):
    l1 = []
    for i in range(len(numbers)):
        for j in range(len(numbers)):
            if i != j and numbers[i] + numbers[j] == target:
                return [i, j]
            

print(findTowSum(numbers))
```
</details>
