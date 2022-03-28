
#### In order to print the full name of the above objects(multiple objects), we need a function, so to use that our-own-created `function`, we use `call()` method. `call()` method takes 1st param as reference(i.e. owner object or function contained variable), rest are the arguments for the reference function/object.
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


> **Function borrowing** - borrowing a function of one obj and using for another obj.
```
printFullName.call(name, "Bhadrak", "Odisha");
printFullName.call(name2, "Dehradun", "Uttrakhand");
```


#### In case of `apply()` method, it does the smae task as `call()`, only difference is way of taking params. i.e arguments are taken within array.
```
printFullName.apply(name2, ["Dehradun", "Uttrakhand"]);
```

#### Now in bind() method, it return a copy of that function which is invoked, instead of using directly unlike the above other two methods.
```
let printMyName = printFullName.bind(name, "Bhadrak", "Odisha");
console.log(printMyName);
printMyName();
```
> In all three methods, the 1st arguments is always target function/object/function-contained-variable.
