# Advanced JavaScript

## 2. Regex
### i. Check whether it contains somthing with pattern
```javascript title="JavaScript"
let str = "The price is $123.45 and the discount is $12.34 and round total is 111";
let pattern = /discount/

console.log(pattern.test(str));
```

### ii. Extract the first matching with pattern.
```javascript title="JavaScript"
let str = "The price is $123.45 and the discount is $12.34 and round total is 111";
let pattern = /(\d+(\.\d+)?)/

console.log(str.match(pattern)[0]);
```

### iii. Extract all matching with pattern - Approach 1.
```javascript title="JavaScript"
let str = "The price is $123.45 and the discount is $12.34 and round total is 111";
let pattern = /(\d+(\.\d+)?)/g

while ((value = pattern.exec(str)) != null)
    console.log(value[0]);
```

### iv. Extract all matching with pattern - Approach 2.
```javascript title="JavaScript"
let str = "The price is $123.45 and the discount is $12.34 and round total is 111";
let pattern = /(\d+(\.\d+)?)/g

let allMatched = str.matchAll(pattern);

for (let match of allMatched) {
    console.log(match[1]);
}
```

### v. Conclusion. ⭐⭐⭐
```javascript title="JavaScript"
let str = "The price is $123.45 and the discount is $12.34 and round total is 111";

console.log(/(\d+(\.\d+)?)/.test(str));             // true

console.log(str.match( /(\d+(\.\d+)?)/ )[0]);       // 123.45
console.log(str.match( /(\d+(\.\d+)?)/g ));         // [ '123.45', '12.34', '111' ]

console.log(str.matchAll( /(\d+(\.\d+)?)/g ));      // Object [RegExp String Iterator] {}
// for (i of str.matchAll(pattern))
//     console.log(i[0]);

let pattern = /(\d+(\.\d+)?)/g
console.log(pattern.exec(str)[0]);                  // 123.45
console.log(pattern.exec(str)[0]);                  // 12.34

```

## 3. Callback methods. ⭐⭐⭐
```javascript title="JavaScript"
let names = ['Sudha', 'Nagraj', 'Chethan'];

function myForEach(arr, callBack) {
    for (let i=0; i<arr.length; i++) {
        callBack(arr[i]);
    }
}

myForEach(names, (name) => {
    console.log(name);
})
```

## 4. Promises. ⭐⭐⭐
```javascript title="JavaScript"
let myPromise = new Promise((resolve, reject) => {

    setTimeout(() => {
        let response = true;

        if (!response)
            resolve("Successful!");
        else
            reject("Failed.");
    }, 3000);

})
```
```javascript title="JavaScript"
myPromise
    .then(result => console.log(result))
    .catch(err => console.log(err))
```

## 5. async & await. ⭐⭐⭐
```javascript title="JavaScript"
let myPromise = new Promise((resolve, reject) => {

    setTimeout(() => {
        let response = true;

        if (response)
            resolve("Successful!");
        else
            reject("Failed.");
    }, 3000);

})
```
```javascript title="JavaScript"
async function handlePromise() {
    try {
        console.log(await myPromise);
    } catch(err) {
        console.log(err);
    }
};

handlePromise();
```

## 6. Read TestData files.
### i. TestData.js file
```javascript title="JavaScript"
module.exports = {
    name: "Sachin",
    age: 27
}
```
```javascript title="JavaScript"
const testData = require('./TestData.js');

console.log(testData.name);
```

### ii. TestData.json file
```json
{
    "name": "Sachin",
    "age": 27
}
```
```javascript title="JavaScript"
const testData = require('./TestData.json');

console.log(testData.age);
```

### iii. TestData.ini file
```ini
[details]
name=Sachin
age=27

[address]
place=Bengaluru
```
```javascript title="JavaScript"
const fs = require('fs');
const ini = require('ini');

const config = ini.parse(fs.readFileSync('TestData.ini', 'utf-8'));

console.log(config.details.name, config.details.age);
```

### iv. TestData.yaml file
```yaml
person:
  name: John Doe
  age: 30
  address:
    street: 123 Main St
    city: Anytown
    postal_code: 12345
  hobbies:
    - Reading
    - Hiking
    - Coding
```
```javascript title="JavaScript"
const fs = require('fs');
const yaml = require('js-yaml');

const config = yaml.load(fs.readFileSync('TestData.yaml', 'utf-8'));

console.log(config.person.address.city);
console.log(config.person.hobbies[2]);
```

### v. .env file
```dotenv
PORT=3306
DB_URL=mysql://localhost:3306/mydatabase
API_KEY=your_api_key
```
```javascript title="JavaScript"
require('dotenv').config();

console.log(process.env.PORT);
```
