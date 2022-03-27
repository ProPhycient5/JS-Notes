

```
let name = {
 firstName: "Sawan",
 lastName: "Das",
}

let printFullName = function (homeTown , state){
    console.log(this.firstName + " " + this.lastName + " from " + homeTown + " in " + state);
 }
 
 let name2 = {
  firstName: "Akshay",
  lastName: "Saini",
}
 ```

### In order to print the full name of obj name2, we could have copy above printFullName key and its value as func
### But we will use call() method which takes 1st param as reference, rest are arguments for the function.



### function borrowing - borrowing a function of one obj and using for another obj.
```
printFullName.call(name, "Bhadrak", "Odisha");
printFullName.call(name2, "Dehradun", "Uttrakhand");
```


### now in apply() method, only difference is way of taking params. i.e arguments are taken within array.
```
printFullName.apply(name2, ["Dehradun", "Uttrakhand"]);
```

### Now in bind() method, it return a copy of that function and it is invoked instead of using directly in other two methods.
```
let printMyName = printFullName.bind(name, "Bhadrak", "Odisha");
console.log(printMyName);
printMyName();
```
