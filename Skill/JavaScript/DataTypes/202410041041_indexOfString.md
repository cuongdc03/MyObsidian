
| id                   | hubs                            | source                                                                                          |
| -------------------- | ------------------------------- | ----------------------------------------------------------------------------------------------- |
| 202410041041_indexOf | [[hubs/JavaScript\|JavaScript]] | https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf |
To search find substring in a String 
Syntax
```
indexOf(searchString)
indexOf(searchString, position)

```
## Parametter
searchString: subString which we wanna find
position: beginning search index
## Return value 
The index of the first occurrence of searchString found, or -1 if not found
#### Return value when using an empty search string

Searching for an empty search string produces strange results. With no second argument, or with a second argument whose value is less than the calling string's length, the return value is the same as the value of the second argument:
```
"hello world".indexOf(""); // returns 0
"hello world".indexOf("", 0); // returns 0
"hello world".indexOf("", 3); // returns 3
"hello world".indexOf("", 8); // returns 8

```
But if the position out of string length, this will return the string length
The indexOf() method is case sensitive
```
"Blue Whale".indexOf("blue"); // returns -1
```

