# Common JavaScript Interview Questions and Answers

Q1. Write a method `sum` that would work with the following syntax?
```js
console.log(sum(2,3));   // Outputs 5
console.log(sum(2)(3));  // Outputs 5
```
<details>
  <summary>Solution</summary>
  
```js
function sum(x) {
  if (arguments.length == 2) {
    return arguments[0] + arguments[1];
  } else {
    return function(y) { return x + y; };
  }
}
```
</details>

-----------------

Q2. What gets logged in the following code?
```js
(function() {
    console.log(1); 
    setTimeout(function(){console.log(2)}, 1000); 
    setTimeout(function(){console.log(3)}, 0); 
    console.log(4);
})();
```
<details>
  <summary>Solution</summary>
  
```
1
4
3
2
```
</details>

-------------------

Q3. What will be the output? How can we fix this?
```
for (var i = 0; i < 5; i++) {
	setTimeout(function() { console.log(i); }, i * 1000 );
}
```
<details>
  <summary>Solution</summary>

Output:
```
5
5
5
5
5
```

The fix:
1. Using `let`
```js
for (let i = 0; i < 5; i++) {
	setTimeout(function() { console.log(i); }, i * 1000 );
}
```

2. Using closures:
```js
for (let i = 0; i < 5; i++) {
	setTimeout(function() { console.log(i); }, i * 1000 );
}
```
</details>

--------------

Q4. What is the output?
```js
var x = 21;
var foo = function () {
    console.log(x);
    var x = 20;
};
foo();
```

<details>
  <summary>Solution</summary>
  
```
undefined
```
</details>

----------

Q5: What will be the output?
```js
console.log(1 < 2 < 3);
console.log(3 > 2 > 1);
```
<details>
  <summary>Solution</summary>
  
```
true
false
```
</details>

--------

Q6: What will be the output?
```js
var b = 1;
function outer(){
   	var b = 2
    function inner(){
        b++;
        var b = 3;
        console.log(b)
    }
    inner();
}
outer();
```
<details>
  <summary>Solution</summary>
  
```
3
```
</details>

