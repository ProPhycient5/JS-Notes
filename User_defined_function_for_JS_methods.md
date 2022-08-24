//user-defined map() for Array
```
Array.prototype.calculate = function (fn) {
    const output = [];
    for (let i = 0; i < this.length; i++){
        output.push(fn(this[i]));
    }
    return output;
}
```

//user-defined filter() for Array

```
Array.prototype.calculate = function (fn) {
    const output = [];
    for (let i = 0; i < this.length; i++){
        if(fn(this[i]))
          output.push(this[i]);
    }
    return output;
}
```

//user-defined reduce() for Array
```
Array.prototype.calculate = function (acc, fn) {
    const output = acc;
    for (let i = 0; i < this.length; i++){
        output = fn(output, this[i]);
    }
    return output;
}
```

**Where fn is the function for logic that user compute**
