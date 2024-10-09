
| id                                 | hubs                            | source                                   |
| ---------------------------------- | ------------------------------- | ---------------------------------------- |
| 202410090044_Object Method Binding | [[hubs/JavaScript\|JavaScript]] | https://www.w3schools.com/js/js_this.asp |
In these examples, `this` is the **person object**:
```
const **person** = {  
  firstName  : "John",  
  lastName   : "Doe",  
  id         : 5566,  
  myFunction : function() {  
    return **this**;  //Object 
  }  
};
```

```
const **person** = {  
  firstName: "John",  
  lastName : "Doe",  
  id       : 5566,  
  fullName : function() {  
    return **this**.firstName + " " + **this**.lastName;   //John Doe
  }  
};
```