
| id                    | hubs                            | source                                                 |
| --------------------- | ------------------------------- | ------------------------------------------------------ |
| 202410041354_Untitled | [[hubs/JavaScript\|JavaScript]] | https://javascript.info/object#literals-and-properties |
```
let user = {

name: "John",

age: 30,

"likes birds": true //multiword key  must be quoted

};

user.isAdmin = true;

delete user.age;

console.log(user);
// { name: 'John', 'likes birds': true, isAdmin: true }
```
## Square Bracket
For multiword properties, the dot doesn't work
```
user.likes birds = true //doesn't work
```
so that we have to use square bracket to nest key
```
user["likes birds"] =true;
```
